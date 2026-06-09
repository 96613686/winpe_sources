# CAppScript::RunScript(ushort const *,ushort const *)

- ea: `0x180053928`
- end: `0x180053a7d`
- name: `?RunScript@CAppScript@@AEAAHPEBG0@Z`
- size: `341`
- prototype: `int(CAppScript *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180053a84`

## callees

- `0x180007960`
- `0x180053928`
- `0x1800582a2`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180053a2e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180053a2e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180053a1a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180053a1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053a39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053a44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053a39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053a44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053a4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053a4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053991`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053991`

## pseudocode

```c
__int64 __fastcall CAppScript::RunScript(CAppScript *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  unsigned int v5; // edi
  __int64 v6; // rax
  unsigned __int64 v7; // rsi
  unsigned __int16 *v8; // rax
  WCHAR *v9; // rbx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v13[16]; // [rsp+E0h] [rbp-20h] BYREF

  v5 = 0;
  *(_OWORD *)v13 = *(_OWORD *)L"cmd.exe /C %s";
  v6 = -1;
  *(_OWORD *)&v13[6] = *(_OWORD *)L"e /C %s";
  do
    ++v6;
  while ( a3[v6] );
  v7 = v6 + 14;
  v8 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v6 + 14));
  v9 = v8;
  if ( v8 )
  {
    if ( StringCchPrintfW(v8, v7, v13, a3) >= 0 )
    {
      memset_0(&StartupInfo.cb + 1, 0, 0x64u);
      StartupInfo.cb = 104;
      memset(&ProcessInformation, 0, sizeof(ProcessInformation));
      v5 = CreateProcessW(0, v9, 0, 0, 0, 0x10u, 0, a2, &StartupInfo, &ProcessInformation);
      if ( v5 )
      {
        WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
        CloseHandle(ProcessInformation.hProcess);
        CloseHandle(ProcessInformation.hThread);
      }
    }
    LocalFree(v9);
  }
  return v5;
}

```

## disassembly

```asm
0x180053928  mov     [rsp-8+arg_0], rbx
0x18005392d  mov     [rsp-8+arg_18], rsi
0x180053932  push    rbp
0x180053933  push    rdi
0x180053934  push    r12
0x180053936  push    r14
0x180053938  push    r15
0x18005393a  lea     rbp, [rsp-10h]
0x18005393f  sub     rsp, 110h
0x180053946  mov     rax, cs:__security_cookie
0x18005394d  xor     rax, rsp
0x180053950  mov     [rbp+30h+var_30], rax
0x180053954  movups  xmm0, xmmword ptr cs:aCmdExeCS; "cmd.exe /C %s"
0x18005395b  xor     r12d, r12d
0x18005395e  mov     r14, r8
0x180053961  movups  xmm1, xmmword ptr cs:aCmdExeCS+0Ch; "e /C %s"
0x180053968  mov     r15, rdx
0x18005396b  mov     edi, r12d
0x18005396e  movups  xmmword ptr [rbp+30h+var_50], xmm0
0x180053972  or      rax, 0FFFFFFFFFFFFFFFFh
0x180053976  movups  xmmword ptr [rbp+30h+var_50+0Ch], xmm1
0x18005397a  inc     rax
0x18005397d  cmp     [r8+rax*2], r12w
0x180053982  jnz     short loc_18005397A
0x180053984  lea     rsi, [rax+0Eh]
0x180053988  mov     ecx, 40h ; '@'; uFlags
0x18005398d  lea     rdx, [rsi+rsi]; uBytes
0x180053991  call    cs:__imp_LocalAlloc
0x180053997  mov     rbx, rax
0x18005399a  test    rax, rax
0x18005399d  jz      loc_180053A53
0x1800539a3  mov     r9, r14
0x1800539a6  lea     r8, [rbp+30h+var_50]; unsigned __int16 *
0x1800539aa  mov     rdx, rsi; unsigned __int64
0x1800539ad  mov     rcx, rax; unsigned __int16 *
0x1800539b0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800539b5  test    eax, eax
0x1800539b7  js      loc_180053A4A
0x1800539bd  xor     edx, edx; Val
0x1800539bf  lea     rcx, [rsp+130h+StartupInfo+4]; void *
0x1800539c4  lea     r8d, [rdx+64h]; Size
0x1800539c8  call    memset_0
0x1800539cd  xor     eax, eax
0x1800539cf  mov     [rsp+130h+StartupInfo.cb], 68h ; 'h'
0x1800539d7  mov     qword ptr [rsp+130h+ProcessInformation.dwProcessId], rax
0x1800539dc  xorps   xmm0, xmm0
0x1800539df  lea     rax, [rsp+130h+ProcessInformation]
0x1800539e4  xor     r9d, r9d; lpThreadAttributes
0x1800539e7  mov     [rsp+130h+lpProcessInformation], rax; lpProcessInformation
0x1800539ec  xor     r8d, r8d; lpProcessAttributes
0x1800539ef  lea     rax, [rsp+130h+StartupInfo]
0x1800539f4  mov     rdx, rbx; lpCommandLine
0x1800539f7  mov     [rsp+130h+lpStartupInfo], rax; lpStartupInfo
0x1800539fc  xor     ecx, ecx; lpApplicationName
0x1800539fe  mov     [rsp+130h+lpCurrentDirectory], r15; lpCurrentDirectory
0x180053a03  mov     [rsp+130h+lpEnvironment], r12; lpEnvironment
0x180053a08  mov     [rsp+130h+dwCreationFlags], 10h; dwCreationFlags
0x180053a10  mov     [rsp+130h+bInheritHandles], r12d; bInheritHandles
0x180053a15  movups  xmmword ptr [rsp+130h+ProcessInformation.hProcess], xmm0
0x180053a1a  call    cs:__imp_CreateProcessW
0x180053a20  mov     edi, eax
0x180053a22  test    eax, eax
0x180053a24  jz      short loc_180053A4A
0x180053a26  mov     rcx, [rsp+130h+ProcessInformation.hProcess]; hHandle
0x180053a2b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180053a2e  call    cs:__imp_WaitForSingleObject
0x180053a34  mov     rcx, [rsp+130h+ProcessInformation.hProcess]; hObject
0x180053a39  call    cs:__imp_CloseHandle
0x180053a3f  mov     rcx, [rsp+130h+ProcessInformation.hThread]; hObject
0x180053a44  call    cs:__imp_CloseHandle
0x180053a4a  mov     rcx, rbx; hMem
0x180053a4d  call    cs:__imp_LocalFree
0x180053a53  mov     eax, edi
0x180053a55  mov     rcx, [rbp+30h+var_30]
0x180053a59  xor     rcx, rsp; StackCookie
0x180053a5c  call    __security_check_cookie
0x180053a61  lea     r11, [rsp+130h+var_20]
0x180053a69  mov     rbx, [r11+30h]
0x180053a6d  mov     rsi, [r11+48h]
0x180053a71  mov     rsp, r11
0x180053a74  pop     r15
0x180053a76  pop     r14
0x180053a78  pop     r12
0x180053a7a  pop     rdi
0x180053a7b  pop     rbp
0x180053a7c  retn
```
