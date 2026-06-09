# IsDeviceCategoryQualified(uchar *,ulong,ushort *,ulong,ushort *,bool)

- ea: `0x18000eadc`
- end: `0x18000ef6b`
- name: `?IsDeviceCategoryQualified@@YAHPEAEKPEAGK1_N@Z`
- size: `1167`
- prototype: `__int64 __fastcall(wchar_t *String, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *AddressString, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000fe40`

## callees

- `0x18000a644`
- `0x18000a66c`
- `0x18000a778`
- `0x18000eadc`
- `0x18000f190`
- `0x18000f49c`
- `0x18000f968`
- `0x180010ed4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ec4f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ec80`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000edd0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ec4f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ec80`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000edd0`

## pseudocode

```c
__int64 __fastcall IsDeviceCategoryQualified(
        wchar_t *String,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *AddressString,
        bool a6)
{
  unsigned __int64 v6; // r15
  _QWORD *v8; // r10
  unsigned int v9; // ebx
  __int64 v10; // rdi
  wchar_t *v11; // rbp
  __int64 v12; // r13
  unsigned __int64 v13; // rcx
  _QWORD *v14; // rcx
  char v15; // si
  __int64 v16; // rdi
  __int64 v17; // r9
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  char v20; // si
  unsigned __int16 * near **v21; // r8
  const WCHAR *v22; // rcx
  __int64 v23; // rdx

  v6 = a2;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  v9 = 1;
  if ( (unsigned int)v6 < 4 )
    goto LABEL_72;
  LODWORD(v10) = 0;
  v11 = String;
  *((_BYTE *)String + (unsigned int)(v6 - 2)) = 0;
  LODWORD(v12) = 0;
  *((_BYTE *)String + (unsigned int)(v6 - 1)) = 0;
  v8 = WPP_GLOBAL_Control;
  if ( !*String )
    goto LABEL_72;
  v13 = 2LL * a6 + 7;
  while ( 2 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    {
      WPP_SF_S(v8[2], 78, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids, v11);
      goto LABEL_10;
    }
    while ( 1 )
    {
      if ( (unsigned int)v10 >= v13 )
        goto LABEL_68;
      if ( IsQualifiedCategory(v11, v10, a6) )
        break;
      LODWORD(v10) = v10 + 1;
LABEL_10:
      v13 = 2LL * a6 + 7;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
        v14 = WPP_GLOBAL_Control;
      }
      if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
        WPP_SF_S(v14[2], 73, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids, v11);
    }
    v15 = 0;
    v16 = 0;
    if ( a6 )
    {
      while ( CompareStringOrdinal(v11, -1, (LPCWCH)(&g_pszNetworkInfrastructureDevices)[v16], -1, 1) != 2 )
      {
        v16 = (unsigned int)(v16 + 1);
        if ( (unsigned int)v16 >= 4 )
          goto LABEL_29;
      }
    }
    else
    {
      while ( CompareStringOrdinal(
                L"NetworkInfrastructure",
                -1,
                (LPCWCH)(&g_pszQualifiedPnpxDeviceCategories)[v16],
                -1,
                1) != 2
           || !IsQualifiedCategory(v11, v16, 0) )
      {
        v16 = (unsigned int)(v16 + 1);
        if ( (unsigned int)v16 >= 7 )
          goto LABEL_29;
      }
    }
    v15 = 1;
LABEL_29:
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      LOBYTE(v17) = v15;
      WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids, v17);
      v18 = WPP_GLOBAL_Control;
    }
    v10 = 0;
    if ( v15 )
    {
      if ( !(unsigned int)IsIgdQualified(AddressString) )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v19 = 79;
          goto LABEL_37;
        }
        goto LABEL_69;
      }
      goto LABEL_59;
    }
    if ( v18 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v18 + 28) & 0x20) != 0 )
      {
        WPP_SF_(v18[2], 69, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
        v18 = WPP_GLOBAL_Control;
      }
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
        WPP_SF_S(v18[2], 70, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids, v11);
    }
    v20 = 0;
    while ( (unsigned int)v10 < 2 * (unsigned __int64)a6 + 7 )
    {
      v21 = &g_pszQualifiedDeviceDisplayCategories;
      if ( !a6 )
        v21 = &g_pszQualifiedPnpxDeviceCategories;
      v22 = L"Multimedia";
      if ( !a6 )
        v22 = L"MediaDevices";
      if ( CompareStringOrdinal(v22, -1, (LPCWCH)v21[v10], -1, 1) == 2 && IsQualifiedCategory(v11, v10, a6) )
      {
        v20 = 1;
        break;
      }
      v10 = (unsigned int)(v10 + 1);
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      LOBYTE(v17) = v20;
      WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids, v17);
      v8 = WPP_GLOBAL_Control;
    }
    LODWORD(v10) = 0;
    if ( !v20 )
    {
LABEL_60:
      v23 = -1;
      do
        ++v23;
      while ( v11[v23] );
      if ( 2 * (v23 + (unsigned __int64)(unsigned int)v12) + 2 < v6 )
      {
        v12 = (unsigned int)(v23 + v12 + 1);
        v11 = &String[v12];
        if ( *v11 )
        {
          v13 = 2LL * a6 + 7;
          continue;
        }
      }
      goto LABEL_72;
    }
    break;
  }
  if ( !(unsigned int)IsMcxDevice(a3, a4) )
  {
LABEL_59:
    v8 = WPP_GLOBAL_Control;
    goto LABEL_60;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v19 = 80;
LABEL_37:
    WPP_SF_(v8[2], v19, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
LABEL_68:
    v8 = WPP_GLOBAL_Control;
  }
LABEL_69:
  v9 = 0;
  if ( v8 == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)v8 + 28) & 8) != 0 )
  {
    WPP_SF_(v8[2], 81, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
LABEL_72:
  if ( v8 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v8 + 28) & 8) != 0 )
    {
      WPP_SF_d(v8[2], 82, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x20) != 0 )
      WPP_SF_(v8[2], 83, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  }
  return v9;
}

```

