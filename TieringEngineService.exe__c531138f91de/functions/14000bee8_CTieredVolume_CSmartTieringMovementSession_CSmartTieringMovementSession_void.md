# CTieredVolume::CSmartTieringMovementSession::~CSmartTieringMovementSession(void)

- ea: `0x14000bee8`
- end: `0x14000bf35`
- name: `??1CSmartTieringMovementSession@CTieredVolume@@QEAA@XZ`
- size: `77`
- prototype: `void __fastcall(CTieredVolume::CSmartTieringMovementSession *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14002d3c4`
- `0x140031e04`
- `0x14003ddd4`

## callees

- `0x140004a68`
- `0x14000bee8`

## import_xrefs

- `ESENT!JetResetSessionContext` at `0x14000bef3`
- `ESENT!JetResetSessionContext` at `0x14000bef3`

## pseudocode

```c
void __fastcall CTieredVolume::CSmartTieringMovementSession::~CSmartTieringMovementSession(
        CTieredVolume::CSmartTieringMovementSession *this)
{
  unsigned int v1; // eax

  v1 = JetResetSessionContext(*(_QWORD *)(*(_QWORD *)this + 8LL));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 266, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, v1);
  }
}

```

## disassembly

```asm
0x14000bee8  sub     rsp, 28h
0x14000beec  mov     rcx, [rcx]
0x14000beef  mov     rcx, [rcx+8]; sesid
0x14000bef3  call    cs:__imp_JetResetSessionContext
0x14000bef9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf00  lea     rdx, WPP_GLOBAL_Control
0x14000bf07  cmp     rcx, rdx
0x14000bf0a  jz      short loc_14000BF30
0x14000bf0c  test    byte ptr [rcx+1Ch], 1
0x14000bf10  jz      short loc_14000BF30
0x14000bf12  cmp     byte ptr [rcx+19h], 2
0x14000bf16  jb      short loc_14000BF30
0x14000bf18  mov     rcx, [rcx+10h]
0x14000bf1c  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14000bf23  mov     edx, 10Ah
0x14000bf28  mov     r9d, eax
0x14000bf2b  call    WPP_SF_d
0x14000bf30  add     rsp, 28h
0x14000bf34  retn
```
