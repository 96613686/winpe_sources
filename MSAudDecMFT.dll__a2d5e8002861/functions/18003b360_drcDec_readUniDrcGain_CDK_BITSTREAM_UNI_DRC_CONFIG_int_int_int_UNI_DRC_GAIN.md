# drcDec_readUniDrcGain(CDK_BITSTREAM *,UNI_DRC_CONFIG *,int,int,int,UNI_DRC_GAIN *)

- ea: `0x18003b360`
- end: `0x18003b506`
- name: `?drcDec_readUniDrcGain@@YA?AW4DRC_ERROR@@PEAUCDK_BITSTREAM@@PEAUUNI_DRC_CONFIG@@HHHPEAUUNI_DRC_GAIN@@@Z`
- size: `422`
- prototype: `enum DRC_ERROR __high(struct CDK_BITSTREAM *, struct UNI_DRC_CONFIG *, int, int, int, struct UNI_DRC_GAIN *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18003b2d4`

## callees

- `0x1800110c0`
- `0x18003a388`
- `0x18003b360`
- `0x18004d320`
- `0x1800769a4`
- `0x1800778ac`
- `0x18009606c`

## pseudocode

```c
__int64 __fastcall drcDec_readUniDrcGain(_DWORD *a1, struct UNI_DRC_CONFIG *a2, int a3, int a4, __int64 a5, _BYTE *a6)
{
  struct DRC_COEFFICIENTS_UNI_DRC *v8; // rax
  __int64 v9; // r8
  struct DRC_COEFFICIENTS_UNI_DRC *v10; // rsi
  int v11; // ebp
  int v12; // r15d
  int i; // edi
  __int64 v14; // rax
  char *v15; // rdx
  int v16; // r9d
  unsigned int v17; // eax
  int v18; // r8d
  unsigned int v19; // edi
  char v20; // al
  __int64 result; // rax
  char v22[4]; // [rsp+30h] [rbp-E8h] BYREF
  int v23; // [rsp+34h] [rbp-E4h]
  _BYTE Src[128]; // [rsp+40h] [rbp-D8h] BYREF

  v23 = a3;
  v8 = selectDrcCoefficients(a2, 1);
  v10 = v8;
  if ( !a6 )
    return 4294967196LL;
  if ( v8 )
  {
    v11 = *((unsigned __int8 *)v8 + 1452);
    v12 = 0;
    for ( i = 0; i < v11; ++i )
    {
      v22[0] = 0;
      if ( i < 12 )
      {
        v14 = *((unsigned __int8 *)v10 + i + 1910);
        if ( (unsigned __int8)v14 >= *((_BYTE *)v10 + 1453) || (unsigned __int8)v14 >= 0xCu )
          return 4294967196LL;
        v15 = (char *)v10 + 38 * v14 + 1454;
        if ( v15[4] )
          v16 = *((unsigned __int16 *)v15 + 3);
        else
          v16 = a4;
        readDrcGainSequence((_DWORD)a1, (_DWORD)v15, v23, v16, (__int64)v22, (__int64)Src);
        v17 = (unsigned __int8)v22[0];
        v18 = 16;
        a6[i] = v22[0];
        if ( v17 < 0x10 )
          v18 = v17;
        memcpy_0(&a6[128 * (__int64)i + 12], Src, (unsigned int)(8 * v18));
      }
      else
      {
        v12 = 1;
      }
    }
    v19 = 0;
    if ( v12
      || (v20 = CDKreadBits(a1, 1, v9), a6[1548] = v20, v20 != 1)
      || (result = readUniDrcGainExtension(a1, a6 + 1552), (v19 = result) == 0) )
    {
      a6[1588] = v11;
      a6[1589] = (_BYTE)v11 == *((_BYTE *)v10 + 1452);
      return v19;
    }
  }
  else
  {
    a6[1589] = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003b360  push    rbx
0x18003b362  push    rbp
0x18003b363  push    rsi
0x18003b364  push    rdi
0x18003b365  push    r12
0x18003b367  push    r13
0x18003b369  push    r14
0x18003b36b  push    r15
0x18003b36d  sub     rsp, 0D8h
0x18003b374  mov     rax, cs:__security_cookie
0x18003b37b  xor     rax, rsp
0x18003b37e  mov     [rsp+118h+var_58], rax
0x18003b386  mov     rbx, [rsp+118h+arg_28]
0x18003b38e  mov     rax, rdx
0x18003b391  mov     r14, rcx
0x18003b394  mov     [rsp+118h+var_E4], r8d
0x18003b399  mov     r12d, 1
0x18003b39f  mov     rcx, rax; struct UNI_DRC_CONFIG *
0x18003b3a2  mov     edx, r12d; int
0x18003b3a5  mov     r13d, r9d
0x18003b3a8  call    ?selectDrcCoefficients@@YAPEAUDRC_COEFFICIENTS_UNI_DRC@@PEAUUNI_DRC_CONFIG@@H@Z; selectDrcCoefficients(UNI_DRC_CONFIG *,int)
0x18003b3ad  mov     rsi, rax
0x18003b3b0  test    rbx, rbx
0x18003b3b3  jz      loc_18003B4DC
0x18003b3b9  test    rax, rax
0x18003b3bc  jz      loc_18003B4D1
0x18003b3c2  movzx   ebp, byte ptr [rax+5ACh]
0x18003b3c9  xor     r15d, r15d
0x18003b3cc  xor     edi, edi
0x18003b3ce  cmp     edi, ebp
0x18003b3d0  jge     loc_18003B484
0x18003b3d6  mov     [rsp+118h+var_E8], 0
0x18003b3db  cmp     edi, 0Ch
0x18003b3de  jl      short loc_18003B3E8
0x18003b3e0  mov     r15d, r12d
0x18003b3e3  jmp     loc_18003B47C
0x18003b3e8  movsxd  r12, edi
0x18003b3eb  movzx   eax, byte ptr [r12+rsi+776h]
0x18003b3f4  cmp     al, [rsi+5ADh]
0x18003b3fa  jnb     loc_18003B4DC
0x18003b400  cmp     al, 0Ch
0x18003b402  jnb     loc_18003B4DC
0x18003b408  imul    rdx, rax, 26h ; '&'
0x18003b40c  add     rdx, 5AEh
0x18003b413  add     rdx, rsi
0x18003b416  cmp     byte ptr [rdx+4], 0
0x18003b41a  jz      short loc_18003B423
0x18003b41c  movzx   r9d, word ptr [rdx+6]
0x18003b421  jmp     short loc_18003B426
0x18003b423  mov     r9d, r13d
0x18003b426  mov     r8d, [rsp+118h+var_E4]
0x18003b42b  lea     rax, [rsp+118h+Src]
0x18003b430  mov     [rsp+118h+var_F0], rax
0x18003b435  mov     rcx, r14
0x18003b438  lea     rax, [rsp+118h+var_E8]
0x18003b43d  mov     [rsp+118h+var_F8], rax
0x18003b442  call    _readDrcGainSequence
0x18003b447  movzx   eax, [rsp+118h+var_E8]
0x18003b44c  lea     rcx, [rbx+0Ch]
0x18003b450  mov     r8d, 10h
0x18003b456  mov     [r12+rbx], al
0x18003b45a  cmp     eax, r8d
0x18003b45d  lea     rdx, [rsp+118h+Src]; Src
0x18003b462  cmovb   r8d, eax
0x18003b466  shl     r12, 7
0x18003b46a  add     rcx, r12; void *
0x18003b46d  shl     r8d, 3; Size
0x18003b471  call    memcpy_0
0x18003b476  mov     r12d, 1
0x18003b47c  add     edi, r12d
0x18003b47f  jmp     loc_18003B3CE
0x18003b484  xor     edi, edi
0x18003b486  test    r15d, r15d
0x18003b489  jnz     short loc_18003B4B6
0x18003b48b  mov     edx, r12d
0x18003b48e  mov     rcx, r14
0x18003b491  call    CDKreadBits
0x18003b496  mov     [rbx+60Ch], al
0x18003b49c  cmp     al, r12b
0x18003b49f  jnz     short loc_18003B4B6
0x18003b4a1  lea     rdx, [rbx+610h]
0x18003b4a8  mov     rcx, r14
0x18003b4ab  call    _readUniDrcGainExtension
0x18003b4b0  mov     edi, eax
0x18003b4b2  test    eax, eax
0x18003b4b4  jnz     short loc_18003B4E1
0x18003b4b6  mov     [rbx+634h], bpl
0x18003b4bd  cmp     bpl, [rsi+5ACh]
0x18003b4c4  setz    al
0x18003b4c7  mov     [rbx+635h], al
0x18003b4cd  mov     eax, edi
0x18003b4cf  jmp     short loc_18003B4E1
0x18003b4d1  mov     byte ptr [rbx+635h], 0
0x18003b4d8  xor     eax, eax
0x18003b4da  jmp     short loc_18003B4E1
0x18003b4dc  mov     eax, 0FFFFFF9Ch
0x18003b4e1  mov     rcx, [rsp+118h+var_58]
0x18003b4e9  xor     rcx, rsp; StackCookie
0x18003b4ec  call    __security_check_cookie
0x18003b4f1  add     rsp, 0D8h
0x18003b4f8  pop     r15
0x18003b4fa  pop     r14
0x18003b4fc  pop     r13
0x18003b4fe  pop     r12
0x18003b500  pop     rdi
0x18003b501  pop     rsi
0x18003b502  pop     rbp
0x18003b503  pop     rbx
0x18003b504  retn
```
