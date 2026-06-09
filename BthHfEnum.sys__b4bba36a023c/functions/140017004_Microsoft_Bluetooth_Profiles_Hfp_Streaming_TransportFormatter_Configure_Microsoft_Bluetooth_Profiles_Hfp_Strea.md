# Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportFormatter::Configure(Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportPacketHeaderType,unsigned __int64)

- ea: `0x140017004`
- end: `0x140017106`
- name: `?Configure@TransportFormatter@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEAAJW4TransportPacketHeaderType@23456@_K@Z`
- size: `258`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002e5c0`

## callees

- `0x140016e64`
- `0x140017004`
- `0x140017898`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140017094`
- `ntoskrnl!ExAllocatePool2` at `0x140017094`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400170b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400170b8`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportFormatter::Configure(
        __int64 a1,
        int a2,
        __int64 a3)
{
  __int64 v6; // r15
  unsigned __int64 v7; // rbp
  __int64 Pool2; // rsi
  void *v9; // rcx
  unsigned int v10; // edi

  v6 = 2;
  if ( a2 != 1 )
    v6 = 0;
  v7 = (a2 == 1) + v6 + a3 - ((unsigned __int64)(a2 == 1) + v6 + a3) % ((unsigned __int64)(a2 == 1) + 1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_ddq(WPP_GLOBAL_Control->AttachedDevice, 10, a3, (unsigned int)a3, (_DWORD)v7, a1);
  }
  Pool2 = ExAllocatePool2(64, v7, 1179145282);
  if ( Pool2 )
  {
    v9 = *(void **)(a1 + 32);
    v10 = 0;
    if ( v9 )
      ExFreePoolWithTag(v9, 0x46485442u);
    *(_DWORD *)(a1 + 4) = a2;
    *(_QWORD *)(a1 + 8) = v6;
    *(_QWORD *)(a1 + 16) = a3;
    *(_QWORD *)(a1 + 24) = v7;
    *(_QWORD *)(a1 + 32) = Pool2;
    *(_DWORD *)(a1 + 96) = 0;
    Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::SetBuffer(
      (Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *)(a1 + 40),
      (char *)(v6 + Pool2),
      a3);
    *(_DWORD *)a1 = 0;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v10;
}

```

## disassembly

```asm
0x140017004  push    rbx
0x140017006  push    rbp
0x140017007  push    rsi
0x140017008  push    rdi
0x140017009  push    r12
0x14001700b  push    r14
0x14001700d  push    r15
0x14001700f  sub     rsp, 30h
0x140017013  xor     eax, eax
0x140017015  lea     rbp, [r8-1]
0x140017019  cmp     edx, 1
0x14001701c  mov     r12d, edx
0x14001701f  mov     r14, r8
0x140017022  mov     rbx, rcx
0x140017025  lea     r15d, [rax+2]
0x140017029  cmovnz  r15d, eax
0x14001702d  xor     r9d, r9d
0x140017030  cmp     edx, 1
0x140017033  setz    r9b
0x140017037  xor     edx, edx
0x140017039  inc     r9
0x14001703c  lea     rax, [r9+r15]
0x140017040  add     rbp, rax
0x140017043  mov     rax, rbp
0x140017046  div     r9
0x140017049  sub     rbp, rdx
0x14001704c  mov     rcx, cs:WPP_GLOBAL_Control
0x140017053  lea     rax, WPP_GLOBAL_Control
0x14001705a  cmp     rcx, rax
0x14001705d  jz      short loc_140017086
0x14001705f  mov     eax, [rcx+2Ch]
0x140017062  test    al, 40h
0x140017064  jz      short loc_140017086
0x140017066  cmp     byte ptr [rcx+29h], 4
0x14001706a  jb      short loc_140017086
0x14001706c  mov     rcx, [rcx+18h]
0x140017070  mov     r9d, r14d
0x140017073  mov     edx, 0Ah
0x140017078  mov     [rsp+68h+var_40], rbx
0x14001707d  mov     [rsp+68h+var_48], ebp
0x140017081  call    WPP_SF_ddq
0x140017086  mov     r8d, 46485442h
0x14001708c  mov     rdx, rbp
0x14001708f  mov     ecx, 40h ; '@'
0x140017094  call    cs:__imp_ExAllocatePool2
0x14001709b  nop     dword ptr [rax+rax+00h]
0x1400170a0  mov     rsi, rax
0x1400170a3  test    rax, rax
0x1400170a6  jz      short loc_1400170EF
0x1400170a8  mov     rcx, [rbx+20h]; P
0x1400170ac  xor     edi, edi
0x1400170ae  test    rcx, rcx
0x1400170b1  jz      short loc_1400170C4
0x1400170b3  mov     edx, 46485442h; Tag
0x1400170b8  call    cs:__imp_ExFreePoolWithTag
0x1400170bf  nop     dword ptr [rax+rax+00h]
0x1400170c4  lea     rdx, [r15+rsi]; char *
0x1400170c8  mov     [rbx+4], r12d
0x1400170cc  lea     rcx, [rbx+28h]; this
0x1400170d0  mov     [rbx+8], r15
0x1400170d4  mov     r8, r14; unsigned __int64
0x1400170d7  mov     [rbx+10h], r14
0x1400170db  mov     [rbx+18h], rbp
0x1400170df  mov     [rbx+20h], rsi
0x1400170e3  mov     [rbx+60h], edi
0x1400170e6  call    ?SetBuffer@ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEAAXPEAD_K_N@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::SetBuffer(char *,unsigned __int64,bool)
0x1400170eb  mov     [rbx], edi
0x1400170ed  jmp     short loc_1400170F4
0x1400170ef  mov     edi, 0C000009Ah
0x1400170f4  mov     eax, edi
0x1400170f6  add     rsp, 30h
0x1400170fa  pop     r15
0x1400170fc  pop     r14
0x1400170fe  pop     r12
0x140017100  pop     rdi
0x140017101  pop     rsi
0x140017102  pop     rbp
0x140017103  pop     rbx
0x140017104  retn
```
