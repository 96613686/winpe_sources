# CMetadataIPTCReaderWriter::IPTCCoerceVariantToPWSZSTR(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x1800d9e00`
- end: `0x1800d9f3d`
- name: `?IPTCCoerceVariantToPWSZSTR@CMetadataIPTCReaderWriter@@AEAAJPEBUtagPROPVARIANT@@PEAU2@@Z`
- size: `317`
- prototype: `__int64 __fastcall(CMetadataIPTCReaderWriter *this, const VARIANTARG *, PROPVARIANT *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d9c9c`

## callees

- `0x180087ee0`
- `0x1800bd9d4`
- `0x1800d9e00`
- `0x18017e438`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800d9e2e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800d9e2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d9ee2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d9ee2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800d9f25`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800d9f25`
- `OLEAUT32!__imp_SysStringLen` at `0x1800d9ecb`
- `OLEAUT32!__imp_SysStringLen` at `0x1800d9ecb`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800d9ea3`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800d9ea3`

## pseudocode

```c
__int64 __fastcall CMetadataIPTCReaderWriter::IPTCCoerceVariantToPWSZSTR(
        CMetadataIPTCReaderWriter *this,
        const VARIANTARG *a2,
        PROPVARIANT *a3,
        int a4)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  const CHAR *pcVal; // rcx
  int v8; // ecx
  SIZE_T v9; // rsi
  void *v10; // rax
  VARIANTARG pvargDest; // [rsp+20h] [rbp-48h] BYREF

  *(_OWORD *)a3 = 0;
  a3[2] = 0;
  memset(&pvargDest, 0, sizeof(pvargDest));
  if ( a2->vt != 31 )
  {
    if ( a2->vt == 30 )
    {
      pcVal = a2->pcVal;
      v6 = 0;
      if ( pcVal )
      {
        v5 = CoerceAnsiStrToWideStr(pcVal, (unsigned __int16 **)a3 + 1, (unsigned int)a3, a4);
        v6 = v5;
        if ( v5 < 0 )
        {
          if ( !(_DWORD)g_doStackCaptures )
            goto LABEL_20;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v5 = VariantChangeType(&pvargDest, a2, 0, 8u);
      v6 = v5;
      if ( v5 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_20;
        goto LABEL_12;
      }
      v9 = 2 * SysStringLen(pvargDest.bstrVal) + 2;
      v10 = CoTaskMemAlloc(v9);
      a3[1] = v10;
      if ( !v10 )
      {
        v6 = -2147024882;
        if ( (_DWORD)g_doStackCaptures )
        {
          v8 = -2147024882;
          goto LABEL_17;
        }
        goto LABEL_20;
      }
      memcpy_0(v10, pvargDest.bstrVal, v9);
    }
    *(_WORD *)a3 = 31;
    goto LABEL_20;
  }
  v5 = PropVariantCopy(a3, (const PROPVARIANT *)a2);
  v6 = v5;
  if ( v5 < 0 && (_DWORD)g_doStackCaptures )
  {
LABEL_12:
    v8 = v5;
LABEL_17:
    DoStackCapture(v8);
  }
LABEL_20:
  PropVariantClear((PROPVARIANT *)&pvargDest);
  return v6;
}

```

## disassembly

