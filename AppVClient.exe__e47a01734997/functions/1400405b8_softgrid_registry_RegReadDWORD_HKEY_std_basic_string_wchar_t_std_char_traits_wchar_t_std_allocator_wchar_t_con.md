# softgrid::registry::RegReadDWORD(HKEY__ *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong &,ulong)

- ea: `0x1400405b8`
- end: `0x14004068f`
- name: `?RegReadDWORD@registry@softgrid@@YAJPEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEAKK@Z`
- size: `215`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140027de0`
- `0x140027fa4`
- `0x140028168`

## callees

- `0x1400042a4`
- `0x1400094bc`
- `0x1400405b8`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x14004066d`
- `ADVAPI32!RegQueryValueExW` at `0x14004066d`
- `ADVAPI32!RegOpenKeyExW` at `0x140040604`
- `ADVAPI32!RegOpenKeyExW` at `0x140040604`
- `ADVAPI32!RegCloseKey` at `0x14004060e`

## pseudocode

```c
LSTATUS __fastcall softgrid::registry::RegReadDWORD(HKEY a1, const WCHAR *a2, const WCHAR *a3, BYTE *a4, DWORD cbData)
{
  bool v6; // cc
  LSTATUS result; // eax
  HKEY v9; // rdi
  _QWORD *v10; // rax
  LSTATUS v11; // ebx
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF
  _QWORD *v13; // [rsp+58h] [rbp+10h] BYREF
  _QWORD *v14; // [rsp+68h] [rbp+20h]

  hKey = a1;
  *(_DWORD *)a4 = 0;
  v6 = *((_QWORD *)a2 + 3) <= 7u;
  hKey = 0;
  if ( !v6 )
    a2 = *(const WCHAR **)a2;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey);
  if ( !result )
  {
    v9 = hKey;
    v10 = operator new(0x18u);
    v14 = v10;
    *v10 = &appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,long (*)(HKEY__ *),HKEY__ * &>>::`vftable';
    v10[1] = RegCloseKey;
    v10[2] = v9;
    v6 = *((_QWORD *)a3 + 3) <= 7u;
    v13 = v10;
    cbData = 4;
    if ( !v6 )
      a3 = *(const WCHAR **)a3;
    v11 = RegQueryValueExW(hKey, a3, 0, 0, a4, &cbData);
    appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)&v13);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x1400405b8  mov     [rsp+arg_10], rbx
0x1400405bd  mov     [rsp+hKey], rcx
0x1400405c2  push    rsi
0x1400405c3  push    rdi
0x1400405c4  push    r14
0x1400405c6  sub     rsp, 30h
0x1400405ca  mov     dword ptr [r9], 0
0x1400405d1  mov     r14, r9
0x1400405d4  cmp     qword ptr [rdx+18h], 7
0x1400405d9  mov     rsi, r8
0x1400405dc  mov     [rsp+48h+hKey], 0
0x1400405e5  jbe     short loc_1400405EA
0x1400405e7  mov     rdx, [rdx]; lpSubKey
0x1400405ea  lea     rax, [rsp+48h+hKey]
0x1400405ef  mov     r9d, 20019h; samDesired
0x1400405f5  xor     r8d, r8d; ulOptions
0x1400405f8  mov     [rsp+48h+phkResult], rax; phkResult
0x1400405fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140040604  call    cs:__imp_RegOpenKeyExW
0x14004060a  test    eax, eax
0x14004060c  jnz     short loc_140040681
0x14004060e  mov     rbx, cs:__imp_RegCloseKey
0x140040615  lea     ecx, [rax+18h]; Size
0x140040618  mov     rdi, [rsp+48h+hKey]
0x14004061d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140040622  lea     rcx, ??_7?$scope_guard_func_impl@V?$_Binder@U_Unforced@std@@P6AJPEAUHKEY__@@@ZAEAPEAU3@@std@@@utility@appv@@6B@; const appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,long (*)(HKEY__ *),HKEY__ * &>>::`vftable'
0x140040629  mov     [rsp+48h+arg_18], rax
0x14004062e  mov     [rax], rcx
0x140040631  mov     [rax+8], rbx
0x140040635  mov     [rax+10h], rdi
0x140040639  cmp     qword ptr [rsi+18h], 7
0x14004063e  mov     [rsp+48h+arg_8], rax
0x140040643  mov     [rsp+48h+cbData], 4
0x14004064b  jbe     short loc_140040650
0x14004064d  mov     rsi, [rsi]
0x140040650  mov     rcx, [rsp+48h+hKey]; hKey
0x140040655  lea     rax, [rsp+48h+cbData]
0x14004065a  mov     [rsp+48h+lpcbData], rax; lpcbData
0x14004065f  xor     r9d, r9d; lpType
0x140040662  xor     r8d, r8d; lpReserved
0x140040665  mov     [rsp+48h+phkResult], r14; lpData
0x14004066a  mov     rdx, rsi; lpValueName
0x14004066d  call    cs:__imp_RegQueryValueExW
0x140040673  lea     rcx, [rsp+48h+arg_8]; this
0x140040678  mov     ebx, eax
0x14004067a  call    ??1scope_guard@utility@appv@@QEAA@XZ; appv::utility::scope_guard::~scope_guard(void)
0x14004067f  mov     eax, ebx
0x140040681  mov     rbx, [rsp+48h+arg_10]
0x140040686  add     rsp, 30h
0x14004068a  pop     r14
0x14004068c  pop     rdi
0x14004068d  pop     rsi
0x14004068e  retn
```
