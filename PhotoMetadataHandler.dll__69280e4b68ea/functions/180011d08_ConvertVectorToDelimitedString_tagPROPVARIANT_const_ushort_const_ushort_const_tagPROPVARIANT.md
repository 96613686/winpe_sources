# ConvertVectorToDelimitedString(tagPROPVARIANT const *,ushort const *,ushort const *,tagPROPVARIANT *)

- ea: `0x180011d08`
- end: `0x180011f12`
- name: `?ConvertVectorToDelimitedString@@YAJPEBUtagPROPVARIANT@@PEBG1PEAU1@@Z`
- size: `522`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, const unsigned __int16 *, const unsigned __int16 *, PROPVARIANT *pvarDest)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011c50`
- `0x180012370`

## callees

- `0x1800096a0`
- `0x18000ab60`
- `0x18000c5a0`
- `0x18000ea14`
- `0x180011d08`
- `0x180020bd4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180011ec7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180011ec7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011e9b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011eb5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011e9b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011eb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011e8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011e8a`

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
0x180011d08  mov     [rsp-38h+arg_10], rbx
0x180011d0d  mov     [rsp-38h+arg_8], rdx
0x180011d12  push    rbp
0x180011d13  push    rsi
0x180011d14  push    rdi
0x180011d15  push    r12
0x180011d17  push    r13
0x180011d19  push    r14
0x180011d1b  push    r15
0x180011d1d  mov     rbp, rsp
0x180011d20  sub     rsp, 40h
0x180011d24  mov     r14, rcx
0x180011d27  mov     rsi, r9
0x180011d2a  mov     ecx, 1Fh
0x180011d2f  mov     r13, r8
0x180011d32  mov     rax, rdx
0x180011d35  cmp     [r14], cx
0x180011d39  jz      loc_180011EB2
0x180011d3f  mov     ecx, 101Fh
0x180011d44  cmp     [r14], cx
0x180011d48  jz      short loc_180011D54
0x180011d4a  mov     edi, 80070057h
0x180011d4f  jmp     loc_180011EF7
0x180011d54  mov     edi, 7FFFFFFFh
0x180011d59  lea     r8, [rbp+var_18]; unsigned __int64 *
0x180011d5d  xor     ebx, ebx
0x180011d5f  mov     edx, edi; unsigned __int64
0x180011d61  mov     rcx, rax; unsigned __int16 *
0x180011d64  mov     [rbp+var_18], rbx
0x180011d68  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180011d6d  test    eax, eax
0x180011d6f  js      loc_180011EF9
0x180011d75  mov     r11, [rbp+var_18]
0x180011d79  mov     r12d, ebx
0x180011d7c  mov     r10d, ebx
0x180011d7f  lea     r8, [rbp+pullResult]; unsigned __int64 *
0x180011d83  mov     [rbp+pullResult], rbx
0x180011d87  cmp     r10d, [r14+8]
0x180011d8b  jnb     short loc_180011DB7
0x180011d8d  mov     rcx, [r14+10h]
0x180011d91  mov     rdx, rdi; unsigned __int64
0x180011d94  mov     eax, r10d
0x180011d97  mov     rcx, [rcx+rax*8]; unsigned __int16 *
0x180011d9b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180011da0  test    eax, eax
0x180011da2  js      loc_180011EF9
0x180011da8  mov     rcx, [rbp+pullResult]
0x180011dac  add     rcx, r11
0x180011daf  add     r12, rcx
0x180011db2  inc     r10d
0x180011db5  jmp     short loc_180011D7F
0x180011db7  inc     r12
0x180011dba  mov     edx, 2; ullMultiplier
0x180011dbf  mov     rcx, r12; ullMultiplicand
0x180011dc2  call    ULongLongMult
0x180011dc7  mov     edi, eax
0x180011dc9  test    eax, eax
0x180011dcb  js      loc_180011EF7
0x180011dd1  mov     rcx, [rbp+pullResult]; Size
0x180011dd5  lea     rdx, [rbp+pv]; void **
0x180011dd9  mov     [rbp+pv], rbx
0x180011ddd  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180011de2  mov     edi, eax
0x180011de4  test    eax, eax
0x180011de6  js      loc_180011EF7
0x180011dec  mov     r15, [rbp+pv]
0x180011df0  mov     r10d, ebx
0x180011df3  mov     ecx, ebx
0x180011df5  mov     dword ptr [rbp+pullResult], ebx
0x180011df8  mov     dword ptr [rbp+pv], ecx
0x180011dfb  mov     [r15], bx
0x180011dff  cmp     [r14+8], ebx
0x180011e03  jbe     loc_180011E98
0x180011e09  test    edi, edi
0x180011e0b  js      short loc_180011E87
0x180011e0d  mov     rax, [r14+10h]
0x180011e11  mov     rax, [rax+rcx*8]
0x180011e15  mov     [rbp+var_10], rax
0x180011e19  test    r13, r13
0x180011e1c  jz      short loc_180011E2D
0x180011e1e  mov     rdx, r13; unsigned __int16 *
0x180011e21  mov     rcx, rax; unsigned __int16 *
0x180011e24  call    ?HasDisallowedCharsInString@@YAHPEBG0@Z; HasDisallowedCharsInString(ushort const *,ushort const *)
0x180011e29  test    eax, eax
0x180011e2b  jnz     short loc_180011E73
0x180011e2d  test    r10d, r10d
0x180011e30  jz      short loc_180011E4D
0x180011e32  cmp     [rbp+var_18], rbx
0x180011e36  jz      short loc_180011E4D
0x180011e38  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x180011e3c  mov     rdx, r12; unsigned __int64
0x180011e3f  mov     rcx, r15; unsigned __int16 *
0x180011e42  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011e47  mov     edi, eax
0x180011e49  test    eax, eax
0x180011e4b  js      short loc_180011E6F
0x180011e4d  mov     r8, [rbp+var_10]; unsigned __int16 *
0x180011e51  mov     rdx, r12; unsigned __int64
0x180011e54  mov     rcx, r15; unsigned __int16 *
0x180011e57  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011e5c  mov     edi, eax
0x180011e5e  test    eax, eax
0x180011e60  js      short loc_180011E6F
0x180011e62  mov     r10d, dword ptr [rbp+pullResult]
0x180011e66  inc     r10d
0x180011e69  mov     dword ptr [rbp+pullResult], r10d
0x180011e6d  jmp     short loc_180011E73
0x180011e6f  mov     r10d, dword ptr [rbp+pullResult]
0x180011e73  mov     ecx, dword ptr [rbp+pv]
0x180011e76  mov     eax, edi
0x180011e78  inc     ecx
0x180011e7a  mov     dword ptr [rbp+pv], ecx
0x180011e7d  cmp     ecx, [r14+8]
0x180011e81  jb      short loc_180011E09
0x180011e83  test    eax, eax
0x180011e85  jns     short loc_180011E98
0x180011e87  mov     rcx, r15; pv
0x180011e8a  call    cs:__imp_CoTaskMemFree
0x180011e91  nop     dword ptr [rax+rax+00h]
0x180011e96  jmp     short loc_180011EF7
0x180011e98  mov     rcx, rsi; pvar
0x180011e9b  call    cs:__imp_PropVariantClear
0x180011ea2  nop     dword ptr [rax+rax+00h]
0x180011ea7  mov     word ptr [rsi], 1Fh
0x180011eac  mov     [rsi+8], r15
0x180011eb0  jmp     short loc_180011EF7
0x180011eb2  mov     rcx, rsi; pvar
0x180011eb5  call    cs:__imp_PropVariantClear
0x180011ebc  nop     dword ptr [rax+rax+00h]
0x180011ec1  mov     rdx, r14; pvarSrc
0x180011ec4  mov     rcx, rsi; pvarDest
0x180011ec7  call    cs:__imp_PropVariantCopy
0x180011ece  nop     dword ptr [rax+rax+00h]
0x180011ed3  xor     ebx, ebx
0x180011ed5  mov     edi, eax
0x180011ed7  test    eax, eax
0x180011ed9  js      short loc_180011EF7
0x180011edb  test    r13, r13
0x180011ede  jz      short loc_180011EF7
0x180011ee0  mov     r10, [rsi+8]
0x180011ee4  mov     rdx, r13; unsigned __int16 *
0x180011ee7  mov     rcx, r10; unsigned __int16 *
0x180011eea  call    ?HasDisallowedCharsInString@@YAHPEBG0@Z; HasDisallowedCharsInString(ushort const *,ushort const *)
0x180011eef  test    eax, eax
0x180011ef1  jz      short loc_180011EF7
0x180011ef3  mov     [r10], bx
0x180011ef7  mov     eax, edi
0x180011ef9  mov     rbx, [rsp+40h+arg_10]
0x180011f01  add     rsp, 40h
0x180011f05  pop     r15
0x180011f07  pop     r14
0x180011f09  pop     r13
0x180011f0b  pop     r12
0x180011f0d  pop     rdi
0x180011f0e  pop     rsi
0x180011f0f  pop     rbp
0x180011f10  retn
```
