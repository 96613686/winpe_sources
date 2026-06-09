# CheckAndConvertWriteInput(CAPABILITIES_LIST_ENTRY const *,tagPROPVARIANT const *,tagPROPVARIANT *,bool *)

- ea: `0x18001defc`
- end: `0x18001e0a9`
- name: `?CheckAndConvertWriteInput@@YAJPEBUCAPABILITIES_LIST_ENTRY@@PEBUtagPROPVARIANT@@PEAU2@PEA_N@Z`
- size: `429`
- prototype: `__int64 __fastcall(const struct CAPABILITIES_LIST_ENTRY *, PROPVARIANT *pvarSrc, struct tagPROPVARIANT *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001c860`
- `0x18001d120`

## callees

- `0x1800084a0`
- `0x18000ab24`
- `0x18000ac88`
- `0x18000bff0`
- `0x18001defc`
- `0x18001e2a0`
- `0x18001e3a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001df8f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001df8f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e067`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e074`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e067`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e074`
- `PROPSYS!PropVariantChangeType` at `0x18001df68`
- `PROPSYS!PropVariantChangeType` at `0x18001df68`
- `PROPSYS!PropVariantGetElementCount` at `0x18001e057`
- `PROPSYS!PropVariantGetElementCount` at `0x18001e057`

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
0x18001defc  mov     [rsp-18h+arg_0], rbx
0x18001df01  mov     [rsp-18h+arg_10], rsi
0x18001df06  push    rbp
0x18001df07  push    rdi
0x18001df08  push    r14
0x18001df0a  mov     rbp, rsp
0x18001df0d  sub     rsp, 50h
0x18001df11  mov     rdi, rcx
0x18001df14  mov     [rbp+arg_8], 0
0x18001df18  xor     ecx, ecx
0x18001df1a  xorps   xmm0, xmm0
0x18001df1d  movups  xmmword ptr [r8], xmm0
0x18001df21  mov     [r8+10h], rcx
0x18001df25  mov     rax, rdx
0x18001df28  mov     qword ptr [rbp+ppropvarDest+10h], rcx
0x18001df2c  mov     r14, r9
0x18001df2f  movzx   r9d, word ptr [rdx]
0x18001df33  mov     rsi, r8
0x18001df36  mov     edx, 0FFFh
0x18001df3b  movzx   ecx, r9w
0x18001df3f  and     cx, dx
0x18001df42  mov     edx, 8
0x18001df47  movups  xmmword ptr [rbp+ppropvarDest], xmm0
0x18001df4b  cmp     dx, cx
0x18001df4e  jnz     short loc_18001DF70
0x18001df50  mov     ecx, 0F01Fh
0x18001df55  xor     r8d, r8d; flags
0x18001df58  and     r9w, cx
0x18001df5c  mov     rdx, rax; propvarSrc
0x18001df5f  or      r9w, 1Fh; vt
0x18001df64  lea     rcx, [rbp+ppropvarDest]; ppropvarDest
0x18001df68  call    cs:__imp_PropVariantChangeType
0x18001df6e  jmp     short loc_18001DF95
0x18001df70  mov     edx, 1Eh
0x18001df75  cmp     dx, cx
0x18001df78  jnz     short loc_18001DF88
0x18001df7a  lea     rdx, [rbp+ppropvarDest]; pvarDest
0x18001df7e  mov     rcx, rax; pvarSrc
0x18001df81  call    ?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18001df86  jmp     short loc_18001DF95
0x18001df88  mov     rdx, rax; pvarSrc
0x18001df8b  lea     rcx, [rbp+ppropvarDest]; pvarDest
0x18001df8f  call    cs:__imp_PropVariantCopy
0x18001df95  mov     ebx, eax
0x18001df97  test    eax, eax
0x18001df99  js      loc_18001E063
0x18001df9f  cmp     dword ptr [rdi+0Ch], 0
0x18001dfa3  jz      short loc_18001DFDA
0x18001dfa5  cmp     dword ptr [rdi+10h], 0
0x18001dfa9  lea     rcx, [rbp+ppropvarDest]; pvarSrc
0x18001dfad  mov     r8d, [rdi+30h]; int
0x18001dfb1  mov     edx, [rdi+2Ch]; int
0x18001dfb4  jz      short loc_18001DFCB
0x18001dfb6  movzx   r9d, word ptr [rdi+34h]; unsigned __int16
0x18001dfbb  lea     rax, [rbp+arg_8]
0x18001dfbf  mov     [rsp+50h+var_30], rax; bool *
0x18001dfc4  call    ?ClipToRange@@YAJPEAUtagPROPVARIANT@@HHGPEA_N@Z; ClipToRange(tagPROPVARIANT *,int,int,ushort,bool *)
0x18001dfc9  jmp     short loc_18001DFD0
0x18001dfcb  call    ?CheckRange@@YAJPEBUtagPROPVARIANT@@HH@Z; CheckRange(tagPROPVARIANT const *,int,int)
0x18001dfd0  mov     ebx, eax
0x18001dfd2  test    eax, eax
0x18001dfd4  js      loc_18001E063
0x18001dfda  xor     eax, eax
0x18001dfdc  lea     r9, [rbp+arg_8]
0x18001dfe0  cmp     [rbp+arg_8], al
0x18001dfe3  lea     rdx, [rbp+ppropvarDest]; struct tagPROPVARIANT *
0x18001dfe7  mov     r8, rsi; struct tagPROPVARIANT *
0x18001dfea  mov     rcx, rdi; struct CAPABILITIES_LIST_ENTRY *
0x18001dfed  cmovnz  r9, rax; bool *
0x18001dff1  call    ?CheckForBadTypesAndCoerceStringVectors@@YAJPEBUCAPABILITIES_LIST_ENTRY@@AEBUtagPROPVARIANT@@PEAU2@PEA_N@Z; CheckForBadTypesAndCoerceStringVectors(CAPABILITIES_LIST_ENTRY const *,tagPROPVARIANT const &,tagPROPVARIANT *,bool *)
0x18001dff6  mov     ebx, eax
0x18001dff8  test    eax, eax
0x18001dffa  js      short loc_18001E063
0x18001dffc  mov     rdx, [rdi+38h]; unsigned __int16 *
0x18001e000  test    rdx, rdx
0x18001e003  jz      short loc_18001E013
0x18001e005  mov     rcx, rsi; struct tagPROPVARIANT *
0x18001e008  call    ?CheckForDisallowedChars@@YAJPEBUtagPROPVARIANT@@PEBG@Z; CheckForDisallowedChars(tagPROPVARIANT const *,ushort const *)
0x18001e00d  mov     ebx, eax
0x18001e00f  test    eax, eax
0x18001e011  js      short loc_18001E063
0x18001e013  movsxd  r10, dword ptr [rdi+24h]
0x18001e017  test    r10d, r10d
0x18001e01a  js      short loc_18001E04D
0x18001e01c  cmp     word ptr [rsi], 1Fh
0x18001e020  jnz     short loc_18001E04D
0x18001e022  mov     rcx, [rsi+8]; unsigned __int16 *
0x18001e026  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x18001e02a  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001e02f  mov     [rbp+arg_18], 0
0x18001e037  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001e03c  test    eax, eax
0x18001e03e  js      short loc_18001E046
0x18001e040  cmp     [rbp+arg_18], r10
0x18001e044  jz      short loc_18001E04D
0x18001e046  mov     ebx, 80028CA1h
0x18001e04b  jmp     short loc_18001E063
0x18001e04d  mov     ebx, [rdi+28h]
0x18001e050  test    ebx, ebx
0x18001e052  js      short loc_18001E061
0x18001e054  mov     rcx, rsi; propvar
0x18001e057  call    cs:__imp_PropVariantGetElementCount
0x18001e05d  cmp     eax, ebx
0x18001e05f  jnz     short loc_18001E046
0x18001e061  xor     ebx, ebx
0x18001e063  lea     rcx, [rbp+ppropvarDest]; pvar
0x18001e067  call    cs:__imp_PropVariantClear
0x18001e06d  test    ebx, ebx
0x18001e06f  jns     short loc_18001E07A
0x18001e071  mov     rcx, rsi; pvar
0x18001e074  call    cs:__imp_PropVariantClear
0x18001e07a  test    r14, r14
0x18001e07d  jz      short loc_18001E092
0x18001e07f  test    ebx, ebx
0x18001e081  js      short loc_18001E08D
0x18001e083  cmp     [rbp+arg_8], 0
0x18001e087  jz      short loc_18001E08D
0x18001e089  mov     al, 1
0x18001e08b  jmp     short loc_18001E08F
0x18001e08d  xor     al, al
0x18001e08f  mov     [r14], al
0x18001e092  lea     r11, [rsp+50h+var_s0]
0x18001e097  mov     eax, ebx
0x18001e099  mov     rbx, [r11+20h]
0x18001e09d  mov     rsi, [r11+30h]
0x18001e0a1  mov     rsp, r11
0x18001e0a4  pop     r14
0x18001e0a6  pop     rdi
0x18001e0a7  pop     rbp
0x18001e0a8  retn
```
