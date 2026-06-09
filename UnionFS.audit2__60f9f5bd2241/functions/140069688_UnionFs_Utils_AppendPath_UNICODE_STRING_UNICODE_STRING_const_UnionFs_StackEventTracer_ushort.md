# UnionFs::Utils::AppendPath(_UNICODE_STRING &,_UNICODE_STRING const &,UnionFs::StackEventTracer &,ushort *)

- ea: `0x140069688`
- end: `0x140069894`
- name: `?AppendPath@Utils@UnionFs@@YAJAEAU_UNICODE_STRING@@AEBU3@AEAVStackEventTracer@2@PEAG@Z`
- size: `524`
- prototype: `__int64 __fastcall(UnionFs::Utils *__hidden this, PCUNICODE_STRING Source, const struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140044334`
- `0x14004fb08`

## callees

- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140069688`
- `0x14006a93c`
- `0x140078764`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400697c6`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400697c6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006980d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006980d`

## string_xrefs

- `0x1400696d6`: `PUSH: ComputeCombinedPathLength`
- `0x14006981f`: `Couldn't append name component`
- `0x1400696e7`: `UnionFs::Utils::AppendPath`
- `0x140069742`: `UnionFs::Utils::AppendPath`
- `0x14006983c`: `UnionFs::Utils::AppendPath`
- `0x1400697fb`: `((((Root.Length >= sizeof(WCHAR)) && (Root.Buffer[(Root.Length / sizeof(WCHAR)) - 1] == L'\\'))) && (RelativePath.Buffer[0] != L'\\')) || ((((Root.Length < sizeof(WCHAR)) || (Root.Buffer[(Root.Length / sizeof(WCHAR)) - 1] != L'\\'))) && (RelativePath.Buffer[0] == L'\\'))`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::AppendPath(
        UnionFs::Utils *this,
        PCUNICODE_STRING Source,
        const struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  UnionFs::Utils *v5; // rcx
  int v7; // ebp
  USHORT Length; // dx
  NTSTATUS appended; // edi
  char v12; // dl
  int v13; // ecx
  WCHAR v14; // r8
  unsigned int v15; // ecx
  unsigned __int64 v16; // rdx
  const unsigned __int16 *v17; // r8
  unsigned int v18; // edx
  char *v19; // [rsp+20h] [rbp-48h]
  const char *v20; // [rsp+28h] [rbp-40h]
  unsigned __int16 v21; // [rsp+70h] [rbp+8h] BYREF

  v5 = (UnionFs::Utils *)*(unsigned __int16 *)this;
  v7 = (int)a3;
  if ( (_WORD)v5 == 2 && **((_WORD **)this + 1) == 92 )
    v5 = 0;
  Length = Source->Length;
  v21 = 0;
  appended = UnionFs::Utils::ComputeCombinedPathLength(
               v5,
               Length,
               (unsigned __int16)&v21,
               &a3->Length,
               (struct UnionFs::StackEventTracer *)v19);
  if ( appended < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)appended,
      v7,
      (struct UnionFs::StackEventTracer *)0x274002104E4LL,
      (unsigned __int64)"UnionFs::Utils::AppendPath",
      "PUSH: ComputeCombinedPathLength",
      v20);
    return (unsigned int)appended;
  }
  v12 = 0;
  if ( a4 && *(_WORD *)this == a4->Length )
  {
    v12 = 1;
    v13 = v21 - 1;
  }
  else
  {
    v13 = v21;
  }
  if ( *((unsigned __int16 *)this + 1) < v13 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0000023LL,
      v7,
      (struct UnionFs::StackEventTracer *)0x275002104F1LL,
      (unsigned __int64)"UnionFs::Utils::AppendPath",
      "ORIGIN: Root too small",
      v20);
    return 3221225507LL;
  }
  if ( !Source->Length || (v14 = *Source->Buffer, v14 == 92) && Source->Length == 2 && !v12 )
  {
    v18 = *(unsigned __int16 *)this;
    if ( v18 > 2 && *(_WORD *)(*((_QWORD *)this + 1) + 2 * ((unsigned __int64)*(unsigned __int16 *)this >> 1) - 2) == 92 )
      *(_WORD *)this = v18 - 2;
    return 0;
  }
  v15 = *(unsigned __int16 *)this;
  v16 = (unsigned __int64)*(unsigned __int16 *)this >> 1;
  if ( v15 >= 2 && *(_WORD *)(*((_QWORD *)this + 1) + 2 * v16 - 2) == 92 )
  {
    if ( v14 == 92 )
    {
      *(_WORD *)this = v15 - 2;
      goto LABEL_30;
    }
LABEL_25:
    if ( *(_WORD *)(*((_QWORD *)this + 1) + 2 * v16 - 2) == 92 )
    {
      if ( v14 != 92 )
        goto LABEL_30;
    }
    else if ( v14 == 92 )
    {
      goto LABEL_30;
    }
    MicrosoftTelemetryAssertTriggeredMsgKM(
      "((((Root.Length >= sizeof(WCHAR)) && (Root.Buffer[(Root.Length / sizeof(WCHAR)) - 1] == L'\\\\'))) && (RelativePat"
      "h.Buffer[0] != L'\\\\')) || ((((Root.Length < sizeof(WCHAR)) || (Root.Buffer[(Root.Length / sizeof(WCHAR)) - 1] !="
      " L'\\\\'))) && (RelativePath.Buffer[0] == L'\\\\'))");
    goto LABEL_30;
  }
  if ( v14 != 92 )
  {
    appended = RtlAppendUnicodeToString((PUNICODE_STRING)this, L"\\");
    if ( appended < 0 )
    {
LABEL_31:
      MicrosoftTelemetryAssertTriggeredMsgKM("Couldn't append name component");
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)appended,
        v7,
        (struct UnionFs::StackEventTracer *)0x2760021052BLL,
        (unsigned __int64)"UnionFs::Utils::AppendPath",
        "API: Constructing Root",
        v20);
      return (unsigned int)appended;
    }
    goto LABEL_30;
  }
  if ( v15 >= 2 )
    goto LABEL_25;
