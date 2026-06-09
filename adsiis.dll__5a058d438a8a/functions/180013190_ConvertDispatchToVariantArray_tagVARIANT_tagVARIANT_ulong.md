# ConvertDispatchToVariantArray(tagVARIANT,tagVARIANT * *,ulong *)

- ea: `0x180013190`
- end: `0x1800132f6`
- name: `?ConvertDispatchToVariantArray@@YAJUtagVARIANT@@PEAPEAU1@PEAK@Z`
- size: `358`
- prototype: `__int64 __fastcall(VARIANTARG *pvargSrc, struct tagVARIANT **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800103bc`

## callees

- `0x180013190`
- `0x18001beb8`

## import_xrefs

- `msvcrt!wcsstr` at `0x18001321b`
- `msvcrt!wcsstr` at `0x180013277`
- `msvcrt!wcsstr` at `0x18001321b`
- `msvcrt!wcsstr` at `0x180013277`
- `OLEAUT32!__imp_VariantInit` at `0x1800131be`
- `OLEAUT32!__imp_VariantInit` at `0x1800132a1`
- `OLEAUT32!__imp_VariantInit` at `0x1800131be`
- `OLEAUT32!__imp_VariantInit` at `0x1800132a1`
- `OLEAUT32!__imp_VariantClear` at `0x1800132dd`
- `OLEAUT32!__imp_VariantClear` at `0x1800132dd`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800131cc`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800131cc`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800131f0`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800131f0`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18001324b`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18001324b`

## pseudocode

