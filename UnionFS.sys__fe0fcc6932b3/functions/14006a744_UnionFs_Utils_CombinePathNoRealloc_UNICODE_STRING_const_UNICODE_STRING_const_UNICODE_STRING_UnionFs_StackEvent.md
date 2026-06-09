# UnionFs::Utils::CombinePathNoRealloc(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING &,UnionFs::StackEventTracer &,ushort const *)

- ea: `0x14006a744`
- end: `0x14006a933`
- name: `?CombinePathNoRealloc@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@0AEAU3@AEAVStackEventTracer@2@PEBG@Z`
- size: `495`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PCUNICODE_STRING Source, const struct _UNICODE_STRING *this, struct _UNICODE_STRING *, struct _UNICODE_STRING *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14006a5bc`
- `0x1400788e0`

## callees

- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x14006a744`
- `0x14006a93c`
- `0x140078764`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006a8b2`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006a8b2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006a8ca`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006a8ca`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006a7f8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006a834`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006a7f8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006a834`

## string_xrefs

- `0x14006a780`: `PUSH: ComputeCombinedPathLength`
- `0x14006a8dc`: `Couldn't append name component`
- `0x14006a791`: `UnionFs::Utils::CombinePathNoRealloc`
- `0x14006a7cc`: `UnionFs::Utils::CombinePathNoRealloc`
- `0x14006a8f9`: `UnionFs::Utils::CombinePathNoRealloc`
- `0x14006a7b9`: `ORIGIN: CombinedPath too small`
- `0x14006a8e8`: `API: Constructing CombinedPath`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::CombinePathNoRealloc(
        PCUNICODE_STRING SourceString,
        PCUNICODE_STRING Source,
        struct _UNICODE_STRING *this,
        struct _UNICODE_STRING *a4,
        struct _UNICODE_STRING *a5)
{
  USHORT Length; // dx
  int v9; // r14d
  int v10; // ebp
  unsigned int v12; // edx
  unsigned __int64 v13; // r8
  WCHAR v14; // r9
  bool v15; // dl
  NTSTATUS appended; // edi
  char *v17; // [rsp+20h] [rbp-48h]
  const char *v18; // [rsp+28h] [rbp-40h]
  unsigned __int16 v19; // [rsp+70h] [rbp+8h] BYREF

  this->Length = 0;
  Length = Source->Length;
  v19 = 0;
  v9 = (int)a4;
  v10 = UnionFs::Utils::ComputeCombinedPathLength(
          (UnionFs::Utils *)SourceString->Length,
          Length,
          (unsigned __int16)&v19,
          &a4->Length,
          (struct UnionFs::StackEventTracer *)v17);
  if ( v10 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v10,
      v9,
      (struct UnionFs::StackEventTracer *)0x49400210482LL,
      (unsigned __int64)"UnionFs::Utils::CombinePathNoRealloc",
      "PUSH: ComputeCombinedPathLength",
      v18);
    return (unsigned int)v10;
  }
  if ( this->MaximumLength < v19 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0000023LL,
      v9,
      (struct UnionFs::StackEventTracer *)0x4FE00210488LL,
      (unsigned __int64)"UnionFs::Utils::CombinePathNoRealloc",
      "ORIGIN: CombinedPath too small",
      v18);
    return 3221225507LL;
  }
  if ( SourceString->Length )
  {
    RtlCopyUnicodeString(this, SourceString);
    if ( Source->Length )
    {
      v14 = *Source->Buffer;
      if ( v14 != 92 || Source->Length != 2 )
      {
        v13 = this->Length;
        v15 = 0;
        if ( this->Buffer[(v13 >> 1) - 1] == 92 )
        {
          if ( v14 == 92 )
          {
            LOWORD(v13) = v13 - 2;
            this->Length = v13;
          }
        }
        else
        {
          v15 = v14 != 92;
        }
        if ( Source->Length )
        {
          if ( v15 && (appended = RtlAppendUnicodeToString(this, L"\\"), appended < 0)
            || (appended = RtlAppendUnicodeStringToString(this, Source), appended < 0) )
          {
            MicrosoftTelemetryAssertTriggeredMsgKM("Couldn't append name component");
            UnionFs::ProcessTraceStatusFromApi(
              (UnionFs *)(unsigned int)appended,
              v9,
              (struct UnionFs::StackEventTracer *)0x2F0002104CALL,
              (unsigned __int64)"UnionFs::Utils::CombinePathNoRealloc",
              "API: Constructing CombinedPath",
              v18);
            return (unsigned int)appended;
          }
        }
      }
    }
    UnionFs::Utils::StripTrailingBackslashFromPath((UnionFs::Utils *)this, a5, (const unsigned __int16 *)v13);
  }
  else
  {
    RtlCopyUnicodeString(this, Source);
    v12 = this->Length;
    if ( v12 > 2 && this->Buffer[((unsigned __int64)this->Length >> 1) - 1] == 92 )
      this->Length = v12 - 2;
  }
  return 0;
}

