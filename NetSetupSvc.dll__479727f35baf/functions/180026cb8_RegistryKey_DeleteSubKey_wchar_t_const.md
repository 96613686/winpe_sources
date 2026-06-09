# RegistryKey::DeleteSubKey(wchar_t const *)

- ea: `0x180026cb8`
- end: `0x180026d34`
- name: `?DeleteSubKey@RegistryKey@@QEBAXPEB_W@Z`
- size: `124`
- prototype: `void __fastcall(RegistryKey *__hidden this, const wchar_t *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001de84`
- `0x18001e3a8`
- `0x18002fc96`

## callees

- `0x1800027c0`
- `0x180008e3c`
- `0x180026bdc`
- `0x180026cb8`
- `0x180028104`
- `0x1800285cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall RegistryKey::DeleteSubKey(RegistryKey *this, const wchar_t *a2)
{
  HKEY v4; // [rsp+30h] [rbp-18h] BYREF

  RegistryKey::TryOpenSubKey(this, &v4, a2, 9, 0);
  if ( v4 )
  {
    RegDeleteTreeRecurse((RegistryKey *)&v4);
    RegistryKey::DeleteEmptySubKey(this, a2);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v4);
}

```

## disassembly

```asm
0x180026cb8  mov     [rsp+arg_10], rbx
0x180026cbd  push    rdi
0x180026cbe  sub     rsp, 40h
0x180026cc2  mov     rax, cs:__security_cookie
0x180026cc9  xor     rax, rsp
0x180026ccc  mov     [rsp+48h+var_10], rax
0x180026cd1  mov     rdi, rdx
0x180026cd4  mov     rbx, rcx
0x180026cd7  mov     [rsp+48h+var_28], 0
0x180026ce0  mov     r9d, 9
0x180026ce6  mov     r8, rdx
0x180026ce9  lea     rdx, [rsp+48h+var_18]
0x180026cee  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x180026cf3  nop
0x180026cf4  cmp     [rsp+48h+var_18], 0
0x180026cfa  jz      short loc_180026D12
0x180026cfc  lea     rcx, [rsp+48h+var_18]; this
0x180026d01  call    RegDeleteTreeRecurse
0x180026d06  mov     rdx, rdi; wchar_t *
0x180026d09  mov     rcx, rbx; this
0x180026d0c  call    ?DeleteEmptySubKey@RegistryKey@@QEBAXPEB_W@Z; RegistryKey::DeleteEmptySubKey(wchar_t const *)
0x180026d11  nop
0x180026d12  lea     rcx, [rsp+48h+var_18]
0x180026d17  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026d1c  mov     rcx, [rsp+48h+var_10]
0x180026d21  xor     rcx, rsp; StackCookie
0x180026d24  call    __security_check_cookie
0x180026d29  mov     rbx, [rsp+48h+arg_10]
0x180026d2e  add     rsp, 40h
0x180026d32  pop     rdi
0x180026d33  retn
```
