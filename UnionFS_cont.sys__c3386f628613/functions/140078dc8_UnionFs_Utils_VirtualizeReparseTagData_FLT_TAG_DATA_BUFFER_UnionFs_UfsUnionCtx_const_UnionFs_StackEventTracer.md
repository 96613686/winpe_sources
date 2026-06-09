# UnionFs::Utils::VirtualizeReparseTagData(_FLT_TAG_DATA_BUFFER * &,UnionFs::UfsUnionCtx const &,UnionFs::StackEventTracer &)

- ea: `0x140078dc8`
- end: `0x1400790e9`
- name: `?VirtualizeReparseTagData@Utils@UnionFs@@YAJAEAPEAU_FLT_TAG_DATA_BUFFER@@AEBVUfsUnionCtx@2@AEAVStackEventTracer@2@@Z`
- size: `801`
- prototype: `int(UnionFs::Utils *__hidden this, struct _FLT_TAG_DATA_BUFFER **, const struct UnionFs::UfsUnionCtx *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140011e00`

## callees

- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140076fd8`
- `0x140078dc8`
- `0x140079c48`
- `0x14007b900`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14007903c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079087`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007903c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079087`
- `ntoskrnl!ExAllocatePool2` at `0x140078f5c`
- `ntoskrnl!ExAllocatePool2` at `0x140078f5c`

## string_xrefs

- `0x140078e7b`: `PUSH: Computing munged substitute name for TagData`
- `0x140078e8c`: `UnionFs::Utils::VirtualizeReparseTagData`
- `0x140078ef3`: `UnionFs::Utils::VirtualizeReparseTagData`
- `0x140079069`: `UnionFs::Utils::VirtualizeReparseTagData`
- `0x1400790a8`: `UnionFs::Utils::VirtualizeReparseTagData`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::VirtualizeReparseTagData(
        PVOID *this,
        struct _FLT_TAG_DATA_BUFFER **a2,
        const struct UnionFs::UfsUnionCtx *a3,
        struct UnionFs::StackEventTracer *a4)
{
  _DWORD *v4; // r9
  int v5; // esi
  int v7; // r14d
  int v8; // r13d
  unsigned __int64 v9; // rax
  struct _UNICODE_STRING *v10; // rdx
  int v11; // ebx
  int v12; // ebx
  unsigned int v13; // eax
  __int64 v14; // r8
  bool v15; // zf
  size_t v16; // rax
  __int64 v17; // rdx
  _WORD *Pool2; // rax
  _WORD *v19; // rdi
  unsigned __int16 v20; // bx
  _DWORD *v21; // rcx
  size_t v22; // r8
  __int64 v23; // rcx
  const char *v25; // [rsp+28h] [rbp-28h]
  void *Src[2]; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING String2; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 v28; // [rsp+90h] [rbp+40h]
  size_t Size; // [rsp+A8h] [rbp+58h]

  v4 = *this;
  v5 = (int)a3;
  v7 = *(_DWORD *)*this;
  String2 = 0;
  if ( v7 == -1610612724 )
  {
    v8 = v4[4];
    if ( (v8 & 1) == 0 )
    {
      String2.Length = *((_WORD *)v4 + 5);
      String2.MaximumLength = *((_WORD *)v4 + 5);
      v9 = ((unsigned __int64)*((unsigned __int16 *)v4 + 4) >> 1) + 10;
      goto LABEL_6;
    }
  }
  else if ( v7 == -1610612733 )
  {
    v8 = 0;
    String2.Length = *((_WORD *)v4 + 5);
    String2.MaximumLength = *((_WORD *)v4 + 5);
    v9 = ((unsigned __int64)*((unsigned __int16 *)v4 + 4) >> 1) + 8;
LABEL_6:
    String2.Buffer = (PWSTR)v4 + v9;
    *(_OWORD *)Src = 0;
    v11 = UnionFs::Utils::ScratchRelativizeSubstituteName(&String2, (__int64)a2, (PUNICODE_STRING)Src, a3);
    if ( v11 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v11,
        v5,
        (struct UnionFs::StackEventTracer *)0x6C300210C8FLL,
        (unsigned __int64)"UnionFs::Utils::VirtualizeReparseTagData",
        "PUSH: Computing munged substitute name for TagData",
        v25);
LABEL_29:
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)Src, v10);
      return (unsigned int)v11;
    }
    if ( !Src[1] )
    {
LABEL_9:
      v11 = 0;
      goto LABEL_29;
    }
    v12 = 20;
    if ( v7 == -1610612724 )
    {
      v13 = 2 * LOWORD(Src[0]);
      if ( v13 > 0xFFFF )
      {
        v14 = 0x6CC00210CA2LL;
LABEL_14:
        v11 = -1073741675;
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)0xC0000095LL,
          v5,
          (struct UnionFs::StackEventTracer *)v14,
          (unsigned __int64)"UnionFs::Utils::VirtualizeReparseTagData",
          "API: Arithmetic error",
          v25);
        goto LABEL_29;
      }
    }
    else
    {
      v12 = 16;
      if ( (unsigned __int16)(LOWORD(Src[0]) + 2) < LOWORD(Src[0]) )
      {
        v14 = 0x6CD00210CACLL;
        goto LABEL_14;
      }
      v13 = 2 * (unsigned __int16)(LOWORD(Src[0]) + 2);
      if ( v13 > 0xFFFF )
      {
        v14 = 0x6CE00210CB1LL;
        goto LABEL_14;
      }
    }
    v28 = v13;
    v15 = v12 + (unsigned __int16)v13 == 0;
    v16 = v12 + (unsigned int)(unsigned __int16)v13;
    v17 = (unsigned int)v16;
    Size = v16;
    if ( v15 )
      v17 = 1;
    Pool2 = (_WORD *)ExAllocatePool2(64, v17, 1651656277);
    v19 = Pool2;
    if ( !Pool2 )
    {
      v11 = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        v5,
        (struct UnionFs::StackEventTracer *)0x6C400210CBFLL,
        (unsigned __int64)"UnionFs::Utils::VirtualizeReparseTagData",
        "ORIGIN: Allocating virtualized tag buffer",
        v25);
      goto LABEL_29;
    }
    memset(Pool2, 0, Size);
    *(_DWORD *)v19 = v7;
    v20 = v28 + v12 - 8;
    v19[3] = *((_WORD *)*this + 3);
    if ( v20 < v28 )
    {
      v19[2] = -1;
      v11 = -1073741675;
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)0xC0000095LL,
        v5,
        (struct UnionFs::StackEventTracer *)0x6BD00210CCBLL,
        (unsigned __int64)"UnionFs::Utils::VirtualizeReparseTagData",
        "API: Arithmetic error",
        v25);
      ExFreePoolWithTag(v19, 0);
      goto LABEL_29;
    }
    v19[2] = v20;
    v21 = v19 + 8;
    if ( v7 == -1610612724 )
    {
      *v21 = v8;
      v19[6] = 0;
      v19[7] = Src[0];
      v19[4] = Src[0];
      v19[5] = Src[0];
      memmove(v19 + 10, Src[1], LOWORD(Src[0]));
      v22 = LOWORD(Src[0]);
      v23 = LOWORD(Src[0]) + 20LL;
    }
    else
    {
      v19[4] = 0;
      v19[5] = Src[0];
      v19[6] = LOWORD(Src[0]) + 2;
      v19[7] = Src[0];
      memmove(v21, Src[1], LOWORD(Src[0]));
      v22 = LOWORD(Src[0]);
      v23 = LOWORD(Src[0]) + 18LL;
    }
    memmove((char *)v19 + v23, Src[1], v22);
    ExFreePoolWithTag(*this, 0);
    *this = v19;
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x140078dc8  mov     [rsp-38h+arg_8], rbx
0x140078dcd  push    rbp
0x140078dce  push    rsi
0x140078dcf  push    rdi
0x140078dd0  push    r12
0x140078dd2  push    r13
0x140078dd4  push    r14
0x140078dd6  push    r15
0x140078dd8  mov     rbp, rsp
0x140078ddb  sub     rsp, 50h
0x140078ddf  mov     r9, [rcx]
0x140078de2  mov     edi, 0A000000Ch
0x140078de7  xorps   xmm0, xmm0
0x140078dea  mov     rsi, r8
0x140078ded  mov     r12, rcx
0x140078df0  mov     r14d, [r9]
0x140078df3  movdqa  xmmword ptr [rbp+String2.Length], xmm0
0x140078df8  cmp     r14d, edi
0x140078dfb  jnz     short loc_140078E2B
0x140078dfd  mov     r13d, [r9+10h]
0x140078e01  test    r13b, 1
0x140078e05  jnz     loc_1400790CE
0x140078e0b  movzx   eax, word ptr [r9+0Ah]
0x140078e10  mov     [rbp+String2.Length], ax
0x140078e14  movzx   eax, word ptr [r9+0Ah]
0x140078e19  mov     [rbp+String2.MaximumLength], ax
0x140078e1d  movzx   eax, word ptr [r9+8]
0x140078e22  shr     rax, 1
0x140078e25  add     rax, 0Ah
0x140078e29  jmp     short loc_140078E59
0x140078e2b  cmp     r14d, 0A0000003h
0x140078e32  jnz     loc_1400790CE
0x140078e38  movzx   eax, word ptr [r9+0Ah]
0x140078e3d  xor     r13d, r13d
0x140078e40  mov     [rbp+String2.Length], ax
0x140078e44  movzx   eax, word ptr [r9+0Ah]
0x140078e49  mov     [rbp+String2.MaximumLength], ax
0x140078e4d  movzx   eax, word ptr [r9+8]
0x140078e52  shr     rax, 1
0x140078e55  add     rax, 8
0x140078e59  lea     rax, [r9+rax*2]
0x140078e5d  mov     r9, rsi; struct UnionFs::StackEventTracer *
0x140078e60  lea     r8, [rbp+Src]; UnicodeString
0x140078e64  mov     [rbp+String2.Buffer], rax
0x140078e68  lea     rcx, [rbp+String2]; String2
0x140078e6c  movups  xmmword ptr [rbp+Src], xmm0
0x140078e70  call    ?ScratchRelativizeSubstituteName@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBVUfsUnionCtx@2@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::ScratchRelativizeSubstituteName(_UNICODE_STRING const &,UnionFs::UfsUnionCtx const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)
0x140078e75  mov     ebx, eax
0x140078e77  test    eax, eax
0x140078e79  jns     short loc_140078EA7
0x140078e7b  lea     rax, aPushComputingM_0; "PUSH: Computing munged substitute name "...
0x140078e82  mov     r8, 6C300210C8Fh; struct UnionFs::StackEventTracer *
0x140078e8c  lea     r9, aUnionfsUtilsVi; "UnionFs::Utils::VirtualizeReparseTagDat"...
0x140078e93  mov     [rsp+50h+var_30], rax; char *
0x140078e98  mov     rdx, rsi; int
0x140078e9b  mov     ecx, ebx; this
0x140078e9d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140078ea2  jmp     loc_1400790C1
0x140078ea7  cmp     [rbp+Src+8], 0
0x140078eac  jnz     short loc_140078EB5
0x140078eae  xor     ebx, ebx
0x140078eb0  jmp     loc_1400790C1
0x140078eb5  mov     ebx, 14h
0x140078eba  cmp     r14d, edi
0x140078ebd  lea     eax, [rbx-4]
0x140078ec0  cmovnz  ebx, eax
0x140078ec3  jnz     short loc_140078F07
0x140078ec5  movzx   eax, word ptr [rbp+Src]
0x140078ec9  mov     r15d, 0FFFFh
0x140078ecf  add     eax, eax
0x140078ed1  cmp     eax, r15d
0x140078ed4  jbe     short loc_140078F3D
0x140078ed6  mov     r8, 6CC00210CA2h; struct UnionFs::StackEventTracer *
0x140078ee0  lea     rax, aApiArithmeticE; "API: Arithmetic error"
0x140078ee7  mov     ebx, 0C0000095h
0x140078eec  mov     ecx, ebx; this
0x140078eee  mov     [rsp+50h+var_30], rax; char *
0x140078ef3  lea     r9, aUnionfsUtilsVi; "UnionFs::Utils::VirtualizeReparseTagDat"...
0x140078efa  mov     rdx, rsi; int
0x140078efd  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140078f02  jmp     loc_1400790C1
0x140078f07  movzx   eax, word ptr [rbp+Src]
0x140078f0b  add     ax, 2
0x140078f0f  cmp     ax, word ptr [rbp+Src]
0x140078f13  jnb     short loc_140078F21
0x140078f15  mov     r8, 6CD00210CACh
0x140078f1f  jmp     short loc_140078EE0
0x140078f21  movzx   eax, ax
0x140078f24  mov     r15d, 0FFFFh
0x140078f2a  add     eax, eax
0x140078f2c  cmp     eax, r15d
0x140078f2f  jbe     short loc_140078F3D
0x140078f31  mov     r8, 6CE00210CB1h
0x140078f3b  jmp     short loc_140078EE0
0x140078f3d  movzx   eax, ax
0x140078f40  mov     r8d, 62724655h
0x140078f46  mov     [rbp+arg_0], eax
0x140078f49  add     eax, ebx
0x140078f4b  mov     edx, eax
0x140078f4d  mov     [rbp+Size], rax
0x140078f51  mov     eax, 1
0x140078f56  cmovz   edx, eax
0x140078f59  lea     ecx, [rax+3Fh]
0x140078f5c  call    cs:__imp_ExAllocatePool2
0x140078f63  nop     dword ptr [rax+rax+00h]
0x140078f68  mov     rdi, rax
0x140078f6b  test    rax, rax
0x140078f6e  jz      loc_140079095
0x140078f74  mov     r8, [rbp+Size]; Size
0x140078f78  xor     edx, edx; Val
0x140078f7a  mov     rcx, rax; void *
0x140078f7d  call    memset
0x140078f82  mov     eax, [rbp+arg_0]
0x140078f85  sub     bx, 8
0x140078f89  mov     [rdi], r14d
0x140078f8c  add     bx, ax
0x140078f8f  mov     rcx, [r12]
0x140078f93  movzx   edx, word ptr [rcx+6]
0x140078f97  mov     [rdi+6], dx
0x140078f9b  cmp     bx, ax
0x140078f9e  jb      loc_140079051
0x140078fa4  xor     eax, eax
0x140078fa6  mov     [rdi+4], bx
0x140078faa  lea     rcx, [rdi+10h]; void *
0x140078fae  cmp     r14d, 0A000000Ch
0x140078fb5  jnz     short loc_140078FF3
0x140078fb7  mov     [rcx], r13d
0x140078fba  lea     rcx, [rdi+14h]; void *
0x140078fbe  mov     [rdi+0Ch], ax
0x140078fc2  movzx   eax, word ptr [rbp+Src]
0x140078fc6  mov     [rdi+0Eh], ax
0x140078fca  movzx   eax, word ptr [rbp+Src]
0x140078fce  mov     [rdi+8], ax
0x140078fd2  movzx   eax, word ptr [rbp+Src]
0x140078fd6  mov     [rdi+0Ah], ax
0x140078fda  movzx   r8d, word ptr [rbp+Src]; Size
0x140078fdf  mov     rdx, [rbp+Src+8]; Src
0x140078fe3  call    memmove
0x140078fe8  movzx   r8d, word ptr [rbp+Src]
0x140078fed  lea     rcx, [r8+14h]
0x140078ff1  jmp     short loc_14007902A
0x140078ff3  mov     [rdi+8], ax
0x140078ff7  movzx   eax, word ptr [rbp+Src]
0x140078ffb  mov     [rdi+0Ah], ax
0x140078fff  movzx   eax, word ptr [rbp+Src]
0x140079003  add     ax, 2
0x140079007  mov     [rdi+0Ch], ax
0x14007900b  movzx   eax, word ptr [rbp+Src]
0x14007900f  mov     [rdi+0Eh], ax
0x140079013  movzx   r8d, word ptr [rbp+Src]; Size
0x140079018  mov     rdx, [rbp+Src+8]; Src
0x14007901c  call    memmove
0x140079021  movzx   r8d, word ptr [rbp+Src]; Size
0x140079026  lea     rcx, [r8+12h]
0x14007902a  mov     rdx, [rbp+Src+8]; Src
0x14007902e  add     rcx, rdi; void *
0x140079031  call    memmove
0x140079036  mov     rcx, [r12]; P
0x14007903a  xor     edx, edx; Tag
0x14007903c  call    cs:__imp_ExFreePoolWithTag
0x140079043  nop     dword ptr [rax+rax+00h]
0x140079048  mov     [r12], rdi
0x14007904c  jmp     loc_140078EAE
0x140079051  lea     rax, aApiArithmeticE; "API: Arithmetic error"
0x140079058  mov     [rdi+4], r15w
0x14007905d  mov     ebx, 0C0000095h
0x140079062  mov     [rsp+50h+var_30], rax; char *
0x140079067  mov     ecx, ebx; this
0x140079069  lea     r9, aUnionfsUtilsVi; "UnionFs::Utils::VirtualizeReparseTagDat"...
0x140079070  mov     r8, 6BD00210CCBh; struct UnionFs::StackEventTracer *
0x14007907a  mov     rdx, rsi; int
0x14007907d  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140079082  xor     edx, edx; Tag
0x140079084  mov     rcx, rdi; P
0x140079087  call    cs:__imp_ExFreePoolWithTag
0x14007908e  nop     dword ptr [rax+rax+00h]
0x140079093  jmp     short loc_1400790C1
0x140079095  lea     rax, aOriginAllocati_39; "ORIGIN: Allocating virtualized tag buff"...
0x14007909c  mov     ebx, 0C000009Ah
0x1400790a1  mov     ecx, ebx; this
0x1400790a3  mov     [rsp+50h+var_30], rax; char *
0x1400790a8  lea     r9, aUnionfsUtilsVi; "UnionFs::Utils::VirtualizeReparseTagDat"...
0x1400790af  mov     r8, 6C400210CBFh; struct UnionFs::StackEventTracer *
0x1400790b9  mov     rdx, rsi; int
0x1400790bc  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400790c1  lea     rcx, [rbp+Src]; UnicodeString
0x1400790c5  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400790ca  mov     eax, ebx
0x1400790cc  jmp     short loc_1400790D0
0x1400790ce  xor     eax, eax
0x1400790d0  mov     rbx, [rsp+50h+arg_8]
0x1400790d8  add     rsp, 50h
0x1400790dc  pop     r15
0x1400790de  pop     r14
0x1400790e0  pop     r13
0x1400790e2  pop     r12
0x1400790e4  pop     rdi
0x1400790e5  pop     rsi
0x1400790e6  pop     rbp
0x1400790e7  retn
```
