# UnionFs::UfsPathName::AllocAndInitWithCombinedPaths(_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)

- ea: `0x140043d5c`
- end: `0x140043f39`
- name: `?AllocAndInitWithCombinedPaths@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@0GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `477`
- prototype: `__int64 __usercall@<rax>(struct _UNICODE_STRING *@<rcx>, struct _UNICODE_STRING *@<rdx>, struct UnionFs::StackEventTracer *)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140043f40`
- `0x14005b650`
- `0x14006e54c`
- `0x1400771d8`

## callees

- `0x140043d5c`
- `0x14004420c`
- `0x140044758`
- `0x140056c7c`
- `0x14006a93c`
- `0x140079f68`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140043da1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043e70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043ee5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043f19`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043da1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043e70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043ee5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043f19`

## string_xrefs

- `0x140043e26`: `PUSH: Allocating UfsPathName`
- `0x140043de8`: `UnionFs::UfsPathName::AllocAndInitWithCombinedPaths`
- `0x140043e37`: `UnionFs::UfsPathName::AllocAndInitWithCombinedPaths`
- `0x140043eb1`: `UnionFs::UfsPathName::AllocAndInitWithCombinedPaths`
- `0x140043dd7`: `PUSH: Computing combined path length`
- `0x140043ea0`: `PUSH: Combining paths`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathName::AllocAndInitWithCombinedPaths(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        unsigned __int16 a3,
        struct _UNICODE_STRING **a4,
        struct UnionFs::StackEventTracer *a5)
{
  struct _UNICODE_STRING *v5; // rbx
  struct UnionFs::StackEventTracer *v10; // rbx
  USHORT Length; // dx
  UnionFs::Utils *v12; // rcx
  int v13; // edi
  struct _UNICODE_STRING *v15; // rdx
  struct _UNICODE_STRING *v16; // rbx
  struct _UNICODE_STRING *v17; // rdi
  struct _UNICODE_STRING *v18; // rdx
  int v19; // ebp
  struct _UNICODE_STRING *v20; // rdx
  struct _UNICODE_STRING *v21; // rbx
  struct UnionFs::StackEventTracer *v22; // [rsp+20h] [rbp-38h]
  const char *v23; // [rsp+28h] [rbp-30h]
  unsigned __int16 v24; // [rsp+60h] [rbp+8h] BYREF
  PVOID P; // [rsp+68h] [rbp+10h] BYREF

  v5 = *a4;
  *a4 = 0;
  if ( v5 )
  {
    if ( !LOBYTE(v5[1].Length) )
      *v5 = 0;
    FsFltWil::Details::FreeUnicodeString(v5, a2);
    ExFreePoolWithTag(v5, 0);
  }
  v10 = a5;
  Length = a2->Length;
  v12 = (UnionFs::Utils *)a1->Length;
  v24 = 0;
  v13 = UnionFs::Utils::ComputeCombinedPathLength(v12, Length, (unsigned __int16)&v24, (unsigned __int16 *)a5, v22);
  if ( v13 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v13,
      (int)v10,
      (struct UnionFs::StackEventTracer *)0x36D001300D2LL,
      (unsigned __int64)"UnionFs::UfsPathName::AllocAndInitWithCombinedPaths",
      "PUSH: Computing combined path length",
      v23);
    return (unsigned int)v13;
  }
  P = 0;
  v13 = UnionFs::UfsPathName::AllocEmpty(v24, &P, v10);
  if ( v13 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v13,
      (int)v10,
      (struct UnionFs::StackEventTracer *)0x36E001300D8LL,
      (unsigned __int64)"UnionFs::UfsPathName::AllocAndInitWithCombinedPaths",
      "PUSH: Allocating UfsPathName",
      v23);
    v16 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v16, v15);
      ExFreePoolWithTag(v16, 0);
    }
    return (unsigned int)v13;
  }
  v17 = (struct _UNICODE_STRING *)P;
  v19 = UnionFs::UfsPathName::CombinePath((UnionFs::UfsPathName *)P, a1, a2, a3, v10);
  if ( v19 >= 0 )
  {
    v21 = *a4;
    *a4 = v17;
    if ( v21 )
    {
      if ( !LOBYTE(v21[1].Length) )
        *v21 = 0;
      FsFltWil::Details::FreeUnicodeString(v21, v18);
      ExFreePoolWithTag(v21, 0);
    }
    return 0;
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v19,
      (int)v10,
      (struct UnionFs::StackEventTracer *)0x36F001300DELL,
      (unsigned __int64)"UnionFs::UfsPathName::AllocAndInitWithCombinedPaths",
      "PUSH: Combining paths",
      v23);
    if ( v17 )
    {
      if ( !LOBYTE(v17[1].Length) )
        *v17 = 0;
      FsFltWil::Details::FreeUnicodeString(v17, v20);
      ExFreePoolWithTag(v17, 0);
    }
    return (unsigned int)v19;
  }
}

```

