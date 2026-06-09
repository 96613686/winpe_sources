# UnionFs::UfsEnumContext::AddDirEnumFileIdMapping(_FLT_FILE_NAME_INFORMATION const &,_UNICODE_STRING const &,UnionFs::UfsFileID,UnionFs::StackEventTracer &)

- ea: `0x14001ad18`
- end: `0x14001af28`
- name: `?AddDirEnumFileIdMapping@UfsEnumContext@UnionFs@@AEAAJAEBU_FLT_FILE_NAME_INFORMATION@@AEBU_UNICODE_STRING@@VUfsFileID@2@AEAVStackEventTracer@2@@Z`
- size: `528`
- prototype: `int __high(const struct _FLT_FILE_NAME_INFORMATION *, const struct _UNICODE_STRING *, struct UnionFs::UfsFileID, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001c5bc`

## callees

- `0x14001ad18`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x14005df2c`
- `0x140075d30`
- `0x140079f68`
- `0x14007a02c`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001ae2b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001ae2b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001ad65`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001ad80`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001ad9c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001ad65`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001ad80`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001ad9c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001ae71`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001ae71`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001ae06`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001ae06`

## string_xrefs

- `0x14001add0`: `ORIGIN: Allocating fullPath`
- `0x14001ae3d`: `API: Appending path separator`

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
0x14001ad18  push    rbp
0x14001ad1a  push    rbx
0x14001ad1b  push    rsi
0x14001ad1c  push    rdi
0x14001ad1d  push    r13
0x14001ad1f  push    r14
0x14001ad21  push    r15
0x14001ad23  mov     rbp, rsp
0x14001ad26  sub     rsp, 50h
0x14001ad2a  movzx   r10d, word ptr [rdx+18h]
0x14001ad2f  xorps   xmm0, xmm0
0x14001ad32  movzx   eax, word ptr [rdx+8]
0x14001ad36  mov     rsi, r8
0x14001ad39  sub     ax, r10w
0x14001ad3d  mov     r13, rcx
0x14001ad40  add     r10, [rdx+10h]
0x14001ad44  lea     rcx, [rbp+String1]; String1
0x14001ad48  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14001ad4c  lea     rdx, ?g_RootName@UnionFs@@3U_UNICODE_STRING@@B; String2
0x14001ad53  mov     [rbp+String1.Buffer], r10
0x14001ad57  mov     r8b, 1; CaseInSensitive
0x14001ad5a  mov     [rbp+String1.Length], ax
0x14001ad5e  mov     r15, r9
0x14001ad61  mov     [rbp+String1.MaximumLength], ax
0x14001ad65  call    cs:__imp_RtlEqualUnicodeString
0x14001ad6c  nop     dword ptr [rax+rax+00h]
0x14001ad71  mov     r8b, 1; CaseInSensitive
0x14001ad74  lea     rdx, ?g_CurrentDirectoryDotName@UnionFs@@3U_UNICODE_STRING@@B; String2
0x14001ad7b  mov     rcx, rsi; String1
0x14001ad7e  mov     bl, al
0x14001ad80  call    cs:__imp_RtlEqualUnicodeString
0x14001ad87  nop     dword ptr [rax+rax+00h]
0x14001ad8c  mov     r8b, 1; CaseInSensitive
0x14001ad8f  lea     rdx, ?g_ParentDirectoryDotName@UnionFs@@3U_UNICODE_STRING@@B; String2
0x14001ad96  mov     rcx, rsi; String1
0x14001ad99  mov     r14b, al
0x14001ad9c  call    cs:__imp_RtlEqualUnicodeString
0x14001ada3  nop     dword ptr [rax+rax+00h]
0x14001ada8  movzx   edx, [rbp+String1.Length]
0x14001adac  lea     rcx, [rbp+DestinationString]
0x14001adb0  add     dx, 2
0x14001adb4  mov     r8d, 6E654655h
0x14001adba  add     dx, [rsi]
0x14001adbd  mov     dil, al
0x14001adc0  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14001adc5  cmp     [rbp+DestinationString.Buffer], 0
0x14001adca  jnz     short loc_14001ADFE
0x14001adcc  mov     rdx, qword ptr [rbp+arg_20]; int
0x14001add0  lea     rax, aOriginAllocati_52; "ORIGIN: Allocating fullPath"
0x14001add7  mov     ebx, 0C000009Ah
0x14001addc  mov     [rsp+50h+var_30], rax; char *
0x14001ade1  mov     ecx, ebx; this
0x14001ade3  lea     r9, aUnionfsUfsenum_4; "UnionFs::UfsEnumContext::AddDirEnumFile"...
0x14001adea  mov     r8, 616000401FEh; struct UnionFs::StackEventTracer *
0x14001adf4  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001adf9  jmp     loc_14001AF0D
0x14001adfe  lea     rdx, [rbp+String1]; SourceString
0x14001ae02  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001ae06  call    cs:__imp_RtlCopyUnicodeString
0x14001ae0d  nop     dword ptr [rax+rax+00h]
0x14001ae12  test    r14b, r14b
0x14001ae15  jnz     short loc_14001AE96
0x14001ae17  test    dil, dil
0x14001ae1a  jnz     short loc_14001AE9B
0x14001ae1c  test    bl, bl
0x14001ae1e  jnz     short loc_14001AE6A
0x14001ae20  lea     rdx, Source; "\\"
0x14001ae27  lea     rcx, [rbp+DestinationString]; Destination
0x14001ae2b  call    cs:__imp_RtlAppendUnicodeToString
0x14001ae32  nop     dword ptr [rax+rax+00h]
0x14001ae37  mov     ebx, eax
0x14001ae39  test    eax, eax
0x14001ae3b  jns     short loc_14001AE6A
0x14001ae3d  lea     rax, aApiAppendingPa_0; "API: Appending path separator"
0x14001ae44  mov     r8, 4FC00040210h; struct UnionFs::StackEventTracer *
0x14001ae4e  mov     rdx, qword ptr [rbp+arg_20]; int
0x14001ae52  lea     r9, aUnionfsUfsenum_4; "UnionFs::UfsEnumContext::AddDirEnumFile"...
0x14001ae59  mov     ecx, ebx; this
0x14001ae5b  mov     [rsp+50h+var_30], rax; char *
0x14001ae60  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001ae65  jmp     loc_14001AF0D
0x14001ae6a  mov     rdx, rsi; Source
0x14001ae6d  lea     rcx, [rbp+DestinationString]; Destination
0x14001ae71  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001ae78  nop     dword ptr [rax+rax+00h]
0x14001ae7d  mov     ebx, eax
0x14001ae7f  test    eax, eax
0x14001ae81  jns     short loc_14001AEC7
0x14001ae83  lea     rax, aApiAppendingCh; "API: Appending ChildFileName"
0x14001ae8a  mov     r8, 4FD00040216h
0x14001ae94  jmp     short loc_14001AE4E
0x14001ae96  test    dil, dil
0x14001ae99  jz      short loc_14001AEC7
0x14001ae9b  test    bl, bl
0x14001ae9d  jnz     short loc_14001AEC7
0x14001ae9f  xor     edx, edx; struct _UNICODE_STRING *
0x14001aea1  lea     rcx, [rbp+DestinationString]; this
0x14001aea5  xor     r8d, r8d; unsigned __int16
0x14001aea8  call    ?RemoveFinalComponent@Utils@UnionFs@@YAGAEAU_UNICODE_STRING@@GPEAU3@@Z; UnionFs::Utils::RemoveFinalComponent(_UNICODE_STRING &,ushort,_UNICODE_STRING *)
0x14001aead  movzx   r8d, [rbp+DestinationString.Length]
0x14001aeb2  cmp     r8w, 2
0x14001aeb7  jbe     short loc_14001AEC7
0x14001aeb9  mov     eax, 0FFFEh
0x14001aebe  add     r8w, ax
0x14001aec2  mov     [rbp+DestinationString.Length], r8w
0x14001aec7  mov     r9, qword ptr [rbp+arg_20]
0x14001aecb  lea     r8, [rbp+DestinationString]
0x14001aecf  mov     rcx, [r13+18h]
0x14001aed3  mov     rdx, r15
0x14001aed6  call    ?AddFileIDMapping@UfsUnionCtx@UnionFs@@QEAAJAEBVUfsFileID@2@$$QEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::AddFileIDMapping(UnionFs::UfsFileID const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &&,UnionFs::StackEventTracer &)
0x14001aedb  mov     ebx, eax
0x14001aedd  test    eax, eax
0x14001aedf  jns     short loc_14001AF0B
0x14001aee1  mov     rdx, qword ptr [rbp+arg_20]; int
0x14001aee5  lea     rax, aPushAddingFile; "PUSH: Adding file ID mapping"
0x14001aeec  lea     r9, aUnionfsUfsenum_4; "UnionFs::UfsEnumContext::AddDirEnumFile"...
0x14001aef3  mov     [rsp+50h+var_30], rax; char *
0x14001aef8  mov     r8, 61D0004022Ch; struct UnionFs::StackEventTracer *
0x14001af02  mov     ecx, ebx; this
0x14001af04  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001af09  jmp     short loc_14001AF0D
0x14001af0b  xor     ebx, ebx
0x14001af0d  lea     rcx, [rbp+DestinationString]; UnicodeString
0x14001af11  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14001af16  mov     eax, ebx
0x14001af18  add     rsp, 50h
0x14001af1c  pop     r15
0x14001af1e  pop     r14
0x14001af20  pop     r13
0x14001af22  pop     rdi
0x14001af23  pop     rsi
0x14001af24  pop     rbx
0x14001af25  pop     rbp
0x14001af26  retn
```
