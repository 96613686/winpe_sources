# jsonMergePatch

- ea: `0x180067c48`
- end: `0x180068096`
- name: `jsonMergePatch`
- size: `1102`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180067c48`
- `0x1800686d0`

## callees

- `0x180064cfc`
- `0x180065a04`
- `0x180067550`
- `0x180067c48`
- `0x18006ac38`
- `0x1800a6d08`

## pseudocode

```c
__int64 __fastcall jsonMergePatch(__int64 a1, unsigned int a2, __int64 *a3, unsigned int a4)
{
  _BYTE *v4; // r15
  __int64 v7; // r14
  char v9; // al
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // ebx
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
    jsonBlobEdit(a1, (unsigned int)v7, v13 + v57, v4, v12);
    return *(_BYTE *)(a1 + 47) != 0 ? 3 : 0;
  }
  if ( (*(_BYTE *)(a2 + *(_QWORD *)a1) & 0xF) != 0xC )
  {
    v15 = jsonbPayloadSize((__int64 *)a1, a2, &v57);
    jsonBlobEdit(a1, (unsigned int)(v15 + v7), v57, 0, 0);
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
      jsonAfterEditSizeAdjust(a1, (unsigned int)v7);
    return *(_BYTE *)(a1 + 47) != 0 ? 3 : 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180067c48  mov     [rsp-8+arg_0], rbx
0x180067c4d  push    rbp
0x180067c4e  push    rsi
0x180067c4f  push    rdi
0x180067c50  push    r12
0x180067c52  push    r13
0x180067c54  push    r14
0x180067c56  push    r15
0x180067c58  lea     rbp, [rsp-27h]
0x180067c5d  sub     rsp, 90h
0x180067c64  xor     r13d, r13d
0x180067c67  mov     r15d, r9d
0x180067c6a  add     r15, [r8]
0x180067c6d  mov     r12b, 0Ch
0x180067c70  mov     ebx, r9d
0x180067c73  mov     rsi, r8
0x180067c76  mov     r14d, edx
0x180067c79  mov     rdi, rcx
0x180067c7c  mov     [rbp+57h+arg_18], r13d
0x180067c80  mov     al, [r15]
0x180067c83  and     al, 0Fh
0x180067c85  mov     [rbp+57h+var_90], r13d
0x180067c89  mov     [rbp+57h+var_8C], r13d
0x180067c8d  mov     [rbp+57h+arg_10], r13d
0x180067c91  mov     [rbp+57h+var_80], r13d
0x180067c95  cmp     al, r12b
0x180067c98  jz      short loc_180067CE8
0x180067c9a  lea     r8, [rbp+57h+arg_18]
0x180067c9e  mov     edx, ebx
0x180067ca0  mov     rcx, rsi
0x180067ca3  call    jsonbPayloadSize
0x180067ca8  mov     ebx, [rbp+57h+arg_18]
0x180067cab  lea     r8, [rbp+57h+arg_18]
0x180067caf  mov     edx, r14d
0x180067cb2  mov     [rbp+57h+arg_18], r13d
0x180067cb6  mov     rcx, rdi
0x180067cb9  add     ebx, eax
0x180067cbb  call    jsonbPayloadSize
0x180067cc0  mov     r8d, [rbp+57h+arg_18]
0x180067cc4  mov     r9, r15
0x180067cc7  add     r8d, eax
0x180067cca  mov     [rsp+0C0h+var_A0], ebx
0x180067cce  mov     edx, r14d
0x180067cd1  mov     rcx, rdi
0x180067cd4  call    jsonBlobEdit
0x180067cd9  mov     al, [rdi+2Fh]
0x180067cdc  neg     al
0x180067cde  sbb     eax, eax
0x180067ce0  and     eax, 3
0x180067ce3  jmp     loc_18006807B
0x180067ce8  mov     rax, [rcx]
0x180067ceb  mov     cl, [r14+rax]
0x180067cef  and     cl, 0Fh
0x180067cf2  cmp     cl, r12b
0x180067cf5  jz      short loc_180067D2E
0x180067cf7  lea     r8, [rbp+57h+arg_18]
0x180067cfb  mov     edx, r14d
0x180067cfe  mov     rcx, rdi
0x180067d01  call    jsonbPayloadSize
0x180067d06  mov     r8d, [rbp+57h+arg_18]
0x180067d0a  xor     r9d, r9d
0x180067d0d  mov     rcx, rdi
0x180067d10  mov     [rsp+0C0h+var_A0], r13d
0x180067d15  lea     edx, [rax+r14]
0x180067d19  call    jsonBlobEdit
0x180067d1e  mov     rcx, [rdi]
0x180067d21  mov     al, [rcx+r14]
0x180067d25  and     al, 0FCh
0x180067d27  or      al, r12b
0x180067d2a  mov     [rcx+r14], al
0x180067d2e  lea     r8, [rbp+57h+arg_18]
0x180067d32  mov     edx, ebx
0x180067d34  mov     rcx, rsi
0x180067d37  call    jsonbPayloadSize
0x180067d3c  test    eax, eax
0x180067d3e  jz      loc_180068076
0x180067d44  lea     r15d, [rax+rbx]
0x180067d48  mov     edx, r14d
0x180067d4b  mov     ebx, [rbp+57h+arg_18]
0x180067d4e  lea     r8, [rbp+57h+arg_18]
0x180067d52  add     ebx, r15d
0x180067d55  mov     rcx, rdi
0x180067d58  mov     dword ptr [rbp+57h+Size+4], ebx
0x180067d5b  call    jsonbPayloadSize
0x180067d60  test    eax, eax
0x180067d62  jz      loc_18006806F
0x180067d68  lea     r12d, [rax+r14]
0x180067d6c  mov     [rbp+57h+var_74], r13d
0x180067d70  mov     eax, [rbp+57h+arg_18]
0x180067d73  add     eax, r12d
0x180067d76  mov     [rbp+57h+var_88], r13d
0x180067d7a  mov     [rbp+57h+var_70], eax
0x180067d7d  mov     [rbp+57h+var_84], r13d
0x180067d81  mov     [rbp+57h+var_78], r13d
0x180067d85  mov     [rbp+57h+var_48], r12d
0x180067d89  cmp     r15d, ebx
0x180067d8c  jnb     loc_180068055
0x180067d92  mov     rax, [rsi]
0x180067d95  mov     ecx, r15d
0x180067d98  mov     [rbp+57h+var_40], rcx
0x180067d9c  mov     r13b, [rax+r15]
0x180067da0  and     r13b, 0Fh
0x180067da4  mov     byte ptr [rbp+57h+arg_18], r13b
0x180067da8  lea     eax, [r13-7]
0x180067dac  cmp     al, 3
0x180067dae  ja      loc_180068076
0x180067db4  lea     r8, [rbp+57h+arg_10]
0x180067db8  mov     edx, r15d
0x180067dbb  mov     rcx, rsi
0x180067dbe  call    jsonbPayloadSize
0x180067dc3  mov     [rbp+57h+var_7C], eax
0x180067dc6  test    eax, eax
0x180067dc8  jz      loc_180068076
0x180067dce  mov     r13d, [rbp+57h+arg_10]
0x180067dd2  add     r13d, eax
0x180067dd5  add     r13d, r15d
0x180067dd8  mov     dword ptr [rbp+57h+var_60], r13d
0x180067ddc  cmp     r13d, ebx
0x180067ddf  jnb     loc_180068076
0x180067de5  lea     r8, [rbp+57h+var_80]
0x180067de9  mov     edx, r13d
0x180067dec  mov     rcx, rsi
0x180067def  call    jsonbPayloadSize
0x180067df4  mov     [rbp+57h+var_54], eax
0x180067df7  mov     ecx, eax
0x180067df9  test    eax, eax
0x180067dfb  jz      loc_180068076
0x180067e01  mov     eax, [rbp+57h+var_80]
0x180067e04  add     eax, ecx
0x180067e06  mov     [rbp+57h+var_6C], r15d
0x180067e0a  mov     dword ptr [rbp+57h+Size], eax
0x180067e0d  lea     r15d, [rax+r13]
0x180067e11  cmp     r15d, ebx
0x180067e14  ja      loc_180068076
0x180067e1a  mov     eax, [rdi+34h]
0x180067e1d  mov     ebx, [rbp+57h+var_70]
0x180067e20  add     ebx, eax
0x180067e22  mov     [rbp+57h+var_58], eax
0x180067e25  cmp     r12d, ebx
0x180067e28  jnb     loc_180067F04
0x180067e2e  mov     rcx, [rdi]
0x180067e31  mov     eax, r12d
0x180067e34  mov     r13b, [rax+rcx]
0x180067e38  and     r13b, 0Fh
0x180067e3c  lea     eax, [r13-7]
0x180067e40  cmp     al, 3
0x180067e42  ja      loc_18006806F
0x180067e48  lea     r8, [rbp+57h+var_90]
0x180067e4c  mov     edx, r12d
0x180067e4f  mov     rcx, rdi
0x180067e52  call    jsonbPayloadSize
0x180067e57  mov     [rbp+57h+var_88], eax
0x180067e5a  test    eax, eax
0x180067e5c  jz      loc_18006806F
0x180067e62  add     eax, [rbp+57h+var_90]
0x180067e65  add     eax, r12d
0x180067e68  mov     [rbp+57h+var_84], eax
0x180067e6b  cmp     eax, ebx
0x180067e6d  jnb     loc_18006806F
0x180067e73  lea     r8, [rbp+57h+var_8C]
0x180067e77  mov     edx, eax
0x180067e79  mov     rcx, rdi
0x180067e7c  call    jsonbPayloadSize
0x180067e81  mov     [rbp+57h+var_78], eax
0x180067e84  test    eax, eax
0x180067e86  jz      loc_18006806F
0x180067e8c  add     eax, [rbp+57h+var_8C]
0x180067e8f  add     eax, [rbp+57h+var_84]
0x180067e92  mov     [rbp+57h+var_68], eax
0x180067e95  cmp     eax, ebx
0x180067e97  ja      loc_18006806F
0x180067e9d  mov     [rbp+57h+var_74], r12d
0x180067ea1  cmp     r13b, 7
0x180067ea5  jz      short loc_180067EB1
0x180067ea7  cmp     r13b, 0Ah
0x180067eab  jz      short loc_180067EB1
0x180067ead  xor     edx, edx
0x180067eaf  jmp     short loc_180067EB6
0x180067eb1  mov     edx, 1
0x180067eb6  mov     r13b, byte ptr [rbp+57h+arg_18]
0x180067eba  cmp     r13b, 7
0x180067ebe  jz      short loc_180067ECB
0x180067ec0  cmp     r13b, 0Ah
0x180067ec4  jz      short loc_180067ECB
0x180067ec6  xor     r8d, r8d
0x180067ec9  jmp     short loc_180067ED1
0x180067ecb  mov     r8d, 1
0x180067ed1  mov     r9d, [rbp+57h+var_88]
0x180067ed5  mov     ecx, [rbp+57h+var_6C]
0x180067ed8  add     r9d, r12d
0x180067edb  add     ecx, [rbp+57h+var_7C]
0x180067ede  mov     eax, [rbp+57h+var_90]
0x180067ee1  add     r9, [rdi]
0x180067ee4  add     rcx, [rsi]
0x180067ee7  mov     [rsp+0C0h+var_98], edx
0x180067eeb  mov     edx, [rbp+57h+arg_10]
0x180067eee  mov     [rsp+0C0h+var_A0], eax
0x180067ef2  call    jsonLabelCompare
0x180067ef7  test    eax, eax
0x180067ef9  jnz     short loc_180067F04
0x180067efb  mov     r12d, [rbp+57h+var_68]
0x180067eff  jmp     loc_180067E25
0x180067f04  mov     r13d, dword ptr [rbp+57h+var_60]
0x180067f08  mov     rcx, [rsi]
0x180067f0b  mov     [rbp+57h+var_60], r13
0x180067f0f  mov     al, [r13+rcx+0]
0x180067f14  and     al, 0Fh
0x180067f16  cmp     r12d, ebx
0x180067f19  jnb     short loc_180067F84
0x180067f1b  mov     rcx, rdi
0x180067f1e  test    al, al
0x180067f20  jnz     short loc_180067F59
0x180067f22  mov     r8d, [rbp+57h+var_8C]
0x180067f26  xor     r13d, r13d
0x180067f29  add     r8d, [rbp+57h+var_78]
0x180067f2d  xor     r9d, r9d
0x180067f30  add     r8d, [rbp+57h+var_90]
0x180067f34  add     r8d, [rbp+57h+var_88]
0x180067f38  mov     edx, [rbp+57h+var_74]
0x180067f3b  mov     [rsp+0C0h+var_A0], r13d
0x180067f40  call    jsonBlobEdit
0x180067f45  cmp     [rdi+2Fh], r13b
0x180067f49  jz      loc_180068049
0x180067f4f  mov     eax, 3
0x180067f54  jmp     loc_18006807B
0x180067f59  mov     edx, [rbp+57h+var_84]
0x180067f5c  mov     r9d, r13d
0x180067f5f  mov     r8, rsi
0x180067f62  mov     dword ptr [rdi+34h], 0
0x180067f69  call    jsonMergePatch
0x180067f6e  xor     r13d, r13d
0x180067f71  test    eax, eax
0x180067f73  jnz     loc_18006807B
0x180067f79  mov     eax, [rbp+57h+var_58]
0x180067f7c  add     [rdi+34h], eax
0x180067f7f  jmp     loc_180068049
0x180067f84  test    al, al
0x180067f86  jz      loc_180068046
0x180067f8c  mov     r12d, [rbp+57h+arg_10]
0x180067f90  xor     r9d, r9d
0x180067f93  add     r12d, [rbp+57h+var_7C]
0x180067f97  xor     r8d, r8d
0x180067f9a  mov     edx, ebx
0x180067f9c  mov     rcx, rdi
0x180067f9f  cmp     al, 0Ch
0x180067fa1  jz      short loc_180067FEB
0x180067fa3  mov     eax, [rbp+57h+var_80]
0x180067fa6  add     eax, r12d
0x180067fa9  add     eax, [rbp+57h+var_54]
0x180067fac  mov     [rsp+0C0h+var_A0], eax
0x180067fb0  call    jsonBlobEdit
0x180067fb5  xor     r13d, r13d
0x180067fb8  cmp     [rdi+2Fh], r13b
0x180067fbc  jnz     short loc_180067F4F
0x180067fbe  mov     rdx, [rbp+57h+var_40]
0x180067fc2  add     rdx, [rsi]; Src
0x180067fc5  mov     ecx, ebx
0x180067fc7  add     rcx, [rdi]; void *
0x180067fca  mov     r8d, r12d; Size
0x180067fcd  call    memcpy_0
0x180067fd2  mov     rdx, [rbp+57h+var_60]
0x180067fd6  lea     ecx, [r12+rbx]
0x180067fda  add     rdx, [rsi]; Src
0x180067fdd  add     rcx, [rdi]; void *
0x180067fe0  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x180067fe4  call    memcpy_0
0x180067fe9  jmp     short loc_180068049
0x180067feb  lea     eax, [r12+1]
0x180067ff0  mov     [rsp+0C0h+var_A0], eax
0x180067ff4  call    jsonBlobEdit
0x180067ff9  cmp     byte ptr [rdi+2Fh], 0
0x180067ffd  jnz     loc_180067F4F
0x180068003  mov     rdx, [rbp+57h+var_40]
0x180068007  add     rdx, [rsi]; Src
0x18006800a  mov     ecx, ebx
0x18006800c  add     rcx, [rdi]; void *
0x18006800f  mov     r8d, r12d; Size
0x180068012  call    memcpy_0
0x180068017  mov     rax, [rdi]
0x18006801a  lea     edx, [r12+rbx]
0x18006801e  mov     r9d, r13d
0x180068021  mov     r8, rsi
0x180068024  mov     rcx, rdi
0x180068027  mov     byte ptr [rdx+rax], 0
0x18006802b  mov     ebx, [rdi+34h]
0x18006802e  mov     dword ptr [rdi+34h], 0
0x180068035  call    jsonMergePatch
0x18006803a  xor     r13d, r13d
0x18006803d  test    eax, eax
0x18006803f  jnz     short loc_18006807B
0x180068041  add     [rdi+34h], ebx
0x180068044  jmp     short loc_180068049
0x180068046  xor     r13d, r13d
0x180068049  mov     ebx, dword ptr [rbp+57h+Size+4]
0x18006804c  mov     r12d, [rbp+57h+var_48]
0x180068050  jmp     loc_180067D89
0x180068055  cmp     [rdi+34h], r13d
0x180068059  jz      loc_180067CD9
0x18006805f  mov     edx, r14d
0x180068062  mov     rcx, rdi
  ... truncated ...
```