## disassembly

```asm
0x140043d5c  mov     [rsp+arg_10], rbx
0x140043d61  push    rbp
0x140043d62  push    rsi
0x140043d63  push    rdi
0x140043d64  push    r14
0x140043d66  push    r15
0x140043d68  sub     rsp, 30h
0x140043d6c  mov     rbx, [r9]
0x140043d6f  mov     rsi, r9
0x140043d72  mov     qword ptr [r9], 0
0x140043d79  movzx   ebp, r8w
0x140043d7d  mov     r14, rdx
0x140043d80  mov     r15, rcx
0x140043d83  test    rbx, rbx
0x140043d86  jz      short loc_140043DAD
0x140043d88  cmp     byte ptr [rbx+10h], 0
0x140043d8c  jnz     short loc_140043D94
0x140043d8e  xorps   xmm0, xmm0
0x140043d91  movups  xmmword ptr [rbx], xmm0
0x140043d94  mov     rcx, rbx; UnicodeString
0x140043d97  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140043d9c  xor     edx, edx; Tag
0x140043d9e  mov     rcx, rbx; P
0x140043da1  call    cs:__imp_ExFreePoolWithTag
0x140043da8  nop     dword ptr [rax+rax+00h]
0x140043dad  mov     rbx, [rsp+58h+arg_20]
0x140043db5  lea     r8, [rsp+58h+arg_0]; unsigned __int16
0x140043dba  movzx   edx, word ptr [r14]; unsigned __int16
0x140043dbe  xor     eax, eax
0x140043dc0  movzx   ecx, word ptr [r15]; this
0x140043dc4  mov     r9, rbx; unsigned __int16 *
0x140043dc7  mov     [rsp+58h+arg_0], ax
0x140043dcc  call    ?ComputeCombinedPathLength@Utils@UnionFs@@YAJGGPEAGAEAVStackEventTracer@2@@Z; UnionFs::Utils::ComputeCombinedPathLength(ushort,ushort,ushort *,UnionFs::StackEventTracer &)
0x140043dd1  mov     edi, eax
0x140043dd3  test    eax, eax
0x140043dd5  jns     short loc_140043E05
0x140043dd7  lea     rax, aPushComputingC; "PUSH: Computing combined path length"
0x140043dde  mov     r8, 36D001300D2h; struct UnionFs::StackEventTracer *
0x140043de8  lea     r9, aUnionfsUfspath_30; "UnionFs::UfsPathName::AllocAndInitWithC"...
0x140043def  mov     [rsp+58h+var_38], rax; char *
0x140043df4  mov     rdx, rbx; int
0x140043df7  mov     ecx, edi; this
0x140043df9  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140043dfe  mov     eax, edi
0x140043e00  jmp     loc_140043F27
0x140043e05  movzx   ecx, [rsp+58h+arg_0]
0x140043e0a  lea     rdx, [rsp+58h+P]
0x140043e0f  mov     r8, rbx
0x140043e12  mov     [rsp+58h+P], 0
0x140043e1b  call    ?AllocEmpty@UfsPathName@UnionFs@@SAJGAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocEmpty(ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140043e20  mov     edi, eax
0x140043e22  test    eax, eax
0x140043e24  jns     short loc_140043E7E
0x140043e26  lea     rax, aPushAllocating_14; "PUSH: Allocating UfsPathName"
0x140043e2d  mov     r8, 36E001300D8h; struct UnionFs::StackEventTracer *
0x140043e37  lea     r9, aUnionfsUfspath_30; "UnionFs::UfsPathName::AllocAndInitWithC"...
0x140043e3e  mov     [rsp+58h+var_38], rax; char *
0x140043e43  mov     rdx, rbx; int
0x140043e46  mov     ecx, edi; this
0x140043e48  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140043e4d  mov     rbx, [rsp+58h+P]
0x140043e52  test    rbx, rbx
0x140043e55  jz      short loc_140043DFE
0x140043e57  cmp     byte ptr [rbx+10h], 0
0x140043e5b  jnz     short loc_140043E63
0x140043e5d  xorps   xmm0, xmm0
0x140043e60  movups  xmmword ptr [rbx], xmm0
0x140043e63  mov     rcx, rbx; UnicodeString
0x140043e66  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140043e6b  xor     edx, edx; Tag
0x140043e6d  mov     rcx, rbx; P
0x140043e70  call    cs:__imp_ExFreePoolWithTag
0x140043e77  nop     dword ptr [rax+rax+00h]
0x140043e7c  jmp     short loc_140043DFE
0x140043e7e  mov     rdi, [rsp+58h+P]
0x140043e83  movzx   r9d, bp; unsigned __int16
0x140043e87  mov     rcx, rdi; this
0x140043e8a  mov     [rsp+58h+var_38], rbx; struct UnionFs::StackEventTracer *
0x140043e8f  mov     r8, r14; struct _UNICODE_STRING *
0x140043e92  mov     rdx, r15; struct _UNICODE_STRING *
0x140043e95  call    ?CombinePath@UfsPathName@UnionFs@@QEAAJAEBU_UNICODE_STRING@@0GAEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::CombinePath(_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,UnionFs::StackEventTracer &)
0x140043e9a  mov     ebp, eax
0x140043e9c  test    eax, eax
0x140043e9e  jns     short loc_140043EF5
0x140043ea0  lea     rax, aPushCombiningP; "PUSH: Combining paths"
0x140043ea7  mov     r8, 36F001300DEh; struct UnionFs::StackEventTracer *
0x140043eb1  lea     r9, aUnionfsUfspath_30; "UnionFs::UfsPathName::AllocAndInitWithC"...
0x140043eb8  mov     [rsp+58h+var_38], rax; char *
0x140043ebd  mov     rdx, rbx; int
0x140043ec0  mov     ecx, ebp; this
0x140043ec2  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140043ec7  test    rdi, rdi
0x140043eca  jz      short loc_140043EF1
0x140043ecc  cmp     byte ptr [rdi+10h], 0
0x140043ed0  jnz     short loc_140043ED8
0x140043ed2  xorps   xmm0, xmm0
0x140043ed5  movups  xmmword ptr [rdi], xmm0
0x140043ed8  mov     rcx, rdi; UnicodeString
0x140043edb  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140043ee0  xor     edx, edx; Tag
0x140043ee2  mov     rcx, rdi; P
0x140043ee5  call    cs:__imp_ExFreePoolWithTag
0x140043eec  nop     dword ptr [rax+rax+00h]
0x140043ef1  mov     eax, ebp
0x140043ef3  jmp     short loc_140043F27
0x140043ef5  mov     rbx, [rsi]
0x140043ef8  mov     [rsi], rdi
0x140043efb  test    rbx, rbx
0x140043efe  jz      short loc_140043F25
0x140043f00  cmp     byte ptr [rbx+10h], 0
0x140043f04  jnz     short loc_140043F0C
0x140043f06  xorps   xmm0, xmm0
0x140043f09  movups  xmmword ptr [rbx], xmm0
0x140043f0c  mov     rcx, rbx; UnicodeString
0x140043f0f  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140043f14  xor     edx, edx; Tag
0x140043f16  mov     rcx, rbx; P
0x140043f19  call    cs:__imp_ExFreePoolWithTag
0x140043f20  nop     dword ptr [rax+rax+00h]
0x140043f25  xor     eax, eax
0x140043f27  mov     rbx, [rsp+58h+arg_10]
0x140043f2c  add     rsp, 30h
0x140043f30  pop     r15
0x140043f32  pop     r14
0x140043f34  pop     rdi
0x140043f35  pop     rsi
0x140043f36  pop     rbp
0x140043f37  retn
```
