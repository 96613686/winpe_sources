# std::unique_ptr<CTieredVolume::CSmartTieringMovementSession,std::default_delete<CTieredVolume::CSmartTieringMovementSession>>::~unique_ptr<CTieredVolume::CSmartTieringMovementSession,std::default_delete<CTieredVolume::CSmartTieringMovementSession>>(void)

- ea: `0x14002d3c4`
- end: `0x14002d3e8`
- name: `??1?$unique_ptr@VCSmartTieringMovementSession@CTieredVolume@@U?$default_delete@VCSmartTieringMovementSession@CTieredVolume@@@std@@@std@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(CTieredVolume::CSmartTieringMovementSession **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14004060d`
- `0x1400406c1`

## callees

- `0x140001a00`
- `0x14000bee8`
- `0x14002d3c4`

## pseudocode

```c
void __fastcall std::unique_ptr<CTieredVolume::CSmartTieringMovementSession>::~unique_ptr<CTieredVolume::CSmartTieringMovementSession>(
        CTieredVolume::CSmartTieringMovementSession **a1)
{
  CTieredVolume::CSmartTieringMovementSession *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    CTieredVolume::CSmartTieringMovementSession::~CSmartTieringMovementSession(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x14002d3c4  push    rbx
0x14002d3c6  sub     rsp, 20h
0x14002d3ca  mov     rbx, [rcx]
0x14002d3cd  test    rbx, rbx
0x14002d3d0  jz      short loc_14002D3E2
0x14002d3d2  mov     rcx, rbx; this
0x14002d3d5  call    ??1CSmartTieringMovementSession@CTieredVolume@@QEAA@XZ; CTieredVolume::CSmartTieringMovementSession::~CSmartTieringMovementSession(void)
0x14002d3da  mov     rcx, rbx; Block
0x14002d3dd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002d3e2  add     rsp, 20h
0x14002d3e6  pop     rbx
0x14002d3e7  retn
```
