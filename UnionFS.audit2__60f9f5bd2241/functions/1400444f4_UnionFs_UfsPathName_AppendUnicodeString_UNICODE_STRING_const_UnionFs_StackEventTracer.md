# UnionFs::UfsPathName::AppendUnicodeString(_UNICODE_STRING const &,UnionFs::StackEventTracer &)

- ea: `0x1400444f4`
- end: `0x1400446a4`
- name: `?AppendUnicodeString@UfsPathName@UnionFs@@QEAAJAEBU_UNICODE_STRING@@AEAVStackEventTracer@2@@Z`
- size: `432`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PCUNICODE_STRING Source, struct UnionFs::StackEventTracer *)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14003b8b8`
- `0x14004c8cc`
- `0x14006c3ec`

## callees

- `0x1400444f4`
- `0x140044aac`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140079f68`
- `0x14007a02c`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004462d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004462d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400445ff`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400445ff`

## string_xrefs

- `0x140044575`: `ORIGIN: Allocating new path string`
- `0x1400445bf`: `PUSH: Taking ownership of newPath`
- `0x140044534`: `UnionFs::UfsPathName::AppendUnicodeString`
- `0x140044588`: `UnionFs::UfsPathName::AppendUnicodeString`
- `0x1400445d0`: `UnionFs::UfsPathName::AppendUnicodeString`
- `0x140044650`: `UnionFs::UfsPathName::AppendUnicodeString`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathName::AppendUnicodeString(
        struct _UNICODE_STRING *SourceString,
        PCUNICODE_STRING Source,
        struct UnionFs::StackEventTracer *a3)
{
  int Length; // ecx
  int v5; // esi
  int v7; // eax
  NTSTATUS appended; // edi
  struct _UNICODE_STRING *v10; // rdx
  struct _UNICODE_STRING *v11; // rdx
  struct _UNICODE_STRING v12; // xmm0
  __int64 Buffer_low; // rdx
  PWSTR Buffer; // rcx
  __int16 v15; // ax
  const char *v16; // [rsp+28h] [rbp-40h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF

  Length = Source->Length;
  v5 = (int)a3;
  if ( (_WORD)Length )
  {
    v7 = SourceString->Length;
    if ( (unsigned __int16)(Length + v7) < (unsigned __int16)v7 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)0xC0000095LL,
        (int)a3,
        (struct UnionFs::StackEventTracer *)0x5E600130270LL,
        (unsigned __int64)"UnionFs::UfsPathName::AppendUnicodeString",
        "API: Adding lengths",
        v16);
      return 3221225621LL;
    }
    if ( SourceString->MaximumLength < (unsigned __int16)(Length + v7) )
    {
      FsFltWil::MakeUniqueUnicodeString(&DestinationString, (unsigned int)(Length + v7), 1634616917);
      if ( !DestinationString.Buffer )
      {
        appended = -1073741670;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          v5,
          (struct UnionFs::StackEventTracer *)0x5E70013027ALL,
          (unsigned __int64)"UnionFs::UfsPathName::AppendUnicodeString",
          "ORIGIN: Allocating new path string",
          v16);
LABEL_10:
        FsFltWil::Details::FreeUnicodeString(&DestinationString, v10);
        return (unsigned int)appended;
      }
      if ( LOBYTE(SourceString[1].Length) )
      {
        RtlCopyUnicodeString(&DestinationString, SourceString);
        v12 = DestinationString;
        DestinationString = *SourceString;
        *SourceString = v12;
      }
      else
      {
        appended = UnionFs::UfsPathName::EnsureOwnedMemory(SourceString, &DestinationString, v5);
        if ( appended < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)appended,
            v5,
            (struct UnionFs::StackEventTracer *)0x3AC00130283LL,
            (unsigned __int64)"UnionFs::UfsPathName::AppendUnicodeString",
            "PUSH: Taking ownership of newPath",
            v16);
          goto LABEL_10;
        }
      }
      FsFltWil::Details::FreeUnicodeString(&DestinationString, v11);
    }
    appended = RtlAppendUnicodeStringToString(SourceString, Source);
    if ( appended < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)appended,
        v5,
        (struct UnionFs::StackEventTracer *)0x5E800130290LL,
        (unsigned __int64)"UnionFs::UfsPathName::AppendUnicodeString",
        "API: Appending string",
        v16);
      return (unsigned int)appended;
    }
    Buffer_low = LOWORD(SourceString[1].Buffer);
    Buffer = SourceString->Buffer;
    *(_QWORD *)&SourceString[2].Length = Buffer;
    WORD1(SourceString[1].Buffer) = Buffer_low;
    LOWORD(SourceString[1].Buffer) = Buffer_low;
    LOWORD(SourceString[3].Buffer) = 0;
    *(_QWORD *)&SourceString[3].Length = (char *)Buffer + Buffer_low;
    v15 = SourceString->Length - Buffer_low;
    WORD1(SourceString[2].Buffer) = v15;
    LOWORD(SourceString[2].Buffer) = v15;
  }
  return 0;
}

