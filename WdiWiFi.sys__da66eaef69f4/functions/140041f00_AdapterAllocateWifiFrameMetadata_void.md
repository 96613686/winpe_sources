# AdapterAllocateWifiFrameMetadata(void *)

- ea: `0x140041f00`
- end: `0x140041f91`
- name: `?AdapterAllocateWifiFrameMetadata@@YAPEAU_WDI_FRAME_METADATA@@PEAX@Z`
- size: `145`
- prototype: `struct _WDI_FRAME_METADATA *__fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140034e04`
- `0x140041f00`
- `0x1400da740`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140041f14`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140041f14`

## pseudocode

```c
struct _WDI_FRAME_METADATA *__fastcall AdapterAllocateWifiFrameMetadata(char *a1)
{
  _DWORD *v2; // rax
  int v3; // edx
  _DWORD *v4; // rbx

  v2 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 5440));
  v4 = v2;
  if ( v2 )
  {
    memset(v2, 0, *((unsigned __int16 *)a1 + 2785));
    *v4 = *((unsigned __int16 *)a1 + 2785);
    return (struct _WDI_FRAME_METADATA *)(v4 + 16);
  }
  else
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v3,
        1,
        235,
        (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x140041f00  mov     [rsp+arg_0], rbx
0x140041f05  push    rdi
0x140041f06  sub     rsp, 30h
0x140041f0a  mov     rdi, rcx
0x140041f0d  add     rcx, 1540h; Lookaside
0x140041f14  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140041f1b  nop     dword ptr [rax+rax+00h]
0x140041f20  mov     rbx, rax
0x140041f23  test    rax, rax
0x140041f26  jz      short loc_140041F53
0x140041f28  movzx   r8d, word ptr [rdi+15C2h]; Size
0x140041f30  xor     edx, edx; Val
0x140041f32  mov     rcx, rax; void *
0x140041f35  call    memset
0x140041f3a  movzx   eax, word ptr [rdi+15C2h]
0x140041f41  mov     [rbx], eax
0x140041f43  lea     rax, [rbx+40h]
0x140041f47  mov     rbx, [rsp+38h+arg_0]
0x140041f4c  add     rsp, 30h
0x140041f50  pop     rdi
0x140041f51  retn
0x140041f53  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140041f5a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140041f61  jz      short loc_140041F8D
0x140041f63  lea     rcx, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x140041f6a  mov     r9d, 0EBh
0x140041f70  mov     [rsp+38h+var_18], rcx
0x140041f75  mov     r8d, 1
0x140041f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140041f82  mov     dl, 2
0x140041f84  mov     rcx, [rcx+40h]
0x140041f88  call    WPP_RECORDER_SF_
0x140041f8d  xor     eax, eax
0x140041f8f  jmp     short loc_140041F47
```
