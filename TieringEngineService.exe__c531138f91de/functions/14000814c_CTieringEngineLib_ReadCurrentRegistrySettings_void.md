# CTieringEngineLib::ReadCurrentRegistrySettings(void)

- ea: `0x14000814c`
- end: `0x140008603`
- name: `?ReadCurrentRegistrySettings@CTieringEngineLib@@AEAAJXZ`
- size: `1207`
- prototype: `__int64 __fastcall(HKEY *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140006720`
- `0x140007e80`

## callees

- `0x140004a40`
- `0x140004a68`
- `0x14000814c`
- `0x140009ec8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400081a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400082d9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400083b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000848c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000856e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400081a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400082d9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400083b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000848c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000856e`

## string_xrefs

- `0x1400082a4`: `MaxHeatBlocksToReplaceInPercentage`

## pseudocode

```c
__int64 __fastcall CTieringEngineLib::ReadCurrentRegistrySettings(HKEY *this)
{
  unsigned int ValueW; // eax
  __int64 v3; // r9
  char v4; // al
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  HKEY v7; // rcx
  unsigned int v8; // eax
  __int64 v9; // r9
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  HKEY v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // r9
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  HKEY v17; // rcx
  LSTATUS v18; // eax
  __int64 v19; // r8
  char v20; // r9
  HKEY v21; // rcx
  LSTATUS v22; // eax
  __int64 v23; // r8
  unsigned __int64 v24; // rax
  unsigned int pvData; // [rsp+70h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+38h] BYREF

  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(this[16], 0, L"EnableDebugInterface", 0x10u, 0, &pvData, &pcbData);
  if ( ValueW )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_22;
    }
    v6 = 112;
    v3 = ValueW;
    goto LABEL_21;
  }
  v3 = pvData;
  if ( !pvData )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids);
    }
    goto LABEL_22;
  }
  if ( pvData != 1 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_22;
    }
    v6 = 111;
LABEL_21:
    WPP_SF_d(v5[2], v6, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, v3);
LABEL_22:
    v4 = 0;
    goto LABEL_23;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids);
  }
  v4 = 1;
LABEL_23:
  *((_BYTE *)this + 140) = v4;
  v7 = this[16];
  pcbData = 4;
  v8 = RegGetValueW(v7, 0, L"MaxHeatBlocksToReplaceInPercentage", 0x10u, 0, &pvData, &pcbData);
  if ( v8 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_39;
    }
    v11 = 115;
    v9 = v8;
    goto LABEL_38;
  }
  v9 = pvData;
  if ( pvData - 1 > 0x63 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_39;
    }
    v11 = 114;
LABEL_38:
    WPP_SF_d(v10[2], v11, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, v9);
LABEL_39:
    *((_WORD *)this + 71) = 10;
    goto LABEL_40;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, pvData);
    LOWORD(v9) = pvData;
  }
  *((_WORD *)this + 71) = v9;
LABEL_40:
  v12 = this[16];
  pcbData = 4;
  v13 = RegGetValueW(v12, 0, L"MaxInMemoryTreeSize", 0x10u, 0, &pvData, &pcbData);
  if ( v13 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_56;
    }
    v16 = 118;
    v14 = v13;
    goto LABEL_55;
  }
  v14 = pvData;
  if ( pvData - 50000 > 0x7734D0B0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_56;
    }
    v16 = 117;
LABEL_55:
    WPP_SF_d(v15[2], v16, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, v14);
LABEL_56:
    *((_DWORD *)this + 36) = 1000000000;
    goto LABEL_57;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, pvData);
    LODWORD(v14) = pvData;
  }
  *((_DWORD *)this + 36) = v14;
LABEL_57:
  v17 = this[16];
  pcbData = 4;
  v18 = RegGetValueW(v17, 0, L"PerfTierReservePercent", 0x10u, 0, &pvData, &pcbData);
  if ( v18 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, v19, 20, v18);
    }
    goto LABEL_72;
  }
  v20 = pvData;
  if ( pvData > 0x64 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, v19, pvData, 20);
    }
LABEL_72:
    *((_BYTE *)this + 148) = 20;
    goto LABEL_73;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, pvData);
    v20 = pvData;
  }
  *((_BYTE *)this + 148) = v20;
LABEL_73:
  v21 = this[16];
  pcbData = 4;
  v22 = RegGetValueW(v21, 0, L"PerfTierReserveMaxSizeInMb", 0x10u, 0, &pvData, &pcbData);
  if ( v22 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, v23, 25600, v22);
    }
    v24 = 0x640000000LL;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, pvData);
    }
    v24 = (unsigned __int64)pvData << 20;
  }
  this[19] = (HKEY)v24;
  return 0;
}

```

