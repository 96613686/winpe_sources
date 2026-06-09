# PinPropertySimple(void *,ulong,_GUID const &,ulong,void *,ulong)

- ea: `0x1800275a0`
- end: `0x180027647`
- name: `?PinPropertySimple@@YAJPEAXKAEBU_GUID@@K0K@Z`
- size: `167`
- prototype: `__int64 __fastcall(void *, unsigned int, const struct _GUID *, unsigned int, void *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018af8`
- `0x18001b7a0`

## callees

- `0x18000a814`
- `0x1800275a0`
- `0x180027650`

## string_xrefs

- `0x180027627`: `avcore\midi2\libs\midikscommon\midikscommon.cpp`

## pseudocode

```c
__int64 __fastcall PinPropertySimple(void *a1, int a2, const struct _GUID *a3, int a4, void *a5, DWORD a6)
{
  __int128 v6; // xmm0
  int v7; // ebx
  __int64 result; // rax
  int v9; // [rsp+20h] [rbp-58h]
  unsigned int v10; // [rsp+38h] [rbp-40h]
  __int128 InBuffer; // [rsp+50h] [rbp-28h] BYREF
  int v12; // [rsp+60h] [rbp-18h]
  int v13; // [rsp+64h] [rbp-14h]
  int v14; // [rsp+68h] [rbp-10h]
  int v15; // [rsp+6Ch] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v6 = (__int128)*a3;
  v12 = a4;
  v14 = a2;
  InBuffer = v6;
  v13 = 1;
  v15 = 0;
  v7 = SyncIoctl(a1, 0x2F0003u, &InBuffer, 0x20u, a5, a6, 0, v10, 0);
  if ( v7 >= 0 )
    return 0;
  result = 2147943570LL;
  if ( v7 != -2147023726 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"avcore\\midi2\\libs\\midikscommon\\midikscommon.cpp",
      (const char *)(unsigned int)v7,
      v9);
    return (unsigned int)v7;
  }
  return result;
}

```

## disassembly

```asm
0x1800275a0  mov     rax, rsp
0x1800275a3  push    rbx
0x1800275a4  sub     rsp, 70h
0x1800275a8  movups  xmm0, xmmword ptr [r8]
0x1800275ac  mov     qword ptr [rax-38h], 0
0x1800275b4  lea     r8, [rsp+78h+InBuffer]; lpInBuffer
0x1800275b9  mov     qword ptr [rax-48h], 0
0x1800275c1  mov     qword ptr [rax-28h], 0
0x1800275c9  mov     qword ptr [rax-20h], 0
0x1800275d1  mov     [rax-18h], r9d
0x1800275d5  mov     r9d, 20h ; ' '; nInBufferSize
0x1800275db  mov     [rax-10h], edx
0x1800275de  mov     edx, 2F0003h; dwIoControlCode
0x1800275e3  movdqu  xmmword ptr [rax-28h], xmm0
0x1800275e8  mov     dword ptr [rax-14h], 1
0x1800275ef  mov     dword ptr [rax-0Ch], 0
0x1800275f6  mov     eax, [rsp+78h+arg_28]
0x1800275fd  mov     [rsp+78h+var_50], eax; DWORD
0x180027601  mov     rax, [rsp+78h+arg_20]
0x180027609  mov     [rsp+78h+var_58], rax; int
0x18002760e  call    ?SyncIoctl@@YAJPEAXK0K0KPEAKK0@Z; SyncIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *,ulong,void *)
0x180027613  mov     ebx, eax
0x180027615  test    eax, eax
0x180027617  jns     short loc_18002763F
0x180027619  mov     eax, 80070492h
0x18002761e  cmp     ebx, eax
0x180027620  jz      short loc_180027641
0x180027622  mov     rcx, [rsp+78h]; this
0x180027627  lea     r8, aAvcoreMidi2Lib_1; "avcore\\midi2\\libs\\midikscommon\\midi"...
0x18002762e  mov     r9d, ebx; char *
0x180027631  mov     edx, 8Bh; void *
0x180027636  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002763b  mov     eax, ebx
0x18002763d  jmp     short loc_180027641
0x18002763f  xor     eax, eax
0x180027641  add     rsp, 70h
0x180027645  pop     rbx
0x180027646  retn
```
