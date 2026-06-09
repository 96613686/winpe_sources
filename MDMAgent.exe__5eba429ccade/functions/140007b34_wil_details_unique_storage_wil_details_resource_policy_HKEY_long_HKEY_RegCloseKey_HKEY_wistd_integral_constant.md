# wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)

- ea: `0x140007b34`
- end: `0x140007b81`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z`
- size: `77`
- prototype: `void __fastcall(HKEY *, HKEY)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140005ec0`
- `0x140006ec0`
- `0x140007130`
- `0x14000b5a0`
- `0x1400104c0`
- `0x140010a68`
- `0x140018060`

## callees

- `0x1400047f8`
- `0x140004c60`
- `0x140007b34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007b5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007b5e`

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
0x140007b34  mov     [rsp+arg_8], rbx
0x140007b39  mov     [rsp+arg_10], rsi
0x140007b3e  push    rdi
0x140007b3f  sub     rsp, 20h
0x140007b43  mov     rdi, [rcx]
0x140007b46  mov     rsi, rdx
0x140007b49  mov     rbx, rcx
0x140007b4c  test    rdi, rdi
0x140007b4f  jz      short loc_140007B6E
0x140007b51  lea     rcx, [rsp+28h+arg_0]; this
0x140007b56  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140007b5b  mov     rcx, rdi; hKey
0x140007b5e  call    cs:__imp_RegCloseKey
0x140007b64  lea     rcx, [rsp+28h+arg_0]; this
0x140007b69  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140007b6e  mov     [rbx], rsi
0x140007b71  mov     rbx, [rsp+28h+arg_8]
0x140007b76  mov     rsi, [rsp+28h+arg_10]
0x140007b7b  add     rsp, 20h
0x140007b7f  pop     rdi
0x140007b80  retn
```
