# CAdapter::FreeWfcFrame(_WFC_FRAME *)

- ea: `0x14003ed50`
- end: `0x14003ee13`
- name: `?FreeWfcFrame@CAdapter@@QEAAXPEAU_WFC_FRAME@@@Z`
- size: `195`
- prototype: `void(CAdapter *__hidden this, struct _WFC_FRAME *)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140033730`
- `0x14003e538`
- `0x14003ea84`
- `0x140046674`
- `0x1400498ac`

## callees

- `0x140034e04`
- `0x140034ec4`
- `0x14003ed50`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ed99`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ed99`

## pseudocode

```c
void __fastcall CAdapter::FreeWfcFrame(CAdapter *this, struct _WFC_FRAME *a2)
{
  struct _WFC_FRAME *v2; // rbx
  int v4; // [rsp+28h] [rbp-30h]

  v2 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      236,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
  }
  if ( v2 )
    ExFreeToNPagedLookasideList(&this->m_WfcFrameLookaside, v2);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    v4 = 0;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      237,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
      v4);
  }
}

```

## disassembly

```asm
0x14003ed50  push    rbx
0x14003ed52  push    rbp
0x14003ed53  push    rsi
0x14003ed54  push    rdi
0x14003ed55  sub     rsp, 38h
0x14003ed59  mov     rbx, rdx
0x14003ed5c  mov     rdi, rcx
0x14003ed5f  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ed66  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14003ed6d  lea     rbp, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x14003ed74  jz      short loc_14003ED8A
0x14003ed76  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ed7d  cmp     byte ptr [rcx+29h], 5
0x14003ed81  jnb     short loc_14003EDF2
0x14003ed83  cmp     word ptr [rcx+48h], 0
0x14003ed88  jnz     short loc_14003EDF2
0x14003ed8a  test    rbx, rbx
0x14003ed8d  jz      short loc_14003EDA5
0x14003ed8f  lea     rcx, [rdi+1540h]; Lookaside
0x14003ed96  mov     rdx, rbx; Entry
0x14003ed99  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003eda0  nop     dword ptr [rax+rax+00h]
0x14003eda5  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14003edac  jz      short loc_14003EDC2
0x14003edae  mov     rcx, cs:WPP_GLOBAL_Control
0x14003edb5  cmp     byte ptr [rcx+29h], 5
0x14003edb9  jnb     short loc_14003EDCC
0x14003edbb  cmp     word ptr [rcx+48h], 0
0x14003edc0  jnz     short loc_14003EDCC
0x14003edc2  add     rsp, 38h
0x14003edc6  pop     rdi
0x14003edc7  pop     rsi
0x14003edc8  pop     rbp
0x14003edc9  pop     rbx
0x14003edca  retn
0x14003edcc  mov     rcx, [rcx+40h]
0x14003edd0  mov     r9d, 0EDh
0x14003edd6  mov     [rsp+58h+var_30], 0
0x14003edde  mov     r8d, 1
0x14003ede4  mov     dl, 5
0x14003ede6  mov     [rsp+58h+var_38], rbp
0x14003edeb  call    WPP_RECORDER_SF_D
0x14003edf0  jmp     short loc_14003EDC2
0x14003edf2  mov     rcx, [rcx+40h]
0x14003edf6  mov     r9d, 0ECh
0x14003edfc  mov     r8d, 1
0x14003ee02  mov     [rsp+58h+var_38], rbp
0x14003ee07  mov     dl, 5
0x14003ee09  call    WPP_RECORDER_SF_
0x14003ee0e  jmp     loc_14003ED8A
```
