# IISTypeToVarTypeCopyIISSynIdBinary(_iistype *,tagVARIANT *,int)

- ea: `0x18001883c`
- end: `0x1800189b6`
- name: `?IISTypeToVarTypeCopyIISSynIdBinary@@YAJPEAU_iistype@@PEAUtagVARIANT@@H@Z`
- size: `378`
- prototype: `__int64 __fastcall(struct _iistype *, struct tagVARIANT *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180018518`

## callees

- `0x18001883c`
- `0x18001beb8`
- `0x18001d652`
- `0x18001d6c0`

## import_xrefs

- `msvcrt!_itow` at `0x180018944`
- `msvcrt!_itow` at `0x180018944`
- `OLEAUT32!__imp_VariantInit` at `0x18001891f`
- `OLEAUT32!__imp_VariantInit` at `0x18001891f`
- `OLEAUT32!__imp_VariantClear` at `0x180018974`
- `OLEAUT32!__imp_VariantClear` at `0x180018974`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180018899`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180018899`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001898b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001898b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800188b8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800188b8`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800188e0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800188e0`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180018968`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180018968`

## pseudocode

```c
__int64 __fastcall IISTypeToVarTypeCopyIISSynIdBinary(struct _iistype *a1, struct tagVARIANT *a2, int a3)
{
  ULONG v3; // eax
  VARTYPE v7; // cx
  SAFEARRAY *v8; // rax
  SAFEARRAY *v9; // rbx
  HRESULT v10; // edi
  ULONG i; // eax
  LONG rgIndices; // [rsp+20h] [rbp-60h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+28h] [rbp-58h] BYREF
  void *ppvData; // [rsp+30h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-48h] BYREF
  wchar_t Buffer[20]; // [rsp+50h] [rbp-30h] BYREF

  v3 = *((_DWORD *)a1 + 2);
  ppvData = 0;
  rgIndices = 0;
  rgsabound.lLbound = 0;
  rgsabound.cElements = v3;
  v7 = 12;
  if ( !a3 )
    v7 = 17;
  v8 = SafeArrayCreate(v7, 1u, &rgsabound);
  v9 = v8;
  if ( v8 )
  {
    v10 = SafeArrayAccessData(v8, &ppvData);
    if ( v10 < 0 )
    {
LABEL_14:
      SafeArrayDestroy(v9);
    }
    else
    {
      if ( a3 )
      {
        rgIndices = 0;
        for ( i = 0; i < rgsabound.cElements; i = ++rgIndices )
        {
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          pvarg.vt = 8;
          _itow(*(unsigned __int8 *)(*((_QWORD *)a1 + 2) + rgIndices), Buffer, 16);
          v10 = ADsAllocString(Buffer, &pvarg.decVal.Lo32);
          if ( v10 < 0 )
            goto LABEL_14;
          v10 = SafeArrayPutElement(v9, &rgIndices, &pvarg);
          VariantClear(&pvarg);
          if ( v10 < 0 )
            goto LABEL_14;
        }
      }
      else
      {
        memcpy_0(ppvData, *((const void **)a1 + 2), rgsabound.cElements);
      }
      SafeArrayUnaccessData(v9);
      a2->vt = a3 != 0 ? 8204 : 8209;
      a2->llVal = (LONGLONG)v9;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001883c  mov     [rsp-28h+arg_10], rbx
0x180018841  push    rbp
0x180018842  push    rsi
0x180018843  push    rdi
0x180018844  push    r14
0x180018846  push    r15
0x180018848  mov     rbp, rsp
0x18001884b  sub     rsp, 80h
0x180018852  mov     rax, cs:__security_cookie
0x180018859  xor     rax, rsp
0x18001885c  mov     [rbp+var_8], rax
0x180018860  mov     eax, [rcx+8]
0x180018863  mov     r15, rdx
0x180018866  mov     edx, 1; cDims
0x18001886b  mov     [rbp+ppvData], 0
0x180018873  mov     esi, r8d
0x180018876  mov     [rbp+rgIndices], 0
0x18001887d  mov     r14, rcx
0x180018880  mov     [rbp+rgsabound.lLbound], 0
0x180018887  test    r8d, r8d
0x18001888a  mov     [rbp+rgsabound.cElements], eax
0x18001888d  lea     ecx, [rdx+0Bh]
0x180018890  lea     r8, [rbp+rgsabound]; rgsabound
0x180018894  jnz     short loc_180018899
0x180018896  lea     ecx, [rdx+10h]; vt
0x180018899  call    cs:__imp_SafeArrayCreate
0x18001889f  mov     rbx, rax
0x1800188a2  test    rax, rax
0x1800188a5  jnz     short loc_1800188B1
0x1800188a7  mov     edi, 8007000Eh
0x1800188ac  jmp     loc_180018991
0x1800188b1  lea     rdx, [rbp+ppvData]; ppvData
0x1800188b5  mov     rcx, rbx; psa
0x1800188b8  call    cs:__imp_SafeArrayAccessData
0x1800188be  mov     edi, eax
0x1800188c0  test    eax, eax
0x1800188c2  js      loc_180018988
0x1800188c8  test    esi, esi
0x1800188ca  jnz     short loc_180018900
0x1800188cc  mov     r8d, [rbp+rgsabound.cElements]; Size
0x1800188d0  mov     rdx, [r14+10h]; Src
0x1800188d4  mov     rcx, [rbp+ppvData]; void *
0x1800188d8  call    memcpy_0
0x1800188dd  mov     rcx, rbx; psa
0x1800188e0  call    cs:__imp_SafeArrayUnaccessData
0x1800188e6  neg     esi
0x1800188e8  sbb     ax, ax
0x1800188eb  and     ax, 0FFFBh
0x1800188ef  add     ax, 2011h
0x1800188f3  mov     [r15], ax
0x1800188f7  mov     [r15+8], rbx
0x1800188fb  jmp     loc_180018991
0x180018900  mov     [rbp+rgIndices], 0
0x180018907  xor     eax, eax
0x180018909  cmp     eax, [rbp+rgsabound.cElements]
0x18001890c  jnb     short loc_1800188DD
0x18001890e  xorps   xmm0, xmm0
0x180018911  lea     rcx, [rbp+pvarg]; pvarg
0x180018915  xor     eax, eax
0x180018917  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001891b  mov     qword ptr [rbp+pvarg+10h], rax
0x18001891f  call    cs:__imp_VariantInit
0x180018925  movsxd  rcx, [rbp+rgIndices]
0x180018929  lea     rdx, [rbp+Buffer]; Buffer
0x18001892d  mov     eax, 8
0x180018932  mov     r8d, 10h; Radix
0x180018938  mov     word ptr [rbp+pvarg], ax
0x18001893c  mov     rax, [r14+10h]
0x180018940  movzx   ecx, byte ptr [rax+rcx]; Value
0x180018944  call    cs:__imp__itow
0x18001894a  lea     rdx, [rbp+pvarg+8]
0x18001894e  lea     rcx, [rbp+Buffer]
0x180018952  call    ADsAllocString
0x180018957  mov     edi, eax
0x180018959  test    eax, eax
0x18001895b  js      short loc_180018988
0x18001895d  lea     r8, [rbp+pvarg]; pv
0x180018961  mov     rcx, rbx; psa
0x180018964  lea     rdx, [rbp+rgIndices]; rgIndices
0x180018968  call    cs:__imp_SafeArrayPutElement
0x18001896e  lea     rcx, [rbp+pvarg]; pvarg
0x180018972  mov     edi, eax
0x180018974  call    cs:__imp_VariantClear
0x18001897a  test    edi, edi
0x18001897c  js      short loc_180018988
0x18001897e  mov     eax, [rbp+rgIndices]
0x180018981  inc     eax
0x180018983  mov     [rbp+rgIndices], eax
0x180018986  jmp     short loc_180018909
0x180018988  mov     rcx, rbx; psa
0x18001898b  call    cs:__imp_SafeArrayDestroy
0x180018991  mov     eax, edi
0x180018993  mov     rcx, [rbp+var_8]
0x180018997  xor     rcx, rsp; StackCookie
0x18001899a  call    __security_check_cookie
0x18001899f  mov     rbx, [rsp+80h+arg_10]
0x1800189a7  add     rsp, 80h
0x1800189ae  pop     r15
0x1800189b0  pop     r14
0x1800189b2  pop     rdi
0x1800189b3  pop     rsi
0x1800189b4  pop     rbp
0x1800189b5  retn
```
