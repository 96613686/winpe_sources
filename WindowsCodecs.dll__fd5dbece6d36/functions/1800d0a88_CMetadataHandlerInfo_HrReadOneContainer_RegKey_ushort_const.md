# CMetadataHandlerInfo::HrReadOneContainer(RegKey *,ushort const *)

- ea: `0x1800d0a88`
- end: `0x1800d0d9e`
- name: `?HrReadOneContainer@CMetadataHandlerInfo@@IEAAJPEAVRegKey@@PEBG@Z`
- size: `790`
- prototype: `int(CMetadataHandlerInfo *__hidden this, struct RegKey *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002f424`

## callees

- `0x180052a04`
- `0x18008fd64`
- `0x18009eb68`
- `0x1800bb784`
- `0x1800c5a6c`
- `0x1800d0a88`
- `0x1800d0da4`
- `0x1800e2f90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d0d6f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d0d78`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d0d6f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d0d78`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800d0ae0`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800d0ae0`

## string_xrefs

- `0x1800d0b77`: `WriteHeader`
- `0x1800d0b55`: `WritePosition`
- `0x1800d0ba2`: `WriteOffset`

## pseudocode

```c
__int64 __fastcall CMetadataHandlerInfo::HrReadOneContainer(
        CMetadataHandlerInfo *this,
        struct RegKey *a2,
        const unsigned __int16 *a3)
{
  void *v5; // r14
  HRESULT IntValue; // eax
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 *v10; // rsi
  _QWORD *v11; // r8
  __int64 v12; // rax
  CRegistryInfo *v13; // rcx
  int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // edx
  int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // edx
  __int64 v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  __int64 v24; // [rsp+30h] [rbp-39h] BYREF
  void *v25; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v26[4]; // [rsp+40h] [rbp-29h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v28[4]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v29; // [rsp+70h] [rbp+7h]
  GUID iid; // [rsp+78h] [rbp+Fh] BYREF

  v25 = 0;
  v29 = 0;
  v5 = 0;
  iid = 0;
  *(_OWORD *)v26 = 0;
  *(_OWORD *)Block = 0;
  *(_OWORD *)v28 = 0;
  IntValue = IIDFromString(a3, &iid);
  v8 = IntValue;
  if ( IntValue < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_48;
LABEL_3:
    DoStackCapture(IntValue);
LABEL_48:
    free(Block[1]);
    free(v5);
    return (unsigned int)v8;
  }
  v9 = 0;
  v10 = (__int64 *)((char *)this + 304);
  while ( (unsigned int)v9 < *((_DWORD *)this + 73) )
  {
    v7 = 56LL * (unsigned int)v9;
    v11 = *(_QWORD **)(v7 + *v10);
    v12 = *(_QWORD *)&iid.Data1 - *v11;
    if ( *(_QWORD *)&iid.Data1 == *v11 )
      v12 = *(_QWORD *)iid.Data4 - v11[1];
    if ( !v12 )
      return (unsigned int)v8;
    v9 = (unsigned int)(v9 + 1);
  }
  if ( (*((_BYTE *)this + 76) & 0x10) != 0 )
  {
    IntValue = CRegistryInfo::SafeReadIntValue(a2, L"WritePosition", &v26[2]);
    v8 = IntValue;
    if ( IntValue < 0
      || (IntValue = CRegistryInfo::SafeReadBinaryValue(
                       v13,
                       a2,
                       L"WriteHeader",
                       (unsigned __int8 **)&Block[1],
                       (unsigned int *)Block),
          v8 = IntValue,
          IntValue < 0) )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_48;
      goto LABEL_3;
    }
    if ( (int)CRegistryInfo::SafeReadIntValue(a2, L"WriteOffset", v28) < 0 )
      *(_QWORD *)v28 = -1;
  }
  else if ( (*((_BYTE *)this + 76) & 8) != 0 )
  {
    v24 = 0;
    v14 = CComponentInfo::ReadPatterns<WICMetadataPattern>(v7, v9, a2, &v25, &v24, (char *)&v24 + 4);
    v8 = v14;
    if ( v14 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(v14);
      v5 = v25;
      goto LABEL_48;
    }
    v5 = v25;
    v29 = v24;
    *(_QWORD *)&v28[2] = v25;
  }
  v15 = *((_DWORD *)this + 118);
  v16 = v15 + 1;
  if ( v15 + 1 < v15 )
  {
    v8 = -2147024362;
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_48;
    DoStackCapture(-2147024362);
    goto LABEL_46;
  }
  if ( v16 <= *((_DWORD *)this + 117) )
  {
    *(GUID *)(*((_QWORD *)this + 56) + 16LL * v15) = iid;
    *((_DWORD *)this + 118) = v16;
    goto LABEL_31;
  }
  v17 = DynArrayImpl<0>::AddMultipleAndSet((__int64)this + 448, 0x10u, 1, &iid);
  v8 = v17;
  if ( v17 < 0 && (_DWORD)g_doStackCaptures )
    DoStackCapture(v17);
  if ( v8 < 0 )
  {
LABEL_46:
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v8);
    goto LABEL_48;
  }
