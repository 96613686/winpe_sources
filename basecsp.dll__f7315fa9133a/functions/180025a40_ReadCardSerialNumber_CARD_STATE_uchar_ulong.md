# ReadCardSerialNumber(_CARD_STATE *,uchar * *,ulong *)

- ea: `0x180025a40`
- end: `0x180025c85`
- name: `?ReadCardSerialNumber@@YAKPEAU_CARD_STATE@@PEAPEAEPEAK@Z`
- size: `581`
- prototype: `__int64 __fastcall(struct _CARD_STATE *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180023ed8`
- `0x180024a40`

## callees

- `0x18000a766`
- `0x18000de80`
- `0x180017bac`
- `0x180019430`
- `0x180019650`
- `0x1800196ac`
- `0x18001e66c`
- `0x180025a40`
- `0x180027d0c`

## pseudocode

```c
__int64 __fastcall ReadCardSerialNumber(struct _CARD_STATE *a1, unsigned __int8 **a2, unsigned int *a3)
{
  _DWORD *v6; // rcx
  __int64 v7; // rcx
  unsigned int CardProperty; // ebx
  _QWORD *v9; // rcx
  int v10; // edx
  __int64 v11; // rcx
  unsigned __int8 *v12; // rax
  __int64 v13; // rcx
  unsigned __int8 *v14; // rdi
  unsigned int v15; // eax
  size_t v16; // rcx
  size_t size[2]; // [rsp+30h] [rbp-38h] BYREF

  *(_OWORD *)size = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  if ( !a1 || !a2 || !a3 || !*((_QWORD *)a1 + 1) )
  {
    CardProperty = 87;
    goto LABEL_28;
  }
  *a2 = 0;
  *a3 = 0;
  v6 = (_DWORD *)*((_QWORD *)a1 + 1);
  if ( *v6 >= 6u )
  {
    CardProperty = GetCardProperty(v6, L"Card Identifier", &size[1], size, 0);
    if ( CardProperty )
    {
      WppTraceIndent(v7, 2);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 31;
LABEL_15:
        WPP_SF_sD(
          v9[2],
          v10,
          (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          (_DWORD)WPP_pszIndent,
          CardProperty);
        goto LABEL_28;
      }
      goto LABEL_28;
    }
LABEL_21:
    v12 = (unsigned __int8 *)MIDL_user_allocate(LODWORD(size[0]));
    v14 = v12;
    if ( v12 )
    {
      memcpy_0(v12, (const void *)size[1], LODWORD(size[0]));
      v15 = size[0];
      *a2 = v14;
      *a3 = v15;
    }
    else
    {
      WppTraceIndent(v13, 2);
      CardProperty = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          WPP_pszIndent);
      }
    }
    goto LABEL_28;
  }
  CardProperty = CspReadFile(a1, 0, "cardid", 0x10000, &size[1], size);
  if ( !CardProperty )
    goto LABEL_21;
  WppTraceIndent(v11, 2);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = 32;
    goto LABEL_15;
  }
LABEL_28:
  v16 = size[1];
  if ( size[1] )
    CspFreeH(size[1]);
  WppTraceIndent(v16, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardProperty);
  }
  return CardProperty;
}

```

## disassembly

