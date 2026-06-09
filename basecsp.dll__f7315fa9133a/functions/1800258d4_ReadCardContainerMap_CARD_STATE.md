# ReadCardContainerMap(_CARD_STATE *)

- ea: `0x1800258d4`
- end: `0x180025a39`
- name: `?ReadCardContainerMap@@YAKPEAU_CARD_STATE@@@Z`
- size: `357`
- prototype: `__int64 __fastcall(struct _CARD_STATE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180023ed8`

## callees

- `0x18000de80`
- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x18001e66c`
- `0x1800258d4`

## pseudocode

```c
__int64 __fastcall ReadCardContainerMap(struct _CARD_STATE *a1)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rcx
  unsigned __int64 v5; // r8
  __int128 v7; // [rsp+30h] [rbp-18h] BYREF

  v7 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  v3 = CspReadFile(a1, "mscp", "cmapfile", 0, (char *)&v7 + 8, &v7);
  if ( v3 )
  {
    WppTraceIndent(v2, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
        (_DWORD)WPP_pszIndent,
        v3);
    }
    v4 = *((_QWORD *)&v7 + 1);
  }
  else
  {
    v4 = 0;
    v5 = (unsigned int)v7;
    *((_QWORD *)a1 + 71) = *((_QWORD *)&v7 + 1);
    *((_QWORD *)&v7 + 1) = 0;
    *((_DWORD *)a1 + 144) = v5 / 0x56;
  }
  if ( v4 )
    CspFreeH(v4);
  WppTraceIndent(v4, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      v3);
  }
  return v3;
}

```

## disassembly

```asm
0x1800258d4  mov     [rsp+arg_0], rbx
0x1800258d9  mov     [rsp+arg_8], rbp
0x1800258de  push    rdi
0x1800258df  sub     rsp, 40h
0x1800258e3  xorps   xmm0, xmm0
0x1800258e6  xor     edx, edx
0x1800258e8  movups  [rsp+48h+var_18], xmm0
0x1800258ed  mov     rdi, rcx
0x1800258f0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800258f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258fc  lea     rbp, WPP_GLOBAL_Control
0x180025903  cmp     rcx, rbp
0x180025906  jz      short loc_180025930
0x180025908  test    byte ptr [rcx+1Ch], 2
0x18002590c  jz      short loc_180025930
0x18002590e  cmp     byte ptr [rcx+19h], 5
0x180025912  jb      short loc_180025930
0x180025914  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002591b  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180025922  mov     rcx, [rcx+10h]
0x180025926  mov     edx, 1Bh
0x18002592b  call    WPP_SF_s
0x180025930  lea     rax, [rsp+48h+var_18]
0x180025935  xor     r9d, r9d
0x180025938  mov     [rsp+48h+var_20], rax
0x18002593d  lea     r8, aCmapfile; "cmapfile"
0x180025944  lea     rax, [rsp+48h+var_18+8]
0x180025949  mov     rcx, rdi
0x18002594c  lea     rdx, aMscp; "mscp"
0x180025953  mov     [rsp+48h+var_28], rax
0x180025958  call    CspReadFile
0x18002595d  mov     ebx, eax
0x18002595f  test    eax, eax
0x180025961  jz      short loc_1800259AC
0x180025963  mov     edx, 2
0x180025968  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002596d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025974  cmp     rcx, rbp
0x180025977  jz      short loc_1800259A5
0x180025979  test    byte ptr [rcx+1Ch], 1
0x18002597d  jz      short loc_1800259A5
0x18002597f  cmp     byte ptr [rcx+19h], 2
0x180025983  jb      short loc_1800259A5
0x180025985  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002598c  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180025993  mov     rcx, [rcx+10h]
0x180025997  mov     edx, 1Ch
0x18002599c  mov     dword ptr [rsp+48h+var_28], ebx
0x1800259a0  call    WPP_SF_sD
0x1800259a5  mov     rcx, qword ptr [rsp+48h+var_18+8]
0x1800259aa  jmp     short loc_1800259DB
0x1800259ac  mov     rax, qword ptr [rsp+48h+var_18+8]
0x1800259b1  xor     ecx, ecx
0x1800259b3  mov     r8d, dword ptr [rsp+48h+var_18]
0x1800259b8  mov     [rdi+238h], rax
0x1800259bf  mov     rax, 0BE82FA0BE82FA0BFh
0x1800259c9  mul     r8
0x1800259cc  mov     qword ptr [rsp+48h+var_18+8], rcx
0x1800259d1  shr     rdx, 6
0x1800259d5  mov     [rdi+240h], edx
0x1800259db  test    rcx, rcx
0x1800259de  jz      short loc_1800259E5
0x1800259e0  call    CspFreeH
0x1800259e5  mov     edx, 1
0x1800259ea  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800259ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800259f6  cmp     rcx, rbp
0x1800259f9  jz      short loc_180025A27
0x1800259fb  test    byte ptr [rcx+1Ch], 2
0x1800259ff  jz      short loc_180025A27
0x180025a01  cmp     byte ptr [rcx+19h], 5
0x180025a05  jb      short loc_180025A27
0x180025a07  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025a0e  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180025a15  mov     rcx, [rcx+10h]
0x180025a19  mov     edx, 1Dh
0x180025a1e  mov     dword ptr [rsp+48h+var_28], ebx
0x180025a22  call    WPP_SF_sD
0x180025a27  mov     rbp, [rsp+48h+arg_8]
0x180025a2c  mov     eax, ebx
0x180025a2e  mov     rbx, [rsp+48h+arg_0]
0x180025a33  add     rsp, 40h
0x180025a37  pop     rdi
0x180025a38  retn
```
