# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x1400561c4`
- end: `0x1400563bc`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `504`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140032628`

## callees

- `0x14000332b`
- `0x14000a9c4`
- `0x140055cd4`
- `0x140055de0`
- `0x1400561c4`
- `0x1400565e0`
- `0x140056784`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140056214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140056214`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14005620a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14005620a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400561f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400561f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005624a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005624a`
- `ntdll!RtlFreeHeap` at `0x140056351`
- `ntdll!RtlFreeHeap` at `0x14005637d`
- `ntdll!RtlFreeHeap` at `0x1400563a4`
- `ntdll!RtlFreeHeap` at `0x140056351`
- `ntdll!RtlFreeHeap` at `0x14005637d`
- `ntdll!RtlFreeHeap` at `0x1400563a4`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetProcessAppId(HANDLE ProcessHandle, _QWORD *a2, unsigned __int16 **a3)
{
  const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **v5; // r9
  signed int LastError; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdx
  PVOID v9; // r8
  const unsigned __int16 *v10; // rcx
  int v11; // eax
  void *v12; // rbx
  unsigned int AppUserModelId; // eax
  void *v14; // rdx
  unsigned int v15; // r8d
  unsigned int v16; // edi
  PVOID P[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  void *TokenHandle; // [rsp+40h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+48h] [rbp+18h] BYREF

  *a2 = 0;
  *(_OWORD *)P = 0;
  TokenHandle = 0;
  if ( ProcessHandle == GetCurrentProcess() )
  {
    v7 = -4;
    TokenHandle = (void *)-4LL;
  }
  else
  {
    if ( !OpenProcessToken(ProcessHandle, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_8;
    }
    v7 = (__int64)TokenHandle;
  }
  LastError = ARI::ProcessToken::SysAppId::Open((HANDLE)v7, P, (const UNICODE_STRING **)&P[1], v5);
  if ( TokenHandle != (void *)-4LL )
    CloseHandle(TokenHandle);
LABEL_8:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023728 || LastError == -2147024891 )
  {
    v9 = P[0];
    if ( !P[0] )
      return (unsigned int)LastError;
LABEL_28:
    if ( v9 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
    return (unsigned int)LastError;
  }
  if ( LastError < 0 )
  {
    v8 = 165;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)(unsigned int)LastError,
      (int)P[0]);
LABEL_15:
    v9 = P[0];
    goto LABEL_28;
  }
  LODWORD(TokenHandle) = 0;
  if ( ARI::ProcessToken::AutoSysAppId::GetAppUserModelId(
         (ARI::ProcessToken::AutoSysAppId *)P,
         0,
         (unsigned int *)&TokenHandle,
         0) != 122 )
  {
    LastError = -2147418113;
    v8 = 168;
    goto LABEL_14;
  }
  pv = 0;
  CoTaskMemFree_0(0);
  v11 = CoAllocStringLen(v10, (unsigned int)TokenHandle, (unsigned __int16 **)&pv);
  LastError = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)(unsigned int)v11,
      (int)P[0]);
    CoTaskMemFree_0(pv);
    goto LABEL_15;
  }
  v12 = pv;
  AppUserModelId = ARI::ProcessToken::AutoSysAppId::GetAppUserModelId(
                     (ARI::ProcessToken::AutoSysAppId *)P,
                     (unsigned int)TokenHandle,
                     (unsigned int *)&TokenHandle,
                     (unsigned __int16 *)pv);
  if ( AppUserModelId )
  {
    v16 = wil::details::in1diag3::Return_Win32(retaddr, v14, v15, (const char *)AppUserModelId, (unsigned int)P[0]);
    CoTaskMemFree_0(v12);
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    return v16;
  }
  else
  {
    *a2 = v12;
    CoTaskMemFree_0(0);
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    return 0;
  }
}

```

## disassembly

