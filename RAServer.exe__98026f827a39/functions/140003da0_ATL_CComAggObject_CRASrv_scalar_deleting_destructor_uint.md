# ATL::CComAggObject<CRASrv>::`scalar deleting destructor'(uint)

- ea: `0x140003da0`
- end: `0x140003dd0`
- name: `??_G?$CComAggObject@VCRASrv@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140003398`
- `0x140003da0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140003dbc`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003dbc`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CRASrv>::`scalar deleting destructor'(void *a1, char a2)
{
  ATL::CComAggObject<CRASrv>::~CComAggObject<CRASrv>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x140003da0  mov     [rsp+arg_0], rbx
0x140003da5  push    rdi
0x140003da6  sub     rsp, 20h
0x140003daa  mov     ebx, edx
0x140003dac  mov     rdi, rcx
0x140003daf  call    ??1?$CComAggObject@VCRASrv@@@ATL@@UEAA@XZ; ATL::CComAggObject<CRASrv>::~CComAggObject<CRASrv>(void)
0x140003db4  test    bl, 1
0x140003db7  jz      short loc_140003DC2
0x140003db9  mov     rcx, rdi
0x140003dbc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003dc2  mov     rbx, [rsp+28h+arg_0]
0x140003dc7  mov     rax, rdi
0x140003dca  add     rsp, 20h
0x140003dce  pop     rdi
0x140003dcf  retn
```
