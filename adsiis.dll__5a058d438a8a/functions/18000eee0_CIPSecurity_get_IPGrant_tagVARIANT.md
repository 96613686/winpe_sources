# CIPSecurity::get_IPGrant(tagVARIANT *)

- ea: `0x18000eee0`
- end: `0x18000f030`
- name: `?get_IPGrant@CIPSecurity@@UEAAJPEAUtagVARIANT@@@Z`
- size: `336`
- prototype: `__int64 __fastcall(CIPSecurity *__hidden this, VARIANTARG *pvarg)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000e528`
- `0x18000eee0`
- `0x18001beb8`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000ef2c`
- `OLEAUT32!__imp_VariantInit` at `0x18000ef88`
- `OLEAUT32!__imp_VariantInit` at `0x18000ef2c`
- `OLEAUT32!__imp_VariantInit` at `0x18000ef88`
- `OLEAUT32!__imp_VariantClear` at `0x18000efed`
- `OLEAUT32!__imp_VariantClear` at `0x18000efed`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000ef49`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000ef49`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000f007`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000f007`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000efe1`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000efe1`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000efcc`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000efcc`

## pseudocode

```c
__int64 __fastcall CIPSecurity::get_IPGrant(CIPSecurity *this, VARIANTARG *pvarg)
{
  __int64 result; // rax
  __int64 v5; // rcx
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
  v5 = *((_QWORD *)this + 3);
  rgIndices = 0;
  if ( v5 )
  {
    v6 = *(unsigned int *)(v5 + 4);
    LODWORD(v6) = v6 & 0x7FFFFFFF;
    v7 = *(_DWORD *)(v6 + v5 + 4);
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
      CIPSecurity::GetEntry(this, 1, 1, (unsigned __int8 **)&pMem, rgIndices);
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
0x18000eee0  mov     [rsp-28h+arg_0], rbx
0x18000eee5  push    rbp
0x18000eee6  push    rsi
0x18000eee7  push    rdi
0x18000eee8  push    r14
0x18000eeea  push    r15
0x18000eeec  mov     rbp, rsp
0x18000eeef  sub     rsp, 50h
0x18000eef3  mov     rdi, rdx
0x18000eef6  mov     r15, rcx
0x18000eef9  test    rdx, rdx
0x18000eefc  jnz     short loc_18000EF08
0x18000eefe  mov     eax, 80004003h
0x18000ef03  jmp     loc_18000F01C
0x18000ef08  mov     rcx, [rcx+18h]
0x18000ef0c  mov     [rbp+rgIndices], 0
0x18000ef13  test    rcx, rcx
0x18000ef16  jz      short loc_18000EF26
0x18000ef18  mov     eax, [rcx+4]
0x18000ef1b  btr     eax, 1Fh
0x18000ef1f  mov     r14d, [rax+rcx+4]
0x18000ef24  jmp     short loc_18000EF29
0x18000ef26  xor     r14d, r14d
0x18000ef29  mov     rcx, rdi; pvarg
0x18000ef2c  call    cs:__imp_VariantInit
0x18000ef32  mov     ecx, 0Ch; vt
0x18000ef37  mov     [rbp+rgsabound.lLbound], 0
0x18000ef3e  lea     r8, [rbp+rgsabound]; rgsabound
0x18000ef42  mov     [rbp+rgsabound.cElements], r14d
0x18000ef46  lea     edx, [rcx-0Bh]; cDims
0x18000ef49  call    cs:__imp_SafeArrayCreate
0x18000ef4f  mov     rsi, rax
0x18000ef52  test    rax, rax
0x18000ef55  jnz     short loc_18000EF61
0x18000ef57  mov     ebx, 8007000Eh
0x18000ef5c  jmp     loc_18000F00D
0x18000ef61  mov     [rbp+rgIndices], 0
0x18000ef68  xor     eax, eax
0x18000ef6a  cmp     eax, r14d
0x18000ef6d  jge     loc_18000F011
0x18000ef73  xor     eax, eax
0x18000ef75  lea     rcx, [rbp+pvarg]; pvarg
0x18000ef79  xorps   xmm0, xmm0
0x18000ef7c  mov     qword ptr [rbp+pvarg+10h], rax
0x18000ef80  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000ef84  mov     [rbp+pMem], rax
0x18000ef88  call    cs:__imp_VariantInit
0x18000ef8e  mov     eax, 8
0x18000ef93  lea     r9, [rbp+pMem]; unsigned __int8 **
0x18000ef97  mov     edx, 1; int
0x18000ef9c  mov     word ptr [rbp+pvarg], ax
0x18000efa0  mov     eax, [rbp+rgIndices]
0x18000efa3  mov     r8d, edx; int
0x18000efa6  mov     rcx, r15; this
0x18000efa9  mov     [rsp+50h+var_30], eax; int
0x18000efad  call    ?GetEntry@CIPSecurity@@QEAAHHHPEAPEAEH@Z; CIPSecurity::GetEntry(int,int,uchar * *,int)
0x18000efb2  mov     rcx, [rbp+pMem]
0x18000efb6  lea     rdx, [rbp+pvarg+8]
0x18000efba  call    ADsAllocString
0x18000efbf  cmp     [rbp+pMem], 0
0x18000efc4  mov     ebx, eax
0x18000efc6  jz      short loc_18000EFD2
0x18000efc8  mov     rcx, [rbp+pMem]; pMem
0x18000efcc  call    cs:__imp_FreeADsMem
0x18000efd2  test    ebx, ebx
0x18000efd4  js      short loc_18000F004
0x18000efd6  lea     r8, [rbp+pvarg]; pv
0x18000efda  mov     rcx, rsi; psa
0x18000efdd  lea     rdx, [rbp+rgIndices]; rgIndices
0x18000efe1  call    cs:__imp_SafeArrayPutElement
0x18000efe7  lea     rcx, [rbp+pvarg]; pvarg
0x18000efeb  mov     ebx, eax
0x18000efed  call    cs:__imp_VariantClear
0x18000eff3  test    ebx, ebx
0x18000eff5  js      short loc_18000F004
0x18000eff7  mov     eax, [rbp+rgIndices]
0x18000effa  inc     eax
0x18000effc  mov     [rbp+rgIndices], eax
0x18000efff  jmp     loc_18000EF6A
0x18000f004  mov     rcx, rsi; psa
0x18000f007  call    cs:__imp_SafeArrayDestroy
0x18000f00d  mov     eax, ebx
0x18000f00f  jmp     short loc_18000F01C
0x18000f011  mov     word ptr [rdi], 200Ch
0x18000f016  xor     eax, eax
0x18000f018  mov     [rdi+8], rsi
0x18000f01c  mov     rbx, [rsp+50h+arg_0]
0x18000f024  add     rsp, 50h
0x18000f028  pop     r15
0x18000f02a  pop     r14
0x18000f02c  pop     rdi
0x18000f02d  pop     rsi
0x18000f02e  pop     rbp
0x18000f02f  retn
```
