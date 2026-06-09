# MakeVariantFromStringArray(ushort *,ushort *,tagVARIANT *)

- ea: `0x180013e08`
- end: `0x180013f8c`
- name: `?MakeVariantFromStringArray@@YAJPEAG0PEAUtagVARIANT@@@Z`
- size: `388`
- prototype: `int(unsigned __int16 *, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006240`
- `0x180008a50`
- `0x180009d90`
- `0x18000a660`

## callees

- `0x180013e08`
- `0x18001beb8`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180013eca`
- `OLEAUT32!__imp_VariantInit` at `0x180013f61`
- `OLEAUT32!__imp_VariantInit` at `0x180013eca`
- `OLEAUT32!__imp_VariantInit` at `0x180013f61`
- `OLEAUT32!__imp_VariantClear` at `0x180013f02`
- `OLEAUT32!__imp_VariantClear` at `0x180013f02`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180013e97`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180013f47`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180013e97`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180013f47`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180013f2f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180013f2f`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180013ef6`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180013ef6`

## pseudocode

```c
__int64 __fastcall MakeVariantFromStringArray(unsigned __int16 *a1, unsigned __int16 *a2, struct tagVARIANT *a3)
{
  unsigned __int16 *v4; // rsi
  unsigned __int16 v5; // cx
  unsigned __int16 v6; // dx
  unsigned __int16 *v7; // rax
  signed int v8; // r14d
  SAFEARRAY *v9; // rdi
  LONG i; // eax
  HRESULT v11; // ebx
  __int64 v12; // rax
  __int64 result; // rax
  LONG rgIndices; // [rsp+20h] [rbp-30h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+28h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF

  v4 = a2;
  if ( a2 )
  {
    v5 = *a2;
    rgIndices = 0;
    if ( v5 )
      v6 = v5;
    else
      v6 = a2[1];
    v7 = v4 + 1;
    v8 = v5 == 0;
    if ( v5 )
      v7 = v4;
    if ( v6 )
    {
      if ( !*v7 )
        goto LABEL_10;
      do
      {
        do
          ++v7;
        while ( *v7 );
LABEL_10:
        ++v7;
        ++v8;
      }
      while ( *v7 );
    }
    rgsabound.lLbound = 0;
    rgsabound.cElements = v8;
    v9 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    if ( v9 )
    {
      rgIndices = 0;
      for ( i = 0; i < v8; i = ++rgIndices )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        pvarg.vt = 8;
        v11 = ADsAllocString(v4, &pvarg.decVal.Lo32);
        if ( v11 < 0 || (v11 = SafeArrayPutElement(v9, &rgIndices, &pvarg), VariantClear(&pvarg), v11 < 0) )
        {
          SafeArrayDestroy(v9);
          return (unsigned int)v11;
        }
        v12 = -1;
        do
          ++v12;
        while ( v4[v12] );
        v4 += v12 + 1;
      }
      goto LABEL_23;
    }
  }
  else
  {
    rgsabound = 0;
    v9 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    if ( v9 )
    {
LABEL_23:
      VariantInit(a3);
      a3->vt = 8204;
      result = 0;
      a3->llVal = (LONGLONG)v9;
      return result;
    }
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x180013e08  mov     [rsp-28h+arg_0], rbx
0x180013e0d  mov     [rsp-28h+arg_18], rsi
0x180013e12  push    rbp
0x180013e13  push    rdi
0x180013e14  push    r12
0x180013e16  push    r14
0x180013e18  push    r15
0x180013e1a  mov     rbp, rsp
0x180013e1d  sub     rsp, 50h
0x180013e21  xor     r12d, r12d
0x180013e24  mov     r15, r8
0x180013e27  mov     rsi, rdx
0x180013e2a  test    rdx, rdx
0x180013e2d  jz      loc_180013F37
0x180013e33  movzx   ecx, word ptr [rdx]
0x180013e36  mov     [rbp+rgIndices], r12d
0x180013e3a  test    cx, cx
0x180013e3d  jnz     short loc_180013E45
0x180013e3f  movzx   edx, word ptr [rdx+2]
0x180013e43  jmp     short loc_180013E48
0x180013e45  movzx   edx, cx
0x180013e48  test    cx, cx
0x180013e4b  lea     rax, [rsi+2]
0x180013e4f  mov     r14d, r12d
0x180013e52  setz    r14b
0x180013e56  test    cx, cx
0x180013e59  cmovnz  rax, rsi
0x180013e5d  test    dx, dx
0x180013e60  jz      short loc_180013E83
0x180013e62  movzx   ecx, word ptr [rax]
0x180013e65  test    cx, cx
0x180013e68  jz      short loc_180013E74
0x180013e6a  add     rax, 2
0x180013e6e  cmp     [rax], r12w
0x180013e72  jnz     short loc_180013E6A
0x180013e74  add     rax, 2
0x180013e78  inc     r14d
0x180013e7b  movzx   ecx, word ptr [rax]
0x180013e7e  test    cx, cx
0x180013e81  jnz     short loc_180013E6A
0x180013e83  mov     ecx, 0Ch; vt
0x180013e88  mov     [rbp+rgsabound.lLbound], r12d
0x180013e8c  lea     r8, [rbp+rgsabound]; rgsabound
0x180013e90  mov     [rbp+rgsabound.cElements], r14d
0x180013e94  lea     edx, [rcx-0Bh]; cDims
0x180013e97  call    cs:__imp_SafeArrayCreate
0x180013e9d  mov     rdi, rax
0x180013ea0  test    rax, rax
0x180013ea3  jz      loc_180013F55
0x180013ea9  mov     [rbp+rgIndices], r12d
0x180013ead  mov     eax, r12d
0x180013eb0  cmp     eax, r14d
0x180013eb3  jge     loc_180013F5E
0x180013eb9  xorps   xmm0, xmm0
0x180013ebc  lea     rcx, [rbp+pvarg]; pvarg
0x180013ec0  xor     eax, eax
0x180013ec2  movups  xmmword ptr [rbp+pvarg], xmm0
0x180013ec6  mov     qword ptr [rbp+pvarg+10h], rax
0x180013eca  call    cs:__imp_VariantInit
0x180013ed0  mov     eax, 8
0x180013ed5  lea     rdx, [rbp+pvarg+8]
0x180013ed9  mov     rcx, rsi
0x180013edc  mov     word ptr [rbp+pvarg], ax
0x180013ee0  call    ADsAllocString
0x180013ee5  mov     ebx, eax
0x180013ee7  test    eax, eax
0x180013ee9  js      short loc_180013F2C
0x180013eeb  lea     r8, [rbp+pvarg]; pv
0x180013eef  mov     rcx, rdi; psa
0x180013ef2  lea     rdx, [rbp+rgIndices]; rgIndices
0x180013ef6  call    cs:__imp_SafeArrayPutElement
0x180013efc  lea     rcx, [rbp+pvarg]; pvarg
0x180013f00  mov     ebx, eax
0x180013f02  call    cs:__imp_VariantClear
0x180013f08  test    ebx, ebx
0x180013f0a  js      short loc_180013F2C
0x180013f0c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013f10  inc     rax
0x180013f13  cmp     [rsi+rax*2], r12w
0x180013f18  jnz     short loc_180013F10
0x180013f1a  lea     rsi, [rsi+rax*2]
0x180013f1e  mov     eax, [rbp+rgIndices]
0x180013f21  add     rsi, 2
0x180013f25  inc     eax
0x180013f27  mov     [rbp+rgIndices], eax
0x180013f2a  jmp     short loc_180013EB0
0x180013f2c  mov     rcx, rdi; psa
0x180013f2f  call    cs:__imp_SafeArrayDestroy
0x180013f35  jmp     short loc_180013F5A
0x180013f37  mov     ecx, 0Ch; vt
0x180013f3c  mov     qword ptr [rbp+rgsabound.cElements], r12
0x180013f40  lea     r8, [rbp+rgsabound]; rgsabound
0x180013f44  lea     edx, [rcx-0Bh]; cDims
0x180013f47  call    cs:__imp_SafeArrayCreate
0x180013f4d  mov     rdi, rax
0x180013f50  test    rax, rax
0x180013f53  jnz     short loc_180013F5E
0x180013f55  mov     ebx, 8007000Eh
0x180013f5a  mov     eax, ebx
0x180013f5c  jmp     short loc_180013F73
0x180013f5e  mov     rcx, r15; pvarg
0x180013f61  call    cs:__imp_VariantInit
0x180013f67  mov     word ptr [r15], 200Ch
0x180013f6d  xor     eax, eax
0x180013f6f  mov     [r15+8], rdi
0x180013f73  lea     r11, [rsp+50h+var_s0]
0x180013f78  mov     rbx, [r11+30h]
0x180013f7c  mov     rsi, [r11+48h]
0x180013f80  mov     rsp, r11
0x180013f83  pop     r15
0x180013f85  pop     r14
0x180013f87  pop     r12
0x180013f89  pop     rdi
0x180013f8a  pop     rbp
0x180013f8b  retn
```
