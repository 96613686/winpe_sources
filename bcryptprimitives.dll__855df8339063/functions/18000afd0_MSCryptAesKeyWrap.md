# MSCryptAesKeyWrap

- ea: `0x18000afd0`
- end: `0x18000b416`
- name: `MSCryptAesKeyWrap`
- size: `1094`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002b960`

## callees

- `0x18000ae00`
- `0x18000afd0`
- `0x18000b420`
- `0x18000c040`
- `0x18000ecb0`
- `0x18000ee60`
- `0x180010270`
- `0x1800102a0`
- `0x180063170`
- `0x18007f790`

## string_xrefs

- `0x18000b2f0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`
- `0x18000b325`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`
- `0x18000b392`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`
- `0x18000b3ba`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`
- `0x18000b3f4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`

## pseudocode

```c
__int64 __fastcall MSCryptAesKeyWrap(__int64 a1, __int64 a2, void *a3, unsigned int a4, unsigned int *a5)
{
  __int64 v7; // r15
  int v8; // edx
  int Property; // ebx
  __int64 v10; // r13
  int v11; // edx
  unsigned int v12; // edi
  unsigned int v13; // esi
  __int64 v14; // r12
  char *p_Src; // rsi
  int KeyData; // eax
  unsigned int v17; // r13d
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rax
  unsigned int v20; // edi
  unsigned int i; // edx
  int v22; // edx
  __int64 v23; // rcx
  __int128 *v24; // rax
  unsigned __int64 *v25; // rax
  size_t *p_Size; // rax
  size_t v28; // r8
  void *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rax
  unsigned int v32; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v33; // [rsp+54h] [rbp-ACh] BYREF
  __int128 v34; // [rsp+58h] [rbp-A8h] BYREF
  void *v35; // [rsp+68h] [rbp-98h]
  __int64 v36; // [rsp+70h] [rbp-90h]
  __int64 v37; // [rsp+78h] [rbp-88h]
  unsigned __int64 v38; // [rsp+80h] [rbp-80h] BYREF
  __int64 v39; // [rsp+88h] [rbp-78h]
  size_t Size; // [rsp+90h] [rbp-70h] BYREF
  __int128 v41; // [rsp+98h] [rbp-68h] BYREF
  char Src; // [rsp+B0h] [rbp-50h] BYREF

  *((_QWORD *)&v34 + 1) = a1;
  v35 = a3;
  v36 = a2;
  LODWORD(v34) = 0;
  v33 = 0;
  v32 = 0;
  v7 = 8;
  Property = MSCryptGetProperty(a2, (__int64)L"BlockLength", &v34, 4u, &v32, 0);
  v10 = 16;
  if ( Property < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
        (unsigned int)"Status",
        Property,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
        173);
    goto LABEL_40;
  }
  if ( v32 != 4 || (_DWORD)v34 != 16 )
  {
    Property = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c", 181);
    goto LABEL_40;
  }
  Property = MSCryptGetProperty(a1, (__int64)L"KeyLength", &v33, 4u, &v32, 0);
  if ( Property < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
        (unsigned int)"Status",
        Property,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
        195);
    goto LABEL_40;
  }
  v12 = v33 >> 3;
  if ( v32 != 4 || (v12 & 7) != 0 )
  {
    Property = -1073741816;
LABEL_40:
    *a5 = 0;
    goto LABEL_24;
  }
  v13 = v12 + 8;
  if ( !v35 )
  {
    Property = 0;
    goto LABEL_20;
  }
  if ( a4 < v13 )
  {
    Property = -1073741789;
    goto LABEL_20;
  }
  Size = v13;
  if ( v13 > 0x48 )
  {
    v31 = SafeAllocaAllocateFromHeap(v13);
    v14 = v31;
    if ( v31 )
    {
      p_Src = (char *)v31;
      goto LABEL_11;
    }
    Property = -1073741801;
    DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c", 243);
LABEL_20:
    *a5 = v13;
    goto LABEL_24;
  }
  v14 = 0;
  p_Src = &Src;
LABEL_11:
  KeyData = MSCryptGetKeyData(*((_QWORD *)&v34 + 1), p_Src + 8, v12);
  Property = KeyData;
  if ( KeyData < 0 )
  {
    DebugTraceError(
      (unsigned int)KeyData,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
      261);
    v17 = v12;
  }
  else
  {
    v17 = v12;
    v18 = (unsigned __int64)v12 >> 3;
    v19 = 0xA6A6A6A6A6A6A6A6uLL;
    *(_QWORD *)&v34 = v18;
    v20 = 0;
LABEL_13:
    if ( v20 >= 6 )
    {
      v28 = Size;
      v29 = v35;
      *(_QWORD *)p_Src = v19;
      memcpy_0(v29, p_Src, v28);
      Property = 0;
    }
    else
    {
      for ( i = 0; ; i = v33 + 1 )
      {
        v33 = i;
        *((_QWORD *)&v34 + 1) = i;
        if ( i >= v18 )
        {
          ++v20;
          goto LABEL_13;
        }
        v38 = v19;
        v37 = 8 * i;
        v39 = *(_QWORD *)&p_Src[v37 + 8];
        v41 = 0;
        Property = MSCryptEncrypt(v36, &v38, 0x10u, 0, &v41, 16, (unsigned __int64)&v38, 0x10u, &v32, 0);
        if ( Property < 0 )
          break;
        v19 = v38 ^ _byteswap_uint64(*((_QWORD *)&v34 + 1) + 1LL + v34 * v20);
        *(_QWORD *)&p_Src[v37 + 8] = v39;
        v18 = v34;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v22,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
          (unsigned int)"Status",
          Property,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
          40);
    }
    v12 = v17;
  }
  *a5 = v12 + 8;
  if ( p_Src )
  {
    v30 = v17 + 8;
    if ( v17 != -8 )
    {
      do
      {
        *p_Src++ = 0;
        --v30;
      }
      while ( v30 );
    }
  }
  if ( v14 )
    MSCryptFree(v14);
  v10 = 16;
LABEL_24:
  v23 = 16;
  v24 = &v41;
  do
  {
    *(_BYTE *)v24 = 0;
    v24 = (__int128 *)((char *)v24 + 1);
    --v23;
  }
  while ( v23 );
  v25 = &v38;
  do
  {
    *(_BYTE *)v25 = 0;
    v25 = (unsigned __int64 *)((char *)v25 + 1);
    --v10;
  }
  while ( v10 );
  p_Size = &Size;
  do
  {
    *(_BYTE *)p_Size = 0;
    p_Size = (size_t *)((char *)p_Size + 1);
    --v7;
  }
  while ( v7 );
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18000afd0  mov     [rsp-8+arg_18], rbx
0x18000afd5  push    rbp
0x18000afd6  push    rsi
0x18000afd7  push    rdi
0x18000afd8  push    r12
0x18000afda  push    r13
0x18000afdc  push    r14
0x18000afde  push    r15
0x18000afe0  lea     rbp, [rsp-10h]
0x18000afe5  sub     rsp, 110h
0x18000afec  mov     rax, cs:__security_cookie
0x18000aff3  xor     rax, rsp
0x18000aff6  mov     [rbp+40h+var_40], rax
0x18000affa  mov     r14, [rbp+40h+arg_20]
0x18000affe  xor     esi, esi
0x18000b000  mov     rdi, rcx
0x18000b003  mov     [rsp+140h+var_E0], rcx
0x18000b008  mov     rax, rdx
0x18000b00b  mov     [rsp+140h+var_D8], r8
0x18000b010  lea     rcx, [rsp+140h+var_F0]
0x18000b015  mov     [rsp+140h+var_D0], rdx
0x18000b01a  mov     r12d, r9d
0x18000b01d  mov     dword ptr [rsp+140h+var_118], esi
0x18000b021  mov     [rsp+140h+var_120], rcx
0x18000b026  lea     r9d, [rsi+4]
0x18000b02a  lea     r8, [rsp+140h+var_E8]
0x18000b02f  mov     dword ptr [rsp+140h+var_E8], esi
0x18000b033  lea     rdx, aBlocklength; "BlockLength"
0x18000b03a  mov     [rsp+140h+var_EC], esi
0x18000b03e  mov     rcx, rax
0x18000b041  mov     [rsp+140h+var_F0], esi
0x18000b045  call    MSCryptGetProperty
0x18000b04a  lea     r15d, [rsi+8]
0x18000b04e  mov     ebx, eax
0x18000b050  lea     r13d, [rsi+10h]
0x18000b054  test    eax, eax
0x18000b056  js      loc_18000B2B2
0x18000b05c  cmp     [rsp+140h+var_F0], 4
0x18000b061  jnz     loc_18000B3EE
0x18000b067  cmp     dword ptr [rsp+140h+var_E8], r13d
0x18000b06c  jnz     loc_18000B3EE
0x18000b072  lea     rax, [rsp+140h+var_F0]
0x18000b077  mov     dword ptr [rsp+140h+var_118], esi
0x18000b07b  lea     r9d, [rsi+4]
0x18000b07f  mov     [rsp+140h+var_120], rax
0x18000b084  lea     r8, [rsp+140h+var_EC]
0x18000b089  mov     rcx, rdi
0x18000b08c  lea     rdx, aKeylength; "KeyLength"
0x18000b093  call    MSCryptGetProperty
0x18000b098  mov     ebx, eax
0x18000b09a  test    eax, eax
0x18000b09c  js      loc_18000B343
0x18000b0a2  mov     edi, [rsp+140h+var_EC]
0x18000b0a6  shr     edi, 3
0x18000b0a9  cmp     [rsp+140h+var_F0], 4
0x18000b0ae  jnz     loc_18000B3E4
0x18000b0b4  test    dil, 7
0x18000b0b8  jnz     loc_18000B3E4
0x18000b0be  cmp     [rsp+140h+var_D8], 0
0x18000b0c4  lea     esi, [rdi+8]
0x18000b0c7  jz      loc_18000B1EF
0x18000b0cd  cmp     r12d, esi
0x18000b0d0  jb      loc_18000B36E
0x18000b0d6  mov     eax, esi
0x18000b0d8  mov     [rbp+40h+Size], rax
0x18000b0dc  cmp     esi, 48h ; 'H'
0x18000b0df  ja      loc_18000B378
0x18000b0e5  xor     r12d, r12d
0x18000b0e8  lea     rsi, [rbp+40h+Src]
0x18000b0ec  mov     rcx, [rsp+140h+var_E0]
0x18000b0f1  lea     rdx, [rsi+8]
0x18000b0f5  mov     r8d, edi
0x18000b0f8  call    MSCryptGetKeyData
0x18000b0fd  mov     ebx, eax
0x18000b0ff  test    eax, eax
0x18000b101  js      loc_18000B3B4
0x18000b107  mov     ecx, edi
0x18000b109  mov     r13d, edi
0x18000b10c  shr     rcx, 3
0x18000b110  mov     rax, 0A6A6A6A6A6A6A6A6h
0x18000b11a  mov     [rsp+140h+var_E8], rcx
0x18000b11f  xor     edi, edi
0x18000b121  cmp     edi, 6
0x18000b124  jnb     loc_18000B266
0x18000b12a  xor     edx, edx
0x18000b12c  mov     r8d, edx
0x18000b12f  mov     [rsp+140h+var_EC], edx
0x18000b133  mov     [rsp+140h+var_E0], r8
0x18000b138  cmp     r8, rcx
0x18000b13b  jnb     loc_18000B1E8
0x18000b141  mov     [rbp+40h+var_C0], rax
0x18000b145  lea     rcx, [rbp+40h+var_C0]
0x18000b149  mov     [rsp+140h+var_F8], 0
0x18000b151  lea     eax, ds:0[rdx*8]
0x18000b158  mov     [rsp+140h+var_C8], rax
0x18000b15d  lea     rdx, [rbp+40h+var_C0]
0x18000b161  mov     rax, [rax+rsi+8]
0x18000b166  xorps   xmm0, xmm0
0x18000b169  mov     [rbp+40h+var_B8], rax
0x18000b16d  xor     r9d, r9d
0x18000b170  lea     rax, [rsp+140h+var_F0]
0x18000b175  mov     [rsp+140h+var_100], rax
0x18000b17a  mov     eax, 10h
0x18000b17f  mov     [rsp+140h+var_108], eax
0x18000b183  mov     r8d, eax
0x18000b186  mov     [rsp+140h+var_110], rcx
0x18000b18b  lea     rcx, [rbp+40h+var_A8]
0x18000b18f  mov     dword ptr [rsp+140h+var_118], eax
0x18000b193  mov     [rsp+140h+var_120], rcx
0x18000b198  mov     rcx, [rsp+140h+var_D0]
0x18000b19d  movups  [rbp+40h+var_A8], xmm0
0x18000b1a1  call    MSCryptEncrypt
0x18000b1a6  mov     ebx, eax
0x18000b1a8  test    eax, eax
0x18000b1aa  js      loc_18000B2D3
0x18000b1b0  mov     rdx, [rsp+140h+var_C8]
0x18000b1b5  mov     rcx, [rsp+140h+var_E0]
0x18000b1ba  inc     rcx
0x18000b1bd  mov     eax, edi
0x18000b1bf  imul    rax, [rsp+140h+var_E8]
0x18000b1c5  add     rax, rcx
0x18000b1c8  mov     rcx, [rbp+40h+var_B8]
0x18000b1cc  bswap   rax
0x18000b1cf  xor     rax, [rbp+40h+var_C0]
0x18000b1d3  mov     [rdx+rsi+8], rcx
0x18000b1d8  mov     edx, [rsp+140h+var_EC]
0x18000b1dc  mov     rcx, [rsp+140h+var_E8]
0x18000b1e1  inc     edx
0x18000b1e3  jmp     loc_18000B12C
0x18000b1e8  inc     edi
0x18000b1ea  jmp     loc_18000B121
0x18000b1ef  xor     ebx, ebx
0x18000b1f1  mov     [r14], esi
0x18000b1f4  xor     esi, esi
0x18000b1f6  jmp     short loc_18000B209
0x18000b1f8  xor     esi, esi
0x18000b1fa  test    r12, r12
0x18000b1fd  jnz     loc_18000B3D7
0x18000b203  mov     r13d, 10h
0x18000b209  mov     rcx, r13
0x18000b20c  lea     rax, [rbp+40h+var_A8]
0x18000b210  mov     [rax], sil
0x18000b213  inc     rax
0x18000b216  sub     rcx, 1
0x18000b21a  jnz     short loc_18000B210
0x18000b21c  lea     rax, [rbp+40h+var_C0]
0x18000b220  mov     [rax], sil
0x18000b223  inc     rax
0x18000b226  sub     r13, 1
0x18000b22a  jnz     short loc_18000B220
0x18000b22c  lea     rax, [rbp+40h+Size]
0x18000b230  mov     [rax], sil
0x18000b233  inc     rax
0x18000b236  sub     r15, 1
0x18000b23a  jnz     short loc_18000B230
0x18000b23c  mov     eax, ebx
0x18000b23e  mov     rcx, [rbp+40h+var_40]
0x18000b242  xor     rcx, rsp; StackCookie
0x18000b245  call    __security_check_cookie
0x18000b24a  mov     rbx, [rsp+140h+arg_18]
0x18000b252  add     rsp, 110h
0x18000b259  pop     r15
0x18000b25b  pop     r14
0x18000b25d  pop     r13
0x18000b25f  pop     r12
0x18000b261  pop     rdi
0x18000b262  pop     rsi
0x18000b263  pop     rbp
0x18000b264  retn
0x18000b266  mov     r8, [rbp+40h+Size]; Size
0x18000b26a  mov     rdx, rsi; Src
0x18000b26d  mov     rcx, [rsp+140h+var_D8]; void *
0x18000b272  mov     [rsi], rax
0x18000b275  call    memcpy_0
0x18000b27a  xor     ebx, ebx
0x18000b27c  mov     edi, r13d
0x18000b27f  mov     eax, r15d
0x18000b282  mov     ecx, r15d
0x18000b285  add     eax, edi
0x18000b287  mov     [r14], eax
0x18000b28a  test    rsi, rsi
0x18000b28d  jz      loc_18000B1F8
0x18000b293  lea     eax, [rcx+r13]
0x18000b297  mov     ecx, eax
0x18000b299  test    eax, eax
0x18000b29b  jz      loc_18000B1F8
0x18000b2a1  mov     byte ptr [rsi], 0
0x18000b2a4  inc     rsi
0x18000b2a7  sub     rcx, 1
0x18000b2ab  jnz     short loc_18000B2A1
0x18000b2ad  jmp     loc_18000B1F8
0x18000b2b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2b9  lea     rax, WPP_GLOBAL_Control
0x18000b2c0  cmp     rcx, rax
0x18000b2c3  jz      short loc_18000B2CB
0x18000b2c5  test    byte ptr [rcx+1Ch], 1
0x18000b2c9  jnz     short loc_18000B319
0x18000b2cb  mov     [r14], esi
0x18000b2ce  jmp     loc_18000B209
0x18000b2d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2da  lea     rax, WPP_GLOBAL_Control
0x18000b2e1  cmp     rcx, rax
0x18000b2e4  jz      short loc_18000B27C
0x18000b2e6  test    byte ptr [rcx+1Ch], 1
0x18000b2ea  jz      short loc_18000B27C
0x18000b2ec  mov     rcx, [rcx+10h]
0x18000b2f0  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b2f7  mov     dword ptr [rsp+140h+var_110], 128h
0x18000b2ff  lea     r9, aStatus; "Status"
0x18000b306  mov     [rsp+140h+var_118], r8
0x18000b30b  mov     dword ptr [rsp+140h+var_120], ebx
0x18000b30f  call    WPP_SF_sDsd
0x18000b314  jmp     loc_18000B27C
0x18000b319  mov     dword ptr [rsp+140h+var_110], 0ADh
0x18000b321  mov     rcx, [rcx+10h]
0x18000b325  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b32c  mov     [rsp+140h+var_118], r8
0x18000b331  lea     r9, aStatus; "Status"
0x18000b338  mov     dword ptr [rsp+140h+var_120], ebx
0x18000b33c  call    WPP_SF_sDsd
0x18000b341  jmp     short loc_18000B2CB
0x18000b343  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b34a  lea     rax, WPP_GLOBAL_Control
0x18000b351  cmp     rcx, rax
0x18000b354  jz      loc_18000B2CB
0x18000b35a  test    byte ptr [rcx+1Ch], 1
0x18000b35e  jz      loc_18000B2CB
0x18000b364  mov     dword ptr [rsp+140h+var_110], 0C3h
0x18000b36c  jmp     short loc_18000B321
0x18000b36e  mov     ebx, 0C0000023h
0x18000b373  jmp     loc_18000B1F1
0x18000b378  mov     rcx, rax
0x18000b37b  call    SafeAllocaAllocateFromHeap
0x18000b380  mov     r12, rax
0x18000b383  test    rax, rax
0x18000b386  jnz     loc_18007FCE2
0x18000b38c  mov     r9d, 0F3h
0x18000b392  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b399  lea     rdx, aStatus; "Status"
0x18000b3a0  mov     ecx, 0C0000017h
0x18000b3a5  mov     ebx, 0C0000017h
0x18000b3aa  call    DebugTraceError
0x18000b3af  jmp     loc_18000B1F1
0x18000b3b4  mov     r9d, 105h
0x18000b3ba  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b3c1  lea     rdx, aStatus; "Status"
0x18000b3c8  mov     ecx, eax
0x18000b3ca  call    DebugTraceError
0x18000b3cf  mov     r13d, edi
0x18000b3d2  jmp     loc_18000B27F
0x18000b3d7  mov     rcx, r12
0x18000b3da  call    MSCryptFree
0x18000b3df  jmp     loc_18000B203
0x18000b3e4  mov     ebx, 0C0000008h
0x18000b3e9  jmp     loc_18000B2CB
0x18000b3ee  mov     r9d, 0B5h
0x18000b3f4  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b3fb  lea     rdx, aStatus; "Status"
0x18000b402  mov     ecx, 0C0000008h
0x18000b407  mov     ebx, 0C0000008h
0x18000b40c  call    DebugTraceError
0x18000b411  jmp     loc_18000B2CB
0x18007fce2  mov     rsi, rax
0x18007fce5  jmp     loc_18000B0EC
```
