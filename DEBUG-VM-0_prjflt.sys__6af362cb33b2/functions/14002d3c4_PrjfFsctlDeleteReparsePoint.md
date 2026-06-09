# PrjfFsctlDeleteReparsePoint

- ea: `0x14002d3c4`
- end: `0x14002d660`
- name: `PrjfFsctlDeleteReparsePoint`
- size: `668`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x14002ec30`

## callees

- `0x1400035d4`
- `0x140003e6c`
- `0x14000d008`
- `0x14002d3c4`

## pseudocode

```c
__int64 __fastcall PrjfFsctlDeleteReparsePoint(struct _FLT_CALLBACK_DATA *a1, __int64 a2)
{
  unsigned int v3; // esi
  int v4; // edx
  char *UnionContextByFileName; // rbp
  int v6; // r8d
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  _WORD *Parameters; // rcx
  int v9; // ebx

  v3 = 1;
  UnionContextByFileName = (char *)PrjfGetUnionContextByFileName(a1, *(PFLT_INSTANCE *)(a2 + 24), 0);
  if ( !UnionContextByFileName )
  {
    if ( (xmmword_14001A3E0 & 0x80u) != 0LL || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = xmmword_14001A3E0 & 0x80;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        1031,
        v4,
        v6,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        4,
        7,
        22,
        (__int64)WPP_52333d08ad443511f3c222844b8995a6_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fsctrl.c",
        255);
    }
    return v3;
  }
  Iopb = a1->Iopb;
  Parameters = Iopb->Parameters.CreatePipe.Parameters;
  if ( Parameters )
  {
    if ( ((Iopb->Parameters.Create.Options - 8) & 0xFFFFFFEF) != 0 )
    {
      if ( (xmmword_14001A3D0 & 0x80u) != 0LL || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v4) = xmmword_14001A3D0 & 0x80;
        LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(
          519,
          v4,
          v6,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          7,
          24,
          (__int64)WPP_52333d08ad443511f3c222844b8995a6_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fsctrl.c",
          20);
      }
    }
    else
    {
      if ( !Parameters[2] )
      {
        if ( *(_DWORD *)Parameters == -1879048164 || (v9 = 0, *(_DWORD *)Parameters == -1610612702) )
        {
          if ( SBYTE8(xmmword_14001A3D0) < 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v4) = BYTE8(xmmword_14001A3D0) & 0x80;
            LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sD(
              775,
              v4,
              v6,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              3,
              7,
              26,
              (__int64)WPP_52333d08ad443511f3c222844b8995a6_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fsctrl.c",
              39);
          }
          v9 = -1073741790;
        }
        goto LABEL_25;
      }
      if ( (xmmword_14001A3D0 & 0x80u) != 0LL || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v4) = xmmword_14001A3D0 & 0x80;
        LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(
          519,
          v4,
          v6,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          7,
          25,
          (__int64)WPP_52333d08ad443511f3c222844b8995a6_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fsctrl.c",
          27);
      }
    }
    v9 = -1073741192;
  }
  else
  {
    if ( (xmmword_14001A3D0 & 0x80u) != 0LL || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = xmmword_14001A3D0 & 0x80;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        519,
        v4,
        v6,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        7,
        23,
        (__int64)WPP_52333d08ad443511f3c222844b8995a6_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fsctrl.c",
        12);
    }
    v9 = -1073741306;
  }
LABEL_25:
  PrjfReleaseUnionContext(UnionContextByFileName);
  if ( v9 < 0 )
  {
    v3 = 4;
    a1->IoStatus.Status = v9;
  }
  return v3;
}

