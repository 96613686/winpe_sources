# Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser::Configure(Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportPacketHeaderType,unsigned __int64)

- ea: `0x14001710c`
- end: `0x140017202`
- name: `?Configure@TransportParser@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEAAJW4TransportPacketHeaderType@23456@_K@Z`
- size: `246`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser *, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002e440`

## callees

- `0x14001710c`
- `0x140017344`
- `0x140017898`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001719e`
- `ntoskrnl!ExAllocatePool2` at `0x14001719e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400171c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400171c2`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser::Configure(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser *a1,
        int a2,
        __int64 a3)
{
  __int64 v6; // r15
  unsigned __int64 v7; // r14
  __int64 Pool2; // rbp
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
    WPP_SF_ddq(WPP_GLOBAL_Control->AttachedDevice, 13, a3, (unsigned int)a3, (_DWORD)v7, a1);
  }
  Pool2 = ExAllocatePool2(64, v6 + 2 * a3, 1179145282);
  if ( Pool2 )
  {
    v9 = (void *)*((_QWORD *)a1 + 4);
    v10 = 0;
    if ( v9 )
      ExFreePoolWithTag(v9, 0x46485442u);
    *(_DWORD *)a1 = a2;
    *((_QWORD *)a1 + 1) = v6;
    *((_QWORD *)a1 + 2) = a3;
    *((_QWORD *)a1 + 3) = v7;
    *((_QWORD *)a1 + 4) = Pool2;
    Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser::ResetParserState(a1);
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
0x14001710c  push    rbx
0x14001710e  push    rbp
0x14001710f  push    rsi
0x140017110  push    rdi
0x140017111  push    r12
0x140017113  push    r14
0x140017115  push    r15
0x140017117  sub     rsp, 30h
0x14001711b  xor     eax, eax
0x14001711d  lea     r14, [r8-1]
0x140017121  cmp     edx, 1
0x140017124  mov     r12d, edx
0x140017127  mov     rsi, r8
0x14001712a  mov     rbx, rcx
0x14001712d  lea     r15d, [rax+2]
0x140017131  cmovnz  r15d, eax
0x140017135  xor     r9d, r9d
0x140017138  cmp     edx, 1
0x14001713b  setz    r9b
0x14001713f  xor     edx, edx
0x140017141  inc     r9
0x140017144  lea     rax, [r9+r15]
0x140017148  add     r14, rax
0x14001714b  mov     rax, r14
0x14001714e  div     r9
0x140017151  sub     r14, rdx
0x140017154  mov     rcx, cs:WPP_GLOBAL_Control
0x14001715b  lea     rax, WPP_GLOBAL_Control
0x140017162  cmp     rcx, rax
0x140017165  jz      short loc_14001718F
0x140017167  mov     eax, [rcx+2Ch]
0x14001716a  test    al, 40h
0x14001716c  jz      short loc_14001718F
0x14001716e  cmp     byte ptr [rcx+29h], 4
0x140017172  jb      short loc_14001718F
0x140017174  mov     rcx, [rcx+18h]
0x140017178  mov     r9d, esi
0x14001717b  mov     edx, 0Dh
0x140017180  mov     [rsp+68h+var_40], rbx
0x140017185  mov     [rsp+68h+var_48], r14d
0x14001718a  call    WPP_SF_ddq
0x14001718f  lea     rdx, [r15+rsi*2]
0x140017193  mov     ecx, 40h ; '@'
0x140017198  mov     r8d, 46485442h
0x14001719e  call    cs:__imp_ExAllocatePool2
0x1400171a5  nop     dword ptr [rax+rax+00h]
0x1400171aa  mov     rbp, rax
0x1400171ad  test    rax, rax
0x1400171b0  jz      short loc_1400171EB
0x1400171b2  mov     rcx, [rbx+20h]; P
0x1400171b6  xor     edi, edi
0x1400171b8  test    rcx, rcx
0x1400171bb  jz      short loc_1400171CE
0x1400171bd  mov     edx, 46485442h; Tag
0x1400171c2  call    cs:__imp_ExFreePoolWithTag
0x1400171c9  nop     dword ptr [rax+rax+00h]
0x1400171ce  mov     rcx, rbx; this
0x1400171d1  mov     [rbx], r12d
0x1400171d4  mov     [rbx+8], r15
0x1400171d8  mov     [rbx+10h], rsi
0x1400171dc  mov     [rbx+18h], r14
0x1400171e0  mov     [rbx+20h], rbp
0x1400171e4  call    ?ResetParserState@TransportParser@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser::ResetParserState(void)
0x1400171e9  jmp     short loc_1400171F0
0x1400171eb  mov     edi, 0C000009Ah
0x1400171f0  mov     eax, edi
0x1400171f2  add     rsp, 30h
0x1400171f6  pop     r15
0x1400171f8  pop     r14
0x1400171fa  pop     r12
0x1400171fc  pop     rdi
0x1400171fd  pop     rsi
0x1400171fe  pop     rbp
0x1400171ff  pop     rbx
0x140017200  retn
```