```asm
0x1400561c4  mov     [rsp-8+arg_10], rbx
0x1400561c9  mov     [rsp-8+arg_18], rdi
0x1400561ce  push    rbp
0x1400561cf  mov     rbp, rsp
0x1400561d2  sub     rsp, 30h
0x1400561d6  xorps   xmm0, xmm0
0x1400561d9  mov     qword ptr [rdx], 0
0x1400561e0  movdqu  xmmword ptr [rbp+P], xmm0
0x1400561e5  mov     rdi, rdx
0x1400561e8  mov     [rbp+TokenHandle], 0
0x1400561f0  mov     rbx, rcx
0x1400561f3  call    cs:__imp_GetCurrentProcess
0x1400561f9  cmp     rbx, rax
0x1400561fc  jz      short loc_140056226
0x1400561fe  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140056202  mov     edx, 8; DesiredAccess
0x140056207  mov     rcx, rbx; ProcessHandle
0x14005620a  call    cs:__imp_OpenProcessToken
0x140056210  test    eax, eax
0x140056212  jnz     short loc_140056220
0x140056214  call    cs:__imp_GetLastError
0x14005621a  mov     ebx, eax
0x14005621c  test    eax, eax
0x14005621e  jnz     short loc_140056250
0x140056220  mov     rcx, [rbp+TokenHandle]
0x140056224  jmp     short loc_140056231
0x140056226  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x14005622d  mov     [rbp+TokenHandle], rcx
0x140056231  lea     r8, [rbp+P+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x140056235  lea     rdx, [rbp+P]; void *
0x140056239  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x14005623e  mov     rcx, [rbp+TokenHandle]; hObject
0x140056242  mov     ebx, eax
0x140056244  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x140056248  jz      short loc_140056250
0x14005624a  call    cs:__imp_CloseHandle
0x140056250  test    ebx, ebx
0x140056252  jle     short loc_14005625D
0x140056254  movzx   ebx, bx
0x140056257  or      ebx, 80070000h
0x14005625d  cmp     ebx, 80070490h
0x140056263  jz      loc_140056387
0x140056269  cmp     ebx, 80070005h
0x14005626f  jz      loc_140056387
0x140056275  test    ebx, ebx
0x140056277  jns     short loc_14005629A
0x140056279  mov     edx, 0A5h; void *
0x14005627e  mov     rcx, [rbp+8]; this
0x140056282  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x140056289  mov     r9d, ebx; char *
0x14005628c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140056291  mov     r8, [rbp+P]
0x140056295  jmp     loc_140056390
0x14005629a  xor     r9d, r9d; unsigned __int16 *
0x14005629d  mov     dword ptr [rbp+TokenHandle], 0
0x1400562a4  lea     r8, [rbp+TokenHandle]; unsigned int *
0x1400562a8  xor     edx, edx; unsigned int
0x1400562aa  lea     rcx, [rbp+P]; this
0x1400562ae  call    ?GetAppUserModelId@AutoSysAppId@ProcessToken@ARI@@QEBAJIPEAIPEAG@Z; ARI::ProcessToken::AutoSysAppId::GetAppUserModelId(uint,uint *,ushort *)
0x1400562b3  cmp     eax, 7Ah ; 'z'
0x1400562b6  jz      short loc_1400562C4
0x1400562b8  mov     ebx, 8000FFFFh
0x1400562bd  mov     edx, 0A8h
0x1400562c2  jmp     short loc_14005627E
0x1400562c4  xor     ecx, ecx; pv
0x1400562c6  mov     [rbp+pv], 0
0x1400562ce  call    CoTaskMemFree_0
0x1400562d3  mov     edx, dword ptr [rbp+TokenHandle]; unsigned __int64
0x1400562d6  lea     r8, [rbp+pv]; unsigned __int16 **
0x1400562da  call    ?CoAllocStringLen@@YAJPEBG_KPEAPEAG@Z; CoAllocStringLen(ushort const *,unsigned __int64,ushort * *)
0x1400562df  mov     ebx, eax
0x1400562e1  test    eax, eax
0x1400562e3  jns     short loc_140056308
0x1400562e5  mov     rcx, [rbp+8]; this
0x1400562e9  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1400562f0  mov     r9d, eax; char *
0x1400562f3  mov     edx, 0ABh; void *
0x1400562f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400562fd  mov     rcx, [rbp+pv]; pv
0x140056301  call    CoTaskMemFree_0
0x140056306  jmp     short loc_140056291
0x140056308  mov     rbx, [rbp+pv]
0x14005630c  lea     r8, [rbp+TokenHandle]; unsigned int *
0x140056310  mov     edx, dword ptr [rbp+TokenHandle]; unsigned int
0x140056313  lea     rcx, [rbp+P]; this
0x140056317  mov     r9, rbx; unsigned __int16 *
0x14005631a  call    ?GetAppUserModelId@AutoSysAppId@ProcessToken@ARI@@QEBAJIPEAIPEAG@Z; ARI::ProcessToken::AutoSysAppId::GetAppUserModelId(uint,uint *,ushort *)
0x14005631f  test    eax, eax
0x140056321  jz      short loc_14005635B
0x140056323  mov     rcx, [rbp+8]; this
0x140056327  mov     r9d, eax; char *
0x14005632a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14005632f  mov     rcx, rbx; pv
0x140056332  mov     edi, eax
0x140056334  call    CoTaskMemFree_0
0x140056339  mov     r8, [rbp+P]; P
0x14005633d  test    r8, r8
0x140056340  jz      short loc_140056357
0x140056342  mov     rcx, gs:60h
0x14005634b  xor     edx, edx; Flags
0x14005634d  mov     rcx, [rcx+30h]; HeapHandle
0x140056351  call    cs:__imp_RtlFreeHeap
0x140056357  mov     eax, edi
0x140056359  jmp     short loc_1400563AC
0x14005635b  xor     ecx, ecx; pv
0x14005635d  mov     [rdi], rbx
0x140056360  call    CoTaskMemFree_0
0x140056365  mov     r8, [rbp+P]; P
0x140056369  test    r8, r8
0x14005636c  jz      short loc_140056383
0x14005636e  mov     rcx, gs:60h
0x140056377  xor     edx, edx; Flags
0x140056379  mov     rcx, [rcx+30h]; HeapHandle
0x14005637d  call    cs:__imp_RtlFreeHeap
0x140056383  xor     eax, eax
0x140056385  jmp     short loc_1400563AC
0x140056387  mov     r8, [rbp+P]; P
0x14005638b  test    r8, r8
0x14005638e  jz      short loc_1400563AA
0x140056390  test    r8, r8
0x140056393  jz      short loc_1400563AA
0x140056395  mov     rcx, gs:60h
0x14005639e  xor     edx, edx; Flags
0x1400563a0  mov     rcx, [rcx+30h]; HeapHandle
0x1400563a4  call    cs:__imp_RtlFreeHeap
0x1400563aa  mov     eax, ebx
0x1400563ac  mov     rbx, [rsp+30h+arg_10]
0x1400563b1  mov     rdi, [rsp+30h+arg_18]
0x1400563b6  add     rsp, 30h
0x1400563ba  pop     rbp
0x1400563bb  retn
```
