# UtilGetProcessName(ulong,wchar_t *,unsigned __int64)

- ea: `0x140030550`
- end: `0x1400306eb`
- name: `?UtilGetProcessName@@YAJKPEA_W_K@Z`
- size: `411`
- prototype: `int(unsigned int, wchar_t *, unsigned __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001b2dc`
- `0x140029a14`
- `0x140029f8c`
- `0x14002c4f4`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x14000b4cc`
- `0x140015b40`
- `0x140030550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003069d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003069d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400306bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400306bb`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x14003065c`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x14003065c`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x14003067a`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x14003067a`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x140030633`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x140030633`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilGetProcessName(__int64 a1, wchar_t *a2, unsigned __int64 a3)
{
  int v5; // ebp
  PROCESSENTRY32W *p_pe; // rcx
  _OWORD *v7; // rax
  __int64 v8; // rdx
  HANDLE Toolhelp32Snapshot; // rax
  void *v10; // rdi
  unsigned __int64 v11; // r14
  unsigned int v12; // ebx
  signed int LastError; // eax
  _BYTE v15[576]; // [rsp+30h] [rbp-4A8h] BYREF
  PROCESSENTRY32W pe; // [rsp+270h] [rbp-268h] BYREF

  v5 = a1;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  memset_0(a2, 0, 2 * a3);
  memset_0(v15, 0, 0x238u);
  p_pe = &pe;
  v7 = v15;
  v8 = 4;
  do
  {
    *(_OWORD *)&p_pe->dwSize = *v7;
    *(_OWORD *)&p_pe->th32DefaultHeapID = v7[1];
    *(_OWORD *)&p_pe->th32ParentProcessID = v7[2];
    *(_OWORD *)&p_pe->szExeFile[2] = v7[3];
    *(_OWORD *)&p_pe->szExeFile[10] = v7[4];
    *(_OWORD *)&p_pe->szExeFile[18] = v7[5];
    *(_OWORD *)&p_pe->szExeFile[26] = v7[6];
    *(_OWORD *)&p_pe->szExeFile[34] = v7[7];
    p_pe = (PROCESSENTRY32W *)((char *)p_pe + 128);
    v7 += 8;
    --v8;
  }
  while ( v8 );
  *(_OWORD *)&p_pe->dwSize = *v7;
  *(_OWORD *)&p_pe->th32DefaultHeapID = v7[1];
  *(_OWORD *)&p_pe->th32ParentProcessID = v7[2];
  *(_QWORD *)&p_pe->szExeFile[2] = *((_QWORD *)v7 + 6);
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(2u, 0);
  v10 = Toolhelp32Snapshot;
  v11 = (unsigned __int64)Toolhelp32Snapshot + 1;
  if ( (unsigned __int64)Toolhelp32Snapshot + 1 > 1 && (pe.dwSize = 568, Process32FirstW(Toolhelp32Snapshot, &pe)) )
  {
    while ( pe.th32ProcessID != v5 )
    {
      if ( !Process32NextW(v10, &pe) )
        goto LABEL_11;
    }
    StringCchCopyW(a2, a3, pe.szExeFile);
LABEL_11:
    v12 = 0;
  }
  else
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v11 > 1 )
    CloseHandle(v10);
  return v12;
}

```

## disassembly

