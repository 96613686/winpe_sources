# UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)

- ea: `0x1400448c8`
- end: `0x140044aa3`
- name: `?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `475`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `14`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x14002194c`
- `0x140027218`
- `0x140028990`
- `0x140028c48`
- `0x14002ca90`
- `0x140035f78`
- `0x140036db8`
- `0x140037b54`
- `0x14003b8b8`
- `0x14003c854`
- `0x140040110`
- `0x1400411c8`
- `0x140041b30`
- `0x14006c3ec`

## callees

- `0x140043c08`
- `0x1400448c8`
- `0x140056c44`
- `0x140056c7c`
- `0x140079f68`
- `0x14007a02c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004494c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004498c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004494c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004498c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400449ad`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140044a3f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400449ad`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140044a3f`

## string_xrefs

- `0x140044902`: `PUSH: Duplicating path name`
- `0x140044913`: `UnionFs::UfsPathName::Copy`
- `0x1400449e9`: `UnionFs::UfsPathName::Copy`
- `0x140044a22`: `UnionFs::UfsPathName::Copy`
- `0x140044a0c`: `PUSH: Copying path name`
- `0x1400449d6`: `ORIGIN: Allocating new path string`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathName::Copy(PCUNICODE_STRING SourceString, __int64 *a2, int a3)
{
  __int64 v3; // rbx
  struct _UNICODE_STRING *v7; // rdx
  int v8; // edi
  __int64 v10; // rbx
  __int64 MaximumLength; // rdx
  struct _UNICODE_STRING *v12; // rdx
  struct _UNICODE_STRING v13; // xmm0
  struct _UNICODE_STRING *v14; // rdx
  __int64 Buffer_low; // rdx
  __int64 v16; // rcx
  __int16 v17; // ax
  const char *v18; // [rsp+28h] [rbp-40h]
  const char *v19; // [rsp+28h] [rbp-40h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF

  v3 = *a2;
  if ( *a2 )
  {
    MaximumLength = SourceString->MaximumLength;
    if ( *(_WORD *)(v3 + 2) < (unsigned __int16)MaximumLength )
    {
      FsFltWil::MakeUniqueUnicodeString(&DestinationString, MaximumLength, 1634616917);
      if ( !DestinationString.Buffer )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          a3,
          (struct UnionFs::StackEventTracer *)0x5EA0013012CLL,
          (unsigned __int64)"UnionFs::UfsPathName::Copy",
          "ORIGIN: Allocating new path string",
          v18);
        FsFltWil::Details::FreeUnicodeString(&DestinationString, v12);
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)0xC000009ALL,
          a3,
          (struct UnionFs::StackEventTracer *)0x63100130115LL,
          (unsigned __int64)"UnionFs::UfsPathName::Copy",
          "PUSH: Copying path name",
          v19);
        return 3221225626LL;
      }
      RtlCopyUnicodeString(&DestinationString, SourceString);
      v13 = DestinationString;
      DestinationString = *(struct _UNICODE_STRING *)v3;
      *(struct _UNICODE_STRING *)v3 = v13;
      FsFltWil::Details::FreeUnicodeString(&DestinationString, v14);
    }
    else
    {
      RtlCopyUnicodeString((PUNICODE_STRING)v3, SourceString);
    }
    Buffer_low = LOWORD(SourceString[1].Buffer);
    v16 = *(_QWORD *)(v3 + 8);
    *(_QWORD *)(v3 + 32) = v16;
    *(_WORD *)(v3 + 26) = Buffer_low;
    *(_WORD *)(v3 + 24) = Buffer_low;
    *(_QWORD *)(v3 + 48) = v16 + Buffer_low;
    v17 = *(_WORD *)v3 - Buffer_low;
    *(_WORD *)(v3 + 42) = v17;
    *(_WORD *)(v3 + 40) = v17;
    *(_WORD *)(v3 + 56) = 0;
  }
  else
  {
    v8 = UnionFs::UfsPathName::AllocAndInit(SourceString);
    if ( v8 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v8,
        a3,
        (struct UnionFs::StackEventTracer *)0x5E90013010FLL,
        (unsigned __int64)"UnionFs::UfsPathName::Copy",
        "PUSH: Duplicating path name",
        v18);
      return (unsigned int)v8;
    }
    v10 = *a2;
    *a2 = 0;
    if ( v10 )
    {
      if ( !*(_BYTE *)(v10 + 16) )
        *(_OWORD *)v10 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v10, v7);
      ExFreePoolWithTag((PVOID)v10, 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400448c8  push    rbx
0x1400448ca  push    rbp
0x1400448cb  push    rsi
0x1400448cc  push    rdi
0x1400448cd  sub     rsp, 48h
0x1400448d1  mov     rbx, [rdx]
0x1400448d4  mov     rbp, r8
0x1400448d7  mov     rsi, rdx
0x1400448da  mov     rdi, rcx
0x1400448dd  test    rbx, rbx
0x1400448e0  jnz     loc_14004499D
0x1400448e6  movzx   edx, word ptr [rcx+18h]
0x1400448ea  mov     r9, r8
0x1400448ed  lea     r8, [rsp+68h+P]
0x1400448f2  mov     [rsp+68h+P], rbx
0x1400448f7  call    ?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInit(_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x1400448fc  mov     edi, eax
0x1400448fe  test    eax, eax
0x140044900  jns     short loc_14004495F
0x140044902  lea     rax, aPushDuplicatin; "PUSH: Duplicating path name"
0x140044909  mov     r8, 5E90013010Fh; struct UnionFs::StackEventTracer *
0x140044913  lea     r9, aUnionfsUfspath_48; "UnionFs::UfsPathName::Copy"
0x14004491a  mov     [rsp+68h+var_48], rax; char *
0x14004491f  mov     rdx, rbp; int
0x140044922  mov     ecx, edi; this
0x140044924  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140044929  mov     rbx, [rsp+68h+P]
0x14004492e  test    rbx, rbx
0x140044931  jz      short loc_140044958
0x140044933  cmp     byte ptr [rbx+10h], 0
0x140044937  jnz     short loc_14004493F
0x140044939  xorps   xmm0, xmm0
0x14004493c  movups  xmmword ptr [rbx], xmm0
0x14004493f  mov     rcx, rbx; UnicodeString
0x140044942  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044947  xor     edx, edx; Tag
0x140044949  mov     rcx, rbx; P
0x14004494c  call    cs:__imp_ExFreePoolWithTag
0x140044953  nop     dword ptr [rax+rax+00h]
0x140044958  mov     eax, edi
0x14004495a  jmp     loc_140044A99
0x14004495f  mov     rbx, [rsi]
0x140044962  mov     rax, [rsp+68h+P]
0x140044967  mov     [rsi], rax
0x14004496a  test    rbx, rbx
0x14004496d  jz      loc_140044A97
0x140044973  cmp     byte ptr [rbx+10h], 0
0x140044977  jnz     short loc_14004497F
0x140044979  xorps   xmm0, xmm0
0x14004497c  movups  xmmword ptr [rbx], xmm0
0x14004497f  mov     rcx, rbx; UnicodeString
0x140044982  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044987  xor     edx, edx; Tag
0x140044989  mov     rcx, rbx; P
0x14004498c  call    cs:__imp_ExFreePoolWithTag
0x140044993  nop     dword ptr [rax+rax+00h]
0x140044998  jmp     loc_140044A97
0x14004499d  movzx   edx, word ptr [rcx+2]
0x1400449a1  cmp     [rbx+2], dx
0x1400449a5  jb      short loc_1400449BE
0x1400449a7  mov     rdx, rdi; SourceString
0x1400449aa  mov     rcx, rbx; DestinationString
0x1400449ad  call    cs:__imp_RtlCopyUnicodeString
0x1400449b4  nop     dword ptr [rax+rax+00h]
0x1400449b9  jmp     loc_140044A67
0x1400449be  mov     r8d, 616E4655h
0x1400449c4  lea     rcx, [rsp+68h+DestinationString]
0x1400449c9  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x1400449ce  cmp     [rsp+68h+DestinationString.Buffer], 0
0x1400449d4  jnz     short loc_140044A37
0x1400449d6  lea     rax, aOriginAllocati_58; "ORIGIN: Allocating new path string"
0x1400449dd  mov     ebx, 0C000009Ah
0x1400449e2  mov     ecx, ebx; this
0x1400449e4  mov     [rsp+68h+var_48], rax; char *
0x1400449e9  lea     r9, aUnionfsUfspath_48; "UnionFs::UfsPathName::Copy"
0x1400449f0  mov     r8, 5EA0013012Ch; struct UnionFs::StackEventTracer *
0x1400449fa  mov     rdx, rbp; int
0x1400449fd  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140044a02  lea     rcx, [rsp+68h+DestinationString]; UnicodeString
0x140044a07  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044a0c  lea     rcx, aPushCopyingPat; "PUSH: Copying path name"
0x140044a13  mov     r8, 63100130115h; struct UnionFs::StackEventTracer *
0x140044a1d  mov     [rsp+68h+var_48], rcx; char *
0x140044a22  lea     r9, aUnionfsUfspath_48; "UnionFs::UfsPathName::Copy"
0x140044a29  mov     ecx, ebx; this
0x140044a2b  mov     rdx, rbp; int
0x140044a2e  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140044a33  mov     eax, ebx
0x140044a35  jmp     short loc_140044A99
0x140044a37  mov     rdx, rdi; SourceString
0x140044a3a  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140044a3f  call    cs:__imp_RtlCopyUnicodeString
0x140044a46  nop     dword ptr [rax+rax+00h]
0x140044a4b  movups  xmm1, xmmword ptr [rbx]
0x140044a4e  lea     rcx, [rsp+68h+DestinationString]; UnicodeString
0x140044a53  movaps  xmm0, xmmword ptr [rsp+68h+DestinationString.Length]
0x140044a58  movdqa  xmmword ptr [rsp+68h+DestinationString.Length], xmm1
0x140044a5e  movdqu  xmmword ptr [rbx], xmm0
0x140044a62  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044a67  movzx   edx, word ptr [rdi+18h]
0x140044a6b  mov     rcx, [rbx+8]
0x140044a6f  mov     [rbx+20h], rcx
0x140044a73  mov     [rbx+1Ah], dx
0x140044a77  mov     [rbx+18h], dx
0x140044a7b  lea     rax, [rcx+rdx]
0x140044a7f  mov     [rbx+30h], rax
0x140044a83  movzx   eax, word ptr [rbx]
0x140044a86  sub     ax, dx
0x140044a89  mov     [rbx+2Ah], ax
0x140044a8d  mov     [rbx+28h], ax
0x140044a91  xor     eax, eax
0x140044a93  mov     [rbx+38h], ax
0x140044a97  xor     eax, eax
0x140044a99  add     rsp, 48h
0x140044a9d  pop     rdi
0x140044a9e  pop     rsi
0x140044a9f  pop     rbp
0x140044aa0  pop     rbx
0x140044aa1  retn
```
