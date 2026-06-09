# CIPSecurity::get_DomainGrant(tagVARIANT *)

- ea: `0x18000ec00`
- end: `0x18000ed45`
- name: `?get_DomainGrant@CIPSecurity@@UEAAJPEAUtagVARIANT@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(CIPSecurity *__hidden this, VARIANTARG *pvarg)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e528`
- `0x18000ec00`
- `0x18001beb8`
- `0x18001cfcc`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000ec43`
- `OLEAUT32!__imp_VariantInit` at `0x18000ec9f`
- `OLEAUT32!__imp_VariantInit` at `0x18000ec43`
- `OLEAUT32!__imp_VariantInit` at `0x18000ec9f`
- `OLEAUT32!__imp_VariantClear` at `0x18000ed02`
- `OLEAUT32!__imp_VariantClear` at `0x18000ed02`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000ec60`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000ec60`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000ed1c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000ed1c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000ecf6`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000ecf6`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000ece1`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000ece1`

## pseudocode

```c
__int64 __fastcall CIPSecurity::get_DomainGrant(CIPSecurity *this, VARIANTARG *pvarg)
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
  NbName = ADDRESS_CHECK::GetNbName((CIPSecurity *)((char *)this + 24), 1);
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
      CIPSecurity::GetEntry(this, 0, 1, (unsigned __int8 **)&pMem, rgIndices);
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
0x18000ec00  mov     [rsp-28h+arg_0], rbx
0x18000ec05  push    rbp
0x18000ec06  push    rsi
0x18000ec07  push    rdi
0x18000ec08  push    r13
0x18000ec0a  push    r14
0x18000ec0c  mov     rbp, rsp
0x18000ec0f  sub     rsp, 50h
0x18000ec13  mov     rdi, rdx
0x18000ec16  mov     r13, rcx
0x18000ec19  test    rdx, rdx
0x18000ec1c  jnz     short loc_18000EC28
0x18000ec1e  mov     eax, 80004003h
0x18000ec23  jmp     loc_18000ED31
0x18000ec28  add     rcx, 18h; this
0x18000ec2c  mov     [rbp+rgIndices], 0
0x18000ec33  mov     edx, 1; int
0x18000ec38  call    ?GetNbName@ADDRESS_CHECK@@QEAAKH@Z; ADDRESS_CHECK::GetNbName(int)
0x18000ec3d  mov     rcx, rdi; pvarg
0x18000ec40  mov     r14d, eax
0x18000ec43  call    cs:__imp_VariantInit
0x18000ec49  mov     ecx, 0Ch; vt
0x18000ec4e  mov     [rbp+rgsabound.lLbound], 0
0x18000ec55  lea     r8, [rbp+rgsabound]; rgsabound
0x18000ec59  mov     [rbp+rgsabound.cElements], r14d
0x18000ec5d  lea     edx, [rcx-0Bh]; cDims
0x18000ec60  call    cs:__imp_SafeArrayCreate
0x18000ec66  mov     rsi, rax
0x18000ec69  test    rax, rax
0x18000ec6c  jnz     short loc_18000EC78
0x18000ec6e  mov     ebx, 8007000Eh
0x18000ec73  jmp     loc_18000ED22
0x18000ec78  mov     [rbp+rgIndices], 0
0x18000ec7f  xor     eax, eax
0x18000ec81  cmp     eax, r14d
0x18000ec84  jge     loc_18000ED26
0x18000ec8a  xor     eax, eax
0x18000ec8c  lea     rcx, [rbp+pvarg]; pvarg
0x18000ec90  xorps   xmm0, xmm0
0x18000ec93  mov     qword ptr [rbp+pvarg+10h], rax
0x18000ec97  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000ec9b  mov     [rbp+pMem], rax
0x18000ec9f  call    cs:__imp_VariantInit
0x18000eca5  mov     eax, 8
0x18000ecaa  lea     r9, [rbp+pMem]; unsigned __int8 **
0x18000ecae  xor     edx, edx; int
0x18000ecb0  mov     word ptr [rbp+pvarg], ax
0x18000ecb4  mov     eax, [rbp+rgIndices]
0x18000ecb7  mov     rcx, r13; this
0x18000ecba  mov     [rsp+50h+var_30], eax; int
0x18000ecbe  lea     r8d, [rdx+1]; int
0x18000ecc2  call    ?GetEntry@CIPSecurity@@QEAAHHHPEAPEAEH@Z; CIPSecurity::GetEntry(int,int,uchar * *,int)
0x18000ecc7  mov     rcx, [rbp+pMem]
0x18000eccb  lea     rdx, [rbp+pvarg+8]
0x18000eccf  call    ADsAllocString
0x18000ecd4  cmp     [rbp+pMem], 0
0x18000ecd9  mov     ebx, eax
0x18000ecdb  jz      short loc_18000ECE7
0x18000ecdd  mov     rcx, [rbp+pMem]; pMem
0x18000ece1  call    cs:__imp_FreeADsMem
0x18000ece7  test    ebx, ebx
0x18000ece9  js      short loc_18000ED19
0x18000eceb  lea     r8, [rbp+pvarg]; pv
0x18000ecef  mov     rcx, rsi; psa
0x18000ecf2  lea     rdx, [rbp+rgIndices]; rgIndices
0x18000ecf6  call    cs:__imp_SafeArrayPutElement
0x18000ecfc  lea     rcx, [rbp+pvarg]; pvarg
0x18000ed00  mov     ebx, eax
0x18000ed02  call    cs:__imp_VariantClear
0x18000ed08  test    ebx, ebx
0x18000ed0a  js      short loc_18000ED19
0x18000ed0c  mov     eax, [rbp+rgIndices]
0x18000ed0f  inc     eax
0x18000ed11  mov     [rbp+rgIndices], eax
0x18000ed14  jmp     loc_18000EC81
0x18000ed19  mov     rcx, rsi; psa
0x18000ed1c  call    cs:__imp_SafeArrayDestroy
0x18000ed22  mov     eax, ebx
0x18000ed24  jmp     short loc_18000ED31
0x18000ed26  mov     word ptr [rdi], 200Ch
0x18000ed2b  xor     eax, eax
0x18000ed2d  mov     [rdi+8], rsi
0x18000ed31  mov     rbx, [rsp+50h+arg_0]
0x18000ed39  add     rsp, 50h
0x18000ed3d  pop     r14
0x18000ed3f  pop     r13
0x18000ed41  pop     rdi
0x18000ed42  pop     rsi
0x18000ed43  pop     rbp
0x18000ed44  retn
```
