# KdcUpdateAndValidateS4UProxyPAC(_KDC_S4U_TICKET_INFO *,uchar * *,ulong *,_S4U_DELEGATION_INFO * *)

- ea: `0x18004a000`
- end: `0x18004a414`
- name: `?KdcUpdateAndValidateS4UProxyPAC@@YAJPEAU_KDC_S4U_TICKET_INFO@@PEAPEAEPEAKPEAPEAU_S4U_DELEGATION_INFO@@@Z`
- size: `1044`
- prototype: `__int64 __fastcall(struct _KDC_S4U_TICKET_INFO *, unsigned __int8 **, unsigned int *, struct _S4U_DELEGATION_INFO **)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004ab84`

## callees

- `0x1800101c4`
- `0x1800101ec`
- `0x18001ff94`
- `0x18002005c`
- `0x180020230`
- `0x18002057c`
- `0x1800206c0`
- `0x1800206e8`
- `0x1800455e8`
- `0x18004a000`
- `0x18005a090`
- `0x18006f2d0`
- `0x18006fc78`
- `0x18006fcac`
- `0x18006feb0`
- `0x180070984`
- `0x180070f30`
- `0x180072338`
- `0x18007bef4`
- `0x18007c4d4`
- `0x1800837f8`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18004a235`
- `ntdll!RtlEqualUnicodeString` at `0x18004a235`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KdcUpdateAndValidateS4UProxyPAC(
        const struct _UNICODE_STRING *a1,
        struct _PACTYPE **a2,
        unsigned int *a3,
        struct _S4U_DELEGATION_INFO **a4)
{
  struct _PACTYPE *v4; // rbx
  __int64 v6; // rax
  unsigned int *v7; // r11
  struct _PAC_INFO_BUFFER *v8; // r8
  CSecurityData *v9; // rcx
  __int64 v10; // rdx
  int v11; // r13d
  struct _PAC_INFO_BUFFER *v12; // rax
  unsigned __int8 v13; // r8
  _BYTE *p_Buffer; // rsi
  unsigned int v15; // esi
  int v16; // edx
  unsigned __int8 *v17; // rcx
  struct _UNICODE_STRING *v19; // r13
  __int64 v20; // rdx
  struct _UNICODE_STRING *v21; // r8
  int updated; // eax
  CSecurityData *v23; // rcx
  __int64 v24; // rdx
  unsigned int Size; // esi
  PCUNICODE_STRING String2; // [rsp+48h] [rbp-89h] BYREF
  struct _PACTYPE *v27; // [rsp+50h] [rbp-81h] BYREF
  unsigned int v28; // [rsp+58h] [rbp-79h] BYREF
  struct _UNICODE_STRING *v29; // [rsp+60h] [rbp-71h]
  unsigned __int8 *v30; // [rsp+68h] [rbp-69h] BYREF
  struct _UNICODE_STRING v31; // [rsp+70h] [rbp-61h] BYREF
  struct _PACTYPE *v32; // [rsp+80h] [rbp-51h]
  struct _UNICODE_STRING v33; // [rsp+88h] [rbp-49h] BYREF
  __int128 v34; // [rsp+98h] [rbp-39h]
  _BYTE v35[48]; // [rsp+A8h] [rbp-29h] BYREF
  char v36; // [rsp+D8h] [rbp+7h] BYREF

  v4 = *a2;
  String2 = 0;
  v33 = 0;
  v34 = 0;
  v30 = 0;
  v28 = 0;
  v27 = 0;
  v31 = 0;
  v6 = lambda_bde1109c27f1d473909aeaf58a3f4245_::_lambda_bde1109c27f1d473909aeaf58a3f4245_(
         (unsigned int)&v36,
         (unsigned int)&v33,
         (unsigned int)&String2,
         (unsigned int)&v30,
         (__int64)&v31,
         (__int64)&v27);
  wil::scope_exit__lambda_bde1109c27f1d473909aeaf58a3f4245___(v35, v6);
  v32 = v4;
  if ( !PAC_UnMarshal(v4, *v7) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v10 = 48;
    goto LABEL_19;
  }
  v11 = 0;
  v29 = 0;
  v12 = PAC_Find(v4, 0xBu, v8);
  if ( v12 )
  {
    v16 = *((_DWORD *)v12 + 1);
    v17 = (unsigned __int8 *)*((_QWORD *)v12 + 1);
    String2 = 0;
    if ( (int)PAC_DecodeS4UDelegationInformation(v17, v16, (struct _S4U_DELEGATION_INFO **)&String2) < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_20;
      v10 = 51;
LABEL_19:
      WPP_SF_(*((_QWORD *)v9 + 2), v10, WPP_3875113a630833a3e73becf979560e87_Traceguids);
      goto LABEL_20;
    }
    p_Buffer = &a1[18].Buffer;
    if ( ((__int64)a1[18].Buffer & 0x100) != 0 )
    {
      v11 = (_DWORD)a1 + 208;
      v29 = (struct _UNICODE_STRING *)&a1[13];
    }
    else if ( (*p_Buffer & 4) != 0 )
    {
      if ( !RtlEqualUnicodeString(a1 + 13, String2, 1u) )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_ZZ(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            52,
            (unsigned int)WPP_3875113a630833a3e73becf979560e87_Traceguids,
            (_DWORD)a1 + 208,
            (__int64)String2);
        }
        v15 = 7;
        goto LABEL_21;
      }
      v11 = (int)v29;
    }
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        (unsigned int)WPP_3875113a630833a3e73becf979560e87_Traceguids,
        v11,
        *(_DWORD *)p_Buffer);
    }
  }
  else
  {
    p_Buffer = &a1[18].Buffer;
    if ( ((__int64)a1[18].Buffer & 0x100) == 0 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_3875113a630833a3e73becf979560e87_Traceguids, a1);
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v15 = 28;
      goto LABEL_21;
    }
    if ( (int)KerbDuplicateStringEx(&v33, a1 + 13, v13) < 0 )
    {
LABEL_20:
      v15 = 60;
      goto LABEL_21;
    }
    String2 = &v33;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    {
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_3875113a630833a3e73becf979560e87_Traceguids, &v33);
    }
  }
  v19 = 0;
  if ( (*(_DWORD *)p_Buffer & 0x100) != 0 )
  {
    v20 = *(_QWORD *)&a1->Length;
    if ( **(_WORD **)&a1->Length == 10 && *(_WORD *)(v20 + 2) == 1 )
      v21 = 0;
    else
      v21 = (struct _UNICODE_STRING *)&a1->Buffer;
    v15 = KerbConvertKdcNameToString(&v31, (struct _KERB_INTERNAL_NAME *)v20, v21);
    if ( v15 )
      goto LABEL_21;
    v19 = &v31;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    {
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_3875113a630833a3e73becf979560e87_Traceguids, &v31);
    }
  }
  updated = PAC_InitAndUpdateTransitedService((struct _S4U_DELEGATION_INFO *)String2, v19, v29, v32, &v27, &v28, &v30);
  if ( updated < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v24 = 55;
    goto LABEL_47;
  }
  Size = PAC_GetSize(v27);
  if ( !PAC_ReMarshal(v27, Size) )
    goto LABEL_20;
  if ( a4 )
  {
    updated = UnmarshalS4UDelegationInformation(v28, v30, a4);
    if ( updated < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_20;
      v24 = 56;
LABEL_47:
      WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_3875113a630833a3e73becf979560e87_Traceguids, (unsigned int)updated);
      goto LABEL_20;
    }
  }
  if ( *a2 != v27 )
  {
    MIDL_user_free(*a2);
    *a2 = v27;
    v27 = 0;
    *a3 = Size;
  }
  v15 = 0;
LABEL_21:
  wil::details::lambda_call__lambda_d92d7add183186a97495539912592b77___::_lambda_call__lambda_d92d7add183186a97495539912592b77___(v35);
  return v15;
}

```

