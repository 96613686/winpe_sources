# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)

- ea: `0x180015064`
- end: `0x1800150b8`
- name: `??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `84`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014f0c`
- `0x1800153c0`
- `0x180015580`
- `0x1800156e0`
- `0x180015910`
- `0x18002ea78`

## callees

- `0x180015064`
- `0x180025db0`
- `0x1800272f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800150a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800150a6`

## pseudocode

```c
void **__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        void **a1,
        void **a2)
{
  void *v4; // rsi
  void *v5; // rbp
  char v7; // [rsp+50h] [rbp+8h] BYREF

  if ( a1 != a2 )
  {
    v4 = *a1;
    v5 = *a2;
    if ( *a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v7);
      CoTaskMemFree(v4);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v7);
    }
    *a1 = v5;
    *a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180015064  push    rbx
0x180015066  push    rbp
0x180015067  push    rsi
0x180015068  push    rdi
0x180015069  sub     rsp, 28h
0x18001506d  mov     rdi, rdx
0x180015070  mov     rbx, rcx
0x180015073  cmp     rcx, rdx
0x180015076  jz      short loc_18001508D
0x180015078  mov     rsi, [rcx]
0x18001507b  mov     rbp, [rdx]
0x18001507e  test    rsi, rsi
0x180015081  jnz     short loc_180015099
0x180015083  mov     [rbx], rbp
0x180015086  mov     qword ptr [rdi], 0
0x18001508d  mov     rax, rbx
0x180015090  add     rsp, 28h
0x180015094  pop     rdi
0x180015095  pop     rsi
0x180015096  pop     rbp
0x180015097  pop     rbx
0x180015098  retn
0x180015099  lea     rcx, [rsp+48h+arg_0]; this
0x18001509e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800150a3  mov     rcx, rsi; pv
0x1800150a6  call    cs:__imp_CoTaskMemFree
0x1800150ac  lea     rcx, [rsp+48h+arg_0]; this
0x1800150b1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800150b6  jmp     short loc_180015083
```
