# wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)

- ea: `0x140007e3c`
- end: `0x140007e90`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z`
- size: `84`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400060c8`
- `0x140007160`
- `0x1400073e0`
- `0x14000bac4`
- `0x140010cf0`
- `0x1400112b0`
- `0x140018d74`

## callees

- `0x1400048c8`
- `0x140004d00`
- `0x140007e3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007e66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007e66`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        HKEY *a1,
        HKEY a2)
{
  HKEY v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    RegCloseKey(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x140007e3c  mov     [rsp+arg_8], rbx
0x140007e41  mov     [rsp+arg_10], rsi
0x140007e46  push    rdi
0x140007e47  sub     rsp, 20h
0x140007e4b  mov     rdi, [rcx]
0x140007e4e  mov     rsi, rdx
0x140007e51  mov     rbx, rcx
0x140007e54  test    rdi, rdi
0x140007e57  jz      short loc_140007E7C
0x140007e59  lea     rcx, [rsp+28h+arg_0]; this
0x140007e5e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140007e63  mov     rcx, rdi; hKey
0x140007e66  call    cs:__imp_RegCloseKey
0x140007e6d  nop     dword ptr [rax+rax+00h]
0x140007e72  lea     rcx, [rsp+28h+arg_0]; this
0x140007e77  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140007e7c  mov     [rbx], rsi
0x140007e7f  mov     rbx, [rsp+28h+arg_8]
0x140007e84  mov     rsi, [rsp+28h+arg_10]
0x140007e89  add     rsp, 20h
0x140007e8d  pop     rdi
0x140007e8e  retn
```
