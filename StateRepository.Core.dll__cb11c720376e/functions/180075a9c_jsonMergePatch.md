# jsonMergePatch

- ea: `0x180075a9c`
- end: `0x180075eea`
- name: `jsonMergePatch`
- size: `1102`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64 *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180075a9c`
- `0x180076530`

## callees

- `0x180072aa4`
- `0x1800737a4`
- `0x180075380`
- `0x180075a9c`
- `0x180078a58`
- `0x180099814`

## pseudocode

```c
__int64 __fastcall jsonMergePatch(__int64 a1, unsigned int a2, __int64 *a3, unsigned int a4)
{
  _BYTE *v4; // r15
  __int64 v7; // r14
  char v9; // al
  int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  int v13; // eax
  __int64 result; // rax
  int v15; // eax
  int v16; // eax
  __int64 v17; // r15
  unsigned int v18; // ebx
  int v19; // eax
  unsigned int v20; // r12d
  __int64 v21; // rax
  int v22; // eax
  unsigned int v23; // r13d
  unsigned int v24; // ebx
  char v25; // r13
  int v26; // eax
  unsigned int v27; // eax
  int v28; // eax
  BOOL v29; // edx
  BOOL v30; // r8d
  __int64 v31; // r13
  __int64 v32; // rcx
  char v33; // al
  __int64 v34; // rdx
  unsigned int v35; // r12d
  __int64 v36; // rdx
  int v37; // ebx
  int v38; // [rsp+30h] [rbp-39h] BYREF
  unsigned int v39; // [rsp+34h] [rbp-35h] BYREF
  int v40; // [rsp+38h] [rbp-31h]
  unsigned int v41; // [rsp+3Ch] [rbp-2Dh]
  unsigned int v42; // [rsp+40h] [rbp-29h] BYREF
  int v43; // [rsp+44h] [rbp-25h]
  int v44; // [rsp+48h] [rbp-21h]
  unsigned int v45; // [rsp+4Ch] [rbp-1Dh]
  int v46; // [rsp+50h] [rbp-19h]
  int v47; // [rsp+54h] [rbp-15h]
  unsigned int v48; // [rsp+58h] [rbp-11h]
  __int64 v49; // [rsp+60h] [rbp-9h]
  int v50; // [rsp+68h] [rbp-1h]
  int v51; // [rsp+6Ch] [rbp+3h]
  unsigned int Size; // [rsp+70h] [rbp+7h]
  unsigned int Size_4; // [rsp+74h] [rbp+Bh]
  unsigned int v54; // [rsp+78h] [rbp+Fh]
  __int64 v55; // [rsp+80h] [rbp+17h]
  unsigned int v56; // [rsp+E0h] [rbp+77h] BYREF
  unsigned int v57; // [rsp+E8h] [rbp+7Fh] BYREF

  v4 = (_BYTE *)(*a3 + a4);
  v7 = a2;
  v57 = 0;
  v9 = *v4 & 0xF;
  v38 = 0;
  v39 = 0;
  v56 = 0;
  v42 = 0;
  if ( v9 != 12 )
  {
    v10 = jsonbPayloadSize(a3, a4, &v57);
    v11 = v57;
    v57 = 0;
    v12 = v10 + v11;
    v13 = jsonbPayloadSize((__int64 *)a1, v7, &v57);
    jsonBlobEdit(a1, v7, v13 + v57, v4, v12);
    return *(_BYTE *)(a1 + 47) != 0 ? 3 : 0;
  }
  if ( (*(_BYTE *)(a2 + *(_QWORD *)a1) & 0xF) != 0xC )
  {
    v15 = jsonbPayloadSize((__int64 *)a1, a2, &v57);
    jsonBlobEdit(a1, v15 + v7, v57, 0, 0);
    *(_BYTE *)(*(_QWORD *)a1 + v7) = *(_BYTE *)(*(_QWORD *)a1 + v7) & 0xF0 | 0xC;
  }
  v16 = jsonbPayloadSize(a3, a4, &v57);
  if ( !v16 )
    return 2;
  v17 = v16 + a4;
  v18 = v17 + v57;
  Size_4 = v17 + v57;
  v19 = jsonbPayloadSize((__int64 *)a1, v7, &v57);
  if ( v19 )
  {
    v20 = v19 + v7;
    v45 = 0;
    v40 = 0;
    v46 = v19 + v7 + v57;
    v41 = 0;
    v44 = 0;
    v54 = v19 + v7;
    while ( (unsigned int)v17 < v18 )
    {
      v21 = *a3;
      v55 = (unsigned int)v17;
      LOBYTE(v57) = *(_BYTE *)(v21 + v17) & 0xF;
      if ( (unsigned __int8)(v57 - 7) > 3u )
        return 2;
      v22 = jsonbPayloadSize(a3, v17, &v56);
      v43 = v22;
      if ( !v22 )
        return 2;
      v23 = v17 + v22 + v56;
      LODWORD(v49) = v23;
      if ( v23 >= v18 )
        return 2;
      v51 = jsonbPayloadSize(a3, v23, &v42);
      if ( !v51 )
        return 2;
      v47 = v17;
      Size = v51 + v42;
      v17 = v51 + v42 + v23;
      if ( (unsigned int)v17 > v18 )
        return 2;
      v24 = *(_DWORD *)(a1 + 52) + v46;
      v50 = *(_DWORD *)(a1 + 52);
      while ( v20 < v24 )
      {
        v25 = *(_BYTE *)(v20 + *(_QWORD *)a1) & 0xF;
        if ( (unsigned __int8)(v25 - 7) > 3u )
          return 1;
        v26 = jsonbPayloadSize((__int64 *)a1, v20, (unsigned int *)&v38);
        v40 = v26;
        if ( !v26 )
          return 1;
        v27 = v20 + v38 + v26;
        v41 = v27;
        if ( v27 >= v24 )
          return 1;
        v28 = jsonbPayloadSize((__int64 *)a1, v27, &v39);
        v44 = v28;
        if ( !v28 )
          return 1;
        v48 = v41 + v39 + v28;
        if ( v48 > v24 )
          return 1;
        v45 = v20;
        v29 = v25 == 7 || v25 == 10;
        v30 = (_BYTE)v57 == 7 || (_BYTE)v57 == 10;
        if ( (unsigned int)jsonLabelCompare(
                             (const void *)(*a3 + (unsigned int)(v43 + v47)),
                             v56,
                             v30,
                             (const void *)(*(_QWORD *)a1 + v20 + v40),
                             v38,
                             v29) )
          break;
        v20 = v48;
      }
      v31 = (unsigned int)v49;
      v32 = *a3;
      v49 = v31;
      v33 = *(_BYTE *)(v31 + v32) & 0xF;
      if ( v20 >= v24 )
      {
        if ( v33 )
        {
          v35 = v43 + v56;
          if ( v33 == 12 )
          {
            jsonBlobEdit(a1, v24, 0, 0, v35 + 1);
            if ( *(_BYTE *)(a1 + 47) )
              return 3;
            memcpy_0((void *)(*(_QWORD *)a1 + v24), (const void *)(*a3 + v55), v35);
            v36 = v35 + v24;
            *(_BYTE *)(v36 + *(_QWORD *)a1) = 0;
            v37 = *(_DWORD *)(a1 + 52);
            *(_DWORD *)(a1 + 52) = 0;
            result = jsonMergePatch(a1, v36, a3, (unsigned int)v31);
            if ( (_DWORD)result )
              return result;
            *(_DWORD *)(a1 + 52) += v37;
          }
          else
          {
            jsonBlobEdit(a1, v24, 0, 0, v51 + v35 + v42);
            if ( *(_BYTE *)(a1 + 47) )
              return 3;
            memcpy_0((void *)(*(_QWORD *)a1 + v24), (const void *)(*a3 + v55), v35);
            memcpy_0((void *)(*(_QWORD *)a1 + v35 + v24), (const void *)(*a3 + v49), Size);
          }
        }
      }
      else if ( v33 )
      {
        v34 = v41;
        *(_DWORD *)(a1 + 52) = 0;
        result = jsonMergePatch(a1, v34, a3, (unsigned int)v31);
        if ( (_DWORD)result )
          return result;
        *(_DWORD *)(a1 + 52) += v50;
      }
      else
      {
        jsonBlobEdit(a1, v45, v40 + v38 + v44 + v39, 0, 0);
        if ( *(_BYTE *)(a1 + 47) )
          return 3;
      }
      v18 = Size_4;
      v20 = v54;
    }
    if ( *(_DWORD *)(a1 + 52) )
      jsonAfterEditSizeAdjust((_DWORD *)a1, (unsigned int)v7);
    return *(_BYTE *)(a1 + 47) != 0 ? 3 : 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180075a9c  mov     [rsp-8+arg_0], rbx
0x180075aa1  push    rbp
0x180075aa2  push    rsi
0x180075aa3  push    rdi
0x180075aa4  push    r12
0x180075aa6  push    r13
0x180075aa8  push    r14
0x180075aaa  push    r15
0x180075aac  lea     rbp, [rsp-27h]
0x180075ab1  sub     rsp, 90h
0x180075ab8  xor     r13d, r13d
0x180075abb  mov     r15d, r9d
0x180075abe  add     r15, [r8]
0x180075ac1  mov     r12b, 0Ch
0x180075ac4  mov     ebx, r9d
0x180075ac7  mov     rsi, r8
0x180075aca  mov     r14d, edx
0x180075acd  mov     rdi, rcx
0x180075ad0  mov     [rbp+57h+arg_18], r13d
0x180075ad4  mov     al, [r15]
0x180075ad7  and     al, 0Fh
0x180075ad9  mov     [rbp+57h+var_90], r13d
0x180075add  mov     [rbp+57h+var_8C], r13d
0x180075ae1  mov     [rbp+57h+arg_10], r13d
0x180075ae5  mov     [rbp+57h+var_80], r13d
0x180075ae9  cmp     al, r12b
0x180075aec  jz      short loc_180075B3C
0x180075aee  lea     r8, [rbp+57h+arg_18]
0x180075af2  mov     edx, ebx
0x180075af4  mov     rcx, rsi
0x180075af7  call    jsonbPayloadSize
0x180075afc  mov     ebx, [rbp+57h+arg_18]
0x180075aff  lea     r8, [rbp+57h+arg_18]
0x180075b03  mov     edx, r14d
0x180075b06  mov     [rbp+57h+arg_18], r13d
0x180075b0a  mov     rcx, rdi
0x180075b0d  add     ebx, eax
0x180075b0f  call    jsonbPayloadSize
0x180075b14  mov     r8d, [rbp+57h+arg_18]
0x180075b18  mov     r9, r15
0x180075b1b  add     r8d, eax
0x180075b1e  mov     [rsp+0C0h+var_A0], ebx
0x180075b22  mov     edx, r14d
0x180075b25  mov     rcx, rdi
0x180075b28  call    jsonBlobEdit
0x180075b2d  mov     al, [rdi+2Fh]
0x180075b30  neg     al
0x180075b32  sbb     eax, eax
0x180075b34  and     eax, 3
0x180075b37  jmp     loc_180075ECF
0x180075b3c  mov     rax, [rcx]
0x180075b3f  mov     cl, [r14+rax]
0x180075b43  and     cl, 0Fh
0x180075b46  cmp     cl, r12b
0x180075b49  jz      short loc_180075B82
0x180075b4b  lea     r8, [rbp+57h+arg_18]
0x180075b4f  mov     edx, r14d
0x180075b52  mov     rcx, rdi
0x180075b55  call    jsonbPayloadSize
0x180075b5a  mov     r8d, [rbp+57h+arg_18]
0x180075b5e  xor     r9d, r9d
0x180075b61  mov     rcx, rdi
0x180075b64  mov     [rsp+0C0h+var_A0], r13d
0x180075b69  lea     edx, [rax+r14]
0x180075b6d  call    jsonBlobEdit
0x180075b72  mov     rcx, [rdi]
0x180075b75  mov     al, [rcx+r14]
0x180075b79  and     al, 0FCh
0x180075b7b  or      al, r12b
0x180075b7e  mov     [rcx+r14], al
0x180075b82  lea     r8, [rbp+57h+arg_18]
0x180075b86  mov     edx, ebx
0x180075b88  mov     rcx, rsi
0x180075b8b  call    jsonbPayloadSize
0x180075b90  test    eax, eax
0x180075b92  jz      loc_180075ECA
0x180075b98  lea     r15d, [rax+rbx]
0x180075b9c  mov     edx, r14d
0x180075b9f  mov     ebx, [rbp+57h+arg_18]
0x180075ba2  lea     r8, [rbp+57h+arg_18]
0x180075ba6  add     ebx, r15d
0x180075ba9  mov     rcx, rdi
0x180075bac  mov     dword ptr [rbp+57h+Size+4], ebx
0x180075baf  call    jsonbPayloadSize
0x180075bb4  test    eax, eax
0x180075bb6  jz      loc_180075EC3
0x180075bbc  lea     r12d, [rax+r14]
0x180075bc0  mov     [rbp+57h+var_74], r13d
0x180075bc4  mov     eax, [rbp+57h+arg_18]
0x180075bc7  add     eax, r12d
0x180075bca  mov     [rbp+57h+var_88], r13d
0x180075bce  mov     [rbp+57h+var_70], eax
0x180075bd1  mov     [rbp+57h+var_84], r13d
0x180075bd5  mov     [rbp+57h+var_78], r13d
0x180075bd9  mov     [rbp+57h+var_48], r12d
0x180075bdd  cmp     r15d, ebx
0x180075be0  jnb     loc_180075EA9
0x180075be6  mov     rax, [rsi]
0x180075be9  mov     ecx, r15d
0x180075bec  mov     [rbp+57h+var_40], rcx
0x180075bf0  mov     r13b, [rax+r15]
0x180075bf4  and     r13b, 0Fh
0x180075bf8  mov     byte ptr [rbp+57h+arg_18], r13b
0x180075bfc  lea     eax, [r13-7]
0x180075c00  cmp     al, 3
0x180075c02  ja      loc_180075ECA
0x180075c08  lea     r8, [rbp+57h+arg_10]
0x180075c0c  mov     edx, r15d
0x180075c0f  mov     rcx, rsi
0x180075c12  call    jsonbPayloadSize
0x180075c17  mov     [rbp+57h+var_7C], eax
0x180075c1a  test    eax, eax
0x180075c1c  jz      loc_180075ECA
0x180075c22  mov     r13d, [rbp+57h+arg_10]
0x180075c26  add     r13d, eax
0x180075c29  add     r13d, r15d
0x180075c2c  mov     dword ptr [rbp+57h+var_60], r13d
0x180075c30  cmp     r13d, ebx
0x180075c33  jnb     loc_180075ECA
0x180075c39  lea     r8, [rbp+57h+var_80]
0x180075c3d  mov     edx, r13d
0x180075c40  mov     rcx, rsi
0x180075c43  call    jsonbPayloadSize
0x180075c48  mov     [rbp+57h+var_54], eax
0x180075c4b  mov     ecx, eax
0x180075c4d  test    eax, eax
0x180075c4f  jz      loc_180075ECA
0x180075c55  mov     eax, [rbp+57h+var_80]
0x180075c58  add     eax, ecx
0x180075c5a  mov     [rbp+57h+var_6C], r15d
0x180075c5e  mov     dword ptr [rbp+57h+Size], eax
0x180075c61  lea     r15d, [rax+r13]
0x180075c65  cmp     r15d, ebx
0x180075c68  ja      loc_180075ECA
0x180075c6e  mov     eax, [rdi+34h]
0x180075c71  mov     ebx, [rbp+57h+var_70]
0x180075c74  add     ebx, eax
0x180075c76  mov     [rbp+57h+var_58], eax
0x180075c79  cmp     r12d, ebx
0x180075c7c  jnb     loc_180075D58
0x180075c82  mov     rcx, [rdi]
0x180075c85  mov     eax, r12d
0x180075c88  mov     r13b, [rax+rcx]
0x180075c8c  and     r13b, 0Fh
0x180075c90  lea     eax, [r13-7]
0x180075c94  cmp     al, 3
0x180075c96  ja      loc_180075EC3
0x180075c9c  lea     r8, [rbp+57h+var_90]
0x180075ca0  mov     edx, r12d
0x180075ca3  mov     rcx, rdi
0x180075ca6  call    jsonbPayloadSize
0x180075cab  mov     [rbp+57h+var_88], eax
0x180075cae  test    eax, eax
0x180075cb0  jz      loc_180075EC3
0x180075cb6  add     eax, [rbp+57h+var_90]
0x180075cb9  add     eax, r12d
0x180075cbc  mov     [rbp+57h+var_84], eax
0x180075cbf  cmp     eax, ebx
0x180075cc1  jnb     loc_180075EC3
0x180075cc7  lea     r8, [rbp+57h+var_8C]
0x180075ccb  mov     edx, eax
0x180075ccd  mov     rcx, rdi
0x180075cd0  call    jsonbPayloadSize
0x180075cd5  mov     [rbp+57h+var_78], eax
0x180075cd8  test    eax, eax
0x180075cda  jz      loc_180075EC3
0x180075ce0  add     eax, [rbp+57h+var_8C]
0x180075ce3  add     eax, [rbp+57h+var_84]
0x180075ce6  mov     [rbp+57h+var_68], eax
0x180075ce9  cmp     eax, ebx
0x180075ceb  ja      loc_180075EC3
0x180075cf1  mov     [rbp+57h+var_74], r12d
0x180075cf5  cmp     r13b, 7
0x180075cf9  jz      short loc_180075D05
0x180075cfb  cmp     r13b, 0Ah
0x180075cff  jz      short loc_180075D05
0x180075d01  xor     edx, edx
0x180075d03  jmp     short loc_180075D0A
0x180075d05  mov     edx, 1
0x180075d0a  mov     r13b, byte ptr [rbp+57h+arg_18]
0x180075d0e  cmp     r13b, 7
0x180075d12  jz      short loc_180075D1F
0x180075d14  cmp     r13b, 0Ah
0x180075d18  jz      short loc_180075D1F
0x180075d1a  xor     r8d, r8d
0x180075d1d  jmp     short loc_180075D25
0x180075d1f  mov     r8d, 1
0x180075d25  mov     r9d, [rbp+57h+var_88]
0x180075d29  mov     ecx, [rbp+57h+var_6C]
0x180075d2c  add     r9d, r12d
0x180075d2f  add     ecx, [rbp+57h+var_7C]
0x180075d32  mov     eax, [rbp+57h+var_90]
0x180075d35  add     r9, [rdi]
0x180075d38  add     rcx, [rsi]
0x180075d3b  mov     [rsp+0C0h+var_98], edx
0x180075d3f  mov     edx, [rbp+57h+arg_10]
0x180075d42  mov     [rsp+0C0h+var_A0], eax
0x180075d46  call    jsonLabelCompare
0x180075d4b  test    eax, eax
0x180075d4d  jnz     short loc_180075D58
0x180075d4f  mov     r12d, [rbp+57h+var_68]
0x180075d53  jmp     loc_180075C79
0x180075d58  mov     r13d, dword ptr [rbp+57h+var_60]
0x180075d5c  mov     rcx, [rsi]
0x180075d5f  mov     [rbp+57h+var_60], r13
0x180075d63  mov     al, [r13+rcx+0]
0x180075d68  and     al, 0Fh
0x180075d6a  cmp     r12d, ebx
0x180075d6d  jnb     short loc_180075DD8
0x180075d6f  mov     rcx, rdi
0x180075d72  test    al, al
0x180075d74  jnz     short loc_180075DAD
0x180075d76  mov     r8d, [rbp+57h+var_8C]
0x180075d7a  xor     r13d, r13d
0x180075d7d  add     r8d, [rbp+57h+var_78]
0x180075d81  xor     r9d, r9d
0x180075d84  add     r8d, [rbp+57h+var_90]
0x180075d88  add     r8d, [rbp+57h+var_88]
0x180075d8c  mov     edx, [rbp+57h+var_74]
0x180075d8f  mov     [rsp+0C0h+var_A0], r13d
0x180075d94  call    jsonBlobEdit
0x180075d99  cmp     [rdi+2Fh], r13b
0x180075d9d  jz      loc_180075E9D
0x180075da3  mov     eax, 3
0x180075da8  jmp     loc_180075ECF
0x180075dad  mov     edx, [rbp+57h+var_84]
0x180075db0  mov     r9d, r13d
0x180075db3  mov     r8, rsi
0x180075db6  mov     dword ptr [rdi+34h], 0
0x180075dbd  call    jsonMergePatch
0x180075dc2  xor     r13d, r13d
0x180075dc5  test    eax, eax
0x180075dc7  jnz     loc_180075ECF
0x180075dcd  mov     eax, [rbp+57h+var_58]
0x180075dd0  add     [rdi+34h], eax
0x180075dd3  jmp     loc_180075E9D
0x180075dd8  test    al, al
0x180075dda  jz      loc_180075E9A
0x180075de0  mov     r12d, [rbp+57h+arg_10]
0x180075de4  xor     r9d, r9d
0x180075de7  add     r12d, [rbp+57h+var_7C]
0x180075deb  xor     r8d, r8d
0x180075dee  mov     edx, ebx
0x180075df0  mov     rcx, rdi
0x180075df3  cmp     al, 0Ch
0x180075df5  jz      short loc_180075E3F
0x180075df7  mov     eax, [rbp+57h+var_80]
0x180075dfa  add     eax, r12d
0x180075dfd  add     eax, [rbp+57h+var_54]
0x180075e00  mov     [rsp+0C0h+var_A0], eax
0x180075e04  call    jsonBlobEdit
0x180075e09  xor     r13d, r13d
0x180075e0c  cmp     [rdi+2Fh], r13b
0x180075e10  jnz     short loc_180075DA3
0x180075e12  mov     rdx, [rbp+57h+var_40]
0x180075e16  add     rdx, [rsi]; Src
0x180075e19  mov     ecx, ebx
0x180075e1b  add     rcx, [rdi]; void *
0x180075e1e  mov     r8d, r12d; Size
0x180075e21  call    memcpy_0
0x180075e26  mov     rdx, [rbp+57h+var_60]
0x180075e2a  lea     ecx, [r12+rbx]
0x180075e2e  add     rdx, [rsi]; Src
0x180075e31  add     rcx, [rdi]; void *
0x180075e34  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x180075e38  call    memcpy_0
0x180075e3d  jmp     short loc_180075E9D
0x180075e3f  lea     eax, [r12+1]
0x180075e44  mov     [rsp+0C0h+var_A0], eax
0x180075e48  call    jsonBlobEdit
0x180075e4d  cmp     byte ptr [rdi+2Fh], 0
0x180075e51  jnz     loc_180075DA3
0x180075e57  mov     rdx, [rbp+57h+var_40]
0x180075e5b  add     rdx, [rsi]; Src
0x180075e5e  mov     ecx, ebx
0x180075e60  add     rcx, [rdi]; void *
0x180075e63  mov     r8d, r12d; Size
0x180075e66  call    memcpy_0
0x180075e6b  mov     rax, [rdi]
0x180075e6e  lea     edx, [r12+rbx]
0x180075e72  mov     r9d, r13d
0x180075e75  mov     r8, rsi
0x180075e78  mov     rcx, rdi
0x180075e7b  mov     byte ptr [rdx+rax], 0
0x180075e7f  mov     ebx, [rdi+34h]
0x180075e82  mov     dword ptr [rdi+34h], 0
0x180075e89  call    jsonMergePatch
0x180075e8e  xor     r13d, r13d
0x180075e91  test    eax, eax
0x180075e93  jnz     short loc_180075ECF
0x180075e95  add     [rdi+34h], ebx
0x180075e98  jmp     short loc_180075E9D
0x180075e9a  xor     r13d, r13d
0x180075e9d  mov     ebx, dword ptr [rbp+57h+Size+4]
0x180075ea0  mov     r12d, [rbp+57h+var_48]
0x180075ea4  jmp     loc_180075BDD
0x180075ea9  cmp     [rdi+34h], r13d
0x180075ead  jz      loc_180075B2D
0x180075eb3  mov     edx, r14d
0x180075eb6  mov     rcx, rdi
  ... truncated ...
```
