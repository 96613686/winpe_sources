# UnionFs::Utils::VirtualizeReparseTagData(_FLT_TAG_DATA_BUFFER * &,UnionFs::UfsUnionCtx const &,UnionFs::StackEventTracer &)

- ea: `0x1400790f0`
- end: `0x1400793fd`
- name: `?VirtualizeReparseTagData@Utils@UnionFs@@YAJAEAPEAU_FLT_TAG_DATA_BUFFER@@AEBVUfsUnionCtx@2@AEAVStackEventTracer@2@@Z`
- size: `781`
- prototype: `int(UnionFs::Utils *__hidden this, struct _FLT_TAG_DATA_BUFFER **, const struct UnionFs::UfsUnionCtx *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140011e20`

## callees

- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140067c28`
- `0x1400771d8`
- `0x1400790f0`
- `0x140079f68`
- `0x14007bc40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140079379`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400793c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079379`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400793c9`

## string_xrefs

- `0x1400791c0`: `UnionFs::Utils::VirtualizeReparseTagData`
- `0x140079227`: `UnionFs::Utils::VirtualizeReparseTagData`
- `0x14007929e`: `UnionFs::Utils::VirtualizeReparseTagData`
- `0x1400793a6`: `UnionFs::Utils::VirtualizeReparseTagData`
- `0x1400791af`: `PUSH: Computing munged substitute name for TagData`

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
  const char *v21; // [rsp+28h] [rbp-28h]
  void *Src[2]; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING String2; // [rsp+40h] [rbp-10h] BYREF
  int v24; // [rsp+90h] [rbp+40h]
  PVOID P; // [rsp+A8h] [rbp+58h] BYREF

  v4 = *this;
  v5 = (int)a3;
  v7 = *(_DWORD *)*this;
  String2 = 0;
  if ( v7 == -1610612724 )
  {
    v24 = v4[4];
    if ( (v24 & 1) == 0 )
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
    v24 = 0;
LABEL_6:
    String2.Buffer = (PWSTR)v4 + v8;
    *(_OWORD *)Src = 0;
    v10 = UnionFs::Utils::ScratchRelativizeSubstituteName(&String2, (__int64)a2, (PUNICODE_STRING)Src, a3);
    if ( v10 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v10,
        v5,
        (struct UnionFs::StackEventTracer *)0x6C300210C9BLL,
        (unsigned __int64)"UnionFs::Utils::VirtualizeReparseTagData",
        "PUSH: Computing munged substitute name for TagData",
        v21);
LABEL_28:
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)Src, v9);
      return (unsigned int)v10;
    }
    if ( !Src[1] )
    {
LABEL_9:
      v10 = 0;
      goto LABEL_28;
    }
    v11 = 20;
    if ( v7 == -1610612724 )
    {
      v12 = 2 * LOWORD(Src[0]);
      if ( v12 > 0xFFFF )
      {
        v13 = 0x6CC00210CAELL;
LABEL_14:
        v10 = -1073741675;
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)0xC0000095LL,
          v5,
          (struct UnionFs::StackEventTracer *)v13,
          (unsigned __int64)"UnionFs::Utils::VirtualizeReparseTagData",
          "API: Arithmetic error",
          v21);
        goto LABEL_28;
      }
    }
    else
    {
      v11 = 16;
      if ( (unsigned __int16)(LOWORD(Src[0]) + 2) < LOWORD(Src[0]) )
      {
        v13 = 0x6CD00210CB8LL;
        goto LABEL_14;
      }
      v12 = 2 * (unsigned __int16)(LOWORD(Src[0]) + 2);
      if ( v12 > 0xFFFF )
      {
        v13 = 0x6CE00210CBDLL;
        goto LABEL_14;
      }
    }
    v14 = v12;
    utl::make_unique_pool<enum gsl::byte [0],64,1651656277,0>(&P, v11 + (unsigned int)(unsigned __int16)v12);
    v15 = P;
    if ( !P )
    {
      v10 = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        v5,
        (struct UnionFs::StackEventTracer *)0x6C400210CCBLL,
        (unsigned __int64)"UnionFs::Utils::VirtualizeReparseTagData",
        "ORIGIN: Allocating virtualized tag buffer",
        v21);
      goto LABEL_28;
    }
    *(_DWORD *)P = v7;
    v16 = v14 + v11 - 8;
    v15[3] = *((_WORD *)*this + 3);
    if ( v16 < v14 )
    {
      v15[2] = -1;
      v10 = -1073741675;
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)0xC0000095LL,
        v5,
        (struct UnionFs::StackEventTracer *)0x6BD00210CD7LL,
        (unsigned __int64)"UnionFs::Utils::VirtualizeReparseTagData",
        "API: Arithmetic error",
        v21);
      if ( v15 )
        ExFreePoolWithTag(v15, 0);
      goto LABEL_28;
    }
    v15[2] = v16;
    v17 = v15 + 8;
    if ( v7 == -1610612724 )
    {
      *v17 = v24;
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
    ExFreePoolWithTag(*this, 0);
    *this = v15;
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x1400790f0  mov     [rsp-38h+arg_8], rbx
0x1400790f5  push    rbp
0x1400790f6  push    rsi
0x1400790f7  push    rdi
0x1400790f8  push    r12
0x1400790fa  push    r13
0x1400790fc  push    r14
0x1400790fe  push    r15
0x140079100  mov     rbp, rsp
0x140079103  sub     rsp, 50h
0x140079107  mov     r9, [rcx]
0x14007910a  mov     edi, 0A000000Ch
0x14007910f  xorps   xmm0, xmm0
0x140079112  mov     rsi, r8
0x140079115  mov     r12, rcx
0x140079118  mov     r14d, [r9]
0x14007911b  movdqa  xmmword ptr [rbp+String2.Length], xmm0
0x140079120  cmp     r14d, edi
0x140079123  jnz     short loc_14007915B
0x140079125  mov     edi, [r9+10h]
0x140079129  mov     [rbp+arg_0], edi
0x14007912c  test    dil, 1
0x140079130  jnz     loc_1400793E2
0x140079136  movzx   eax, word ptr [r9+0Ah]
0x14007913b  mov     edi, 0A000000Ch
0x140079140  mov     [rbp+String2.Length], ax
0x140079144  movzx   eax, word ptr [r9+0Ah]
0x140079149  mov     [rbp+String2.MaximumLength], ax
0x14007914d  movzx   eax, word ptr [r9+8]
0x140079152  shr     rax, 1
0x140079155  add     rax, 0Ah
0x140079159  jmp     short loc_14007918D
0x14007915b  cmp     r14d, 0A0000003h
0x140079162  jnz     loc_1400793E2
0x140079168  movzx   eax, word ptr [r9+0Ah]
0x14007916d  mov     [rbp+String2.Length], ax
0x140079171  movzx   eax, word ptr [r9+0Ah]
0x140079176  mov     [rbp+String2.MaximumLength], ax
0x14007917a  movzx   eax, word ptr [r9+8]
0x14007917f  shr     rax, 1
0x140079182  add     rax, 8
0x140079186  mov     [rbp+arg_0], 0
0x14007918d  lea     rax, [r9+rax*2]
0x140079191  mov     r9, rsi; struct UnionFs::StackEventTracer *
0x140079194  lea     r8, [rbp+Src]; UnicodeString
0x140079198  mov     [rbp+String2.Buffer], rax
0x14007919c  lea     rcx, [rbp+String2]; String2
0x1400791a0  movups  xmmword ptr [rbp+Src], xmm0
0x1400791a4  call    ?ScratchRelativizeSubstituteName@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBVUfsUnionCtx@2@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::ScratchRelativizeSubstituteName(_UNICODE_STRING const &,UnionFs::UfsUnionCtx const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)
0x1400791a9  mov     ebx, eax
0x1400791ab  test    eax, eax
0x1400791ad  jns     short loc_1400791DB
0x1400791af  lea     rax, aPushComputingM_0; "PUSH: Computing munged substitute name "...
0x1400791b6  mov     r8, 6C300210C9Bh; struct UnionFs::StackEventTracer *
0x1400791c0  lea     r9, aUnionfsUtilsVi; "UnionFs::Utils::VirtualizeReparseTagDat"...
0x1400791c7  mov     [rsp+50h+var_30], rax; char *
0x1400791cc  mov     rdx, rsi; int
0x1400791cf  mov     ecx, ebx; this
0x1400791d1  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400791d6  jmp     loc_1400793D5
0x1400791db  cmp     [rbp+Src+8], 0
0x1400791e0  jnz     short loc_1400791E9
0x1400791e2  xor     ebx, ebx
0x1400791e4  jmp     loc_1400793D5
0x1400791e9  mov     ebx, 14h
0x1400791ee  cmp     r14d, edi
0x1400791f1  lea     eax, [rbx-4]
0x1400791f4  cmovnz  ebx, eax
0x1400791f7  jnz     short loc_14007923B
0x1400791f9  movzx   eax, word ptr [rbp+Src]
0x1400791fd  mov     r15d, 0FFFFh
0x140079203  add     eax, eax
0x140079205  cmp     eax, r15d
0x140079208  jbe     short loc_140079271
0x14007920a  mov     r8, 6CC00210CAEh; struct UnionFs::StackEventTracer *
0x140079214  lea     rax, aApiArithmeticE; "API: Arithmetic error"
0x14007921b  mov     ebx, 0C0000095h
0x140079220  mov     ecx, ebx; this
0x140079222  mov     [rsp+50h+var_30], rax; char *
0x140079227  lea     r9, aUnionfsUtilsVi; "UnionFs::Utils::VirtualizeReparseTagDat"...
0x14007922e  mov     rdx, rsi; int
0x140079231  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140079236  jmp     loc_1400793D5
0x14007923b  movzx   eax, word ptr [rbp+Src]
0x14007923f  add     ax, 2
0x140079243  cmp     ax, word ptr [rbp+Src]
0x140079247  jnb     short loc_140079255
0x140079249  mov     r8, 6CD00210CB8h
0x140079253  jmp     short loc_140079214
0x140079255  movzx   eax, ax
0x140079258  mov     r15d, 0FFFFh
0x14007925e  add     eax, eax
0x140079260  cmp     eax, r15d
0x140079263  jbe     short loc_140079271
0x140079265  mov     r8, 6CE00210CBDh
0x14007926f  jmp     short loc_140079214
0x140079271  movzx   r13d, ax
0x140079275  lea     rcx, [rbp+P]
0x140079279  lea     edx, [rbx+r13]
0x14007927d  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0EA@$0GCHCEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],64,1651656277,0>(unsigned __int64)
0x140079282  mov     rdi, [rbp+P]
0x140079286  test    rdi, rdi
0x140079289  jnz     short loc_1400792BC
0x14007928b  lea     rax, aOriginAllocati_40; "ORIGIN: Allocating virtualized tag buff"...
0x140079292  mov     ebx, 0C000009Ah
0x140079297  mov     ecx, ebx; this
0x140079299  mov     [rsp+50h+var_30], rax; char *
0x14007929e  lea     r9, aUnionfsUtilsVi; "UnionFs::Utils::VirtualizeReparseTagDat"...
0x1400792a5  mov     r8, 6C400210CCBh; struct UnionFs::StackEventTracer *
0x1400792af  mov     rdx, rsi; int
0x1400792b2  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400792b7  jmp     loc_1400793D5
0x1400792bc  mov     [rdi], r14d
0x1400792bf  sub     bx, 8
0x1400792c3  mov     rax, [r12]
0x1400792c7  add     bx, r13w
0x1400792cb  movzx   ecx, word ptr [rax+6]
0x1400792cf  mov     [rdi+6], cx
0x1400792d3  cmp     bx, r13w
0x1400792d7  jb      loc_14007938E
0x1400792dd  mov     [rdi+4], bx
0x1400792e1  lea     rcx, [rdi+10h]; void *
0x1400792e5  cmp     r14d, 0A000000Ch
0x1400792ec  jnz     short loc_14007932E
0x1400792ee  mov     eax, [rbp+arg_0]
0x1400792f1  mov     [rcx], eax
0x1400792f3  xor     eax, eax
0x1400792f5  mov     [rdi+0Ch], ax
0x1400792f9  lea     rcx, [rdi+14h]; void *
0x1400792fd  movzx   eax, word ptr [rbp+Src]
0x140079301  mov     [rdi+0Eh], ax
0x140079305  movzx   eax, word ptr [rbp+Src]
0x140079309  mov     [rdi+8], ax
0x14007930d  movzx   eax, word ptr [rbp+Src]
0x140079311  mov     [rdi+0Ah], ax
0x140079315  movzx   r8d, word ptr [rbp+Src]; Size
0x14007931a  mov     rdx, [rbp+Src+8]; Src
0x14007931e  call    memmove
0x140079323  movzx   r8d, word ptr [rbp+Src]
0x140079328  lea     rcx, [r8+14h]
0x14007932c  jmp     short loc_140079367
0x14007932e  xor     eax, eax
0x140079330  mov     [rdi+8], ax
0x140079334  movzx   eax, word ptr [rbp+Src]
0x140079338  mov     [rdi+0Ah], ax
0x14007933c  movzx   eax, word ptr [rbp+Src]
0x140079340  add     ax, 2
0x140079344  mov     [rdi+0Ch], ax
0x140079348  movzx   eax, word ptr [rbp+Src]
0x14007934c  mov     [rdi+0Eh], ax
0x140079350  movzx   r8d, word ptr [rbp+Src]; Size
0x140079355  mov     rdx, [rbp+Src+8]; Src
0x140079359  call    memmove
0x14007935e  movzx   r8d, word ptr [rbp+Src]; Size
0x140079363  lea     rcx, [r8+12h]
0x140079367  mov     rdx, [rbp+Src+8]; Src
0x14007936b  add     rcx, rdi; void *
0x14007936e  call    memmove
0x140079373  mov     rcx, [r12]; P
0x140079377  xor     edx, edx; Tag
0x140079379  call    cs:__imp_ExFreePoolWithTag
0x140079380  nop     dword ptr [rax+rax+00h]
0x140079385  mov     [r12], rdi
0x140079389  jmp     loc_1400791E2
0x14007938e  lea     rax, aApiArithmeticE; "API: Arithmetic error"
0x140079395  mov     [rdi+4], r15w
0x14007939a  mov     ebx, 0C0000095h
0x14007939f  mov     [rsp+50h+var_30], rax; char *
0x1400793a4  mov     ecx, ebx; this
0x1400793a6  lea     r9, aUnionfsUtilsVi; "UnionFs::Utils::VirtualizeReparseTagDat"...
0x1400793ad  mov     r8, 6BD00210CD7h; struct UnionFs::StackEventTracer *
0x1400793b7  mov     rdx, rsi; int
0x1400793ba  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400793bf  test    rdi, rdi
0x1400793c2  jz      short loc_1400793D5
0x1400793c4  xor     edx, edx; Tag
0x1400793c6  mov     rcx, rdi; P
0x1400793c9  call    cs:__imp_ExFreePoolWithTag
0x1400793d0  nop     dword ptr [rax+rax+00h]
0x1400793d5  lea     rcx, [rbp+Src]; UnicodeString
0x1400793d9  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400793de  mov     eax, ebx
0x1400793e0  jmp     short loc_1400793E4
0x1400793e2  xor     eax, eax
0x1400793e4  mov     rbx, [rsp+50h+arg_8]
0x1400793ec  add     rsp, 50h
0x1400793f0  pop     r15
0x1400793f2  pop     r14
0x1400793f4  pop     r13
0x1400793f6  pop     r12
0x1400793f8  pop     rdi
0x1400793f9  pop     rsi
0x1400793fa  pop     rbp
0x1400793fb  retn
```
