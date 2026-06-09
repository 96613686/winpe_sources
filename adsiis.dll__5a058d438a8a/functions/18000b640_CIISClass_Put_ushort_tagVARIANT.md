# CIISClass::Put(ushort *,tagVARIANT)

- ea: `0x18000b640`
- end: `0x18000b784`
- name: `?Put@CIISClass@@UEAAJPEAGUtagVARIANT@@@Z`
- size: `324`
- prototype: `int(CIISClass *__hidden this, unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000b640`
- `0x18000c0a8`
- `0x180012fc8`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000b689`
- `OLEAUT32!__imp_VariantInit` at `0x18000b689`
- `OLEAUT32!__imp_VariantClear` at `0x18000b769`
- `OLEAUT32!__imp_VariantClear` at `0x18000b769`
- `OLEAUT32!__imp_VariantCopy` at `0x18000b75d`
- `OLEAUT32!__imp_VariantCopy` at `0x18000b75d`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000b6b0`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000b6b0`

## pseudocode

```c
__int64 __fastcall CIISClass::Put(CIISClass *this, unsigned __int16 *a2, struct tagVARIANT *a3)
{
  HRESULT v7; // ebx
  VARIANTARG *v8; // rcx
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  unsigned int v10; // [rsp+68h] [rbp+28h] BYREF
  unsigned int v11; // [rsp+78h] [rbp+38h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v11 = 0;
  v10 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v7 = ValidateClassObjProps(a2, &v11, &v10);
  if ( v7 >= 0 )
  {
    v7 = VariantCopyInd(&pvarg, a3);
    if ( v7 >= 0 )
    {
      if ( v10 == 7 )
      {
        if ( pvarg.vt && ((pvarg.vt & 0xFFF) != 0xC || (pvarg.vt & 0x2000) == 0) )
        {
LABEL_14:
          v7 = -2147463156;
          goto LABEL_21;
        }
        v8 = (VARIANTARG *)((char *)this + 80);
      }
      else
      {
        if ( v10 != 12 )
        {
          if ( v10 == 13 )
          {
            v7 = CheckVariantDataType(a3, 0xBu);
            if ( v7 >= 0 )
              *((_WORD *)this + 76) = a3->iVal == -1;
          }
          else
          {
            v7 = -2147463162;
          }
          goto LABEL_21;
        }
        if ( pvarg.vt && ((pvarg.vt & 0xFFF) != 0xC || (pvarg.vt & 0x2000) == 0) )
          goto LABEL_14;
        v8 = (VARIANTARG *)((char *)this + 128);
      }
      v7 = VariantCopy(v8, &pvarg);
    }
  }
LABEL_21:
  VariantClear(&pvarg);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b640  mov     [rsp-18h+arg_0], rbx
0x18000b645  mov     [rsp-18h+arg_10], rsi
0x18000b64a  push    rbp
0x18000b64b  push    rdi
0x18000b64c  push    r14
0x18000b64e  mov     rbp, rsp
0x18000b651  sub     rsp, 40h
0x18000b655  xor     r14d, r14d
0x18000b658  mov     rdi, r8
0x18000b65b  mov     rbx, rdx
0x18000b65e  mov     rsi, rcx
0x18000b661  test    rdx, rdx
0x18000b664  jnz     short loc_18000B670
0x18000b666  mov     eax, 80004003h
0x18000b66b  jmp     loc_18000B771
0x18000b670  xorps   xmm0, xmm0
0x18000b673  mov     [rbp+arg_18], r14d
0x18000b677  xor     eax, eax
0x18000b679  mov     [rbp+arg_8], r14d
0x18000b67d  lea     rcx, [rbp+pvarg]; pvarg
0x18000b681  mov     qword ptr [rbp+pvarg+10h], rax
0x18000b685  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000b689  call    cs:__imp_VariantInit
0x18000b68f  lea     r8, [rbp+arg_8]; unsigned int *
0x18000b693  mov     rcx, rbx; String2
0x18000b696  lea     rdx, [rbp+arg_18]; unsigned int *
0x18000b69a  call    ?ValidateClassObjProps@@YAJPEAGPEAK1@Z; ValidateClassObjProps(ushort *,ulong *,ulong *)
0x18000b69f  mov     ebx, eax
0x18000b6a1  test    eax, eax
0x18000b6a3  js      loc_18000B765
0x18000b6a9  mov     rdx, rdi; pvargSrc
0x18000b6ac  lea     rcx, [rbp+pvarg]; pvarDest
0x18000b6b0  call    cs:__imp_VariantCopyInd
0x18000b6b6  mov     ebx, eax
0x18000b6b8  test    eax, eax
0x18000b6ba  js      loc_18000B765
0x18000b6c0  mov     eax, [rbp+arg_8]
0x18000b6c3  sub     eax, 7
0x18000b6c6  jz      short loc_18000B734
0x18000b6c8  sub     eax, 5
0x18000b6cb  jz      short loc_18000B703
0x18000b6cd  cmp     eax, 1
0x18000b6d0  jz      short loc_18000B6DC
0x18000b6d2  mov     ebx, 80005006h
0x18000b6d7  jmp     loc_18000B765
0x18000b6dc  mov     edx, 0Bh; unsigned __int16
0x18000b6e1  mov     rcx, rdi; pvarSrc
0x18000b6e4  call    ?CheckVariantDataType@@YAJPEAUtagVARIANT@@G@Z; CheckVariantDataType(tagVARIANT *,ushort)
0x18000b6e9  mov     ebx, eax
0x18000b6eb  test    eax, eax
0x18000b6ed  js      short loc_18000B765
0x18000b6ef  cmp     word ptr [rdi+8], 0FFFFh
0x18000b6f4  mov     eax, r14d
0x18000b6f7  setz    al
0x18000b6fa  mov     [rsi+98h], ax
0x18000b701  jmp     short loc_18000B765
0x18000b703  movzx   ecx, word ptr [rbp+pvarg]
0x18000b707  test    cx, cx
0x18000b70a  jz      short loc_18000B72B
0x18000b70c  movzx   eax, cx
0x18000b70f  mov     edx, 0FFFh
0x18000b714  and     ax, dx
0x18000b717  cmp     ax, 0Ch
0x18000b71b  jnz     short loc_18000B724
0x18000b71d  bt      cx, 0Dh
0x18000b722  jb      short loc_18000B72B
0x18000b724  mov     ebx, 8000500Ch
0x18000b729  jmp     short loc_18000B765
0x18000b72b  lea     rcx, [rsi+80h]
0x18000b732  jmp     short loc_18000B759
0x18000b734  movzx   ecx, word ptr [rbp+pvarg]
0x18000b738  test    cx, cx
0x18000b73b  jz      short loc_18000B755
0x18000b73d  movzx   eax, cx
0x18000b740  mov     edx, 0FFFh
0x18000b745  and     ax, dx
0x18000b748  cmp     ax, 0Ch
0x18000b74c  jnz     short loc_18000B724
0x18000b74e  bt      cx, 0Dh
0x18000b753  jnb     short loc_18000B724
0x18000b755  lea     rcx, [rsi+50h]; pvargDest
0x18000b759  lea     rdx, [rbp+pvarg]; pvargSrc
0x18000b75d  call    cs:__imp_VariantCopy
0x18000b763  mov     ebx, eax
0x18000b765  lea     rcx, [rbp+pvarg]; pvarg
0x18000b769  call    cs:__imp_VariantClear
0x18000b76f  mov     eax, ebx
0x18000b771  mov     rbx, [rsp+40h+arg_0]
0x18000b776  mov     rsi, [rsp+40h+arg_10]
0x18000b77b  add     rsp, 40h
0x18000b77f  pop     r14
0x18000b781  pop     rdi
0x18000b782  pop     rbp
0x18000b783  retn
```
