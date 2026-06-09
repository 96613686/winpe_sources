# ReportInitiateShutdownHelperTelemetry

- ea: `0x18002d6f4`
- end: `0x18002d9d1`
- name: `ReportInitiateShutdownHelperTelemetry`
- size: `733`
- prototype: `__int64 __fastcall(wchar_t *Str)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002d1e0`

## callees

- `0x180001008`
- `0x18002d6f4`
- `0x180035c48`
- `0x180035f28`
- `0x18003846c`
- `0x18006505a`
- `0x180065090`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002d748`
- `msvcrt!wcsrchr` at `0x18002d8b8`
- `msvcrt!wcsrchr` at `0x18002d748`
- `msvcrt!wcsrchr` at `0x18002d8b8`
- `msvcrt!wcsstr` at `0x18002d831`
- `msvcrt!wcsstr` at `0x18002d831`
- `msvcrt!_wcsicmp` at `0x18002d818`
- `msvcrt!_wcsicmp` at `0x18002d818`
- `ntdll!RtlQueryPackageIdentity` at `0x18002d7b6`
- `ntdll!RtlQueryPackageIdentity` at `0x18002d7b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002d7cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002d7cd`
- `KERNEL32!GetModuleHandleW` at `0x18002d841`
- `KERNEL32!GetModuleHandleW` at `0x18002d857`
- `KERNEL32!GetModuleHandleW` at `0x18002d867`
- `KERNEL32!GetModuleHandleW` at `0x18002d877`
- `KERNEL32!GetModuleHandleW` at `0x18002d841`
- `KERNEL32!GetModuleHandleW` at `0x18002d857`
- `KERNEL32!GetModuleHandleW` at `0x18002d867`
- `KERNEL32!GetModuleHandleW` at `0x18002d877`

## string_xrefs

- `0x18002d86d`: `wuaueng.dll`
- `0x18002d849`: `qmgr.dll`
- `0x18002d85d`: `dosvc.dll`
- `0x18002d837`: `usosvc.dll`

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
  result = (unsigned int)dword_18009F088;
  if ( (unsigned int)dword_18009F088 > 5 )
  {
    result = tlgKeywordOn(&dword_18009F088, 0x400000000000LL);
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
      return tlgWriteTransfer_EventWriteTransfer(&dword_18009F088, byte_18008AE21, 0, 0, 9, v24, v6, v21, v22, v23);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002d6f4  push    rbp
0x18002d6f6  push    rbx
0x18002d6f7  push    rsi
0x18002d6f8  push    rdi
0x18002d6f9  push    r12
0x18002d6fb  push    r13
0x18002d6fd  push    r14
0x18002d6ff  push    r15
0x18002d701  lea     rbp, [rsp-398h]
0x18002d709  sub     rsp, 498h
0x18002d710  mov     rax, cs:__security_cookie
0x18002d717  xor     rax, rsp
0x18002d71a  mov     [rbp+3D0h+var_50], rax
0x18002d721  mov     rax, gs:60h
0x18002d72a  xor     r12d, r12d
0x18002d72d  mov     r15, rcx
0x18002d730  mov     rbx, [rax+2D8h]
0x18002d737  test    rbx, rbx
0x18002d73a  jz      short loc_18002D763
0x18002d73c  lea     edx, [r12+5Ch]; Ch
0x18002d741  lea     rcx, [rbx+0B3Ch]; Str
0x18002d748  call    cs:__imp_wcsrchr
0x18002d74e  mov     r12, rax
0x18002d751  test    rax, rax
0x18002d754  jz      short loc_18002D75C
0x18002d756  add     r12, 2
0x18002d75a  jmp     short loc_18002D763
0x18002d75c  lea     r12, [rbx+0B3Ch]
0x18002d763  mov     r8d, 100h; Size
0x18002d769  lea     rcx, [rbp+3D0h+var_360]; void *
0x18002d76d  xor     edx, edx; Val
0x18002d76f  mov     [rsp+4D0h+var_490], r8
0x18002d774  call    memset_0
0x18002d779  mov     r8d, 84h; Size
0x18002d77f  lea     rcx, [rbp+3D0h+var_3F0]; void *
0x18002d783  xor     edx, edx; Val
0x18002d785  mov     [rsp+4D0h+var_498], r8
0x18002d78a  call    memset_0
0x18002d78f  lea     rax, [rsp+4D0h+var_498]
0x18002d794  mov     [rsp+4D0h+var_4A8], 0
0x18002d79d  lea     r9, [rbp+3D0h+var_3F0]
0x18002d7a1  mov     [rsp+4D0h+var_4B0], rax
0x18002d7a6  lea     r8, [rsp+4D0h+var_490]
0x18002d7ab  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x18002d7b2  lea     rdx, [rbp+3D0h+var_360]
0x18002d7b6  call    cs:__imp_RtlQueryPackageIdentity
0x18002d7bc  mov     edx, 104h; uSize
0x18002d7c1  lea     rcx, [rbp+3D0h+Buffer]; lpBuffer
0x18002d7c8  xor     edi, edi
0x18002d7ca  xor     r13d, r13d
0x18002d7cd  call    cs:__imp_GetSystemDirectoryW
0x18002d7d3  dec     eax
0x18002d7d5  cmp     eax, 102h
0x18002d7da  ja      loc_18002D8AB
0x18002d7e0  lea     r8, aSvchostExe; "\\svchost.exe"
0x18002d7e7  mov     edx, 208h; cbDest
0x18002d7ec  lea     rcx, [rbp+3D0h+Buffer]; pszDest
0x18002d7f3  call    StringCbCatW
0x18002d7f8  test    eax, eax
0x18002d7fa  js      loc_18002D8AB
0x18002d800  mov     rax, gs:60h
0x18002d809  lea     rdx, [rbp+3D0h+Buffer]; String2
0x18002d810  mov     rbx, [rax+20h]
0x18002d814  mov     rcx, [rbx+68h]; String1
0x18002d818  call    cs:__imp__wcsicmp
0x18002d81e  test    eax, eax
0x18002d820  jnz     loc_18002D8AB
0x18002d826  mov     rcx, [rbx+78h]; Str
0x18002d82a  lea     rdx, aS_0; " -s "
0x18002d831  call    cs:__imp_wcsstr
0x18002d837  lea     rcx, aUsosvcDll; "usosvc.dll"
0x18002d83e  mov     r14, rax
0x18002d841  call    cs:__imp_GetModuleHandleW
0x18002d847  xor     esi, esi
0x18002d849  lea     rcx, aQmgrDll; "qmgr.dll"
0x18002d850  test    rax, rax
0x18002d853  setnz   sil
0x18002d857  call    cs:__imp_GetModuleHandleW
0x18002d85d  lea     rcx, aDosvcDll; "dosvc.dll"
0x18002d864  mov     rdi, rax
0x18002d867  call    cs:__imp_GetModuleHandleW
0x18002d86d  lea     rcx, aWuauengDll; "wuaueng.dll"
0x18002d874  mov     rbx, rax
0x18002d877  call    cs:__imp_GetModuleHandleW
0x18002d87d  neg     rax
0x18002d880  sbb     r13d, r13d
0x18002d883  and     r13d, 8
0x18002d887  neg     rbx
0x18002d88a  sbb     ecx, ecx
0x18002d88c  and     ecx, 4
0x18002d88f  or      r13d, ecx
0x18002d892  neg     rdi
0x18002d895  lea     rdi, [r14+8]
0x18002d899  sbb     eax, eax
0x18002d89b  and     eax, 2
0x18002d89e  or      r13d, eax
0x18002d8a1  or      r13d, esi
0x18002d8a4  test    r14, r14
0x18002d8a7  cmovz   rdi, r14
0x18002d8ab  test    r15, r15
0x18002d8ae  jz      short loc_18002D8CA
0x18002d8b0  mov     edx, 5Ch ; '\'; Ch
0x18002d8b5  mov     rcx, r15; Str
0x18002d8b8  call    cs:__imp_wcsrchr
0x18002d8be  mov     r15, rax
0x18002d8c1  test    rax, rax
0x18002d8c4  jz      short loc_18002D8CA
0x18002d8c6  add     r15, 2
0x18002d8ca  mov     eax, cs:dword_18009F088
0x18002d8d0  cmp     eax, 5
0x18002d8d3  jbe     loc_18002D9AE
0x18002d8d9  mov     rdx, 400000000000h
0x18002d8e3  lea     rcx, dword_18009F088
0x18002d8ea  call    _tlgKeywordOn
0x18002d8ef  test    al, al
0x18002d8f1  jz      loc_18002D9AE
0x18002d8f7  lea     rax, [rsp+4D0h+var_488]
0x18002d8fc  mov     [rsp+4D0h+var_488], 1000000h
0x18002d905  lea     r9, P
0x18002d90c  mov     [rsp+4D0h+var_460], rax
0x18002d911  test    r15, r15
0x18002d914  mov     [rsp+4D0h+var_458], 8
0x18002d91d  mov     rdx, r9
0x18002d920  lea     rcx, [rbp+3D0h+var_450]
0x18002d924  cmovnz  rdx, r15
0x18002d928  call    _tlgCreate1Sz_wchar_t
0x18002d92d  test    r12, r12
0x18002d930  lea     rcx, [rbp+3D0h+var_440]
0x18002d934  mov     rdx, r9
0x18002d937  cmovnz  rdx, r12
0x18002d93b  call    _tlgCreate1Sz_wchar_t
0x18002d940  lea     rdx, [rbp+3D0h+var_360]
0x18002d944  lea     rcx, [rbp+3D0h+var_430]
0x18002d948  call    _tlgCreate1Sz_wchar_t
0x18002d94d  lea     rdx, [rbp+3D0h+var_3F0]
0x18002d951  lea     rcx, [rbp+3D0h+var_420]
0x18002d955  call    _tlgCreate1Sz_wchar_t
0x18002d95a  test    rdi, rdi
0x18002d95d  lea     rcx, [rbp+3D0h+var_410]
0x18002d961  cmovnz  r9, rdi
0x18002d965  mov     rdx, r9
0x18002d968  call    _tlgCreate1Sz_wchar_t
0x18002d96d  lea     rax, [rsp+4D0h+var_4A0]
0x18002d972  mov     [rsp+4D0h+var_4A0], r13d
0x18002d977  mov     [rbp+3D0h+var_400], rax
0x18002d97b  lea     rdx, byte_18008AE21
0x18002d982  lea     rax, [rsp+4D0h+var_480]
0x18002d987  mov     [rbp+3D0h+var_3F8], 4
0x18002d98f  mov     [rsp+4D0h+var_4A8], rax
0x18002d994  lea     rcx, dword_18009F088
0x18002d99b  xor     r9d, r9d
0x18002d99e  mov     dword ptr [rsp+4D0h+var_4B0], 9
0x18002d9a6  xor     r8d, r8d
0x18002d9a9  call    _tlgWriteTransfer_EventWriteTransfer
0x18002d9ae  mov     rcx, [rbp+3D0h+var_50]
0x18002d9b5  xor     rcx, rsp; StackCookie
0x18002d9b8  call    __security_check_cookie
0x18002d9bd  add     rsp, 498h
0x18002d9c4  pop     r15
0x18002d9c6  pop     r14
0x18002d9c8  pop     r13
0x18002d9ca  pop     r12
0x18002d9cc  pop     rdi
0x18002d9cd  pop     rsi
0x18002d9ce  pop     rbx
0x18002d9cf  pop     rbp
0x18002d9d0  retn
```
