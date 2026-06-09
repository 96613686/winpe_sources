# UnionFs::UfsPathName::AppendUnicodeString(_UNICODE_STRING const &,UnionFs::StackEventTracer &)

- ea: `0x140044374`
- end: `0x140044524`
- name: `?AppendUnicodeString@UfsPathName@UnionFs@@QEAAJAEBU_UNICODE_STRING@@AEAVStackEventTracer@2@@Z`
- size: `432`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PCUNICODE_STRING Source, struct UnionFs::StackEventTracer *)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14003b798`
- `0x14004c74c`
- `0x14006c1fc`

## callees

- `0x140044374`
- `0x14004492c`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140079c48`
- `0x140079d0c`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400444ad`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400444ad`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004447f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004447f`

## string_xrefs

- `0x1400443f5`: `ORIGIN: Allocating new path string`
- `0x14004443f`: `PUSH: Taking ownership of newPath`
- `0x1400443b4`: `UnionFs::UfsPathName::AppendUnicodeString`
- `0x140044408`: `UnionFs::UfsPathName::AppendUnicodeString`
- `0x140044450`: `UnionFs::UfsPathName::AppendUnicodeString`
- `0x1400444d0`: `UnionFs::UfsPathName::AppendUnicodeString`

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
0x140044374  push    rbx
0x140044376  push    rbp
0x140044377  push    rsi
0x140044378  push    rdi
0x140044379  push    r14
0x14004437b  sub     rsp, 40h
0x14004437f  mov     rbx, rcx
0x140044382  xor     ebp, ebp
0x140044384  movzx   ecx, word ptr [rdx]
0x140044387  mov     rsi, r8
0x14004438a  mov     r14, rdx
0x14004438d  test    cx, cx
0x140044390  jz      loc_140044516
0x140044396  movzx   eax, word ptr [rbx]
0x140044399  lea     edx, [rcx+rax]
0x14004439c  cmp     dx, ax
0x14004439f  jnb     short loc_1400443D4
0x1400443a1  lea     rax, aApiAddingLengt; "API: Adding lengths"
0x1400443a8  mov     ebx, 0C0000095h
0x1400443ad  mov     ecx, ebx; this
0x1400443af  mov     [rsp+68h+var_48], rax; char *
0x1400443b4  lea     r9, aUnionfsUfspath_24; "UnionFs::UfsPathName::AppendUnicodeStri"...
0x1400443bb  mov     r8, 5E600130270h; struct UnionFs::StackEventTracer *
0x1400443c5  mov     rdx, rsi; int
0x1400443c8  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400443cd  mov     eax, ebx
0x1400443cf  jmp     loc_140044518
0x1400443d4  cmp     [rbx+2], dx
0x1400443d8  jnb     loc_1400444A7
0x1400443de  mov     r8d, 616E4655h
0x1400443e4  lea     rcx, [rsp+68h+DestinationString]
0x1400443e9  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x1400443ee  cmp     [rsp+68h+DestinationString.Buffer], rbp
0x1400443f3  jnz     short loc_140044423
0x1400443f5  lea     rax, aOriginAllocati_57; "ORIGIN: Allocating new path string"
0x1400443fc  mov     edi, 0C000009Ah
0x140044401  mov     ecx, edi; this
0x140044403  mov     [rsp+68h+var_48], rax; char *
0x140044408  lea     r9, aUnionfsUfspath_24; "UnionFs::UfsPathName::AppendUnicodeStri"...
0x14004440f  mov     r8, 5E70013027Ah; struct UnionFs::StackEventTracer *
0x140044419  mov     rdx, rsi; int
0x14004441c  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140044421  jmp     short loc_140044466
0x140044423  cmp     [rbx+10h], bpl
0x140044427  jnz     short loc_140044477
0x140044429  mov     r8, rsi; int
0x14004442c  lea     rdx, [rsp+68h+DestinationString]; DestinationString
0x140044431  mov     rcx, rbx; SourceString
0x140044434  call    ?EnsureOwnedMemory@UfsPathName@UnionFs@@AEAAJ$$QEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::EnsureOwnedMemory(wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &&,UnionFs::StackEventTracer &)
0x140044439  mov     edi, eax
0x14004443b  test    eax, eax
0x14004443d  jns     short loc_14004449D
0x14004443f  lea     rax, aPushTakingOwne; "PUSH: Taking ownership of newPath"
0x140044446  mov     r8, 3AC00130283h; struct UnionFs::StackEventTracer *
0x140044450  lea     r9, aUnionfsUfspath_24; "UnionFs::UfsPathName::AppendUnicodeStri"...
0x140044457  mov     [rsp+68h+var_48], rax; char *
0x14004445c  mov     rdx, rsi; int
0x14004445f  mov     ecx, edi; this
0x140044461  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140044466  lea     rcx, [rsp+68h+DestinationString]; UnicodeString
0x14004446b  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044470  mov     eax, edi
0x140044472  jmp     loc_140044518
0x140044477  mov     rdx, rbx; SourceString
0x14004447a  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14004447f  call    cs:__imp_RtlCopyUnicodeString
0x140044486  nop     dword ptr [rax+rax+00h]
0x14004448b  movups  xmm1, xmmword ptr [rbx]
0x14004448e  movaps  xmm0, xmmword ptr [rsp+68h+DestinationString.Length]
0x140044493  movdqa  xmmword ptr [rsp+68h+DestinationString.Length], xmm1
0x140044499  movdqu  xmmword ptr [rbx], xmm0
0x14004449d  lea     rcx, [rsp+68h+DestinationString]; UnicodeString
0x1400444a2  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400444a7  mov     rdx, r14; Source
0x1400444aa  mov     rcx, rbx; Destination
0x1400444ad  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400444b4  nop     dword ptr [rax+rax+00h]
0x1400444b9  mov     edi, eax
0x1400444bb  test    eax, eax
0x1400444bd  jns     short loc_1400444E8
0x1400444bf  lea     rax, aApiAppendingSt; "API: Appending string"
0x1400444c6  mov     r8, 5E800130290h; struct UnionFs::StackEventTracer *
0x1400444d0  lea     r9, aUnionfsUfspath_24; "UnionFs::UfsPathName::AppendUnicodeStri"...
0x1400444d7  mov     [rsp+68h+var_48], rax; char *
0x1400444dc  mov     rdx, rsi; int
0x1400444df  mov     ecx, edi; this
0x1400444e1  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400444e6  jmp     short loc_140044470
0x1400444e8  movzx   edx, word ptr [rbx+18h]
0x1400444ec  mov     rcx, [rbx+8]
0x1400444f0  mov     [rbx+20h], rcx
0x1400444f4  mov     [rbx+1Ah], dx
0x1400444f8  mov     [rbx+18h], dx
0x1400444fc  lea     rax, [rcx+rdx]
0x140044500  mov     [rbx+38h], bp
0x140044504  mov     [rbx+30h], rax
0x140044508  movzx   eax, word ptr [rbx]
0x14004450b  sub     ax, dx
0x14004450e  mov     [rbx+2Ah], ax
0x140044512  mov     [rbx+28h], ax
0x140044516  xor     eax, eax
0x140044518  add     rsp, 40h
0x14004451c  pop     r14
0x14004451e  pop     rdi
0x14004451f  pop     rsi
0x140044520  pop     rbp
0x140044521  pop     rbx
0x140044522  retn
```
