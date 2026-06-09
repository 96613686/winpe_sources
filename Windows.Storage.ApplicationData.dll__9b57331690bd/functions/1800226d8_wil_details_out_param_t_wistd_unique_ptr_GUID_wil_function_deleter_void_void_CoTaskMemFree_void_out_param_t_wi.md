# wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)

- ea: `0x1800226d8`
- end: `0x180022702`
- name: `??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(wil::details::out_param_t<wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > *this)`
- caller_count: `14`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022eec`
- `0x18003a114`
- `0x18003a230`
- `0x18003a34c`
- `0x18003a46c`
- `0x18003a58c`
- `0x18003a6ac`
- `0x18003a7cc`
- `0x18003aa00`
- `0x18003ab20`
- `0x18003ac40`
- `0x18003ad5c`
- `0x18003ae7c`
- `0x18003af9c`

## callees

- `0x1800226d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800226f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800226f7`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
        wil::details::out_param_t<wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > *this)
{
  __int64 *value; // r8

  if ( this->replace )
  {
    value = this->wrapper->__ptr_.__value_;
    this->wrapper->__ptr_.__value_ = this->pRaw;
    if ( value )
      CoTaskMemFree(value);
  }
}

```

## disassembly

```asm
0x1800226d8  sub     rsp, 28h
0x1800226dc  cmp     byte ptr [this+10h], 0
0x1800226e0  jz      short loc_1800226FD
0x1800226e2  mov     rdx, [this]
0x1800226e5  mov     rax, [this+8]
0x1800226e9  mov     r8, [rdx]
0x1800226ec  mov     [rdx], rax
0x1800226ef  test    r8, r8
0x1800226f2  jz      short loc_1800226FD
0x1800226f4  mov     this, r8; pv
0x1800226f7  call    cs:__imp_CoTaskMemFree
0x1800226fd  add     rsp, 28h
0x180022701  retn
```