```asm
0x140030550  mov     [rsp+arg_0], rbx
0x140030555  mov     [rsp+arg_18], rbp
0x14003055a  push    rsi
0x14003055b  push    rdi
0x14003055c  push    r14
0x14003055e  sub     rsp, 4C0h
0x140030565  mov     rax, cs:__security_cookie
0x14003056c  xor     rax, rsp
0x14003056f  mov     [rsp+4D8h+var_28], rax
0x140030577  mov     rsi, r8
0x14003057a  mov     rbx, rdx
0x14003057d  mov     ebp, ecx
0x14003057f  test    rdx, rdx
0x140030582  jnz     short loc_140030589
0x140030584  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140030589  mov     [rsp+4D8h+var_4B8], 0
0x140030592  lea     r8, [rsi+rsi]; Size
0x140030596  xor     edx, edx; Val
0x140030598  mov     rcx, rbx; void *
0x14003059b  call    memset_0
0x1400305a0  xor     edx, edx; Val
0x1400305a2  mov     r8d, 238h; Size
0x1400305a8  lea     rcx, [rsp+4D8h+var_4A8]; void *
0x1400305ad  call    memset_0
0x1400305b2  lea     rcx, [rsp+4D8h+pe]
0x1400305ba  lea     rax, [rsp+4D8h+var_4A8]
0x1400305bf  mov     edx, 4
0x1400305c4  lea     r8d, [rdx+7Ch]
0x1400305c8  movups  xmm0, xmmword ptr [rax]
0x1400305cb  movups  xmmword ptr [rcx], xmm0
0x1400305ce  movups  xmm1, xmmword ptr [rax+10h]
0x1400305d2  movups  xmmword ptr [rcx+10h], xmm1
0x1400305d6  movups  xmm0, xmmword ptr [rax+20h]
0x1400305da  movups  xmmword ptr [rcx+20h], xmm0
0x1400305de  movups  xmm1, xmmword ptr [rax+30h]
0x1400305e2  movups  xmmword ptr [rcx+30h], xmm1
0x1400305e6  movups  xmm0, xmmword ptr [rax+40h]
0x1400305ea  movups  xmmword ptr [rcx+40h], xmm0
0x1400305ee  movups  xmm1, xmmword ptr [rax+50h]
0x1400305f2  movups  xmmword ptr [rcx+50h], xmm1
0x1400305f6  movups  xmm0, xmmword ptr [rax+60h]
0x1400305fa  movups  xmmword ptr [rcx+60h], xmm0
0x1400305fe  movups  xmm1, xmmword ptr [rax+70h]
0x140030602  movups  xmmword ptr [rcx+70h], xmm1
0x140030606  add     rcx, r8
0x140030609  add     rax, r8
0x14003060c  sub     rdx, 1; th32ProcessID
0x140030610  jnz     short loc_1400305C8
0x140030612  movups  xmm0, xmmword ptr [rax]
0x140030615  movups  xmmword ptr [rcx], xmm0
0x140030618  movups  xmm1, xmmword ptr [rax+10h]
0x14003061c  movups  xmmword ptr [rcx+10h], xmm1
0x140030620  movups  xmm0, xmmword ptr [rax+20h]
0x140030624  movups  xmmword ptr [rcx+20h], xmm0
0x140030628  mov     rax, [rax+30h]
0x14003062c  mov     [rcx+30h], rax
0x140030630  lea     ecx, [rdx+2]; dwFlags
0x140030633  call    cs:__imp_CreateToolhelp32Snapshot
0x140030639  mov     rdi, rax
0x14003063c  lea     r14, [rax+1]
0x140030640  cmp     r14, 1
0x140030644  jbe     short loc_14003069D
0x140030646  mov     [rsp+4D8h+pe.dwSize], 238h
0x140030651  lea     rdx, [rsp+4D8h+pe]; lppe
0x140030659  mov     rcx, rax; hSnapshot
0x14003065c  call    cs:__imp_Process32FirstW
0x140030662  test    eax, eax
0x140030664  jz      short loc_14003069D
0x140030666  cmp     [rsp+4D8h+pe.th32ProcessID], ebp
0x14003066d  jz      short loc_140030686
0x14003066f  lea     rdx, [rsp+4D8h+pe]; lppe
0x140030677  mov     rcx, rdi; hSnapshot
0x14003067a  call    cs:__imp_Process32NextW
0x140030680  test    eax, eax
0x140030682  jnz     short loc_140030666
0x140030684  jmp     short loc_140030699
0x140030686  lea     r8, [rsp+4D8h+pe.szExeFile]; wchar_t *
0x14003068e  mov     rdx, rsi; unsigned __int64
0x140030691  mov     rcx, rbx; wchar_t *
0x140030694  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140030699  xor     ebx, ebx
0x14003069b  jmp     short loc_1400306B2
0x14003069d  call    cs:__imp_GetLastError
0x1400306a3  test    eax, eax
0x1400306a5  mov     ebx, eax
0x1400306a7  jle     short loc_1400306B2
0x1400306a9  movzx   ebx, ax
0x1400306ac  or      ebx, 80070000h
0x1400306b2  cmp     r14, 1
0x1400306b6  jbe     short loc_1400306C1
0x1400306b8  mov     rcx, rdi; hObject
0x1400306bb  call    cs:__imp_CloseHandle
0x1400306c1  mov     eax, ebx
0x1400306c3  mov     rcx, [rsp+4D8h+var_28]
0x1400306cb  xor     rcx, rsp; StackCookie
0x1400306ce  call    __security_check_cookie
0x1400306d3  lea     r11, [rsp+4D8h+var_18]
0x1400306db  mov     rbx, [r11+20h]
0x1400306df  mov     rbp, [r11+38h]
0x1400306e3  mov     rsp, r11
0x1400306e6  pop     r14
0x1400306e8  pop     rdi
0x1400306e9  pop     rsi
0x1400306ea  retn
```