```

## disassembly

```asm
0x1400444f4  push    rbx
0x1400444f6  push    rbp
0x1400444f7  push    rsi
0x1400444f8  push    rdi
0x1400444f9  push    r14
0x1400444fb  sub     rsp, 40h
0x1400444ff  mov     rbx, rcx
0x140044502  xor     ebp, ebp
0x140044504  movzx   ecx, word ptr [rdx]
0x140044507  mov     rsi, r8
0x14004450a  mov     r14, rdx
0x14004450d  test    cx, cx
0x140044510  jz      loc_140044696
0x140044516  movzx   eax, word ptr [rbx]
0x140044519  lea     edx, [rcx+rax]
0x14004451c  cmp     dx, ax
0x14004451f  jnb     short loc_140044554
0x140044521  lea     rax, aApiAddingLengt; "API: Adding lengths"
0x140044528  mov     ebx, 0C0000095h
0x14004452d  mov     ecx, ebx; this
0x14004452f  mov     [rsp+68h+var_48], rax; char *
0x140044534  lea     r9, aUnionfsUfspath_24; "UnionFs::UfsPathName::AppendUnicodeStri"...
0x14004453b  mov     r8, 5E600130270h; struct UnionFs::StackEventTracer *
0x140044545  mov     rdx, rsi; int
0x140044548  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004454d  mov     eax, ebx
0x14004454f  jmp     loc_140044698
0x140044554  cmp     [rbx+2], dx
0x140044558  jnb     loc_140044627
0x14004455e  mov     r8d, 616E4655h
0x140044564  lea     rcx, [rsp+68h+DestinationString]
0x140044569  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14004456e  cmp     [rsp+68h+DestinationString.Buffer], rbp
0x140044573  jnz     short loc_1400445A3
0x140044575  lea     rax, aOriginAllocati_58; "ORIGIN: Allocating new path string"
0x14004457c  mov     edi, 0C000009Ah
0x140044581  mov     ecx, edi; this
0x140044583  mov     [rsp+68h+var_48], rax; char *
0x140044588  lea     r9, aUnionfsUfspath_24; "UnionFs::UfsPathName::AppendUnicodeStri"...
0x14004458f  mov     r8, 5E70013027Ah; struct UnionFs::StackEventTracer *
0x140044599  mov     rdx, rsi; int
0x14004459c  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400445a1  jmp     short loc_1400445E6
0x1400445a3  cmp     [rbx+10h], bpl
0x1400445a7  jnz     short loc_1400445F7
0x1400445a9  mov     r8, rsi; int
0x1400445ac  lea     rdx, [rsp+68h+DestinationString]; DestinationString
0x1400445b1  mov     rcx, rbx; SourceString
0x1400445b4  call    ?EnsureOwnedMemory@UfsPathName@UnionFs@@AEAAJ$$QEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::EnsureOwnedMemory(wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &&,UnionFs::StackEventTracer &)
0x1400445b9  mov     edi, eax
0x1400445bb  test    eax, eax
0x1400445bd  jns     short loc_14004461D
0x1400445bf  lea     rax, aPushTakingOwne; "PUSH: Taking ownership of newPath"
0x1400445c6  mov     r8, 3AC00130283h; struct UnionFs::StackEventTracer *
0x1400445d0  lea     r9, aUnionfsUfspath_24; "UnionFs::UfsPathName::AppendUnicodeStri"...
0x1400445d7  mov     [rsp+68h+var_48], rax; char *
0x1400445dc  mov     rdx, rsi; int
0x1400445df  mov     ecx, edi; this
0x1400445e1  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400445e6  lea     rcx, [rsp+68h+DestinationString]; UnicodeString
0x1400445eb  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400445f0  mov     eax, edi
0x1400445f2  jmp     loc_140044698
0x1400445f7  mov     rdx, rbx; SourceString
0x1400445fa  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1400445ff  call    cs:__imp_RtlCopyUnicodeString
0x140044606  nop     dword ptr [rax+rax+00h]
0x14004460b  movups  xmm1, xmmword ptr [rbx]
0x14004460e  movaps  xmm0, xmmword ptr [rsp+68h+DestinationString.Length]
0x140044613  movdqa  xmmword ptr [rsp+68h+DestinationString.Length], xmm1
0x140044619  movdqu  xmmword ptr [rbx], xmm0
0x14004461d  lea     rcx, [rsp+68h+DestinationString]; UnicodeString
0x140044622  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044627  mov     rdx, r14; Source
0x14004462a  mov     rcx, rbx; Destination
0x14004462d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140044634  nop     dword ptr [rax+rax+00h]
0x140044639  mov     edi, eax
0x14004463b  test    eax, eax
0x14004463d  jns     short loc_140044668
0x14004463f  lea     rax, aApiAppendingSt; "API: Appending string"
0x140044646  mov     r8, 5E800130290h; struct UnionFs::StackEventTracer *
0x140044650  lea     r9, aUnionfsUfspath_24; "UnionFs::UfsPathName::AppendUnicodeStri"...
0x140044657  mov     [rsp+68h+var_48], rax; char *
0x14004465c  mov     rdx, rsi; int
0x14004465f  mov     ecx, edi; this
0x140044661  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140044666  jmp     short loc_1400445F0
0x140044668  movzx   edx, word ptr [rbx+18h]
0x14004466c  mov     rcx, [rbx+8]
0x140044670  mov     [rbx+20h], rcx
0x140044674  mov     [rbx+1Ah], dx
0x140044678  mov     [rbx+18h], dx
0x14004467c  lea     rax, [rcx+rdx]
0x140044680  mov     [rbx+38h], bp
0x140044684  mov     [rbx+30h], rax
0x140044688  movzx   eax, word ptr [rbx]
0x14004468b  sub     ax, dx
0x14004468e  mov     [rbx+2Ah], ax
0x140044692  mov     [rbx+28h], ax
0x140044696  xor     eax, eax
0x140044698  add     rsp, 40h
0x14004469c  pop     r14
0x14004469e  pop     rdi
0x14004469f  pop     rsi
0x1400446a0  pop     rbp
0x1400446a1  pop     rbx
0x1400446a2  retn
```
