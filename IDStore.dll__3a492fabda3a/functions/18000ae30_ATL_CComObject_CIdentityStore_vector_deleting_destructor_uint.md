# ATL::CComObject<CIdentityStore>::`vector deleting destructor'(uint)

- ea: `0x18000ae30`
- end: `0x18000ae61`
- name: `??_E?$CComObject@VCIdentityStore@@@ATL@@UEAAPEAXI@Z`
- size: `49`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000ae30`
- `0x18000ae70`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ae4d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ae4d`

## pseudocode

```c
void *__fastcall ATL::CComObject<CIdentityStore>::`vector deleting destructor'(void *a1, char a2)
{
  ATL::CComObject<CIdentityStore>::~CComObject<CIdentityStore>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000ae30  mov     [rsp+arg_0], rbx
0x18000ae35  push    rdi
0x18000ae36  sub     rsp, 20h
0x18000ae3a  mov     edi, edx
0x18000ae3c  mov     rbx, rcx
0x18000ae3f  call    ??1?$CComObject@VCIdentityStore@@@ATL@@UEAA@XZ; ATL::CComObject<CIdentityStore>::~CComObject<CIdentityStore>(void)
0x18000ae44  test    dil, 1
0x18000ae48  jz      short loc_18000AE53
0x18000ae4a  mov     rcx, rbx
0x18000ae4d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ae53  mov     rax, rbx
0x18000ae56  mov     rbx, [rsp+28h+arg_0]
0x18000ae5b  add     rsp, 20h
0x18000ae5f  pop     rdi
0x18000ae60  retn
```
