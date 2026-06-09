# VarTypeToIISTypeCopyIISSynIdBinary(tagVARIANT *,_iistype *,int)

- ea: `0x180018cbc`
- end: `0x180018f17`
- name: `?VarTypeToIISTypeCopyIISSynIdBinary@@YAJPEAUtagVARIANT@@PEAU_iistype@@H@Z`
- size: `603`
- prototype: `__int64 __fastcall(VARIANTARG *pvarSrc, struct _iistype *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018a44`

## callees

- `0x180018cbc`
- `0x18001d652`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180018e6d`
- `OLEAUT32!__imp_SysStringLen` at `0x180018e6d`
- `OLEAUT32!__imp_VariantInit` at `0x180018df3`
- `OLEAUT32!__imp_VariantInit` at `0x180018e39`
- `OLEAUT32!__imp_VariantInit` at `0x180018df3`
- `OLEAUT32!__imp_VariantInit` at `0x180018e39`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018d16`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018d16`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180018d6d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180018d6d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180018d52`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180018d52`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180018db9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180018db9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180018eed`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180018eed`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180018e05`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180018e4b`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180018e05`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180018e4b`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180018d87`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180018d87`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180018f00`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180018f00`

## pseudocode

```c
__int64 __fastcall VarTypeToIISTypeCopyIISSynIdBinary(VARIANTARG *pvarSrc, struct _iistype *a2, int a3)
{
  VARTYPE v6; // r9
  HRESULT v7; // eax
  HRESULT LBound; // ebx
  bool v9; // zf
  DWORD v10; // esi
  LPVOID v11; // rax
  int i; // eax
  LONGLONG llVal; // rsi
  UINT v14; // r10d
  char v15; // r8
  __int64 j; // r9
  __int16 v17; // dx
  char v18; // dl
  void *v19; // rcx
  void *ppvData; // [rsp+20h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-18h] BYREF
  LONG rgIndices; // [rsp+88h] [rbp+48h] BYREF
  LONG plLbound; // [rsp+90h] [rbp+50h] BYREF
  LONG plUbound; // [rsp+98h] [rbp+58h] BYREF

  plLbound = 0;
  plUbound = 0;
  ppvData = 0;
  *((_QWORD *)a2 + 2) = 0;
  if ( !a3 )
  {
    v6 = 8209;
LABEL_5:
    v7 = VariantChangeType(pvarSrc, pvarSrc, 0, v6);
    LBound = v7;
    if ( v7 < 0 )
    {
      if ( v7 == -2147024882 )
        goto LABEL_36;
      goto LABEL_7;
    }
    goto LABEL_8;
  }
  if ( pvarSrc->vt != 8204 )
  {
    v6 = 8204;
    goto LABEL_5;
  }
LABEL_8:
  if ( a3 )
    v9 = pvarSrc->vt == 8204;
  else
    v9 = pvarSrc->vt == 8209;
  if ( !v9 )
  {
LABEL_7:
    LBound = -2147463156;
    goto LABEL_36;
  }
  LBound = SafeArrayGetLBound(pvarSrc->parray, 1u, &plLbound);
  if ( LBound >= 0 )
  {
    LBound = SafeArrayGetUBound(pvarSrc->parray, 1u, &plUbound);
    if ( LBound >= 0 )
    {
      v10 = plUbound - plLbound + 1;
      v11 = AllocADsMem(v10);
      *((_QWORD *)a2 + 2) = v11;
      if ( !v11 )
      {
        LBound = -2147024882;
        goto LABEL_36;
      }
      *(_DWORD *)a2 = 5;
      *((_DWORD *)a2 + 2) = v10;
      LBound = SafeArrayAccessData(pvarSrc->parray, &ppvData);
      if ( LBound >= 0 )
      {
        memcpy_0(*((void **)a2 + 2), ppvData, v10);
        if ( !a3 )
        {
LABEL_35:
          SafeArrayUnaccessData(pvarSrc->parray);
          return (unsigned int)LBound;
        }
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        LBound = SafeArrayGetElement(pvarSrc->parray, &plLbound, &pvarg);
        if ( LBound >= 0 )
        {
          if ( pvarg.vt == 8 )
          {
            for ( i = plLbound; ; i = rgIndices + 1 )
            {
              rgIndices = i;
              if ( i > plUbound )
                break;
              VariantInit(&pvarg);
              LBound = SafeArrayGetElement(pvarSrc->parray, &rgIndices, &pvarg);
              if ( LBound < 0 )
                goto LABEL_36;
              if ( pvarg.vt != 8 )
                goto LABEL_7;
              llVal = pvarg.llVal;
              v14 = SysStringLen(pvarg.bstrVal);
              if ( v14 - 1 > 1 )
                goto LABEL_7;
              v15 = 0;
              for ( j = 0; (unsigned int)j < v14; j = (unsigned int)(j + 1) )
              {
                v17 = *(_WORD *)(llVal + 2 * j);
                if ( (unsigned __int16)(v17 - 48) > 9u )
                {
                  if ( (unsigned __int16)(v17 - 65) > 5u )
                  {
                    if ( (unsigned __int16)(v17 - 97) > 5u )
                      goto LABEL_7;
                    v18 = v17 - 87;
                  }
                  else
                  {
                    v18 = v17 - 55;
                  }
                }
                else
                {
                  v18 = v17 - 48;
                }
                v15 = v18 | (16 * v15);
              }
              *(_BYTE *)(rgIndices - plLbound + *((_QWORD *)a2 + 2)) = v15;
            }
          }
          goto LABEL_35;
        }
      }
    }
  }
LABEL_36:
  v19 = (void *)*((_QWORD *)a2 + 2);
  if ( v19 )
    FreeADsMem(v19);
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x180018cbc  push    rbp
0x180018cbe  push    rbx
0x180018cbf  push    rsi
0x180018cc0  push    rdi
0x180018cc1  push    r13
0x180018cc3  push    r14
0x180018cc5  push    r15
0x180018cc7  mov     rbp, rsp
0x180018cca  sub     rsp, 40h
0x180018cce  mov     [rbp+plLbound], 0
0x180018cd5  mov     esi, 200Ch
0x180018cda  mov     [rbp+plUbound], 0
0x180018ce1  mov     r15d, r8d
0x180018ce4  mov     [rbp+ppvData], 0
0x180018cec  mov     r14, rdx
0x180018cef  mov     qword ptr [rdx+10h], 0
0x180018cf7  mov     rdi, rcx
0x180018cfa  lea     r13d, [rsi+5]
0x180018cfe  test    r8d, r8d
0x180018d01  jz      short loc_180018D0D
0x180018d03  cmp     si, [rcx]
0x180018d06  jz      short loc_180018D37
0x180018d08  mov     r9d, esi
0x180018d0b  jmp     short loc_180018D10
0x180018d0d  mov     r9d, r13d; vt
0x180018d10  xor     r8d, r8d; wFlags
0x180018d13  mov     rdx, rdi; pvarSrc
0x180018d16  call    cs:__imp_VariantChangeType
0x180018d1c  mov     ebx, eax
0x180018d1e  test    eax, eax
0x180018d20  jns     short loc_180018D37
0x180018d22  cmp     eax, 8007000Eh
0x180018d27  jz      loc_180018EF7
0x180018d2d  mov     ebx, 8000500Ch
0x180018d32  jmp     loc_180018EF7
0x180018d37  test    r15d, r15d
0x180018d3a  jz      short loc_180018DA0
0x180018d3c  cmp     [rdi], si
0x180018d3f  jnz     short loc_180018D2D
0x180018d41  mov     rcx, [rdi+8]; psa
0x180018d45  lea     r8, [rbp+plLbound]; plLbound
0x180018d49  mov     r13d, 1
0x180018d4f  mov     edx, r13d; nDim
0x180018d52  call    cs:__imp_SafeArrayGetLBound
0x180018d58  mov     ebx, eax
0x180018d5a  test    eax, eax
0x180018d5c  js      loc_180018EF7
0x180018d62  mov     rcx, [rdi+8]; psa
0x180018d66  lea     r8, [rbp+plUbound]; plUbound
0x180018d6a  mov     edx, r13d; nDim
0x180018d6d  call    cs:__imp_SafeArrayGetUBound
0x180018d73  mov     ebx, eax
0x180018d75  test    eax, eax
0x180018d77  js      loc_180018EF7
0x180018d7d  mov     esi, [rbp+plUbound]
0x180018d80  sub     esi, [rbp+plLbound]
0x180018d83  inc     esi
0x180018d85  mov     ecx, esi; cb
0x180018d87  call    cs:__imp_AllocADsMem
0x180018d8d  mov     [r14+10h], rax
0x180018d91  test    rax, rax
0x180018d94  jnz     short loc_180018DA6
0x180018d96  mov     ebx, 8007000Eh
0x180018d9b  jmp     loc_180018EF7
0x180018da0  cmp     [rdi], r13w
0x180018da4  jmp     short loc_180018D3F
0x180018da6  mov     dword ptr [r14], 5
0x180018dad  lea     rdx, [rbp+ppvData]; ppvData
0x180018db1  mov     [r14+8], esi
0x180018db5  mov     rcx, [rdi+8]; psa
0x180018db9  call    cs:__imp_SafeArrayAccessData
0x180018dbf  mov     ebx, eax
0x180018dc1  test    eax, eax
0x180018dc3  js      loc_180018EF7
0x180018dc9  mov     rdx, [rbp+ppvData]; Src
0x180018dcd  mov     rcx, [r14+10h]; void *
0x180018dd1  mov     r8d, esi; Size
0x180018dd4  call    memcpy_0
0x180018dd9  test    r15d, r15d
0x180018ddc  jz      loc_180018EE9
0x180018de2  xorps   xmm0, xmm0
0x180018de5  lea     rcx, [rbp+pvarg]; pvarg
0x180018de9  xor     eax, eax
0x180018deb  movups  xmmword ptr [rbp+pvarg], xmm0
0x180018def  mov     qword ptr [rbp+pvarg+10h], rax
0x180018df3  call    cs:__imp_VariantInit
0x180018df9  mov     rcx, [rdi+8]; psa
0x180018dfd  lea     r8, [rbp+pvarg]; pv
0x180018e01  lea     rdx, [rbp+plLbound]; rgIndices
0x180018e05  call    cs:__imp_SafeArrayGetElement
0x180018e0b  mov     ebx, eax
0x180018e0d  test    eax, eax
0x180018e0f  js      loc_180018EF7
0x180018e15  mov     r15d, 8
0x180018e1b  cmp     r15w, word ptr [rbp+pvarg]
0x180018e20  jnz     loc_180018EE9
0x180018e26  mov     eax, [rbp+plLbound]
0x180018e29  mov     [rbp+rgIndices], eax
0x180018e2c  cmp     eax, [rbp+plUbound]
0x180018e2f  jg      loc_180018EE9
0x180018e35  lea     rcx, [rbp+pvarg]; pvarg
0x180018e39  call    cs:__imp_VariantInit
0x180018e3f  mov     rcx, [rdi+8]; psa
0x180018e43  lea     r8, [rbp+pvarg]; pv
0x180018e47  lea     rdx, [rbp+rgIndices]; rgIndices
0x180018e4b  call    cs:__imp_SafeArrayGetElement
0x180018e51  mov     ebx, eax
0x180018e53  test    eax, eax
0x180018e55  js      loc_180018EF7
0x180018e5b  cmp     r15w, word ptr [rbp+pvarg]
0x180018e60  jnz     loc_180018D2D
0x180018e66  mov     rsi, qword ptr [rbp+pvarg+8]
0x180018e6a  mov     rcx, rsi; pbstr
0x180018e6d  call    cs:__imp_SysStringLen
0x180018e73  mov     r10d, eax
0x180018e76  lea     ecx, [rax-1]
0x180018e79  cmp     ecx, r13d
0x180018e7c  ja      loc_180018D2D
0x180018e82  xor     r8b, r8b
0x180018e85  xor     r9d, r9d
0x180018e88  cmp     r9d, r10d
0x180018e8b  jnb     short loc_180018ECD
0x180018e8d  movzx   edx, word ptr [rsi+r9*2]
0x180018e92  lea     eax, [rdx-30h]
0x180018e95  cmp     ax, 9
0x180018e99  ja      short loc_180018EA0
0x180018e9b  sub     dl, 30h ; '0'
0x180018e9e  jmp     short loc_180018EC1
0x180018ea0  lea     eax, [rdx-41h]
0x180018ea3  mov     ecx, 5
0x180018ea8  cmp     ax, cx
0x180018eab  ja      short loc_180018EB2
0x180018ead  sub     dl, 37h ; '7'
0x180018eb0  jmp     short loc_180018EC1
0x180018eb2  lea     eax, [rdx-61h]
0x180018eb5  cmp     ax, cx
0x180018eb8  ja      loc_180018D2D
0x180018ebe  sub     dl, 57h ; 'W'
0x180018ec1  shl     r8b, 4
0x180018ec5  or      r8b, dl
0x180018ec8  add     r9d, r13d
0x180018ecb  jmp     short loc_180018E88
0x180018ecd  mov     eax, [rbp+rgIndices]
0x180018ed0  sub     eax, [rbp+plLbound]
0x180018ed3  movsxd  rcx, eax
0x180018ed6  mov     rax, [r14+10h]
0x180018eda  mov     [rcx+rax], r8b
0x180018ede  mov     eax, [rbp+rgIndices]
0x180018ee1  add     eax, r13d
0x180018ee4  jmp     loc_180018E29
0x180018ee9  mov     rcx, [rdi+8]; psa
0x180018eed  call    cs:__imp_SafeArrayUnaccessData
0x180018ef3  test    ebx, ebx
0x180018ef5  jns     short loc_180018F06
0x180018ef7  mov     rcx, [r14+10h]; pMem
0x180018efb  test    rcx, rcx
0x180018efe  jz      short loc_180018F06
0x180018f00  call    cs:__imp_FreeADsMem
0x180018f06  mov     eax, ebx
0x180018f08  add     rsp, 40h
0x180018f0c  pop     r15
0x180018f0e  pop     r14
0x180018f10  pop     r13
0x180018f12  pop     rdi
0x180018f13  pop     rsi
0x180018f14  pop     rbx
0x180018f15  pop     rbp
0x180018f16  retn
```
