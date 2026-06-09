# UnionFs::Utils::ScratchRelativizeSubstituteName(_UNICODE_STRING const &,UnionFs::UfsUnionCtx const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)

- ea: `0x140076fd8`
- end: `0x14007770a`
- name: `?ScratchRelativizeSubstituteName@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBVUfsUnionCtx@2@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z`
- size: `1842`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, int, PUNICODE_STRING UnicodeString, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140078a98`
- `0x140078dc8`

## callees

- `0x14000f7fc`
- `0x140043bdc`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140060148`
- `0x14006de98`
- `0x140076fd8`
- `0x140079a24`
- `0x140079c48`
- `0x140079d0c`
- `0x140079da0`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140077025`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140077062`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400770b4`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400770ff`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140077025`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140077062`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400770b4`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400770ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077408`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400774eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077522`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400775f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007762a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077689`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400776c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077408`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400774eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077522`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400775f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007762a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077689`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400776c0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140077664`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140077664`
- `FLTMGR!FltGetVolumeName` at `0x1400772a5`
- `FLTMGR!FltGetVolumeName` at `0x14007731a`
- `FLTMGR!FltGetVolumeName` at `0x1400772a5`
- `FLTMGR!FltGetVolumeName` at `0x14007731a`
- `FLTMGR!FltGetVolumeFromName` at `0x14007720f`
- `FLTMGR!FltGetVolumeFromName` at `0x14007720f`
- `FLTMGR!FltObjectDereference` at `0x140077233`
- `FLTMGR!FltObjectDereference` at `0x14007727b`
- `FLTMGR!FltObjectDereference` at `0x140077427`
- `FLTMGR!FltObjectDereference` at `0x140077541`
- `FLTMGR!FltObjectDereference` at `0x140077649`
- `FLTMGR!FltObjectDereference` at `0x1400776df`
- `FLTMGR!FltObjectDereference` at `0x140077233`
- `FLTMGR!FltObjectDereference` at `0x14007727b`
- `FLTMGR!FltObjectDereference` at `0x140077427`
- `FLTMGR!FltObjectDereference` at `0x140077541`
- `FLTMGR!FltObjectDereference` at `0x140077649`
- `FLTMGR!FltObjectDereference` at `0x1400776df`

## string_xrefs

- `0x1400774a1`: `PUSH: Converting layer path to scratch path`
- `0x1400772e5`: `ORIGIN: Allocating temp string for volume name`
- `0x140077122`: `UnionFs::Utils::GetVolumeLengthFromPath`
- `0x1400773bf`: `PUSH: Creating UfsPathName`

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
  else if ( RtlPrefixUnicodeString(&stru_14007EE40, String2, 1u)
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
    v13 = RtlPrefixUnicodeString(&stru_14007EE50, String2, 1u);
    p_Buffer = &String2->Buffer;
    String2a = *String2;
    if ( v13 )
    {
      String2a.Buffer = *p_Buffer + 14;
      String2a.Length = String2->Length - 28;
      String2a.MaximumLength = String2a.Length;
    }
    if ( !RtlPrefixUnicodeString(&stru_14007EE60, &String2a, 1u) )
    {
      VolumeFromName = -1073741773;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000033LL,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x6B900210B5BLL,
        (unsigned __int64)"UnionFs::Utils::GetVolumeLengthFromPath",
        "ORIGIN: Unrecognized SubstituteName format",
        v47);
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)0xC0000033LL,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x6BA00210B83LL,
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
      (struct UnionFs::StackEventTracer *)0x6BB00210B9ALL,
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
      (struct UnionFs::StackEventTracer *)0x40E002123D3LL,
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
      (struct UnionFs::StackEventTracer *)0x6BC00210BA0LL,
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
      (struct UnionFs::StackEventTracer *)0x6BE00210BABLL,
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
      (struct UnionFs::StackEventTracer *)0x6BF00210BB3LL,
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
        (struct UnionFs::StackEventTracer *)0x6C100210BC2LL,
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
0x140076fd8  mov     rax, rsp
0x140076fdb  push    rbp
0x140076fdc  push    rbx
0x140076fdd  push    rsi
0x140076fde  push    rdi
0x140076fdf  push    r12
0x140076fe1  push    r13
0x140076fe3  push    r14
0x140076fe5  push    r15
0x140076fe7  lea     rbp, [rax-5Fh]
0x140076feb  sub     rsp, 0D8h
0x140076ff2  mov     rdi, rcx
0x140076ff5  movaps  xmmword ptr [rax-58h], xmm6
0x140076ff9  mov     rcx, r8; UnicodeString
0x140076ffc  mov     r14, r9
0x140076fff  mov     r12, r8
0x140077002  mov     r15, rdx
0x140077005  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14007700a  xorps   xmm0, xmm0
0x14007700d  lea     rcx, String1; String1
0x140077014  movups  xmmword ptr [r12], xmm0
0x140077019  movzx   esi, word ptr [rdi]
0x14007701c  mov     r8b, 1; CaseInSensitive
0x14007701f  mov     rdx, rdi; String2
0x140077022  shr     rsi, 1
0x140077025  call    cs:__imp_RtlPrefixUnicodeString
0x14007702c  nop     dword ptr [rax+rax+00h]
0x140077031  xor     r13d, r13d
0x140077034  test    al, al
0x140077036  jz      short loc_140077055
0x140077038  cmp     rsi, 31h ; '1'
0x14007703c  jb      short loc_140077055
0x14007703e  lea     rbx, [rdi+8]
0x140077042  mov     rax, [rbx]
0x140077045  cmp     word ptr [rax+5Eh], 7Dh ; '}'
0x14007704a  jnz     short loc_140077055
0x14007704c  lea     ecx, [r13+60h]
0x140077050  jmp     loc_1400771B0
0x140077055  mov     r8b, 1; CaseInSensitive
0x140077058  lea     rcx, stru_14007EE40; String1
0x14007705f  mov     rdx, rdi; String2
0x140077062  call    cs:__imp_RtlPrefixUnicodeString
0x140077069  nop     dword ptr [rax+rax+00h]
0x14007706e  test    al, al
0x140077070  jz      short loc_1400770A7
0x140077072  cmp     rsi, 6
0x140077076  jb      short loc_1400770A7
0x140077078  lea     rbx, [rdi+8]
0x14007707c  mov     rdx, [rbx]
0x14007707f  movzx   ecx, word ptr [rdx+8]
0x140077083  lea     eax, [rcx-61h]
0x140077086  cmp     ax, 19h
0x14007708a  jbe     short loc_140077096
0x14007708c  sub     cx, 41h ; 'A'
0x140077090  cmp     cx, 19h
0x140077094  ja      short loc_1400770A7
0x140077096  cmp     word ptr [rdx+0Ah], 3Ah ; ':'
0x14007709b  jnz     short loc_1400770A7
0x14007709d  mov     ecx, 0Ch
0x1400770a2  jmp     loc_1400771B0
0x1400770a7  mov     r8b, 1; CaseInSensitive
0x1400770aa  lea     rcx, stru_14007EE50; String1
0x1400770b1  mov     rdx, rdi; String2
0x1400770b4  call    cs:__imp_RtlPrefixUnicodeString
0x1400770bb  nop     dword ptr [rax+rax+00h]
0x1400770c0  movups  xmm0, xmmword ptr [rdi]
0x1400770c3  mov     sil, al
0x1400770c6  lea     rbx, [rdi+8]
0x1400770ca  mov     eax, 1Ch
0x1400770cf  movdqu  xmmword ptr [rbp+57h+String2.Length], xmm0
0x1400770d4  test    sil, sil
0x1400770d7  jz      short loc_1400770F1
0x1400770d9  mov     rcx, [rbx]
0x1400770dc  add     rcx, rax
0x1400770df  mov     [rbp+57h+String2.Buffer], rcx
0x1400770e3  movzx   ecx, word ptr [rdi]
0x1400770e6  sub     cx, ax
0x1400770e9  mov     [rbp+57h+String2.Length], cx
0x1400770ed  mov     [rbp+57h+String2.MaximumLength], cx
0x1400770f1  mov     r8b, 1; CaseInSensitive
0x1400770f4  lea     rdx, [rbp+57h+String2]; String2
0x1400770f8  lea     rcx, stru_14007EE60; String1
0x1400770ff  call    cs:__imp_RtlPrefixUnicodeString
0x140077106  nop     dword ptr [rax+rax+00h]
0x14007710b  test    al, al
0x14007710d  jnz     short loc_140077169
0x14007710f  lea     rax, aOriginUnrecogn_0; "ORIGIN: Unrecognized SubstituteName for"...
0x140077116  mov     ebx, 0C0000033h
0x14007711b  mov     ecx, ebx; this
0x14007711d  mov     [rsp+110h+var_F0], rax; char *
0x140077122  lea     r9, aUnionfsUtilsGe_1; "UnionFs::Utils::GetVolumeLengthFromPath"
0x140077129  mov     r8, 6B900210B5Bh; struct UnionFs::StackEventTracer *
0x140077133  mov     rdx, r14; int
0x140077136  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007713b  lea     rcx, aPushGettingVol_0; "PUSH: Getting volume length"
0x140077142  mov     r8, 6BA00210B83h; struct UnionFs::StackEventTracer *
0x14007714c  mov     [rsp+110h+var_F0], rcx; char *
0x140077151  lea     r9, aUnionfsUtilsSc; "UnionFs::Utils::ScratchRelativizeSubsti"...
0x140077158  mov     ecx, ebx; this
0x14007715a  mov     rdx, r14; int
0x14007715d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140077162  mov     eax, ebx
0x140077164  jmp     loc_1400776ED
0x140077169  movzx   edx, [rbp+57h+String2.Length]; unsigned __int16 *
0x14007716d  lea     r9, [rbp+57h+BufferSizeNeeded]; unsigned __int16
0x140077171  mov     rcx, [rbp+57h+String2.Buffer]; this
0x140077175  mov     eax, 10h
0x14007717a  mov     [rbp+57h+var_C0], ax
0x14007717e  lea     rax, [rbp+57h+var_C0]
0x140077182  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x140077187  mov     word ptr [rbp+57h+BufferSizeNeeded], r13w
0x14007718c  call    ?FindCharForward@Utils@UnionFs@@YA_NPEBGGGPEAG1@Z; UnionFs::Utils::FindCharForward(ushort const *,ushort,ushort,ushort *,ushort *)
0x140077191  test    al, al
0x140077193  jz      short loc_1400771AD
0x140077195  neg     sil
0x140077198  mov     ecx, 1Ch
0x14007719d  sbb     ax, ax
0x1400771a0  and     cx, ax
0x1400771a3  sub     cx, 2
0x1400771a7  add     cx, word ptr [rbp+57h+BufferSizeNeeded]
0x1400771ab  jmp     short loc_1400771B0
0x1400771ad  movzx   ecx, word ptr [rdi]
0x1400771b0  movzx   edx, word ptr [rdi]
0x1400771b3  xorps   xmm0, xmm0
0x1400771b6  mov     r8, [rbx]
0x1400771b9  mov     dword ptr [rbp+57h+VolumeName+4], r13d
0x1400771bd  mov     [rbp+57h+VolumeName.Buffer], r8
0x1400771c1  mov     [rbp+57h+VolumeName.Length], cx
0x1400771c5  mov     [rbp+57h+VolumeName.MaximumLength], cx
0x1400771c9  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x1400771cd  cmp     cx, dx
0x1400771d0  jnb     short loc_1400771E7
0x1400771d2  movzx   eax, cx
0x1400771d5  add     rax, r8
0x1400771d8  sub     dx, cx
0x1400771db  mov     [rbp+57h+var_78.Buffer], rax
0x1400771df  mov     [rbp+57h+var_78.Length], dx
0x1400771e3  mov     [rbp+57h+var_78.MaximumLength], dx
0x1400771e7  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400771ee  lea     rax, [rsp+110h+var_E0]
0x1400771f3  mov     [rsp+110h+var_E0], r13
0x1400771f8  lea     r8, [rbp+57h+var_A0.Buffer]; RetVolume
0x1400771fc  lea     rdx, [rbp+57h+VolumeName]; VolumeName
0x140077200  mov     qword ptr [rbp+57h+var_A0.Length], rax
0x140077204  mov     [rbp+57h+var_A0.Buffer], r13
0x140077208  mov     rcx, [rcx]; Filter
0x14007720b  mov     [rbp+57h+var_90], 1
0x14007720f  call    cs:__imp_FltGetVolumeFromName
0x140077216  nop     dword ptr [rax+rax+00h]
0x14007721b  mov     ebx, eax
0x14007721d  cmp     [rbp+57h+var_90], r13b
0x140077221  jz      short loc_140077242
0x140077223  mov     rdi, qword ptr [rbp+57h+var_A0.Length]
0x140077227  mov     rsi, [rbp+57h+var_A0.Buffer]
0x14007722b  mov     rcx, [rdi]; FltObject
0x14007722e  test    rcx, rcx
0x140077231  jz      short loc_14007723F
0x140077233  call    cs:__imp_FltObjectDereference
0x14007723a  nop     dword ptr [rax+rax+00h]
0x14007723f  mov     [rdi], rsi
0x140077242  test    ebx, ebx
0x140077244  jns     short loc_14007728C
0x140077246  lea     rax, aApiFltgetvolum_1; "API: FltGetVolumeFromName"
0x14007724d  mov     r8, 6BB00210B9Ah; struct UnionFs::StackEventTracer *
0x140077257  lea     r9, aUnionfsUtilsSc; "UnionFs::Utils::ScratchRelativizeSubsti"...
0x14007725e  mov     [rsp+110h+var_F0], rax; char *
0x140077263  mov     rdx, r14; int
0x140077266  mov     ecx, ebx; this
0x140077268  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007726d  mov     rcx, [rsp+110h+var_E0]; FltObject
0x140077272  test    rcx, rcx
0x140077275  jz      loc_140077162
0x14007727b  call    cs:__imp_FltObjectDereference
0x140077282  nop     dword ptr [rax+rax+00h]
0x140077287  jmp     loc_140077162
0x14007728c  mov     rbx, [rsp+110h+var_E0]
0x140077291  lea     r8, [rbp+57h+BufferSizeNeeded]; BufferSizeNeeded
0x140077295  xorps   xmm0, xmm0
0x140077298  mov     dword ptr [rbp+57h+BufferSizeNeeded], r13d
0x14007729c  mov     rcx, rbx; Volume
0x14007729f  xor     edx, edx; VolumeName
0x1400772a1  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x1400772a5  call    cs:__imp_FltGetVolumeName
0x1400772ac  nop     dword ptr [rax+rax+00h]
0x1400772b1  mov     edx, dword ptr [rbp+57h+BufferSizeNeeded]
0x1400772b4  cmp     edx, 0FFFFh
0x1400772ba  jbe     short loc_1400772CB
0x1400772bc  lea     rcx, aVolumenamesize; "volumeNameSize <= MAXUSHORT"
0x1400772c3  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400772c8  mov     edx, dword ptr [rbp+57h+BufferSizeNeeded]
0x1400772cb  mov     r8d, 4C467346h
0x1400772d1  lea     rcx, [rbp+57h+String2]
0x1400772d5  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x1400772da  mov     edi, 0C000009Ah
0x1400772df  cmp     [rbp+57h+String2.Buffer], r13
0x1400772e3  jnz     short loc_140077310
0x1400772e5  lea     rax, aOriginAllocati_66; "ORIGIN: Allocating temp string for volu"...
0x1400772ec  mov     r8, 40E002123D3h; struct UnionFs::StackEventTracer *
0x1400772f6  lea     r9, aUnionfsUtilsGe; "UnionFs::Utils::GetVolumeName"
0x1400772fd  mov     [rsp+110h+var_F0], rax; char *
0x140077302  mov     rdx, r14; int
0x140077305  mov     ecx, edi; this
0x140077307  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007730c  mov     ebx, edi
0x14007730e  jmp     short loc_140077358
0x140077310  xor     r8d, r8d; BufferSizeNeeded
0x140077313  lea     rdx, [rbp+57h+String2]; VolumeName
0x140077317  mov     rcx, rbx; Volume
0x14007731a  call    cs:__imp_FltGetVolumeName
0x140077321  nop     dword ptr [rax+rax+00h]
0x140077326  movzx   eax, [rbp+57h+UnicodeString.Length]
0x14007732a  mov     ebx, r13d
0x14007732d  movaps  xmm0, xmmword ptr [rbp+57h+String2.Length]
0x140077331  mov     rcx, [rbp+57h+UnicodeString.Buffer]
0x140077335  mov     [rbp+57h+var_A0.Length], ax
0x140077339  mov     eax, dword ptr [rbp+57h+UnicodeString.MaximumLength]
0x14007733c  mov     dword ptr [rbp+57h+var_A0.MaximumLength], eax
0x14007733f  movzx   eax, word ptr [rbp+57h+UnicodeString+6]
0x140077343  mov     word ptr [rbp+57h+var_A0+6], ax
0x140077347  mov     rax, qword ptr [rbp+57h+var_A0.Length]
0x14007734b  mov     qword ptr [rbp+57h+String2.Length], rax
0x14007734f  movdqa  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x140077354  mov     [rbp+57h+String2.Buffer], rcx
0x140077358  lea     rcx, [rbp+57h+String2]; UnicodeString
0x14007735c  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140077361  test    ebx, ebx
0x140077363  jns     short loc_14007739A
0x140077365  lea     rax, aPushGetvolumen; "PUSH: GetVolumeName"
0x14007736c  mov     r8, 6BC00210BA0h; struct UnionFs::StackEventTracer *
0x140077376  lea     r9, aUnionfsUtilsSc; "UnionFs::Utils::ScratchRelativizeSubsti"...
0x14007737d  mov     [rsp+110h+var_F0], rax; char *
0x140077382  mov     rdx, r14; int
0x140077385  mov     ecx, ebx; this
0x140077387  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007738c  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x140077390  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140077395  jmp     loc_14007726D
0x14007739a  movzx   r8d, [rbp+57h+UnicodeString.Length]
0x14007739f  lea     r9, [rbp+57h+BufferSizeNeeded]
0x1400773a3  lea     rdx, [rbp+57h+var_78]; struct _UNICODE_STRING *
0x1400773a7  mov     [rbp+57h+BufferSizeNeeded], r13
0x1400773ab  lea     rcx, [rbp+57h+UnicodeString]; struct _UNICODE_STRING *
0x1400773af  mov     [rsp+110h+var_F0], r14; struct UnionFs::StackEventTracer *
0x1400773b4  call    ?AllocAndInitWithCombinedPaths@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@0GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInitWithCombinedPaths(_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x1400773b9  mov     edi, eax
0x1400773bb  test    eax, eax
0x1400773bd  jns     short loc_14007743A
0x1400773bf  lea     rax, aPushCreatingUf; "PUSH: Creating UfsPathName"
0x1400773c6  mov     r8, 6BE00210BABh; struct UnionFs::StackEventTracer *
0x1400773d0  lea     r9, aUnionfsUtilsSc; "UnionFs::Utils::ScratchRelativizeSubsti"...
0x1400773d7  mov     [rsp+110h+var_F0], rax; char *
0x1400773dc  mov     rdx, r14; int
0x1400773df  mov     ecx, edi; this
0x1400773e1  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400773e6  mov     rbx, [rbp+57h+BufferSizeNeeded]
0x1400773ea  test    rbx, rbx
0x1400773ed  jz      short loc_140077414
0x1400773ef  cmp     [rbx+10h], r13b
0x1400773f3  jnz     short loc_1400773FB
0x1400773f5  xorps   xmm0, xmm0
0x1400773f8  movups  xmmword ptr [rbx], xmm0
0x1400773fb  mov     rcx, rbx; UnicodeString
0x1400773fe  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140077403  xor     edx, edx; Tag
0x140077405  mov     rcx, rbx; P
0x140077408  call    cs:__imp_ExFreePoolWithTag
0x14007740f  nop     dword ptr [rax+rax+00h]
0x140077414  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x140077418  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14007741d  mov     rcx, [rsp+110h+var_E0]; FltObject
0x140077422  test    rcx, rcx
0x140077425  jz      short loc_140077433
0x140077427  call    cs:__imp_FltObjectDereference
0x14007742e  nop     dword ptr [rax+rax+00h]
0x140077433  mov     eax, edi
0x140077435  jmp     loc_1400776ED
0x14007743a  lea     rdx, [r15+48h]
0x14007743e  lea     rcx, [rbp+57h+String2]
0x140077442  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140077447  mov     rcx, [r15+30h]
0x14007744b  mov     rdi, [rcx+8]
0x14007744f  mov     rax, [rcx]
0x140077452  mov     qword ptr [rbp+57h+var_A0.Length], rax
0x140077456  mov     [rbp+57h+var_A0.Buffer], rdi
0x14007745a  test    rdi, rdi
0x14007745d  jz      short loc_140077463
0x14007745f  lock inc dword ptr [rdi+8]
0x140077463  mov     rcx, qword ptr [rbp+57h+String2.Length]; this
0x140077467  test    rcx, rcx
0x14007746a  jz      short loc_140077471
0x14007746c  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140077471  mov     rbx, [rbp+57h+BufferSizeNeeded]
0x140077475  lea     r9, [rbp+57h+var_A0]; int
0x140077479  mov     rdx, rbx; int
0x14007747c  mov     [rsp+110h+var_E8], r13; char *
0x140077481  lea     r8, [rbp+57h+String2]; int
0x140077485  mov     qword ptr [rbp+57h+String2.Length], r13
0x140077489  mov     rcx, r15; int
0x14007748c  mov     [rsp+110h+var_F0], r14; char *
0x140077491  call    ?ConvertLayerPathToScratchPath@UfsUnionCtx@UnionFs@@QEBAJAEBVUfsPathName@2@AEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEBV?$shared_ptr@VUfsLayerCtx@UnionFs@@@5@AEAVStackEventTracer@2@PEAV65@@Z; UnionFs::UfsUnionCtx::ConvertLayerPathToScratchPath(UnionFs::UfsPathName const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,utl::shared_ptr<UnionFs::UfsLayerCtx> const &,UnionFs::StackEventTracer &,utl::shared_ptr<UnionFs::UfsLayerCtx> *)
  ... truncated ...
```
