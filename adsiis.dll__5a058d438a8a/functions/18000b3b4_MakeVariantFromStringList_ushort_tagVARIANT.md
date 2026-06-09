# MakeVariantFromStringList(ushort *,tagVARIANT *)

- ea: `0x18000b3b4`
- end: `0x18000b562`
- name: `?MakeVariantFromStringList@@YAJPEAGPEAUtagVARIANT@@@Z`
- size: `430`
- prototype: `int(unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180009a44`
- `0x18000a5b0`
- `0x18000aa70`

## callees

- `0x18000b3b4`
- `0x18001beb8`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000b4f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b526`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b526`
- `OLEAUT32!__imp_VariantInit` at `0x18000b477`
- `OLEAUT32!__imp_VariantInit` at `0x18000b4e4`
- `OLEAUT32!__imp_VariantInit` at `0x18000b541`
- `OLEAUT32!__imp_VariantInit` at `0x18000b477`
- `OLEAUT32!__imp_VariantInit` at `0x18000b4e4`
- `OLEAUT32!__imp_VariantInit` at `0x18000b541`
- `OLEAUT32!__imp_VariantClear` at `0x18000b4b3`
- `OLEAUT32!__imp_VariantClear` at `0x18000b4b3`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000b445`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000b50b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000b445`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000b50b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000b534`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000b534`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000b4a7`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000b4a7`

## pseudocode

