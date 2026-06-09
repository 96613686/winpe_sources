# ATL::CComAggObject<CIdentityProfileHandler>::`scalar deleting destructor'(uint)

- ea: `0x180010a10`
- end: `0x180010a40`
- name: `??_G?$CComAggObject@VCIdentityProfileHandler@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800108fc`
- `0x180010a10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180010a2c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010a2c`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CIdentityProfileHandler>::`scalar deleting destructor'(void *a1, char a2)
{
  ATL::CComAggObject<CIdentityProfileHandler>::~CComAggObject<CIdentityProfileHandler>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180010a10  mov     [rsp+arg_0], rbx
0x180010a15  push    rdi
0x180010a16  sub     rsp, 20h
0x180010a1a  mov     ebx, edx
0x180010a1c  mov     rdi, rcx
0x180010a1f  call    ??1?$CComAggObject@VCIdentityProfileHandler@@@ATL@@UEAA@XZ; ATL::CComAggObject<CIdentityProfileHandler>::~CComAggObject<CIdentityProfileHandler>(void)
0x180010a24  test    bl, 1
0x180010a27  jz      short loc_180010A32
0x180010a29  mov     rcx, rdi
0x180010a2c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010a32  mov     rbx, [rsp+28h+arg_0]
0x180010a37  mov     rax, rdi
0x180010a3a  add     rsp, 20h
0x180010a3e  pop     rdi
0x180010a3f  retn
```
