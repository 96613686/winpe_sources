# Microsoft::Bluetooth::Foundation::GuidFactory::GetNextId(void)

- ea: `0x180010b78`
- end: `0x180010bb4`
- name: `?GetNextId@GuidFactory@Foundation@Bluetooth@Microsoft@@YA?AU_GUID@@XZ`
- size: `60`
- prototype: `struct _GUID *(Microsoft::Bluetooth::Foundation::GuidFactory *__hidden this, struct _GUID *__return_ptr __struct_ptr retstr)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010370`
- `0x180010770`
- `0x180018200`
- `0x1800472d0`
- `0x180049770`
- `0x180053c20`

## callees

- `0x18000e0c0`
- `0x180010b78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180010b87`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180010b87`

## pseudocode

```c
struct _GUID *__fastcall Microsoft::Bluetooth::Foundation::GuidFactory::GetNextId(
        GUID *this,
        struct _GUID *__return_ptr retstr)
{
  HRESULT Guid; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *this = 0;
  Guid = CoCreateGuid(this);
  if ( Guid < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\IdFactory.h",
      (const char *)(unsigned int)Guid,
      v5);
  return this;
}

```

## disassembly

```asm
0x180010b78  push    rbx; int
0x180010b7a  sub     rsp, 20h
0x180010b7e  xorps   xmm0, xmm0
0x180010b81  mov     rbx, rcx
0x180010b84  movups  xmmword ptr [rcx], xmm0
0x180010b87  call    cs:__imp_CoCreateGuid
0x180010b8d  test    eax, eax
0x180010b8f  jns     short loc_180010BAB
0x180010b91  mov     rcx, [rsp+28h]; this
0x180010b96  lea     r8, aOnecoreDrivers_43; "onecore\\drivers\\bluetooth\\foundation"...
0x180010b9d  mov     r9d, eax; char *
0x180010ba0  mov     edx, 15h; void *
0x180010ba5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010bab  mov     rax, rbx
0x180010bae  add     rsp, 20h
0x180010bb2  pop     rbx
0x180010bb3  retn
```
