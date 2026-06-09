# ConvertVectorToDelimitedString(tagPROPVARIANT const *,ushort const *,ushort const *,tagPROPVARIANT *)

- ea: `0x18001150c`
- end: `0x1800116fd`
- name: `?ConvertVectorToDelimitedString@@YAJPEBUtagPROPVARIANT@@PEBG1PEAU1@@Z`
- size: `497`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, const unsigned __int16 *, const unsigned __int16 *, PROPVARIANT *pvarDest)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011460`
- `0x180011b20`

## callees

- `0x180007d90`
- `0x18000af20`
- `0x18000bff0`
- `0x18000e364`
- `0x18001150c`
- `0x18001fc18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800116b9`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800116b9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011699`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800116ad`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011699`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800116ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001168e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001168e`

## pseudocode

```c
__int64 __fastcall ConvertVectorToDelimitedString(
        PROPVARIANT *pvarSrc,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        PROPVARIANT *pvarDest)
{
  HRESULT v7; // edi
  __int64 result; // rax
  __int64 v9; // r12
  unsigned int i; // r10d
  int v11; // r10d
  __int64 v12; // r11
  ULONGLONG v13; // r12
  unsigned __int16 *v14; // r15
  int v15; // r10d
  __int64 v16; // rcx
  unsigned __int16 *v17; // rax
  _WORD *v18; // r10
  LPVOID pv; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int64 v20; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int16 *v21; // [rsp+30h] [rbp-10h]
  ULONGLONG pullResult; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int16 *v23; // [rsp+88h] [rbp+48h]

  v23 = a2;
  if ( pvarSrc->vt == 31 )
  {
    PropVariantClear(pvarDest);
    v7 = PropVariantCopy(pvarDest, pvarSrc);
    if ( v7 >= 0 && a3 && (unsigned int)HasDisallowedCharsInString(pvarDest->bstrVal, a3) )
      *v18 = 0;
  }
  else if ( pvarSrc->vt == 4127 )
  {
    v20 = 0;
    result = StringCchLengthW(a2, 0x7FFFFFFFu, &v20);
    if ( (int)result < 0 )
      return result;
    v9 = 0;
    for ( i = 0; ; i = v11 + 1 )
    {
      pullResult = 0;
      if ( i >= pvarSrc->lVal )
        break;
      result = StringCchLengthW(
                 *(const unsigned __int16 **)&pvarSrc->bstrblobVal.pData[8 * i],
                 0x7FFFFFFFu,
                 &pullResult);
      if ( (int)result < 0 )
        return result;
      v9 += v12 + pullResult;
    }
    v13 = v9 + 1;
    v7 = ULongLongMult(v13, 2u, &pullResult);
    if ( v7 >= 0 )
    {
      pv = 0;
      v7 = CoTaskMemAllocWithInit(pullResult, &pv);
      if ( v7 >= 0 )
      {
        v14 = (unsigned __int16 *)pv;
        v15 = 0;
        v16 = 0;
        LODWORD(pullResult) = 0;
        LODWORD(pv) = 0;
        *v14 = 0;
        if ( pvarSrc->lVal )
        {
          while ( v7 >= 0 )
          {
            v17 = *(unsigned __int16 **)&pvarSrc->bstrblobVal.pData[8 * v16];
            v21 = v17;
            if ( !a3 || !(unsigned int)HasDisallowedCharsInString(v17, a3) )
            {
              if ( v15 && v20 && (v7 = StringCchCatW(v14, v13, v23), v7 < 0)
                || (v7 = StringCchCatW(v14, v13, v21), v7 < 0) )
              {
                v15 = pullResult;
              }
              else
              {
                v15 = pullResult + 1;
                LODWORD(pullResult) = pullResult + 1;
              }
            }
            v16 = (unsigned int)((_DWORD)pv + 1);
            LODWORD(pv) = v16;
            if ( (unsigned int)v16 >= pvarSrc->lVal )
            {
              if ( v7 >= 0 )
                goto LABEL_24;
              break;
            }
          }
          CoTaskMemFree(v14);
        }
        else
        {
LABEL_24:
          PropVariantClear(pvarDest);
          pvarDest->vt = 31;
          pvarDest->hVal.QuadPart = (LONGLONG)v14;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001150c  mov     [rsp-38h+arg_10], rbx
0x180011511  mov     [rsp-38h+arg_8], rdx
0x180011516  push    rbp
0x180011517  push    rsi
0x180011518  push    rdi
0x180011519  push    r12
0x18001151b  push    r13
0x18001151d  push    r14
0x18001151f  push    r15
0x180011521  mov     rbp, rsp
0x180011524  sub     rsp, 40h
0x180011528  mov     r14, rcx
0x18001152b  mov     rsi, r9
0x18001152e  mov     ecx, 1Fh
0x180011533  mov     r13, r8
0x180011536  mov     rax, rdx
0x180011539  cmp     [r14], cx
0x18001153d  jz      loc_1800116AA
0x180011543  mov     ecx, 101Fh
0x180011548  cmp     [r14], cx
0x18001154c  jz      short loc_180011558
0x18001154e  mov     edi, 80070057h
0x180011553  jmp     loc_1800116E3
0x180011558  mov     edi, 7FFFFFFFh
0x18001155d  lea     r8, [rbp+var_18]; unsigned __int64 *
0x180011561  xor     ebx, ebx
0x180011563  mov     edx, edi; unsigned __int64
0x180011565  mov     rcx, rax; unsigned __int16 *
0x180011568  mov     [rbp+var_18], rbx
0x18001156c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180011571  test    eax, eax
0x180011573  js      loc_1800116E5
0x180011579  mov     r11, [rbp+var_18]
0x18001157d  mov     r12d, ebx
0x180011580  mov     r10d, ebx
0x180011583  lea     r8, [rbp+pullResult]; unsigned __int64 *
0x180011587  mov     [rbp+pullResult], rbx
0x18001158b  cmp     r10d, [r14+8]
0x18001158f  jnb     short loc_1800115BB
0x180011591  mov     rcx, [r14+10h]
0x180011595  mov     rdx, rdi; unsigned __int64
0x180011598  mov     eax, r10d
0x18001159b  mov     rcx, [rcx+rax*8]; unsigned __int16 *
0x18001159f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800115a4  test    eax, eax
0x1800115a6  js      loc_1800116E5
0x1800115ac  mov     rcx, [rbp+pullResult]
0x1800115b0  add     rcx, r11
0x1800115b3  add     r12, rcx
0x1800115b6  inc     r10d
0x1800115b9  jmp     short loc_180011583
0x1800115bb  inc     r12
0x1800115be  mov     edx, 2; ullMultiplier
0x1800115c3  mov     rcx, r12; ullMultiplicand
0x1800115c6  call    ULongLongMult
0x1800115cb  mov     edi, eax
0x1800115cd  test    eax, eax
0x1800115cf  js      loc_1800116E3
0x1800115d5  mov     rcx, [rbp+pullResult]; Size
0x1800115d9  lea     rdx, [rbp+pv]; void **
0x1800115dd  mov     [rbp+pv], rbx
0x1800115e1  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x1800115e6  mov     edi, eax
0x1800115e8  test    eax, eax
0x1800115ea  js      loc_1800116E3
0x1800115f0  mov     r15, [rbp+pv]
0x1800115f4  mov     r10d, ebx
0x1800115f7  mov     ecx, ebx
0x1800115f9  mov     dword ptr [rbp+pullResult], ebx
0x1800115fc  mov     dword ptr [rbp+pv], ecx
0x1800115ff  mov     [r15], bx
0x180011603  cmp     [r14+8], ebx
0x180011607  jbe     loc_180011696
0x18001160d  test    edi, edi
0x18001160f  js      short loc_18001168B
0x180011611  mov     rax, [r14+10h]
0x180011615  mov     rax, [rax+rcx*8]
0x180011619  mov     [rbp+var_10], rax
0x18001161d  test    r13, r13
0x180011620  jz      short loc_180011631
0x180011622  mov     rdx, r13; unsigned __int16 *
0x180011625  mov     rcx, rax; unsigned __int16 *
0x180011628  call    ?HasDisallowedCharsInString@@YAHPEBG0@Z; HasDisallowedCharsInString(ushort const *,ushort const *)
0x18001162d  test    eax, eax
0x18001162f  jnz     short loc_180011677
0x180011631  test    r10d, r10d
0x180011634  jz      short loc_180011651
0x180011636  cmp     [rbp+var_18], rbx
0x18001163a  jz      short loc_180011651
0x18001163c  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x180011640  mov     rdx, r12; unsigned __int64
0x180011643  mov     rcx, r15; unsigned __int16 *
0x180011646  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001164b  mov     edi, eax
0x18001164d  test    eax, eax
0x18001164f  js      short loc_180011673
0x180011651  mov     r8, [rbp+var_10]; unsigned __int16 *
0x180011655  mov     rdx, r12; unsigned __int64
0x180011658  mov     rcx, r15; unsigned __int16 *
0x18001165b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011660  mov     edi, eax
0x180011662  test    eax, eax
0x180011664  js      short loc_180011673
0x180011666  mov     r10d, dword ptr [rbp+pullResult]
0x18001166a  inc     r10d
0x18001166d  mov     dword ptr [rbp+pullResult], r10d
0x180011671  jmp     short loc_180011677
0x180011673  mov     r10d, dword ptr [rbp+pullResult]
0x180011677  mov     ecx, dword ptr [rbp+pv]
0x18001167a  mov     eax, edi
0x18001167c  inc     ecx
0x18001167e  mov     dword ptr [rbp+pv], ecx
0x180011681  cmp     ecx, [r14+8]
0x180011685  jb      short loc_18001160D
0x180011687  test    eax, eax
0x180011689  jns     short loc_180011696
0x18001168b  mov     rcx, r15; pv
0x18001168e  call    cs:__imp_CoTaskMemFree
0x180011694  jmp     short loc_1800116E3
0x180011696  mov     rcx, rsi; pvar
0x180011699  call    cs:__imp_PropVariantClear
0x18001169f  mov     word ptr [rsi], 1Fh
0x1800116a4  mov     [rsi+8], r15
0x1800116a8  jmp     short loc_1800116E3
0x1800116aa  mov     rcx, rsi; pvar
0x1800116ad  call    cs:__imp_PropVariantClear
0x1800116b3  mov     rdx, r14; pvarSrc
0x1800116b6  mov     rcx, rsi; pvarDest
0x1800116b9  call    cs:__imp_PropVariantCopy
0x1800116bf  xor     ebx, ebx
0x1800116c1  mov     edi, eax
0x1800116c3  test    eax, eax
0x1800116c5  js      short loc_1800116E3
0x1800116c7  test    r13, r13
0x1800116ca  jz      short loc_1800116E3
0x1800116cc  mov     r10, [rsi+8]
0x1800116d0  mov     rdx, r13; unsigned __int16 *
0x1800116d3  mov     rcx, r10; unsigned __int16 *
0x1800116d6  call    ?HasDisallowedCharsInString@@YAHPEBG0@Z; HasDisallowedCharsInString(ushort const *,ushort const *)
0x1800116db  test    eax, eax
0x1800116dd  jz      short loc_1800116E3
0x1800116df  mov     [r10], bx
0x1800116e3  mov     eax, edi
0x1800116e5  mov     rbx, [rsp+40h+arg_10]
0x1800116ed  add     rsp, 40h
0x1800116f1  pop     r15
0x1800116f3  pop     r14
0x1800116f5  pop     r13
0x1800116f7  pop     r12
0x1800116f9  pop     rdi
0x1800116fa  pop     rsi
0x1800116fb  pop     rbp
0x1800116fc  retn
```