```asm
0x180025a40  push    rbx
0x180025a42  push    rsi
0x180025a43  push    rdi
0x180025a44  push    r13
0x180025a46  push    r14
0x180025a48  sub     rsp, 40h
0x180025a4c  mov     r14, rdx
0x180025a4f  xorps   xmm0, xmm0
0x180025a52  xor     edx, edx
0x180025a54  mov     rsi, r8
0x180025a57  movups  xmmword ptr [rsp+68h+size], xmm0
0x180025a5c  mov     rbx, rcx
0x180025a5f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025a64  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a6b  lea     r13, WPP_GLOBAL_Control
0x180025a72  cmp     rcx, r13
0x180025a75  jz      short loc_180025A9F
0x180025a77  test    byte ptr [rcx+1Ch], 2
0x180025a7b  jz      short loc_180025A9F
0x180025a7d  cmp     byte ptr [rcx+19h], 5
0x180025a81  jb      short loc_180025A9F
0x180025a83  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025a8a  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180025a91  mov     rcx, [rcx+10h]
0x180025a95  mov     edx, 1Eh
0x180025a9a  call    WPP_SF_s
0x180025a9f  test    rbx, rbx
0x180025aa2  jz      loc_180025C21
0x180025aa8  test    r14, r14
0x180025aab  jz      loc_180025C21
0x180025ab1  test    rsi, rsi
0x180025ab4  jz      loc_180025C21
0x180025aba  cmp     qword ptr [rbx+8], 0
0x180025abf  jz      loc_180025C21
0x180025ac5  mov     qword ptr [r14], 0
0x180025acc  mov     dword ptr [rsi], 0
0x180025ad2  mov     rcx, [rbx+8]
0x180025ad6  cmp     dword ptr [rcx], 6
0x180025ad9  jb      short loc_180025B56
0x180025adb  lea     r9, [rsp+68h+size]
0x180025ae0  mov     dword ptr [rsp+68h+var_48], 0
0x180025ae8  lea     r8, [rsp+68h+size+8]
0x180025aed  lea     rdx, aCardIdentifier; "Card Identifier"
0x180025af4  call    GetCardProperty
0x180025af9  mov     ebx, eax
0x180025afb  test    eax, eax
0x180025afd  jz      loc_180025BB4
0x180025b03  mov     edx, 2
0x180025b08  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025b0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b14  cmp     rcx, r13
0x180025b17  jz      loc_180025C26
0x180025b1d  test    byte ptr [rcx+1Ch], 1
0x180025b21  jz      loc_180025C26
0x180025b27  cmp     byte ptr [rcx+19h], 2
0x180025b2b  jb      loc_180025C26
0x180025b31  mov     edx, 1Fh
0x180025b36  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025b3d  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180025b44  mov     rcx, [rcx+10h]
0x180025b48  mov     dword ptr [rsp+68h+var_48], ebx
0x180025b4c  call    WPP_SF_sD
0x180025b51  jmp     loc_180025C26
0x180025b56  lea     rax, [rsp+68h+size]
0x180025b5b  mov     r9d, 10000h
0x180025b61  mov     [rsp+68h+var_40], rax
0x180025b66  lea     r8, aCardid; "cardid"
0x180025b6d  lea     rax, [rsp+68h+size+8]
0x180025b72  xor     edx, edx
0x180025b74  mov     rcx, rbx
0x180025b77  mov     [rsp+68h+var_48], rax
0x180025b7c  call    CspReadFile
0x180025b81  mov     ebx, eax
0x180025b83  test    eax, eax
0x180025b85  jz      short loc_180025BB4
0x180025b87  mov     edx, 2
0x180025b8c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025b91  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b98  cmp     rcx, r13
0x180025b9b  jz      loc_180025C26
0x180025ba1  test    byte ptr [rcx+1Ch], 1
0x180025ba5  jz      short loc_180025C26
0x180025ba7  cmp     byte ptr [rcx+19h], 2
0x180025bab  jb      short loc_180025C26
0x180025bad  mov     edx, 20h ; ' '
0x180025bb2  jmp     short loc_180025B36
0x180025bb4  mov     ecx, dword ptr [rsp+68h+size]; size
0x180025bb8  call    MIDL_user_allocate
0x180025bbd  mov     rdi, rax
0x180025bc0  test    rax, rax
0x180025bc3  jnz     short loc_180025C04
0x180025bc5  lea     edx, [rax+2]
0x180025bc8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025bcd  lea     ebx, [rdi+8]
0x180025bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180025bd7  cmp     rcx, r13
0x180025bda  jz      short loc_180025C26
0x180025bdc  test    byte ptr [rcx+1Ch], 1
0x180025be0  jz      short loc_180025C26
0x180025be2  cmp     byte ptr [rcx+19h], 2
0x180025be6  jb      short loc_180025C26
0x180025be8  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025bef  lea     edx, [rdi+21h]
0x180025bf2  mov     rcx, [rcx+10h]
0x180025bf6  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180025bfd  call    WPP_SF_s
0x180025c02  jmp     short loc_180025C26
0x180025c04  mov     r8d, dword ptr [rsp+68h+size]; Size
0x180025c09  mov     rcx, rdi; void *
0x180025c0c  mov     rdx, [rsp+68h+size+8]; Src
0x180025c11  call    memcpy_0
0x180025c16  mov     eax, dword ptr [rsp+68h+size]
0x180025c1a  mov     [r14], rdi
0x180025c1d  mov     [rsi], eax
0x180025c1f  jmp     short loc_180025C26
0x180025c21  mov     ebx, 57h ; 'W'
0x180025c26  mov     rcx, [rsp+68h+size+8]
0x180025c2b  test    rcx, rcx
0x180025c2e  jz      short loc_180025C35
0x180025c30  call    CspFreeH
0x180025c35  mov     edx, 1
0x180025c3a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025c3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c46  cmp     rcx, r13
0x180025c49  jz      short loc_180025C77
0x180025c4b  test    byte ptr [rcx+1Ch], 2
0x180025c4f  jz      short loc_180025C77
0x180025c51  cmp     byte ptr [rcx+19h], 5
0x180025c55  jb      short loc_180025C77
0x180025c57  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025c5e  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180025c65  mov     rcx, [rcx+10h]
0x180025c69  mov     edx, 22h ; '"'
0x180025c6e  mov     dword ptr [rsp+68h+var_48], ebx
0x180025c72  call    WPP_SF_sD
0x180025c77  mov     eax, ebx
0x180025c79  add     rsp, 40h
0x180025c7d  pop     r14
0x180025c7f  pop     r13
0x180025c81  pop     rdi
0x180025c82  pop     rsi
0x180025c83  pop     rbx
0x180025c84  retn
```
