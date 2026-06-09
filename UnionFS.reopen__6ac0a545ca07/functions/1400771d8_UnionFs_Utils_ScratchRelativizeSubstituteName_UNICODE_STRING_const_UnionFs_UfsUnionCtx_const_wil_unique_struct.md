# UnionFs::Utils::ScratchRelativizeSubstituteName(_UNICODE_STRING const &,UnionFs::UfsUnionCtx const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)

- ea: `0x1400771d8`
- end: `0x14007790a`
- name: `?ScratchRelativizeSubstituteName@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBVUfsUnionCtx@2@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z`
- size: `1842`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, int, PUNICODE_STRING UnicodeString, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140078dc0`
- `0x1400790f0`

## callees

- `0x14000f81c`
- `0x140043d5c`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x1400602c8`
- `0x14006e088`
- `0x1400771d8`
- `0x140079d44`
- `0x140079f68`
- `0x14007a02c`
- `0x14007a0c0`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140077225`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140077262`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400772b4`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400772ff`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140077225`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140077262`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400772b4`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400772ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077608`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400776eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077722`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400777f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007782a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077889`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400778c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077608`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400776eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077722`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400777f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007782a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077889`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400778c0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140077864`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140077864`
- `FLTMGR!FltGetVolumeName` at `0x1400774a5`
- `FLTMGR!FltGetVolumeName` at `0x14007751a`
- `FLTMGR!FltGetVolumeName` at `0x1400774a5`
- `FLTMGR!FltGetVolumeName` at `0x14007751a`
- `FLTMGR!FltGetVolumeFromName` at `0x14007740f`
- `FLTMGR!FltGetVolumeFromName` at `0x14007740f`
- `FLTMGR!FltObjectDereference` at `0x140077433`
- `FLTMGR!FltObjectDereference` at `0x14007747b`
- `FLTMGR!FltObjectDereference` at `0x140077627`
- `FLTMGR!FltObjectDereference` at `0x140077741`
- `FLTMGR!FltObjectDereference` at `0x140077849`
- `FLTMGR!FltObjectDereference` at `0x1400778df`
- `FLTMGR!FltObjectDereference` at `0x140077433`
- `FLTMGR!FltObjectDereference` at `0x14007747b`
- `FLTMGR!FltObjectDereference` at `0x140077627`
- `FLTMGR!FltObjectDereference` at `0x140077741`
- `FLTMGR!FltObjectDereference` at `0x140077849`
- `FLTMGR!FltObjectDereference` at `0x1400778df`

## string_xrefs

- `0x1400776a1`: `PUSH: Converting layer path to scratch path`
- `0x1400774e5`: `ORIGIN: Allocating temp string for volume name`
- `0x140077322`: `UnionFs::Utils::GetVolumeLengthFromPath`
- `0x1400775bf`: `PUSH: Creating UfsPathName`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::ScratchRelativizeSubstituteName(
        PCUNICODE_STRING String2,
        __int64 a2,
        PUNICODE_STRING UnicodeString,
        struct UnionFs::StackEventTracer *a4)
{
  unsigned __int64 v8; // rsi
  PWSTR *p_Buffer; // rbx
  USHORT Length; // cx
  PWSTR Buffer; // rdx
  WCHAR v12; // cx
  BOOLEAN v13; // si
  unsigned __int16 v14; // r8
  NTSTATUS VolumeFromName; // ebx
  USHORT v17; // dx
  WCHAR *v18; // r8
  struct _FLT_FILTER *v19; // rcx
  PWSTR *v20; // rdi
  PWSTR v21; // rsi
  struct _FLT_VOLUME *v22; // rbx
  __int64 v23; // rdx
  struct _UNICODE_STRING *v24; // rdx
  struct _UNICODE_STRING v25; // xmm0
  WCHAR *v26; // rcx
  struct _UNICODE_STRING *v27; // rdx
  int v28; // edi
  struct _UNICODE_STRING *v29; // rdx
  struct _UNICODE_STRING *v30; // rbx
  unsigned __int64 *v31; // rdx
  _QWORD *v32; // rcx
  __int64 v33; // rdi
  __int64 v34; // rbx
  struct _UNICODE_STRING *v35; // rdx
  int v36; // r15d
  struct _UNICODE_STRING *v37; // rdx
  struct _UNICODE_STRING *v38; // rsi
  __int64 v39; // rsi
  __int64 v40; // rdx
  struct _UNICODE_STRING *UniqueUnicodeString; // rax
  struct _UNICODE_STRING *v42; // rdx
  struct _UNICODE_STRING v43; // xmm6
  struct _UNICODE_STRING *v44; // rdx
  struct _UNICODE_STRING *v45; // rdx
  struct _UNICODE_STRING *v46; // rdx
  char *v47; // [rsp+30h] [rbp-91h]
  char *v48; // [rsp+30h] [rbp-91h]
  char *v49; // [rsp+30h] [rbp-91h]
  struct _FLT_VOLUME *v50; // [rsp+38h] [rbp-89h] BYREF
  UNICODE_STRING String2a; // [rsp+48h] [rbp-79h] BYREF
  unsigned __int16 v52[8]; // [rsp+58h] [rbp-69h] BYREF
  struct _UNICODE_STRING UnicodeStringa; // [rsp+68h] [rbp-59h] BYREF
  struct _UNICODE_STRING v54; // [rsp+78h] [rbp-49h] BYREF
  char v55; // [rsp+88h] [rbp-39h]
  UNICODE_STRING VolumeName; // [rsp+90h] [rbp-31h] BYREF
  struct _UNICODE_STRING v57; // [rsp+A0h] [rbp-21h] BYREF
  UNICODE_STRING SourceString; // [rsp+B0h] [rbp-11h] BYREF
  __int64 BufferSizeNeeded; // [rsp+128h] [rbp+67h] BYREF

  FsFltWil::Details::FreeUnicodeString(UnicodeString, (struct _UNICODE_STRING *)a2);
  *UnicodeString = 0;
  v8 = (unsigned __int64)String2->Length >> 1;
  if ( RtlPrefixUnicodeString(&String1, String2, 1u)
    && v8 >= 0x31
    && (p_Buffer = &String2->Buffer, String2->Buffer[47] == 125) )
  {
    Length = 96;
  }
  else if ( RtlPrefixUnicodeString(&stru_14007EE48, String2, 1u)
         && v8 >= 6
         && ((p_Buffer = &String2->Buffer,
              Buffer = String2->Buffer,
              v12 = Buffer[4],
              (unsigned __int16)(v12 - 97) <= 0x19u)
          || (unsigned __int16)(v12 - 65) <= 0x19u)
         && Buffer[5] == 58 )
  {
    Length = 12;
  }
  else
  {
    v13 = RtlPrefixUnicodeString(&stru_14007EE58, String2, 1u);
    p_Buffer = &String2->Buffer;
    String2a = *String2;
    if ( v13 )
    {
      String2a.Buffer = *p_Buffer + 14;
      String2a.Length = String2->Length - 28;
      String2a.MaximumLength = String2a.Length;
    }
    if ( !RtlPrefixUnicodeString(&stru_14007EE68, &String2a, 1u) )
    {
      VolumeFromName = -1073741773;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000033LL,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x6B900210B67LL,
        (unsigned __int64)"UnionFs::Utils::GetVolumeLengthFromPath",
        "ORIGIN: Unrecognized SubstituteName format",
        v47);
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)0xC0000033LL,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x6BA00210B8FLL,
        (unsigned __int64)"UnionFs::Utils::ScratchRelativizeSubstituteName",
        "PUSH: Getting volume length",
        v48);
      return (unsigned int)VolumeFromName;
    }
    v52[0] = 16;
    LOWORD(BufferSizeNeeded) = 0;
    if ( UnionFs::Utils::FindCharForward(
           (UnionFs::Utils *)String2a.Buffer,
           (const unsigned __int16 *)String2a.Length,
           v14,
           (unsigned __int16)&BufferSizeNeeded,
           v52,
           (unsigned __int16 *)v47) )
    {
      Length = BufferSizeNeeded + (v13 != 0 ? 26 : -2);
    }
    else
    {
      Length = String2->Length;
    }
  }
  v17 = String2->Length;
  v18 = *p_Buffer;
  *(_DWORD *)(&VolumeName.MaximumLength + 1) = 0;
  VolumeName.Buffer = v18;
  VolumeName.Length = Length;
  VolumeName.MaximumLength = Length;
  v57 = 0;
  if ( Length < v17 )
  {
    v57.Buffer = (WCHAR *)((char *)v18 + Length);
    v57.Length = v17 - Length;
    v57.MaximumLength = v17 - Length;
  }
  v50 = 0;
  *(_QWORD *)&v54.Length = &v50;
  v54.Buffer = 0;
  v19 = *(struct _FLT_FILTER **)UnionFs::g_FilterState;
  v55 = 1;
  VolumeFromName = FltGetVolumeFromName(v19, &VolumeName, (PFLT_VOLUME *)&v54.Buffer);
  if ( v55 )
  {
    v20 = *(PWSTR **)&v54.Length;
    v21 = v54.Buffer;
    if ( **(_QWORD **)&v54.Length )
      FltObjectDereference(**(PVOID **)&v54.Length);
    *v20 = v21;
  }
  if ( VolumeFromName < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)VolumeFromName,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x6BB00210BA6LL,
      (unsigned __int64)"UnionFs::Utils::ScratchRelativizeSubstituteName",
      "API: FltGetVolumeFromName",
      v47);
    goto LABEL_27;
  }
  v22 = v50;
  LODWORD(BufferSizeNeeded) = 0;
  UnicodeStringa = 0;
  FltGetVolumeName(v50, 0, (PULONG)&BufferSizeNeeded);
  v23 = (unsigned int)BufferSizeNeeded;
  if ( (unsigned int)BufferSizeNeeded > 0xFFFF )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("volumeNameSize <= MAXUSHORT");
    v23 = (unsigned int)BufferSizeNeeded;
  }
  FsFltWil::MakeUniqueUnicodeString(&String2a, v23, 1279685446);
  if ( String2a.Buffer )
  {
    FltGetVolumeName(v22, &String2a, 0);
    VolumeFromName = 0;
    v25 = String2a;
    v26 = UnicodeStringa.Buffer;
    v54.Length = UnicodeStringa.Length;
    *(_DWORD *)&v54.MaximumLength = *(_DWORD *)&UnicodeStringa.MaximumLength;
    *(&v54.MaximumLength + 2) = *(&UnicodeStringa.MaximumLength + 2);
    *(_QWORD *)&String2a.Length = *(_QWORD *)&v54.Length;
    UnicodeStringa = v25;
    String2a.Buffer = v26;
  }
  else
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x40E00212409LL,
      (unsigned __int64)"UnionFs::Utils::GetVolumeName",
      "ORIGIN: Allocating temp string for volume name",
      v47);
    VolumeFromName = -1073741670;
  }
  FsFltWil::Details::FreeUnicodeString(&String2a, v24);
  if ( VolumeFromName < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)VolumeFromName,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x6BC00210BACLL,
      (unsigned __int64)"UnionFs::Utils::ScratchRelativizeSubstituteName",
      "PUSH: GetVolumeName",
      v47);
    FsFltWil::Details::FreeUnicodeString(&UnicodeStringa, v27);
LABEL_27:
    if ( v50 )
      FltObjectDereference(v50);
    return (unsigned int)VolumeFromName;
  }
  BufferSizeNeeded = 0;
  v28 = UnionFs::UfsPathName::AllocAndInitWithCombinedPaths(&UnicodeStringa, &v57, a4);
  if ( v28 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v28,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x6BE00210BB7LL,
      (unsigned __int64)"UnionFs::Utils::ScratchRelativizeSubstituteName",
      "PUSH: Creating UfsPathName",
      v47);
    v30 = (struct _UNICODE_STRING *)BufferSizeNeeded;
    if ( BufferSizeNeeded )
    {
      if ( !*(_BYTE *)(BufferSizeNeeded + 16) )
        *(_OWORD *)BufferSizeNeeded = 0;
      FsFltWil::Details::FreeUnicodeString(v30, v29);
      ExFreePoolWithTag(v30, 0);
    }
    FsFltWil::Details::FreeUnicodeString(&UnicodeStringa, v29);
    if ( v50 )
      FltObjectDereference(v50);
    return (unsigned int)v28;
  }
  FsFltWil::AcquirePushLockShared(&String2a, a2 + 72);
  v32 = *(_QWORD **)(a2 + 48);
  v33 = v32[1];
  *(_QWORD *)&v54.Length = *v32;
  v54.Buffer = (PWSTR)v33;
  if ( v33 )
    _InterlockedIncrement((volatile signed __int32 *)(v33 + 8));
  if ( *(_QWORD *)&String2a.Length )
    FsFltWil::Details::ReleasePushLockShared(*(FsFltWil::Details **)&String2a.Length, v31);
  v34 = BufferSizeNeeded;
  *(_QWORD *)&String2a.Length = 0;
  v36 = UnionFs::UfsUnionCtx::ConvertLayerPathToScratchPath(
          a2,
          BufferSizeNeeded,
          (int)&String2a,
          (int)&v54,
          (char *)a4,
          0);
  if ( v36 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v36,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x6BF00210BBFLL,
      (unsigned __int64)"UnionFs::Utils::ScratchRelativizeSubstituteName",
      "PUSH: Converting layer path to scratch path",
      v49);
    v38 = *(struct _UNICODE_STRING **)&String2a.Length;
    if ( *(_QWORD *)&String2a.Length )
    {
      if ( !*(_BYTE *)(*(_QWORD *)&String2a.Length + 16LL) )
        *(_OWORD *)*(_QWORD *)&String2a.Length = 0;
      FsFltWil::Details::FreeUnicodeString(v38, v37);
      ExFreePoolWithTag(v38, 0);
    }
    if ( v33 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v33);
    if ( v34 )
    {
      if ( !*(_BYTE *)(v34 + 16) )
        *(_OWORD *)v34 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v34, v37);
      ExFreePoolWithTag((PVOID)v34, 0);
    }
    FsFltWil::Details::FreeUnicodeString(&UnicodeStringa, v37);
    if ( v50 )
      FltObjectDereference(v50);
    return (unsigned int)v36;
  }
  v39 = *(_QWORD *)&String2a.Length;
  if ( *(_QWORD *)&String2a.Length )
  {
    v40 = (unsigned int)_mm_cvtsi128_si32(**(__m128i **)&String2a.Length);
    SourceString = *(UNICODE_STRING *)*(_QWORD *)&String2a.Length;
    UniqueUnicodeString = (struct _UNICODE_STRING *)FsFltWil::MakeUniqueUnicodeString(&v54, v40, 1279685446);
    if ( UnicodeString != UniqueUnicodeString )
    {
      v43 = *UniqueUnicodeString;
      *UniqueUnicodeString = 0;
      FsFltWil::Details::FreeUnicodeString(UnicodeString, v42);
      *UnicodeString = v43;
    }
    FsFltWil::Details::FreeUnicodeString(&v54, v42);
    if ( !UnicodeString->Buffer )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x6C100210BCELL,
        (unsigned __int64)"UnionFs::Utils::ScratchRelativizeSubstituteName",
        "ORIGIN: Allocating munged substitute name",
        v49);
      if ( !*(_BYTE *)(v39 + 16) )
        *(_OWORD *)v39 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v39, v44);
      ExFreePoolWithTag((PVOID)v39, 0);
      if ( v33 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v33);
      if ( v34 )
      {
        if ( !*(_BYTE *)(v34 + 16) )
          *(_OWORD *)v34 = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v34, v45);
        ExFreePoolWithTag((PVOID)v34, 0);
      }
      FsFltWil::Details::FreeUnicodeString(&UnicodeStringa, v45);
      if ( v50 )
        FltObjectDereference(v50);
      return 3221225626LL;
    }
    RtlCopyUnicodeString(UnicodeString, &SourceString);
    if ( !*(_BYTE *)(v39 + 16) )
      *(_OWORD *)v39 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v39, v46);
    ExFreePoolWithTag((PVOID)v39, 0);
  }
  if ( v33 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v33);
  if ( v34 )
  {
    if ( !*(_BYTE *)(v34 + 16) )
      *(_OWORD *)v34 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v34, v35);
    ExFreePoolWithTag((PVOID)v34, 0);
  }
  FsFltWil::Details::FreeUnicodeString(&UnicodeStringa, v35);
  if ( v50 )
    FltObjectDereference(v50);
  return 0;
}

```

