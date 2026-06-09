# UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)

- ea: `0x140043ef4`
- end: `0x140044083`
- name: `?AllocAndInitWithReplacedPathPrefix@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@00GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `399`
- prototype: `__int64 __usercall@<rax>(UnionFs::Rtl *this@<rcx>, struct _UNICODE_STRING *@<rdx>, PCUNICODE_STRING Source@<r8>, PVOID P, int)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x140013708`
- `0x140013bb0`
- `0x1400156a8`
- `0x140017370`
- `0x14001834c`
- `0x140019438`
- `0x14001a10c`
- `0x140036c78`
- `0x140037a14`
- `0x14006117c`

## callees

- `0x140043a88`
- `0x140043ef4`
- `0x140056afc`
- `0x140076308`
- `0x140079c48`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140043f40`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004401d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044059`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043f40`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004401d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044059`

## string_xrefs

- `0x140043f7a`: `PUSH: Replacing path prefix`
- `0x140043fd0`: `PUSH: Creating new path name`
- `0x140043f8b`: `UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix`
- `0x140043fe1`: `UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix`

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
0x140043ef4  push    rbx
0x140043ef6  push    rbp
0x140043ef7  push    rsi
0x140043ef8  push    rdi
0x140043ef9  push    r12
0x140043efb  push    r14
0x140043efd  push    r15
0x140043eff  sub     rsp, 40h
0x140043f03  mov     rdi, [rsp+78h+P]
0x140043f0b  movzx   esi, r9w
0x140043f0f  mov     r14, r8
0x140043f12  mov     r15, rdx
0x140043f15  mov     r12, rcx
0x140043f18  mov     rbx, [rdi]
0x140043f1b  mov     qword ptr [rdi], 0
0x140043f22  test    rbx, rbx
0x140043f25  jz      short loc_140043F4C
0x140043f27  cmp     byte ptr [rbx+10h], 0
0x140043f2b  jnz     short loc_140043F33
0x140043f2d  xorps   xmm0, xmm0
0x140043f30  movups  xmmword ptr [rbx], xmm0
0x140043f33  mov     rcx, rbx; UnicodeString
0x140043f36  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140043f3b  xor     edx, edx; Tag
0x140043f3d  mov     rcx, rbx; P
0x140043f40  call    cs:__imp_ExFreePoolWithTag
0x140043f47  nop     dword ptr [rax+rax+00h]
0x140043f4c  mov     rbp, [rsp+78h+arg_28]
0x140043f54  lea     r9, [rsp+78h+UnicodeString]
0x140043f59  xorps   xmm0, xmm0
0x140043f5c  mov     [rsp+78h+var_58], rbp; int
0x140043f61  mov     r8, r14; Source
0x140043f64  mov     rdx, r15; struct _UNICODE_STRING *
0x140043f67  mov     rcx, r12; this
0x140043f6a  movups  xmmword ptr [rsp+78h+UnicodeString.Length], xmm0
0x140043f6f  call    ?ReplaceFirstSubstring@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@00AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::ReplaceFirstSubstring(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)
0x140043f74  mov     ebx, eax
0x140043f76  test    eax, eax
0x140043f78  jns     short loc_140043FA6
0x140043f7a  lea     rax, aPushReplacingP; "PUSH: Replacing path prefix"
0x140043f81  mov     r8, 638001300F5h; struct UnionFs::StackEventTracer *
0x140043f8b  lea     r9, aUnionfsUfspath_29; "UnionFs::UfsPathName::AllocAndInitWithR"...
0x140043f92  mov     [rsp+78h+var_58], rax; char *
0x140043f97  mov     rdx, rbp; int
0x140043f9a  mov     ecx, ebx; this
0x140043f9c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140043fa1  jmp     loc_140044067
0x140043fa6  mov     r9, rbp
0x140043fa9  mov     [rsp+78h+P], 0
0x140043fb5  lea     r8, [rsp+78h+P]
0x140043fbd  movzx   edx, si
0x140043fc0  lea     rcx, [rsp+78h+UnicodeString]; SourceString
0x140043fc5  call    ?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInit(_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140043fca  mov     esi, eax
0x140043fcc  test    eax, eax
0x140043fce  jns     short loc_14004402D
0x140043fd0  lea     rax, aPushCreatingNe_0; "PUSH: Creating new path name"
0x140043fd7  mov     r8, 639001300FBh; struct UnionFs::StackEventTracer *
0x140043fe1  lea     r9, aUnionfsUfspath_29; "UnionFs::UfsPathName::AllocAndInitWithR"...
0x140043fe8  mov     [rsp+78h+var_58], rax; char *
0x140043fed  mov     rdx, rbp; int
0x140043ff0  mov     ecx, esi; this
0x140043ff2  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140043ff7  mov     rbx, [rsp+78h+P]
0x140043fff  test    rbx, rbx
0x140044002  jz      short loc_140044029
0x140044004  cmp     byte ptr [rbx+10h], 0
0x140044008  jnz     short loc_140044010
0x14004400a  xorps   xmm0, xmm0
0x14004400d  movups  xmmword ptr [rbx], xmm0
0x140044010  mov     rcx, rbx; UnicodeString
0x140044013  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044018  xor     edx, edx; Tag
0x14004401a  mov     rcx, rbx; P
0x14004401d  call    cs:__imp_ExFreePoolWithTag
0x140044024  nop     dword ptr [rax+rax+00h]
0x140044029  mov     ebx, esi
0x14004402b  jmp     short loc_140044067
0x14004402d  mov     rbx, [rdi]
0x140044030  mov     rax, [rsp+78h+P]
0x140044038  mov     [rdi], rax
0x14004403b  test    rbx, rbx
0x14004403e  jz      short loc_140044065
0x140044040  cmp     byte ptr [rbx+10h], 0
0x140044044  jnz     short loc_14004404C
0x140044046  xorps   xmm0, xmm0
0x140044049  movups  xmmword ptr [rbx], xmm0
0x14004404c  mov     rcx, rbx; UnicodeString
0x14004404f  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044054  xor     edx, edx; Tag
0x140044056  mov     rcx, rbx; P
0x140044059  call    cs:__imp_ExFreePoolWithTag
0x140044060  nop     dword ptr [rax+rax+00h]
0x140044065  xor     ebx, ebx
0x140044067  lea     rcx, [rsp+78h+UnicodeString]; UnicodeString
0x14004406c  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044071  mov     eax, ebx
0x140044073  add     rsp, 40h
0x140044077  pop     r15
0x140044079  pop     r14
0x14004407b  pop     r12
0x14004407d  pop     rdi
0x14004407e  pop     rsi
0x14004407f  pop     rbp
0x140044080  pop     rbx
0x140044081  retn
```
