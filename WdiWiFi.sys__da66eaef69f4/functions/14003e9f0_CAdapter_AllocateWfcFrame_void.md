# CAdapter::AllocateWfcFrame(void)

- ea: `0x14003e9f0`
- end: `0x14003ea7e`
- name: `?AllocateWfcFrame@CAdapter@@QEAAPEAU_WFC_FRAME@@XZ`
- size: `142`
- prototype: `struct _WFC_FRAME *__fastcall(CAdapter *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14003e538`
- `0x14006048c`

## callees

- `0x140034e04`
- `0x14003e9f0`
- `0x1400da740`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003ea04`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003ea04`

## pseudocode

```c
struct _WFC_FRAME *__fastcall CAdapter::AllocateWfcFrame(CAdapter *this)
{
  _DWORD *v2; // rax
  int v3; // edx
  _DWORD *v4; // rbx

  v2 = ExAllocateFromNPagedLookasideList(&this->m_WfcFrameLookaside);
  v4 = v2;
  if ( v2 )
  {
    memset(v2, 0, this->m_WfcFrameSize);
    *v4 = this->m_WfcFrameSize;
  }
  else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v3) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v3,
      1,
      235,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
  }
  return (struct _WFC_FRAME *)v4;
}

```

## disassembly

```asm
0x14003e9f0  mov     [rsp+arg_0], rbx
0x14003e9f5  push    rdi
0x14003e9f6  sub     rsp, 30h
0x14003e9fa  mov     rdi, rcx
0x14003e9fd  add     rcx, 1540h; Lookaside
0x14003ea04  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003ea0b  nop     dword ptr [rax+rax+00h]
0x14003ea10  mov     rbx, rax
0x14003ea13  test    rax, rax
0x14003ea16  jz      short loc_14003EA42
0x14003ea18  movzx   r8d, word ptr [rdi+15C2h]; Size
0x14003ea20  xor     edx, edx; Val
0x14003ea22  mov     rcx, rax; void *
0x14003ea25  call    memset
0x14003ea2a  movzx   eax, word ptr [rdi+15C2h]
0x14003ea31  mov     [rbx], eax
0x14003ea33  mov     rax, rbx
0x14003ea36  mov     rbx, [rsp+38h+arg_0]
0x14003ea3b  add     rsp, 30h
0x14003ea3f  pop     rdi
0x14003ea40  retn
0x14003ea42  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ea49  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003ea50  jz      short loc_14003EA33
0x14003ea52  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ea59  lea     rax, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x14003ea60  mov     r9d, 0EBh
0x14003ea66  mov     [rsp+38h+var_18], rax
0x14003ea6b  mov     r8d, 1
0x14003ea71  mov     dl, 2
0x14003ea73  mov     rcx, [rcx+40h]
0x14003ea77  call    WPP_RECORDER_SF_
0x14003ea7c  jmp     short loc_14003EA33
```
