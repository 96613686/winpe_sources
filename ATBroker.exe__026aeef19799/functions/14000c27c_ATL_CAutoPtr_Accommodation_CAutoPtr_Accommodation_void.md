# ATL::CAutoPtr<Accommodation>::~CAutoPtr<Accommodation>(void)

- ea: `0x14000c27c`
- end: `0x14000c2b3`
- name: `??1?$CAutoPtr@VAccommodation@@@ATL@@QEAA@XZ`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140015ce2`
- `0x140016008`

## callees

- `0x140001e44`
- `0x14000c27c`
- `0x1400113b0`

## pseudocode

```c
void __fastcall ATL::CAutoPtr<Accommodation>::~CAutoPtr<Accommodation>(Accommodation **a1)
{
  Accommodation *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    Accommodation::~Accommodation(*a1);
    operator delete(v1);
  }
  *a1 = 0;
}

```

## disassembly

```asm
0x14000c27c  mov     [rsp+arg_0], rbx
0x14000c281  push    rdi
0x14000c282  sub     rsp, 20h
0x14000c286  mov     rbx, [rcx]
0x14000c289  mov     rdi, rcx
0x14000c28c  test    rbx, rbx
0x14000c28f  jz      short loc_14000C2A1
0x14000c291  mov     rcx, rbx; this
0x14000c294  call    ??1Accommodation@@QEAA@XZ; Accommodation::~Accommodation(void)
0x14000c299  mov     rcx, rbx; Block
0x14000c29c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c2a1  mov     rbx, [rsp+28h+arg_0]
0x14000c2a6  mov     qword ptr [rdi], 0
0x14000c2ad  add     rsp, 20h
0x14000c2b1  pop     rdi
0x14000c2b2  retn
```