```

## disassembly

```asm
0x14002d3c4  push    rbx
0x14002d3c6  push    rbp
0x14002d3c7  push    rsi
0x14002d3c8  push    rdi
0x14002d3c9  push    r14
0x14002d3cb  sub     rsp, 50h
0x14002d3cf  mov     rdx, [rdx+18h]; Instance
0x14002d3d3  xor     r9d, r9d
0x14002d3d6  xor     r8d, r8d; String2
0x14002d3d9  mov     rdi, rcx
0x14002d3dc  mov     esi, 1
0x14002d3e1  call    PrjfGetUnionContextByFileName
0x14002d3e6  xor     r14d, r14d
0x14002d3e9  mov     rbp, rax
0x14002d3ec  test    rax, rax
0x14002d3ef  jnz     short loc_14002D465
0x14002d3f1  mov     dl, byte ptr cs:xmmword_14001A3E0
0x14002d3f7  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d3fe  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d405  setnz   r8b
0x14002d409  and     dl, 80h
0x14002d40c  jnz     short loc_14002D417
0x14002d40e  test    r8b, r8b
0x14002d411  jz      loc_14002D652
0x14002d417  mov     r9, cs:WPP_GLOBAL_Control
0x14002d41e  lea     rax, aOnecoreBaseFsG_8; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002d425  mov     [rsp+78h+var_30], 1FFh
0x14002d42d  mov     ecx, 407h
0x14002d432  mov     [rsp+78h+var_38], rax
0x14002d437  lea     rax, WPP_52333d08ad443511f3c222844b8995a6_Traceguids
0x14002d43e  mov     [rsp+78h+var_40], rax
0x14002d443  mov     r9, [r9+40h]
0x14002d447  mov     [rsp+78h+var_48], 16h
0x14002d44e  mov     [rsp+78h+var_50], 7
0x14002d456  mov     [rsp+78h+var_58], 4
0x14002d45b  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14002d460  jmp     loc_14002D652
0x14002d465  mov     rax, [rdi+10h]
0x14002d469  mov     rcx, [rax+30h]
0x14002d46d  test    rcx, rcx
0x14002d470  jnz     short loc_14002D4E7
0x14002d472  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14002d478  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d47f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d486  setnz   r8b
0x14002d48a  and     dl, 80h
0x14002d48d  jnz     short loc_14002D494
0x14002d48f  test    r8b, r8b
0x14002d492  jz      short loc_14002D4DD
0x14002d494  mov     r9, cs:WPP_GLOBAL_Control
0x14002d49b  lea     rax, aOnecoreBaseFsG_8; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002d4a2  mov     [rsp+78h+var_30], 20Ch
0x14002d4aa  mov     ecx, 207h
0x14002d4af  mov     [rsp+78h+var_38], rax
0x14002d4b4  lea     rax, WPP_52333d08ad443511f3c222844b8995a6_Traceguids
0x14002d4bb  mov     [rsp+78h+var_40], rax
0x14002d4c0  mov     r9, [r9+40h]
0x14002d4c4  mov     [rsp+78h+var_48], 17h
0x14002d4cb  mov     [rsp+78h+var_50], 7
0x14002d4d3  mov     [rsp+78h+var_58], 2
0x14002d4d8  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14002d4dd  mov     ebx, 0C0000206h
0x14002d4e2  jmp     loc_14002D63E
0x14002d4e7  mov     eax, [rax+20h]
0x14002d4ea  sub     eax, 8
0x14002d4ed  test    eax, 0FFFFFFEFh
0x14002d4f2  jz      short loc_14002D569
0x14002d4f4  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14002d4fa  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d501  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d508  setnz   r8b
0x14002d50c  and     dl, 80h
0x14002d50f  jnz     short loc_14002D516
0x14002d511  test    r8b, r8b
0x14002d514  jz      short loc_14002D55F
0x14002d516  mov     [rsp+78h+var_30], 214h
0x14002d51e  lea     rax, aOnecoreBaseFsG_8; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002d525  mov     [rsp+78h+var_38], rax
0x14002d52a  lea     rax, WPP_52333d08ad443511f3c222844b8995a6_Traceguids
0x14002d531  mov     [rsp+78h+var_40], rax
0x14002d536  mov     [rsp+78h+var_48], 18h
0x14002d53d  mov     r9, cs:WPP_GLOBAL_Control
0x14002d544  mov     ecx, 207h
0x14002d549  mov     [rsp+78h+var_50], 7
0x14002d551  mov     [rsp+78h+var_58], 2
0x14002d556  mov     r9, [r9+40h]
0x14002d55a  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14002d55f  mov     ebx, 0C0000278h
0x14002d564  jmp     loc_14002D63E
0x14002d569  cmp     [rcx+4], r14w
0x14002d56e  jz      short loc_14002D5BB
0x14002d570  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14002d576  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d57d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d584  setnz   r8b
0x14002d588  and     dl, 80h
0x14002d58b  jnz     short loc_14002D592
0x14002d58d  test    r8b, r8b
0x14002d590  jz      short loc_14002D55F
0x14002d592  mov     [rsp+78h+var_30], 21Bh
0x14002d59a  lea     rax, aOnecoreBaseFsG_8; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002d5a1  mov     [rsp+78h+var_38], rax
0x14002d5a6  lea     rax, WPP_52333d08ad443511f3c222844b8995a6_Traceguids
0x14002d5ad  mov     [rsp+78h+var_40], rax
0x14002d5b2  mov     [rsp+78h+var_48], 19h
0x14002d5b9  jmp     short loc_14002D53D
0x14002d5bb  mov     eax, [rcx]
0x14002d5bd  cmp     eax, 9000001Ch
0x14002d5c2  jz      short loc_14002D5CE
0x14002d5c4  mov     ebx, r14d
0x14002d5c7  cmp     eax, 0A0000022h
0x14002d5cc  jnz     short loc_14002D63E
0x14002d5ce  mov     dl, byte ptr cs:xmmword_14001A3D0+8
0x14002d5d4  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d5db  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d5e2  setnz   r8b
0x14002d5e6  and     dl, 80h
0x14002d5e9  jnz     short loc_14002D5F0
0x14002d5eb  test    r8b, r8b
0x14002d5ee  jz      short loc_14002D639
0x14002d5f0  mov     r9, cs:WPP_GLOBAL_Control
0x14002d5f7  lea     rax, aOnecoreBaseFsG_8; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002d5fe  mov     [rsp+78h+var_30], 227h
0x14002d606  mov     ecx, 307h
0x14002d60b  mov     [rsp+78h+var_38], rax
0x14002d610  lea     rax, WPP_52333d08ad443511f3c222844b8995a6_Traceguids
0x14002d617  mov     [rsp+78h+var_40], rax
0x14002d61c  mov     r9, [r9+40h]
0x14002d620  mov     [rsp+78h+var_48], 1Ah
0x14002d627  mov     [rsp+78h+var_50], 7
0x14002d62f  mov     [rsp+78h+var_58], 3
0x14002d634  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14002d639  mov     ebx, 0C0000022h
0x14002d63e  mov     rcx, rbp; P
0x14002d641  call    PrjfReleaseUnionContext
0x14002d646  test    ebx, ebx
0x14002d648  jns     short loc_14002D652
0x14002d64a  mov     esi, 4
0x14002d64f  mov     [rdi+18h], ebx
0x14002d652  mov     eax, esi
0x14002d654  add     rsp, 50h
0x14002d658  pop     r14
0x14002d65a  pop     rdi
0x14002d65b  pop     rsi
0x14002d65c  pop     rbp
0x14002d65d  pop     rbx
0x14002d65e  retn
```
