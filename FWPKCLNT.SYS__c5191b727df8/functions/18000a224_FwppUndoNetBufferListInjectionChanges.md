# FwppUndoNetBufferListInjectionChanges

- ea: `0x18000a224`
- end: `0x18000a2b6`
- name: `FwppUndoNetBufferListInjectionChanges`
- size: `146`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180001f70`
- `0x180003048`
- `0x180003b60`
- `0x18001e740`

## callees

- `0x180004a60`
- `0x18000a224`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000a249`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000a293`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000a249`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000a293`
- `NETIO!NetioUpdateNetBufferListContext` at `0x18000a25d`
- `NETIO!NetioUpdateNetBufferListContext` at `0x18000a25d`

## pseudocode

```c
void __fastcall FwppUndoNetBufferListInjectionChanges(__int64 a1)
{
  __int64 PacketInfo; // rax
  void *v3; // rdx
  __int64 v4; // rbx
  void *v5; // rdx

  PacketInfo = FwppGetPacketInfo(a1);
  v3 = *(void **)(a1 + 88);
  v4 = PacketInfo;
  if ( v3 )
  {
    ExFreeToNPagedLookasideList(&stru_180048240, v3);
    NetioUpdateNetBufferListContext(a1, 0, 0);
    *(_QWORD *)(a1 + 72) = 0;
    *(_DWORD *)(v4 + 176) = 0;
  }
  if ( v4 )
  {
    v5 = *(void **)(v4 + 328);
    if ( v5 )
    {
      ExFreeToNPagedLookasideList(&stru_180048500, v5);
      *(_QWORD *)(v4 + 328) = 0;
    }
  }
}

```

## disassembly

```asm
0x18000a224  mov     [rsp+arg_0], rbx
0x18000a229  push    rdi
0x18000a22a  sub     rsp, 20h
0x18000a22e  mov     rdi, rcx
0x18000a231  call    FwppGetPacketInfo
0x18000a236  mov     rdx, [rdi+58h]; Entry
0x18000a23a  mov     rbx, rax
0x18000a23d  test    rdx, rdx
0x18000a240  jz      short loc_18000A27B
0x18000a242  lea     rcx, stru_180048240; Lookaside
0x18000a249  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000a250  nop     dword ptr [rax+rax+00h]
0x18000a255  xor     r8d, r8d
0x18000a258  xor     edx, edx
0x18000a25a  mov     rcx, rdi
0x18000a25d  call    cs:__imp_NetioUpdateNetBufferListContext
0x18000a264  nop     dword ptr [rax+rax+00h]
0x18000a269  mov     qword ptr [rdi+48h], 0
0x18000a271  mov     dword ptr [rbx+0B0h], 0
0x18000a27b  test    rbx, rbx
0x18000a27e  jz      short loc_18000A2AA
0x18000a280  mov     rdx, [rbx+148h]; Entry
0x18000a287  test    rdx, rdx
0x18000a28a  jz      short loc_18000A2AA
0x18000a28c  lea     rcx, stru_180048500; Lookaside
0x18000a293  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000a29a  nop     dword ptr [rax+rax+00h]
0x18000a29f  mov     qword ptr [rbx+148h], 0
0x18000a2aa  mov     rbx, [rsp+28h+arg_0]
0x18000a2af  add     rsp, 20h
0x18000a2b3  pop     rdi
0x18000a2b4  retn
```