```asm
0x1800d9e00  push    rbx
0x1800d9e02  push    rbp
0x1800d9e03  push    rsi
0x1800d9e04  push    rdi
0x1800d9e05  sub     rsp, 48h
0x1800d9e09  xor     eax, eax
0x1800d9e0b  xorps   xmm0, xmm0
0x1800d9e0e  movups  xmmword ptr [r8], xmm0
0x1800d9e12  mov     [r8+10h], rax
0x1800d9e16  mov     rdi, r8
0x1800d9e19  movups  xmmword ptr [rsp+68h+pvargDest], xmm0
0x1800d9e1e  lea     ebp, [rax+1Fh]
0x1800d9e21  mov     qword ptr [rsp+68h+pvargDest+10h], rax
0x1800d9e26  cmp     bp, [rdx]
0x1800d9e29  jnz     short loc_1800D9E53
0x1800d9e2b  mov     rcx, r8; pvarDest
0x1800d9e2e  call    cs:__imp_PropVariantCopy
0x1800d9e35  nop     dword ptr [rax+rax+00h]
0x1800d9e3a  mov     ebx, eax
0x1800d9e3c  test    eax, eax
0x1800d9e3e  jns     loc_1800D9F20
0x1800d9e44  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d9e4b  jz      loc_1800D9F20
0x1800d9e51  jmp     short loc_1800D9EBE
0x1800d9e53  mov     eax, 1Eh
0x1800d9e58  cmp     ax, [rdx]
0x1800d9e5b  jnz     short loc_1800D9E95
0x1800d9e5d  mov     rcx, [rdx+8]; lpMultiByteStr
0x1800d9e61  xor     ebx, ebx
0x1800d9e63  test    rcx, rcx
0x1800d9e66  jz      loc_1800D9F1D
0x1800d9e6c  lea     rdx, [r8+8]; unsigned __int16 **
0x1800d9e70  call    ?CoerceAnsiStrToWideStr@@YAJPEBDPEAPEAGIH@Z; CoerceAnsiStrToWideStr(char const *,ushort * *,uint,int)
0x1800d9e75  mov     ebx, eax
0x1800d9e77  test    eax, eax
0x1800d9e79  jns     loc_1800D9F1D
0x1800d9e7f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d9e86  jnz     short loc_1800D9EBE
0x1800d9e88  test    eax, eax
0x1800d9e8a  js      loc_1800D9F20
0x1800d9e90  jmp     loc_1800D9F1D
0x1800d9e95  mov     r9d, 8; vt
0x1800d9e9b  lea     rcx, [rsp+68h+pvargDest]; pvargDest
0x1800d9ea0  xor     r8d, r8d; wFlags
0x1800d9ea3  call    cs:__imp_VariantChangeType
0x1800d9eaa  nop     dword ptr [rax+rax+00h]
0x1800d9eaf  mov     ebx, eax
0x1800d9eb1  test    eax, eax
0x1800d9eb3  jns     short loc_1800D9EC6
0x1800d9eb5  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d9ebc  jz      short loc_1800D9EC2
0x1800d9ebe  mov     ecx, eax
0x1800d9ec0  jmp     short loc_1800D9F06
0x1800d9ec2  test    eax, eax
0x1800d9ec4  js      short loc_1800D9F20
0x1800d9ec6  mov     rcx, qword ptr [rsp+68h+pvargDest+8]; pbstr
0x1800d9ecb  call    cs:__imp_SysStringLen
0x1800d9ed2  nop     dword ptr [rax+rax+00h]
0x1800d9ed7  lea     eax, ds:2[rax*2]
0x1800d9ede  mov     ecx, eax; cb
0x1800d9ee0  mov     esi, eax
0x1800d9ee2  call    cs:__imp_CoTaskMemAlloc
0x1800d9ee9  nop     dword ptr [rax+rax+00h]
0x1800d9eee  mov     [rdi+8], rax
0x1800d9ef2  test    rax, rax
0x1800d9ef5  jnz     short loc_1800D9F0D
0x1800d9ef7  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800d9efd  mov     ebx, 8007000Eh
0x1800d9f02  jz      short loc_1800D9F20
0x1800d9f04  mov     ecx, ebx; int
0x1800d9f06  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d9f0b  jmp     short loc_1800D9F20
0x1800d9f0d  mov     rdx, qword ptr [rsp+68h+pvargDest+8]; Src
0x1800d9f12  mov     r8, rsi; Size
0x1800d9f15  mov     rcx, rax; void *
0x1800d9f18  call    memcpy_0
0x1800d9f1d  mov     [rdi], bp
0x1800d9f20  lea     rcx, [rsp+68h+pvargDest]; pvar
0x1800d9f25  call    cs:__imp_PropVariantClear
0x1800d9f2c  nop     dword ptr [rax+rax+00h]
0x1800d9f31  mov     eax, ebx
0x1800d9f33  add     rsp, 48h
0x1800d9f37  pop     rdi
0x1800d9f38  pop     rsi
0x1800d9f39  pop     rbp
0x1800d9f3a  pop     rbx
0x1800d9f3b  retn
```