```

## disassembly

```asm
0x14006a744  push    rbx
0x14006a746  push    rbp
0x14006a747  push    rsi
0x14006a748  push    rdi
0x14006a749  push    r14
0x14006a74b  push    r15
0x14006a74d  sub     rsp, 38h
0x14006a751  xor     r15d, r15d
0x14006a754  mov     rbx, r8
0x14006a757  mov     [r8], r15w
0x14006a75b  mov     rsi, rdx
0x14006a75e  movzx   edx, word ptr [rdx]; unsigned __int16
0x14006a761  lea     r8, [rsp+68h+arg_0]; unsigned __int16
0x14006a766  mov     rdi, rcx
0x14006a769  mov     [rsp+68h+arg_0], r15w
0x14006a76f  movzx   ecx, word ptr [rcx]; this
0x14006a772  mov     r14, r9
0x14006a775  call    ?ComputeCombinedPathLength@Utils@UnionFs@@YAJGGPEAGAEAVStackEventTracer@2@@Z; UnionFs::Utils::ComputeCombinedPathLength(ushort,ushort,ushort *,UnionFs::StackEventTracer &)
0x14006a77a  mov     ebp, eax
0x14006a77c  test    eax, eax
0x14006a77e  jns     short loc_14006A7AE
0x14006a780  lea     rax, aPushComputecom_0; "PUSH: ComputeCombinedPathLength"
0x14006a787  mov     r8, 49400210482h; struct UnionFs::StackEventTracer *
0x14006a791  lea     r9, aUnionfsUtilsCo_0; "UnionFs::Utils::CombinePathNoRealloc"
0x14006a798  mov     [rsp+68h+var_48], rax; char *
0x14006a79d  mov     rdx, r14; int
0x14006a7a0  mov     ecx, ebp; this
0x14006a7a2  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006a7a7  mov     eax, ebp
0x14006a7a9  jmp     loc_14006A925
0x14006a7ae  movzx   eax, [rsp+68h+arg_0]
0x14006a7b3  cmp     [rbx+2], ax
0x14006a7b7  jnb     short loc_14006A7EC
0x14006a7b9  lea     rax, aOriginCombined; "ORIGIN: CombinedPath too small"
0x14006a7c0  mov     ebx, 0C0000023h
0x14006a7c5  mov     ecx, ebx; this
0x14006a7c7  mov     [rsp+68h+var_48], rax; char *
0x14006a7cc  lea     r9, aUnionfsUtilsCo_0; "UnionFs::Utils::CombinePathNoRealloc"
0x14006a7d3  mov     r8, 4FE00210488h; struct UnionFs::StackEventTracer *
0x14006a7dd  mov     rdx, r14; int
0x14006a7e0  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006a7e5  mov     eax, ebx
0x14006a7e7  jmp     loc_14006A925
0x14006a7ec  mov     rcx, rbx; DestinationString
0x14006a7ef  cmp     [rdi], r15w
0x14006a7f3  jnz     short loc_14006A831
0x14006a7f5  mov     rdx, rsi; SourceString
0x14006a7f8  call    cs:__imp_RtlCopyUnicodeString
0x14006a7ff  nop     dword ptr [rax+rax+00h]
0x14006a804  movzx   edx, word ptr [rbx]
0x14006a807  cmp     edx, 2
0x14006a80a  jbe     loc_14006A923
0x14006a810  mov     rax, [rbx+8]
0x14006a814  mov     ecx, edx
0x14006a816  shr     rcx, 1
0x14006a819  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14006a81f  jnz     loc_14006A923
0x14006a825  sub     dx, 2
0x14006a829  mov     [rbx], dx
0x14006a82c  jmp     loc_14006A923
0x14006a831  mov     rdx, rdi; SourceString
0x14006a834  call    cs:__imp_RtlCopyUnicodeString
0x14006a83b  nop     dword ptr [rax+rax+00h]
0x14006a840  movzx   ecx, word ptr [rsi]
0x14006a843  test    cx, cx
0x14006a846  jz      loc_14006A913
0x14006a84c  mov     rax, [rsi+8]
0x14006a850  movzx   r9d, word ptr [rax]
0x14006a854  cmp     r9w, 5Ch ; '\'
0x14006a859  jnz     short loc_14006A865
0x14006a85b  cmp     cx, 2
0x14006a85f  jz      loc_14006A913
0x14006a865  movzx   r8d, word ptr [rbx]
0x14006a869  mov     rax, [rbx+8]
0x14006a86d  mov     ecx, r8d
0x14006a870  shr     rcx, 1
0x14006a873  movzx   edx, r15b
0x14006a877  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14006a87d  jnz     short loc_14006A891
0x14006a87f  cmp     r9w, 5Ch ; '\'
0x14006a884  jnz     short loc_14006A89E
0x14006a886  sub     r8w, 2
0x14006a88b  mov     [rbx], r8w
0x14006a88f  jmp     short loc_14006A89E
0x14006a891  cmp     r9w, 5Ch ; '\'
0x14006a896  mov     eax, 1
0x14006a89b  cmovnz  edx, eax
0x14006a89e  cmp     [rsi], r15w
0x14006a8a2  jz      short loc_14006A913
0x14006a8a4  test    dl, dl
0x14006a8a6  jz      short loc_14006A8C4
0x14006a8a8  lea     rdx, Source; "\\"
0x14006a8af  mov     rcx, rbx; Destination
0x14006a8b2  call    cs:__imp_RtlAppendUnicodeToString
0x14006a8b9  nop     dword ptr [rax+rax+00h]
0x14006a8be  mov     edi, eax
0x14006a8c0  test    eax, eax
0x14006a8c2  js      short loc_14006A8DC
0x14006a8c4  mov     rdx, rsi; Source
0x14006a8c7  mov     rcx, rbx; Destination
0x14006a8ca  call    cs:__imp_RtlAppendUnicodeStringToString
0x14006a8d1  nop     dword ptr [rax+rax+00h]
0x14006a8d6  mov     edi, eax
0x14006a8d8  test    eax, eax
0x14006a8da  jns     short loc_14006A913
0x14006a8dc  lea     rcx, aCouldnTAppendN; "Couldn't append name component"
0x14006a8e3  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14006a8e8  lea     rax, aApiConstructin_1; "API: Constructing CombinedPath"
0x14006a8ef  mov     r8, 2F0002104CAh; struct UnionFs::StackEventTracer *
0x14006a8f9  lea     r9, aUnionfsUtilsCo_0; "UnionFs::Utils::CombinePathNoRealloc"
0x14006a900  mov     [rsp+68h+var_48], rax; char *
0x14006a905  mov     rdx, r14; int
0x14006a908  mov     ecx, edi; this
0x14006a90a  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006a90f  mov     eax, edi
0x14006a911  jmp     short loc_14006A925
0x14006a913  mov     rdx, [rsp+68h+arg_20]; struct _UNICODE_STRING *
0x14006a91b  mov     rcx, rbx; this
0x14006a91e  call    ?StripTrailingBackslashFromPath@Utils@UnionFs@@YAXAEAU_UNICODE_STRING@@PEBG@Z; UnionFs::Utils::StripTrailingBackslashFromPath(_UNICODE_STRING &,ushort const *)
0x14006a923  xor     eax, eax
0x14006a925  add     rsp, 38h
0x14006a929  pop     r15
0x14006a92b  pop     r14
0x14006a92d  pop     rdi
0x14006a92e  pop     rsi
0x14006a92f  pop     rbp
0x14006a930  pop     rbx
0x14006a931  retn
```
