# UnionFs::UfsPathName::MakeShortNameCopy(_FLT_INSTANCE const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)

- ea: `0x140044b40`
- end: `0x140044d23`
- name: `?MakeShortNameCopy@UfsPathName@UnionFs@@QEBAJAEBU_FLT_INSTANCE@@AEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140048244`

## callees

- `0x140043c08`
- `0x140044b40`
- `0x140056c7c`
- `0x14006a5bc`
- `0x14006a9c0`
- `0x140079f68`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140044b84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044cb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044cf3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044b84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044cb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044cf3`

## string_xrefs

- `0x140044bba`: `PUSH: Converting to short name path`
- `0x140044bcb`: `UnionFs::UfsPathName::MakeShortNameCopy`
- `0x140044c20`: `UnionFs::UfsPathName::MakeShortNameCopy`
- `0x140044c78`: `UnionFs::UfsPathName::MakeShortNameCopy`
- `0x140044c0f`: `PUSH: Combining short name path`
- `0x140044c67`: `PUSH: Creating short name path`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathName::MakeShortNameCopy(
        __int64 a1,
        struct _UNICODE_STRING *a2,
        PVOID *a3,
        struct _UNICODE_STRING *a4)
{
  struct _UNICODE_STRING *v4; // rbx
  int v9; // ebx
  struct _UNICODE_STRING *v10; // rdx
  struct _UNICODE_STRING *v11; // r14
  struct _UNICODE_STRING *v12; // rdx
  struct _UNICODE_STRING *Length; // rdx
  struct _UNICODE_STRING *v14; // rdx
  int v15; // r14d
  struct _UNICODE_STRING *v16; // rdx
  struct _UNICODE_STRING *v17; // rbx
  struct _UNICODE_STRING *v18; // rbx
  const char *v20; // [rsp+28h] [rbp-40h]
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-38h] BYREF
  UNICODE_STRING Source; // [rsp+40h] [rbp-28h] BYREF
  UNICODE_STRING SourceString; // [rsp+50h] [rbp-18h] BYREF
  PVOID P; // [rsp+B0h] [rbp+48h] BYREF

  v4 = (struct _UNICODE_STRING *)*a3;
  *a3 = 0;
  if ( v4 )
  {
    if ( !LOBYTE(v4[1].Length) )
      *v4 = 0;
    FsFltWil::Details::FreeUnicodeString(v4, a2);
    ExFreePoolWithTag(v4, 0);
  }
  SourceString = *(UNICODE_STRING *)(a1 + 40);
  Source = 0;
  v9 = UnionFs::Utils::ConvertPathToShortNamePath((PFLT_INSTANCE)a2, &SourceString, &Source, (__int64)a4);
  if ( v9 >= 0 )
  {
    v11 = (struct _UNICODE_STRING *)(a1 + 24);
    UnicodeString = 0;
    v9 = UnionFs::Utils::CombinePath(v11, &Source, &UnicodeString, a4, v11);
    if ( v9 >= 0 )
    {
      Length = (struct _UNICODE_STRING *)v11->Length;
      P = 0;
      v15 = UnionFs::UfsPathName::AllocAndInit(&UnicodeString, Length, (__int64 *)&P, (__int64)a4);
      if ( v15 >= 0 )
      {
        v18 = (struct _UNICODE_STRING *)*a3;
        *a3 = P;
        if ( v18 )
        {
          if ( !LOBYTE(v18[1].Length) )
            *v18 = 0;
          FsFltWil::Details::FreeUnicodeString(v18, v14);
          ExFreePoolWithTag(v18, 0);
        }
        FsFltWil::Details::FreeUnicodeString(&UnicodeString, v14);
        v9 = 0;
      }
      else
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v15,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x5D300130158LL,
          (unsigned __int64)"UnionFs::UfsPathName::MakeShortNameCopy",
          "PUSH: Creating short name path",
          v20);
        v17 = (struct _UNICODE_STRING *)P;
        if ( P )
        {
          if ( !*((_BYTE *)P + 16) )
            *(_OWORD *)P = 0;
          FsFltWil::Details::FreeUnicodeString(v17, v16);
          ExFreePoolWithTag(v17, 0);
        }
        FsFltWil::Details::FreeUnicodeString(&UnicodeString, v16);
        v9 = v15;
      }
    }
    else
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v9,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x5BB00130151LL,
        (unsigned __int64)"UnionFs::UfsPathName::MakeShortNameCopy",
        "PUSH: Combining short name path",
        v20);
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v12);
    }
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v9,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x5B800130147LL,
      (unsigned __int64)"UnionFs::UfsPathName::MakeShortNameCopy",
      "PUSH: Converting to short name path",
      v20);
  }
  FsFltWil::Details::FreeUnicodeString(&Source, v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140044b40  push    rbp
0x140044b42  push    rbx
0x140044b43  push    rsi
0x140044b44  push    rdi
0x140044b45  push    r14
0x140044b47  push    r15
0x140044b49  mov     rbp, rsp
0x140044b4c  sub     rsp, 68h
0x140044b50  mov     rbx, [r8]
0x140044b53  mov     rdi, r9
0x140044b56  mov     qword ptr [r8], 0
0x140044b5d  mov     rsi, r8
0x140044b60  mov     r15, rdx
0x140044b63  mov     r14, rcx
0x140044b66  test    rbx, rbx
0x140044b69  jz      short loc_140044B90
0x140044b6b  cmp     byte ptr [rbx+10h], 0
0x140044b6f  jnz     short loc_140044B77
0x140044b71  xorps   xmm0, xmm0
0x140044b74  movups  xmmword ptr [rbx], xmm0
0x140044b77  mov     rcx, rbx; UnicodeString
0x140044b7a  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044b7f  xor     edx, edx; Tag
0x140044b81  mov     rcx, rbx; P
0x140044b84  call    cs:__imp_ExFreePoolWithTag
0x140044b8b  nop     dword ptr [rax+rax+00h]
0x140044b90  movups  xmm1, xmmword ptr [r14+28h]
0x140044b95  lea     r8, [rbp+Source]; UnicodeString
0x140044b99  mov     r9, rdi; int
0x140044b9c  xorps   xmm0, xmm0
0x140044b9f  lea     rdx, [rbp+SourceString]; SourceString
0x140044ba3  mov     rcx, r15; Instance
0x140044ba6  movdqu  xmmword ptr [rbp+SourceString.Length], xmm1
0x140044bab  movups  xmmword ptr [rbp+Source.Length], xmm0
0x140044baf  call    ?ConvertPathToShortNamePath@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::ConvertPathToShortNamePath(_FLT_INSTANCE const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)
0x140044bb4  mov     ebx, eax
0x140044bb6  test    eax, eax
0x140044bb8  jns     short loc_140044BE6
0x140044bba  lea     rax, aPushConverting_4; "PUSH: Converting to short name path"
0x140044bc1  mov     r8, 5B800130147h; struct UnionFs::StackEventTracer *
0x140044bcb  lea     r9, aUnionfsUfspath_26; "UnionFs::UfsPathName::MakeShortNameCopy"
0x140044bd2  mov     [rsp+68h+var_48], rax; char *
0x140044bd7  mov     rdx, rdi; int
0x140044bda  mov     ecx, ebx; this
0x140044bdc  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140044be1  jmp     loc_140044D0A
0x140044be6  add     r14, 18h
0x140044bea  lea     r8, [rbp+UnicodeString]; UnicodeString
0x140044bee  xorps   xmm0, xmm0
0x140044bf1  mov     [rsp+68h+var_48], r14; struct _UNICODE_STRING *
0x140044bf6  mov     rcx, r14; SourceString
0x140044bf9  lea     rdx, [rbp+Source]; Source
0x140044bfd  mov     r9, rdi; struct _UNICODE_STRING *
0x140044c00  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x140044c04  call    ?CombinePath@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@0AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@PEBG@Z; UnionFs::Utils::CombinePath(_UNICODE_STRING const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,ushort const *)
0x140044c09  mov     ebx, eax
0x140044c0b  test    eax, eax
0x140044c0d  jns     short loc_140044C44
0x140044c0f  lea     rax, aPushCombiningS_0; "PUSH: Combining short name path"
0x140044c16  mov     r8, 5BB00130151h; struct UnionFs::StackEventTracer *
0x140044c20  lea     r9, aUnionfsUfspath_26; "UnionFs::UfsPathName::MakeShortNameCopy"
0x140044c27  mov     [rsp+68h+var_48], rax; char *
0x140044c2c  mov     rdx, rdi; int
0x140044c2f  mov     ecx, ebx; this
0x140044c31  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140044c36  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x140044c3a  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044c3f  jmp     loc_140044D0A
0x140044c44  movzx   edx, word ptr [r14]
0x140044c48  lea     r8, [rbp+P]
0x140044c4c  mov     r9, rdi
0x140044c4f  mov     [rbp+P], 0
0x140044c57  lea     rcx, [rbp+UnicodeString]; SourceString
0x140044c5b  call    ?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInit(_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140044c60  mov     r14d, eax
0x140044c63  test    eax, eax
0x140044c65  jns     short loc_140044CCB
0x140044c67  lea     rax, aPushCreatingSh_0; "PUSH: Creating short name path"
0x140044c6e  mov     r8, 5D300130158h; struct UnionFs::StackEventTracer *
0x140044c78  lea     r9, aUnionfsUfspath_26; "UnionFs::UfsPathName::MakeShortNameCopy"
0x140044c7f  mov     [rsp+68h+var_48], rax; char *
0x140044c84  mov     rdx, rdi; int
0x140044c87  mov     ecx, r14d; this
0x140044c8a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140044c8f  mov     rbx, [rbp+P]
0x140044c93  test    rbx, rbx
0x140044c96  jz      short loc_140044CBD
0x140044c98  cmp     byte ptr [rbx+10h], 0
0x140044c9c  jnz     short loc_140044CA4
0x140044c9e  xorps   xmm0, xmm0
0x140044ca1  movups  xmmword ptr [rbx], xmm0
0x140044ca4  mov     rcx, rbx; UnicodeString
0x140044ca7  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044cac  xor     edx, edx; Tag
0x140044cae  mov     rcx, rbx; P
0x140044cb1  call    cs:__imp_ExFreePoolWithTag
0x140044cb8  nop     dword ptr [rax+rax+00h]
0x140044cbd  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x140044cc1  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044cc6  mov     ebx, r14d
0x140044cc9  jmp     short loc_140044D0A
0x140044ccb  mov     rbx, [rsi]
0x140044cce  mov     rax, [rbp+P]
0x140044cd2  mov     [rsi], rax
0x140044cd5  test    rbx, rbx
0x140044cd8  jz      short loc_140044CFF
0x140044cda  cmp     byte ptr [rbx+10h], 0
0x140044cde  jnz     short loc_140044CE6
0x140044ce0  xorps   xmm0, xmm0
0x140044ce3  movups  xmmword ptr [rbx], xmm0
0x140044ce6  mov     rcx, rbx; UnicodeString
0x140044ce9  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044cee  xor     edx, edx; Tag
0x140044cf0  mov     rcx, rbx; P
0x140044cf3  call    cs:__imp_ExFreePoolWithTag
0x140044cfa  nop     dword ptr [rax+rax+00h]
0x140044cff  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x140044d03  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044d08  xor     ebx, ebx
0x140044d0a  lea     rcx, [rbp+Source]; UnicodeString
0x140044d0e  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044d13  mov     eax, ebx
0x140044d15  add     rsp, 68h
0x140044d19  pop     r15
0x140044d1b  pop     r14
0x140044d1d  pop     rdi
0x140044d1e  pop     rsi
0x140044d1f  pop     rbx
0x140044d20  pop     rbp
0x140044d21  retn
```
