# ATL::CComAggObject<CConnectedUserStore>::`scalar deleting destructor'(uint)

- ea: `0x1800109d0`
- end: `0x180010a00`
- name: `??_G?$CComAggObject@VCConnectedUserStore@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800108b0`
- `0x1800109d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800109ec`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800109ec`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CConnectedUserStore>::`scalar deleting destructor'(void *a1, char a2)
{
  ATL::CComAggObject<CConnectedUserStore>::~CComAggObject<CConnectedUserStore>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800109d0  mov     [rsp+arg_0], rbx
0x1800109d5  push    rdi
0x1800109d6  sub     rsp, 20h
0x1800109da  mov     ebx, edx
0x1800109dc  mov     rdi, rcx
0x1800109df  call    ??1?$CComAggObject@VCConnectedUserStore@@@ATL@@UEAA@XZ; ATL::CComAggObject<CConnectedUserStore>::~CComAggObject<CConnectedUserStore>(void)
0x1800109e4  test    bl, 1
0x1800109e7  jz      short loc_1800109F2
0x1800109e9  mov     rcx, rdi
0x1800109ec  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800109f2  mov     rbx, [rsp+28h+arg_0]
0x1800109f7  mov     rax, rdi
0x1800109fa  add     rsp, 20h
0x1800109fe  pop     rdi
0x1800109ff  retn
```
