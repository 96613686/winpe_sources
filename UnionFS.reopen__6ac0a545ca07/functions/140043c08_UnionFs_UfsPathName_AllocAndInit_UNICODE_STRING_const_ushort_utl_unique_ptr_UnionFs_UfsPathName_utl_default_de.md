# UnionFs::UfsPathName::AllocAndInit(_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)

- ea: `0x140043c08`
- end: `0x140043d56`
- name: `?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `334`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x140040110`
- `0x140043afc`
- `0x140044074`
- `0x1400448c8`
- `0x140044b40`
- `0x140044e54`

## callees

- `0x140043c08`
- `0x14004420c`
- `0x140056c7c`
- `0x140079f68`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140043c4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043cc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043d3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043c4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043cc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043d3a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140043cdc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140043cdc`

## string_xrefs

- `0x140043c77`: `PUSH: Allocating UfsPathName`
- `0x140043c88`: `UnionFs::UfsPathName::AllocAndInit`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathName::AllocAndInit(
        PCUNICODE_STRING SourceString,
        struct _UNICODE_STRING *a2,
        __int64 *a3,
        __int64 a4)
{
  __int64 v4; // rbx
  __int64 v6; // r14
  __int64 MaximumLength; // rcx
  int v10; // edi
  struct _UNICODE_STRING *v11; // rdx
  struct _UNICODE_STRING *v12; // rbx
  _QWORD *v14; // rbx
  struct _UNICODE_STRING *v15; // rdx
  __int64 v16; // rcx
  __int16 v17; // ax
  __int64 v18; // rdi
  const char *v19; // [rsp+28h] [rbp-40h]
  PVOID P; // [rsp+70h] [rbp+8h] BYREF

  v4 = *a3;
  v6 = (unsigned __int16)a2;
  *a3 = 0;
  if ( v4 )
  {
    if ( !*(_BYTE *)(v4 + 16) )
      *(_OWORD *)v4 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v4, a2);
    ExFreePoolWithTag((PVOID)v4, 0);
  }
  MaximumLength = SourceString->MaximumLength;
  P = 0;
  v10 = UnionFs::UfsPathName::AllocEmpty(MaximumLength, &P, a4);
  if ( v10 >= 0 )
  {
    v14 = P;
    RtlCopyUnicodeString((PUNICODE_STRING)P, SourceString);
    v16 = v14[1];
    v14[4] = v16;
    *((_WORD *)v14 + 13) = v6;
    *((_WORD *)v14 + 12) = v6;
    v14[6] = v16 + v6;
    v17 = *(_WORD *)v14 - v6;
    *((_WORD *)v14 + 21) = v17;
    *((_WORD *)v14 + 20) = v17;
    *((_WORD *)v14 + 28) = 0;
    v18 = *a3;
    *a3 = (__int64)v14;
    if ( v18 )
    {
      if ( !*(_BYTE *)(v18 + 16) )
        *(_OWORD *)v18 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v18, v15);
      ExFreePoolWithTag((PVOID)v18, 0);
    }
    return 0;
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v10,
      a4,
      (struct UnionFs::StackEventTracer *)0x5A400130027LL,
      (unsigned __int64)"UnionFs::UfsPathName::AllocAndInit",
      "PUSH: Allocating UfsPathName",
      v19);
    v12 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v12, v11);
      ExFreePoolWithTag(v12, 0);
    }
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x140043c08  push    rbx
0x140043c0a  push    rbp
0x140043c0b  push    rsi
0x140043c0c  push    rdi
0x140043c0d  push    r14
0x140043c0f  push    r15
0x140043c11  sub     rsp, 38h
0x140043c15  mov     rbx, [r8]
0x140043c18  mov     rbp, r9
0x140043c1b  movzx   r14d, dx
0x140043c1f  mov     rsi, r8
0x140043c22  mov     qword ptr [r8], 0
0x140043c29  mov     r15, rcx
0x140043c2c  test    rbx, rbx
0x140043c2f  jz      short loc_140043C56
0x140043c31  cmp     byte ptr [rbx+10h], 0
0x140043c35  jnz     short loc_140043C3D
0x140043c37  xorps   xmm0, xmm0
0x140043c3a  movups  xmmword ptr [rbx], xmm0
0x140043c3d  mov     rcx, rbx; UnicodeString
0x140043c40  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140043c45  xor     edx, edx; Tag
0x140043c47  mov     rcx, rbx; P
0x140043c4a  call    cs:__imp_ExFreePoolWithTag
0x140043c51  nop     dword ptr [rax+rax+00h]
0x140043c56  movzx   ecx, word ptr [r15+2]
0x140043c5b  lea     rdx, [rsp+68h+P]
0x140043c60  mov     r8, rbp
0x140043c63  mov     [rsp+68h+P], 0
0x140043c6c  call    ?AllocEmpty@UfsPathName@UnionFs@@SAJGAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocEmpty(ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140043c71  mov     edi, eax
0x140043c73  test    eax, eax
0x140043c75  jns     short loc_140043CD1
0x140043c77  lea     rax, aPushAllocating_14; "PUSH: Allocating UfsPathName"
0x140043c7e  mov     r8, 5A400130027h; struct UnionFs::StackEventTracer *
0x140043c88  lea     r9, aUnionfsUfspath_42; "UnionFs::UfsPathName::AllocAndInit"
0x140043c8f  mov     [rsp+68h+var_48], rax; char *
0x140043c94  mov     rdx, rbp; int
0x140043c97  mov     ecx, edi; this
0x140043c99  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140043c9e  mov     rbx, [rsp+68h+P]
0x140043ca3  test    rbx, rbx
0x140043ca6  jz      short loc_140043CCD
0x140043ca8  cmp     byte ptr [rbx+10h], 0
0x140043cac  jnz     short loc_140043CB4
0x140043cae  xorps   xmm0, xmm0
0x140043cb1  movups  xmmword ptr [rbx], xmm0
0x140043cb4  mov     rcx, rbx; UnicodeString
0x140043cb7  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140043cbc  xor     edx, edx; Tag
0x140043cbe  mov     rcx, rbx; P
0x140043cc1  call    cs:__imp_ExFreePoolWithTag
0x140043cc8  nop     dword ptr [rax+rax+00h]
0x140043ccd  mov     eax, edi
0x140043ccf  jmp     short loc_140043D48
0x140043cd1  mov     rbx, [rsp+68h+P]
0x140043cd6  mov     rdx, r15; SourceString
0x140043cd9  mov     rcx, rbx; DestinationString
0x140043cdc  call    cs:__imp_RtlCopyUnicodeString
0x140043ce3  nop     dword ptr [rax+rax+00h]
0x140043ce8  mov     rcx, [rbx+8]
0x140043cec  mov     [rbx+20h], rcx
0x140043cf0  mov     [rbx+1Ah], r14w
0x140043cf5  mov     [rbx+18h], r14w
0x140043cfa  lea     rax, [rcx+r14]
0x140043cfe  mov     [rbx+30h], rax
0x140043d02  movzx   eax, word ptr [rbx]
0x140043d05  sub     ax, r14w
0x140043d09  mov     [rbx+2Ah], ax
0x140043d0d  mov     [rbx+28h], ax
0x140043d11  xor     eax, eax
0x140043d13  mov     [rbx+38h], ax
0x140043d17  mov     rdi, [rsi]
0x140043d1a  mov     [rsi], rbx
0x140043d1d  test    rdi, rdi
0x140043d20  jz      short loc_140043D46
0x140043d22  cmp     [rdi+10h], al
0x140043d25  jnz     short loc_140043D2D
0x140043d27  xorps   xmm0, xmm0
0x140043d2a  movups  xmmword ptr [rdi], xmm0
0x140043d2d  mov     rcx, rdi; UnicodeString
0x140043d30  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140043d35  xor     edx, edx; Tag
0x140043d37  mov     rcx, rdi; P
0x140043d3a  call    cs:__imp_ExFreePoolWithTag
0x140043d41  nop     dword ptr [rax+rax+00h]
0x140043d46  xor     eax, eax
0x140043d48  add     rsp, 38h
0x140043d4c  pop     r15
0x140043d4e  pop     r14
0x140043d50  pop     rdi
0x140043d51  pop     rsi
0x140043d52  pop     rbp
0x140043d53  pop     rbx
0x140043d54  retn
```