## disassembly

```asm
0x1400771d8  mov     rax, rsp
0x1400771db  push    rbp
0x1400771dc  push    rbx
0x1400771dd  push    rsi
0x1400771de  push    rdi
0x1400771df  push    r12
0x1400771e1  push    r13
0x1400771e3  push    r14
0x1400771e5  push    r15
0x1400771e7  lea     rbp, [rax-5Fh]
0x1400771eb  sub     rsp, 0D8h
0x1400771f2  mov     rdi, rcx
0x1400771f5  movaps  xmmword ptr [rax-58h], xmm6
0x1400771f9  mov     rcx, r8; UnicodeString
0x1400771fc  mov     r14, r9
0x1400771ff  mov     r12, r8
0x140077202  mov     r15, rdx
0x140077205  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14007720a  xorps   xmm0, xmm0
0x14007720d  lea     rcx, String1; String1
0x140077214  movups  xmmword ptr [r12], xmm0
0x140077219  movzx   esi, word ptr [rdi]
0x14007721c  mov     r8b, 1; CaseInSensitive
0x14007721f  mov     rdx, rdi; String2
0x140077222  shr     rsi, 1
0x140077225  call    cs:__imp_RtlPrefixUnicodeString
0x14007722c  nop     dword ptr [rax+rax+00h]
0x140077231  xor     r13d, r13d
0x140077234  test    al, al
0x140077236  jz      short loc_140077255
0x140077238  cmp     rsi, 31h ; '1'
0x14007723c  jb      short loc_140077255
0x14007723e  lea     rbx, [rdi+8]
0x140077242  mov     rax, [rbx]
0x140077245  cmp     word ptr [rax+5Eh], 7Dh ; '}'
0x14007724a  jnz     short loc_140077255
0x14007724c  lea     ecx, [r13+60h]
0x140077250  jmp     loc_1400773B0
0x140077255  mov     r8b, 1; CaseInSensitive
0x140077258  lea     rcx, stru_14007EE48; String1
0x14007725f  mov     rdx, rdi; String2
0x140077262  call    cs:__imp_RtlPrefixUnicodeString
0x140077269  nop     dword ptr [rax+rax+00h]
0x14007726e  test    al, al
0x140077270  jz      short loc_1400772A7
0x140077272  cmp     rsi, 6
0x140077276  jb      short loc_1400772A7
0x140077278  lea     rbx, [rdi+8]
0x14007727c  mov     rdx, [rbx]
0x14007727f  movzx   ecx, word ptr [rdx+8]
0x140077283  lea     eax, [rcx-61h]
0x140077286  cmp     ax, 19h
0x14007728a  jbe     short loc_140077296
0x14007728c  sub     cx, 41h ; 'A'
0x140077290  cmp     cx, 19h
0x140077294  ja      short loc_1400772A7
0x140077296  cmp     word ptr [rdx+0Ah], 3Ah ; ':'
0x14007729b  jnz     short loc_1400772A7
0x14007729d  mov     ecx, 0Ch
0x1400772a2  jmp     loc_1400773B0
0x1400772a7  mov     r8b, 1; CaseInSensitive
0x1400772aa  lea     rcx, stru_14007EE58; String1
0x1400772b1  mov     rdx, rdi; String2
0x1400772b4  call    cs:__imp_RtlPrefixUnicodeString
0x1400772bb  nop     dword ptr [rax+rax+00h]
0x1400772c0  movups  xmm0, xmmword ptr [rdi]
0x1400772c3  mov     sil, al
0x1400772c6  lea     rbx, [rdi+8]
0x1400772ca  mov     eax, 1Ch
0x1400772cf  movdqu  xmmword ptr [rbp+57h+String2.Length], xmm0
0x1400772d4  test    sil, sil
0x1400772d7  jz      short loc_1400772F1
0x1400772d9  mov     rcx, [rbx]
0x1400772dc  add     rcx, rax
0x1400772df  mov     [rbp+57h+String2.Buffer], rcx
0x1400772e3  movzx   ecx, word ptr [rdi]
0x1400772e6  sub     cx, ax
0x1400772e9  mov     [rbp+57h+String2.Length], cx
0x1400772ed  mov     [rbp+57h+String2.MaximumLength], cx
0x1400772f1  mov     r8b, 1; CaseInSensitive
0x1400772f4  lea     rdx, [rbp+57h+String2]; String2
0x1400772f8  lea     rcx, stru_14007EE68; String1
0x1400772ff  call    cs:__imp_RtlPrefixUnicodeString
0x140077306  nop     dword ptr [rax+rax+00h]
0x14007730b  test    al, al
0x14007730d  jnz     short loc_140077369
0x14007730f  lea     rax, aOriginUnrecogn_0; "ORIGIN: Unrecognized SubstituteName for"...
0x140077316  mov     ebx, 0C0000033h
0x14007731b  mov     ecx, ebx; this
0x14007731d  mov     [rsp+110h+var_F0], rax; char *
0x140077322  lea     r9, aUnionfsUtilsGe_1; "UnionFs::Utils::GetVolumeLengthFromPath"
0x140077329  mov     r8, 6B900210B67h; struct UnionFs::StackEventTracer *
0x140077333  mov     rdx, r14; int
0x140077336  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007733b  lea     rcx, aPushGettingVol_0; "PUSH: Getting volume length"
0x140077342  mov     r8, 6BA00210B8Fh; struct UnionFs::StackEventTracer *
0x14007734c  mov     [rsp+110h+var_F0], rcx; char *
0x140077351  lea     r9, aUnionfsUtilsSc; "UnionFs::Utils::ScratchRelativizeSubsti"...
0x140077358  mov     ecx, ebx; this
0x14007735a  mov     rdx, r14; int
0x14007735d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140077362  mov     eax, ebx
0x140077364  jmp     loc_1400778ED
0x140077369  movzx   edx, [rbp+57h+String2.Length]; unsigned __int16 *
0x14007736d  lea     r9, [rbp+57h+BufferSizeNeeded]; unsigned __int16
0x140077371  mov     rcx, [rbp+57h+String2.Buffer]; this
0x140077375  mov     eax, 10h
0x14007737a  mov     [rbp+57h+var_C0], ax
0x14007737e  lea     rax, [rbp+57h+var_C0]
0x140077382  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x140077387  mov     word ptr [rbp+57h+BufferSizeNeeded], r13w
0x14007738c  call    ?FindCharForward@Utils@UnionFs@@YA_NPEBGGGPEAG1@Z; UnionFs::Utils::FindCharForward(ushort const *,ushort,ushort,ushort *,ushort *)
0x140077391  test    al, al
0x140077393  jz      short loc_1400773AD
0x140077395  neg     sil
0x140077398  mov     ecx, 1Ch
0x14007739d  sbb     ax, ax
0x1400773a0  and     cx, ax
0x1400773a3  sub     cx, 2
0x1400773a7  add     cx, word ptr [rbp+57h+BufferSizeNeeded]
0x1400773ab  jmp     short loc_1400773B0
0x1400773ad  movzx   ecx, word ptr [rdi]
0x1400773b0  movzx   edx, word ptr [rdi]
0x1400773b3  xorps   xmm0, xmm0
0x1400773b6  mov     r8, [rbx]
0x1400773b9  mov     dword ptr [rbp+57h+VolumeName+4], r13d
0x1400773bd  mov     [rbp+57h+VolumeName.Buffer], r8
0x1400773c1  mov     [rbp+57h+VolumeName.Length], cx
0x1400773c5  mov     [rbp+57h+VolumeName.MaximumLength], cx
0x1400773c9  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x1400773cd  cmp     cx, dx
0x1400773d0  jnb     short loc_1400773E7
0x1400773d2  movzx   eax, cx
0x1400773d5  add     rax, r8
0x1400773d8  sub     dx, cx
0x1400773db  mov     [rbp+57h+var_78.Buffer], rax
0x1400773df  mov     [rbp+57h+var_78.Length], dx
0x1400773e3  mov     [rbp+57h+var_78.MaximumLength], dx
0x1400773e7  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400773ee  lea     rax, [rsp+110h+var_E0]
0x1400773f3  mov     [rsp+110h+var_E0], r13
0x1400773f8  lea     r8, [rbp+57h+var_A0.Buffer]; RetVolume
0x1400773fc  lea     rdx, [rbp+57h+VolumeName]; VolumeName
0x140077400  mov     qword ptr [rbp+57h+var_A0.Length], rax
0x140077404  mov     [rbp+57h+var_A0.Buffer], r13
0x140077408  mov     rcx, [rcx]; Filter
0x14007740b  mov     [rbp+57h+var_90], 1
0x14007740f  call    cs:__imp_FltGetVolumeFromName
0x140077416  nop     dword ptr [rax+rax+00h]
0x14007741b  mov     ebx, eax
0x14007741d  cmp     [rbp+57h+var_90], r13b
0x140077421  jz      short loc_140077442
0x140077423  mov     rdi, qword ptr [rbp+57h+var_A0.Length]
0x140077427  mov     rsi, [rbp+57h+var_A0.Buffer]
0x14007742b  mov     rcx, [rdi]; FltObject
0x14007742e  test    rcx, rcx
0x140077431  jz      short loc_14007743F
0x140077433  call    cs:__imp_FltObjectDereference
0x14007743a  nop     dword ptr [rax+rax+00h]
0x14007743f  mov     [rdi], rsi
0x140077442  test    ebx, ebx
0x140077444  jns     short loc_14007748C
0x140077446  lea     rax, aApiFltgetvolum_1; "API: FltGetVolumeFromName"
0x14007744d  mov     r8, 6BB00210BA6h; struct UnionFs::StackEventTracer *
0x140077457  lea     r9, aUnionfsUtilsSc; "UnionFs::Utils::ScratchRelativizeSubsti"...
0x14007745e  mov     [rsp+110h+var_F0], rax; char *
0x140077463  mov     rdx, r14; int
0x140077466  mov     ecx, ebx; this
0x140077468  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007746d  mov     rcx, [rsp+110h+var_E0]; FltObject
0x140077472  test    rcx, rcx
0x140077475  jz      loc_140077362
0x14007747b  call    cs:__imp_FltObjectDereference
0x140077482  nop     dword ptr [rax+rax+00h]
0x140077487  jmp     loc_140077362
0x14007748c  mov     rbx, [rsp+110h+var_E0]
0x140077491  lea     r8, [rbp+57h+BufferSizeNeeded]; BufferSizeNeeded
0x140077495  xorps   xmm0, xmm0
0x140077498  mov     dword ptr [rbp+57h+BufferSizeNeeded], r13d
0x14007749c  mov     rcx, rbx; Volume
0x14007749f  xor     edx, edx; VolumeName
0x1400774a1  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x1400774a5  call    cs:__imp_FltGetVolumeName
0x1400774ac  nop     dword ptr [rax+rax+00h]
0x1400774b1  mov     edx, dword ptr [rbp+57h+BufferSizeNeeded]
0x1400774b4  cmp     edx, 0FFFFh
0x1400774ba  jbe     short loc_1400774CB
0x1400774bc  lea     rcx, aVolumenamesize; "volumeNameSize <= MAXUSHORT"
0x1400774c3  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400774c8  mov     edx, dword ptr [rbp+57h+BufferSizeNeeded]
0x1400774cb  mov     r8d, 4C467346h
0x1400774d1  lea     rcx, [rbp+57h+String2]
0x1400774d5  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x1400774da  mov     edi, 0C000009Ah
0x1400774df  cmp     [rbp+57h+String2.Buffer], r13
0x1400774e3  jnz     short loc_140077510
0x1400774e5  lea     rax, aOriginAllocati_67; "ORIGIN: Allocating temp string for volu"...
0x1400774ec  mov     r8, 40E00212409h; struct UnionFs::StackEventTracer *
0x1400774f6  lea     r9, aUnionfsUtilsGe; "UnionFs::Utils::GetVolumeName"
0x1400774fd  mov     [rsp+110h+var_F0], rax; char *
0x140077502  mov     rdx, r14; int
0x140077505  mov     ecx, edi; this
0x140077507  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007750c  mov     ebx, edi
0x14007750e  jmp     short loc_140077558
0x140077510  xor     r8d, r8d; BufferSizeNeeded
0x140077513  lea     rdx, [rbp+57h+String2]; VolumeName
0x140077517  mov     rcx, rbx; Volume
0x14007751a  call    cs:__imp_FltGetVolumeName
0x140077521  nop     dword ptr [rax+rax+00h]
0x140077526  movzx   eax, [rbp+57h+UnicodeString.Length]
0x14007752a  mov     ebx, r13d
0x14007752d  movaps  xmm0, xmmword ptr [rbp+57h+String2.Length]
0x140077531  mov     rcx, [rbp+57h+UnicodeString.Buffer]
0x140077535  mov     [rbp+57h+var_A0.Length], ax
0x140077539  mov     eax, dword ptr [rbp+57h+UnicodeString.MaximumLength]
0x14007753c  mov     dword ptr [rbp+57h+var_A0.MaximumLength], eax
0x14007753f  movzx   eax, word ptr [rbp+57h+UnicodeString+6]
0x140077543  mov     word ptr [rbp+57h+var_A0+6], ax
0x140077547  mov     rax, qword ptr [rbp+57h+var_A0.Length]
0x14007754b  mov     qword ptr [rbp+57h+String2.Length], rax
0x14007754f  movdqa  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x140077554  mov     [rbp+57h+String2.Buffer], rcx
0x140077558  lea     rcx, [rbp+57h+String2]; UnicodeString
0x14007755c  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140077561  test    ebx, ebx
0x140077563  jns     short loc_14007759A
0x140077565  lea     rax, aPushGetvolumen; "PUSH: GetVolumeName"
0x14007756c  mov     r8, 6BC00210BACh; struct UnionFs::StackEventTracer *
0x140077576  lea     r9, aUnionfsUtilsSc; "UnionFs::Utils::ScratchRelativizeSubsti"...
0x14007757d  mov     [rsp+110h+var_F0], rax; char *
0x140077582  mov     rdx, r14; int
0x140077585  mov     ecx, ebx; this
0x140077587  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007758c  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x140077590  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140077595  jmp     loc_14007746D
0x14007759a  movzx   r8d, [rbp+57h+UnicodeString.Length]
0x14007759f  lea     r9, [rbp+57h+BufferSizeNeeded]
0x1400775a3  lea     rdx, [rbp+57h+var_78]; struct _UNICODE_STRING *
0x1400775a7  mov     [rbp+57h+BufferSizeNeeded], r13
0x1400775ab  lea     rcx, [rbp+57h+UnicodeString]; struct _UNICODE_STRING *
0x1400775af  mov     [rsp+110h+var_F0], r14; struct UnionFs::StackEventTracer *
0x1400775b4  call    ?AllocAndInitWithCombinedPaths@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@0GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInitWithCombinedPaths(_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x1400775b9  mov     edi, eax
0x1400775bb  test    eax, eax
0x1400775bd  jns     short loc_14007763A
0x1400775bf  lea     rax, aPushCreatingUf; "PUSH: Creating UfsPathName"
0x1400775c6  mov     r8, 6BE00210BB7h; struct UnionFs::StackEventTracer *
0x1400775d0  lea     r9, aUnionfsUtilsSc; "UnionFs::Utils::ScratchRelativizeSubsti"...
0x1400775d7  mov     [rsp+110h+var_F0], rax; char *
0x1400775dc  mov     rdx, r14; int
0x1400775df  mov     ecx, edi; this
0x1400775e1  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400775e6  mov     rbx, [rbp+57h+BufferSizeNeeded]
0x1400775ea  test    rbx, rbx
0x1400775ed  jz      short loc_140077614
0x1400775ef  cmp     [rbx+10h], r13b
0x1400775f3  jnz     short loc_1400775FB
0x1400775f5  xorps   xmm0, xmm0
0x1400775f8  movups  xmmword ptr [rbx], xmm0
0x1400775fb  mov     rcx, rbx; UnicodeString
0x1400775fe  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140077603  xor     edx, edx; Tag
0x140077605  mov     rcx, rbx; P
0x140077608  call    cs:__imp_ExFreePoolWithTag
0x14007760f  nop     dword ptr [rax+rax+00h]
0x140077614  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x140077618  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14007761d  mov     rcx, [rsp+110h+var_E0]; FltObject
0x140077622  test    rcx, rcx
0x140077625  jz      short loc_140077633
0x140077627  call    cs:__imp_FltObjectDereference
0x14007762e  nop     dword ptr [rax+rax+00h]
0x140077633  mov     eax, edi
0x140077635  jmp     loc_1400778ED
0x14007763a  lea     rdx, [r15+48h]
0x14007763e  lea     rcx, [rbp+57h+String2]
0x140077642  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140077647  mov     rcx, [r15+30h]
0x14007764b  mov     rdi, [rcx+8]
0x14007764f  mov     rax, [rcx]
0x140077652  mov     qword ptr [rbp+57h+var_A0.Length], rax
0x140077656  mov     [rbp+57h+var_A0.Buffer], rdi
0x14007765a  test    rdi, rdi
0x14007765d  jz      short loc_140077663
0x14007765f  lock inc dword ptr [rdi+8]
0x140077663  mov     rcx, qword ptr [rbp+57h+String2.Length]; this
0x140077667  test    rcx, rcx
0x14007766a  jz      short loc_140077671
0x14007766c  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140077671  mov     rbx, [rbp+57h+BufferSizeNeeded]
0x140077675  lea     r9, [rbp+57h+var_A0]; int
0x140077679  mov     rdx, rbx; int
0x14007767c  mov     [rsp+110h+var_E8], r13; char *
0x140077681  lea     r8, [rbp+57h+String2]; int
0x140077685  mov     qword ptr [rbp+57h+String2.Length], r13
0x140077689  mov     rcx, r15; int
0x14007768c  mov     [rsp+110h+var_F0], r14; char *
0x140077691  call    ?ConvertLayerPathToScratchPath@UfsUnionCtx@UnionFs@@QEBAJAEBVUfsPathName@2@AEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEBV?$shared_ptr@VUfsLayerCtx@UnionFs@@@5@AEAVStackEventTracer@2@PEAV65@@Z; UnionFs::UfsUnionCtx::ConvertLayerPathToScratchPath(UnionFs::UfsPathName const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,utl::shared_ptr<UnionFs::UfsLayerCtx> const &,UnionFs::StackEventTracer &,utl::shared_ptr<UnionFs::UfsLayerCtx> *)
  ... truncated ...
```
