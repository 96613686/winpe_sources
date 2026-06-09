# DepFSDecrementActiveMountCount

- ea: `0x18000b964`
- end: `0x18000ba99`
- name: `DepFSDecrementActiveMountCount`
- size: `309`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bb48`
- `0x18000e88c`
- `0x18000fc50`

## callees

- `0x180001430`
- `0x180001a08`
- `0x18000b964`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18000b982`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18000b982`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000ba7c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000ba7c`
- `ntoskrnl!KeSetEvent` at `0x18000b9d8`
- `ntoskrnl!KeSetEvent` at `0x18000ba6b`
- `ntoskrnl!KeSetEvent` at `0x18000b9d8`
- `ntoskrnl!KeSetEvent` at `0x18000ba6b`

## pseudocode

```c
__int64 __fastcall DepFSDecrementActiveMountCount(__int64 a1)
{
  __int64 v1; // rdi
  _WORD v5[2]; // [rsp+40h] [rbp-18h] BYREF
  int v6; // [rsp+44h] [rbp-14h]
  __int64 v7; // [rsp+48h] [rbp-10h]

  v1 = a1 + 184;
  ExAcquirePushLockExclusiveEx(a1 + 184, 0);
  if ( *(int *)(a1 + 192) <= 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_bc64936b77293105c4440102cf4189d6_Traceguids);
    }
    KeSetEvent(&Event, 0, 0);
  }
  v5[0] = *(_WORD *)(a1 + 138);
  v5[1] = v5[0];
  v6 = 0;
  v7 = *(_QWORD *)(a1 + 144);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qddZ(
      WPP_GLOBAL_Control->AttachedDevice,
      38,
      (unsigned int)WPP_bc64936b77293105c4440102cf4189d6_Traceguids,
      a1,
      *(_DWORD *)(a1 + 192),
      *(_DWORD *)(a1 + 192) - 1,
      (__int64)v5);
  }
  if ( (*(_DWORD *)(a1 + 192))-- == 1 )
    KeSetEvent((PRKEVENT)(a1 + 200), 0, 0);
  return ExReleasePushLockExclusiveEx(v1, 0);
}

```

## disassembly

```asm
0x18000b964  mov     [rsp+arg_8], rbx
0x18000b969  mov     [rsp+arg_10], rsi
0x18000b96e  push    rdi
0x18000b96f  sub     rsp, 50h
0x18000b973  lea     rdi, [rcx+0B8h]
0x18000b97a  mov     rbx, rcx
0x18000b97d  mov     rcx, rdi
0x18000b980  xor     edx, edx
0x18000b982  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x18000b989  nop     dword ptr [rax+rax+00h]
0x18000b98e  cmp     dword ptr [rbx+0C0h], 0
0x18000b995  lea     rsi, WPP_GLOBAL_Control
0x18000b99c  jg      short loc_18000B9E4
0x18000b99e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9a5  cmp     rcx, rsi
0x18000b9a8  jz      short loc_18000B9CC
0x18000b9aa  mov     eax, [rcx+2Ch]
0x18000b9ad  test    al, 1
0x18000b9af  jz      short loc_18000B9CC
0x18000b9b1  cmp     byte ptr [rcx+29h], 2
0x18000b9b5  jb      short loc_18000B9CC
0x18000b9b7  mov     rcx, [rcx+18h]
0x18000b9bb  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x18000b9c2  mov     edx, 25h ; '%'
0x18000b9c7  call    WPP_SF_
0x18000b9cc  xor     r8d, r8d; Wait
0x18000b9cf  lea     rcx, Event; Event
0x18000b9d6  xor     edx, edx; Increment
0x18000b9d8  call    cs:__imp_KeSetEvent
0x18000b9df  nop     dword ptr [rax+rax+00h]
0x18000b9e4  movzx   eax, word ptr [rbx+8Ah]
0x18000b9eb  mov     [rsp+58h+var_18], ax
0x18000b9f0  mov     [rsp+58h+var_16], ax
0x18000b9f5  xor     eax, eax
0x18000b9f7  mov     [rsp+58h+var_14], eax
0x18000b9fb  mov     rax, [rbx+90h]
0x18000ba02  mov     [rsp+58h+var_10], rax
0x18000ba07  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba0e  cmp     rcx, rsi
0x18000ba11  jz      short loc_18000BA56
0x18000ba13  mov     eax, [rcx+2Ch]
0x18000ba16  test    al, 10h
0x18000ba18  jz      short loc_18000BA56
0x18000ba1a  cmp     byte ptr [rcx+29h], 4
0x18000ba1e  jb      short loc_18000BA56
0x18000ba20  mov     r9d, [rbx+0C0h]
0x18000ba27  lea     r10, [rsp+58h+var_18]
0x18000ba2c  mov     rcx, [rcx+18h]
0x18000ba30  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x18000ba37  mov     [rsp+58h+var_28], r10
0x18000ba3c  mov     edx, 26h ; '&'
0x18000ba41  lea     eax, [r9-1]
0x18000ba45  mov     [rsp+58h+var_30], eax
0x18000ba49  mov     [rsp+58h+var_38], r9d
0x18000ba4e  mov     r9, rbx
0x18000ba51  call    WPP_SF_qddZ
0x18000ba56  sub     dword ptr [rbx+0C0h], 1
0x18000ba5d  jnz     short loc_18000BA77
0x18000ba5f  lea     rcx, [rbx+0C8h]; Event
0x18000ba66  xor     r8d, r8d; Wait
0x18000ba69  xor     edx, edx; Increment
0x18000ba6b  call    cs:__imp_KeSetEvent
0x18000ba72  nop     dword ptr [rax+rax+00h]
0x18000ba77  xor     edx, edx
0x18000ba79  mov     rcx, rdi
0x18000ba7c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x18000ba83  nop     dword ptr [rax+rax+00h]
0x18000ba88  mov     rbx, [rsp+58h+arg_8]
0x18000ba8d  mov     rsi, [rsp+58h+arg_10]
0x18000ba92  add     rsp, 50h
0x18000ba96  pop     rdi
0x18000ba97  retn
```
