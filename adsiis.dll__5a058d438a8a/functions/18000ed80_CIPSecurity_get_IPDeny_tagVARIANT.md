# CIPSecurity::get_IPDeny(tagVARIANT *)

- ea: `0x18000ed80`
- end: `0x18000eece`
- name: `?get_IPDeny@CIPSecurity@@UEAAJPEAUtagVARIANT@@@Z`
- size: `334`
- prototype: `__int64 __fastcall(CIPSecurity *__hidden this, VARIANTARG *pvarg)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000e528`
- `0x18000ed80`
- `0x18001beb8`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000edcb`
- `OLEAUT32!__imp_VariantInit` at `0x18000ee27`
- `OLEAUT32!__imp_VariantInit` at `0x18000edcb`
- `OLEAUT32!__imp_VariantInit` at `0x18000ee27`
- `OLEAUT32!__imp_VariantClear` at `0x18000ee8b`
- `OLEAUT32!__imp_VariantClear` at `0x18000ee8b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000ede8`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000ede8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000eea5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000eea5`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000ee7f`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000ee7f`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000ee6a`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000ee6a`

## pseudocode

```c
__int64 __fastcall CIPSecurity::get_IPDeny(CIPSecurity *this, VARIANTARG *pvarg)
{
  __int64 result; // rax
  unsigned int *v5; // rcx
  __int64 v6; // rax
  signed int v7; // r14d
  SAFEARRAY *v8; // rsi
  HRESULT v9; // ebx
  LONG i; // eax
  VARIANTARG pvarga; // [rsp+30h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+88h] [rbp+38h] BYREF
  LPVOID pMem; // [rsp+90h] [rbp+40h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+98h] [rbp+48h] BYREF

  if ( !pvarg )
    return 2147500035LL;
  v5 = (unsigned int *)*((_QWORD *)this + 3);
  rgIndices = 0;
  if ( v5 )
  {
    v6 = *v5;
    LODWORD(v6) = v6 & 0x7FFFFFFF;
    v7 = *(unsigned int *)((char *)v5 + v6 + 4);
  }
  else
  {
    v7 = 0;
  }
  VariantInit(pvarg);
  rgsabound.lLbound = 0;
  rgsabound.cElements = v7;
  v8 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  if ( v8 )
  {
    rgIndices = 0;
    for ( i = 0; i < v7; i = ++rgIndices )
    {
      memset(&pvarga, 0, sizeof(pvarga));
      pMem = 0;
      VariantInit(&pvarga);
      pvarga.vt = 8;
      CIPSecurity::GetEntry(this, 1, 0, (unsigned __int8 **)&pMem, rgIndices);
      v9 = ADsAllocString(pMem, &pvarga.decVal.Lo32);
      if ( pMem )
        FreeADsMem(pMem);
      if ( v9 >= 0 )
      {
        v9 = SafeArrayPutElement(v8, &rgIndices, &pvarga);
        VariantClear(&pvarga);
        if ( v9 >= 0 )
          continue;
      }
      SafeArrayDestroy(v8);
      return (unsigned int)v9;
    }
    pvarg->vt = 8204;
    result = 0;
    pvarg->llVal = (LONGLONG)v8;
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
0x18000ed80  mov     [rsp-28h+arg_0], rbx
0x18000ed85  push    rbp
0x18000ed86  push    rsi
0x18000ed87  push    rdi
0x18000ed88  push    r14
0x18000ed8a  push    r15
0x18000ed8c  mov     rbp, rsp
0x18000ed8f  sub     rsp, 50h
0x18000ed93  mov     rdi, rdx
0x18000ed96  mov     r15, rcx
0x18000ed99  test    rdx, rdx
0x18000ed9c  jnz     short loc_18000EDA8
0x18000ed9e  mov     eax, 80004003h
0x18000eda3  jmp     loc_18000EEBA
0x18000eda8  mov     rcx, [rcx+18h]
0x18000edac  mov     [rbp+rgIndices], 0
0x18000edb3  test    rcx, rcx
0x18000edb6  jz      short loc_18000EDC5
0x18000edb8  mov     eax, [rcx]
0x18000edba  btr     eax, 1Fh
0x18000edbe  mov     r14d, [rax+rcx+4]
0x18000edc3  jmp     short loc_18000EDC8
0x18000edc5  xor     r14d, r14d
0x18000edc8  mov     rcx, rdi; pvarg
0x18000edcb  call    cs:__imp_VariantInit
0x18000edd1  mov     ecx, 0Ch; vt
0x18000edd6  mov     [rbp+rgsabound.lLbound], 0
0x18000eddd  lea     r8, [rbp+rgsabound]; rgsabound
0x18000ede1  mov     [rbp+rgsabound.cElements], r14d
0x18000ede5  lea     edx, [rcx-0Bh]; cDims
0x18000ede8  call    cs:__imp_SafeArrayCreate
0x18000edee  mov     rsi, rax
0x18000edf1  test    rax, rax
0x18000edf4  jnz     short loc_18000EE00
0x18000edf6  mov     ebx, 8007000Eh
0x18000edfb  jmp     loc_18000EEAB
0x18000ee00  mov     [rbp+rgIndices], 0
0x18000ee07  xor     eax, eax
0x18000ee09  cmp     eax, r14d
0x18000ee0c  jge     loc_18000EEAF
0x18000ee12  xor     eax, eax
0x18000ee14  lea     rcx, [rbp+pvarg]; pvarg
0x18000ee18  xorps   xmm0, xmm0
0x18000ee1b  mov     qword ptr [rbp+pvarg+10h], rax
0x18000ee1f  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000ee23  mov     [rbp+pMem], rax
0x18000ee27  call    cs:__imp_VariantInit
0x18000ee2d  mov     eax, 8
0x18000ee32  lea     r9, [rbp+pMem]; unsigned __int8 **
0x18000ee36  xor     r8d, r8d; int
0x18000ee39  mov     word ptr [rbp+pvarg], ax
0x18000ee3d  mov     eax, [rbp+rgIndices]
0x18000ee40  mov     rcx, r15; this
0x18000ee43  mov     [rsp+50h+var_30], eax; int
0x18000ee47  lea     edx, [r8+1]; int
0x18000ee4b  call    ?GetEntry@CIPSecurity@@QEAAHHHPEAPEAEH@Z; CIPSecurity::GetEntry(int,int,uchar * *,int)
0x18000ee50  mov     rcx, [rbp+pMem]
0x18000ee54  lea     rdx, [rbp+pvarg+8]
0x18000ee58  call    ADsAllocString
0x18000ee5d  cmp     [rbp+pMem], 0
0x18000ee62  mov     ebx, eax
0x18000ee64  jz      short loc_18000EE70
0x18000ee66  mov     rcx, [rbp+pMem]; pMem
0x18000ee6a  call    cs:__imp_FreeADsMem
0x18000ee70  test    ebx, ebx
0x18000ee72  js      short loc_18000EEA2
0x18000ee74  lea     r8, [rbp+pvarg]; pv
0x18000ee78  mov     rcx, rsi; psa
0x18000ee7b  lea     rdx, [rbp+rgIndices]; rgIndices
0x18000ee7f  call    cs:__imp_SafeArrayPutElement
0x18000ee85  lea     rcx, [rbp+pvarg]; pvarg
0x18000ee89  mov     ebx, eax
0x18000ee8b  call    cs:__imp_VariantClear
0x18000ee91  test    ebx, ebx
0x18000ee93  js      short loc_18000EEA2
0x18000ee95  mov     eax, [rbp+rgIndices]
0x18000ee98  inc     eax
0x18000ee9a  mov     [rbp+rgIndices], eax
0x18000ee9d  jmp     loc_18000EE09
0x18000eea2  mov     rcx, rsi; psa
0x18000eea5  call    cs:__imp_SafeArrayDestroy
0x18000eeab  mov     eax, ebx
0x18000eead  jmp     short loc_18000EEBA
0x18000eeaf  mov     word ptr [rdi], 200Ch
0x18000eeb4  xor     eax, eax
0x18000eeb6  mov     [rdi+8], rsi
0x18000eeba  mov     rbx, [rsp+50h+arg_0]
0x18000eec2  add     rsp, 50h
0x18000eec6  pop     r15
0x18000eec8  pop     r14
0x18000eeca  pop     rdi
0x18000eecb  pop     rsi
0x18000eecc  pop     rbp
0x18000eecd  retn
```
