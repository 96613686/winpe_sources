# jsonMergePatch

- ea: `0x180084cb8`
- end: `0x180085106`
- name: `jsonMergePatch`
- size: `1102`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180084cb8`
- `0x180085740`

## callees

- `0x180081d0c`
- `0x180082a14`
- `0x1800845c0`
- `0x180084cb8`
- `0x180087c68`
- `0x1800af620`

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
  _BOOL8 v30; // r8
  __int64 v31; // r13
  __int64 v32; // rcx
  char v33; // al
  __int64 v34; // rdx
  unsigned int v35; // r12d
  __int64 v36; // rdx
  int v37; // ebx
  unsigned int v38; // [rsp+30h] [rbp-39h] BYREF
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
        v26 = jsonbPayloadSize((__int64 *)a1, v20, &v38);
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
                             *a3 + (unsigned int)(v43 + v47),
                             v56,
                             v30,
                             *(_QWORD *)a1 + v20 + v40,
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
0x180084cb8  mov     [rsp-8+arg_0], rbx
0x180084cbd  push    rbp
0x180084cbe  push    rsi
0x180084cbf  push    rdi
0x180084cc0  push    r12
0x180084cc2  push    r13
0x180084cc4  push    r14
0x180084cc6  push    r15
0x180084cc8  lea     rbp, [rsp-27h]
0x180084ccd  sub     rsp, 90h
0x180084cd4  xor     r13d, r13d
0x180084cd7  mov     r15d, r9d
0x180084cda  add     r15, [r8]
0x180084cdd  mov     r12b, 0Ch
0x180084ce0  mov     ebx, r9d
0x180084ce3  mov     rsi, r8
0x180084ce6  mov     r14d, edx
0x180084ce9  mov     rdi, rcx
0x180084cec  mov     [rbp+57h+arg_18], r13d
0x180084cf0  mov     al, [r15]
0x180084cf3  and     al, 0Fh
0x180084cf5  mov     [rbp+57h+var_90], r13d
0x180084cf9  mov     [rbp+57h+var_8C], r13d
0x180084cfd  mov     [rbp+57h+arg_10], r13d
0x180084d01  mov     [rbp+57h+var_80], r13d
0x180084d05  cmp     al, r12b
0x180084d08  jz      short loc_180084D58
0x180084d0a  lea     r8, [rbp+57h+arg_18]
0x180084d0e  mov     edx, ebx
0x180084d10  mov     rcx, rsi
0x180084d13  call    jsonbPayloadSize
0x180084d18  mov     ebx, [rbp+57h+arg_18]
0x180084d1b  lea     r8, [rbp+57h+arg_18]
0x180084d1f  mov     edx, r14d
0x180084d22  mov     [rbp+57h+arg_18], r13d
0x180084d26  mov     rcx, rdi
0x180084d29  add     ebx, eax
0x180084d2b  call    jsonbPayloadSize
0x180084d30  mov     r8d, [rbp+57h+arg_18]
0x180084d34  mov     r9, r15
0x180084d37  add     r8d, eax
0x180084d3a  mov     [rsp+0C0h+var_A0], ebx
0x180084d3e  mov     edx, r14d
0x180084d41  mov     rcx, rdi
0x180084d44  call    jsonBlobEdit
0x180084d49  mov     al, [rdi+2Fh]
0x180084d4c  neg     al
0x180084d4e  sbb     eax, eax
0x180084d50  and     eax, 3
0x180084d53  jmp     loc_1800850EB
0x180084d58  mov     rax, [rcx]
0x180084d5b  mov     cl, [r14+rax]
0x180084d5f  and     cl, 0Fh
0x180084d62  cmp     cl, r12b
0x180084d65  jz      short loc_180084D9E
0x180084d67  lea     r8, [rbp+57h+arg_18]
0x180084d6b  mov     edx, r14d
0x180084d6e  mov     rcx, rdi
0x180084d71  call    jsonbPayloadSize
0x180084d76  mov     r8d, [rbp+57h+arg_18]
0x180084d7a  xor     r9d, r9d
0x180084d7d  mov     rcx, rdi
0x180084d80  mov     [rsp+0C0h+var_A0], r13d
0x180084d85  lea     edx, [rax+r14]
0x180084d89  call    jsonBlobEdit
0x180084d8e  mov     rcx, [rdi]
0x180084d91  mov     al, [rcx+r14]
0x180084d95  and     al, 0FCh
0x180084d97  or      al, r12b
0x180084d9a  mov     [rcx+r14], al
0x180084d9e  lea     r8, [rbp+57h+arg_18]
0x180084da2  mov     edx, ebx
0x180084da4  mov     rcx, rsi
0x180084da7  call    jsonbPayloadSize
0x180084dac  test    eax, eax
0x180084dae  jz      loc_1800850E6
0x180084db4  lea     r15d, [rax+rbx]
0x180084db8  mov     edx, r14d
0x180084dbb  mov     ebx, [rbp+57h+arg_18]
0x180084dbe  lea     r8, [rbp+57h+arg_18]
0x180084dc2  add     ebx, r15d
0x180084dc5  mov     rcx, rdi
0x180084dc8  mov     dword ptr [rbp+57h+Size+4], ebx
0x180084dcb  call    jsonbPayloadSize
0x180084dd0  test    eax, eax
0x180084dd2  jz      loc_1800850DF
0x180084dd8  lea     r12d, [rax+r14]
0x180084ddc  mov     [rbp+57h+var_74], r13d
0x180084de0  mov     eax, [rbp+57h+arg_18]
0x180084de3  add     eax, r12d
0x180084de6  mov     [rbp+57h+var_88], r13d
0x180084dea  mov     [rbp+57h+var_70], eax
0x180084ded  mov     [rbp+57h+var_84], r13d
0x180084df1  mov     [rbp+57h+var_78], r13d
0x180084df5  mov     [rbp+57h+var_48], r12d
0x180084df9  cmp     r15d, ebx
0x180084dfc  jnb     loc_1800850C5
0x180084e02  mov     rax, [rsi]
0x180084e05  mov     ecx, r15d
0x180084e08  mov     [rbp+57h+var_40], rcx
0x180084e0c  mov     r13b, [rax+r15]
0x180084e10  and     r13b, 0Fh
0x180084e14  mov     byte ptr [rbp+57h+arg_18], r13b
0x180084e18  lea     eax, [r13-7]
0x180084e1c  cmp     al, 3
0x180084e1e  ja      loc_1800850E6
0x180084e24  lea     r8, [rbp+57h+arg_10]
0x180084e28  mov     edx, r15d
0x180084e2b  mov     rcx, rsi
0x180084e2e  call    jsonbPayloadSize
0x180084e33  mov     [rbp+57h+var_7C], eax
0x180084e36  test    eax, eax
0x180084e38  jz      loc_1800850E6
0x180084e3e  mov     r13d, [rbp+57h+arg_10]
0x180084e42  add     r13d, eax
0x180084e45  add     r13d, r15d
0x180084e48  mov     dword ptr [rbp+57h+var_60], r13d
0x180084e4c  cmp     r13d, ebx
0x180084e4f  jnb     loc_1800850E6
0x180084e55  lea     r8, [rbp+57h+var_80]
0x180084e59  mov     edx, r13d
0x180084e5c  mov     rcx, rsi
0x180084e5f  call    jsonbPayloadSize
0x180084e64  mov     [rbp+57h+var_54], eax
0x180084e67  mov     ecx, eax
0x180084e69  test    eax, eax
0x180084e6b  jz      loc_1800850E6
0x180084e71  mov     eax, [rbp+57h+var_80]
0x180084e74  add     eax, ecx
0x180084e76  mov     [rbp+57h+var_6C], r15d
0x180084e7a  mov     dword ptr [rbp+57h+Size], eax
0x180084e7d  lea     r15d, [rax+r13]
0x180084e81  cmp     r15d, ebx
0x180084e84  ja      loc_1800850E6
0x180084e8a  mov     eax, [rdi+34h]
0x180084e8d  mov     ebx, [rbp+57h+var_70]
0x180084e90  add     ebx, eax
0x180084e92  mov     [rbp+57h+var_58], eax
0x180084e95  cmp     r12d, ebx
0x180084e98  jnb     loc_180084F74
0x180084e9e  mov     rcx, [rdi]
0x180084ea1  mov     eax, r12d
0x180084ea4  mov     r13b, [rax+rcx]
0x180084ea8  and     r13b, 0Fh
0x180084eac  lea     eax, [r13-7]
0x180084eb0  cmp     al, 3
0x180084eb2  ja      loc_1800850DF
0x180084eb8  lea     r8, [rbp+57h+var_90]
0x180084ebc  mov     edx, r12d
0x180084ebf  mov     rcx, rdi
0x180084ec2  call    jsonbPayloadSize
0x180084ec7  mov     [rbp+57h+var_88], eax
0x180084eca  test    eax, eax
0x180084ecc  jz      loc_1800850DF
0x180084ed2  add     eax, [rbp+57h+var_90]
0x180084ed5  add     eax, r12d
0x180084ed8  mov     [rbp+57h+var_84], eax
0x180084edb  cmp     eax, ebx
0x180084edd  jnb     loc_1800850DF
0x180084ee3  lea     r8, [rbp+57h+var_8C]
0x180084ee7  mov     edx, eax
0x180084ee9  mov     rcx, rdi
0x180084eec  call    jsonbPayloadSize
0x180084ef1  mov     [rbp+57h+var_78], eax
0x180084ef4  test    eax, eax
0x180084ef6  jz      loc_1800850DF
0x180084efc  add     eax, [rbp+57h+var_8C]
0x180084eff  add     eax, [rbp+57h+var_84]
0x180084f02  mov     [rbp+57h+var_68], eax
0x180084f05  cmp     eax, ebx
0x180084f07  ja      loc_1800850DF
0x180084f0d  mov     [rbp+57h+var_74], r12d
0x180084f11  cmp     r13b, 7
0x180084f15  jz      short loc_180084F21
0x180084f17  cmp     r13b, 0Ah
0x180084f1b  jz      short loc_180084F21
0x180084f1d  xor     edx, edx
0x180084f1f  jmp     short loc_180084F26
0x180084f21  mov     edx, 1
0x180084f26  mov     r13b, byte ptr [rbp+57h+arg_18]
0x180084f2a  cmp     r13b, 7
0x180084f2e  jz      short loc_180084F3B
0x180084f30  cmp     r13b, 0Ah
0x180084f34  jz      short loc_180084F3B
0x180084f36  xor     r8d, r8d
0x180084f39  jmp     short loc_180084F41
0x180084f3b  mov     r8d, 1
0x180084f41  mov     r9d, [rbp+57h+var_88]
0x180084f45  mov     ecx, [rbp+57h+var_6C]
0x180084f48  add     r9d, r12d
0x180084f4b  add     ecx, [rbp+57h+var_7C]
0x180084f4e  mov     eax, [rbp+57h+var_90]
0x180084f51  add     r9, [rdi]
0x180084f54  add     rcx, [rsi]
0x180084f57  mov     [rsp+0C0h+var_98], edx
0x180084f5b  mov     edx, [rbp+57h+arg_10]
0x180084f5e  mov     [rsp+0C0h+var_A0], eax
0x180084f62  call    jsonLabelCompare
0x180084f67  test    eax, eax
0x180084f69  jnz     short loc_180084F74
0x180084f6b  mov     r12d, [rbp+57h+var_68]
0x180084f6f  jmp     loc_180084E95
0x180084f74  mov     r13d, dword ptr [rbp+57h+var_60]
0x180084f78  mov     rcx, [rsi]
0x180084f7b  mov     [rbp+57h+var_60], r13
0x180084f7f  mov     al, [r13+rcx+0]
0x180084f84  and     al, 0Fh
0x180084f86  cmp     r12d, ebx
0x180084f89  jnb     short loc_180084FF4
0x180084f8b  mov     rcx, rdi
0x180084f8e  test    al, al
0x180084f90  jnz     short loc_180084FC9
0x180084f92  mov     r8d, [rbp+57h+var_8C]
0x180084f96  xor     r13d, r13d
0x180084f99  add     r8d, [rbp+57h+var_78]
0x180084f9d  xor     r9d, r9d
0x180084fa0  add     r8d, [rbp+57h+var_90]
0x180084fa4  add     r8d, [rbp+57h+var_88]
0x180084fa8  mov     edx, [rbp+57h+var_74]
0x180084fab  mov     [rsp+0C0h+var_A0], r13d
0x180084fb0  call    jsonBlobEdit
0x180084fb5  cmp     [rdi+2Fh], r13b
0x180084fb9  jz      loc_1800850B9
0x180084fbf  mov     eax, 3
0x180084fc4  jmp     loc_1800850EB
0x180084fc9  mov     edx, [rbp+57h+var_84]
0x180084fcc  mov     r9d, r13d
0x180084fcf  mov     r8, rsi
0x180084fd2  mov     dword ptr [rdi+34h], 0
0x180084fd9  call    jsonMergePatch
0x180084fde  xor     r13d, r13d
0x180084fe1  test    eax, eax
0x180084fe3  jnz     loc_1800850EB
0x180084fe9  mov     eax, [rbp+57h+var_58]
0x180084fec  add     [rdi+34h], eax
0x180084fef  jmp     loc_1800850B9
0x180084ff4  test    al, al
0x180084ff6  jz      loc_1800850B6
0x180084ffc  mov     r12d, [rbp+57h+arg_10]
0x180085000  xor     r9d, r9d
0x180085003  add     r12d, [rbp+57h+var_7C]
0x180085007  xor     r8d, r8d
0x18008500a  mov     edx, ebx
0x18008500c  mov     rcx, rdi
0x18008500f  cmp     al, 0Ch
0x180085011  jz      short loc_18008505B
0x180085013  mov     eax, [rbp+57h+var_80]
0x180085016  add     eax, r12d
0x180085019  add     eax, [rbp+57h+var_54]
0x18008501c  mov     [rsp+0C0h+var_A0], eax
0x180085020  call    jsonBlobEdit
0x180085025  xor     r13d, r13d
0x180085028  cmp     [rdi+2Fh], r13b
0x18008502c  jnz     short loc_180084FBF
0x18008502e  mov     rdx, [rbp+57h+var_40]
0x180085032  add     rdx, [rsi]; Src
0x180085035  mov     ecx, ebx
0x180085037  add     rcx, [rdi]; void *
0x18008503a  mov     r8d, r12d; Size
0x18008503d  call    memcpy_0
0x180085042  mov     rdx, [rbp+57h+var_60]
0x180085046  lea     ecx, [r12+rbx]
0x18008504a  add     rdx, [rsi]; Src
0x18008504d  add     rcx, [rdi]; void *
0x180085050  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x180085054  call    memcpy_0
0x180085059  jmp     short loc_1800850B9
0x18008505b  lea     eax, [r12+1]
0x180085060  mov     [rsp+0C0h+var_A0], eax
0x180085064  call    jsonBlobEdit
0x180085069  cmp     byte ptr [rdi+2Fh], 0
0x18008506d  jnz     loc_180084FBF
0x180085073  mov     rdx, [rbp+57h+var_40]
0x180085077  add     rdx, [rsi]; Src
0x18008507a  mov     ecx, ebx
0x18008507c  add     rcx, [rdi]; void *
0x18008507f  mov     r8d, r12d; Size
0x180085082  call    memcpy_0
0x180085087  mov     rax, [rdi]
0x18008508a  lea     edx, [r12+rbx]
0x18008508e  mov     r9d, r13d
0x180085091  mov     r8, rsi
0x180085094  mov     rcx, rdi
0x180085097  mov     byte ptr [rdx+rax], 0
0x18008509b  mov     ebx, [rdi+34h]
0x18008509e  mov     dword ptr [rdi+34h], 0
0x1800850a5  call    jsonMergePatch
0x1800850aa  xor     r13d, r13d
0x1800850ad  test    eax, eax
0x1800850af  jnz     short loc_1800850EB
0x1800850b1  add     [rdi+34h], ebx
0x1800850b4  jmp     short loc_1800850B9
0x1800850b6  xor     r13d, r13d
0x1800850b9  mov     ebx, dword ptr [rbp+57h+Size+4]
0x1800850bc  mov     r12d, [rbp+57h+var_48]
0x1800850c0  jmp     loc_180084DF9
0x1800850c5  cmp     [rdi+34h], r13d
0x1800850c9  jz      loc_180084D49
0x1800850cf  mov     edx, r14d
0x1800850d2  mov     rcx, rdi
  ... truncated ...
```
