# ReportInitiateShutdownHelperTelemetry

- ea: `0x1800303bc`
- end: `0x1800306d6`
- name: `ReportInitiateShutdownHelperTelemetry`
- size: `794`
- prototype: `__int64 __fastcall(wchar_t *Str)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002fe34`

## callees

- `0x180001008`
- `0x1800303bc`
- `0x180039a98`
- `0x180039f20`
- `0x18003c6a0`
- `0x18007205a`
- `0x1800720b0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180030410`
- `msvcrt!wcsrchr` at `0x1800305b6`
- `msvcrt!wcsrchr` at `0x180030410`
- `msvcrt!wcsrchr` at `0x1800305b6`
- `msvcrt!wcsstr` at `0x180030511`
- `msvcrt!wcsstr` at `0x180030511`
- `msvcrt!_wcsicmp` at `0x1800304f2`
- `msvcrt!_wcsicmp` at `0x1800304f2`
- `ntdll!RtlQueryPackageIdentity` at `0x180030484`
- `ntdll!RtlQueryPackageIdentity` at `0x180030484`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800304a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800304a1`
- `KERNEL32!GetModuleHandleW` at `0x180030527`
- `KERNEL32!GetModuleHandleW` at `0x180030543`
- `KERNEL32!GetModuleHandleW` at `0x180030559`
- `KERNEL32!GetModuleHandleW` at `0x18003056f`
- `KERNEL32!GetModuleHandleW` at `0x180030527`
- `KERNEL32!GetModuleHandleW` at `0x180030543`
- `KERNEL32!GetModuleHandleW` at `0x180030559`
- `KERNEL32!GetModuleHandleW` at `0x18003056f`

## string_xrefs

- `0x18003054f`: `dosvc.dll`
- `0x180030565`: `wuaueng.dll`
- `0x18003051d`: `usosvc.dll`
- `0x180030535`: `qmgr.dll`

## pseudocode

```c
__int64 __fastcall ReportInitiateShutdownHelperTelemetry(wchar_t *Str)
{
  wchar_t *v1; // r12
  const wchar_t *pShimData; // rbx
  wchar_t *v4; // rax
  wchar_t *v5; // rdi
  int v6; // r13d
  struct _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // rbx
  wchar_t *v8; // r14
  BOOL v9; // esi
  HMODULE ModuleHandleW; // rdi
  HMODULE v11; // rbx
  HMODULE v12; // rax
  bool v13; // cf
  wchar_t *v14; // rax
  __int64 result; // rax
  const wchar_t *v16; // rdx
  wchar_t *v17; // r9
  wchar_t *v18; // rdx
  wchar_t *v19; // r9
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  char v24[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v25; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+78h] [rbp-88h]
  char v27[16]; // [rsp+80h] [rbp-80h] BYREF
  char v28[16]; // [rsp+90h] [rbp-70h] BYREF
  char v29[16]; // [rsp+A0h] [rbp-60h] BYREF
  char v30[16]; // [rsp+B0h] [rbp-50h] BYREF
  char v31[16]; // [rsp+C0h] [rbp-40h] BYREF
  int *v32; // [rsp+D0h] [rbp-30h]
  __int64 v33; // [rsp+D8h] [rbp-28h]
  _BYTE v34[144]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v35[256]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR Buffer[264]; // [rsp+270h] [rbp+170h] BYREF

  v1 = 0;
  pShimData = (const wchar_t *)NtCurrentPeb()->pShimData;
  if ( pShimData )
  {
    v4 = wcsrchr(pShimData + 1438, 0x5Cu);
    if ( v4 )
      v1 = v4 + 1;
    else
      v1 = (wchar_t *)(pShimData + 1438);
  }
  v22 = 256;
  memset_0(v35, 0, sizeof(v35));
  v21 = 132;
  memset_0(v34, 0, 0x84u);
  RtlQueryPackageIdentity(-4, v35, &v22, v34, &v21, 0);
  v5 = 0;
  v6 = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 <= 0x102 && StringCbCatW(Buffer, 0x208u, L"\\svchost.exe") >= 0 )
  {
    ProcessParameters = NtCurrentPeb()->ProcessParameters;
    if ( !_wcsicmp(ProcessParameters->ImagePathName.Buffer, Buffer) )
    {
      v8 = wcsstr(ProcessParameters->CommandLine.Buffer, L" -s ");
      v9 = GetModuleHandleW(L"usosvc.dll") != 0;
      ModuleHandleW = GetModuleHandleW(L"qmgr.dll");
      v11 = GetModuleHandleW(L"dosvc.dll");
      v12 = GetModuleHandleW(L"wuaueng.dll");
      v13 = ModuleHandleW != 0;
      v5 = v8 + 4;
      v6 = v9 | (v13 ? 2 : 0) | (v11 != 0 ? 4 : 0) | (v12 != 0 ? 8 : 0);
      if ( !v8 )
        v5 = 0;
    }
  }
  if ( Str )
  {
    v14 = wcsrchr(Str, 0x5Cu);
    Str = v14;
    if ( v14 )
      Str = v14 + 1;
  }
  result = (unsigned int)dword_1800AE088;
  if ( (unsigned int)dword_1800AE088 > 5 )
  {
    result = tlgKeywordOn(&dword_1800AE088, 0x400000000000LL);
    if ( (_BYTE)result )
    {
      v23 = 0x1000000;
      v25 = &v23;
      v26 = 8;
      v16 = &P;
      if ( Str )
        v16 = Str;
      tlgCreate1Sz_wchar_t(v27, v16);
      v18 = v17;
      if ( v1 )
        v18 = v1;
      tlgCreate1Sz_wchar_t(v28, v18);
      tlgCreate1Sz_wchar_t(v29, v35);
      tlgCreate1Sz_wchar_t(v30, v34);
      if ( v5 )
        v19 = v5;
      tlgCreate1Sz_wchar_t(v31, v19);
      v32 = &v20;
      v33 = 4;
      return tlgWriteTransfer_EventWriteTransfer(&dword_1800AE088, byte_180099139, 0, 0, 9, v24, v6, v21, v22, v23);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800303bc  push    rbp
0x1800303be  push    rbx
0x1800303bf  push    rsi
0x1800303c0  push    rdi
0x1800303c1  push    r12
0x1800303c3  push    r13
0x1800303c5  push    r14
0x1800303c7  push    r15
0x1800303c9  lea     rbp, [rsp-398h]
0x1800303d1  sub     rsp, 498h
0x1800303d8  mov     rax, cs:__security_cookie
0x1800303df  xor     rax, rsp
0x1800303e2  mov     [rbp+3D0h+var_50], rax
0x1800303e9  mov     rax, gs:60h
0x1800303f2  xor     r12d, r12d
0x1800303f5  mov     r15, rcx
0x1800303f8  mov     rbx, [rax+2D8h]
0x1800303ff  test    rbx, rbx
0x180030402  jz      short loc_180030431
0x180030404  lea     edx, [r12+5Ch]; Ch
0x180030409  lea     rcx, [rbx+0B3Ch]; Str
0x180030410  call    cs:__imp_wcsrchr
0x180030417  nop     dword ptr [rax+rax+00h]
0x18003041c  mov     r12, rax
0x18003041f  test    rax, rax
0x180030422  jz      short loc_18003042A
0x180030424  add     r12, 2
0x180030428  jmp     short loc_180030431
0x18003042a  lea     r12, [rbx+0B3Ch]
0x180030431  mov     r8d, 100h; Size
0x180030437  lea     rcx, [rbp+3D0h+var_360]; void *
0x18003043b  xor     edx, edx; Val
0x18003043d  mov     [rsp+4D0h+var_490], r8
0x180030442  call    memset_0
0x180030447  mov     r8d, 84h; Size
0x18003044d  lea     rcx, [rbp+3D0h+var_3F0]; void *
0x180030451  xor     edx, edx; Val
0x180030453  mov     [rsp+4D0h+var_498], r8
0x180030458  call    memset_0
0x18003045d  lea     rax, [rsp+4D0h+var_498]
0x180030462  mov     [rsp+4D0h+var_4A8], 0
0x18003046b  lea     r9, [rbp+3D0h+var_3F0]
0x18003046f  mov     [rsp+4D0h+var_4B0], rax
0x180030474  lea     r8, [rsp+4D0h+var_490]
0x180030479  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x180030480  lea     rdx, [rbp+3D0h+var_360]
0x180030484  call    cs:__imp_RtlQueryPackageIdentity
0x18003048b  nop     dword ptr [rax+rax+00h]
0x180030490  mov     edx, 104h; uSize
0x180030495  lea     rcx, [rbp+3D0h+Buffer]; lpBuffer
0x18003049c  xor     edi, edi
0x18003049e  xor     r13d, r13d
0x1800304a1  call    cs:__imp_GetSystemDirectoryW
0x1800304a8  nop     dword ptr [rax+rax+00h]
0x1800304ad  dec     eax
0x1800304af  cmp     eax, 102h
0x1800304b4  ja      loc_1800305A9
0x1800304ba  lea     r8, aSvchostExe; "\\svchost.exe"
0x1800304c1  mov     edx, 208h; cbDest
0x1800304c6  lea     rcx, [rbp+3D0h+Buffer]; pszDest
0x1800304cd  call    StringCbCatW
0x1800304d2  test    eax, eax
0x1800304d4  js      loc_1800305A9
0x1800304da  mov     rax, gs:60h
0x1800304e3  lea     rdx, [rbp+3D0h+Buffer]; String2
0x1800304ea  mov     rbx, [rax+20h]
0x1800304ee  mov     rcx, [rbx+68h]; String1
0x1800304f2  call    cs:__imp__wcsicmp
0x1800304f9  nop     dword ptr [rax+rax+00h]
0x1800304fe  test    eax, eax
0x180030500  jnz     loc_1800305A9
0x180030506  mov     rcx, [rbx+78h]; Str
0x18003050a  lea     rdx, aS_0; " -s "
0x180030511  call    cs:__imp_wcsstr
0x180030518  nop     dword ptr [rax+rax+00h]
0x18003051d  lea     rcx, aUsosvcDll; "usosvc.dll"
0x180030524  mov     r14, rax
0x180030527  call    cs:__imp_GetModuleHandleW
0x18003052e  nop     dword ptr [rax+rax+00h]
0x180030533  xor     esi, esi
0x180030535  lea     rcx, aQmgrDll; "qmgr.dll"
0x18003053c  test    rax, rax
0x18003053f  setnz   sil
0x180030543  call    cs:__imp_GetModuleHandleW
0x18003054a  nop     dword ptr [rax+rax+00h]
0x18003054f  lea     rcx, aDosvcDll; "dosvc.dll"
0x180030556  mov     rdi, rax
0x180030559  call    cs:__imp_GetModuleHandleW
0x180030560  nop     dword ptr [rax+rax+00h]
0x180030565  lea     rcx, aWuauengDll; "wuaueng.dll"
0x18003056c  mov     rbx, rax
0x18003056f  call    cs:__imp_GetModuleHandleW
0x180030576  nop     dword ptr [rax+rax+00h]
0x18003057b  neg     rax
0x18003057e  sbb     r13d, r13d
0x180030581  and     r13d, 8
0x180030585  neg     rbx
0x180030588  sbb     ecx, ecx
0x18003058a  and     ecx, 4
0x18003058d  or      r13d, ecx
0x180030590  neg     rdi
0x180030593  lea     rdi, [r14+8]
0x180030597  sbb     eax, eax
0x180030599  and     eax, 2
0x18003059c  or      r13d, eax
0x18003059f  or      r13d, esi
0x1800305a2  test    r14, r14
0x1800305a5  cmovz   rdi, r14
0x1800305a9  test    r15, r15
0x1800305ac  jz      short loc_1800305CE
0x1800305ae  mov     edx, 5Ch ; '\'; Ch
0x1800305b3  mov     rcx, r15; Str
0x1800305b6  call    cs:__imp_wcsrchr
0x1800305bd  nop     dword ptr [rax+rax+00h]
0x1800305c2  mov     r15, rax
0x1800305c5  test    rax, rax
0x1800305c8  jz      short loc_1800305CE
0x1800305ca  add     r15, 2
0x1800305ce  mov     eax, cs:dword_1800AE088
0x1800305d4  cmp     eax, 5
0x1800305d7  jbe     loc_1800306B2
0x1800305dd  mov     rdx, 400000000000h
0x1800305e7  lea     rcx, dword_1800AE088
0x1800305ee  call    _tlgKeywordOn
0x1800305f3  test    al, al
0x1800305f5  jz      loc_1800306B2
0x1800305fb  lea     rax, [rsp+4D0h+var_488]
0x180030600  mov     [rsp+4D0h+var_488], 1000000h
0x180030609  lea     r9, P
0x180030610  mov     [rsp+4D0h+var_460], rax
0x180030615  test    r15, r15
0x180030618  mov     [rsp+4D0h+var_458], 8
0x180030621  mov     rdx, r9
0x180030624  lea     rcx, [rbp+3D0h+var_450]
0x180030628  cmovnz  rdx, r15
0x18003062c  call    _tlgCreate1Sz_wchar_t
0x180030631  test    r12, r12
0x180030634  lea     rcx, [rbp+3D0h+var_440]
0x180030638  mov     rdx, r9
0x18003063b  cmovnz  rdx, r12
0x18003063f  call    _tlgCreate1Sz_wchar_t
0x180030644  lea     rdx, [rbp+3D0h+var_360]
0x180030648  lea     rcx, [rbp+3D0h+var_430]
0x18003064c  call    _tlgCreate1Sz_wchar_t
0x180030651  lea     rdx, [rbp+3D0h+var_3F0]
0x180030655  lea     rcx, [rbp+3D0h+var_420]
0x180030659  call    _tlgCreate1Sz_wchar_t
0x18003065e  test    rdi, rdi
0x180030661  lea     rcx, [rbp+3D0h+var_410]
0x180030665  cmovnz  r9, rdi
0x180030669  mov     rdx, r9
0x18003066c  call    _tlgCreate1Sz_wchar_t
0x180030671  lea     rax, [rsp+4D0h+var_4A0]
0x180030676  mov     [rsp+4D0h+var_4A0], r13d
0x18003067b  mov     [rbp+3D0h+var_400], rax
0x18003067f  lea     rdx, byte_180099139
0x180030686  lea     rax, [rsp+4D0h+var_480]
0x18003068b  mov     [rbp+3D0h+var_3F8], 4
0x180030693  mov     [rsp+4D0h+var_4A8], rax
0x180030698  lea     rcx, dword_1800AE088
0x18003069f  xor     r9d, r9d
0x1800306a2  mov     dword ptr [rsp+4D0h+var_4B0], 9
0x1800306aa  xor     r8d, r8d
0x1800306ad  call    _tlgWriteTransfer_EventWriteTransfer
0x1800306b2  mov     rcx, [rbp+3D0h+var_50]
0x1800306b9  xor     rcx, rsp; StackCookie
0x1800306bc  call    __security_check_cookie
0x1800306c1  add     rsp, 498h
0x1800306c8  pop     r15
0x1800306ca  pop     r14
0x1800306cc  pop     r13
0x1800306ce  pop     r12
0x1800306d0  pop     rdi
0x1800306d1  pop     rsi
0x1800306d2  pop     rbx
0x1800306d3  pop     rbp
0x1800306d4  retn
```
