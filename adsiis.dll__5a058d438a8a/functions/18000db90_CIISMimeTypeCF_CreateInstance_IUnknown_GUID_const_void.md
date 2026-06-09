# CIISMimeTypeCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000db90`
- end: `0x18000dbb8`
- name: `?CreateInstance@CIISMimeTypeCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `40`
- prototype: `int(CIISMimeTypeCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000db90`
- `0x18000de1c`

## pseudocode

```c
__int64 __fastcall CIISMimeTypeCF::CreateInstance(
        CIISMimeTypeCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return 2147500037LL;
  else
    return CMimeType::CreateMimeType(a3, a4);
}

```

## disassembly

```asm
0x18000db90  test    r9, r9
0x18000db93  jnz     short loc_18000DB9B
0x18000db95  mov     eax, 80004003h
0x18000db9a  retn
0x18000db9b  mov     qword ptr [r9], 0
0x18000dba2  test    rdx, rdx
0x18000dba5  jz      short loc_18000DBAD
0x18000dba7  mov     eax, 80004005h
0x18000dbac  retn
0x18000dbad  mov     rdx, r9; void **
0x18000dbb0  mov     rcx, r8; struct _GUID *
0x18000dbb3  jmp     ?CreateMimeType@CMimeType@@SAJAEBU_GUID@@PEAPEAX@Z; CMimeType::CreateMimeType(_GUID const &,void * *)
```
