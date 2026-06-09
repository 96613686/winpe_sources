# UnionFs::UfsPathName::AllocAndInitWithCombinedPaths(_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)

- ea: `0x140043bdc`
- end: `0x140043db9`
- name: `?AllocAndInitWithCombinedPaths@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@0GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `477`
- prototype: `__int64 __usercall@<rax>(struct _UNICODE_STRING *@<rcx>, struct _UNICODE_STRING *@<rdx>, struct UnionFs::StackEventTracer *)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140043dc0`
- `0x14005b4d0`
- `0x14006e35c`
- `0x140076fd8`

## callees

- `0x140043bdc`
- `0x14004408c`
- `0x1400445d8`
- `0x140056afc`
- `0x14006a74c`
- `0x140079c48`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140043c21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043cf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043d65`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043d99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043c21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043cf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043d65`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043d99`

## string_xrefs

- `0x140043ca6`: `PUSH: Allocating UfsPathName`
- `0x140043c68`: `UnionFs::UfsPathName::AllocAndInitWithCombinedPaths`
- `0x140043cb7`: `UnionFs::UfsPathName::AllocAndInitWithCombinedPaths`
- `0x140043d31`: `UnionFs::UfsPathName::AllocAndInitWithCombinedPaths`
- `0x140043c57`: `PUSH: Computing combined path length`
- `0x140043d20`: `PUSH: Combining paths`

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
0x140043bdc  mov     [rsp+arg_10], rbx
0x140043be1  push    rbp
0x140043be2  push    rsi
0x140043be3  push    rdi
0x140043be4  push    r14
0x140043be6  push    r15
0x140043be8  sub     rsp, 30h
0x140043bec  mov     rbx, [r9]
0x140043bef  mov     rsi, r9
0x140043bf2  mov     qword ptr [r9], 0
0x140043bf9  movzx   ebp, r8w
0x140043bfd  mov     r14, rdx
0x140043c00  mov     r15, rcx
0x140043c03  test    rbx, rbx
0x140043c06  jz      short loc_140043C2D
0x140043c08  cmp     byte ptr [rbx+10h], 0
0x140043c0c  jnz     short loc_140043C14
0x140043c0e  xorps   xmm0, xmm0
0x140043c11  movups  xmmword ptr [rbx], xmm0
0x140043c14  mov     rcx, rbx; UnicodeString
0x140043c17  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140043c1c  xor     edx, edx; Tag
0x140043c1e  mov     rcx, rbx; P
0x140043c21  call    cs:__imp_ExFreePoolWithTag
0x140043c28  nop     dword ptr [rax+rax+00h]
0x140043c2d  mov     rbx, [rsp+58h+arg_20]
0x140043c35  lea     r8, [rsp+58h+arg_0]; unsigned __int16
0x140043c3a  movzx   edx, word ptr [r14]; unsigned __int16
0x140043c3e  xor     eax, eax
0x140043c40  movzx   ecx, word ptr [r15]; this
0x140043c44  mov     r9, rbx; unsigned __int16 *
0x140043c47  mov     [rsp+58h+arg_0], ax
0x140043c4c  call    ?ComputeCombinedPathLength@Utils@UnionFs@@YAJGGPEAGAEAVStackEventTracer@2@@Z; UnionFs::Utils::ComputeCombinedPathLength(ushort,ushort,ushort *,UnionFs::StackEventTracer &)
0x140043c51  mov     edi, eax
0x140043c53  test    eax, eax
0x140043c55  jns     short loc_140043C85
0x140043c57  lea     rax, aPushComputingC; "PUSH: Computing combined path length"
0x140043c5e  mov     r8, 36D001300D2h; struct UnionFs::StackEventTracer *
0x140043c68  lea     r9, aUnionfsUfspath_30; "UnionFs::UfsPathName::AllocAndInitWithC"...
0x140043c6f  mov     [rsp+58h+var_38], rax; char *
0x140043c74  mov     rdx, rbx; int
0x140043c77  mov     ecx, edi; this
0x140043c79  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140043c7e  mov     eax, edi
0x140043c80  jmp     loc_140043DA7
0x140043c85  movzx   ecx, [rsp+58h+arg_0]
0x140043c8a  lea     rdx, [rsp+58h+P]
0x140043c8f  mov     r8, rbx
0x140043c92  mov     [rsp+58h+P], 0
0x140043c9b  call    ?AllocEmpty@UfsPathName@UnionFs@@SAJGAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocEmpty(ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140043ca0  mov     edi, eax
0x140043ca2  test    eax, eax
0x140043ca4  jns     short loc_140043CFE
0x140043ca6  lea     rax, aPushAllocating_14; "PUSH: Allocating UfsPathName"
0x140043cad  mov     r8, 36E001300D8h; struct UnionFs::StackEventTracer *
0x140043cb7  lea     r9, aUnionfsUfspath_30; "UnionFs::UfsPathName::AllocAndInitWithC"...
0x140043cbe  mov     [rsp+58h+var_38], rax; char *
0x140043cc3  mov     rdx, rbx; int
0x140043cc6  mov     ecx, edi; this
0x140043cc8  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140043ccd  mov     rbx, [rsp+58h+P]
0x140043cd2  test    rbx, rbx
0x140043cd5  jz      short loc_140043C7E
0x140043cd7  cmp     byte ptr [rbx+10h], 0
0x140043cdb  jnz     short loc_140043CE3
0x140043cdd  xorps   xmm0, xmm0
0x140043ce0  movups  xmmword ptr [rbx], xmm0
0x140043ce3  mov     rcx, rbx; UnicodeString
0x140043ce6  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140043ceb  xor     edx, edx; Tag
0x140043ced  mov     rcx, rbx; P
0x140043cf0  call    cs:__imp_ExFreePoolWithTag
0x140043cf7  nop     dword ptr [rax+rax+00h]
0x140043cfc  jmp     short loc_140043C7E
0x140043cfe  mov     rdi, [rsp+58h+P]
0x140043d03  movzx   r9d, bp; unsigned __int16
0x140043d07  mov     rcx, rdi; this
0x140043d0a  mov     [rsp+58h+var_38], rbx; struct UnionFs::StackEventTracer *
0x140043d0f  mov     r8, r14; struct _UNICODE_STRING *
0x140043d12  mov     rdx, r15; struct _UNICODE_STRING *
0x140043d15  call    ?CombinePath@UfsPathName@UnionFs@@QEAAJAEBU_UNICODE_STRING@@0GAEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::CombinePath(_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,UnionFs::StackEventTracer &)
0x140043d1a  mov     ebp, eax
0x140043d1c  test    eax, eax
0x140043d1e  jns     short loc_140043D75
0x140043d20  lea     rax, aPushCombiningP; "PUSH: Combining paths"
0x140043d27  mov     r8, 36F001300DEh; struct UnionFs::StackEventTracer *
0x140043d31  lea     r9, aUnionfsUfspath_30; "UnionFs::UfsPathName::AllocAndInitWithC"...
0x140043d38  mov     [rsp+58h+var_38], rax; char *
0x140043d3d  mov     rdx, rbx; int
0x140043d40  mov     ecx, ebp; this
0x140043d42  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140043d47  test    rdi, rdi
0x140043d4a  jz      short loc_140043D71
0x140043d4c  cmp     byte ptr [rdi+10h], 0
0x140043d50  jnz     short loc_140043D58
0x140043d52  xorps   xmm0, xmm0
0x140043d55  movups  xmmword ptr [rdi], xmm0
0x140043d58  mov     rcx, rdi; UnicodeString
0x140043d5b  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140043d60  xor     edx, edx; Tag
0x140043d62  mov     rcx, rdi; P
0x140043d65  call    cs:__imp_ExFreePoolWithTag
0x140043d6c  nop     dword ptr [rax+rax+00h]
0x140043d71  mov     eax, ebp
0x140043d73  jmp     short loc_140043DA7
0x140043d75  mov     rbx, [rsi]
0x140043d78  mov     [rsi], rdi
0x140043d7b  test    rbx, rbx
0x140043d7e  jz      short loc_140043DA5
0x140043d80  cmp     byte ptr [rbx+10h], 0
0x140043d84  jnz     short loc_140043D8C
0x140043d86  xorps   xmm0, xmm0
0x140043d89  movups  xmmword ptr [rbx], xmm0
0x140043d8c  mov     rcx, rbx; UnicodeString
0x140043d8f  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140043d94  xor     edx, edx; Tag
0x140043d96  mov     rcx, rbx; P
0x140043d99  call    cs:__imp_ExFreePoolWithTag
0x140043da0  nop     dword ptr [rax+rax+00h]
0x140043da5  xor     eax, eax
0x140043da7  mov     rbx, [rsp+58h+arg_10]
0x140043dac  add     rsp, 30h
0x140043db0  pop     r15
0x140043db2  pop     r14
0x140043db4  pop     rdi
0x140043db5  pop     rsi
0x140043db6  pop     rbp
0x140043db7  retn
```
