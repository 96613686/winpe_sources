# UnionFs::Utils::VirtualizeReparseData(utl::unique_ptr<_REPARSE_DATA_BUFFER,utl::default_delete<_REPARSE_DATA_BUFFER>> &,ulong &,UnionFs::UfsUnionCtx const &,UnionFs::StackEventTracer &)

- ea: `0x140078dc0`
- end: `0x1400790e8`
- name: `?VirtualizeReparseData@Utils@UnionFs@@YAJAEAV?$unique_ptr@U_REPARSE_DATA_BUFFER@@U?$default_delete@U_REPARSE_DATA_BUFFER@@@utl@@@utl@@AEAKAEBVUfsUnionCtx@2@AEAVStackEventTracer@2@@Z`
- size: `808`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x140040110`
- `0x14006c3ec`

## callees

- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140067ad8`
- `0x1400771d8`
- `0x140078dc0`
- `0x140079f68`
- `0x14007bc40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14007905f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400790b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007905f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400790b4`

## string_xrefs

- `0x140078e87`: `PUSH: Computing munged substitute name`
- `0x140078f68`: `ORIGIN: Allocating virtualized reparse buffer`
- `0x140078e98`: `UnionFs::Utils::VirtualizeReparseData`
- `0x140078eff`: `UnionFs::Utils::VirtualizeReparseData`
- `0x140078f7b`: `UnionFs::Utils::VirtualizeReparseData`
- `0x140079091`: `UnionFs::Utils::VirtualizeReparseData`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::VirtualizeReparseData(
        int **a1,
        unsigned int *a2,
        __int64 a3,
        struct UnionFs::StackEventTracer *a4)
{
  int *v4; // r10
  int v5; // esi
  int v7; // r14d
  unsigned __int64 v8; // rax
  struct _UNICODE_STRING *v9; // rdx
  int v10; // ebx
  int v11; // ebx
  unsigned int v12; // eax
  __int64 v13; // r8
  unsigned __int16 v14; // r13
  _WORD *v15; // rdi
  unsigned __int16 v16; // bx
  _DWORD *v17; // rcx
  size_t v18; // r8
  __int64 v19; // rcx
  int *v20; // rcx
  const char *v22; // [rsp+28h] [rbp-38h]
  unsigned int v23; // [rsp+30h] [rbp-30h]
  PVOID P; // [rsp+38h] [rbp-28h] BYREF
  void *Src[2]; // [rsp+40h] [rbp-20h] BYREF
  UNICODE_STRING String2; // [rsp+50h] [rbp-10h] BYREF
  int v27; // [rsp+A0h] [rbp+40h]

