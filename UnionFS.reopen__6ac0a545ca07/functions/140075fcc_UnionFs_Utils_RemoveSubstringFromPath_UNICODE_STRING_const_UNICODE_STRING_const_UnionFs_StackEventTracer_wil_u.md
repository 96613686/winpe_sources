# UnionFs::Utils::RemoveSubstringFromPath(_UNICODE_STRING const &,_UNICODE_STRING const &,UnionFs::StackEventTracer &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &)

- ea: `0x140075fcc`
- end: `0x1400761d1`
- name: `?RemoveSubstringFromPath@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@0AEAVStackEventTracer@2@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@Z`
- size: `517`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140020740`
- `0x140025208`
- `0x14005c680`

## callees

- `0x140056bd0`
- `0x140056c44`
- `0x14006e114`
- `0x140075fcc`
- `0x140079f68`
- `0x14007a02c`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400760d5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007614d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400760d5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007614d`

## string_xrefs

- `0x140076010`: `UnionFs::Utils::RemoveSubstringFromPath`
- `0x14007608b`: `UnionFs::Utils::RemoveSubstringFromPath`
- `0x1400760f8`: `UnionFs::Utils::RemoveSubstringFromPath`
- `0x1400761a6`: `UnionFs::Utils::RemoveSubstringFromPath`
- `0x140075ff2`: `ORIGIN: Substring is entire FullPath.`
- `0x140076033`: `ORIGIN: Could not find Substring in FullPath.`
- `0x14007615f`: `API: Copying suffix into final`
- `0x1400760e7`: `API: Copying prefix into final`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::RemoveSubstringFromPath(
        PWSTR *a1,
        const struct _UNICODE_STRING *a2,
        const struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  int v5; // edi
  const char *v8; // rax
  __int64 v9; // r8
  unsigned int appended; // ebx
  unsigned __int16 *UnicodeSubstring; // r15
  __int64 v12; // rdx
  PWSTR v13; // rbx
  struct _UNICODE_STRING *v14; // rdx
  __int64 v15; // r15
  const char *v16; // rax
  __int64 v17; // r8
  __int16 v18; // cx
  __int64 v19; // rdx
  __int16 v20; // ax
  USHORT v21; // cx
  PWSTR v22; // rax
  struct _UNICODE_STRING v23; // xmm0
  const char *v25; // [rsp+28h] [rbp-38h]
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-30h] BYREF
  UNICODE_STRING Source; // [rsp+40h] [rbp-20h] BYREF
  UNICODE_STRING v28; // [rsp+50h] [rbp-10h] BYREF

  v5 = (int)a3;
  if ( *(_WORD *)a1 != a2->Length )
  {
    LOBYTE(a3) = 1;
    UnicodeSubstring = UnionFs::Rtl::FindUnicodeSubstring((UnionFs::Rtl *)a1, a2, a3, (unsigned __int8)a4);
    if ( !UnicodeSubstring )
    {
      v8 = "ORIGIN: Could not find Substring in FullPath.";
      v9 = 0x37400210380LL;
      appended = -1073741275;
      goto LABEL_3;
    }
    v12 = *(unsigned __int16 *)a1;
    if ( (unsigned __int16)v12 < a2->Length )
    {
      appended = -1073741675;
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)0xC0000095LL,
        v5,
        (struct UnionFs::StackEventTracer *)0x3750021038ALL,
        (unsigned __int64)"UnionFs::Utils::RemoveSubstringFromPath",
        "API: Arithmetic error",
        v25);
      return appended;
    }
    v13 = a1[1];
    LOWORD(v12) = v12 - a2->Length;
    FsFltWil::MakeUniqueUnicodeString(&Destination, v12, 1279685446);
    if ( Destination.Buffer )
    {
      Source = 0;
      v15 = UnicodeSubstring - v13;
      Source.MaximumLength = 2 * v15;
      Source.Length = 2 * v15;
      Source.Buffer = a1[1];
      appended = RtlAppendUnicodeStringToString(&Destination, &Source);
      if ( (appended & 0x80000000) == 0 )
      {
        v18 = *(_WORD *)a1;
        v19 = (unsigned __int16)(v15 + (a2->Length >> 1));
        v20 = v15 + (a2->Length >> 1);
        v28 = 0;
        v21 = v18 - 2 * v20;
        v22 = a1[1];
        v28.MaximumLength = v21;
        v28.Length = v21;
        v28.Buffer = &v22[v19];
        appended = RtlAppendUnicodeStringToString(&Destination, &v28);
        if ( (appended & 0x80000000) == 0 )
        {
          appended = 0;
          v23 = Destination;
          Destination = *a4;
          *a4 = v23;
          goto LABEL_15;
        }
        v16 = "API: Copying suffix into final";
        v17 = 0x378002103ACLL;
      }
      else
      {
        v16 = "API: Copying prefix into final";
        v17 = 0x377002103A0LL;
      }
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)appended,
        v5,
        (struct UnionFs::StackEventTracer *)v17,
        (unsigned __int64)"UnionFs::Utils::RemoveSubstringFromPath",
        v16,
        v25);
    }
    else
    {
      appended = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        v5,
        (struct UnionFs::StackEventTracer *)0x37600210394LL,
        (unsigned __int64)"UnionFs::Utils::RemoveSubstringFromPath",
        "ORIGIN: Allocating final string",
        v25);
    }
