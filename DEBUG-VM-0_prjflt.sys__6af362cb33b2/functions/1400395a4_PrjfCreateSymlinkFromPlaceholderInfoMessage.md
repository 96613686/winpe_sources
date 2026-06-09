# PrjfCreateSymlinkFromPlaceholderInfoMessage

- ea: `0x1400395a4`
- end: `0x14003969b`
- name: `PrjfCreateSymlinkFromPlaceholderInfoMessage`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x1400368c4`

## callees

- `0x14000d128`
- `0x140038f1c`
- `0x1400395a4`

## pseudocode

```c
__int64 __fastcall PrjfCreateSymlinkFromPlaceholderInfoMessage(
        struct _FLT_INSTANCE *a1,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        __int64 a4)
{
  __int16 v4; // ax
  __int16 v6; // ax
  __int64 v7; // rax
  __int64 v8; // r9
  int v9; // edx
  int SymbolicLink; // ebx
  int v11; // r8d
  __int128 v13; // [rsp+60h] [rbp-28h] BYREF
  __int128 v14; // [rsp+70h] [rbp-18h] BYREF

  v4 = *(_WORD *)(a4 + 112);
  v14 = 0;
  WORD1(v14) = v4;
  LOWORD(v14) = v4;
  *((_QWORD *)&v14 + 1) = a4 + *(unsigned int *)(a4 + 104);
  v6 = *(_WORD *)(a4 + 114);
  v13 = 0;
  WORD1(v13) = v6;
  LOWORD(v13) = v6;
  v7 = a4 + *(unsigned int *)(a4 + 108);
  v8 = *(unsigned int *)(a4 + 96);
  *((_QWORD *)&v13 + 1) = v7;
  SymbolicLink = PrjfCreateSymbolicLink(
                   a1,
                   a2,
                   a3,
                   a4 + v8,
                   (const void **)&v14,
                   (const void **)&v13,
                   *(_DWORD *)(a4 + 116));
  if ( SymbolicLink < 0
    && ((xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
  {
    LOBYTE(v9) = xmmword_14001A3D0 & 0x20;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      517,
      v9,
      v11,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      5,
      221,
      (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
      141,
      SymbolicLink);
  }
  return (unsigned int)SymbolicLink;
}

```

## disassembly

```asm
0x1400395a4  mov     r11, rsp
0x1400395a7  push    rbx
0x1400395a8  sub     rsp, 80h
0x1400395af  movzx   eax, word ptr [r9+70h]
0x1400395b4  mov     r10, r9
0x1400395b7  xorps   xmm0, xmm0
0x1400395ba  xorps   xmm1, xmm1
0x1400395bd  movups  [rsp+88h+var_18], xmm0
0x1400395c2  mov     word ptr [rsp+88h+var_18+2], ax
0x1400395c7  mov     word ptr [rsp+88h+var_18], ax
0x1400395cc  mov     eax, [r9+68h]
0x1400395d0  add     rax, r9
0x1400395d3  mov     [r11-10h], rax
0x1400395d7  movzx   eax, word ptr [r9+72h]
0x1400395dc  movups  [rsp+88h+var_28], xmm1
0x1400395e1  mov     word ptr [rsp+88h+var_28+2], ax
0x1400395e6  mov     word ptr [rsp+88h+var_28], ax
0x1400395eb  mov     eax, [r9+6Ch]
0x1400395ef  add     rax, r9
0x1400395f2  mov     r9d, [r9+60h]
0x1400395f6  mov     [r11-20h], rax
0x1400395fa  add     r9, r10
0x1400395fd  mov     eax, [r10+74h]
0x140039601  mov     [rsp+88h+var_58], eax
0x140039605  lea     rax, [r11-28h]
0x140039609  mov     [r11-60h], rax
0x14003960d  lea     rax, [r11-18h]
0x140039611  mov     [r11-68h], rax
0x140039615  call    PrjfCreateSymbolicLink
0x14003961a  mov     ebx, eax
0x14003961c  test    eax, eax
0x14003961e  jns     short loc_14003968F
0x140039620  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140039626  lea     rax, WPP_RECORDER_INITIALIZED
0x14003962d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140039634  setnz   r8b
0x140039638  and     dl, 20h
0x14003963b  jnz     short loc_140039642
0x14003963d  test    r8b, r8b
0x140039640  jz      short loc_14003968F
0x140039642  mov     r9, cs:WPP_GLOBAL_Control
0x140039649  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140039650  mov     [rsp+88h+var_38], ebx
0x140039654  mov     ecx, 205h
0x140039659  mov     [rsp+88h+var_40], 248Dh
0x140039661  mov     [rsp+88h+var_48], rax
0x140039666  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003966d  mov     r9, [r9+40h]
0x140039671  mov     [rsp+88h+var_50], rax
0x140039676  mov     word ptr [rsp+88h+var_58], 0DDh
0x14003967d  mov     [rsp+88h+var_60], 5
0x140039685  mov     [rsp+88h+var_68], 2
0x14003968a  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003968f  mov     eax, ebx
0x140039691  add     rsp, 80h
0x140039698  pop     rbx
0x140039699  retn
```
