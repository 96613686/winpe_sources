# DavConvertIDNToPunyCodeUNC

- ea: `0x180010028`
- end: `0x18001039e`
- name: `DavConvertIDNToPunyCodeUNC`
- size: `886`
- prototype: `__int64 __fastcall(_WORD *, wchar_t **)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x18000235c`
- `0x180004344`
- `0x180006670`
- `0x180006d20`

## callees

- `0x18000b5f0`
- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b89c`
- `0x18000b93c`
- `0x18000fce0`
- `0x180010028`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001011a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010285`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001011a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010285`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800100eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800102c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800100eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800102c8`
- `KERNEL32!LocalFree` at `0x180010232`
- `KERNEL32!LocalFree` at `0x180010381`
- `KERNEL32!LocalFree` at `0x180010232`
- `KERNEL32!LocalFree` at `0x180010381`
- `KERNEL32!LocalAlloc` at `0x18001010c`
- `KERNEL32!LocalAlloc` at `0x1800101e5`
- `KERNEL32!LocalAlloc` at `0x18001010c`
- `KERNEL32!LocalAlloc` at `0x1800101e5`

## pseudocode

```c
__int64 __fastcall DavConvertIDNToPunyCodeUNC(_WORD *a1, wchar_t **a2)
{
  wchar_t **v2; // rbp
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rsi
  unsigned int v7; // r12d
  wchar_t *v8; // r14
  WCHAR *v9; // r15
  DWORD v10; // eax
  DWORD v11; // edi
  _QWORD *v12; // rcx
  __int64 v13; // rcx
  WCHAR v14; // ax
  _WORD *v15; // rax
  const wchar_t *v16; // rbp
  WCHAR *v17; // rcx
  unsigned int v18; // eax
  unsigned int v19; // edi
  size_t v20; // r13
  DWORD LastError; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  wchar_t v25; // ax
  WCHAR *v26; // rdx
  WCHAR *v27; // rcx
  HRESULT v28; // eax
  unsigned int v29; // esi

  v2 = a2;
  if ( !a1 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_16;
    v5 = 10;
LABEL_15:
    WPP_SF_(v4[2], v5, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids);
LABEL_16:
    SetLastError(0x57u);
    return 0;
  }
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  if ( (unsigned int)v6 < 3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, a1);
    goto LABEL_16;
  }
  if ( !a2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_16;
    v5 = 12;
    goto LABEL_15;
  }
  *a2 = 0;
  v7 = 0;
  v8 = 0;
  v9 = (WCHAR *)LocalAlloc(0x40u, 2LL * (unsigned int)(v6 + 2));
  if ( v9 )
  {
    v13 = 0;
    if ( *a1 )
    {
      do
      {
        v14 = a1[v13];
        if ( v14 == 64 || (unsigned int)v13 >= 2 && v14 == 92 )
          break;
        v9[v13] = v14;
        v13 = (unsigned int)(v13 + 1);
      }
      while ( a1[v13] );
    }
    v15 = &a1[v13];
    v9[v13] = 0;
    if ( *v15 == 92 || (v16 = 0, *v15 == 64) )
      v16 = &a1[v13];
    v17 = v9 + 2;
    if ( v9[1] != 92 )
      v17 = v9;
    v18 = DavConvertIDNToPunyCode(v17, 0, 0);
    v19 = v18;
    if ( !v18 )
    {
      v11 = 0;
      goto LABEL_37;
    }
    v20 = v18 + (_DWORD)v6 + 3;
    v8 = (wchar_t *)LocalAlloc(0x40u, 2 * v20);
    if ( v8 )
    {
      v25 = *v9;
      v8[1] = *v9;
      *v8 = v25;
      if ( v9[1] == 92 )
      {
        v26 = v8 + 2;
        v27 = v9 + 2;
      }
      else
      {
        v26 = v8;
        v27 = v9;
      }
      DavConvertIDNToPunyCode(v27, v26, v19);
      LastError = GetLastError();
      v11 = LastError;
      if ( !LastError )
      {
        if ( !v16 || (v28 = StringCchCatW(v8, v20, v16), v29 = v28, v28 >= 0) )
        {
          v2 = a2;
          v7 = v20;
          *a2 = v8;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v8);
          v11 = 0;
          goto LABEL_38;
        }
        SetLastError(v28);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v29);
LABEL_37:
        v2 = a2;
LABEL_38:
        LocalFree(v9);
        goto LABEL_39;
      }
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v23 = 15;
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v23 = 14;
    }
    WPP_SF_d(v22[2], v23, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, LastError);
    goto LABEL_37;
  }
  v10 = GetLastError();
  v11 = v10;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_40;
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v10);
LABEL_39:
  v12 = WPP_GLOBAL_Control;
LABEL_40:
  if ( !v11 && v7 )
    return v7;
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
    WPP_SF_Dd(v12[2], 18, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v11, v7);
  if ( v8 )
    LocalFree(v8);
  *v2 = 0;
  return 0;
}

```

