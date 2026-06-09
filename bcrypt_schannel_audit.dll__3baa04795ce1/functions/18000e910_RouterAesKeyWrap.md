# RouterAesKeyWrap

- ea: `0x18000e910`
- end: `0x18000ed18`
- name: `RouterAesKeyWrap`
- size: `1032`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180009ba0`

## callees

- `0x1800041d0`
- `0x180004200`
- `0x180005060`
- `0x180007a7c`
- `0x18000e910`
- `0x180015db4`
- `0x18001b79d`
- `0x18001b7e0`
- `0x18001c010`

## string_xrefs

- `0x18000e9e2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x18000ea65`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x18000eae2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x18000eb28`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x18000ec30`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`

## pseudocode

```c
__int64 __fastcall RouterAesKeyWrap(__int64 a1, __int64 a2, void *a3, unsigned int a4, unsigned int *a5)
{
  __int64 v5; // rax
  __int64 v7; // r10
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, const wchar_t *, unsigned int *, __int64, int *, _DWORD); // r14
  __int64 v10; // rax
  __int64 (__fastcall *v11)(__int64, unsigned __int64 *, __int64, _QWORD, __int128 *, int, unsigned __int64 *, int, int *, _DWORD); // r8
  __int64 (__fastcall *v12)(__int64, const wchar_t *, int *, __int64, int *, _DWORD); // rax
  __int64 v13; // r13
  int v14; // edx
  int v15; // ebx
  __int64 v16; // r12
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // r8
  unsigned int v20; // r14d
  unsigned int v21; // edi
  __int64 v22; // r15
  char *p_Src; // rdi
  __int64 v24; // rax
  int KeyDataBlob; // eax
  unsigned int v26; // r12d
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rax
  unsigned int v29; // r14d
  unsigned int i; // ecx
  int v31; // eax
  size_t v32; // r8
  void *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int128 *v36; // rax
  unsigned __int64 *v37; // rax
  size_t *p_Size; // rax
  unsigned int v40; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+64h] [rbp-9Ch] BYREF
  int v42; // [rsp+68h] [rbp-98h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h]
  void *v44; // [rsp+78h] [rbp-88h]
  __int64 v45; // [rsp+80h] [rbp-80h]
  __int64 (__fastcall *v46)(__int64, unsigned __int64 *, __int64, _QWORD, __int128 *, int, unsigned __int64 *, int, int *, _DWORD); // [rsp+88h] [rbp-78h]
  unsigned __int64 v47; // [rsp+90h] [rbp-70h]
  __int64 v48; // [rsp+98h] [rbp-68h]
  __int64 v49; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v50; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-50h]
  size_t Size; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v53; // [rsp+C0h] [rbp-40h] BYREF
  char Src; // [rsp+D0h] [rbp-30h] BYREF

  v5 = *(_QWORD *)(a1 + 8);
  v7 = *(_QWORD *)(a2 + 16);
  v8 = *(_QWORD *)(a1 + 16);
  v42 = 0;
  v40 = 0;
  v41 = 0;
  v9 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, __int64, int *, _DWORD))(v5 + 64);
  v10 = *(_QWORD *)(a2 + 8);
  v44 = a3;
  v43 = a1;
  v11 = *(__int64 (__fastcall **)(__int64, unsigned __int64 *, __int64, _QWORD, __int128 *, int, unsigned __int64 *, int, int *, _DWORD))(v10 + 96);
  v12 = *(__int64 (__fastcall **)(__int64, const wchar_t *, int *, __int64, int *, _DWORD))(v10 + 64);
  v46 = v11;
  v45 = v7;
  v13 = 8;
  v15 = v12(v7, L"BlockLength", &v42, 4, &v41, 0);
  v16 = 16;
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c",
        (unsigned int)"Status",
        v15,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c",
        186);
    goto LABEL_48;
  }
  if ( v41 != 4 || v42 != 16 )
  {
    v15 = -1073741816;
    v18 = 3221225480LL;
    goto LABEL_9;
  }
  v17 = v9(v8, L"KeyLength", &v40, 4, &v41, 0);
  v15 = v17;
  if ( v17 < 0 )
  {
    v18 = (unsigned int)v17;
LABEL_9:
    DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c");
LABEL_48:
    *a5 = 0;
    goto LABEL_40;
  }
  v19 = v40 >> 3;
  v20 = v40 >> 3;
  v40 >>= 3;
  if ( v41 != 4 || (v20 & 7) != 0 )
  {
    v15 = -1073741816;
    goto LABEL_48;
  }
  v21 = v19 + 8;
  if ( !v44 )
  {
    v15 = 0;
LABEL_20:
    *a5 = v21;
    goto LABEL_40;
  }
  if ( a4 < v21 )
  {
    v15 = -1073741789;
    goto LABEL_20;
  }
  Size = v21;
  if ( v21 > 0x48 )
  {
    v24 = SafeAllocaAllocateFromHeap(v21);
    v22 = v24;
    if ( !v24 )
    {
      v15 = -1073741801;
      DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c");
      goto LABEL_20;
    }
    v19 = v40;
    p_Src = (char *)v24;
  }
  else
  {
    v22 = 0;
    p_Src = &Src;
  }
  KeyDataBlob = RouterGetKeyDataBlob(v43, p_Src + 8, v19);
  v15 = KeyDataBlob;
  if ( KeyDataBlob >= 0 )
  {
    v26 = v20;
    v27 = (unsigned __int64)v40 >> 3;
    v28 = 0xA6A6A6A6A6A6A6A6uLL;
    v47 = v27;
    v29 = 0;
LABEL_25:
    if ( v29 >= 6 )
    {
      v32 = Size;
      v33 = v44;
      *(_QWORD *)p_Src = v28;
      memcpy_0(v33, p_Src, v32);
      v15 = 0;
    }
    else
    {
      for ( i = 0; ; i = v43 + 1 )
      {
        LODWORD(v43) = i;
        v48 = i;
        if ( i >= v27 )
        {
          ++v29;
          goto LABEL_25;
        }
        v50 = v28;
        v49 = 8 * i;
        v51 = *(_QWORD *)&p_Src[v49 + 8];
        v53 = 0;
        v31 = v46(v45, &v50, 16, 0, &v53, 16, &v50, 16, &v41, 0);
        v15 = v31;
        if ( v31 < 0 )
          break;
        v27 = v47;
        v28 = v50 ^ _byteswap_uint64(v48 + 1 + v47 * v29);
        *(_QWORD *)&p_Src[v49 + 8] = v51;
      }
      DebugTraceError(
        (unsigned int)v31,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c");
    }
    v20 = v26;
  }
  else
  {
    DebugTraceError(
      (unsigned int)KeyDataBlob,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c");
    v26 = v20;
  }
  *a5 = v20 + 8;
  if ( p_Src )
  {
    v34 = v26 + 8;
    if ( v26 != -8 )
    {
      do
      {
        *p_Src++ = 0;
        --v34;
      }
      while ( v34 );
    }
  }
  if ( v22 )
    BCryptFree(v22);
  v16 = 16;
LABEL_40:
  v35 = 16;
  v36 = &v53;
  do
  {
    *(_BYTE *)v36 = 0;
    v36 = (__int128 *)((char *)v36 + 1);
    --v35;
  }
  while ( v35 );
  v37 = &v50;
  do
  {
    *(_BYTE *)v37 = 0;
    v37 = (unsigned __int64 *)((char *)v37 + 1);
    --v16;
  }
  while ( v16 );
  p_Size = &Size;
  do
  {
    *(_BYTE *)p_Size = 0;
    p_Size = (size_t *)((char *)p_Size + 1);
    --v13;
  }
  while ( v13 );
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000e910  mov     [rsp-8+arg_18], rbx
0x18000e915  push    rbp
0x18000e916  push    rsi
0x18000e917  push    rdi
0x18000e918  push    r12
0x18000e91a  push    r13
0x18000e91c  push    r14
0x18000e91e  push    r15
0x18000e920  lea     rbp, [rsp-30h]
0x18000e925  sub     rsp, 130h
0x18000e92c  mov     rax, cs:__security_cookie
0x18000e933  xor     rax, rsp
0x18000e936  mov     [rbp+60h+var_40], rax
0x18000e93a  mov     rax, [rcx+8]
0x18000e93e  mov     r15d, r9d
0x18000e941  mov     r10, [rdx+10h]
0x18000e945  xor     r9d, r9d
0x18000e948  mov     rdi, [rcx+10h]
0x18000e94c  mov     rsi, [rbp+60h+arg_20]
0x18000e953  mov     [rsp+160h+var_F8], r9d
0x18000e958  mov     [rsp+160h+var_100], r9d
0x18000e95d  mov     [rsp+160h+var_FC], r9d
0x18000e962  mov     r14, [rax+40h]
0x18000e966  mov     rax, [rdx+8]
0x18000e96a  lea     rdx, aBlocklength; "BlockLength"
0x18000e971  mov     [rsp+160h+var_E8], r8
0x18000e976  mov     [rsp+160h+var_F0], rcx
0x18000e97b  lea     rcx, [rsp+160h+var_FC]
0x18000e980  mov     dword ptr [rsp+160h+var_138], r9d
0x18000e985  mov     r9d, 4
0x18000e98b  mov     r8, [rax+60h]
0x18000e98f  mov     rax, [rax+40h]
0x18000e993  mov     [rbp+60h+var_D8], r8
0x18000e997  lea     r8, [rsp+160h+var_F8]
0x18000e99c  mov     [rsp+160h+var_140], rcx
0x18000e9a1  mov     rcx, r10
0x18000e9a4  mov     [rbp+60h+var_E0], r10
0x18000e9a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9ad  mov     r13d, 8
0x18000e9b3  mov     ebx, eax
0x18000e9b5  lea     r12d, [r13+8]
0x18000e9b9  test    eax, eax
0x18000e9bb  jns     short loc_18000EA0B
0x18000e9bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9c4  lea     rax, WPP_GLOBAL_Control
0x18000e9cb  cmp     rcx, rax
0x18000e9ce  jz      loc_18000ECFB
0x18000e9d4  test    byte ptr [rcx+1Ch], 1
0x18000e9d8  jz      loc_18000ECFB
0x18000e9de  mov     rcx, [rcx+10h]
0x18000e9e2  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e9e9  mov     dword ptr [rsp+160h+var_130], 0BAh
0x18000e9f1  lea     r9, aStatus; "Status"
0x18000e9f8  mov     [rsp+160h+var_138], r8
0x18000e9fd  mov     dword ptr [rsp+160h+var_140], ebx
0x18000ea01  call    WPP_SF_sDsd
0x18000ea06  jmp     loc_18000ECFB
0x18000ea0b  cmp     [rsp+160h+var_FC], 4
0x18000ea10  jnz     loc_18000ED03
0x18000ea16  cmp     [rsp+160h+var_F8], r12d
0x18000ea1b  jnz     loc_18000ED03
0x18000ea21  lea     rax, [rsp+160h+var_FC]
0x18000ea26  mov     dword ptr [rsp+160h+var_138], 0
0x18000ea2e  mov     [rsp+160h+var_140], rax
0x18000ea33  lea     r8, [rsp+160h+var_100]
0x18000ea38  mov     rax, r14
0x18000ea3b  lea     rdx, aKeylength; "KeyLength"
0x18000ea42  mov     r9d, 4
0x18000ea48  mov     rcx, rdi
0x18000ea4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea50  mov     ebx, eax
0x18000ea52  test    eax, eax
0x18000ea54  jns     short loc_18000EA76
0x18000ea56  mov     r9d, 0D0h
0x18000ea5c  mov     ecx, eax
0x18000ea5e  lea     rdx, aStatus; "Status"
0x18000ea65  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ea6c  call    DebugTraceError
0x18000ea71  jmp     loc_18000ECFB
0x18000ea76  mov     r8d, [rsp+160h+var_100]
0x18000ea7b  shr     r8d, 3
0x18000ea7f  cmp     [rsp+160h+var_FC], 4
0x18000ea84  mov     r14d, r8d
0x18000ea87  mov     [rsp+160h+var_100], r8d
0x18000ea8c  jnz     loc_18000ECF6
0x18000ea92  test    r14b, 7
0x18000ea96  jnz     loc_18000ECF6
0x18000ea9c  cmp     [rsp+160h+var_E8], 0
0x18000eaa2  lea     edi, [r8+8]
0x18000eaa6  jnz     short loc_18000EAAC
0x18000eaa8  xor     ebx, ebx
0x18000eaaa  jmp     short loc_18000EAFF
0x18000eaac  cmp     r15d, edi
0x18000eaaf  jnb     short loc_18000EAB8
0x18000eab1  mov     ebx, 0C0000023h
0x18000eab6  jmp     short loc_18000EAFF
0x18000eab8  mov     eax, edi
0x18000eaba  mov     [rbp+60h+Size], rax
0x18000eabe  cmp     edi, 48h ; 'H'
0x18000eac1  ja      short loc_18000EACC
0x18000eac3  xor     r15d, r15d
0x18000eac6  lea     rdi, [rbp+60h+Src]
0x18000eaca  jmp     short loc_18000EB0E
0x18000eacc  mov     rcx, rax
0x18000eacf  call    SafeAllocaAllocateFromHeap
0x18000ead4  mov     r15, rax
0x18000ead7  test    rax, rax
0x18000eada  jnz     short loc_18000EB06
0x18000eadc  mov     r9d, 100h
0x18000eae2  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000eae9  lea     rdx, aStatus; "Status"
0x18000eaf0  mov     ecx, 0C0000017h
0x18000eaf5  mov     ebx, 0C0000017h
0x18000eafa  call    DebugTraceError
0x18000eaff  mov     [rsi], edi
0x18000eb01  jmp     loc_18000EC99
0x18000eb06  mov     r8d, [rsp+160h+var_100]
0x18000eb0b  mov     rdi, rax
0x18000eb0e  mov     rcx, [rsp+160h+var_F0]
0x18000eb13  lea     rdx, [rdi+8]
0x18000eb17  call    RouterGetKeyDataBlob
0x18000eb1c  mov     ebx, eax
0x18000eb1e  test    eax, eax
0x18000eb20  jns     short loc_18000EB45
0x18000eb22  mov     r9d, 112h
0x18000eb28  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000eb2f  lea     rdx, aStatus; "Status"
0x18000eb36  mov     ecx, eax
0x18000eb38  call    DebugTraceError
0x18000eb3d  mov     r12d, r14d
0x18000eb40  jmp     loc_18000EC60
0x18000eb45  mov     edx, [rsp+160h+var_100]
0x18000eb49  mov     r12d, r14d
0x18000eb4c  shr     rdx, 3
0x18000eb50  mov     rax, 0A6A6A6A6A6A6A6A6h
0x18000eb5a  mov     [rbp+60h+var_D0], rdx
0x18000eb5e  xor     r14d, r14d
0x18000eb61  cmp     r14d, 6
0x18000eb65  jnb     loc_18000EC47
0x18000eb6b  xor     ecx, ecx
0x18000eb6d  mov     r8d, ecx
0x18000eb70  mov     dword ptr [rsp+160h+var_F0], ecx
0x18000eb74  mov     [rbp+60h+var_C8], r8
0x18000eb78  cmp     r8, rdx
0x18000eb7b  jnb     loc_18000EC22
0x18000eb81  mov     [rbp+60h+var_B8], rax
0x18000eb85  lea     rdx, [rbp+60h+var_B8]
0x18000eb89  lea     eax, ds:0[rcx*8]
0x18000eb90  mov     [rsp+160h+var_118], 0
0x18000eb98  mov     [rbp+60h+var_C0], rax
0x18000eb9c  lea     rcx, [rbp+60h+var_B8]
0x18000eba0  mov     rax, [rax+rdi+8]
0x18000eba5  xorps   xmm0, xmm0
0x18000eba8  mov     [rbp+60h+var_B0], rax
0x18000ebac  xor     r9d, r9d
0x18000ebaf  lea     rax, [rsp+160h+var_FC]
0x18000ebb4  mov     [rsp+160h+var_120], rax
0x18000ebb9  mov     eax, 10h
0x18000ebbe  mov     [rsp+160h+var_128], eax
0x18000ebc2  mov     r8d, eax
0x18000ebc5  mov     [rsp+160h+var_130], rcx
0x18000ebca  lea     rcx, [rbp+60h+var_A0]
0x18000ebce  mov     dword ptr [rsp+160h+var_138], eax
0x18000ebd2  mov     rax, [rbp+60h+var_D8]
0x18000ebd6  mov     [rsp+160h+var_140], rcx
0x18000ebdb  mov     rcx, [rbp+60h+var_E0]
0x18000ebdf  movups  [rbp+60h+var_A0], xmm0
0x18000ebe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebe8  mov     ebx, eax
0x18000ebea  test    eax, eax
0x18000ebec  js      short loc_18000EC2A
0x18000ebee  mov     rdx, [rbp+60h+var_D0]
0x18000ebf2  mov     rcx, [rbp+60h+var_C8]
0x18000ebf6  mov     r8, [rbp+60h+var_C0]
0x18000ebfa  inc     rcx
0x18000ebfd  mov     eax, r14d
0x18000ec00  imul    rax, rdx
0x18000ec04  add     rax, rcx
0x18000ec07  mov     rcx, [rbp+60h+var_B0]
0x18000ec0b  bswap   rax
0x18000ec0e  xor     rax, [rbp+60h+var_B8]
0x18000ec12  mov     [r8+rdi+8], rcx
0x18000ec17  mov     ecx, dword ptr [rsp+160h+var_F0]
0x18000ec1b  inc     ecx
0x18000ec1d  jmp     loc_18000EB6D
0x18000ec22  inc     r14d
0x18000ec25  jmp     loc_18000EB61
0x18000ec2a  mov     r9d, 135h
0x18000ec30  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ec37  lea     rdx, aStatus; "Status"
0x18000ec3e  mov     ecx, eax
0x18000ec40  call    DebugTraceError
0x18000ec45  jmp     short loc_18000EC5D
0x18000ec47  mov     r8, [rbp+60h+Size]; Size
0x18000ec4b  mov     rdx, rdi; Src
0x18000ec4e  mov     rcx, [rsp+160h+var_E8]; void *
0x18000ec53  mov     [rdi], rax
0x18000ec56  call    memcpy_0
0x18000ec5b  xor     ebx, ebx
0x18000ec5d  mov     r14d, r12d
0x18000ec60  mov     eax, r13d
0x18000ec63  mov     ecx, r13d
0x18000ec66  add     eax, r14d
0x18000ec69  mov     [rsi], eax
0x18000ec6b  test    rdi, rdi
0x18000ec6e  jz      short loc_18000EC86
0x18000ec70  lea     eax, [r12+rcx]
0x18000ec74  mov     ecx, eax
0x18000ec76  test    eax, eax
0x18000ec78  jz      short loc_18000EC86
0x18000ec7a  mov     byte ptr [rdi], 0
0x18000ec7d  inc     rdi
0x18000ec80  sub     rcx, 1
0x18000ec84  jnz     short loc_18000EC7A
0x18000ec86  test    r15, r15
0x18000ec89  jz      short loc_18000EC93
0x18000ec8b  mov     rcx, r15
0x18000ec8e  call    BCryptFree
0x18000ec93  mov     r12d, 10h
0x18000ec99  mov     rcx, r12
0x18000ec9c  lea     rax, [rbp+60h+var_A0]
0x18000eca0  mov     byte ptr [rax], 0
0x18000eca3  inc     rax
0x18000eca6  sub     rcx, 1
0x18000ecaa  jnz     short loc_18000ECA0
0x18000ecac  lea     rax, [rbp+60h+var_B8]
0x18000ecb0  mov     byte ptr [rax], 0
0x18000ecb3  inc     rax
0x18000ecb6  sub     r12, 1
0x18000ecba  jnz     short loc_18000ECB0
0x18000ecbc  lea     rax, [rbp+60h+Size]
0x18000ecc0  mov     byte ptr [rax], 0
0x18000ecc3  inc     rax
0x18000ecc6  sub     r13, 1
0x18000ecca  jnz     short loc_18000ECC0
0x18000eccc  mov     eax, ebx
0x18000ecce  mov     rcx, [rbp+60h+var_40]
0x18000ecd2  xor     rcx, rsp; StackCookie
0x18000ecd5  call    __security_check_cookie
0x18000ecda  mov     rbx, [rsp+160h+arg_18]
0x18000ece2  add     rsp, 130h
0x18000ece9  pop     r15
0x18000eceb  pop     r14
0x18000eced  pop     r13
0x18000ecef  pop     r12
0x18000ecf1  pop     rdi
0x18000ecf2  pop     rsi
0x18000ecf3  pop     rbp
0x18000ecf4  retn
0x18000ecf6  mov     ebx, 0C0000008h
0x18000ecfb  mov     dword ptr [rsi], 0
0x18000ed01  jmp     short loc_18000EC99
0x18000ed03  mov     ebx, 0C0000008h
0x18000ed08  mov     r9d, 0C2h
0x18000ed0e  mov     ecx, 0C0000008h
0x18000ed13  jmp     loc_18000EA5E
```