  v4 = *a1;
  v5 = (int)a4;
  v7 = **a1;
  String2 = 0;
  if ( v7 == -1610612724 )
  {
    v27 = v4[4];
    if ( (v27 & 1) == 0 )
    {
      String2.Length = *((_WORD *)v4 + 5);
      String2.MaximumLength = *((_WORD *)v4 + 5);
      v8 = ((unsigned __int64)*((unsigned __int16 *)v4 + 4) >> 1) + 10;
      goto LABEL_6;
    }
  }
  else if ( v7 == -1610612733 )
  {
    String2.Length = *((_WORD *)v4 + 5);
    String2.MaximumLength = *((_WORD *)v4 + 5);
    v8 = ((unsigned __int64)*((unsigned __int16 *)v4 + 4) >> 1) + 8;
    v27 = 0;
LABEL_6:
    String2.Buffer = (PWSTR)v4 + v8;
    *(_OWORD *)Src = 0;
    v10 = UnionFs::Utils::ScratchRelativizeSubstituteName(&String2, a3, (PUNICODE_STRING)Src, a4);
    if ( v10 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v10,
        v5,
        (struct UnionFs::StackEventTracer *)0x6C700210C3CLL,
        (unsigned __int64)"UnionFs::Utils::VirtualizeReparseData",
        "PUSH: Computing munged substitute name",
        v22);
LABEL_30:
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)Src, v9);
      return (unsigned int)v10;
    }
    if ( !Src[1] )
    {
LABEL_9:
      v10 = 0;
      goto LABEL_30;
    }
    v11 = 20;
    if ( v7 == -1610612724 )
    {
      v12 = 2 * LOWORD(Src[0]);
      if ( v12 > 0xFFFF )
      {
        v13 = 0x6C900210C4FLL;
LABEL_14:
        v10 = -1073741675;
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)0xC0000095LL,
          v5,
          (struct UnionFs::StackEventTracer *)v13,
          (unsigned __int64)"UnionFs::Utils::VirtualizeReparseData",
          "API: Arithmetic error",
          v22);
        goto LABEL_30;
      }
    }
    else
    {
      v11 = 16;
      if ( (unsigned __int16)(LOWORD(Src[0]) + 2) < LOWORD(Src[0]) )
      {
        v13 = 0x6CA00210C59LL;
        goto LABEL_14;
      }
      v12 = 2 * (unsigned __int16)(LOWORD(Src[0]) + 2);
      if ( v12 > 0xFFFF )
      {
        v13 = 0x6CB00210C5ELL;
        goto LABEL_14;
      }
    }
    v14 = v12;
    v23 = v11 + (unsigned __int16)v12;
    utl::make_unique_pool<enum gsl::byte [0],256,1651656277,0>(&P, v23);
    v15 = P;
    if ( !P )
    {
      v10 = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        v5,
        (struct UnionFs::StackEventTracer *)0x6C800210C6CLL,
        (unsigned __int64)"UnionFs::Utils::VirtualizeReparseData",
        "ORIGIN: Allocating virtualized reparse buffer",
        v22);
      goto LABEL_30;
    }
    *(_DWORD *)P = v7;
    v16 = v14 + v11 - 8;
    if ( v16 < v14 )
    {
      v15[2] = -1;
      v10 = -1073741675;
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)0xC0000095LL,
        v5,
        (struct UnionFs::StackEventTracer *)0x6CF00210C77LL,
        (unsigned __int64)"UnionFs::Utils::VirtualizeReparseData",
        "API: Arithmetic error",
        v22);
      if ( v15 )
        ExFreePoolWithTag(v15, 0);
      goto LABEL_30;
    }
    v15[2] = v16;
    v15[3] = *((_WORD *)*a1 + 3);
    v17 = v15 + 8;
    if ( v7 == -1610612724 )
    {
      *v17 = v27;
      v15[6] = 0;
      v15[7] = Src[0];
      v15[4] = Src[0];
      v15[5] = Src[0];
      memmove(v15 + 10, Src[1], LOWORD(Src[0]));
      v18 = LOWORD(Src[0]);
      v19 = LOWORD(Src[0]) + 20LL;
    }
    else
    {
      v15[4] = 0;
      v15[5] = Src[0];
      v15[6] = LOWORD(Src[0]) + 2;
      v15[7] = Src[0];
      memmove(v17, Src[1], LOWORD(Src[0]));
      v18 = LOWORD(Src[0]);
      v19 = LOWORD(Src[0]) + 18LL;
    }
    memmove((char *)v15 + v19, Src[1], v18);
    v20 = *a1;
    *a1 = (int *)v15;
    if ( v20 )
      ExFreePoolWithTag(v20, 0);
    *a2 = v23;
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x140078dc0  mov     [rsp-38h+arg_10], rbx
0x140078dc5  mov     [rsp-38h+arg_8], rdx
0x140078dca  push    rbp
0x140078dcb  push    rsi
0x140078dcc  push    rdi
0x140078dcd  push    r12
0x140078dcf  push    r13
0x140078dd1  push    r14
0x140078dd3  push    r15
0x140078dd5  mov     rbp, rsp
0x140078dd8  sub     rsp, 60h
0x140078ddc  mov     r10, [rcx]
0x140078ddf  mov     edi, 0A000000Ch
0x140078de4  xorps   xmm0, xmm0
0x140078de7  mov     rsi, r9
0x140078dea  mov     r11, r8
0x140078ded  mov     r12, rcx
0x140078df0  mov     r14d, [r10]
0x140078df3  movdqa  xmmword ptr [rbp+String2.Length], xmm0
0x140078df8  cmp     r14d, edi
0x140078dfb  jnz     short loc_140078E33
0x140078dfd  mov     edi, [r10+10h]
0x140078e01  mov     [rbp+arg_0], edi
0x140078e04  test    dil, 1
0x140078e08  jnz     loc_1400790CD
0x140078e0e  movzx   eax, word ptr [r10+0Ah]
0x140078e13  mov     edi, 0A000000Ch
0x140078e18  mov     [rbp+String2.Length], ax
0x140078e1c  movzx   eax, word ptr [r10+0Ah]
0x140078e21  mov     [rbp+String2.MaximumLength], ax
0x140078e25  movzx   eax, word ptr [r10+8]
0x140078e2a  shr     rax, 1
0x140078e2d  add     rax, 0Ah
0x140078e31  jmp     short loc_140078E65
0x140078e33  cmp     r14d, 0A0000003h
0x140078e3a  jnz     loc_1400790CD
0x140078e40  movzx   eax, word ptr [r10+0Ah]
0x140078e45  mov     [rbp+String2.Length], ax
0x140078e49  movzx   eax, word ptr [r10+0Ah]
0x140078e4e  mov     [rbp+String2.MaximumLength], ax
0x140078e52  movzx   eax, word ptr [r10+8]
0x140078e57  shr     rax, 1
0x140078e5a  add     rax, 8
0x140078e5e  mov     [rbp+arg_0], 0
0x140078e65  lea     rax, [r10+rax*2]
0x140078e69  mov     rdx, r11; int
0x140078e6c  lea     r8, [rbp+Src]; UnicodeString
0x140078e70  mov     [rbp+String2.Buffer], rax
0x140078e74  lea     rcx, [rbp+String2]; String2
0x140078e78  movups  xmmword ptr [rbp+Src], xmm0
0x140078e7c  call    ?ScratchRelativizeSubstituteName@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBVUfsUnionCtx@2@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::ScratchRelativizeSubstituteName(_UNICODE_STRING const &,UnionFs::UfsUnionCtx const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)
0x140078e81  mov     ebx, eax
0x140078e83  test    eax, eax
0x140078e85  jns     short loc_140078EB3
0x140078e87  lea     rax, aPushComputingM; "PUSH: Computing munged substitute name"
0x140078e8e  mov     r8, 6C700210C3Ch; struct UnionFs::StackEventTracer *
0x140078e98  lea     r9, aUnionfsUtilsVi_0; "UnionFs::Utils::VirtualizeReparseData"
0x140078e9f  mov     [rsp+60h+var_40], rax; char *
0x140078ea4  mov     rdx, rsi; int
0x140078ea7  mov     ecx, ebx; this
0x140078ea9  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140078eae  jmp     loc_1400790C0
0x140078eb3  cmp     [rbp+Src+8], 0
0x140078eb8  jnz     short loc_140078EC1
0x140078eba  xor     ebx, ebx
0x140078ebc  jmp     loc_1400790C0
0x140078ec1  mov     ebx, 14h
0x140078ec6  cmp     r14d, edi
0x140078ec9  lea     eax, [rbx-4]
0x140078ecc  cmovnz  ebx, eax
0x140078ecf  jnz     short loc_140078F13
0x140078ed1  movzx   eax, word ptr [rbp+Src]
0x140078ed5  mov     r15d, 0FFFFh
0x140078edb  add     eax, eax
0x140078edd  cmp     eax, r15d
0x140078ee0  jbe     short loc_140078F49
0x140078ee2  mov     r8, 6C900210C4Fh; struct UnionFs::StackEventTracer *
0x140078eec  lea     rax, aApiArithmeticE; "API: Arithmetic error"
0x140078ef3  mov     ebx, 0C0000095h
0x140078ef8  mov     ecx, ebx; this
0x140078efa  mov     [rsp+60h+var_40], rax; char *
0x140078eff  lea     r9, aUnionfsUtilsVi_0; "UnionFs::Utils::VirtualizeReparseData"
0x140078f06  mov     rdx, rsi; int
0x140078f09  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140078f0e  jmp     loc_1400790C0
0x140078f13  movzx   eax, word ptr [rbp+Src]
0x140078f17  add     ax, 2
0x140078f1b  cmp     ax, word ptr [rbp+Src]
0x140078f1f  jnb     short loc_140078F2D
0x140078f21  mov     r8, 6CA00210C59h
0x140078f2b  jmp     short loc_140078EEC
0x140078f2d  movzx   eax, ax
0x140078f30  mov     r15d, 0FFFFh
0x140078f36  add     eax, eax
0x140078f38  cmp     eax, r15d
0x140078f3b  jbe     short loc_140078F49
0x140078f3d  mov     r8, 6CB00210C5Eh
0x140078f47  jmp     short loc_140078EEC
0x140078f49  movzx   r13d, ax
0x140078f4d  lea     rcx, [rbp+P]
0x140078f51  lea     eax, [rbx+r13]
0x140078f55  mov     edx, eax
0x140078f57  mov     [rbp+var_30], eax
0x140078f5a  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0GCHCEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1651656277,0>(unsigned __int64)
0x140078f5f  mov     rdi, [rbp+P]
0x140078f63  test    rdi, rdi
0x140078f66  jnz     short loc_140078F99
0x140078f68  lea     rax, aOriginAllocati_55; "ORIGIN: Allocating virtualized reparse "...
0x140078f6f  mov     ebx, 0C000009Ah
0x140078f74  mov     ecx, ebx; this
0x140078f76  mov     [rsp+60h+var_40], rax; char *
0x140078f7b  lea     r9, aUnionfsUtilsVi_0; "UnionFs::Utils::VirtualizeReparseData"
0x140078f82  mov     r8, 6C800210C6Ch; struct UnionFs::StackEventTracer *
0x140078f8c  mov     rdx, rsi; int
0x140078f8f  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140078f94  jmp     loc_1400790C0
0x140078f99  sub     bx, 8
0x140078f9d  mov     [rdi], r14d
0x140078fa0  add     bx, r13w
0x140078fa4  cmp     bx, r13w
0x140078fa8  jb      loc_140079079
0x140078fae  mov     [rdi+4], bx
0x140078fb2  mov     rax, [r12]
0x140078fb6  movzx   ecx, word ptr [rax+6]
0x140078fba  mov     [rdi+6], cx
0x140078fbe  lea     rcx, [rdi+10h]; void *
0x140078fc2  cmp     r14d, 0A000000Ch
0x140078fc9  jnz     short loc_14007900B
0x140078fcb  mov     eax, [rbp+arg_0]
0x140078fce  mov     [rcx], eax
0x140078fd0  xor     eax, eax
0x140078fd2  mov     [rdi+0Ch], ax
0x140078fd6  lea     rcx, [rdi+14h]; void *
0x140078fda  movzx   eax, word ptr [rbp+Src]
0x140078fde  mov     [rdi+0Eh], ax
0x140078fe2  movzx   eax, word ptr [rbp+Src]
0x140078fe6  mov     [rdi+8], ax
0x140078fea  movzx   eax, word ptr [rbp+Src]
0x140078fee  mov     [rdi+0Ah], ax
0x140078ff2  movzx   r8d, word ptr [rbp+Src]; Size
0x140078ff7  mov     rdx, [rbp+Src+8]; Src
0x140078ffb  call    memmove
0x140079000  movzx   r8d, word ptr [rbp+Src]
0x140079005  lea     rcx, [r8+14h]
0x140079009  jmp     short loc_140079044
0x14007900b  xor     eax, eax
0x14007900d  mov     [rdi+8], ax
0x140079011  movzx   eax, word ptr [rbp+Src]
0x140079015  mov     [rdi+0Ah], ax
0x140079019  movzx   eax, word ptr [rbp+Src]
0x14007901d  add     ax, 2
0x140079021  mov     [rdi+0Ch], ax
0x140079025  movzx   eax, word ptr [rbp+Src]
0x140079029  mov     [rdi+0Eh], ax
0x14007902d  movzx   r8d, word ptr [rbp+Src]; Size
0x140079032  mov     rdx, [rbp+Src+8]; Src
0x140079036  call    memmove
0x14007903b  movzx   r8d, word ptr [rbp+Src]; Size
0x140079040  lea     rcx, [r8+12h]
0x140079044  mov     rdx, [rbp+Src+8]; Src
0x140079048  add     rcx, rdi; void *
0x14007904b  call    memmove
0x140079050  mov     rcx, [r12]; P
0x140079054  mov     [r12], rdi
0x140079058  test    rcx, rcx
0x14007905b  jz      short loc_14007906B
0x14007905d  xor     edx, edx; Tag
0x14007905f  call    cs:__imp_ExFreePoolWithTag
0x140079066  nop     dword ptr [rax+rax+00h]
0x14007906b  mov     rcx, [rbp+arg_8]
0x14007906f  mov     eax, [rbp+var_30]
0x140079072  mov     [rcx], eax
0x140079074  jmp     loc_140078EBA
0x140079079  lea     rax, aApiArithmeticE; "API: Arithmetic error"
0x140079080  mov     [rdi+4], r15w
0x140079085  mov     ebx, 0C0000095h
0x14007908a  mov     [rsp+60h+var_40], rax; char *
0x14007908f  mov     ecx, ebx; this
0x140079091  lea     r9, aUnionfsUtilsVi_0; "UnionFs::Utils::VirtualizeReparseData"
0x140079098  mov     r8, 6CF00210C77h; struct UnionFs::StackEventTracer *
0x1400790a2  mov     rdx, rsi; int
0x1400790a5  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400790aa  test    rdi, rdi
0x1400790ad  jz      short loc_1400790C0
0x1400790af  xor     edx, edx; Tag
0x1400790b1  mov     rcx, rdi; P
0x1400790b4  call    cs:__imp_ExFreePoolWithTag
0x1400790bb  nop     dword ptr [rax+rax+00h]
0x1400790c0  lea     rcx, [rbp+Src]; UnicodeString
0x1400790c4  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400790c9  mov     eax, ebx
0x1400790cb  jmp     short loc_1400790CF
0x1400790cd  xor     eax, eax
0x1400790cf  mov     rbx, [rsp+60h+arg_10]
0x1400790d7  add     rsp, 60h
0x1400790db  pop     r15
0x1400790dd  pop     r14
0x1400790df  pop     r13
0x1400790e1  pop     r12
0x1400790e3  pop     rdi
0x1400790e4  pop     rsi
0x1400790e5  pop     rbp
0x1400790e6  retn
```
