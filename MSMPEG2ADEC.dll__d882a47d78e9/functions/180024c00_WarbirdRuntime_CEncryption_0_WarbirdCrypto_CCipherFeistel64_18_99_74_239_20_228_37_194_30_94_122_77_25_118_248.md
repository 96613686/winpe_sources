# WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::Encrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar *)

- ea: `0x180024c00`
- end: `0x180024fc1`
- name: `?Encrypt@?$CEncryption@$0A@V?$CCipherFeistel64@$0BC@$0GD@$0EK@$0OP@$0BE@$0OE@$0CF@$0MC@$0BO@$0FO@$0HK@$0EN@$0BJ@$0HG@$0PI@$0OK@$0BG@$0PH@$0CF@$0JN@$00$03$0N@$0BE@$07$0HP@$07$0NI@$0L@$0BN@$0FB@$0EK@$09$0OH@$0HF@$0BM@$01$0NF@$0ND@$0FG@@WarbirdCrypto@@V?$CHashFunctionSCP@$01$02$0A@$0?BMINLIEJLPHNNHJC@@2@UENCRYPTED_SEGMENT_DATA_CONST_1@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@K1@Z`
- size: `961`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800236a0`

## callees

- `0x1800017b0`
- `0x180024c00`

## pseudocode

```c
void __fastcall WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::Encrypt(
        char *a1,
        unsigned __int64 *a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        unsigned int a5,
        _BYTE *a6)
{
  int v8; // edi
  int v9; // ebx
  __int64 v10; // rsi
  _QWORD *v11; // rax
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // r15
  unsigned __int64 *v14; // r10
  unsigned __int64 v15; // r12
  int v16; // edx
  int v17; // r8d
  unsigned int v18; // ecx
  unsigned int v19; // edx
  int v20; // r8d
  int v21; // ecx
  int v22; // edx
  int v23; // r8d
  __int16 v24; // r11
  int v25; // ebx
  int v26; // edi
  _BYTE *v27; // r8
  __int64 v28; // rcx
  char *v29; // rdx
  char v30; // al
  char *v31; // rdx
  __int64 v32; // rcx
  unsigned __int64 *v33; // r8
  unsigned __int64 *v34; // r9
  __int64 v35; // rdx
  char v36; // cl
  unsigned __int64 v37; // rbp
  __int64 *v38; // rcx
  int v39; // r13d
  __int64 v40; // r11
  int v41; // r9d
  int v42; // edx
  int v43; // r8d
  int v44; // r9d
  unsigned int v45; // edx
  unsigned int v46; // r8d
  int v47; // r10d
  int v48; // r9d
  unsigned int v49; // edx
  int v50; // rdi^4
  unsigned __int64 *v51; // rdx
  unsigned __int64 v52; // [rsp+0h] [rbp-68h] BYREF
  int v53; // [rsp+8h] [rbp-60h]
  _QWORD *v54; // [rsp+10h] [rbp-58h] BYREF
  unsigned __int64 *v55; // [rsp+18h] [rbp-50h]
  unsigned __int64 v56; // [rsp+20h] [rbp-48h]

  if ( a3 )
  {
    v8 = a5;
    v9 = ~a5;
    *a6 = a1[a3 - 1];
    v55 = a2;
    v10 = a3 & 7;
    if ( (a3 & 7) != 0 )
    {
      v12 = HIDWORD(a4);
      v15 = HIWORD(a4);
      v13 = a4 >> 16;
      v53 = a4;
      v16 = v9 ^ (a5 >> 2) ^ (WORD1(a4) * (a5 ^ WORD2(a4)));
      LODWORD(v52) = (unsigned __int16)a4;
      v17 = a5 ^ ((unsigned __int16)a4 * __ROL4__(WORD1(a4) ^ v16, 6) - __ROR4__(v16, 29));
      v18 = v16 ^ __ROR4__(v17, 13) ^ (HIWORD(a4) * __ROL4__(WORD2(a4) ^ v17, 5));
      v19 = v17 ^ (v18 >> 7) ^ (WORD2(a4) * __ROL4__(v18 - (unsigned __int16)a4, 2));
      v20 = v18 ^ (WORD1(a4) * (v19 - HIWORD(a4)) - (v19 >> 14));
      v21 = v19 ^ ((unsigned __int16)a4 * __ROR4__(v20 - HIDWORD(a4), 7) - __ROR4__(v20, 3));
      v22 = v20 ^ (WORD2(a4) * (__ROR4__(v21, 14) - HIWORD(a4)));
      v23 = v21 ^ (v22 - a4 - WORD2(a4));
      v24 = a4;
      v25 = v22 ^ __ROR4__(v23, 9) ^ (WORD1(a4) * __ROR4__(HIDWORD(a4) ^ v23, 7));
      v26 = v23 ^ __ROR4__(v25, 23) ^ ((unsigned __int16)a4 * __ROR4__(v25 - HIDWORD(a4), 13));
      v56 = 0;
      v27 = &v54;
      v54 = 0;
      v28 = v10;
      v29 = a1;
      do
      {
        v30 = *v29++;
        *v27++ = v30;
        --v28;
      }
      while ( v28 );
      v8 = HIDWORD(v54) ^ v26;
      v11 = v54;
      v31 = (char *)&v52 + v10;
      v9 = (unsigned int)v54 ^ v25;
      v52 = __PAIR64__(v8, v9);
      v32 = 8 - v10;
      if ( v10 != 8 )
      {
        do
        {
          *v31++ = 0;
          --v32;
        }
        while ( v32 );
        v8 = HIDWORD(v52);
        v9 = v52;
      }
      v14 = v55;
      v33 = &v52;
      v34 = v55;
      v35 = v10;
      do
      {
        v36 = *(_BYTE *)v33;
        v33 = (unsigned __int64 *)((char *)v33 + 1);
        *(_BYTE *)v34 = v36;
        v34 = (unsigned __int64 *)((char *)v34 + 1);
        --v35;
      }
      while ( v35 );
      LOWORD(a4) = v24;
    }
    else
    {
      v11 = 0;
      v12 = HIDWORD(a4);
      v13 = a4 >> 16;
      v14 = a2;
      v56 = 0;
      v15 = HIWORD(a4);
      v53 = a4;
    }
    v37 = a3 >> 3;
    v55 = (unsigned __int64 *)((char *)v14 + v10);
    v38 = (__int64 *)&a1[v10];
    if ( v37 )
    {
      v39 = (unsigned __int16)a4;
      do
      {
        v40 = *v38;
        v54 = v38 + 1;
        v41 = v8 ^ HIDWORD(v40) ^ __ROR4__(v9 ^ v40, 23) ^ (v39 * __ROR4__((v9 ^ v40) - v12, 13));
        v42 = v9 ^ v40 ^ __ROR4__(v41, 9) ^ ((unsigned __int16)v13 * __ROR4__(v12 ^ v41, 7));
        v43 = v41 ^ (v42 - (unsigned __int16)v12 - v53);
        v44 = v42 ^ ((unsigned __int16)v12 * (__ROR4__(v43, 14) - v15));
        v45 = v43 ^ (v39 * __ROR4__(v44 - v12, 7) - __ROR4__(v44, 3));
        v46 = v44 ^ ((unsigned __int16)v13 * (v45 - v15) - (v45 >> 14));
        v47 = v45 ^ (v46 >> 7) ^ ((unsigned __int16)v12 * __ROL4__(v46 - v39, 2));
        v48 = v46 ^ __ROR4__(v47, 13) ^ (v15 * __ROL4__((unsigned __int16)v12 ^ v47, 5));
        v49 = v47 ^ (v39 * __ROL4__((unsigned __int16)v13 ^ v48, 6) - __ROR4__(v48, 29));
        v9 = (unsigned int)v11 ^ v48 ^ (v49 >> 2) ^ ((unsigned __int16)v13 * ((unsigned __int16)v12 ^ v49));
        LODWORD(v52) = v9;
        v50 = HIDWORD(v11);
        v11 = (_QWORD *)v40;
        v8 = v49 ^ v50;
        v51 = v55;
        HIDWORD(v52) = v8;
        *v55 = v52;
        v55 = v51 + 1;
        ++v56;
        v38 = v54;
      }
      while ( v56 < v37 );
    }
  }
}

