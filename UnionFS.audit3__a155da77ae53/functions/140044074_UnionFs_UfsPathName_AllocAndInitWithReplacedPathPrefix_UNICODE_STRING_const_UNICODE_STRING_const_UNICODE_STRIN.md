# UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)

- ea: `0x140044074`
- end: `0x140044203`
- name: `?AllocAndInitWithReplacedPathPrefix@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@00GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `399`
- prototype: `__int64 __usercall@<rax>(UnionFs::Rtl *this@<rcx>, struct _UNICODE_STRING *@<rdx>, PCUNICODE_STRING Source@<r8>, PVOID P, int)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x1400136b8`
- `0x140013b60`
- `0x14001568c`
- `0x1400173f0`
- `0x1400183cc`
- `0x1400194b8`
- `0x14001a18c`
- `0x140036db8`
- `0x140037b54`
- `0x1400612fc`

## callees

- `0x140043c08`
- `0x140044074`
- `0x140056c7c`
- `0x140076508`
- `0x140079f68`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400440c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004419d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400441d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400440c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004419d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400441d9`

## string_xrefs

- `0x1400440fa`: `PUSH: Replacing path prefix`
- `0x140044150`: `PUSH: Creating new path name`
- `0x14004410b`: `UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix`
- `0x140044161`: `UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(
        PWSTR *this,
        struct _UNICODE_STRING *a2,
        PCUNICODE_STRING Source,
        unsigned __int16 a4,
        __int64 *P,
        __int64 a6)
{
  __int64 *v6; // rdi
  __int64 v11; // rbx
  __int64 v12; // rbp
  int v13; // ebx
  struct _UNICODE_STRING *v14; // rdx
  int v15; // esi
  struct _UNICODE_STRING *v16; // rbx
  __int64 v17; // rbx
  const char *v19; // [rsp+28h] [rbp-50h]
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-48h] BYREF

  v6 = P;
  v11 = *P;
  *P = 0;
  if ( v11 )
  {
    if ( !*(_BYTE *)(v11 + 16) )
      *(_OWORD *)v11 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v11, a2);
    ExFreePoolWithTag((PVOID)v11, 0);
  }
  v12 = a6;
  UnicodeString = 0;
  v13 = UnionFs::Utils::ReplaceFirstSubstring(this, a2, Source, &UnicodeString, a6);
  if ( v13 >= 0 )
  {
    P = 0;
    v15 = UnionFs::UfsPathName::AllocAndInit(&UnicodeString, (struct _UNICODE_STRING *)a4, (__int64 *)&P, v12);
    if ( v15 >= 0 )
    {
      v17 = *v6;
      *v6 = (__int64)P;
      if ( v17 )
      {
        if ( !*(_BYTE *)(v17 + 16) )
          *(_OWORD *)v17 = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v17, v14);
        ExFreePoolWithTag((PVOID)v17, 0);
      }
      v13 = 0;
    }
    else
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v15,
        v12,
        (struct UnionFs::StackEventTracer *)0x639001300FBLL,
        (unsigned __int64)"UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix",
        "PUSH: Creating new path name",
        v19);
      v16 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v16, v14);
        ExFreePoolWithTag(v16, 0);
      }
      v13 = v15;
    }
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v13,
      v12,
      (struct UnionFs::StackEventTracer *)0x638001300F5LL,
      (unsigned __int64)"UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix",
      "PUSH: Replacing path prefix",
      v19);
  }
  FsFltWil::Details::FreeUnicodeString(&UnicodeString, v14);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140044074  push    rbx
0x140044076  push    rbp
0x140044077  push    rsi
0x140044078  push    rdi
0x140044079  push    r12
0x14004407b  push    r14
0x14004407d  push    r15
0x14004407f  sub     rsp, 40h
0x140044083  mov     rdi, [rsp+78h+P]
0x14004408b  movzx   esi, r9w
0x14004408f  mov     r14, r8
0x140044092  mov     r15, rdx
0x140044095  mov     r12, rcx
0x140044098  mov     rbx, [rdi]
0x14004409b  mov     qword ptr [rdi], 0
0x1400440a2  test    rbx, rbx
0x1400440a5  jz      short loc_1400440CC
0x1400440a7  cmp     byte ptr [rbx+10h], 0
0x1400440ab  jnz     short loc_1400440B3
0x1400440ad  xorps   xmm0, xmm0
0x1400440b0  movups  xmmword ptr [rbx], xmm0
0x1400440b3  mov     rcx, rbx; UnicodeString
0x1400440b6  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400440bb  xor     edx, edx; Tag
0x1400440bd  mov     rcx, rbx; P
0x1400440c0  call    cs:__imp_ExFreePoolWithTag
0x1400440c7  nop     dword ptr [rax+rax+00h]
0x1400440cc  mov     rbp, [rsp+78h+arg_28]
0x1400440d4  lea     r9, [rsp+78h+UnicodeString]
0x1400440d9  xorps   xmm0, xmm0
0x1400440dc  mov     [rsp+78h+var_58], rbp; int
0x1400440e1  mov     r8, r14; Source
0x1400440e4  mov     rdx, r15; struct _UNICODE_STRING *
0x1400440e7  mov     rcx, r12; this
0x1400440ea  movups  xmmword ptr [rsp+78h+UnicodeString.Length], xmm0
0x1400440ef  call    ?ReplaceFirstSubstring@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@00AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::ReplaceFirstSubstring(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)
0x1400440f4  mov     ebx, eax
0x1400440f6  test    eax, eax
0x1400440f8  jns     short loc_140044126
0x1400440fa  lea     rax, aPushReplacingP; "PUSH: Replacing path prefix"
0x140044101  mov     r8, 638001300F5h; struct UnionFs::StackEventTracer *
0x14004410b  lea     r9, aUnionfsUfspath_29; "UnionFs::UfsPathName::AllocAndInitWithR"...
0x140044112  mov     [rsp+78h+var_58], rax; char *
0x140044117  mov     rdx, rbp; int
0x14004411a  mov     ecx, ebx; this
0x14004411c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140044121  jmp     loc_1400441E7
0x140044126  mov     r9, rbp
0x140044129  mov     [rsp+78h+P], 0
0x140044135  lea     r8, [rsp+78h+P]
0x14004413d  movzx   edx, si
0x140044140  lea     rcx, [rsp+78h+UnicodeString]; SourceString
0x140044145  call    ?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInit(_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14004414a  mov     esi, eax
0x14004414c  test    eax, eax
0x14004414e  jns     short loc_1400441AD
0x140044150  lea     rax, aPushCreatingNe_0; "PUSH: Creating new path name"
0x140044157  mov     r8, 639001300FBh; struct UnionFs::StackEventTracer *
0x140044161  lea     r9, aUnionfsUfspath_29; "UnionFs::UfsPathName::AllocAndInitWithR"...
0x140044168  mov     [rsp+78h+var_58], rax; char *
0x14004416d  mov     rdx, rbp; int
0x140044170  mov     ecx, esi; this
0x140044172  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140044177  mov     rbx, [rsp+78h+P]
0x14004417f  test    rbx, rbx
0x140044182  jz      short loc_1400441A9
0x140044184  cmp     byte ptr [rbx+10h], 0
0x140044188  jnz     short loc_140044190
0x14004418a  xorps   xmm0, xmm0
0x14004418d  movups  xmmword ptr [rbx], xmm0
0x140044190  mov     rcx, rbx; UnicodeString
0x140044193  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044198  xor     edx, edx; Tag
0x14004419a  mov     rcx, rbx; P
0x14004419d  call    cs:__imp_ExFreePoolWithTag
0x1400441a4  nop     dword ptr [rax+rax+00h]
0x1400441a9  mov     ebx, esi
0x1400441ab  jmp     short loc_1400441E7
0x1400441ad  mov     rbx, [rdi]
0x1400441b0  mov     rax, [rsp+78h+P]
0x1400441b8  mov     [rdi], rax
0x1400441bb  test    rbx, rbx
0x1400441be  jz      short loc_1400441E5
0x1400441c0  cmp     byte ptr [rbx+10h], 0
0x1400441c4  jnz     short loc_1400441CC
0x1400441c6  xorps   xmm0, xmm0
0x1400441c9  movups  xmmword ptr [rbx], xmm0
0x1400441cc  mov     rcx, rbx; UnicodeString
0x1400441cf  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400441d4  xor     edx, edx; Tag
0x1400441d6  mov     rcx, rbx; P
0x1400441d9  call    cs:__imp_ExFreePoolWithTag
0x1400441e0  nop     dword ptr [rax+rax+00h]
0x1400441e5  xor     ebx, ebx
0x1400441e7  lea     rcx, [rsp+78h+UnicodeString]; UnicodeString
0x1400441ec  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400441f1  mov     eax, ebx
0x1400441f3  add     rsp, 40h
0x1400441f7  pop     r15
0x1400441f9  pop     r14
0x1400441fb  pop     r12
0x1400441fd  pop     rdi
0x1400441fe  pop     rsi
0x1400441ff  pop     rbp
0x140044200  pop     rbx
0x140044201  retn
```