LABEL_31:
  v18 = *((unsigned int *)this + 82);
  *(_QWORD *)v26 = *((_QWORD *)this + 56) + 16LL * (unsigned int)(*((_DWORD *)this + 118) - 1);
  v19 = v18 + 1;
  if ( (int)v18 + 1 < (unsigned int)v18 )
  {
    v8 = -2147024362;
    if ( !(_DWORD)g_doStackCaptures )
    {
LABEL_43:
      DynArray<_GUID,0>::RemoveAt((char *)this + 448, (unsigned int)(*((_DWORD *)this + 118) - 1));
      goto LABEL_48;
    }
    DoStackCapture(-2147024362);
LABEL_41:
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v8);
    goto LABEL_43;
  }
  if ( v19 <= *((_DWORD *)this + 81) )
  {
    v8 = 0;
    v20 = 56 * v18;
    v21 = *v10;
    *(_OWORD *)(v20 + v21) = *(_OWORD *)v26;
    *(_OWORD *)(v20 + v21 + 16) = *(_OWORD *)Block;
    *(_OWORD *)(v20 + v21 + 32) = *(_OWORD *)v28;
    *(_QWORD *)(v20 + v21 + 48) = v29;
    *((_DWORD *)this + 82) = v19;
    return (unsigned int)v8;
  }
  v22 = DynArrayImpl<0>::AddMultipleAndSet((__int64)this + 304, 0x38u, 1, v26);
  v8 = v22;
  if ( v22 < 0 && (_DWORD)g_doStackCaptures )
    DoStackCapture(v22);
  if ( v8 < 0 )
    goto LABEL_41;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800d0a88  push    rbp