## disassembly

```asm
0x18000eadc  mov     [rsp+arg_0], rbx
0x18000eae1  mov     [rsp+arg_18], r9d
0x18000eae6  mov     [rsp+Str], r8
0x18000eaeb  push    rbp
0x18000eaec  push    rsi
0x18000eaed  push    rdi
0x18000eaee  push    r12
0x18000eaf0  push    r13
0x18000eaf2  push    r14
0x18000eaf4  push    r15
0x18000eaf6  sub     rsp, 40h
0x18000eafa  mov     r15d, edx
0x18000eafd  mov     r14, rcx
0x18000eb00  mov     r10, cs:WPP_GLOBAL_Control
0x18000eb07  lea     rdx, WPP_GLOBAL_Control
0x18000eb0e  cmp     r10, rdx
0x18000eb11  jz      short loc_18000EB3D
0x18000eb13  test    byte ptr [r10+1Ch], 20h
0x18000eb18  jz      short loc_18000EB3D
0x18000eb1a  mov     rcx, [r10+10h]
0x18000eb1e  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000eb25  mov     edx, 4Dh ; 'M'
0x18000eb2a  call    WPP_SF_
0x18000eb2f  mov     r10, cs:WPP_GLOBAL_Control
0x18000eb36  lea     rdx, WPP_GLOBAL_Control
0x18000eb3d  mov     ebx, 1
0x18000eb42  cmp     r15d, 4
0x18000eb46  jb      loc_18000EEFE
0x18000eb4c  movzx   r12d, [rsp+78h+arg_28]
0x18000eb55  lea     eax, [r15-2]
0x18000eb59  xor     edi, edi
0x18000eb5b  mov     rbp, r14
0x18000eb5e  mov     [rax+r14], dil
0x18000eb62  mov     r13d, edi
0x18000eb65  lea     eax, [r15-1]
0x18000eb69  mov     [rax+r14], dil
0x18000eb6d  mov     r10, cs:WPP_GLOBAL_Control
0x18000eb74  cmp     [r14], di
0x18000eb78  jz      loc_18000EEFE
0x18000eb7e  lea     rcx, ds:7[r12*2]
0x18000eb86  mov     [rsp+78h+var_48], rcx
0x18000eb8b  cmp     r10, rdx
0x18000eb8e  jz      short loc_18000EBB4
0x18000eb90  test    byte ptr [r10+1Ch], 8
0x18000eb95  jz      short loc_18000EBB4
0x18000eb97  mov     rcx, [r10+10h]
0x18000eb9b  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000eba2  mov     edx, 4Eh ; 'N'
0x18000eba7  mov     r9, rbp
0x18000ebaa  call    WPP_SF_S
0x18000ebaf  mov     rcx, [rsp+78h+var_48]
0x18000ebb4  mov     eax, edi
0x18000ebb6  cmp     rax, rcx
0x18000ebb9  jnb     loc_18000EEC2
0x18000ebbf  mov     r8b, r12b; bool
0x18000ebc2  mov     edx, edi; int
0x18000ebc4  mov     rcx, rbp; String
0x18000ebc7  call    ?IsQualifiedCategory@@YA_NPEBGH_N@Z; IsQualifiedCategory(ushort const *,int,bool)
0x18000ebcc  test    al, al
0x18000ebce  jnz     short loc_18000EBD4
0x18000ebd0  add     edi, ebx
0x18000ebd2  jmp     short loc_18000EBAF
0x18000ebd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebdb  lea     rdi, WPP_GLOBAL_Control
0x18000ebe2  cmp     rcx, rdi
0x18000ebe5  jz      short loc_18000EC2C
0x18000ebe7  test    byte ptr [rcx+1Ch], 20h
0x18000ebeb  jz      short loc_18000EC09
0x18000ebed  mov     rcx, [rcx+10h]
0x18000ebf1  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000ebf8  mov     edx, 48h ; 'H'
0x18000ebfd  call    WPP_SF_
0x18000ec02  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec09  cmp     rcx, rdi
0x18000ec0c  jz      short loc_18000EC2C
0x18000ec0e  test    byte ptr [rcx+1Ch], 8
0x18000ec12  jz      short loc_18000EC2C
0x18000ec14  mov     rcx, [rcx+10h]
0x18000ec18  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000ec1f  mov     edx, 49h ; 'I'
0x18000ec24  mov     r9, rbp
0x18000ec27  call    WPP_SF_S
0x18000ec2c  xor     sil, sil
0x18000ec2f  xor     edi, edi
0x18000ec31  test    r12b, r12b
0x18000ec34  jz      short loc_18000EC63
0x18000ec36  lea     rax, ?g_pszNetworkInfrastructureDevices@@3PAPEAGA; ushort * near * g_pszNetworkInfrastructureDevices
0x18000ec3d  mov     [rsp+78h+bIgnoreCase], ebx; bIgnoreCase
0x18000ec41  mov     r8, [rax+rdi*8]; lpString2
0x18000ec45  or      r9d, 0FFFFFFFFh; cchCount2
0x18000ec49  or      edx, r9d; cchCount1
0x18000ec4c  mov     rcx, rbp; lpString1
0x18000ec4f  call    cs:__imp_CompareStringOrdinal
0x18000ec55  cmp     eax, 2
0x18000ec58  jz      short loc_18000ECA5
0x18000ec5a  add     edi, ebx
0x18000ec5c  cmp     edi, 4
0x18000ec5f  jb      short loc_18000EC36
0x18000ec61  jmp     short loc_18000ECA8
0x18000ec63  or      r9d, 0FFFFFFFFh; cchCount2
0x18000ec67  mov     [rsp+78h+bIgnoreCase], ebx; bIgnoreCase
0x18000ec6b  lea     rax, ?g_pszQualifiedPnpxDeviceCategories@@3PAPEAGA; ushort * near * g_pszQualifiedPnpxDeviceCategories
0x18000ec72  or      edx, r9d; cchCount1
0x18000ec75  mov     r8, [rax+rdi*8]; lpString2
0x18000ec79  lea     rcx, String1; "NetworkInfrastructure"
0x18000ec80  call    cs:__imp_CompareStringOrdinal
0x18000ec86  cmp     eax, 2
0x18000ec89  jnz     short loc_18000EC9C
0x18000ec8b  xor     r8d, r8d; bool
0x18000ec8e  mov     edx, edi; int
0x18000ec90  mov     rcx, rbp; String
0x18000ec93  call    ?IsQualifiedCategory@@YA_NPEBGH_N@Z; IsQualifiedCategory(ushort const *,int,bool)
0x18000ec98  test    al, al
0x18000ec9a  jnz     short loc_18000ECA5
0x18000ec9c  add     edi, ebx
0x18000ec9e  cmp     edi, 7
0x18000eca1  jb      short loc_18000EC63
0x18000eca3  jmp     short loc_18000ECA8
0x18000eca5  mov     sil, bl
0x18000eca8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecaf  lea     rax, WPP_GLOBAL_Control
0x18000ecb6  cmp     rcx, rax
0x18000ecb9  jz      short loc_18000ECE7
0x18000ecbb  test    byte ptr [rcx+1Ch], 20h
0x18000ecbf  jz      short loc_18000ECE7
0x18000ecc1  mov     rcx, [rcx+10h]
0x18000ecc5  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000eccc  mov     edx, 4Ah ; 'J'
0x18000ecd1  mov     r9b, sil
0x18000ecd4  call    WPP_SF_c
0x18000ecd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ece0  lea     rax, WPP_GLOBAL_Control
0x18000ece7  xor     edi, edi
0x18000ece9  test    sil, sil
0x18000ecec  jz      short loc_18000ED3D
0x18000ecee  mov     rcx, [rsp+78h+AddressString]; AddressString
0x18000ecf6  call    ?IsIgdQualified@@YAHPEAG@Z; IsIgdQualified(ushort *)
0x18000ecfb  test    eax, eax
0x18000ecfd  jnz     loc_18000EE4B
0x18000ed03  mov     r10, cs:WPP_GLOBAL_Control
0x18000ed0a  lea     rsi, WPP_GLOBAL_Control
0x18000ed11  cmp     r10, rsi
0x18000ed14  jz      loc_18000EED2
0x18000ed1a  test    byte ptr [r10+1Ch], 8
0x18000ed1f  jz      loc_18000EED2
0x18000ed25  lea     edx, [rdi+4Fh]
0x18000ed28  mov     rcx, [r10+10h]
0x18000ed2c  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000ed33  call    WPP_SF_
0x18000ed38  jmp     loc_18000EECB
0x18000ed3d  cmp     rcx, rax
0x18000ed40  jz      short loc_18000ED8E
0x18000ed42  test    byte ptr [rcx+1Ch], 20h
0x18000ed46  jz      short loc_18000ED6B
0x18000ed48  mov     rcx, [rcx+10h]
0x18000ed4c  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000ed53  mov     edx, 45h ; 'E'
0x18000ed58  call    WPP_SF_
0x18000ed5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed64  lea     rax, WPP_GLOBAL_Control
0x18000ed6b  cmp     rcx, rax
0x18000ed6e  jz      short loc_18000ED8E
0x18000ed70  test    byte ptr [rcx+1Ch], 8
0x18000ed74  jz      short loc_18000ED8E
0x18000ed76  mov     rcx, [rcx+10h]
0x18000ed7a  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000ed81  mov     edx, 46h ; 'F'
0x18000ed86  mov     r9, rbp
0x18000ed89  call    WPP_SF_S
0x18000ed8e  mov     sil, dil
0x18000ed91  mov     eax, edi
0x18000ed93  cmp     rax, [rsp+78h+var_48]
0x18000ed98  jnb     short loc_18000EDF3
0x18000ed9a  lea     rdx, aMediadevices; "MediaDevices"
0x18000eda1  mov     [rsp+78h+bIgnoreCase], ebx; bIgnoreCase
0x18000eda5  test    r12b, r12b
0x18000eda8  lea     rcx, ?g_pszQualifiedPnpxDeviceCategories@@3PAPEAGA; ushort * near * g_pszQualifiedPnpxDeviceCategories
0x18000edaf  lea     r8, ?g_pszQualifiedDeviceDisplayCategories@@3PAPEAGA; ushort * near * g_pszQualifiedDeviceDisplayCategories
0x18000edb6  cmovz   r8, rcx
0x18000edba  lea     rcx, aMultimedia; "Multimedia"
0x18000edc1  cmovz   rcx, rdx; lpString1
0x18000edc5  or      r9d, 0FFFFFFFFh; cchCount2
0x18000edc9  or      edx, r9d; cchCount1
0x18000edcc  mov     r8, [r8+rdi*8]; lpString2
0x18000edd0  call    cs:__imp_CompareStringOrdinal
0x18000edd6  cmp     eax, 2
0x18000edd9  jnz     short loc_18000EDEC
0x18000eddb  mov     r8b, r12b; bool
0x18000edde  mov     edx, edi; int
0x18000ede0  mov     rcx, rbp; String
0x18000ede3  call    ?IsQualifiedCategory@@YA_NPEBGH_N@Z; IsQualifiedCategory(ushort const *,int,bool)
0x18000ede8  test    al, al
0x18000edea  jnz     short loc_18000EDF0
0x18000edec  add     edi, ebx
0x18000edee  jmp     short loc_18000ED91
0x18000edf0  mov     sil, bl
0x18000edf3  mov     r10, cs:WPP_GLOBAL_Control
0x18000edfa  lea     rax, WPP_GLOBAL_Control
0x18000ee01  cmp     r10, rax
0x18000ee04  jz      short loc_18000EE2C
0x18000ee06  test    byte ptr [r10+1Ch], 20h
0x18000ee0b  jz      short loc_18000EE2C
0x18000ee0d  mov     rcx, [r10+10h]
0x18000ee11  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000ee18  mov     edx, 47h ; 'G'
0x18000ee1d  mov     r9b, sil
0x18000ee20  call    WPP_SF_c
0x18000ee25  mov     r10, cs:WPP_GLOBAL_Control
0x18000ee2c  xor     edi, edi
0x18000ee2e  test    sil, sil
0x18000ee31  jz      short loc_18000EE58
0x18000ee33  mov     edx, [rsp+78h+arg_18]; unsigned int
0x18000ee3a  mov     rcx, [rsp+78h+Str]; Str
0x18000ee42  call    ?IsMcxDevice@@YAHPEAGK@Z; IsMcxDevice(ushort *,ulong)
0x18000ee47  test    eax, eax
0x18000ee49  jnz     short loc_18000EE9E
0x18000ee4b  mov     eax, ebx
0x18000ee4d  test    eax, eax
0x18000ee4f  jz      short loc_18000EEC4
0x18000ee51  mov     r10, cs:WPP_GLOBAL_Control
0x18000ee58  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000ee5c  inc     rdx
0x18000ee5f  cmp     [rbp+rdx*2+0], di
0x18000ee64  jnz     short loc_18000EE5C
0x18000ee66  mov     eax, r13d
0x18000ee69  add     rax, rdx
0x18000ee6c  lea     rcx, ds:2[rax*2]
0x18000ee74  cmp     rcx, r15
0x18000ee77  jnb     loc_18000EEFE
0x18000ee7d  inc     r13d
0x18000ee80  add     r13d, edx
0x18000ee83  lea     rbp, [r14+r13*2]
0x18000ee87  cmp     [rbp+0], di
0x18000ee8b  jz      short loc_18000EEFE
0x18000ee8d  mov     rcx, [rsp+78h+var_48]
0x18000ee92  lea     rdx, WPP_GLOBAL_Control
0x18000ee99  jmp     loc_18000EB8B
0x18000ee9e  mov     r10, cs:WPP_GLOBAL_Control
0x18000eea5  lea     rsi, WPP_GLOBAL_Control
0x18000eeac  cmp     r10, rsi
0x18000eeaf  jz      short loc_18000EED2
0x18000eeb1  test    byte ptr [r10+1Ch], 8
0x18000eeb6  jz      short loc_18000EED2
0x18000eeb8  mov     edx, 50h ; 'P'
0x18000eebd  jmp     loc_18000ED28
0x18000eec2  xor     edi, edi
0x18000eec4  lea     rsi, WPP_GLOBAL_Control
0x18000eecb  mov     r10, cs:WPP_GLOBAL_Control
0x18000eed2  mov     ebx, edi
0x18000eed4  cmp     r10, rsi
0x18000eed7  jz      short loc_18000EF51
0x18000eed9  test    byte ptr [r10+1Ch], 8
0x18000eede  jz      short loc_18000EF05
0x18000eee0  mov     rcx, [r10+10h]
0x18000eee4  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000eeeb  mov     edx, 51h ; 'Q'
0x18000eef0  call    WPP_SF_
0x18000eef5  mov     r10, cs:WPP_GLOBAL_Control
0x18000eefc  jmp     short loc_18000EF05
0x18000eefe  lea     rsi, WPP_GLOBAL_Control
0x18000ef05  cmp     r10, rsi
0x18000ef08  jz      short loc_18000EF51
0x18000ef0a  test    byte ptr [r10+1Ch], 8
0x18000ef0f  jz      short loc_18000EF30
0x18000ef11  mov     rcx, [r10+10h]
0x18000ef15  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000ef1c  mov     edx, 52h ; 'R'
0x18000ef21  mov     r9d, ebx
0x18000ef24  call    WPP_SF_d
0x18000ef29  mov     r10, cs:WPP_GLOBAL_Control
0x18000ef30  cmp     r10, rsi
0x18000ef33  jz      short loc_18000EF51
0x18000ef35  test    byte ptr [r10+1Ch], 20h
0x18000ef3a  jz      short loc_18000EF51
0x18000ef3c  mov     rcx, [r10+10h]
0x18000ef40  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000ef47  mov     edx, 53h ; 'S'
0x18000ef4c  call    WPP_SF_
0x18000ef51  mov     eax, ebx
0x18000ef53  mov     rbx, [rsp+78h+arg_0]
0x18000ef5b  add     rsp, 40h
0x18000ef5f  pop     r15
0x18000ef61  pop     r14
0x18000ef63  pop     r13
0x18000ef65  pop     r12
0x18000ef67  pop     rdi
0x18000ef68  pop     rsi
0x18000ef69  pop     rbp
0x18000ef6a  retn
```
