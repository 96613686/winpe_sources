# UnionFs::Utils::AppendPath(_UNICODE_STRING &,_UNICODE_STRING const &,UnionFs::StackEventTracer &,ushort *)

- ea: `0x140069498`
- end: `0x1400696a4`
- name: `?AppendPath@Utils@UnionFs@@YAJAEAU_UNICODE_STRING@@AEBU3@AEAVStackEventTracer@2@PEAG@Z`
- size: `524`
- prototype: `__int64 __fastcall(UnionFs::Utils *__hidden this, PCUNICODE_STRING Source, const struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400441b4`
- `0x14004f988`

## callees

- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140069498`
- `0x14006a74c`
- `0x14007843c`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400695d6`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400695d6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006961d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006961d`

## string_xrefs

- `0x1400694e6`: `PUSH: ComputeCombinedPathLength`
- `0x14006962f`: `Couldn't append name component`
- `0x1400694f7`: `UnionFs::Utils::AppendPath`
- `0x140069552`: `UnionFs::Utils::AppendPath`
- `0x14006964c`: `UnionFs::Utils::AppendPath`
- `0x14006960b`: `((((Root.Length >= sizeof(WCHAR)) && (Root.Buffer[(Root.Length / sizeof(WCHAR)) - 1] == L'\\'))) && (RelativePath.Buffer[0] != L'\\')) || ((((Root.Length < sizeof(WCHAR)) || (Root.Buffer[(Root.Length / sizeof(WCHAR)) - 1] != L'\\'))) && (RelativePath.Buffer[0] == L'\\'))`

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
0x140069498  push    rbx
0x14006949a  push    rbp
0x14006949b  push    rsi
0x14006949c  push    rdi
0x14006949d  push    r12
0x14006949f  push    r14
0x1400694a1  sub     rsp, 38h
0x1400694a5  mov     rbx, rcx
0x1400694a8  xor     r12d, r12d
0x1400694ab  movzx   ecx, word ptr [rcx]
0x1400694ae  mov     rsi, r9
0x1400694b1  mov     rbp, r8
0x1400694b4  mov     r14, rdx
0x1400694b7  cmp     cx, 2
0x1400694bb  jnz     short loc_1400694CA
0x1400694bd  mov     rax, [rbx+8]
0x1400694c1  cmp     word ptr [rax], 5Ch ; '\'
0x1400694c5  jnz     short loc_1400694CA
0x1400694c7  mov     ecx, r12d; this
0x1400694ca  movzx   edx, word ptr [rdx]; unsigned __int16
0x1400694cd  lea     r8, [rsp+68h+arg_0]; unsigned __int16
0x1400694d2  mov     r9, rbp; unsigned __int16 *
0x1400694d5  mov     [rsp+68h+arg_0], r12w
0x1400694db  call    ?ComputeCombinedPathLength@Utils@UnionFs@@YAJGGPEAGAEAVStackEventTracer@2@@Z; UnionFs::Utils::ComputeCombinedPathLength(ushort,ushort,ushort *,UnionFs::StackEventTracer &)
0x1400694e0  mov     edi, eax
0x1400694e2  test    eax, eax
0x1400694e4  jns     short loc_140069514
0x1400694e6  lea     rax, aPushComputecom_0; "PUSH: ComputeCombinedPathLength"
0x1400694ed  mov     r8, 274002104E4h; struct UnionFs::StackEventTracer *
0x1400694f7  lea     r9, aUnionfsUtilsAp; "UnionFs::Utils::AppendPath"
0x1400694fe  mov     [rsp+68h+var_48], rax; char *
0x140069503  mov     rdx, rbp; int
0x140069506  mov     ecx, edi; this
0x140069508  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006950d  mov     eax, edi
0x14006950f  jmp     loc_140069696
0x140069514  mov     dl, r12b
0x140069517  test    rsi, rsi
0x14006951a  jz      short loc_140069532
0x14006951c  movzx   eax, word ptr [rsi]
0x14006951f  cmp     [rbx], ax
0x140069522  jnz     short loc_140069532
0x140069524  movzx   ecx, [rsp+68h+arg_0]
0x140069529  mov     edx, 1
0x14006952e  sub     ecx, edx
0x140069530  jmp     short loc_140069537
0x140069532  movzx   ecx, [rsp+68h+arg_0]
0x140069537  movzx   eax, word ptr [rbx+2]
0x14006953b  cmp     eax, ecx
0x14006953d  jge     short loc_140069572
0x14006953f  lea     rax, aOriginRootTooS; "ORIGIN: Root too small"
0x140069546  mov     ebx, 0C0000023h
0x14006954b  mov     ecx, ebx; this
0x14006954d  mov     [rsp+68h+var_48], rax; char *
0x140069552  lea     r9, aUnionfsUtilsAp; "UnionFs::Utils::AppendPath"
0x140069559  mov     r8, 275002104F1h; struct UnionFs::StackEventTracer *
0x140069563  mov     rdx, rbp; int
0x140069566  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006956b  mov     eax, ebx
0x14006956d  jmp     loc_140069696
0x140069572  movzx   ecx, word ptr [r14]
0x140069576  test    cx, cx
0x140069579  jz      loc_140069674
0x14006957f  mov     rax, [r14+8]
0x140069583  movzx   r8d, word ptr [rax]
0x140069587  cmp     r8w, 5Ch ; '\'
0x14006958c  jnz     short loc_14006959C
0x14006958e  cmp     cx, 2
0x140069592  jnz     short loc_14006959C
0x140069594  test    dl, dl
0x140069596  jz      loc_140069674
0x14006959c  movzx   ecx, word ptr [rbx]
0x14006959f  mov     edx, ecx
0x1400695a1  shr     rdx, 1
0x1400695a4  cmp     ecx, 2
0x1400695a7  jb      short loc_1400695C5
0x1400695a9  mov     rax, [rbx+8]
0x1400695ad  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x1400695b3  jnz     short loc_1400695C5
0x1400695b5  cmp     r8w, 5Ch ; '\'
0x1400695ba  jnz     short loc_1400695EF
0x1400695bc  sub     cx, 2
0x1400695c0  mov     [rbx], cx
0x1400695c3  jmp     short loc_140069617
0x1400695c5  cmp     r8w, 5Ch ; '\'
0x1400695ca  jz      short loc_1400695EA
0x1400695cc  lea     rdx, Source; "\\"
0x1400695d3  mov     rcx, rbx; Destination
0x1400695d6  call    cs:__imp_RtlAppendUnicodeToString
0x1400695dd  nop     dword ptr [rax+rax+00h]
0x1400695e2  mov     edi, eax
0x1400695e4  test    eax, eax
0x1400695e6  js      short loc_14006962F
0x1400695e8  jmp     short loc_140069617
0x1400695ea  cmp     ecx, 2
0x1400695ed  jb      short loc_140069617
0x1400695ef  mov     rax, [rbx+8]
0x1400695f3  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x1400695f9  jnz     short loc_140069604
0x1400695fb  cmp     r8w, 5Ch ; '\'
0x140069600  jnz     short loc_140069617
0x140069602  jmp     short loc_14006960B
0x140069604  cmp     r8w, 5Ch ; '\'
0x140069609  jz      short loc_140069617
0x14006960b  lea     rcx, aRootLengthSize; "((((Root.Length >= sizeof(WCHAR)) && (R"...
0x140069612  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140069617  mov     rdx, r14; Source
0x14006961a  mov     rcx, rbx; Destination
0x14006961d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140069624  nop     dword ptr [rax+rax+00h]
0x140069629  mov     edi, eax
0x14006962b  test    eax, eax
0x14006962d  jns     short loc_140069667
0x14006962f  lea     rcx, aCouldnTAppendN; "Couldn't append name component"
0x140069636  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14006963b  lea     rax, aApiConstructin; "API: Constructing Root"
0x140069642  mov     r8, 2760021052Bh; struct UnionFs::StackEventTracer *
0x14006964c  lea     r9, aUnionfsUtilsAp; "UnionFs::Utils::AppendPath"
0x140069653  mov     [rsp+68h+var_48], rax; char *
0x140069658  mov     rdx, rbp; int
0x14006965b  mov     ecx, edi; this
0x14006965d  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140069662  jmp     loc_14006950D
0x140069667  mov     rdx, rsi; struct _UNICODE_STRING *
0x14006966a  mov     rcx, rbx; this
0x14006966d  call    ?StripTrailingBackslashFromPath@Utils@UnionFs@@YAXAEAU_UNICODE_STRING@@PEBG@Z; UnionFs::Utils::StripTrailingBackslashFromPath(_UNICODE_STRING &,ushort const *)
0x140069672  jmp     short loc_140069694
0x140069674  movzx   edx, word ptr [rbx]
0x140069677  cmp     edx, 2
0x14006967a  jbe     short loc_140069694
0x14006967c  mov     rax, [rbx+8]
0x140069680  mov     ecx, edx
0x140069682  shr     rcx, 1
0x140069685  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14006968b  jnz     short loc_140069694
0x14006968d  sub     dx, 2
0x140069691  mov     [rbx], dx
0x140069694  xor     eax, eax
0x140069696  add     rsp, 38h
0x14006969a  pop     r14
0x14006969c  pop     r12
0x14006969e  pop     rdi
0x14006969f  pop     rsi
0x1400696a0  pop     rbp
0x1400696a1  pop     rbx
0x1400696a2  retn
```