```

## disassembly

```asm
0x180024c00  test    r8, r8
0x180024c03  jz      locret_180024FBF
0x180024c09  push    rbp
0x180024c0a  push    r13
0x180024c0c  sub     rsp, 58h
0x180024c10  mov     rax, cs:__security_cookie
0x180024c17  xor     rax, rsp
0x180024c1a  mov     [rsp+68h+var_40], rax
0x180024c1f  mov     [rsp+68h+arg_0], rbx
0x180024c24  mov     r13, rcx
0x180024c27  mov     rcx, [rsp+68h+arg_28]
0x180024c2f  mov     rbp, r8
0x180024c32  mov     [rsp+68h+var_18], rsi
0x180024c37  mov     rsi, r8
0x180024c3a  mov     [rsp+68h+var_20], rdi
0x180024c3f  mov     edi, [rsp+68h+arg_20]
0x180024c46  mov     ebx, edi
0x180024c48  movzx   eax, byte ptr [r13+r8-1]
0x180024c4e  not     ebx
0x180024c50  mov     [rsp+68h+var_28], r12
0x180024c55  mov     r12, r9
0x180024c58  mov     [rsp+68h+var_30], r14
0x180024c5d  mov     r14, r9
0x180024c60  mov     [rsp+68h+var_38], r15
0x180024c65  mov     r15, r9
0x180024c68  mov     [rcx], al
0x180024c6a  mov     [rsp+68h+var_50], rdx
0x180024c6f  and     esi, 7
0x180024c72  jnz     short loc_180024C94
0x180024c74  xor     eax, eax
0x180024c76  shr     r14, 20h
0x180024c7a  shr     r15, 10h
0x180024c7e  mov     r10, rdx
0x180024c81  mov     [rsp+68h+var_48], rax
0x180024c86  shr     r12, 30h
0x180024c8a  mov     [rsp+68h+var_60], r9d
0x180024c8f  jmp     loc_180024E29
0x180024c94  mov     eax, edi
0x180024c96  shr     r14, 20h
0x180024c9a  shr     eax, 2
0x180024c9d  movzx   r10d, r14w
0x180024ca1  shr     r12, 30h
0x180024ca5  mov     edx, r10d
0x180024ca8  xor     edx, edi
0x180024caa  shr     r15, 10h
0x180024cae  movzx   r11d, r15w
0x180024cb2  imul    edx, r11d
0x180024cb6  mov     [rsp+68h+var_60], r9d
0x180024cbb  xor     edx, eax
0x180024cbd  xor     edx, ebx
0x180024cbf  movzx   ebx, r9w
0x180024cc3  mov     eax, edx
0x180024cc5  mov     dword ptr [rsp+68h+var_68], ebx
0x180024cc8  ror     eax, 1Dh
0x180024ccb  mov     r8d, edx
0x180024cce  xor     r8d, r11d
0x180024cd1  rol     r8d, 6
0x180024cd5  imul    r8d, ebx
0x180024cd9  sub     r8d, eax
0x180024cdc  xor     r8d, edi
0x180024cdf  mov     eax, r8d
0x180024ce2  mov     ecx, r8d
0x180024ce5  ror     eax, 0Dh
0x180024ce8  xor     ecx, r10d
0x180024ceb  rol     ecx, 5
0x180024cee  imul    ecx, r12d
0x180024cf2  xor     ecx, eax
0x180024cf4  xor     ecx, edx
0x180024cf6  mov     eax, ecx
0x180024cf8  mov     edx, ecx
0x180024cfa  sub     edx, ebx
0x180024cfc  shr     eax, 7
0x180024cff  rol     edx, 2
0x180024d02  imul    edx, r10d
0x180024d06  xor     edx, eax
0x180024d08  xor     edx, r8d
0x180024d0b  mov     eax, edx
0x180024d0d  mov     r8d, edx
0x180024d10  sub     r8d, r12d
0x180024d13  shr     eax, 0Eh
0x180024d16  imul    r8d, r11d
0x180024d1a  sub     r8d, eax
0x180024d1d  xor     r8d, ecx
0x180024d20  mov     eax, r8d
0x180024d23  mov     ecx, r8d
0x180024d26  ror     eax, 3
0x180024d29  sub     ecx, r14d
0x180024d2c  ror     ecx, 7
0x180024d2f  imul    ecx, ebx
0x180024d32  sub     ecx, eax
0x180024d34  xor     ecx, edx
0x180024d36  mov     edx, ecx
0x180024d38  ror     edx, 0Eh
0x180024d3b  sub     edx, r12d
0x180024d3e  imul    edx, r10d
0x180024d42  xor     edx, r8d
0x180024d45  mov     r8d, edx
0x180024d48  sub     r8d, r9d
0x180024d4b  sub     r8d, r10d
0x180024d4e  xor     r8d, ecx
0x180024d51  mov     eax, r8d
0x180024d54  mov     ebx, r8d
0x180024d57  xor     ebx, r14d
0x180024d5a  ror     eax, 9
0x180024d5d  ror     ebx, 7
0x180024d60  imul    ebx, r11d
0x180024d64  mov     r11d, dword ptr [rsp+68h+var_68]
0x180024d68  xor     ebx, eax
0x180024d6a  xor     ebx, edx
0x180024d6c  mov     eax, ebx
0x180024d6e  mov     edi, ebx
0x180024d70  sub     edi, r14d
0x180024d73  ror     eax, 17h
0x180024d76  ror     edi, 0Dh
0x180024d79  imul    edi, r11d
0x180024d7d  xor     edi, eax
0x180024d7f  xor     edi, r8d
0x180024d82  xor     eax, eax
0x180024d84  mov     [rsp+68h+var_48], rax
0x180024d89  lea     r8, [rsp+68h+var_58]
0x180024d8e  mov     [rsp+68h+var_58], rax
0x180024d93  mov     rcx, rsi
0x180024d96  mov     rdx, r13
0x180024d99  nop     dword ptr [rax+00000000h]
0x180024da0  movzx   eax, byte ptr [rdx]
0x180024da3  lea     rdx, [rdx+1]
0x180024da7  mov     [r8], al
0x180024daa  lea     r8, [r8+1]
0x180024dae  sub     rcx, 1
0x180024db2  jnz     short loc_180024DA0
0x180024db4  xor     edi, dword ptr [rsp+68h+var_58+4]
0x180024db8  lea     rdx, [rsp+68h+var_68]
0x180024dbc  mov     rax, [rsp+68h+var_58]
0x180024dc1  lea     rdx, [rdx+rsi]
0x180024dc5  xor     ebx, eax
0x180024dc7  mov     dword ptr [rsp+68h+var_68+4], edi
0x180024dcb  mov     ecx, 8
0x180024dd0  mov     dword ptr [rsp+68h+var_68], ebx
0x180024dd3  sub     rcx, rsi
0x180024dd6  jz      short loc_180024DF4
0x180024dd8  nop     dword ptr [rax+rax+00000000h]
0x180024de0  mov     byte ptr [rdx], 0
0x180024de3  lea     rdx, [rdx+1]
0x180024de7  sub     rcx, 1
0x180024deb  jnz     short loc_180024DE0
0x180024ded  mov     edi, dword ptr [rsp+68h+var_68+4]
0x180024df1  mov     ebx, dword ptr [rsp+68h+var_68]
0x180024df4  mov     r10, [rsp+68h+var_50]
0x180024df9  lea     r8, [rsp+68h+var_68]
0x180024dfd  mov     r9, r10
0x180024e00  mov     rdx, rsi
0x180024e03  nop     dword ptr [rax+00h]
0x180024e07  nop     word ptr [rax+rax+00000000h]
0x180024e10  movzx   ecx, byte ptr [r8]
0x180024e14  lea     r8, [r8+1]
0x180024e18  mov     [r9], cl
0x180024e1b  lea     r9, [r9+1]
0x180024e1f  sub     rdx, 1
0x180024e23  jnz     short loc_180024E10
0x180024e25  movzx   r9d, r11w
0x180024e29  shr     rbp, 3
0x180024e2d  lea     rdx, [rsi+r10]
0x180024e31  mov     [rsp+68h+var_50], rdx
0x180024e36  lea     rcx, [rsi+r13]
0x180024e3a  test    rbp, rbp
0x180024e3d  jz      loc_180024F8D
0x180024e43  movzx   r13d, r9w
0x180024e47  movzx   r15d, r15w
0x180024e4b  movzx   esi, r14w
0x180024e4f  nop
0x180024e50  mov     r11, [rcx]
0x180024e53  add     rcx, 8
0x180024e57  mov     [rsp+68h+var_58], rcx
0x180024e5c  mov     r8d, r11d
0x180024e5f  xor     r8d, ebx
0x180024e62  mov     ecx, r8d
0x180024e65  mov     r9d, r8d
0x180024e68  ror     ecx, 17h
0x180024e6b  sub     r9d, r14d
0x180024e6e  ror     r9d, 0Dh
0x180024e72  imul    r9d, r13d
0x180024e76  xor     r9d, ecx
0x180024e79  mov     rcx, r11
0x180024e7c  shr     rcx, 20h
0x180024e80  xor     r9d, ecx
0x180024e83  xor     r9d, edi
0x180024e86  mov     edx, r9d
0x180024e89  mov     ecx, r9d
0x180024e8c  xor     edx, r14d
0x180024e8f  ror     ecx, 9
0x180024e92  ror     edx, 7
0x180024e95  imul    edx, r15d
0x180024e99  xor     edx, ecx
0x180024e9b  xor     edx, r8d
0x180024e9e  mov     r8d, edx
0x180024ea1  sub     r8d, esi
0x180024ea4  sub     r8d, [rsp+68h+var_60]
0x180024ea9  xor     r8d, r9d
0x180024eac  mov     r9d, r8d
0x180024eaf  ror     r9d, 0Eh
0x180024eb3  sub     r9d, r12d
0x180024eb6  imul    r9d, esi
0x180024eba  xor     r9d, edx
0x180024ebd  mov     edx, r9d
0x180024ec0  mov     ecx, r9d
0x180024ec3  ror     ecx, 3
0x180024ec6  sub     edx, r14d
0x180024ec9  ror     edx, 7
0x180024ecc  imul    edx, r13d
0x180024ed0  sub     edx, ecx
0x180024ed2  xor     edx, r8d
0x180024ed5  mov     r8d, edx
0x180024ed8  mov     ecx, edx
0x180024eda  shr     ecx, 0Eh
0x180024edd  sub     r8d, r12d
0x180024ee0  imul    r8d, r15d
0x180024ee4  sub     r8d, ecx
0x180024ee7  xor     r8d, r9d
0x180024eea  mov     r10d, r8d
0x180024eed  mov     ecx, r8d
0x180024ef0  shr     ecx, 7
0x180024ef3  sub     r10d, r13d
0x180024ef6  rol     r10d, 2
0x180024efa  imul    r10d, esi
0x180024efe  xor     r10d, ecx
0x180024f01  xor     r10d, edx
0x180024f04  mov     r9d, r10d
0x180024f07  mov     ecx, r10d
0x180024f0a  ror     ecx, 0Dh
0x180024f0d  xor     r9d, esi
0x180024f10  rol     r9d, 5
0x180024f14  imul    r9d, r12d
0x180024f18  xor     r9d, ecx
0x180024f1b  xor     r9d, r8d
0x180024f1e  mov     edx, r9d
0x180024f21  mov     ecx, r9d
0x180024f24  xor     edx, r15d
0x180024f27  ror     ecx, 1Dh
0x180024f2a  rol     edx, 6
0x180024f2d  imul    edx, r13d
0x180024f31  sub     edx, ecx
0x180024f33  xor     edx, r10d
0x180024f36  mov     ebx, edx
0x180024f38  mov     ecx, edx
0x180024f3a  xor     ebx, esi
0x180024f3c  shr     ecx, 2
0x180024f3f  imul    ebx, r15d
0x180024f43  xor     ebx, ecx
0x180024f45  xor     ebx, r9d
0x180024f48  xor     ebx, eax
0x180024f4a  mov     dword ptr [rsp+68h+var_68], ebx
0x180024f4d  mov     rdi, rax
0x180024f50  mov     rax, r11
0x180024f53  shr     rdi, 20h
0x180024f57  xor     edi, edx
0x180024f59  mov     rdx, [rsp+68h+var_50]
0x180024f5e  mov     dword ptr [rsp+68h+var_68+4], edi
0x180024f62  mov     rcx, [rsp+68h+var_68]
0x180024f66  mov     [rdx], rcx
0x180024f69  add     rdx, 8
0x180024f6d  mov     rcx, [rsp+68h+var_48]
0x180024f72  inc     rcx
0x180024f75  mov     [rsp+68h+var_50], rdx
0x180024f7a  mov     [rsp+68h+var_48], rcx
0x180024f7f  cmp     rcx, rbp
0x180024f82  mov     rcx, [rsp+68h+var_58]
0x180024f87  jb      loc_180024E50
0x180024f8d  mov     r14, [rsp+68h+var_30]
0x180024f92  mov     r12, [rsp+68h+var_28]
0x180024f97  mov     r15, [rsp+68h+var_38]
0x180024f9c  mov     rsi, [rsp+68h+var_18]
0x180024fa1  mov     rbx, [rsp+68h+arg_0]
0x180024fa6  mov     rdi, [rsp+68h+var_20]
0x180024fab  mov     rcx, [rsp+68h+var_40]
0x180024fb0  xor     rcx, rsp; StackCookie
0x180024fb3  call    __security_check_cookie
0x180024fb8  add     rsp, 58h
0x180024fbc  pop     r13
0x180024fbe  pop     rbp
0x180024fbf  retn
```
