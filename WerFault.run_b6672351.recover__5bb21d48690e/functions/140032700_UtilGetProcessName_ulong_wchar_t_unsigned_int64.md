# UtilGetProcessName(ulong,wchar_t *,unsigned __int64)

- ea: `0x140032700`
- end: `0x1400328ba`
- name: `?UtilGetProcessName@@YAJKPEA_W_K@Z`
- size: `442`
- prototype: `int(unsigned int, wchar_t *, unsigned __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001c370`
- `0x14002b5d8`
- `0x14002bb50`
- `0x14002e2cc`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x14000b50c`
- `0x1400166ec`
- `0x140032700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003285f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003285f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140032883`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140032883`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x140032812`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x140032812`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x140032836`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x140032836`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1400327e3`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1400327e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilGetProcessName(__int64 a1, wchar_t *a2, unsigned __int64 a3, __int64 a4)
{
  int v6; // ebp
  PROCESSENTRY32W *p_pe; // rcx
  _OWORD *v8; // rax
  __int64 v9; // rdx
  HANDLE Toolhelp32Snapshot; // rax
  void *v11; // rdi
  unsigned __int64 v12; // r14
  unsigned int v13; // ebx
  signed int LastError; // eax
  _BYTE v16[576]; // [rsp+30h] [rbp-4A8h] BYREF
  PROCESSENTRY32W pe; // [rsp+270h] [rbp-268h] BYREF

  v6 = a1;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, 0, a3, a4);
  memset_0(a2, 0, 2 * a3);
  memset_0(v16, 0, 0x238u);
  p_pe = &pe;
  v8 = v16;
  v9 = 4;
  do
  {
    *(_OWORD *)&p_pe->dwSize = *v8;
    *(_OWORD *)&p_pe->th32DefaultHeapID = v8[1];
    *(_OWORD *)&p_pe->th32ParentProcessID = v8[2];
    *(_OWORD *)&p_pe->szExeFile[2] = v8[3];
    *(_OWORD *)&p_pe->szExeFile[10] = v8[4];
    *(_OWORD *)&p_pe->szExeFile[18] = v8[5];
    *(_OWORD *)&p_pe->szExeFile[26] = v8[6];
    *(_OWORD *)&p_pe->szExeFile[34] = v8[7];
    p_pe = (PROCESSENTRY32W *)((char *)p_pe + 128);
    v8 += 8;
    --v9;
  }
  while ( v9 );
  *(_OWORD *)&p_pe->dwSize = *v8;
  *(_OWORD *)&p_pe->th32DefaultHeapID = v8[1];
  *(_OWORD *)&p_pe->th32ParentProcessID = v8[2];
  *(_QWORD *)&p_pe->szExeFile[2] = *((_QWORD *)v8 + 6);
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(2u, 0);
  v11 = Toolhelp32Snapshot;
  v12 = (unsigned __int64)Toolhelp32Snapshot + 1;
  if ( (unsigned __int64)Toolhelp32Snapshot + 1 > 1 && (pe.dwSize = 568, Process32FirstW(Toolhelp32Snapshot, &pe)) )
  {
    while ( pe.th32ProcessID != v6 )
    {
      if ( !Process32NextW(v11, &pe) )
        goto LABEL_11;
    }
    StringCchCopyW(a2, a3, pe.szExeFile);
LABEL_11:
    v13 = 0;
  }
  else
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v12 > 1 )
    CloseHandle(v11);
  return v13;
}

```

## disassembly

