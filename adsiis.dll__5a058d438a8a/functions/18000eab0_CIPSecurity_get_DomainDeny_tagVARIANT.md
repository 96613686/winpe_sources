# CIPSecurity::get_DomainDeny(tagVARIANT *)

- ea: `0x18000eab0`
- end: `0x18000ebf1`
- name: `?get_DomainDeny@CIPSecurity@@UEAAJPEAUtagVARIANT@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(CIPSecurity *__hidden this, VARIANTARG *pvarg)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e528`
- `0x18000eab0`
- `0x18001beb8`
- `0x18001cfcc`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000eaf0`
- `OLEAUT32!__imp_VariantInit` at `0x18000eb4c`
- `OLEAUT32!__imp_VariantInit` at `0x18000eaf0`
- `OLEAUT32!__imp_VariantInit` at `0x18000eb4c`
- `OLEAUT32!__imp_VariantClear` at `0x18000ebae`
- `OLEAUT32!__imp_VariantClear` at `0x18000ebae`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000eb0d`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000eb0d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000ebc8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000ebc8`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000eba2`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000eba2`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000eb8d`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000eb8d`

## pseudocode

```c
__int64 __fastcall CIPSecurity::get_DomainDeny(CIPSecurity *this, VARIANTARG *pvarg)
{
  __int64 result; // rax
  signed int NbName; // r14d
  SAFEARRAY *v6; // rsi
  HRESULT v7; // ebx
  LONG i; // eax
  VARIANTARG pvarga; // [rsp+30h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+88h] [rbp+38h] BYREF
  LPVOID pMem; // [rsp+90h] [rbp+40h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+98h] [rbp+48h] BYREF

  if ( !pvarg )
    return 2147500035LL;
  rgIndices = 0;
  NbName = ADDRESS_CHECK::GetNbName((CIPSecurity *)((char *)this + 24), 0);
  VariantInit(pvarg);
  rgsabound.lLbound = 0;
  rgsabound.cElements = NbName;
  v6 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  if ( v6 )
  {
    rgIndices = 0;
    for ( i = 0; i < NbName; i = ++rgIndices )
    {
      memset(&pvarga, 0, sizeof(pvarga));
      pMem = 0;
      VariantInit(&pvarga);
      pvarga.vt = 8;
      CIPSecurity::GetEntry(this, 0, 0, (unsigned __int8 **)&pMem, rgIndices);
      v7 = ADsAllocString(pMem, &pvarga.decVal.Lo32);
      if ( pMem )
        FreeADsMem(pMem);
      if ( v7 >= 0 )
      {
        v7 = SafeArrayPutElement(v6, &rgIndices, &pvarga);
        VariantClear(&pvarga);
        if ( v7 >= 0 )
          continue;
      }
      SafeArrayDestroy(v6);
      return (unsigned int)v7;
    }
    pvarg->vt = 8204;
    result = 0;
    pvarg->llVal = (LONGLONG)v6;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return result;
}

```

## disassembly

```asm
0x18000eab0  mov     [rsp-28h+arg_0], rbx
0x18000eab5  push    rbp
0x18000eab6  push    rsi
0x18000eab7  push    rdi
0x18000eab8  push    r13
0x18000eaba  push    r14
0x18000eabc  mov     rbp, rsp
0x18000eabf  sub     rsp, 50h
0x18000eac3  mov     rdi, rdx
0x18000eac6  mov     r13, rcx
0x18000eac9  test    rdx, rdx
0x18000eacc  jnz     short loc_18000EAD8
0x18000eace  mov     eax, 80004003h
0x18000ead3  jmp     loc_18000EBDD
0x18000ead8  add     rcx, 18h; this
0x18000eadc  mov     [rbp+rgIndices], 0
0x18000eae3  xor     edx, edx; int
0x18000eae5  call    ?GetNbName@ADDRESS_CHECK@@QEAAKH@Z; ADDRESS_CHECK::GetNbName(int)
0x18000eaea  mov     rcx, rdi; pvarg
0x18000eaed  mov     r14d, eax
0x18000eaf0  call    cs:__imp_VariantInit
0x18000eaf6  mov     ecx, 0Ch; vt
0x18000eafb  mov     [rbp+rgsabound.lLbound], 0
0x18000eb02  lea     r8, [rbp+rgsabound]; rgsabound
0x18000eb06  mov     [rbp+rgsabound.cElements], r14d
0x18000eb0a  lea     edx, [rcx-0Bh]; cDims
0x18000eb0d  call    cs:__imp_SafeArrayCreate
0x18000eb13  mov     rsi, rax
0x18000eb16  test    rax, rax
0x18000eb19  jnz     short loc_18000EB25
0x18000eb1b  mov     ebx, 8007000Eh
0x18000eb20  jmp     loc_18000EBCE
0x18000eb25  mov     [rbp+rgIndices], 0
0x18000eb2c  xor     eax, eax
0x18000eb2e  cmp     eax, r14d
0x18000eb31  jge     loc_18000EBD2
0x18000eb37  xor     eax, eax
0x18000eb39  lea     rcx, [rbp+pvarg]; pvarg
0x18000eb3d  xorps   xmm0, xmm0
0x18000eb40  mov     qword ptr [rbp+pvarg+10h], rax
0x18000eb44  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000eb48  mov     [rbp+pMem], rax
0x18000eb4c  call    cs:__imp_VariantInit
0x18000eb52  mov     eax, 8
0x18000eb57  lea     r9, [rbp+pMem]; unsigned __int8 **
0x18000eb5b  mov     word ptr [rbp+pvarg], ax
0x18000eb5f  xor     r8d, r8d; int
0x18000eb62  mov     eax, [rbp+rgIndices]
0x18000eb65  xor     edx, edx; int
0x18000eb67  mov     rcx, r13; this
0x18000eb6a  mov     [rsp+50h+var_30], eax; int
0x18000eb6e  call    ?GetEntry@CIPSecurity@@QEAAHHHPEAPEAEH@Z; CIPSecurity::GetEntry(int,int,uchar * *,int)
0x18000eb73  mov     rcx, [rbp+pMem]
0x18000eb77  lea     rdx, [rbp+pvarg+8]
0x18000eb7b  call    ADsAllocString
0x18000eb80  cmp     [rbp+pMem], 0
0x18000eb85  mov     ebx, eax
0x18000eb87  jz      short loc_18000EB93
0x18000eb89  mov     rcx, [rbp+pMem]; pMem
0x18000eb8d  call    cs:__imp_FreeADsMem
0x18000eb93  test    ebx, ebx
0x18000eb95  js      short loc_18000EBC5
0x18000eb97  lea     r8, [rbp+pvarg]; pv
0x18000eb9b  mov     rcx, rsi; psa
0x18000eb9e  lea     rdx, [rbp+rgIndices]; rgIndices
0x18000eba2  call    cs:__imp_SafeArrayPutElement
0x18000eba8  lea     rcx, [rbp+pvarg]; pvarg
0x18000ebac  mov     ebx, eax
0x18000ebae  call    cs:__imp_VariantClear
0x18000ebb4  test    ebx, ebx
0x18000ebb6  js      short loc_18000EBC5
0x18000ebb8  mov     eax, [rbp+rgIndices]
0x18000ebbb  inc     eax
0x18000ebbd  mov     [rbp+rgIndices], eax
0x18000ebc0  jmp     loc_18000EB2E
0x18000ebc5  mov     rcx, rsi; psa
0x18000ebc8  call    cs:__imp_SafeArrayDestroy
0x18000ebce  mov     eax, ebx
0x18000ebd0  jmp     short loc_18000EBDD
0x18000ebd2  mov     word ptr [rdi], 200Ch
0x18000ebd7  xor     eax, eax
0x18000ebd9  mov     [rdi+8], rsi
0x18000ebdd  mov     rbx, [rsp+50h+arg_0]
0x18000ebe5  add     rsp, 50h
0x18000ebe9  pop     r14
0x18000ebeb  pop     r13
0x18000ebed  pop     rdi
0x18000ebee  pop     rsi
0x18000ebef  pop     rbp
0x18000ebf0  retn
```