```c
__int64 __fastcall MakeVariantFromStringList(unsigned __int16 *a1, struct tagVARIANT *a2)
{
  OLECHAR *v3; // rbx
  SAFEARRAY *v4; // rsi
  int v5; // eax
  HRESULT v6; // edi
  LONG v7; // ecx
  signed int v8; // r12d
  OLECHAR i; // dx
  OLECHAR *v10; // r13
  LONG j; // eax
  __int64 v12; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+80h] [rbp+40h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+90h] [rbp+50h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp+58h] BYREF

  rgsabound = 0;
  v3 = 0;
  bstrString = 0;
  if ( !a1 )
  {
    v4 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    if ( v4 )
    {
      VariantInit(a2);
      a2->vt = 8204;
      a2->llVal = (LONGLONG)v4;
      return 0;
    }
    goto LABEL_18;
  }
  rgIndices = 0;
  v4 = 0;
  v5 = ADsAllocString(a1, &bstrString);
  v3 = bstrString;
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = rgIndices;
    v8 = 1;
    for ( i = bstrString[rgIndices]; i; i = v3[v7] )
    {
      if ( i == 44 )
      {
        ++v8;
        v3[v7] = 0;
        v7 = rgIndices;
      }
      rgIndices = ++v7;
    }
    rgsabound.lLbound = 0;
    rgsabound.cElements = v8;
    v4 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    if ( v4 )
    {
      v10 = v3;
      rgIndices = 0;
      for ( j = 0; j < v8; j = ++rgIndices )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        pvarg.vt = 8;
        v6 = ADsAllocString(v10, &pvarg.decVal.Lo32);
        if ( v6 < 0 )
          goto LABEL_19;
        v6 = SafeArrayPutElement(v4, &rgIndices, &pvarg);
        VariantClear(&pvarg);
        if ( v6 < 0 )
          goto LABEL_19;
        v12 = -1;
        do
          ++v12;
        while ( v10[v12] );
        v10 += v12 + 1;
      }
      VariantInit(a2);
      a2->vt = 8204;
      a2->llVal = (LONGLONG)v4;
      SysFreeString(v3);
      return 0;
    }
LABEL_18:
    v6 = -2147024882;
  }
LABEL_19:
  if ( v3 )
    SysFreeString(v3);
  if ( v4 )
    SafeArrayDestroy(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000b3b4  push    rbp
0x18000b3b6  push    rbx
0x18000b3b7  push    rsi
0x18000b3b8  push    rdi
0x18000b3b9  push    r12
0x18000b3bb  push    r13
0x18000b3bd  push    r14
0x18000b3bf  mov     rbp, rsp
0x18000b3c2  sub     rsp, 40h
0x18000b3c6  xor     r13d, r13d
0x18000b3c9  mov     r14, rdx
0x18000b3cc  mov     qword ptr [rbp+rgsabound.cElements], r13
0x18000b3d0  mov     ebx, r13d
0x18000b3d3  mov     [rbp+bstrString], rbx
0x18000b3d7  test    rcx, rcx
0x18000b3da  jz      loc_18000B4FF
0x18000b3e0  lea     rdx, [rbp+bstrString]
0x18000b3e4  mov     [rbp+rgIndices], r13d
0x18000b3e8  mov     esi, r13d
0x18000b3eb  call    ADsAllocString
0x18000b3f0  mov     rbx, [rbp+bstrString]
0x18000b3f4  mov     edi, eax
0x18000b3f6  test    eax, eax
0x18000b3f8  js      loc_18000B51E
0x18000b3fe  movsxd  rcx, [rbp+rgIndices]
0x18000b402  lea     r12d, [r13+1]
0x18000b406  movzx   edx, word ptr [rbx+rcx*2]
0x18000b40a  jmp     short loc_18000B42C
0x18000b40c  cmp     dx, 2Ch ; ','
0x18000b410  jnz     short loc_18000B420
0x18000b412  movsxd  rcx, ecx
0x18000b415  inc     r12d
0x18000b418  mov     [rbx+rcx*2], r13w
0x18000b41d  mov     ecx, [rbp+rgIndices]
0x18000b420  inc     ecx
0x18000b422  movsxd  rax, ecx
0x18000b425  mov     [rbp+rgIndices], ecx
0x18000b428  movzx   edx, word ptr [rbx+rax*2]
0x18000b42c  test    dx, dx
0x18000b42f  jnz     short loc_18000B40C
0x18000b431  mov     ecx, 0Ch; vt
0x18000b436  mov     [rbp+rgsabound.lLbound], r13d
0x18000b43a  lea     r8, [rbp+rgsabound]; rgsabound
0x18000b43e  mov     [rbp+rgsabound.cElements], r12d
0x18000b442  lea     edx, [rcx-0Bh]; cDims
0x18000b445  call    cs:__imp_SafeArrayCreate
0x18000b44b  mov     rsi, rax
0x18000b44e  test    rax, rax
0x18000b451  jz      loc_18000B519
0x18000b457  xor     ecx, ecx
0x18000b459  mov     r13, rbx
0x18000b45c  mov     [rbp+rgIndices], ecx
0x18000b45f  mov     eax, ecx
0x18000b461  cmp     eax, r12d
0x18000b464  jge     short loc_18000B4E1
0x18000b466  xorps   xmm0, xmm0
0x18000b469  lea     rcx, [rbp+pvarg]; pvarg
0x18000b46d  xor     eax, eax
0x18000b46f  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000b473  mov     qword ptr [rbp+pvarg+10h], rax
0x18000b477  call    cs:__imp_VariantInit
0x18000b47d  mov     eax, 8
0x18000b482  lea     rdx, [rbp+pvarg+8]
0x18000b486  mov     rcx, r13
0x18000b489  mov     word ptr [rbp+pvarg], ax
0x18000b48d  call    ADsAllocString
0x18000b492  mov     edi, eax
0x18000b494  test    eax, eax
0x18000b496  js      loc_18000B51E
0x18000b49c  lea     r8, [rbp+pvarg]; pv
0x18000b4a0  mov     rcx, rsi; psa
0x18000b4a3  lea     rdx, [rbp+rgIndices]; rgIndices
0x18000b4a7  call    cs:__imp_SafeArrayPutElement
0x18000b4ad  lea     rcx, [rbp+pvarg]; pvarg
0x18000b4b1  mov     edi, eax
0x18000b4b3  call    cs:__imp_VariantClear
0x18000b4b9  xor     ecx, ecx
0x18000b4bb  test    edi, edi
0x18000b4bd  js      short loc_18000B51E
0x18000b4bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b4c3  inc     rax
0x18000b4c6  cmp     [r13+rax*2+0], cx
0x18000b4cc  jnz     short loc_18000B4C3
0x18000b4ce  lea     r13, [r13+rax*2+0]
0x18000b4d3  mov     eax, [rbp+rgIndices]
0x18000b4d6  add     r13, 2
0x18000b4da  inc     eax
0x18000b4dc  mov     [rbp+rgIndices], eax
0x18000b4df  jmp     short loc_18000B461
0x18000b4e1  mov     rcx, r14; pvarg
0x18000b4e4  call    cs:__imp_VariantInit
0x18000b4ea  mov     rcx, rbx; bstrString
0x18000b4ed  mov     word ptr [r14], 200Ch
0x18000b4f3  mov     [r14+8], rsi
0x18000b4f7  call    cs:__imp_SysFreeString
0x18000b4fd  jmp     short loc_18000B551
0x18000b4ff  mov     ecx, 0Ch; vt
0x18000b504  lea     r8, [rbp+rgsabound]; rgsabound
0x18000b508  lea     edx, [rcx-0Bh]; cDims
0x18000b50b  call    cs:__imp_SafeArrayCreate
0x18000b511  mov     rsi, rax
0x18000b514  test    rax, rax
0x18000b517  jnz     short loc_18000B53E
0x18000b519  mov     edi, 8007000Eh
0x18000b51e  test    rbx, rbx
0x18000b521  jz      short loc_18000B52C
0x18000b523  mov     rcx, rbx; bstrString
0x18000b526  call    cs:__imp_SysFreeString
0x18000b52c  test    rsi, rsi
0x18000b52f  jz      short loc_18000B53A
0x18000b531  mov     rcx, rsi; psa
0x18000b534  call    cs:__imp_SafeArrayDestroy
0x18000b53a  mov     eax, edi
0x18000b53c  jmp     short loc_18000B553
0x18000b53e  mov     rcx, r14; pvarg
0x18000b541  call    cs:__imp_VariantInit
0x18000b547  mov     word ptr [r14], 200Ch
0x18000b54d  mov     [r14+8], rsi
0x18000b551  xor     eax, eax
0x18000b553  add     rsp, 40h
0x18000b557  pop     r14
0x18000b559  pop     r13
0x18000b55b  pop     r12
0x18000b55d  pop     rdi
0x18000b55e  pop     rsi
0x18000b55f  pop     rbx
0x18000b560  pop     rbp
0x18000b561  retn
```