## disassembly

```asm
0x18004a000  mov     rax, rsp
0x18004a003  mov     [rax+8], rbx
0x18004a007  mov     [rax+20h], r9
0x18004a00b  mov     [rax+18h], r8
0x18004a00f  mov     [rax+10h], rdx
0x18004a013  push    rbp
0x18004a014  push    rsi
0x18004a015  push    r13
0x18004a017  push    r14
0x18004a019  push    r15
0x18004a01b  lea     rbp, [rax-5Fh]
0x18004a01f  sub     rsp, 100h
0x18004a026  mov     r11, r8
0x18004a029  mov     rbx, [rdx]
0x18004a02c  mov     r15, rcx
0x18004a02f  xor     esi, esi
0x18004a031  mov     [rsp+120h+String2], rsi
0x18004a036  xorps   xmm0, xmm0
0x18004a039  movups  xmmword ptr [rbp+57h+var_A0.Length], xmm0
0x18004a03d  movups  [rbp+57h+var_90], xmm0
0x18004a041  mov     [rbp+57h+var_C0], rsi
0x18004a045  mov     [rbp+57h+var_D0], esi
0x18004a048  mov     [rsp+120h+var_D8], rsi
0x18004a04d  movups  xmmword ptr [rbp+57h+var_B8.Length], xmm0
0x18004a051  lea     rax, [rsp+120h+var_D8]
0x18004a056  mov     [rsp+120h+var_F8], rax
0x18004a05b  lea     rax, [rbp+57h+var_B8]
0x18004a05f  mov     [rsp+120h+var_100], rax
0x18004a064  lea     r9, [rbp+57h+var_C0]
0x18004a068  lea     r8, [rsp+120h+String2]
0x18004a06d  lea     rdx, [rbp+57h+var_A0]
0x18004a071  lea     rcx, [rbp+57h+var_50]
0x18004a075  call    _lambda_bde1109c27f1d473909aeaf58a3f4245____lambda_bde1109c27f1d473909aeaf58a3f4245_
0x18004a07a  mov     rdx, rax
0x18004a07d  lea     rcx, [rbp+57h+var_80]
0x18004a081  call    wil__scope_exit__lambda_bde1109c27f1d473909aeaf58a3f4245___
0x18004a086  nop
0x18004a087  mov     [rbp+57h+var_A8], rbx
0x18004a08b  mov     edx, [r11]; unsigned int
0x18004a08e  mov     rcx, rbx; struct _PACTYPE *
0x18004a091  call    ?PAC_UnMarshal@@YAKPEAU_PACTYPE@@K@Z; PAC_UnMarshal(_PACTYPE *,ulong)
0x18004a096  test    eax, eax
0x18004a098  jnz     short loc_18004A0CA
0x18004a09a  lea     rbx, WPP_GLOBAL_Control
0x18004a0a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a0a8  cmp     rcx, rbx
0x18004a0ab  jz      loc_18004A1DA
0x18004a0b1  test    byte ptr [rcx+1Ch], 1
0x18004a0b5  jz      loc_18004A1DA
0x18004a0bb  lea     edx, [rsi+30h]
0x18004a0be  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x18004a0c5  jmp     loc_18004A1D1
0x18004a0ca  mov     r13, rsi
0x18004a0cd  mov     [rbp+57h+var_C8], rsi
0x18004a0d1  mov     edx, 0Bh; unsigned int
0x18004a0d6  mov     rcx, rbx; struct _PACTYPE *
0x18004a0d9  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x18004a0de  lea     r14, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x18004a0e5  test    rax, rax
0x18004a0e8  jnz     loc_18004A196
0x18004a0ee  lea     rsi, [r15+128h]
0x18004a0f5  test    dword ptr [rsi], 100h
0x18004a0fb  jnz     short loc_18004A137
0x18004a0fd  lea     rbx, WPP_GLOBAL_Control
0x18004a104  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a10b  cmp     rcx, rbx
0x18004a10e  jz      short loc_18004A128
0x18004a110  test    byte ptr [rcx+1Ch], 1
0x18004a114  jz      short loc_18004A128
0x18004a116  lea     edx, [rax+31h]
0x18004a119  mov     r9, r15
0x18004a11c  mov     r8, r14
0x18004a11f  mov     rcx, [rcx+10h]
0x18004a123  call    WPP_SF_q
0x18004a128  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004a12d  mov     esi, 1Ch
0x18004a132  jmp     loc_18004A1DF
0x18004a137  lea     rdx, [r15+0D0h]; struct _UNICODE_STRING *
0x18004a13e  lea     rcx, [rbp+57h+var_A0]; struct _UNICODE_STRING *
0x18004a142  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18004a147  test    eax, eax
0x18004a149  js      loc_18004A1DA
0x18004a14f  lea     rax, [rbp+57h+var_A0]
0x18004a153  mov     [rsp+120h+String2], rax
0x18004a158  lea     rbx, WPP_GLOBAL_Control
0x18004a15f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a166  cmp     rcx, rbx
0x18004a169  jz      loc_18004A2BA
0x18004a16f  test    dword ptr [rcx+1Ch], 8000h
0x18004a176  jz      loc_18004A2BA
0x18004a17c  mov     edx, 32h ; '2'
0x18004a181  lea     r9, [rbp+57h+var_A0]
0x18004a185  mov     r8, r14
0x18004a188  mov     rcx, [rcx+10h]
0x18004a18c  call    WPP_SF_Z
0x18004a191  jmp     loc_18004A2BA
0x18004a196  mov     edx, [rax+4]; unsigned int
0x18004a199  mov     rcx, [rax+8]; unsigned __int8 *
0x18004a19d  mov     [rsp+120h+String2], rsi
0x18004a1a2  lea     r8, [rsp+120h+String2]; struct _S4U_DELEGATION_INFO **
0x18004a1a7  call    ?PAC_DecodeS4UDelegationInformation@@YAJPEAEKPEAPEAU_S4U_DELEGATION_INFO@@@Z; PAC_DecodeS4UDelegationInformation(uchar *,ulong,_S4U_DELEGATION_INFO * *)
0x18004a1ac  test    eax, eax
0x18004a1ae  jns     short loc_18004A202
0x18004a1b0  lea     rbx, WPP_GLOBAL_Control
0x18004a1b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a1be  cmp     rcx, rbx
0x18004a1c1  jz      short loc_18004A1DA
0x18004a1c3  test    byte ptr [rcx+1Ch], 1
0x18004a1c7  jz      short loc_18004A1DA
0x18004a1c9  mov     edx, 33h ; '3'
0x18004a1ce  mov     r8, r14
0x18004a1d1  mov     rcx, [rcx+10h]
0x18004a1d5  call    WPP_SF_
0x18004a1da  mov     esi, 3Ch ; '<'
0x18004a1df  lea     rcx, [rbp+57h+var_80]
0x18004a1e3  call    wil__details__lambda_call__lambda_d92d7add183186a97495539912592b77______lambda_call__lambda_d92d7add183186a97495539912592b77___
0x18004a1e8  mov     eax, esi
0x18004a1ea  mov     rbx, [rsp+120h+arg_0]
0x18004a1f2  add     rsp, 100h
0x18004a1f9  pop     r15
0x18004a1fb  pop     r14
0x18004a1fd  pop     r13
0x18004a1ff  pop     rsi
0x18004a200  pop     rbp
0x18004a201  retn
0x18004a202  lea     rsi, [r15+128h]
0x18004a209  test    dword ptr [rsi], 100h
0x18004a20f  jz      short loc_18004A21E
0x18004a211  lea     r13, [r15+0D0h]
0x18004a218  mov     [rbp+57h+var_C8], r13
0x18004a21c  jmp     short loc_18004A284
0x18004a21e  test    byte ptr [rsi], 4
0x18004a221  jz      short loc_18004A284
0x18004a223  lea     r13, [r15+0D0h]
0x18004a22a  mov     r8b, 1; CaseInsensitive
0x18004a22d  mov     rdx, [rsp+120h+String2]; String2
0x18004a232  mov     rcx, r13; String1
0x18004a235  call    cs:__imp_RtlEqualUnicodeString
0x18004a23b  test    al, al
0x18004a23d  jnz     short loc_18004A280
0x18004a23f  lea     rbx, WPP_GLOBAL_Control
0x18004a246  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a24d  cmp     rcx, rbx
0x18004a250  jz      short loc_18004A276
0x18004a252  test    byte ptr [rcx+1Ch], 1
0x18004a256  jz      short loc_18004A276
0x18004a258  mov     edx, 34h ; '4'
0x18004a25d  mov     rax, [rsp+120h+String2]
0x18004a262  mov     [rsp+120h+var_100], rax
0x18004a267  mov     r9, r13
0x18004a26a  mov     r8, r14
0x18004a26d  mov     rcx, [rcx+10h]
0x18004a271  call    WPP_SF_ZZ
0x18004a276  mov     esi, 7
0x18004a27b  jmp     loc_18004A1DF
0x18004a280  mov     r13, [rbp+57h+var_C8]
0x18004a284  lea     rbx, WPP_GLOBAL_Control
0x18004a28b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a292  cmp     rcx, rbx
0x18004a295  jz      short loc_18004A2BA
0x18004a297  test    dword ptr [rcx+1Ch], 8000h
0x18004a29e  jz      short loc_18004A2BA
0x18004a2a0  mov     edx, 35h ; '5'
0x18004a2a5  mov     eax, [rsi]
0x18004a2a7  mov     dword ptr [rsp+120h+var_100], eax
0x18004a2ab  mov     r9, r13
0x18004a2ae  mov     r8, r14
0x18004a2b1  mov     rcx, [rcx+10h]
0x18004a2b5  call    WPP_SF_Zd
0x18004a2ba  xor     r13d, r13d
0x18004a2bd  test    dword ptr [rsi], 100h
0x18004a2c3  jz      short loc_18004A31D
0x18004a2c5  mov     rdx, [r15]; struct _KERB_INTERNAL_NAME *
0x18004a2c8  cmp     word ptr [rdx], 0Ah
0x18004a2cc  jnz     short loc_18004A2DA
0x18004a2ce  cmp     word ptr [rdx+2], 1
0x18004a2d3  jnz     short loc_18004A2DA
0x18004a2d5  xor     r8d, r8d
0x18004a2d8  jmp     short loc_18004A2DE
0x18004a2da  lea     r8, [r15+8]; struct _UNICODE_STRING *
0x18004a2de  lea     rcx, [rbp+57h+var_B8]; struct _UNICODE_STRING *
0x18004a2e2  call    ?KerbConvertKdcNameToString@@YAJPEAU_UNICODE_STRING@@PEAU_KERB_INTERNAL_NAME@@0@Z; KerbConvertKdcNameToString(_UNICODE_STRING *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *)
0x18004a2e7  mov     esi, eax
0x18004a2e9  test    eax, eax
0x18004a2eb  jnz     loc_18004A1DF
0x18004a2f1  lea     r13, [rbp+57h+var_B8]
0x18004a2f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a2fc  cmp     rcx, rbx
0x18004a2ff  jz      short loc_18004A31D
0x18004a301  test    dword ptr [rcx+1Ch], 8000h
0x18004a308  jz      short loc_18004A31D
0x18004a30a  lea     edx, [rax+36h]
0x18004a30d  lea     r9, [rbp+57h+var_B8]
0x18004a311  mov     r8, r14
0x18004a314  mov     rcx, [rcx+10h]
0x18004a318  call    WPP_SF_Z
0x18004a31d  lea     rax, [rbp+57h+var_C0]
0x18004a321  mov     [rsp+30h], rax; unsigned __int8 **
0x18004a326  lea     rax, [rbp+57h+var_D0]
0x18004a32a  mov     [rsp+120h+var_F8], rax; unsigned int *
0x18004a32f  lea     rax, [rsp+120h+var_D8]
0x18004a334  mov     [rsp+120h+var_100], rax; struct _PACTYPE **
0x18004a339  mov     r9, [rbp+57h+var_A8]; struct _PACTYPE *
0x18004a33d  mov     r8, [rbp+57h+var_C8]; struct _UNICODE_STRING *
0x18004a341  mov     rdx, r13; struct _UNICODE_STRING *
0x18004a344  mov     rcx, [rsp+120h+String2]; struct _S4U_DELEGATION_INFO *
0x18004a349  call    ?PAC_InitAndUpdateTransitedService@@YAJPEAU_S4U_DELEGATION_INFO@@PEAU_UNICODE_STRING@@1PEAU_PACTYPE@@PEAPEAU3@PEAKPEAPEAE@Z; PAC_InitAndUpdateTransitedService(_S4U_DELEGATION_INFO *,_UNICODE_STRING *,_UNICODE_STRING *,_PACTYPE *,_PACTYPE * *,ulong *,uchar * *)
0x18004a34e  test    eax, eax
0x18004a350  jns     short loc_18004A385
0x18004a352  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a359  cmp     rcx, rbx
0x18004a35c  jz      loc_18004A1DA
0x18004a362  test    byte ptr [rcx+1Ch], 1
0x18004a366  jz      loc_18004A1DA
0x18004a36c  mov     edx, 37h ; '7'
0x18004a371  mov     r9d, eax
0x18004a374  mov     r8, r14
0x18004a377  mov     rcx, [rcx+10h]
0x18004a37b  call    WPP_SF_d
0x18004a380  jmp     loc_18004A1DA
0x18004a385  mov     rcx, [rsp+120h+var_D8]; struct _PACTYPE *
0x18004a38a  call    ?PAC_GetSize@@YAKPEAU_PACTYPE@@@Z; PAC_GetSize(_PACTYPE *)
0x18004a38f  mov     esi, eax
0x18004a391  mov     edx, eax; unsigned int
0x18004a393  mov     rcx, [rsp+120h+var_D8]; struct _PACTYPE *
0x18004a398  call    ?PAC_ReMarshal@@YAEPEAU_PACTYPE@@K@Z; PAC_ReMarshal(_PACTYPE *,ulong)
0x18004a39d  test    al, al
0x18004a39f  jz      loc_18004A1DA
0x18004a3a5  mov     rax, [rbp+57h+arg_18]
0x18004a3a9  test    rax, rax
0x18004a3ac  jz      short loc_18004A3E2
0x18004a3ae  mov     r8, rax; struct _S4U_DELEGATION_INFO **
0x18004a3b1  mov     rdx, [rbp+57h+var_C0]; unsigned __int8 *
0x18004a3b5  mov     ecx, [rbp+57h+var_D0]; unsigned int
0x18004a3b8  call    ?UnmarshalS4UDelegationInformation@@YAJKPEAEPEAPEAU_S4U_DELEGATION_INFO@@@Z; UnmarshalS4UDelegationInformation(ulong,uchar *,_S4U_DELEGATION_INFO * *)
0x18004a3bd  test    eax, eax
0x18004a3bf  jns     short loc_18004A3E2
0x18004a3c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a3c8  cmp     rcx, rbx
0x18004a3cb  jz      loc_18004A1DA
0x18004a3d1  test    byte ptr [rcx+1Ch], 1
0x18004a3d5  jz      loc_18004A1DA
0x18004a3db  mov     edx, 38h ; '8'
0x18004a3e0  jmp     short loc_18004A371
0x18004a3e2  mov     rbx, [rbp+57h+arg_8]
0x18004a3e6  mov     rcx, [rbx]; void *
0x18004a3e9  cmp     rcx, [rsp+120h+var_D8]
0x18004a3ee  jz      short loc_18004A40C
0x18004a3f0  call    MIDL_user_free
0x18004a3f5  mov     rax, [rsp+120h+var_D8]
0x18004a3fa  mov     [rbx], rax
0x18004a3fd  mov     [rsp+120h+var_D8], 0
0x18004a406  mov     rax, [rbp+57h+arg_10]
0x18004a40a  mov     [rax], esi
0x18004a40c  xor     esi, esi
0x18004a40e  jmp     loc_18004A1DF
```