LABEL_15:
    FsFltWil::Details::FreeUnicodeString(&Destination, v14);
    return appended;
  }
  v8 = "ORIGIN: Substring is entire FullPath.";
  v9 = 0x41000210375LL;
  appended = -1073741811;
LABEL_3:
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)appended,
    v5,
    (struct UnionFs::StackEventTracer *)v9,
    (unsigned __int64)"UnionFs::Utils::RemoveSubstringFromPath",
    v8,
    v25);
  return appended;
}

```

## disassembly

```asm
0x140075fcc  push    rbp
0x140075fce  push    rbx
0x140075fcf  push    rsi
0x140075fd0  push    rdi
0x140075fd1  push    r12
0x140075fd3  push    r14
0x140075fd5  push    r15
0x140075fd7  mov     rbp, rsp
0x140075fda  sub     rsp, 60h
0x140075fde  movzx   eax, word ptr [rdx]
0x140075fe1  mov     r12, r9
0x140075fe4  mov     rdi, r8
0x140075fe7  mov     r14, rdx
0x140075fea  mov     rsi, rcx
0x140075fed  cmp     [rcx], ax
0x140075ff0  jnz     short loc_140076023
0x140075ff2  lea     rax, aOriginSubstrin; "ORIGIN: Substring is entire FullPath."
0x140075ff9  mov     r8, 41000210375h; struct UnionFs::StackEventTracer *
0x140076003  mov     ebx, 0C000000Dh
0x140076008  mov     rdx, rdi; int
0x14007600b  mov     [rsp+60h+var_40], rax; char *
0x140076010  lea     r9, aUnionfsUtilsRe_3; "UnionFs::Utils::RemoveSubstringFromPath"
0x140076017  mov     ecx, ebx; this
0x140076019  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007601e  jmp     loc_1400761BF
0x140076023  mov     r8b, 1; struct _UNICODE_STRING *
0x140076026  call    ?FindUnicodeSubstring@Rtl@UnionFs@@YAPEAGPEBU_UNICODE_STRING@@0E@Z; UnionFs::Rtl::FindUnicodeSubstring(_UNICODE_STRING const *,_UNICODE_STRING const *,uchar)
0x14007602b  mov     r15, rax
0x14007602e  test    rax, rax
0x140076031  jnz     short loc_14007604B
0x140076033  lea     rax, aOriginCouldNot_3; "ORIGIN: Could not find Substring in Ful"...
0x14007603a  mov     r8, 37400210380h
0x140076044  mov     ebx, 0C0000225h
0x140076049  jmp     short loc_140076008
0x14007604b  movzx   eax, word ptr [r14]
0x14007604f  movzx   edx, word ptr [rsi]
0x140076052  cmp     dx, ax
0x140076055  jb      loc_140076193
0x14007605b  mov     rbx, [rsi+8]
0x14007605f  lea     rcx, [rbp+Destination]
0x140076063  sub     dx, ax
0x140076066  mov     r8d, 4C467346h
0x14007606c  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x140076071  cmp     [rbp+Destination.Buffer], 0
0x140076076  jnz     short loc_1400760A9
0x140076078  lea     rax, aOriginAllocati_2; "ORIGIN: Allocating final string"
0x14007607f  mov     ebx, 0C000009Ah
0x140076084  mov     ecx, ebx; this
0x140076086  mov     [rsp+60h+var_40], rax; char *
0x14007608b  lea     r9, aUnionfsUtilsRe_3; "UnionFs::Utils::RemoveSubstringFromPath"
0x140076092  mov     r8, 37600210394h; struct UnionFs::StackEventTracer *
0x14007609c  mov     rdx, rdi; int
0x14007609f  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400760a4  jmp     loc_140076188
0x1400760a9  xorps   xmm0, xmm0
0x1400760ac  lea     rdx, [rbp+Source]; Source
0x1400760b0  movups  xmmword ptr [rbp+Source.Length], xmm0
0x1400760b4  sub     r15, rbx
0x1400760b7  lea     rcx, [rbp+Destination]; Destination
0x1400760bb  sar     r15, 1
0x1400760be  movzx   eax, r15w
0x1400760c2  add     ax, ax
0x1400760c5  mov     [rbp+Source.MaximumLength], ax
0x1400760c9  mov     [rbp+Source.Length], ax
0x1400760cd  mov     rax, [rsi+8]
0x1400760d1  mov     [rbp+Source.Buffer], rax
0x1400760d5  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400760dc  nop     dword ptr [rax+rax+00h]
0x1400760e1  mov     ebx, eax
0x1400760e3  test    eax, eax
0x1400760e5  jns     short loc_140076110
0x1400760e7  lea     rax, aApiCopyingPref; "API: Copying prefix into final"
0x1400760ee  mov     r8, 377002103A0h; struct UnionFs::StackEventTracer *
0x1400760f8  lea     r9, aUnionfsUtilsRe_3; "UnionFs::Utils::RemoveSubstringFromPath"
0x1400760ff  mov     [rsp+60h+var_40], rax; char *
0x140076104  mov     rdx, rdi; int
0x140076107  mov     ecx, ebx; this
0x140076109  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007610e  jmp     short loc_140076188
0x140076110  movzx   eax, word ptr [r14]
0x140076114  xorps   xmm0, xmm0
0x140076117  movzx   ecx, word ptr [rsi]
0x14007611a  shr     ax, 1
0x14007611d  add     ax, r15w
0x140076121  movzx   edx, ax
0x140076124  movzx   eax, dx
0x140076127  movups  xmmword ptr [rbp+var_10.Length], xmm0
0x14007612b  add     ax, ax
0x14007612e  sub     cx, ax
0x140076131  mov     rax, [rsi+8]
0x140076135  mov     [rbp+var_10.MaximumLength], cx
0x140076139  mov     [rbp+var_10.Length], cx
0x14007613d  lea     rcx, [rax+rdx*2]
0x140076141  mov     [rbp+var_10.Buffer], rcx
0x140076145  lea     rdx, [rbp+var_10]; Source
0x140076149  lea     rcx, [rbp+Destination]; Destination
0x14007614d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140076154  nop     dword ptr [rax+rax+00h]
0x140076159  mov     ebx, eax
0x14007615b  test    eax, eax
0x14007615d  jns     short loc_140076172
0x14007615f  lea     rax, aApiCopyingSuff; "API: Copying suffix into final"
0x140076166  mov     r8, 378002103ACh
0x140076170  jmp     short loc_1400760F8
0x140076172  movups  xmm1, xmmword ptr [r12]
0x140076177  xor     ebx, ebx
0x140076179  movaps  xmm0, xmmword ptr [rbp+Destination.Length]
0x14007617d  movdqa  xmmword ptr [rbp+Destination.Length], xmm1
0x140076182  movdqu  xmmword ptr [r12], xmm0
0x140076188  lea     rcx, [rbp+Destination]; UnicodeString
0x14007618c  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140076191  jmp     short loc_1400761BF
0x140076193  lea     rax, aApiArithmeticE; "API: Arithmetic error"
0x14007619a  mov     ebx, 0C0000095h
0x14007619f  mov     ecx, ebx; this
0x1400761a1  mov     [rsp+60h+var_40], rax; char *
0x1400761a6  lea     r9, aUnionfsUtilsRe_3; "UnionFs::Utils::RemoveSubstringFromPath"
0x1400761ad  mov     r8, 3750021038Ah; struct UnionFs::StackEventTracer *
0x1400761b7  mov     rdx, rdi; int
0x1400761ba  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400761bf  mov     eax, ebx
0x1400761c1  add     rsp, 60h
0x1400761c5  pop     r15
0x1400761c7  pop     r14
0x1400761c9  pop     r12
0x1400761cb  pop     rdi
0x1400761cc  pop     rsi
0x1400761cd  pop     rbx
0x1400761ce  pop     rbp
0x1400761cf  retn
```
