# UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)

- ea: `0x140044748`
- end: `0x140044923`
- name: `?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `475`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `14`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x1400218ac`
- `0x140027178`
- `0x1400288f0`
- `0x140028ba8`
- `0x14002c9f0`
- `0x140035e38`
- `0x140036c78`
- `0x140037a14`
- `0x14003b798`
- `0x14003c734`
- `0x14003ff88`
- `0x140041040`
- `0x1400419a8`
- `0x14006c1fc`

## callees

- `0x140043a88`
- `0x140044748`
- `0x140056ac4`
- `0x140056afc`
- `0x140079c48`
- `0x140079d0c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400447cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004480c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400447cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004480c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004482d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400448bf`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004482d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400448bf`

## string_xrefs

- `0x140044782`: `PUSH: Duplicating path name`
- `0x140044793`: `UnionFs::UfsPathName::Copy`
- `0x140044869`: `UnionFs::UfsPathName::Copy`
- `0x1400448a2`: `UnionFs::UfsPathName::Copy`
- `0x14004488c`: `PUSH: Copying path name`
- `0x140044856`: `ORIGIN: Allocating new path string`

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
0x140044748  push    rbx
0x14004474a  push    rbp
0x14004474b  push    rsi
0x14004474c  push    rdi
0x14004474d  sub     rsp, 48h
0x140044751  mov     rbx, [rdx]
0x140044754  mov     rbp, r8
0x140044757  mov     rsi, rdx
0x14004475a  mov     rdi, rcx
0x14004475d  test    rbx, rbx
0x140044760  jnz     loc_14004481D
0x140044766  movzx   edx, word ptr [rcx+18h]
0x14004476a  mov     r9, r8
0x14004476d  lea     r8, [rsp+68h+P]
0x140044772  mov     [rsp+68h+P], rbx
0x140044777  call    ?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInit(_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14004477c  mov     edi, eax
0x14004477e  test    eax, eax
0x140044780  jns     short loc_1400447DF
0x140044782  lea     rax, aPushDuplicatin; "PUSH: Duplicating path name"
0x140044789  mov     r8, 5E90013010Fh; struct UnionFs::StackEventTracer *
0x140044793  lea     r9, aUnionfsUfspath_48; "UnionFs::UfsPathName::Copy"
0x14004479a  mov     [rsp+68h+var_48], rax; char *
0x14004479f  mov     rdx, rbp; int
0x1400447a2  mov     ecx, edi; this
0x1400447a4  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400447a9  mov     rbx, [rsp+68h+P]
0x1400447ae  test    rbx, rbx
0x1400447b1  jz      short loc_1400447D8
0x1400447b3  cmp     byte ptr [rbx+10h], 0
0x1400447b7  jnz     short loc_1400447BF
0x1400447b9  xorps   xmm0, xmm0
0x1400447bc  movups  xmmword ptr [rbx], xmm0
0x1400447bf  mov     rcx, rbx; UnicodeString
0x1400447c2  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400447c7  xor     edx, edx; Tag
0x1400447c9  mov     rcx, rbx; P
0x1400447cc  call    cs:__imp_ExFreePoolWithTag
0x1400447d3  nop     dword ptr [rax+rax+00h]
0x1400447d8  mov     eax, edi
0x1400447da  jmp     loc_140044919
0x1400447df  mov     rbx, [rsi]
0x1400447e2  mov     rax, [rsp+68h+P]
0x1400447e7  mov     [rsi], rax
0x1400447ea  test    rbx, rbx
0x1400447ed  jz      loc_140044917
0x1400447f3  cmp     byte ptr [rbx+10h], 0
0x1400447f7  jnz     short loc_1400447FF
0x1400447f9  xorps   xmm0, xmm0
0x1400447fc  movups  xmmword ptr [rbx], xmm0
0x1400447ff  mov     rcx, rbx; UnicodeString
0x140044802  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044807  xor     edx, edx; Tag
0x140044809  mov     rcx, rbx; P
0x14004480c  call    cs:__imp_ExFreePoolWithTag
0x140044813  nop     dword ptr [rax+rax+00h]
0x140044818  jmp     loc_140044917
0x14004481d  movzx   edx, word ptr [rcx+2]
0x140044821  cmp     [rbx+2], dx
0x140044825  jb      short loc_14004483E
0x140044827  mov     rdx, rdi; SourceString
0x14004482a  mov     rcx, rbx; DestinationString
0x14004482d  call    cs:__imp_RtlCopyUnicodeString
0x140044834  nop     dword ptr [rax+rax+00h]
0x140044839  jmp     loc_1400448E7
0x14004483e  mov     r8d, 616E4655h
0x140044844  lea     rcx, [rsp+68h+DestinationString]
0x140044849  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14004484e  cmp     [rsp+68h+DestinationString.Buffer], 0
0x140044854  jnz     short loc_1400448B7
0x140044856  lea     rax, aOriginAllocati_57; "ORIGIN: Allocating new path string"
0x14004485d  mov     ebx, 0C000009Ah
0x140044862  mov     ecx, ebx; this
0x140044864  mov     [rsp+68h+var_48], rax; char *
0x140044869  lea     r9, aUnionfsUfspath_48; "UnionFs::UfsPathName::Copy"
0x140044870  mov     r8, 5EA0013012Ch; struct UnionFs::StackEventTracer *
0x14004487a  mov     rdx, rbp; int
0x14004487d  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140044882  lea     rcx, [rsp+68h+DestinationString]; UnicodeString
0x140044887  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004488c  lea     rcx, aPushCopyingPat; "PUSH: Copying path name"
0x140044893  mov     r8, 63100130115h; struct UnionFs::StackEventTracer *
0x14004489d  mov     [rsp+68h+var_48], rcx; char *
0x1400448a2  lea     r9, aUnionfsUfspath_48; "UnionFs::UfsPathName::Copy"
0x1400448a9  mov     ecx, ebx; this
0x1400448ab  mov     rdx, rbp; int
0x1400448ae  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400448b3  mov     eax, ebx
0x1400448b5  jmp     short loc_140044919
0x1400448b7  mov     rdx, rdi; SourceString
0x1400448ba  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1400448bf  call    cs:__imp_RtlCopyUnicodeString
0x1400448c6  nop     dword ptr [rax+rax+00h]
0x1400448cb  movups  xmm1, xmmword ptr [rbx]
0x1400448ce  lea     rcx, [rsp+68h+DestinationString]; UnicodeString
0x1400448d3  movaps  xmm0, xmmword ptr [rsp+68h+DestinationString.Length]
0x1400448d8  movdqa  xmmword ptr [rsp+68h+DestinationString.Length], xmm1
0x1400448de  movdqu  xmmword ptr [rbx], xmm0
0x1400448e2  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400448e7  movzx   edx, word ptr [rdi+18h]
0x1400448eb  mov     rcx, [rbx+8]
0x1400448ef  mov     [rbx+20h], rcx
0x1400448f3  mov     [rbx+1Ah], dx
0x1400448f7  mov     [rbx+18h], dx
0x1400448fb  lea     rax, [rcx+rdx]
0x1400448ff  mov     [rbx+30h], rax
0x140044903  movzx   eax, word ptr [rbx]
0x140044906  sub     ax, dx
0x140044909  mov     [rbx+2Ah], ax
0x14004490d  mov     [rbx+28h], ax
0x140044911  xor     eax, eax
0x140044913  mov     [rbx+38h], ax
0x140044917  xor     eax, eax
0x140044919  add     rsp, 48h
0x14004491d  pop     rdi
0x14004491e  pop     rsi
0x14004491f  pop     rbp
0x140044920  pop     rbx
0x140044921  retn
```
