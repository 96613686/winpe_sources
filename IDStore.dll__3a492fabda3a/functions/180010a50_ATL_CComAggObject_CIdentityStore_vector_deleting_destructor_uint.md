# ATL::CComAggObject<CIdentityStore>::`vector deleting destructor'(uint)

- ea: `0x180010a50`
- end: `0x180010a80`
- name: `??_E?$CComAggObject@VCIdentityStore@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180010940`
- `0x180010a50`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180010a6c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010a6c`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CIdentityStore>::`vector deleting destructor'(void *a1, char a2)
{
  ATL::CComAggObject<CIdentityStore>::~CComAggObject<CIdentityStore>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180010a50  mov     [rsp+arg_0], rbx
0x180010a55  push    rdi
0x180010a56  sub     rsp, 20h
0x180010a5a  mov     ebx, edx
0x180010a5c  mov     rdi, rcx
0x180010a5f  call    ??1?$CComAggObject@VCIdentityStore@@@ATL@@UEAA@XZ; ATL::CComAggObject<CIdentityStore>::~CComAggObject<CIdentityStore>(void)
0x180010a64  test    bl, 1
0x180010a67  jz      short loc_180010A72
0x180010a69  mov     rcx, rdi
0x180010a6c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010a72  mov     rbx, [rsp+28h+arg_0]
0x180010a77  mov     rax, rdi
0x180010a7a  add     rsp, 20h
0x180010a7e  pop     rdi
0x180010a7f  retn
```