## disassembly

```asm
0x180010028  mov     [rsp+arg_8], rdx
0x18001002d  push    rbx
0x18001002e  push    rbp
0x18001002f  push    rsi
0x180010030  push    rdi
0x180010031  push    r12
0x180010033  push    r13
0x180010035  push    r14
0x180010037  push    r15
0x180010039  sub     rsp, 38h
0x18001003d  xor     r13d, r13d
0x180010040  mov     rbp, rdx
0x180010043  mov     rdi, rcx
0x180010046  test    rcx, rcx
0x180010049  jnz     short loc_18001006D
0x18001004b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010052  lea     rbx, WPP_GLOBAL_Control
0x180010059  cmp     rcx, rbx
0x18001005c  jz      loc_1800100E6
0x180010062  test    byte ptr [rcx+1Ch], 1
0x180010066  jz      short loc_1800100E6
0x180010068  lea     edx, [rdi+0Ah]
0x18001006b  jmp     short loc_1800100D6
0x18001006d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180010071  inc     rsi
0x180010074  cmp     [rcx+rsi*2], r13w
0x180010079  jnz     short loc_180010071
0x18001007b  cmp     esi, 3
0x18001007e  jnb     short loc_1800100B3
0x180010080  mov     rcx, cs:WPP_GLOBAL_Control
0x180010087  lea     rbx, WPP_GLOBAL_Control
0x18001008e  cmp     rcx, rbx
0x180010091  jz      short loc_1800100E6
0x180010093  test    byte ptr [rcx+1Ch], 1
0x180010097  jz      short loc_1800100E6
0x180010099  mov     rcx, [rcx+10h]
0x18001009d  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x1800100a4  mov     edx, 0Bh
0x1800100a9  mov     r9, rdi
0x1800100ac  call    WPP_SF_S
0x1800100b1  jmp     short loc_1800100E6
0x1800100b3  test    rdx, rdx
0x1800100b6  jnz     short loc_1800100F6
0x1800100b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100bf  lea     rbx, WPP_GLOBAL_Control
0x1800100c6  cmp     rcx, rbx
0x1800100c9  jz      short loc_1800100E6
0x1800100cb  test    byte ptr [rcx+1Ch], 1
0x1800100cf  jz      short loc_1800100E6
0x1800100d1  mov     edx, 0Ch
0x1800100d6  mov     rcx, [rcx+10h]
0x1800100da  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x1800100e1  call    WPP_SF_
0x1800100e6  mov     ecx, 57h ; 'W'; dwErrCode
0x1800100eb  call    cs:__imp_SetLastError
0x1800100f1  jmp     loc_18001038B
0x1800100f6  mov     [rdx], r13
0x1800100f9  mov     ebx, 40h ; '@'
0x1800100fe  lea     edx, [rsi+2]
0x180010101  mov     ecx, ebx; uFlags
0x180010103  add     rdx, rdx; uBytes
0x180010106  mov     r12d, r13d
0x180010109  mov     r14, r13
0x18001010c  call    cs:__imp_LocalAlloc
0x180010112  mov     r15, rax
0x180010115  test    rax, rax
0x180010118  jnz     short loc_18001015F
0x18001011a  call    cs:__imp_GetLastError
0x180010120  mov     edi, eax
0x180010122  mov     rcx, cs:WPP_GLOBAL_Control
0x180010129  lea     rbx, WPP_GLOBAL_Control
0x180010130  cmp     rcx, rbx
0x180010133  jz      loc_18001023F
0x180010139  test    byte ptr [rcx+1Ch], 1
0x18001013d  jz      loc_18001023F
0x180010143  mov     rcx, [rcx+10h]
0x180010147  lea     edx, [r15+0Dh]
0x18001014b  mov     r9d, eax
0x18001014e  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180010155  call    WPP_SF_d
0x18001015a  jmp     loc_180010238
0x18001015f  mov     ecx, r13d
0x180010162  cmp     [rdi], r13w
0x180010166  jz      short loc_18001018A
0x180010168  movzx   eax, word ptr [rdi+rcx*2]
0x18001016c  cmp     ax, bx
0x18001016f  jz      short loc_18001018A
0x180010171  cmp     ecx, 2
0x180010174  jb      short loc_18001017C
0x180010176  cmp     ax, 5Ch ; '\'
0x18001017a  jz      short loc_18001018A
0x18001017c  mov     [r15+rcx*2], ax
0x180010181  inc     ecx
0x180010183  cmp     [rdi+rcx*2], r13w
0x180010188  jnz     short loc_180010168
0x18001018a  lea     rax, [rdi+rcx*2]
0x18001018e  mov     [r15+rcx*2], r13w
0x180010193  cmp     word ptr [rax], 5Ch ; '\'
0x180010197  jz      short loc_1800101A1
0x180010199  mov     rbp, r13
0x18001019c  cmp     [rax], bx
0x18001019f  jnz     short loc_1800101A4
0x1800101a1  mov     rbp, rax
0x1800101a4  cmp     word ptr [r15+2], 5Ch ; '\'
0x1800101aa  lea     rcx, [r15+4]
0x1800101ae  jz      short loc_1800101B3
0x1800101b0  mov     rcx, r15; hMem
0x1800101b3  xor     r8d, r8d
0x1800101b6  xor     edx, edx
0x1800101b8  call    DavConvertIDNToPunyCode
0x1800101bd  lea     rbx, WPP_GLOBAL_Control
0x1800101c4  mov     edi, eax
0x1800101c6  test    eax, eax
0x1800101c8  jz      loc_180010349
0x1800101ce  lea     r13d, [rsi+3]
0x1800101d2  mov     ecx, 40h ; '@'; uFlags
0x1800101d7  add     r13d, eax
0x1800101da  mov     esi, r13d
0x1800101dd  lea     rdx, ds:0[r13*2]; uBytes
0x1800101e5  call    cs:__imp_LocalAlloc
0x1800101eb  mov     r14, rax
0x1800101ee  test    rax, rax
0x1800101f1  jnz     short loc_180010258
0x1800101f3  call    cs:__imp_GetLastError
0x1800101f9  mov     edi, eax
0x1800101fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180010202  cmp     rcx, rbx
0x180010205  jz      short loc_180010224
0x180010207  test    byte ptr [rcx+1Ch], 1
0x18001020b  jz      short loc_180010224
0x18001020d  lea     edx, [r14+0Eh]
0x180010211  mov     rcx, [rcx+10h]
0x180010215  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18001021c  mov     r9d, eax
0x18001021f  call    WPP_SF_d
0x180010224  xor     r13d, r13d
0x180010227  mov     rbp, [rsp+78h+arg_8]
0x18001022f  mov     rcx, r15; hMem
0x180010232  call    cs:__imp_LocalFree
0x180010238  mov     rcx, cs:WPP_GLOBAL_Control
0x18001023f  test    edi, edi
0x180010241  jnz     loc_180010351
0x180010247  test    r12d, r12d
0x18001024a  jz      loc_180010351
0x180010250  mov     eax, r12d
0x180010253  jmp     loc_18001038D
0x180010258  movzx   eax, word ptr [r15]
0x18001025c  mov     [r14+2], ax
0x180010261  mov     [r14], ax
0x180010265  cmp     word ptr [r15+2], 5Ch ; '\'
0x18001026b  jnz     short loc_180010277
0x18001026d  lea     rdx, [r14+4]
0x180010271  lea     rcx, [r15+4]
0x180010275  jmp     short loc_18001027D
0x180010277  mov     rdx, r14
0x18001027a  mov     rcx, r15; hMem
0x18001027d  mov     r8d, edi
0x180010280  call    DavConvertIDNToPunyCode
0x180010285  call    cs:__imp_GetLastError
0x18001028b  mov     edi, eax
0x18001028d  test    eax, eax
0x18001028f  jz      short loc_1800102AD
0x180010291  mov     rcx, cs:WPP_GLOBAL_Control
0x180010298  cmp     rcx, rbx
0x18001029b  jz      short loc_180010224
0x18001029d  test    byte ptr [rcx+1Ch], 1
0x1800102a1  jz      short loc_180010224
0x1800102a3  mov     edx, 0Fh
0x1800102a8  jmp     loc_180010211
0x1800102ad  test    rbp, rbp
0x1800102b0  jz      short loc_180010305
0x1800102b2  mov     r8, rbp; pszSrc
0x1800102b5  mov     rdx, rsi; cchDest
0x1800102b8  mov     rcx, r14; pszDest
0x1800102bb  call    StringCchCatW
0x1800102c0  mov     esi, eax
0x1800102c2  test    eax, eax
0x1800102c4  jns     short loc_180010305
0x1800102c6  mov     ecx, eax; dwErrCode
0x1800102c8  call    cs:__imp_SetLastError
0x1800102ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102d5  cmp     rcx, rbx
0x1800102d8  jz      loc_180010224
0x1800102de  test    byte ptr [rcx+1Ch], 1
0x1800102e2  jz      loc_180010224
0x1800102e8  mov     rcx, [rcx+10h]
0x1800102ec  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x1800102f3  mov     edx, 10h
0x1800102f8  mov     r9d, esi
0x1800102fb  call    WPP_SF_d
0x180010300  jmp     loc_180010224
0x180010305  mov     rbp, [rsp+78h+arg_8]
0x18001030d  mov     r12d, r13d
0x180010310  mov     [rbp+0], r14
0x180010314  mov     rcx, cs:WPP_GLOBAL_Control
0x18001031b  cmp     rcx, rbx
0x18001031e  jz      short loc_18001033E
0x180010320  test    byte ptr [rcx+1Ch], 2
0x180010324  jz      short loc_18001033E
0x180010326  mov     rcx, [rcx+10h]
0x18001032a  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180010331  mov     edx, 11h
0x180010336  mov     r9, r14
0x180010339  call    WPP_SF_S
0x18001033e  xor     r13d, r13d
0x180010341  mov     edi, r13d
0x180010344  jmp     loc_18001022F
0x180010349  mov     edi, r13d
0x18001034c  jmp     loc_180010227
0x180010351  cmp     rcx, rbx
0x180010354  jz      short loc_180010379
0x180010356  test    byte ptr [rcx+1Ch], 2
0x18001035a  jz      short loc_180010379
0x18001035c  mov     rcx, [rcx+10h]
0x180010360  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180010367  mov     edx, 12h
0x18001036c  mov     [rsp+78h+var_58], r12d
0x180010371  mov     r9d, edi
0x180010374  call    WPP_SF_Dd
0x180010379  test    r14, r14
0x18001037c  jz      short loc_180010387
0x18001037e  mov     rcx, r14; hMem
0x180010381  call    cs:__imp_LocalFree
0x180010387  mov     [rbp+0], r13
0x18001038b  xor     eax, eax
0x18001038d  add     rsp, 38h
0x180010391  pop     r15
0x180010393  pop     r14
0x180010395  pop     r13
0x180010397  pop     r12
0x180010399  pop     rdi
0x18001039a  pop     rsi
0x18001039b  pop     rbp
0x18001039c  pop     rbx
0x18001039d  retn
```