```c
__int64 __fastcall ConvertDispatchToVariantArray(VARIANTARG *pvargSrc, struct tagVARIANT **a2, unsigned int *a3)
{
  HRESULT v6; // ebx
  const wchar_t *bstrVal; // rsi
  unsigned int v8; // edi
  wchar_t *v9; // rax
  wchar_t *v10; // rdx
  wchar_t *v11; // rcx
  struct tagVARIANT *v12; // r15
  const wchar_t *v13; // rsi
  int v14; // ebp
  wchar_t *v15; // r14
  VARIANTARG *v16; // rbx
  VARIANTARG pvarg; // [rsp+20h] [rbp-68h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v6 = VariantCopyInd(&pvarg, pvargSrc);
  if ( v6 >= 0 )
  {
    v6 = VariantChangeType(&pvarg, &pvarg, 0, 8u);
    if ( v6 >= 0 )
    {
      bstrVal = pvarg.bstrVal;
      v8 = 0;
      if ( !pvarg.llVal )
        goto LABEL_20;
      do
      {
        v9 = wcsstr(bstrVal, L",");
        ++v8;
        v10 = v9 + 1;
        v11 = v9 + 1;
        if ( !v9 )
        {
          v10 = 0;
          v11 = (wchar_t *)bstrVal;
        }
        bstrVal = v11;
      }
      while ( v10 );
      if ( v8 )
      {
        v12 = (struct tagVARIANT *)AllocADsMem(24 * v8);
        if ( v12 )
        {
          v13 = pvarg.bstrVal;
          v14 = 0;
          while ( v13 )
          {
            v15 = wcsstr(v13, L",");
            if ( v15 )
              *v15++ = 0;
            if ( *v13 )
            {
              v16 = &v12[v14];
              VariantInit(v16);
              v16->vt = 8;
              v6 = ADsAllocString(v13, &v16->decVal.Lo32);
              if ( v6 < 0 )
                goto LABEL_21;
              ++v14;
            }
            else
            {
              --v8;
            }
            v13 = v15;
          }
          *a2 = v12;
          *a3 = v8;
        }
        else
        {
          v6 = -2147024882;
        }
      }
      else
      {
LABEL_20:
        v6 = -2147467259;
      }
    }
  }
LABEL_21:
  VariantClear(&pvarg);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180013190  push    rbx
0x180013192  push    rbp
0x180013193  push    rsi
0x180013194  push    rdi
0x180013195  push    r12
0x180013197  push    r13
0x180013199  push    r14
0x18001319b  push    r15
0x18001319d  sub     rsp, 48h
0x1800131a1  mov     rbx, rcx
0x1800131a4  xorps   xmm0, xmm0
0x1800131a7  xor     eax, eax
0x1800131a9  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1800131ae  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x1800131b3  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x1800131b8  mov     r12, r8
0x1800131bb  mov     r13, rdx
0x1800131be  call    cs:__imp_VariantInit
0x1800131c4  mov     rdx, rbx; pvargSrc
0x1800131c7  lea     rcx, [rsp+88h+pvarg]; pvarDest
0x1800131cc  call    cs:__imp_VariantCopyInd
0x1800131d2  xor     r14d, r14d
0x1800131d5  mov     ebx, eax
0x1800131d7  test    eax, eax
0x1800131d9  js      loc_1800132D8
0x1800131df  lea     r9d, [r14+8]; vt
0x1800131e3  xor     r8d, r8d; wFlags
0x1800131e6  lea     rdx, [rsp+88h+pvarg]; pvarSrc
0x1800131eb  lea     rcx, [rsp+88h+pvarg]; pvargDest
0x1800131f0  call    cs:__imp_VariantChangeType
0x1800131f6  mov     ebx, eax
0x1800131f8  test    eax, eax
0x1800131fa  js      loc_1800132D8
0x180013200  mov     rsi, qword ptr [rsp+88h+pvarg+8]
0x180013205  mov     edi, r14d
0x180013208  test    rsi, rsi
0x18001320b  jz      loc_1800132D3
0x180013211  lea     rdx, Delimiter; ","
0x180013218  mov     rcx, rsi; Str
0x18001321b  call    cs:__imp_wcsstr
0x180013221  inc     edi
0x180013223  test    rax, rax
0x180013226  lea     rdx, [rax+2]
0x18001322a  mov     rcx, rdx
0x18001322d  cmovz   rdx, rax
0x180013231  cmovz   rcx, rsi
0x180013235  mov     rsi, rcx
0x180013238  test    rdx, rdx
0x18001323b  jnz     short loc_180013211
0x18001323d  test    edi, edi
0x18001323f  jz      loc_1800132D3
0x180013245  lea     ecx, [rdi+rdi*2]
0x180013248  shl     ecx, 3; cb
0x18001324b  call    cs:__imp_AllocADsMem
0x180013251  mov     r15, rax
0x180013254  test    rax, rax
0x180013257  jnz     short loc_180013260
0x180013259  mov     ebx, 8007000Eh
0x18001325e  jmp     short loc_1800132D8
0x180013260  mov     rsi, qword ptr [rsp+88h+pvarg+8]
0x180013265  mov     ebp, r14d
0x180013268  test    rsi, rsi
0x18001326b  jz      short loc_1800132C9
0x18001326d  lea     rdx, Delimiter; ","
0x180013274  mov     rcx, rsi; Str
0x180013277  call    cs:__imp_wcsstr
0x18001327d  mov     r14, rax
0x180013280  xor     eax, eax
0x180013282  test    r14, r14
0x180013285  jz      short loc_18001328F
0x180013287  mov     [r14], ax
0x18001328b  add     r14, 2
0x18001328f  cmp     [rsi], ax
0x180013292  jz      short loc_1800132C2
0x180013294  mov     edx, ebp
0x180013296  lea     r8, [rdx+rdx*2]
0x18001329a  lea     rbx, [r15+r8*8]
0x18001329e  mov     rcx, rbx; pvarg
0x1800132a1  call    cs:__imp_VariantInit
0x1800132a7  lea     rdx, [rbx+8]
0x1800132ab  mov     word ptr [rbx], 8
0x1800132b0  mov     rcx, rsi
0x1800132b3  call    ADsAllocString
0x1800132b8  mov     ebx, eax
0x1800132ba  test    eax, eax
0x1800132bc  js      short loc_1800132D8
0x1800132be  inc     ebp
0x1800132c0  jmp     short loc_1800132C4
0x1800132c2  dec     edi
0x1800132c4  mov     rsi, r14
0x1800132c7  jmp     short loc_180013268
0x1800132c9  mov     [r13+0], r15
0x1800132cd  mov     [r12], edi
0x1800132d1  jmp     short loc_1800132D8
0x1800132d3  mov     ebx, 80004005h
0x1800132d8  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1800132dd  call    cs:__imp_VariantClear
0x1800132e3  mov     eax, ebx
0x1800132e5  add     rsp, 48h
0x1800132e9  pop     r15
0x1800132eb  pop     r14
0x1800132ed  pop     r13
0x1800132ef  pop     r12
0x1800132f1  pop     rdi
0x1800132f2  pop     rsi
0x1800132f3  pop     rbp
0x1800132f4  pop     rbx
0x1800132f5  retn
```
