# wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tagPROPVARIANT *)

- ea: `0x180017870`
- end: `0x18001788d`
- name: `?reset@?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtagPROPVARIANT@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013ed8`
- `0x180014078`
- `0x1800186e8`
- `0x180018844`
- `0x18001dba0`
- `0x18001f140`
- `0x180021e5c`
- `0x180021ff4`
- `0x180023ba0`
- `0x180029790`
- `0x1800299d4`
- `0x18002b428`

## callees

- `0x180017870`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017882`

## pseudocode

```c
void __fastcall wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rax

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
    CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x180017870  sub     rsp, 28h
0x180017874  mov     rax, [rcx]
0x180017877  mov     [rcx], rdx
0x18001787a  test    rax, rax
0x18001787d  jz      short loc_180017888
0x18001787f  mov     rcx, rax; pv
0x180017882  call    cs:__imp_CoTaskMemFree
0x180017888  add     rsp, 28h
0x18001788c  retn
```
