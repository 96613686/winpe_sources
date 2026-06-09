# UnionFs::UfsEnumContext::AddDirEnumFileIdMapping(_FLT_FILE_NAME_INFORMATION const &,_UNICODE_STRING const &,UnionFs::UfsFileID,UnionFs::StackEventTracer &)

- ea: `0x14001ac78`
- end: `0x14001ae88`
- name: `?AddDirEnumFileIdMapping@UfsEnumContext@UnionFs@@AEAAJAEBU_FLT_FILE_NAME_INFORMATION@@AEBU_UNICODE_STRING@@VUfsFileID@2@AEAVStackEventTracer@2@@Z`
- size: `528`
- prototype: `int __high(const struct _FLT_FILE_NAME_INFORMATION *, const struct _UNICODE_STRING *, struct UnionFs::UfsFileID, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001c51c`

## callees

- `0x14001ac78`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x14005ddac`
- `0x140075b30`
- `0x140079c48`
- `0x140079d0c`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001ad8b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001ad8b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001acc5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001ace0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001acfc`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001acc5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001ace0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001acfc`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001add1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001add1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001ad66`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001ad66`

## string_xrefs

- `0x14001ad30`: `ORIGIN: Allocating fullPath`
- `0x14001ad9d`: `API: Appending path separator`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsEnumContext::AddDirEnumFileIdMapping(
        __int64 a1,
        __int64 a2,
        const UNICODE_STRING *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v5; // r10
  USHORT v7; // ax
  WCHAR *v9; // r10
  BOOLEAN v11; // bl
  BOOLEAN v12; // r14
  BOOLEAN v13; // di
  NTSTATUS appended; // ebx
  struct _UNICODE_STRING *v15; // rdx
  struct _UNICODE_STRING *v16; // r9
  const char *v17; // rax
  __int64 v18; // r8
  const char *v20; // [rsp+28h] [rbp-28h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-10h] BYREF

  v5 = *(unsigned __int16 *)(a2 + 24);
  v7 = *(_WORD *)(a2 + 8) - v5;
  v9 = (WCHAR *)(*(_QWORD *)(a2 + 16) + v5);
  *(_DWORD *)(&String1.MaximumLength + 1) = 0;
  String1.Buffer = v9;
  String1.Length = v7;
  String1.MaximumLength = v7;
  v11 = RtlEqualUnicodeString(&String1, &UnionFs::g_RootName, 1u);
  v12 = RtlEqualUnicodeString(a3, &UnionFs::g_CurrentDirectoryDotName, 1u);
  v13 = RtlEqualUnicodeString(a3, &UnionFs::g_ParentDirectoryDotName, 1u);
  FsFltWil::MakeUniqueUnicodeString(&DestinationString, (unsigned __int16)(a3->Length + String1.Length + 2), 1852130901);
  if ( !DestinationString.Buffer )
  {
    appended = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a5,
      (struct UnionFs::StackEventTracer *)0x616000401FELL,
      (unsigned __int64)"UnionFs::UfsEnumContext::AddDirEnumFileIdMapping",
      "ORIGIN: Allocating fullPath",
      v20);
    goto LABEL_18;
  }
  RtlCopyUnicodeString(&DestinationString, &String1);
  if ( v12 )
  {
    if ( !v13 )
      goto LABEL_15;
LABEL_12:
    if ( !v11 )
    {
      UnionFs::Utils::RemoveFinalComponent((UnionFs::Utils *)&DestinationString, 0, 0, v16);
      if ( DestinationString.Length > 2u )
        DestinationString.Length -= 2;
    }
    goto LABEL_15;
  }
  if ( v13 )
    goto LABEL_12;
  if ( !v11 )
  {
    appended = RtlAppendUnicodeToString(&DestinationString, L"\\");
    if ( appended < 0 )
    {
      v17 = "API: Appending path separator";
      v18 = 0x4FC00040210LL;
LABEL_8:
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)appended,
        a5,
        (struct UnionFs::StackEventTracer *)v18,
        (unsigned __int64)"UnionFs::UfsEnumContext::AddDirEnumFileIdMapping",
        v17,
        v20);
      goto LABEL_18;
    }
  }
  appended = RtlAppendUnicodeStringToString(&DestinationString, a3);
  if ( appended < 0 )
  {
    v17 = "API: Appending ChildFileName";
    v18 = 0x4FD00040216LL;
    goto LABEL_8;
  }
LABEL_15:
  appended = UnionFs::UfsUnionCtx::AddFileIDMapping(*(_QWORD *)(a1 + 24), a4, &DestinationString, a5);
  if ( appended >= 0 )
    appended = 0;
  else
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)appended,
      a5,
      (struct UnionFs::StackEventTracer *)0x61D0004022CLL,
      (unsigned __int64)"UnionFs::UfsEnumContext::AddDirEnumFileIdMapping",
      "PUSH: Adding file ID mapping",
      v20);
LABEL_18:
  FsFltWil::Details::FreeUnicodeString(&DestinationString, v15);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14001ac78  push    rbp
0x14001ac7a  push    rbx
0x14001ac7b  push    rsi
0x14001ac7c  push    rdi
0x14001ac7d  push    r13
0x14001ac7f  push    r14
0x14001ac81  push    r15
0x14001ac83  mov     rbp, rsp
0x14001ac86  sub     rsp, 50h
0x14001ac8a  movzx   r10d, word ptr [rdx+18h]
0x14001ac8f  xorps   xmm0, xmm0
0x14001ac92  movzx   eax, word ptr [rdx+8]
0x14001ac96  mov     rsi, r8
0x14001ac99  sub     ax, r10w
0x14001ac9d  mov     r13, rcx
0x14001aca0  add     r10, [rdx+10h]
0x14001aca4  lea     rcx, [rbp+String1]; String1
0x14001aca8  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14001acac  lea     rdx, ?g_RootName@UnionFs@@3U_UNICODE_STRING@@B; String2
0x14001acb3  mov     [rbp+String1.Buffer], r10
0x14001acb7  mov     r8b, 1; CaseInSensitive
0x14001acba  mov     [rbp+String1.Length], ax
0x14001acbe  mov     r15, r9
0x14001acc1  mov     [rbp+String1.MaximumLength], ax
0x14001acc5  call    cs:__imp_RtlEqualUnicodeString
0x14001accc  nop     dword ptr [rax+rax+00h]
0x14001acd1  mov     r8b, 1; CaseInSensitive
0x14001acd4  lea     rdx, ?g_CurrentDirectoryDotName@UnionFs@@3U_UNICODE_STRING@@B; String2
0x14001acdb  mov     rcx, rsi; String1
0x14001acde  mov     bl, al
0x14001ace0  call    cs:__imp_RtlEqualUnicodeString
0x14001ace7  nop     dword ptr [rax+rax+00h]
0x14001acec  mov     r8b, 1; CaseInSensitive
0x14001acef  lea     rdx, ?g_ParentDirectoryDotName@UnionFs@@3U_UNICODE_STRING@@B; String2
0x14001acf6  mov     rcx, rsi; String1
0x14001acf9  mov     r14b, al
0x14001acfc  call    cs:__imp_RtlEqualUnicodeString
0x14001ad03  nop     dword ptr [rax+rax+00h]
0x14001ad08  movzx   edx, [rbp+String1.Length]
0x14001ad0c  lea     rcx, [rbp+DestinationString]
0x14001ad10  add     dx, 2
0x14001ad14  mov     r8d, 6E654655h
0x14001ad1a  add     dx, [rsi]
0x14001ad1d  mov     dil, al
0x14001ad20  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14001ad25  cmp     [rbp+DestinationString.Buffer], 0
0x14001ad2a  jnz     short loc_14001AD5E
0x14001ad2c  mov     rdx, qword ptr [rbp+arg_20]; int
0x14001ad30  lea     rax, aOriginAllocati_51; "ORIGIN: Allocating fullPath"
0x14001ad37  mov     ebx, 0C000009Ah
0x14001ad3c  mov     [rsp+50h+var_30], rax; char *
0x14001ad41  mov     ecx, ebx; this
0x14001ad43  lea     r9, aUnionfsUfsenum_4; "UnionFs::UfsEnumContext::AddDirEnumFile"...
0x14001ad4a  mov     r8, 616000401FEh; struct UnionFs::StackEventTracer *
0x14001ad54  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001ad59  jmp     loc_14001AE6D
0x14001ad5e  lea     rdx, [rbp+String1]; SourceString
0x14001ad62  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001ad66  call    cs:__imp_RtlCopyUnicodeString
0x14001ad6d  nop     dword ptr [rax+rax+00h]
0x14001ad72  test    r14b, r14b
0x14001ad75  jnz     short loc_14001ADF6
0x14001ad77  test    dil, dil
0x14001ad7a  jnz     short loc_14001ADFB
0x14001ad7c  test    bl, bl
0x14001ad7e  jnz     short loc_14001ADCA
0x14001ad80  lea     rdx, Source; "\\"
0x14001ad87  lea     rcx, [rbp+DestinationString]; Destination
0x14001ad8b  call    cs:__imp_RtlAppendUnicodeToString
0x14001ad92  nop     dword ptr [rax+rax+00h]
0x14001ad97  mov     ebx, eax
0x14001ad99  test    eax, eax
0x14001ad9b  jns     short loc_14001ADCA
0x14001ad9d  lea     rax, aApiAppendingPa_0; "API: Appending path separator"
0x14001ada4  mov     r8, 4FC00040210h; struct UnionFs::StackEventTracer *
0x14001adae  mov     rdx, qword ptr [rbp+arg_20]; int
0x14001adb2  lea     r9, aUnionfsUfsenum_4; "UnionFs::UfsEnumContext::AddDirEnumFile"...
0x14001adb9  mov     ecx, ebx; this
0x14001adbb  mov     [rsp+50h+var_30], rax; char *
0x14001adc0  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001adc5  jmp     loc_14001AE6D
0x14001adca  mov     rdx, rsi; Source
0x14001adcd  lea     rcx, [rbp+DestinationString]; Destination
0x14001add1  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001add8  nop     dword ptr [rax+rax+00h]
0x14001addd  mov     ebx, eax
0x14001addf  test    eax, eax
0x14001ade1  jns     short loc_14001AE27
0x14001ade3  lea     rax, aApiAppendingCh; "API: Appending ChildFileName"
0x14001adea  mov     r8, 4FD00040216h
0x14001adf4  jmp     short loc_14001ADAE
0x14001adf6  test    dil, dil
0x14001adf9  jz      short loc_14001AE27
0x14001adfb  test    bl, bl
0x14001adfd  jnz     short loc_14001AE27
0x14001adff  xor     edx, edx; struct _UNICODE_STRING *
0x14001ae01  lea     rcx, [rbp+DestinationString]; this
0x14001ae05  xor     r8d, r8d; unsigned __int16
0x14001ae08  call    ?RemoveFinalComponent@Utils@UnionFs@@YAGAEAU_UNICODE_STRING@@GPEAU3@@Z; UnionFs::Utils::RemoveFinalComponent(_UNICODE_STRING &,ushort,_UNICODE_STRING *)
0x14001ae0d  movzx   r8d, [rbp+DestinationString.Length]
0x14001ae12  cmp     r8w, 2
0x14001ae17  jbe     short loc_14001AE27
0x14001ae19  mov     eax, 0FFFEh
0x14001ae1e  add     r8w, ax
0x14001ae22  mov     [rbp+DestinationString.Length], r8w
0x14001ae27  mov     r9, qword ptr [rbp+arg_20]
0x14001ae2b  lea     r8, [rbp+DestinationString]
0x14001ae2f  mov     rcx, [r13+18h]
0x14001ae33  mov     rdx, r15
0x14001ae36  call    ?AddFileIDMapping@UfsUnionCtx@UnionFs@@QEAAJAEBVUfsFileID@2@$$QEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::AddFileIDMapping(UnionFs::UfsFileID const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &&,UnionFs::StackEventTracer &)
0x14001ae3b  mov     ebx, eax
0x14001ae3d  test    eax, eax
0x14001ae3f  jns     short loc_14001AE6B
0x14001ae41  mov     rdx, qword ptr [rbp+arg_20]; int
0x14001ae45  lea     rax, aPushAddingFile; "PUSH: Adding file ID mapping"
0x14001ae4c  lea     r9, aUnionfsUfsenum_4; "UnionFs::UfsEnumContext::AddDirEnumFile"...
0x14001ae53  mov     [rsp+50h+var_30], rax; char *
0x14001ae58  mov     r8, 61D0004022Ch; struct UnionFs::StackEventTracer *
0x14001ae62  mov     ecx, ebx; this
0x14001ae64  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001ae69  jmp     short loc_14001AE6D
0x14001ae6b  xor     ebx, ebx
0x14001ae6d  lea     rcx, [rbp+DestinationString]; UnicodeString
0x14001ae71  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14001ae76  mov     eax, ebx
0x14001ae78  add     rsp, 50h
0x14001ae7c  pop     r15
0x14001ae7e  pop     r14
0x14001ae80  pop     r13
0x14001ae82  pop     rdi
0x14001ae83  pop     rsi
0x14001ae84  pop     rbx
0x14001ae85  pop     rbp
0x14001ae86  retn
```