LABEL_30:
  appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)this, Source);
  if ( appended < 0 )
    goto LABEL_31;
  UnionFs::Utils::StripTrailingBackslashFromPath(this, a4, v17);
  return 0;
}

```

## disassembly

```asm
0x140069688  push    rbx
0x14006968a  push    rbp
0x14006968b  push    rsi
0x14006968c  push    rdi
0x14006968d  push    r12
0x14006968f  push    r14
0x140069691  sub     rsp, 38h
0x140069695  mov     rbx, rcx
0x140069698  xor     r12d, r12d
0x14006969b  movzx   ecx, word ptr [rcx]
0x14006969e  mov     rsi, r9
0x1400696a1  mov     rbp, r8
0x1400696a4  mov     r14, rdx
0x1400696a7  cmp     cx, 2
0x1400696ab  jnz     short loc_1400696BA
0x1400696ad  mov     rax, [rbx+8]
0x1400696b1  cmp     word ptr [rax], 5Ch ; '\'
0x1400696b5  jnz     short loc_1400696BA
0x1400696b7  mov     ecx, r12d; this
0x1400696ba  movzx   edx, word ptr [rdx]; unsigned __int16
0x1400696bd  lea     r8, [rsp+68h+arg_0]; unsigned __int16
0x1400696c2  mov     r9, rbp; unsigned __int16 *
0x1400696c5  mov     [rsp+68h+arg_0], r12w
0x1400696cb  call    ?ComputeCombinedPathLength@Utils@UnionFs@@YAJGGPEAGAEAVStackEventTracer@2@@Z; UnionFs::Utils::ComputeCombinedPathLength(ushort,ushort,ushort *,UnionFs::StackEventTracer &)
0x1400696d0  mov     edi, eax
0x1400696d2  test    eax, eax
0x1400696d4  jns     short loc_140069704
0x1400696d6  lea     rax, aPushComputecom_0; "PUSH: ComputeCombinedPathLength"
0x1400696dd  mov     r8, 274002104E4h; struct UnionFs::StackEventTracer *
0x1400696e7  lea     r9, aUnionfsUtilsAp; "UnionFs::Utils::AppendPath"
0x1400696ee  mov     [rsp+68h+var_48], rax; char *
0x1400696f3  mov     rdx, rbp; int
0x1400696f6  mov     ecx, edi; this
0x1400696f8  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400696fd  mov     eax, edi
0x1400696ff  jmp     loc_140069886
0x140069704  mov     dl, r12b
0x140069707  test    rsi, rsi
0x14006970a  jz      short loc_140069722
0x14006970c  movzx   eax, word ptr [rsi]
0x14006970f  cmp     [rbx], ax
0x140069712  jnz     short loc_140069722
0x140069714  movzx   ecx, [rsp+68h+arg_0]
0x140069719  mov     edx, 1
0x14006971e  sub     ecx, edx
0x140069720  jmp     short loc_140069727
0x140069722  movzx   ecx, [rsp+68h+arg_0]
0x140069727  movzx   eax, word ptr [rbx+2]
0x14006972b  cmp     eax, ecx
0x14006972d  jge     short loc_140069762
0x14006972f  lea     rax, aOriginRootTooS; "ORIGIN: Root too small"
0x140069736  mov     ebx, 0C0000023h
0x14006973b  mov     ecx, ebx; this
0x14006973d  mov     [rsp+68h+var_48], rax; char *
0x140069742  lea     r9, aUnionfsUtilsAp; "UnionFs::Utils::AppendPath"
0x140069749  mov     r8, 275002104F1h; struct UnionFs::StackEventTracer *
0x140069753  mov     rdx, rbp; int
0x140069756  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006975b  mov     eax, ebx
0x14006975d  jmp     loc_140069886
0x140069762  movzx   ecx, word ptr [r14]
0x140069766  test    cx, cx
0x140069769  jz      loc_140069864
0x14006976f  mov     rax, [r14+8]
0x140069773  movzx   r8d, word ptr [rax]
0x140069777  cmp     r8w, 5Ch ; '\'
0x14006977c  jnz     short loc_14006978C
0x14006977e  cmp     cx, 2
0x140069782  jnz     short loc_14006978C
0x140069784  test    dl, dl
0x140069786  jz      loc_140069864
0x14006978c  movzx   ecx, word ptr [rbx]
0x14006978f  mov     edx, ecx
0x140069791  shr     rdx, 1
0x140069794  cmp     ecx, 2
0x140069797  jb      short loc_1400697B5
0x140069799  mov     rax, [rbx+8]
0x14006979d  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x1400697a3  jnz     short loc_1400697B5
0x1400697a5  cmp     r8w, 5Ch ; '\'
0x1400697aa  jnz     short loc_1400697DF
0x1400697ac  sub     cx, 2
0x1400697b0  mov     [rbx], cx
0x1400697b3  jmp     short loc_140069807
0x1400697b5  cmp     r8w, 5Ch ; '\'
0x1400697ba  jz      short loc_1400697DA
0x1400697bc  lea     rdx, Source; "\\"
0x1400697c3  mov     rcx, rbx; Destination
0x1400697c6  call    cs:__imp_RtlAppendUnicodeToString
0x1400697cd  nop     dword ptr [rax+rax+00h]
0x1400697d2  mov     edi, eax
0x1400697d4  test    eax, eax
0x1400697d6  js      short loc_14006981F
0x1400697d8  jmp     short loc_140069807
0x1400697da  cmp     ecx, 2
0x1400697dd  jb      short loc_140069807
0x1400697df  mov     rax, [rbx+8]
0x1400697e3  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x1400697e9  jnz     short loc_1400697F4
0x1400697eb  cmp     r8w, 5Ch ; '\'
0x1400697f0  jnz     short loc_140069807
0x1400697f2  jmp     short loc_1400697FB
0x1400697f4  cmp     r8w, 5Ch ; '\'
0x1400697f9  jz      short loc_140069807
0x1400697fb  lea     rcx, aRootLengthSize; "((((Root.Length >= sizeof(WCHAR)) && (R"...
0x140069802  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140069807  mov     rdx, r14; Source
0x14006980a  mov     rcx, rbx; Destination
0x14006980d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140069814  nop     dword ptr [rax+rax+00h]
0x140069819  mov     edi, eax
0x14006981b  test    eax, eax
0x14006981d  jns     short loc_140069857
0x14006981f  lea     rcx, aCouldnTAppendN; "Couldn't append name component"
0x140069826  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14006982b  lea     rax, aApiConstructin; "API: Constructing Root"
0x140069832  mov     r8, 2760021052Bh; struct UnionFs::StackEventTracer *
0x14006983c  lea     r9, aUnionfsUtilsAp; "UnionFs::Utils::AppendPath"
0x140069843  mov     [rsp+68h+var_48], rax; char *
0x140069848  mov     rdx, rbp; int
0x14006984b  mov     ecx, edi; this
0x14006984d  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140069852  jmp     loc_1400696FD
0x140069857  mov     rdx, rsi; struct _UNICODE_STRING *
0x14006985a  mov     rcx, rbx; this
0x14006985d  call    ?StripTrailingBackslashFromPath@Utils@UnionFs@@YAXAEAU_UNICODE_STRING@@PEBG@Z; UnionFs::Utils::StripTrailingBackslashFromPath(_UNICODE_STRING &,ushort const *)
0x140069862  jmp     short loc_140069884
0x140069864  movzx   edx, word ptr [rbx]
0x140069867  cmp     edx, 2
0x14006986a  jbe     short loc_140069884
0x14006986c  mov     rax, [rbx+8]
0x140069870  mov     ecx, edx
0x140069872  shr     rcx, 1
0x140069875  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14006987b  jnz     short loc_140069884
0x14006987d  sub     dx, 2
0x140069881  mov     [rbx], dx
0x140069884  xor     eax, eax
0x140069886  add     rsp, 38h
0x14006988a  pop     r14
0x14006988c  pop     r12
0x14006988e  pop     rdi
0x14006988f  pop     rsi
0x140069890  pop     rbp
0x140069891  pop     rbx
0x140069892  retn
```
