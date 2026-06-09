# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18001662c`
- end: `0x180016739`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `269`
- prototype: `int(ATL::CRegKey *__hidden this, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180001110`
- `0x180011264`
- `0x180019210`
- `0x18001a850`
- `0x1800323b4`
- `0x180037f90`
- `0x18003b478`
- `0x18003da40`
- `0x1800420ec`

## callees

- `0x18001662c`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001666f`
- `KERNEL32!GetModuleHandleW` at `0x18001666f`
- `KERNEL32!GetProcAddress` at `0x180016684`
- `KERNEL32!GetProcAddress` at `0x180016684`
- `ADVAPI32!RegCloseKey` at `0x180016703`
- `ADVAPI32!RegCloseKey` at `0x180016703`
- `ADVAPI32!RegOpenKeyExW` at `0x1800166ef`
- `ADVAPI32!RegOpenKeyExW` at `0x1800166ef`

## string_xrefs

- `0x180016668`: `Advapi32.dll`
- `0x18001667a`: `RegOpenKeyTransactedW`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY a2, const unsigned __int16 *a3)
{
  __int64 v5; // rdi
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  unsigned int v8; // eax
  __int64 v9; // rcx
  HKEY phkResult; // [rsp+40h] [rbp-18h] BYREF

  phkResult = 0;
  v5 = *((_QWORD *)this + 2);
  if ( !v5 )
    goto LABEL_8;
  if ( !*(_QWORD *)v5 )
  {
    if ( !*(_DWORD *)(v5 + 8) )
    {
LABEL_7:
      v9 = 1;
      goto LABEL_10;
    }
LABEL_8:
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20219u, &phkResult);
    goto LABEL_9;
  }
  ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
  if ( !ModuleHandleW )
    goto LABEL_7;
  ProcAddress = GetProcAddress(ModuleHandleW, "RegOpenKeyTransactedW");
  if ( !ProcAddress )
    goto LABEL_7;
  v8 = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, _QWORD, __int64, HKEY *, _QWORD, _QWORD))ProcAddress)(
         -2147483646,
         a3,
         0,
         131609,
         &phkResult,
         *(_QWORD *)v5,
         0);
LABEL_9:
  v9 = v8;
LABEL_10:
  if ( !(_DWORD)v9 )
  {
    if ( *(_QWORD *)this != v9 )
      LODWORD(v9) = RegCloseKey(*(HKEY *)this);
    *(_QWORD *)this = phkResult;
    *((_DWORD *)this + 2) = 512;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001662c  mov     [rsp+arg_8], rbx
0x180016631  mov     [rsp+arg_18], rsi
0x180016636  push    rdi
0x180016637  sub     rsp, 50h
0x18001663b  mov     rax, cs:__security_cookie
0x180016642  xor     rax, rsp
0x180016645  mov     [rsp+58h+var_10], rax
0x18001664a  mov     rsi, r8
0x18001664d  mov     rbx, rcx
0x180016650  mov     [rsp+58h+var_18], 0
0x180016659  mov     rdi, [rcx+10h]
0x18001665d  test    rdi, rdi
0x180016660  jz      short loc_1800166D2
0x180016662  cmp     qword ptr [rdi], 0
0x180016666  jz      short loc_1800166C5
0x180016668  lea     rcx, ModuleName; "Advapi32.dll"
0x18001666f  call    cs:__imp_GetModuleHandleW
0x180016675  test    rax, rax
0x180016678  jz      short loc_1800166CB
0x18001667a  lea     rdx, aRegopenkeytran; "RegOpenKeyTransactedW"
0x180016681  mov     rcx, rax; hModule
0x180016684  call    cs:__imp_GetProcAddress
0x18001668a  test    rax, rax
0x18001668d  jz      short loc_1800166CB
0x18001668f  mov     [rsp+58h+var_28], 0
0x180016698  mov     rcx, [rdi]
0x18001669b  mov     [rsp+58h+var_30], rcx
0x1800166a0  lea     rcx, [rsp+58h+var_18]
0x1800166a5  mov     [rsp+58h+phkResult], rcx
0x1800166aa  mov     r9d, 20219h
0x1800166b0  xor     r8d, r8d
0x1800166b3  mov     rdx, rsi
0x1800166b6  mov     rcx, 0FFFFFFFF80000002h
0x1800166bd  call    cs:__guard_dispatch_icall_fptr
0x1800166c3  jmp     short loc_1800166F5
0x1800166c5  cmp     dword ptr [rdi+8], 0
0x1800166c9  jnz     short loc_1800166D2
0x1800166cb  mov     ecx, 1
0x1800166d0  jmp     short loc_1800166F7
0x1800166d2  lea     rax, [rsp+58h+var_18]
0x1800166d7  mov     [rsp+58h+phkResult], rax; phkResult
0x1800166dc  mov     r9d, 20219h; samDesired
0x1800166e2  xor     r8d, r8d; ulOptions
0x1800166e5  mov     rdx, rsi; lpSubKey
0x1800166e8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800166ef  call    cs:__imp_RegOpenKeyExW
0x1800166f5  mov     ecx, eax
0x1800166f7  test    ecx, ecx
0x1800166f9  jnz     short loc_18001671A
0x1800166fb  cmp     [rbx], rcx
0x1800166fe  jz      short loc_18001670B
0x180016700  mov     rcx, [rbx]; hKey
0x180016703  call    cs:__imp_RegCloseKey
0x180016709  mov     ecx, eax
0x18001670b  mov     rax, [rsp+58h+var_18]
0x180016710  mov     [rbx], rax
0x180016713  mov     dword ptr [rbx+8], 200h
0x18001671a  mov     eax, ecx
0x18001671c  mov     rcx, [rsp+58h+var_10]
0x180016721  xor     rcx, rsp; StackCookie
0x180016724  call    __security_check_cookie
0x180016729  mov     rbx, [rsp+58h+arg_8]
0x18001672e  mov     rsi, [rsp+58h+arg_18]
0x180016733  add     rsp, 50h
0x180016737  pop     rdi
0x180016738  retn
```