## disassembly

```asm
0x14000814c  mov     r11, rsp
0x14000814f  mov     [r11+18h], rbx
0x140008153  push    rbp
0x140008154  push    rsi
0x140008155  push    rdi
0x140008156  push    r13
0x140008158  push    r15
0x14000815a  mov     rbp, rsp
0x14000815d  sub     rsp, 40h
0x140008161  mov     r13d, 4
0x140008167  mov     [rbp+arg_0], 0
0x14000816e  lea     rax, [rbp+arg_8]
0x140008172  mov     [rbp+arg_8], r13d
0x140008176  mov     [r11-38h], rax
0x14000817a  lea     r8, Value; "EnableDebugInterface"
0x140008181  lea     rax, [rbp+arg_0]
0x140008185  mov     rdi, rcx
0x140008188  mov     rcx, [rcx+80h]; hkey
0x14000818f  lea     r9d, [r13+0Ch]; dwFlags
0x140008193  mov     [r11-40h], rax
0x140008197  xor     edx, edx; lpSubKey
0x140008199  mov     qword ptr [r11-48h], 0
0x1400081a1  call    cs:__imp_RegGetValueW
0x1400081a7  lea     rsi, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x1400081ae  lea     r15d, [r13-3]
0x1400081b2  test    eax, eax
0x1400081b4  jnz     loc_140008269
0x1400081ba  mov     r9d, [rbp+arg_0]
0x1400081be  test    r9d, r9d
0x1400081c1  jnz     short loc_140008202
0x1400081c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400081ca  lea     rbx, WPP_GLOBAL_Control
0x1400081d1  cmp     rcx, rbx
0x1400081d4  jz      loc_14000829C
0x1400081da  test    [rcx+1Ch], r15b
0x1400081de  jz      loc_14000829C
0x1400081e4  cmp     byte ptr [rcx+19h], 3
0x1400081e8  jb      loc_14000829C
0x1400081ee  mov     rcx, [rcx+10h]
0x1400081f2  lea     edx, [rax+6Dh]
0x1400081f5  mov     r8, rsi
0x1400081f8  call    WPP_SF_
0x1400081fd  jmp     loc_14000829C
0x140008202  cmp     r9d, r15d
0x140008205  jnz     short loc_140008243
0x140008207  mov     rcx, cs:WPP_GLOBAL_Control
0x14000820e  lea     rbx, WPP_GLOBAL_Control
0x140008215  lea     rsi, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x14000821c  cmp     rcx, rbx
0x14000821f  jz      short loc_14000823E
0x140008221  test    [rcx+1Ch], r15b
0x140008225  jz      short loc_14000823E
0x140008227  cmp     byte ptr [rcx+19h], 3
0x14000822b  jb      short loc_14000823E
0x14000822d  mov     rcx, [rcx+10h]
0x140008231  mov     edx, 6Eh ; 'n'
0x140008236  mov     r8, rsi
0x140008239  call    WPP_SF_
0x14000823e  mov     al, r15b
0x140008241  jmp     short loc_14000829E
0x140008243  mov     rcx, cs:WPP_GLOBAL_Control
0x14000824a  lea     rbx, WPP_GLOBAL_Control
0x140008251  cmp     rcx, rbx
0x140008254  jz      short loc_14000829C
0x140008256  test    [rcx+1Ch], r15b
0x14000825a  jz      short loc_14000829C
0x14000825c  cmp     byte ptr [rcx+19h], 2
0x140008260  jb      short loc_14000829C
0x140008262  mov     edx, 6Fh ; 'o'
0x140008267  jmp     short loc_140008290
0x140008269  mov     rcx, cs:WPP_GLOBAL_Control
0x140008270  lea     rbx, WPP_GLOBAL_Control
0x140008277  cmp     rcx, rbx
0x14000827a  jz      short loc_14000829C
0x14000827c  test    [rcx+1Ch], r15b
0x140008280  jz      short loc_14000829C
0x140008282  cmp     [rcx+19h], r13b
0x140008286  jb      short loc_14000829C
0x140008288  mov     edx, 70h ; 'p'
0x14000828d  mov     r9d, eax
0x140008290  mov     rcx, [rcx+10h]
0x140008294  mov     r8, rsi
0x140008297  call    WPP_SF_d
0x14000829c  xor     al, al
0x14000829e  mov     [rdi+8Ch], al
0x1400082a4  lea     r8, aMaxheatblockst; "MaxHeatBlocksToReplaceInPercentage"
0x1400082ab  mov     rcx, [rdi+80h]; hkey
0x1400082b2  lea     rax, [rbp+arg_8]
0x1400082b6  mov     [rsp+40h+pcbData], rax; pcbData
0x1400082bb  mov     r9d, 10h; dwFlags
0x1400082c1  lea     rax, [rbp+arg_0]
0x1400082c5  mov     [rbp+arg_8], r13d
0x1400082c9  mov     [rsp+40h+pvData], rax; pvData
0x1400082ce  xor     edx, edx; lpSubKey
0x1400082d0  mov     [rsp+40h+pdwType], 0; pdwType
0x1400082d9  call    cs:__imp_RegGetValueW
0x1400082df  test    eax, eax
0x1400082e1  jnz     short loc_140008346
0x1400082e3  mov     r9d, [rbp+arg_0]
0x1400082e7  lea     eax, [r9-1]
0x1400082eb  cmp     eax, 63h ; 'c'
0x1400082ee  ja      short loc_140008327
0x1400082f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400082f7  cmp     rcx, rbx
0x1400082fa  jz      short loc_14000831D
0x1400082fc  test    [rcx+1Ch], r15b
0x140008300  jz      short loc_14000831D
0x140008302  cmp     byte ptr [rcx+19h], 3
0x140008306  jb      short loc_14000831D
0x140008308  mov     rcx, [rcx+10h]
0x14000830c  mov     edx, 71h ; 'q'
0x140008311  mov     r8, rsi
0x140008314  call    WPP_SF_d
0x140008319  mov     r9d, [rbp+arg_0]
0x14000831d  mov     [rdi+8Eh], r9w
0x140008325  jmp     short loc_14000837B
0x140008327  mov     rcx, cs:WPP_GLOBAL_Control
0x14000832e  cmp     rcx, rbx
0x140008331  jz      short loc_140008372
0x140008333  test    [rcx+1Ch], r15b
0x140008337  jz      short loc_140008372
0x140008339  cmp     byte ptr [rcx+19h], 2
0x14000833d  jb      short loc_140008372
0x14000833f  mov     edx, 72h ; 'r'
0x140008344  jmp     short loc_140008366
0x140008346  mov     rcx, cs:WPP_GLOBAL_Control
0x14000834d  cmp     rcx, rbx
0x140008350  jz      short loc_140008372
0x140008352  test    [rcx+1Ch], r15b
0x140008356  jz      short loc_140008372
0x140008358  cmp     [rcx+19h], r13b
0x14000835c  jb      short loc_140008372
0x14000835e  mov     edx, 73h ; 's'
0x140008363  mov     r9d, eax
0x140008366  mov     rcx, [rcx+10h]
0x14000836a  mov     r8, rsi
0x14000836d  call    WPP_SF_d
0x140008372  mov     word ptr [rdi+8Eh], 0Ah
0x14000837b  mov     rcx, [rdi+80h]; hkey
0x140008382  lea     rax, [rbp+arg_8]
0x140008386  mov     [rsp+40h+pcbData], rax; pcbData
0x14000838b  lea     r8, aMaxinmemorytre; "MaxInMemoryTreeSize"
0x140008392  lea     rax, [rbp+arg_0]
0x140008396  mov     [rbp+arg_8], r13d
0x14000839a  mov     [rsp+40h+pvData], rax; pvData
0x14000839f  mov     r9d, 10h; dwFlags
0x1400083a5  xor     edx, edx; lpSubKey
0x1400083a7  mov     [rsp+40h+pdwType], 0; pdwType
0x1400083b0  call    cs:__imp_RegGetValueW
0x1400083b6  test    eax, eax
0x1400083b8  jnz     short loc_140008421
0x1400083ba  mov     r9d, [rbp+arg_0]
0x1400083be  lea     eax, [r9-0C350h]
0x1400083c5  cmp     eax, 7734D0B0h
0x1400083ca  ja      short loc_140008402
0x1400083cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400083d3  cmp     rcx, rbx
0x1400083d6  jz      short loc_1400083F9
0x1400083d8  test    [rcx+1Ch], r15b
0x1400083dc  jz      short loc_1400083F9
0x1400083de  cmp     byte ptr [rcx+19h], 3
0x1400083e2  jb      short loc_1400083F9
0x1400083e4  mov     rcx, [rcx+10h]
0x1400083e8  mov     edx, 74h ; 't'
0x1400083ed  mov     r8, rsi
0x1400083f0  call    WPP_SF_d
0x1400083f5  mov     r9d, [rbp+arg_0]
0x1400083f9  mov     [rdi+90h], r9d
0x140008400  jmp     short loc_140008457
0x140008402  mov     rcx, cs:WPP_GLOBAL_Control
0x140008409  cmp     rcx, rbx
0x14000840c  jz      short loc_14000844D
0x14000840e  test    [rcx+1Ch], r15b
0x140008412  jz      short loc_14000844D
0x140008414  cmp     byte ptr [rcx+19h], 2
0x140008418  jb      short loc_14000844D
0x14000841a  mov     edx, 75h ; 'u'
0x14000841f  jmp     short loc_140008441
0x140008421  mov     rcx, cs:WPP_GLOBAL_Control
0x140008428  cmp     rcx, rbx
0x14000842b  jz      short loc_14000844D
0x14000842d  test    [rcx+1Ch], r15b
0x140008431  jz      short loc_14000844D
0x140008433  cmp     [rcx+19h], r13b
0x140008437  jb      short loc_14000844D
0x140008439  mov     edx, 76h ; 'v'
0x14000843e  mov     r9d, eax
0x140008441  mov     rcx, [rcx+10h]
0x140008445  mov     r8, rsi
0x140008448  call    WPP_SF_d
0x14000844d  mov     dword ptr [rdi+90h], 3B9ACA00h
0x140008457  mov     rcx, [rdi+80h]; hkey
0x14000845e  lea     rax, [rbp+arg_8]
0x140008462  mov     [rsp+40h+pcbData], rax; pcbData
0x140008467  lea     r8, aPerftierreserv_0; "PerfTierReservePercent"
0x14000846e  lea     rax, [rbp+arg_0]
0x140008472  mov     [rbp+arg_8], r13d
0x140008476  mov     [rsp+40h+pvData], rax; pvData
0x14000847b  mov     r9d, 10h; dwFlags
0x140008481  xor     edx, edx; lpSubKey
0x140008483  mov     [rsp+40h+pdwType], 0; pdwType
0x14000848c  call    cs:__imp_RegGetValueW
0x140008492  test    eax, eax
0x140008494  jnz     short loc_140008504
0x140008496  mov     r9d, [rbp+arg_0]
0x14000849a  cmp     r9d, 64h ; 'd'
0x14000849e  ja      short loc_1400084D4
0x1400084a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400084a7  cmp     rcx, rbx
0x1400084aa  jz      short loc_1400084CB
0x1400084ac  test    [rcx+1Ch], r15b
0x1400084b0  jz      short loc_1400084CB
0x1400084b2  cmp     byte ptr [rcx+19h], 3
0x1400084b6  jb      short loc_1400084CB
0x1400084b8  mov     rcx, [rcx+10h]
0x1400084bc  lea     edx, [rax+77h]
0x1400084bf  mov     r8, rsi
0x1400084c2  call    WPP_SF_d
0x1400084c7  mov     r9d, [rbp+arg_0]
0x1400084cb  mov     [rdi+94h], r9b
0x1400084d2  jmp     short loc_140008539
0x1400084d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400084db  cmp     rcx, rbx
0x1400084de  jz      short loc_140008532
0x1400084e0  test    [rcx+1Ch], r15b
0x1400084e4  jz      short loc_140008532
0x1400084e6  cmp     byte ptr [rcx+19h], 2
0x1400084ea  jb      short loc_140008532
0x1400084ec  mov     rcx, [rcx+10h]
0x1400084f0  mov     edx, 78h ; 'x'
0x1400084f5  mov     dword ptr [rsp+40h+pdwType], 14h
0x1400084fd  call    WPP_SF_dd
0x140008502  jmp     short loc_140008532
0x140008504  mov     rcx, cs:WPP_GLOBAL_Control
0x14000850b  cmp     rcx, rbx
0x14000850e  jz      short loc_140008532
0x140008510  test    [rcx+1Ch], r15b
0x140008514  jz      short loc_140008532
0x140008516  cmp     [rcx+19h], r13b
0x14000851a  jb      short loc_140008532
0x14000851c  mov     rcx, [rcx+10h]
0x140008520  mov     edx, 79h ; 'y'
0x140008525  mov     dword ptr [rsp+40h+pdwType], eax
0x140008529  lea     r9d, [rdx-65h]
0x14000852d  call    WPP_SF_dd
0x140008532  mov     byte ptr [rdi+94h], 14h
0x140008539  mov     rcx, [rdi+80h]; hkey
0x140008540  lea     rax, [rbp+arg_8]
0x140008544  mov     [rsp+40h+pcbData], rax; pcbData
0x140008549  lea     r8, aPerftierreserv; "PerfTierReserveMaxSizeInMb"
0x140008550  lea     rax, [rbp+arg_0]
0x140008554  mov     [rbp+arg_8], r13d
0x140008558  mov     [rsp+40h+pvData], rax; pvData
0x14000855d  mov     r9d, 10h; dwFlags
0x140008563  xor     edx, edx; lpSubKey
0x140008565  mov     [rsp+40h+pdwType], 0; pdwType
0x14000856e  call    cs:__imp_RegGetValueW
0x140008574  test    eax, eax
0x140008576  jnz     short loc_1400085AC
0x140008578  mov     rcx, cs:WPP_GLOBAL_Control
0x14000857f  cmp     rcx, rbx
0x140008582  jz      short loc_1400085A3
0x140008584  test    [rcx+1Ch], r15b
0x140008588  jz      short loc_1400085A3
0x14000858a  cmp     byte ptr [rcx+19h], 3
0x14000858e  jb      short loc_1400085A3
0x140008590  mov     r9d, [rbp+arg_0]
0x140008594  lea     edx, [rax+7Ah]
0x140008597  mov     rcx, [rcx+10h]
0x14000859b  mov     r8, rsi
0x14000859e  call    WPP_SF_d
0x1400085a3  mov     eax, [rbp+arg_0]
0x1400085a6  shl     rax, 14h
0x1400085aa  jmp     short loc_1400085E6
0x1400085ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400085b3  cmp     rcx, rbx
0x1400085b6  jz      short loc_1400085DC
0x1400085b8  test    [rcx+1Ch], r15b
0x1400085bc  jz      short loc_1400085DC
0x1400085be  cmp     [rcx+19h], r13b
0x1400085c2  jb      short loc_1400085DC
0x1400085c4  mov     rcx, [rcx+10h]
0x1400085c8  mov     edx, 7Ch ; '|'
0x1400085cd  mov     r9d, 6400h
0x1400085d3  mov     dword ptr [rsp+40h+pdwType], eax
0x1400085d7  call    WPP_SF_dd
0x1400085dc  mov     rax, 640000000h
0x1400085e6  mov     [rdi+98h], rax
0x1400085ed  xor     eax, eax
0x1400085ef  mov     rbx, [rsp+40h+arg_10]
0x1400085f7  add     rsp, 40h
0x1400085fb  pop     r15
0x1400085fd  pop     r13
0x1400085ff  pop     rdi
0x140008600  pop     rsi
0x140008601  pop     rbp
0x140008602  retn
```
