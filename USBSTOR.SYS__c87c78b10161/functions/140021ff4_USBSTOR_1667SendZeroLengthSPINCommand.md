# USBSTOR_1667SendZeroLengthSPINCommand

- ea: `0x140021ff4`
- end: `0x140022092`
- name: `USBSTOR_1667SendZeroLengthSPINCommand`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140021d00`

## callees

- `0x140010664`
- `0x140021ff4`
- `0x1400266ac`

## pseudocode

```c
char __fastcall USBSTOR_1667SendZeroLengthSPINCommand(struct _DEVICE_OBJECT *a1, __int64 a2, char a3)
{
  __int128 Src; // [rsp+40h] [rbp-10h] BYREF
  __int64 v5; // [rsp+70h] [rbp+20h] BYREF

  LODWORD(v5) = 0;
  Src = 0;
  BYTE4(Src) = a3 != 0 ? 0x80 : 0;
  LODWORD(Src) = 162;
  *(_DWORD *)((char *)&Src + 6) = 0;
  if ( (int)USBSTOR_IssueInternalCdbToLun(a1, (__int64)&v5, &Src, 12, 10) >= 0 )
    return 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140021ff4  push    rbp
0x140021ff6  mov     rbp, rsp
0x140021ff9  sub     rsp, 50h
0x140021ffd  mov     [rsp+50h+var_18], 0Ah; int
0x140022005  neg     r8b
0x140022008  xorps   xmm0, xmm0
0x14002200b  mov     [rsp+50h+var_20], 0Ch; char
0x140022010  sbb     al, al
0x140022012  mov     dword ptr [rbp+arg_10], 0
0x140022019  and     al, 80h
0x14002201b  xor     r9d, r9d
0x14002201e  movups  [rbp+var_10], xmm0
0x140022022  mov     byte ptr [rbp+var_10+4], al
0x140022025  lea     rax, [rbp+var_10]
0x140022029  mov     [rsp+50h+Src], rax; Src
0x14002202e  lea     rax, [rbp+arg_10]
0x140022032  mov     [rsp+50h+var_30], rax; __int64
0x140022037  mov     dword ptr [rbp+var_10], 0A2h
0x14002203e  mov     dword ptr [rbp+var_10+6], 0
0x140022045  call    USBSTOR_IssueInternalCdbToLun
0x14002204a  test    eax, eax
0x14002204c  js      short loc_140022052
0x14002204e  mov     al, 1
0x140022050  jmp     short loc_14002208B
0x140022052  mov     rcx, cs:WPP_GLOBAL_Control
0x140022059  lea     rax, WPP_GLOBAL_Control
0x140022060  cmp     rcx, rax
0x140022063  jz      short loc_140022089
0x140022065  test    dword ptr [rcx+2Ch], 100h
0x14002206c  jz      short loc_140022089
0x14002206e  cmp     byte ptr [rcx+29h], 3
0x140022072  jb      short loc_140022089
0x140022074  mov     rcx, [rcx+18h]
0x140022078  lea     r8, WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids
0x14002207f  mov     edx, 19h
0x140022084  call    WPP_SF_
0x140022089  xor     al, al
0x14002208b  add     rsp, 50h
0x14002208f  pop     rbp
0x140022090  retn
```
