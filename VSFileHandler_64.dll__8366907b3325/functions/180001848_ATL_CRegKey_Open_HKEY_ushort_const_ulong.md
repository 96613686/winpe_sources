# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180001848`
- end: `0x180001939`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `241`
- prototype: `int(ATL::CRegKey *__hidden this, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180001a38`
- `0x1800048ec`
- `0x180004bb4`

## callees

- `0x180001848`
- `0x180007700`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180001906`
- `ADVAPI32!RegCloseKey` at `0x180001906`
- `ADVAPI32!RegOpenKeyExW` at `0x1800018f2`
- `ADVAPI32!RegOpenKeyExW` at `0x1800018f2`
- `KERNEL32!GetModuleHandleW` at `0x18000188a`
- `KERNEL32!GetModuleHandleW` at `0x18000188a`
- `KERNEL32!GetProcAddress` at `0x18000189f`
- `KERNEL32!GetProcAddress` at `0x18000189f`

## string_xrefs

- `0x180001895`: `RegOpenKeyTransactedW`
- `0x180001883`: `Advapi32.dll`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY a2, const unsigned __int16 *a3, REGSAM a4)
{
  __int64 v5; // rsi
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  unsigned int v11; // eax
  __int64 v12; // rcx
  HKEY phkResult; // [rsp+40h] [rbp-38h] BYREF

  phkResult = 0;
  v5 = *((_QWORD *)this + 2);
  if ( !v5 )
    goto LABEL_8;
  if ( !*(_QWORD *)v5 )
  {
    if ( !*(_DWORD *)(v5 + 8) )
    {
LABEL_7:
      v12 = 1;
      goto LABEL_10;
    }
LABEL_8:
    v11 = RegOpenKeyExW(a2, a3, 0, a4, &phkResult);
    goto LABEL_9;
  }
  ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
  if ( !ModuleHandleW )
    goto LABEL_7;
  ProcAddress = GetProcAddress(ModuleHandleW, "RegOpenKeyTransactedW");
  if ( !ProcAddress )
    goto LABEL_7;
  v11 = ((__int64 (__fastcall *)(HKEY, const unsigned __int16 *, _QWORD, _QWORD, HKEY *, _QWORD, _QWORD))ProcAddress)(
          a2,
          a3,
          0,
          a4,
          &phkResult,
          *(_QWORD *)v5,
          0);
LABEL_9:
  v12 = v11;
LABEL_10:
  if ( !(_DWORD)v12 )
  {
    if ( *(_QWORD *)this != v12 )
      LODWORD(v12) = RegCloseKey(*(HKEY *)this);
    *(_QWORD *)this = phkResult;
    *((_DWORD *)this + 2) = a4 & 0x300;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180001848  push    rbx
0x18000184a  push    rbp
0x18000184b  push    rsi
0x18000184c  push    rdi
0x18000184d  push    r14
0x18000184f  sub     rsp, 50h
0x180001853  mov     rax, cs:__security_cookie
0x18000185a  xor     rax, rsp
0x18000185d  mov     [rsp+78h+var_30], rax
0x180001862  and     [rsp+78h+var_38], 0
0x180001868  mov     ebx, r9d
0x18000186b  mov     rsi, [rcx+10h]
0x18000186f  mov     r14, r8
0x180001872  mov     rbp, rdx
0x180001875  mov     rdi, rcx
0x180001878  test    rsi, rsi
0x18000187b  jz      short loc_1800018DF
0x18000187d  cmp     qword ptr [rsi], 0
0x180001881  jz      short loc_1800018D2
0x180001883  lea     rcx, aAdvapi32Dll_0; "Advapi32.dll"
0x18000188a  call    cs:__imp_GetModuleHandleW
0x180001890  test    rax, rax
0x180001893  jz      short loc_1800018D8
0x180001895  lea     rdx, aRegopenkeytran; "RegOpenKeyTransactedW"
0x18000189c  mov     rcx, rax; hModule
0x18000189f  call    cs:__imp_GetProcAddress
0x1800018a5  test    rax, rax
0x1800018a8  jz      short loc_1800018D8
0x1800018aa  mov     r8, [rsi]
0x1800018ad  lea     rcx, [rsp+78h+var_38]
0x1800018b2  and     [rsp+78h+var_48], 0
0x1800018b8  mov     r9d, ebx
0x1800018bb  mov     [rsp+78h+var_50], r8
0x1800018c0  mov     rdx, r14
0x1800018c3  mov     [rsp+78h+phkResult], rcx
0x1800018c8  xor     r8d, r8d
0x1800018cb  mov     rcx, rbp
0x1800018ce  call    rax
0x1800018d0  jmp     short loc_1800018F8
0x1800018d2  cmp     dword ptr [rsi+8], 0
0x1800018d6  jnz     short loc_1800018DF
0x1800018d8  mov     ecx, 1
0x1800018dd  jmp     short loc_1800018FA
0x1800018df  lea     rax, [rsp+78h+var_38]
0x1800018e4  xor     r8d, r8d; ulOptions
0x1800018e7  mov     rdx, r14; lpSubKey
0x1800018ea  mov     [rsp+78h+phkResult], rax; phkResult
0x1800018ef  mov     rcx, rbp; hKey
0x1800018f2  call    cs:__imp_RegOpenKeyExW
0x1800018f8  mov     ecx, eax
0x1800018fa  test    ecx, ecx
0x1800018fc  jnz     short loc_18000191F
0x1800018fe  cmp     [rdi], rcx
0x180001901  jz      short loc_18000190E
0x180001903  mov     rcx, [rdi]; hKey
0x180001906  call    cs:__imp_RegCloseKey
0x18000190c  mov     ecx, eax
0x18000190e  mov     rax, [rsp+78h+var_38]
0x180001913  and     ebx, 300h
0x180001919  mov     [rdi], rax
0x18000191c  mov     [rdi+8], ebx
0x18000191f  mov     eax, ecx
0x180001921  mov     rcx, [rsp+78h+var_30]
0x180001926  xor     rcx, rsp; StackCookie
0x180001929  call    __security_check_cookie
0x18000192e  add     rsp, 50h
0x180001932  pop     r14
0x180001934  pop     rdi
0x180001935  pop     rsi
0x180001936  pop     rbp
0x180001937  pop     rbx
0x180001938  retn
```
