# CheckAndConvertWriteInput(CAPABILITIES_LIST_ENTRY const *,tagPROPVARIANT const *,tagPROPVARIANT *,bool *)

- ea: `0x18001ed1c`
- end: `0x18001eee8`
- name: `?CheckAndConvertWriteInput@@YAJPEBUCAPABILITIES_LIST_ENTRY@@PEBUtagPROPVARIANT@@PEAU2@PEA_N@Z`
- size: `460`
- prototype: `__int64 __fastcall(const struct CAPABILITIES_LIST_ENTRY *, PROPVARIANT *pvarSrc, struct tagPROPVARIANT *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001d5c0`
- `0x18001ded0`

## callees

- `0x180006fc0`
- `0x18000b0f8`
- `0x18000b26c`
- `0x18000c5a0`
- `0x18001ed1c`
- `0x18001f0e4`
- `0x18001f1f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001edb5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001edb5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ee99`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001eeac`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ee99`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001eeac`
- `PROPSYS!PropVariantChangeType` at `0x18001ed88`
- `PROPSYS!PropVariantChangeType` at `0x18001ed88`
- `PROPSYS!PropVariantGetElementCount` at `0x18001ee83`
- `PROPSYS!PropVariantGetElementCount` at `0x18001ee83`

## pseudocode

```c
__int64 __fastcall CheckAndConvertWriteInput(
        const struct CAPABILITIES_LIST_ENTRY *a1,
        PROPVARIANT *pvarSrc,
        struct tagPROPVARIANT *a3,
        bool *a4)
{
  VARTYPE vt; // r9
  HRESULT v8; // eax
  int v9; // ebx
  int v10; // r8d
  int v11; // edx
  int v12; // eax
  bool *v13; // r9
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *bstrVal; // rcx
  __int64 v16; // r10
  int v17; // ebx
  bool v18; // al
  PROPVARIANT ppropvarDest; // [rsp+30h] [rbp-20h] BYREF
  bool v21; // [rsp+78h] [rbp+28h] BYREF
  unsigned __int64 v22; // [rsp+88h] [rbp+38h] BYREF

  v21 = 0;
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  vt = pvarSrc->vt;
  memset(&ppropvarDest, 0, sizeof(ppropvarDest));
  if ( (vt & 0xFFF) == 8 )
  {
    v8 = PropVariantChangeType(&ppropvarDest, pvarSrc, 0, vt & 0xF000 | 0x1F);
  }
  else if ( (vt & 0xFFF) == 0x1E )
  {
    v8 = SniffAndConvertToWideString(pvarSrc, &ppropvarDest);
  }
  else
  {
    v8 = PropVariantCopy(&ppropvarDest, pvarSrc);
  }
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( !*((_DWORD *)a1 + 3)
      || ((v10 = *((_DWORD *)a1 + 12), v11 = *((_DWORD *)a1 + 11), !*((_DWORD *)a1 + 4))
        ? (v12 = CheckRange(&ppropvarDest, v11, v10))
        : (v12 = ClipToRange(&ppropvarDest, v11, v10, *((_WORD *)a1 + 26), &v21)),
          v9 = v12,
          v12 >= 0) )
    {
      v13 = &v21;
      if ( v21 )
        v13 = 0;
      v9 = CheckForBadTypesAndCoerceStringVectors(a1, &ppropvarDest, a3, v13);
      if ( v9 >= 0 )
      {
        v14 = (const unsigned __int16 *)*((_QWORD *)a1 + 7);
        if ( !v14 || (v9 = CheckForDisallowedChars(a3, v14), v9 >= 0) )
        {
          if ( (*((int *)a1 + 9) < 0
             || a3->vt != 31
             || (bstrVal = a3->bstrVal, v22 = 0, (int)StringCchLengthW(bstrVal, 0x7FFFFFFFu, &v22) >= 0) && v22 == v16)
            && ((v17 = *((_DWORD *)a1 + 10), v17 < 0) || PropVariantGetElementCount(a3) == v17) )
          {
            v9 = 0;
          }
          else
          {
            v9 = -2147316575;
          }
        }
      }
    }
  }
  PropVariantClear(&ppropvarDest);
  if ( v9 < 0 )
    PropVariantClear(a3);
  if ( a4 )
  {
    v18 = v9 >= 0 && v21;
    *a4 = v18;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001ed1c  mov     [rsp-18h+arg_0], rbx
0x18001ed21  mov     [rsp-18h+arg_10], rsi
0x18001ed26  push    rbp
0x18001ed27  push    rdi
0x18001ed28  push    r14
0x18001ed2a  mov     rbp, rsp
0x18001ed2d  sub     rsp, 50h
0x18001ed31  mov     rdi, rcx
0x18001ed34  mov     [rbp+arg_8], 0
0x18001ed38  xor     ecx, ecx
0x18001ed3a  xorps   xmm0, xmm0
0x18001ed3d  movups  xmmword ptr [r8], xmm0
0x18001ed41  mov     [r8+10h], rcx
0x18001ed45  mov     rax, rdx
0x18001ed48  mov     qword ptr [rbp+ppropvarDest+10h], rcx
0x18001ed4c  mov     r14, r9
0x18001ed4f  movzx   r9d, word ptr [rdx]
0x18001ed53  mov     rsi, r8
0x18001ed56  mov     edx, 0FFFh
0x18001ed5b  movzx   ecx, r9w
0x18001ed5f  and     cx, dx
0x18001ed62  mov     edx, 8
0x18001ed67  movups  xmmword ptr [rbp+ppropvarDest], xmm0
0x18001ed6b  cmp     dx, cx
0x18001ed6e  jnz     short loc_18001ED96
0x18001ed70  mov     ecx, 0F01Fh
0x18001ed75  xor     r8d, r8d; flags
0x18001ed78  and     r9w, cx
0x18001ed7c  mov     rdx, rax; propvarSrc
0x18001ed7f  or      r9w, 1Fh; vt
0x18001ed84  lea     rcx, [rbp+ppropvarDest]; ppropvarDest
0x18001ed88  call    cs:__imp_PropVariantChangeType
0x18001ed8f  nop     dword ptr [rax+rax+00h]
0x18001ed94  jmp     short loc_18001EDC1
0x18001ed96  mov     edx, 1Eh
0x18001ed9b  cmp     dx, cx
0x18001ed9e  jnz     short loc_18001EDAE
0x18001eda0  lea     rdx, [rbp+ppropvarDest]; pvarDest
0x18001eda4  mov     rcx, rax; pvarSrc
0x18001eda7  call    ?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18001edac  jmp     short loc_18001EDC1
0x18001edae  mov     rdx, rax; pvarSrc
0x18001edb1  lea     rcx, [rbp+ppropvarDest]; pvarDest
0x18001edb5  call    cs:__imp_PropVariantCopy
0x18001edbc  nop     dword ptr [rax+rax+00h]
0x18001edc1  mov     ebx, eax
0x18001edc3  test    eax, eax
0x18001edc5  js      loc_18001EE95
0x18001edcb  cmp     dword ptr [rdi+0Ch], 0
0x18001edcf  jz      short loc_18001EE06
0x18001edd1  cmp     dword ptr [rdi+10h], 0
0x18001edd5  lea     rcx, [rbp+ppropvarDest]; pvarSrc
0x18001edd9  mov     r8d, [rdi+30h]; int
0x18001eddd  mov     edx, [rdi+2Ch]; int
0x18001ede0  jz      short loc_18001EDF7
0x18001ede2  movzx   r9d, word ptr [rdi+34h]; unsigned __int16
0x18001ede7  lea     rax, [rbp+arg_8]
0x18001edeb  mov     [rsp+50h+var_30], rax; bool *
0x18001edf0  call    ?ClipToRange@@YAJPEAUtagPROPVARIANT@@HHGPEA_N@Z; ClipToRange(tagPROPVARIANT *,int,int,ushort,bool *)
0x18001edf5  jmp     short loc_18001EDFC
0x18001edf7  call    ?CheckRange@@YAJPEBUtagPROPVARIANT@@HH@Z; CheckRange(tagPROPVARIANT const *,int,int)
0x18001edfc  mov     ebx, eax
0x18001edfe  test    eax, eax
0x18001ee00  js      loc_18001EE95
0x18001ee06  xor     eax, eax
0x18001ee08  lea     r9, [rbp+arg_8]
0x18001ee0c  cmp     [rbp+arg_8], al
0x18001ee0f  lea     rdx, [rbp+ppropvarDest]; struct tagPROPVARIANT *
0x18001ee13  mov     r8, rsi; struct tagPROPVARIANT *
0x18001ee16  mov     rcx, rdi; struct CAPABILITIES_LIST_ENTRY *
0x18001ee19  cmovnz  r9, rax; bool *
0x18001ee1d  call    ?CheckForBadTypesAndCoerceStringVectors@@YAJPEBUCAPABILITIES_LIST_ENTRY@@AEBUtagPROPVARIANT@@PEAU2@PEA_N@Z; CheckForBadTypesAndCoerceStringVectors(CAPABILITIES_LIST_ENTRY const *,tagPROPVARIANT const &,tagPROPVARIANT *,bool *)
0x18001ee22  mov     ebx, eax
0x18001ee24  test    eax, eax
0x18001ee26  js      short loc_18001EE95
0x18001ee28  mov     rdx, [rdi+38h]; unsigned __int16 *
0x18001ee2c  test    rdx, rdx
0x18001ee2f  jz      short loc_18001EE3F
0x18001ee31  mov     rcx, rsi; struct tagPROPVARIANT *
0x18001ee34  call    ?CheckForDisallowedChars@@YAJPEBUtagPROPVARIANT@@PEBG@Z; CheckForDisallowedChars(tagPROPVARIANT const *,ushort const *)
0x18001ee39  mov     ebx, eax
0x18001ee3b  test    eax, eax
0x18001ee3d  js      short loc_18001EE95
0x18001ee3f  movsxd  r10, dword ptr [rdi+24h]
0x18001ee43  test    r10d, r10d
0x18001ee46  js      short loc_18001EE79
0x18001ee48  cmp     word ptr [rsi], 1Fh
0x18001ee4c  jnz     short loc_18001EE79
0x18001ee4e  mov     rcx, [rsi+8]; unsigned __int16 *
0x18001ee52  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x18001ee56  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001ee5b  mov     [rbp+arg_18], 0
0x18001ee63  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001ee68  test    eax, eax
0x18001ee6a  js      short loc_18001EE72
0x18001ee6c  cmp     [rbp+arg_18], r10
0x18001ee70  jz      short loc_18001EE79
0x18001ee72  mov     ebx, 80028CA1h
0x18001ee77  jmp     short loc_18001EE95
0x18001ee79  mov     ebx, [rdi+28h]
0x18001ee7c  test    ebx, ebx
0x18001ee7e  js      short loc_18001EE93
0x18001ee80  mov     rcx, rsi; propvar
0x18001ee83  call    cs:__imp_PropVariantGetElementCount
0x18001ee8a  nop     dword ptr [rax+rax+00h]
0x18001ee8f  cmp     eax, ebx
0x18001ee91  jnz     short loc_18001EE72
0x18001ee93  xor     ebx, ebx
0x18001ee95  lea     rcx, [rbp+ppropvarDest]; pvar
0x18001ee99  call    cs:__imp_PropVariantClear
0x18001eea0  nop     dword ptr [rax+rax+00h]
0x18001eea5  test    ebx, ebx
0x18001eea7  jns     short loc_18001EEB8
0x18001eea9  mov     rcx, rsi; pvar
0x18001eeac  call    cs:__imp_PropVariantClear
0x18001eeb3  nop     dword ptr [rax+rax+00h]
0x18001eeb8  test    r14, r14
0x18001eebb  jz      short loc_18001EED0
0x18001eebd  test    ebx, ebx
0x18001eebf  js      short loc_18001EECB
0x18001eec1  cmp     [rbp+arg_8], 0
0x18001eec5  jz      short loc_18001EECB
0x18001eec7  mov     al, 1
0x18001eec9  jmp     short loc_18001EECD
0x18001eecb  xor     al, al
0x18001eecd  mov     [r14], al
0x18001eed0  lea     r11, [rsp+50h+var_s0]
0x18001eed5  mov     eax, ebx
0x18001eed7  mov     rbx, [r11+20h]
0x18001eedb  mov     rsi, [r11+30h]
0x18001eedf  mov     rsp, r11
0x18001eee2  pop     r14
0x18001eee4  pop     rdi
0x18001eee5  pop     rbp
0x18001eee6  retn
```