```asm
0x140032700  mov     [rsp+arg_0], rbx
0x140032705  mov     [rsp+arg_18], rbp
0x14003270a  push    rsi
0x14003270b  push    rdi
0x14003270c  push    r14
0x14003270e  sub     rsp, 4C0h
0x140032715  mov     rax, cs:__security_cookie
0x14003271c  xor     rax, rsp
0x14003271f  mov     [rsp+4D8h+var_28], rax
0x140032727  mov     rsi, r8
0x14003272a  mov     rbx, rdx
0x14003272d  mov     ebp, ecx
0x14003272f  test    rdx, rdx
0x140032732  jnz     short loc_140032739
0x140032734  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140032739  mov     [rsp+4D8h+var_4B8], 0
0x140032742  lea     r8, [rsi+rsi]; Size
0x140032746  xor     edx, edx; Val
0x140032748  mov     rcx, rbx; void *
0x14003274b  call    memset_0
0x140032750  xor     edx, edx; Val
0x140032752  mov     r8d, 238h; Size
0x140032758  lea     rcx, [rsp+4D8h+var_4A8]; void *
0x14003275d  call    memset_0
0x140032762  lea     rcx, [rsp+4D8h+pe]
0x14003276a  lea     rax, [rsp+4D8h+var_4A8]
0x14003276f  mov     edx, 4
0x140032774  lea     r8d, [rdx+7Ch]
0x140032778  movups  xmm0, xmmword ptr [rax]
0x14003277b  movups  xmmword ptr [rcx], xmm0
0x14003277e  movups  xmm1, xmmword ptr [rax+10h]
0x140032782  movups  xmmword ptr [rcx+10h], xmm1
0x140032786  movups  xmm0, xmmword ptr [rax+20h]
0x14003278a  movups  xmmword ptr [rcx+20h], xmm0
0x14003278e  movups  xmm1, xmmword ptr [rax+30h]
0x140032792  movups  xmmword ptr [rcx+30h], xmm1
0x140032796  movups  xmm0, xmmword ptr [rax+40h]
0x14003279a  movups  xmmword ptr [rcx+40h], xmm0
0x14003279e  movups  xmm1, xmmword ptr [rax+50h]
0x1400327a2  movups  xmmword ptr [rcx+50h], xmm1
0x1400327a6  movups  xmm0, xmmword ptr [rax+60h]
0x1400327aa  movups  xmmword ptr [rcx+60h], xmm0
0x1400327ae  movups  xmm1, xmmword ptr [rax+70h]
0x1400327b2  movups  xmmword ptr [rcx+70h], xmm1
0x1400327b6  add     rcx, r8
0x1400327b9  add     rax, r8
0x1400327bc  sub     rdx, 1; th32ProcessID
0x1400327c0  jnz     short loc_140032778
0x1400327c2  movups  xmm0, xmmword ptr [rax]
0x1400327c5  movups  xmmword ptr [rcx], xmm0
0x1400327c8  movups  xmm1, xmmword ptr [rax+10h]
0x1400327cc  movups  xmmword ptr [rcx+10h], xmm1
0x1400327d0  movups  xmm0, xmmword ptr [rax+20h]
0x1400327d4  movups  xmmword ptr [rcx+20h], xmm0
0x1400327d8  mov     rax, [rax+30h]
0x1400327dc  mov     [rcx+30h], rax
0x1400327e0  lea     ecx, [rdx+2]; dwFlags
0x1400327e3  call    cs:__imp_CreateToolhelp32Snapshot
0x1400327ea  nop     dword ptr [rax+rax+00h]
0x1400327ef  mov     rdi, rax
0x1400327f2  lea     r14, [rax+1]
0x1400327f6  cmp     r14, 1
0x1400327fa  jbe     short loc_14003285F
0x1400327fc  mov     [rsp+4D8h+pe.dwSize], 238h
0x140032807  lea     rdx, [rsp+4D8h+pe]; lppe
0x14003280f  mov     rcx, rax; hSnapshot
0x140032812  call    cs:__imp_Process32FirstW
0x140032819  nop     dword ptr [rax+rax+00h]
0x14003281e  test    eax, eax
0x140032820  jz      short loc_14003285F
0x140032822  cmp     [rsp+4D8h+pe.th32ProcessID], ebp
0x140032829  jz      short loc_140032848
0x14003282b  lea     rdx, [rsp+4D8h+pe]; lppe
0x140032833  mov     rcx, rdi; hSnapshot
0x140032836  call    cs:__imp_Process32NextW
0x14003283d  nop     dword ptr [rax+rax+00h]
0x140032842  test    eax, eax
0x140032844  jnz     short loc_140032822
0x140032846  jmp     short loc_14003285B
0x140032848  lea     r8, [rsp+4D8h+pe.szExeFile]; wchar_t *
0x140032850  mov     rdx, rsi; unsigned __int64
0x140032853  mov     rcx, rbx; wchar_t *
0x140032856  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14003285b  xor     ebx, ebx
0x14003285d  jmp     short loc_14003287A
0x14003285f  call    cs:__imp_GetLastError
0x140032866  nop     dword ptr [rax+rax+00h]
0x14003286b  test    eax, eax
0x14003286d  mov     ebx, eax
0x14003286f  jle     short loc_14003287A
0x140032871  movzx   ebx, ax
0x140032874  or      ebx, 80070000h
0x14003287a  cmp     r14, 1
0x14003287e  jbe     short loc_14003288F
0x140032880  mov     rcx, rdi; hObject
0x140032883  call    cs:__imp_CloseHandle
0x14003288a  nop     dword ptr [rax+rax+00h]
0x14003288f  mov     eax, ebx
0x140032891  mov     rcx, [rsp+4D8h+var_28]
0x140032899  xor     rcx, rsp; StackCookie
0x14003289c  call    __security_check_cookie
0x1400328a1  lea     r11, [rsp+4D8h+var_18]
0x1400328a9  mov     rbx, [r11+20h]
0x1400328ad  mov     rbp, [r11+38h]
0x1400328b1  mov     rsp, r11
0x1400328b4  pop     r14
0x1400328b6  pop     rdi
0x1400328b7  pop     rsi
0x1400328b8  retn
```