0x1800d0a8a  push    rbx
0x1800d0a8b  push    rsi
0x1800d0a8c  push    rdi
0x1800d0a8d  push    r12
0x1800d0a8f  push    r14
0x1800d0a91  push    r15
0x1800d0a93  lea     rbp, [rsp-27h]
0x1800d0a98  sub     rsp, 90h
0x1800d0a9f  mov     rax, cs:__security_cookie
0x1800d0aa6  xor     rax, rsp
0x1800d0aa9  mov     [rbp+57h+var_38], rax
0x1800d0aad  xorps   xmm1, xmm1
0x1800d0ab0  mov     rdi, rdx
0x1800d0ab3  mov     r15, rcx
0x1800d0ab6  lea     rdx, [rbp+57h+iid]; lpiid
0x1800d0aba  xor     r12d, r12d
0x1800d0abd  xorps   xmm0, xmm0
0x1800d0ac0  xor     eax, eax
0x1800d0ac2  mov     [rbp+57h+var_88], r12
0x1800d0ac6  mov     rcx, r8; lpsz
0x1800d0ac9  mov     [rbp+57h+var_50], rax
0x1800d0acd  mov     r14d, r12d
0x1800d0ad0  movups  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x1800d0ad4  movups  xmmword ptr [rbp+57h+var_80], xmm1
0x1800d0ad8  movups  xmmword ptr [rbp+57h+Block], xmm1
0x1800d0adc  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x1800d0ae0  call    cs:__imp_IIDFromString
0x1800d0ae6  mov     ebx, eax
0x1800d0ae8  test    eax, eax
0x1800d0aea  jns     short loc_1800D0B09
0x1800d0aec  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d0af3  jz      short loc_1800D0B01
0x1800d0af5  mov     ecx, eax; int
0x1800d0af7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d0afc  jmp     loc_1800D0D6B
0x1800d0b01  test    eax, eax
0x1800d0b03  js      loc_1800D0D6B
0x1800d0b09  mov     edx, r12d
0x1800d0b0c  lea     rsi, [r15+130h]
0x1800d0b13  cmp     edx, [r15+124h]
0x1800d0b1a  jnb     short loc_1800D0B47
0x1800d0b1c  mov     eax, edx
0x1800d0b1e  imul    rcx, rax, 38h ; '8'
0x1800d0b22  mov     rax, [rsi]
0x1800d0b25  mov     r8, [rcx+rax]
0x1800d0b29  mov     rax, qword ptr [rbp+57h+iid.Data1]
0x1800d0b2d  sub     rax, [r8]
0x1800d0b30  jnz     short loc_1800D0B3A
0x1800d0b32  mov     rax, qword ptr [rbp+57h+iid.Data4]
0x1800d0b36  sub     rax, [r8+8]
0x1800d0b3a  test    rax, rax
0x1800d0b3d  jz      loc_1800D0D7E
0x1800d0b43  inc     edx
0x1800d0b45  jmp     short loc_1800D0B13
0x1800d0b47  test    byte ptr [r15+4Ch], 10h
0x1800d0b4c  jz      short loc_1800D0BBC
0x1800d0b4e  lea     r8, [rbp+57h+var_80+8]; unsigned int *
0x1800d0b52  mov     rcx, rdi; struct RegKey *
0x1800d0b55  lea     rdx, aWriteposition; "WritePosition"
0x1800d0b5c  call    ?SafeReadIntValue@CRegistryInfo@@KAJPEAVRegKey@@PEBGPEAK@Z; CRegistryInfo::SafeReadIntValue(RegKey *,ushort const *,ulong *)
0x1800d0b61  mov     ebx, eax
0x1800d0b63  test    eax, eax
0x1800d0b65  js      short loc_1800D0B89
0x1800d0b67  lea     rax, [rbp+57h+Block]
0x1800d0b6b  mov     rdx, rdi; struct RegKey *
0x1800d0b6e  lea     r9, [rbp+57h+Block+8]; unsigned __int8 **
0x1800d0b72  mov     [rsp+0C0h+var_A0], rax; unsigned int *
0x1800d0b77  lea     r8, aWriteheader; "WriteHeader"
0x1800d0b7e  call    ?SafeReadBinaryValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAPEAEPEAI@Z; CRegistryInfo::SafeReadBinaryValue(RegKey *,ushort const *,uchar * *,uint *)
0x1800d0b83  mov     ebx, eax
0x1800d0b85  test    eax, eax
0x1800d0b87  jns     short loc_1800D0B9B
0x1800d0b89  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d0b90  jz      loc_1800D0D6B
0x1800d0b96  jmp     loc_1800D0AF5
0x1800d0b9b  lea     r8, [rbp+57h+var_60]; unsigned int *
0x1800d0b9f  mov     rcx, rdi; struct RegKey *
0x1800d0ba2  lea     rdx, aWriteoffset; "WriteOffset"
0x1800d0ba9  call    ?SafeReadIntValue@CRegistryInfo@@KAJPEAVRegKey@@PEBGPEAK@Z; CRegistryInfo::SafeReadIntValue(RegKey *,ushort const *,ulong *)
0x1800d0bae  test    eax, eax
0x1800d0bb0  jns     short loc_1800D0C1C
0x1800d0bb2  mov     qword ptr [rbp+57h+var_60], 0FFFFFFFFFFFFFFFFh
0x1800d0bba  jmp     short loc_1800D0C1C
0x1800d0bbc  test    byte ptr [r15+4Ch], 8
0x1800d0bc1  jz      short loc_1800D0C1C
0x1800d0bc3  lea     rax, [rbp+57h+var_90+4]
0x1800d0bc7  mov     dword ptr [rbp+57h+var_90+4], r12d
0x1800d0bcb  mov     [rsp+0C0h+var_98], rax
0x1800d0bd0  lea     r9, [rbp+57h+var_88]
0x1800d0bd4  lea     rax, [rbp+57h+var_90]
0x1800d0bd8  mov     dword ptr [rbp+57h+var_90], r12d
0x1800d0bdc  mov     r8, rdi
0x1800d0bdf  mov     [rsp+0C0h+var_A0], rax
0x1800d0be4  call    ??$ReadPatterns@UWICMetadataPattern@@@CComponentInfo@@IEAAJP6AJPEAVRegKey@@PEAUWICMetadataPattern@@@Z0PEAPEAU2@PEAI4@Z; CComponentInfo::ReadPatterns<WICMetadataPattern>(long (*)(RegKey *,WICMetadataPattern *),RegKey *,WICMetadataPattern * *,uint *,uint *)
0x1800d0be9  mov     ebx, eax
0x1800d0beb  test    eax, eax
0x1800d0bed  jns     short loc_1800D0C08
0x1800d0bef  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d0bf6  jz      short loc_1800D0BFF
0x1800d0bf8  mov     ecx, eax; int
0x1800d0bfa  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d0bff  mov     r14, [rbp+57h+var_88]
0x1800d0c03  jmp     loc_1800D0D6B
0x1800d0c08  mov     eax, dword ptr [rbp+57h+var_90]
0x1800d0c0b  mov     r14, [rbp+57h+var_88]
0x1800d0c0f  mov     dword ptr [rbp+57h+var_50], eax
0x1800d0c12  mov     eax, dword ptr [rbp+57h+var_90+4]
0x1800d0c15  mov     dword ptr [rbp+57h+var_50+4], eax
0x1800d0c18  mov     qword ptr [rbp+57h+var_60+8], r14
0x1800d0c1c  lea     rdi, [r15+1C0h]
0x1800d0c23  mov     eax, [rdi+18h]
0x1800d0c26  lea     edx, [rax+1]
0x1800d0c29  cmp     edx, eax
0x1800d0c2b  jb      loc_1800D0D42
0x1800d0c31  cmp     edx, [rdi+14h]
0x1800d0c34  ja      short loc_1800D0C4C
0x1800d0c36  movups  xmm0, xmmword ptr [rbp+57h+iid.Data1]
0x1800d0c3a  mov     ecx, eax
0x1800d0c3c  mov     rax, [rdi]
0x1800d0c3f  add     rcx, rcx
0x1800d0c42  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x1800d0c47  mov     [rdi+18h], edx
0x1800d0c4a  jmp     short loc_1800D0C7F
0x1800d0c4c  mov     edx, 10h
0x1800d0c51  lea     r9, [rbp+57h+iid]
0x1800d0c55  mov     rcx, rdi
0x1800d0c58  lea     r8d, [rdx-0Fh]
0x1800d0c5c  call    ?AddMultipleAndSet@?$DynArrayImpl@$0A@@@IEAAJIIPEBX@Z; DynArrayImpl<0>::AddMultipleAndSet(uint,uint,void const *)
0x1800d0c61  mov     ebx, eax
0x1800d0c63  test    eax, eax
0x1800d0c65  jns     short loc_1800D0C77
0x1800d0c67  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d0c6e  jz      short loc_1800D0C77
0x1800d0c70  mov     ecx, eax; int
0x1800d0c72  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d0c77  test    ebx, ebx
0x1800d0c79  js      loc_1800D0D57
0x1800d0c7f  mov     ecx, [rdi+18h]
0x1800d0c82  mov     eax, [rsi+18h]
0x1800d0c85  dec     ecx
0x1800d0c87  shl     rcx, 4
0x1800d0c8b  add     rcx, [rdi]
0x1800d0c8e  mov     qword ptr [rbp+57h+var_80], rcx
0x1800d0c92  lea     edx, [rax+1]
0x1800d0c95  cmp     edx, eax
0x1800d0c97  jb      short loc_1800D0D06
0x1800d0c99  cmp     edx, [rsi+14h]
0x1800d0c9c  ja      short loc_1800D0CD5
0x1800d0c9e  movups  xmm0, xmmword ptr [rbp+57h+var_80]
0x1800d0ca2  mov     ebx, r12d
0x1800d0ca5  imul    rcx, rax, 38h ; '8'
0x1800d0ca9  mov     rax, [rsi]
0x1800d0cac  movups  xmmword ptr [rcx+rax], xmm0
0x1800d0cb0  movups  xmm1, xmmword ptr [rbp+57h+Block]
0x1800d0cb4  movups  xmmword ptr [rcx+rax+10h], xmm1
0x1800d0cb9  movups  xmm0, xmmword ptr [rbp+57h+var_60]
0x1800d0cbd  movups  xmmword ptr [rcx+rax+20h], xmm0
0x1800d0cc2  movsd   xmm1, [rbp+57h+var_50]
0x1800d0cc7  movsd   qword ptr [rcx+rax+30h], xmm1
0x1800d0ccd  mov     [rsi+18h], edx
0x1800d0cd0  jmp     loc_1800D0D7E
0x1800d0cd5  mov     edx, 38h ; '8'
0x1800d0cda  lea     r9, [rbp+57h+var_80]
0x1800d0cde  mov     rcx, rsi
0x1800d0ce1  lea     r8d, [rdx-37h]
0x1800d0ce5  call    ?AddMultipleAndSet@?$DynArrayImpl@$0A@@@IEAAJIIPEBX@Z; DynArrayImpl<0>::AddMultipleAndSet(uint,uint,void const *)
0x1800d0cea  mov     ebx, eax
0x1800d0cec  test    eax, eax
0x1800d0cee  jns     short loc_1800D0D00
0x1800d0cf0  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d0cf7  jz      short loc_1800D0D00
0x1800d0cf9  mov     ecx, eax; int
0x1800d0cfb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d0d00  test    ebx, ebx
0x1800d0d02  jns     short loc_1800D0D7E
0x1800d0d04  jmp     short loc_1800D0D1B
0x1800d0d06  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d0d0d  mov     ebx, 80070216h
0x1800d0d12  jz      short loc_1800D0D2B
0x1800d0d14  mov     ecx, ebx; int
0x1800d0d16  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d0d1b  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d0d22  jz      short loc_1800D0D2B
0x1800d0d24  mov     ecx, ebx; int
0x1800d0d26  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d0d2b  test    ebx, ebx
0x1800d0d2d  jns     short loc_1800D0D7E
0x1800d0d2f  lea     rcx, [r15+1C0h]
0x1800d0d36  mov     edx, [rcx+18h]
0x1800d0d39  dec     edx
0x1800d0d3b  call    ?RemoveAt@?$DynArray@U_GUID@@$0A@@@QEAAJI@Z; DynArray<_GUID,0>::RemoveAt(uint)
0x1800d0d40  jmp     short loc_1800D0D6B
0x1800d0d42  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d0d49  mov     ebx, 80070216h
0x1800d0d4e  jz      short loc_1800D0D67
0x1800d0d50  mov     ecx, ebx; int
0x1800d0d52  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d0d57  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d0d5e  jz      short loc_1800D0D67
0x1800d0d60  mov     ecx, ebx; int
0x1800d0d62  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d0d67  test    ebx, ebx
0x1800d0d69  jns     short loc_1800D0D7E
0x1800d0d6b  mov     rcx, [rbp+57h+Block+8]; Block
0x1800d0d6f  call    cs:__imp_free
0x1800d0d75  mov     rcx, r14; Block
0x1800d0d78  call    cs:__imp_free
0x1800d0d7e  mov     eax, ebx
0x1800d0d80  mov     rcx, [rbp+57h+var_38]
0x1800d0d84  xor     rcx, rsp; StackCookie
0x1800d0d87  call    __security_check_cookie
0x1800d0d8c  add     rsp, 90h
0x1800d0d93  pop     r15
0x1800d0d95  pop     r14
0x1800d0d97  pop     r12
0x1800d0d99  pop     rdi
0x1800d0d9a  pop     rsi
0x1800d0d9b  pop     rbx
0x1800d0d9c  pop     rbp
0x1800d0d9d  retn
```
