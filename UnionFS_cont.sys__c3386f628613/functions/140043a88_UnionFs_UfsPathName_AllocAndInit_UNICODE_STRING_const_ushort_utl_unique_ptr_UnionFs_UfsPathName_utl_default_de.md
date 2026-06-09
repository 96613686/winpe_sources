# UnionFs::UfsPathName::AllocAndInit(_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)

- ea: `0x140043a88`
- end: `0x140043bd6`
- name: `?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `334`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x14003ff88`
- `0x14004397c`
- `0x140043ef4`
- `0x140044748`
- `0x1400449c0`
- `0x140044cd4`

## callees

- `0x140043a88`
- `0x14004408c`
- `0x140056afc`
- `0x140079c48`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140043aca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043b41`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043bba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043aca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043b41`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043bba`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140043b5c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140043b5c`

## string_xrefs

- `0x140043af7`: `PUSH: Allocating UfsPathName`
- `0x140043b08`: `UnionFs::UfsPathName::AllocAndInit`

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
0x140043a88  push    rbx
0x140043a8a  push    rbp
0x140043a8b  push    rsi
0x140043a8c  push    rdi
0x140043a8d  push    r14
0x140043a8f  push    r15
0x140043a91  sub     rsp, 38h
0x140043a95  mov     rbx, [r8]
0x140043a98  mov     rbp, r9
0x140043a9b  movzx   r14d, dx
0x140043a9f  mov     rsi, r8
0x140043aa2  mov     qword ptr [r8], 0
0x140043aa9  mov     r15, rcx
0x140043aac  test    rbx, rbx
0x140043aaf  jz      short loc_140043AD6
0x140043ab1  cmp     byte ptr [rbx+10h], 0
0x140043ab5  jnz     short loc_140043ABD
0x140043ab7  xorps   xmm0, xmm0
0x140043aba  movups  xmmword ptr [rbx], xmm0
0x140043abd  mov     rcx, rbx; UnicodeString
0x140043ac0  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140043ac5  xor     edx, edx; Tag
0x140043ac7  mov     rcx, rbx; P
0x140043aca  call    cs:__imp_ExFreePoolWithTag
0x140043ad1  nop     dword ptr [rax+rax+00h]
0x140043ad6  movzx   ecx, word ptr [r15+2]
0x140043adb  lea     rdx, [rsp+68h+P]
0x140043ae0  mov     r8, rbp
0x140043ae3  mov     [rsp+68h+P], 0
0x140043aec  call    ?AllocEmpty@UfsPathName@UnionFs@@SAJGAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocEmpty(ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140043af1  mov     edi, eax
0x140043af3  test    eax, eax
0x140043af5  jns     short loc_140043B51
0x140043af7  lea     rax, aPushAllocating_14; "PUSH: Allocating UfsPathName"
0x140043afe  mov     r8, 5A400130027h; struct UnionFs::StackEventTracer *
0x140043b08  lea     r9, aUnionfsUfspath_43; "UnionFs::UfsPathName::AllocAndInit"
0x140043b0f  mov     [rsp+68h+var_48], rax; char *
0x140043b14  mov     rdx, rbp; int
0x140043b17  mov     ecx, edi; this
0x140043b19  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140043b1e  mov     rbx, [rsp+68h+P]
0x140043b23  test    rbx, rbx
0x140043b26  jz      short loc_140043B4D
0x140043b28  cmp     byte ptr [rbx+10h], 0
0x140043b2c  jnz     short loc_140043B34
0x140043b2e  xorps   xmm0, xmm0
0x140043b31  movups  xmmword ptr [rbx], xmm0
0x140043b34  mov     rcx, rbx; UnicodeString
0x140043b37  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140043b3c  xor     edx, edx; Tag
0x140043b3e  mov     rcx, rbx; P
0x140043b41  call    cs:__imp_ExFreePoolWithTag
0x140043b48  nop     dword ptr [rax+rax+00h]
0x140043b4d  mov     eax, edi
0x140043b4f  jmp     short loc_140043BC8
0x140043b51  mov     rbx, [rsp+68h+P]
0x140043b56  mov     rdx, r15; SourceString
0x140043b59  mov     rcx, rbx; DestinationString
0x140043b5c  call    cs:__imp_RtlCopyUnicodeString
0x140043b63  nop     dword ptr [rax+rax+00h]
0x140043b68  mov     rcx, [rbx+8]
0x140043b6c  mov     [rbx+20h], rcx
0x140043b70  mov     [rbx+1Ah], r14w
0x140043b75  mov     [rbx+18h], r14w
0x140043b7a  lea     rax, [rcx+r14]
0x140043b7e  mov     [rbx+30h], rax
0x140043b82  movzx   eax, word ptr [rbx]
0x140043b85  sub     ax, r14w
0x140043b89  mov     [rbx+2Ah], ax
0x140043b8d  mov     [rbx+28h], ax
0x140043b91  xor     eax, eax
0x140043b93  mov     [rbx+38h], ax
0x140043b97  mov     rdi, [rsi]
0x140043b9a  mov     [rsi], rbx
0x140043b9d  test    rdi, rdi
0x140043ba0  jz      short loc_140043BC6
0x140043ba2  cmp     [rdi+10h], al
0x140043ba5  jnz     short loc_140043BAD
0x140043ba7  xorps   xmm0, xmm0
0x140043baa  movups  xmmword ptr [rdi], xmm0
0x140043bad  mov     rcx, rdi; UnicodeString
0x140043bb0  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140043bb5  xor     edx, edx; Tag
0x140043bb7  mov     rcx, rdi; P
0x140043bba  call    cs:__imp_ExFreePoolWithTag
0x140043bc1  nop     dword ptr [rax+rax+00h]
0x140043bc6  xor     eax, eax
0x140043bc8  add     rsp, 38h
0x140043bcc  pop     r15
0x140043bce  pop     r14
0x140043bd0  pop     rdi
0x140043bd1  pop     rsi
0x140043bd2  pop     rbp
0x140043bd3  pop     rbx
0x140043bd4  retn
```
