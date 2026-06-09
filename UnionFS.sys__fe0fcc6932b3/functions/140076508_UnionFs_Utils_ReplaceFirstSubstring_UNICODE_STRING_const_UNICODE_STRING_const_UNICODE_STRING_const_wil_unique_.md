# UnionFs::Utils::ReplaceFirstSubstring(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)

- ea: `0x140076508`
- end: `0x140076859`
- name: `?ReplaceFirstSubstring@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@00AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z`
- size: `849`
- prototype: `__int64 __usercall@<rax>(UnionFs::Rtl *this@<rcx>, struct _UNICODE_STRING *@<rdx>, PCUNICODE_STRING Source@<r8>, int)`
- caller_count: `6`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140025208`
- `0x140040110`
- `0x140044074`
- `0x140044d84`
- `0x140044e54`
- `0x140076fa4`

## callees

- `0x140056bd0`
- `0x140056c44`
- `0x14006e114`
- `0x140076508`
- `0x140079f68`
- `0x14007a02c`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400766ca`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140076710`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007675b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400767f7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400766ca`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140076710`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007675b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400767f7`

## string_xrefs

- `0x1400765a4`: `UnionFs::Utils::ReplaceFirstSubstring`
- `0x14007661d`: `UnionFs::Utils::ReplaceFirstSubstring`
- `0x140076683`: `UnionFs::Utils::ReplaceFirstSubstring`
- `0x1400766f1`: `UnionFs::Utils::ReplaceFirstSubstring`
- `0x140076722`: `API: Copying substring into destination`
- `0x1400766dc`: `API: Copying prefix into destination`
- `0x14007676d`: `API: Copying whack into destination`
- `0x140076809`: `API: Copying suffix into destination`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::ReplaceFirstSubstring(
        PWSTR *this,
        struct _UNICODE_STRING *a2,
        PCUNICODE_STRING Source,
        struct _UNICODE_STRING *a4,
        int a5)
{
  unsigned int Length; // edx
  bool v8; // r12
  PCUNICODE_STRING v9; // rsi
  unsigned __int64 v10; // rcx
  PWSTR Buffer; // rax
  bool v12; // di
  unsigned __int16 *UnicodeSubstring; // r13
  NTSTATUS appended; // ebx
  PWSTR v15; // rbx
  __int64 v16; // rdx
  unsigned __int16 v17; // ax
  __int64 v18; // r8
  struct _UNICODE_STRING *v19; // rdx
  __int64 v20; // r13
  const char *v21; // rax
  __int64 v22; // r8
  USHORT v23; // dx
  __int16 v24; // cx
  __int64 v25; // rdx
  __int16 v26; // ax
  USHORT v27; // cx
  PWSTR v28; // rax
  struct _UNICODE_STRING v29; // xmm1
  const char *v31; // [rsp+28h] [rbp-48h]
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-40h] BYREF
  UNICODE_STRING Sourcea; // [rsp+40h] [rbp-30h] BYREF
  UNICODE_STRING v34; // [rsp+50h] [rbp-20h] BYREF
  UNICODE_STRING v35; // [rsp+60h] [rbp-10h] BYREF
  int v36; // [rsp+B8h] [rbp+48h] BYREF
  struct _UNICODE_STRING *v37; // [rsp+C8h] [rbp+58h]

  v37 = a4;
  Length = a2->Length;
  v8 = 0;
  v9 = Source;
  v10 = (unsigned __int64)Source->Length >> 1;
  Buffer = Source->Buffer;
  if ( a2->Buffer[((unsigned __int64)Length >> 1) - 1] == 92 )
  {
    v12 = Buffer[v10 - 1] != 92;
  }
  else
  {
    v12 = 0;
    if ( Buffer[v10 - 1] == 92 )
      v8 = *(_WORD *)this != (unsigned __int16)Length;
  }
  LOBYTE(Source) = 1;
  UnicodeSubstring = UnionFs::Rtl::FindUnicodeSubstring((UnionFs::Rtl *)this, a2, Source, (unsigned __int8)a4);
  if ( UnicodeSubstring )
  {
    v15 = this[1];
    v16 = *(unsigned __int16 *)this;
    if ( v9->Length != a2->Length )
    {
      if ( (unsigned __int16)v16 < a2->Length )
        MicrosoftTelemetryAssertTriggeredMsgKM("Source.Length >= OldSubstr.Length");
      if ( *(_WORD *)this < a2->Length )
      {
        v18 = 0xD800210773LL;
        goto LABEL_13;
      }
      v17 = *(_WORD *)this - a2->Length;
      v16 = v17;
      LOWORD(v16) = v9->Length + v17;
      if ( (unsigned __int16)v16 < v17 )
      {
        v18 = 0xD900210778LL;
LABEL_13:
        appended = -1073741675;
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)0xC0000095LL,
          a5,
          (struct UnionFs::StackEventTracer *)v18,
          (unsigned __int64)"UnionFs::Utils::ReplaceFirstSubstring",
          "API: Arithmetic error",
          v31);
        return (unsigned int)appended;
      }
    }
    if ( v12 )
    {
      LOWORD(v16) = v16 + 2;
    }
    else if ( v8 )
    {
      LOWORD(v16) = v16 - 2;
    }
    FsFltWil::MakeUniqueUnicodeString(&Destination, v16, 1279685446);
    if ( !Destination.Buffer )
    {
      appended = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        a5,
        (struct UnionFs::StackEventTracer *)0xDA00210790LL,
        (unsigned __int64)"UnionFs::Utils::ReplaceFirstSubstring",
        "ORIGIN: Allocating destination string",
        v31);
LABEL_36:
      FsFltWil::Details::FreeUnicodeString(&Destination, v19);
      return (unsigned int)appended;
    }
    Sourcea = 0;
    v20 = UnicodeSubstring - v15;
    Sourcea.MaximumLength = 2 * v20;
    Sourcea.Length = 2 * v20;
    Sourcea.Buffer = this[1];
    appended = RtlAppendUnicodeStringToString(&Destination, &Sourcea);
    if ( appended >= 0 )
    {
      appended = RtlAppendUnicodeStringToString(&Destination, v9);
      if ( appended >= 0 )
      {
        if ( v12 )
        {
          v36 = *(_DWORD *)L"\\";
          *(_QWORD *)&v34.Length = 262146;
          v34.Buffer = (PWSTR)&v36;
          appended = RtlAppendUnicodeStringToString(&Destination, &v34);
          if ( appended < 0 )
          {
            v21 = "API: Copying whack into destination";
            v22 = 0xDD002107ABLL;
            goto LABEL_23;
          }
        }
        else if ( v8 )
        {
          v23 = Destination.Length;
          if ( Destination.Buffer[((unsigned __int64)Destination.Length >> 1) - 1] != 92 )
          {
            MicrosoftTelemetryAssertTriggeredMsgKM("We expect a terminal \\ here.");
            v23 = Destination.Length;
          }
          Destination.Length = v23 - 2;
        }
        v24 = *(_WORD *)this;
        v25 = (unsigned __int16)(v20 + (a2->Length >> 1));
        v26 = v20 + (a2->Length >> 1);
        v35 = 0;
        v27 = v24 - 2 * v26;
        v28 = this[1];
        v35.MaximumLength = v27;
        v35.Length = v27;
        v35.Buffer = &v28[v25];
        appended = RtlAppendUnicodeStringToString(&Destination, &v35);
        if ( appended >= 0 )
        {
          appended = 0;
          v29 = *v37;
          *v37 = Destination;
          Destination = v29;
          goto LABEL_36;
        }
        v21 = "API: Copying suffix into destination";
        v22 = 0xDE002107BELL;
        goto LABEL_23;
      }
      v21 = "API: Copying substring into destination";
      v22 = 0xDC002107A1LL;
    }
    else
    {
      v21 = "API: Copying prefix into destination";
      v22 = 0xDB0021079BLL;
    }
LABEL_23:
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)appended,
      a5,
      (struct UnionFs::StackEventTracer *)v22,
      (unsigned __int64)"UnionFs::Utils::ReplaceFirstSubstring",
      v21,
      v31);
    goto LABEL_36;
  }
  appended = -1073741275;
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)0xC0000225LL,
    a5,
    (struct UnionFs::StackEventTracer *)0xD70021075FLL,
    (unsigned __int64)"UnionFs::Utils::ReplaceFirstSubstring",
    "ORIGIN: Could not find old substring in source.",
    v31);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140076508  mov     [rsp-38h+arg_0], rbx
0x14007650d  mov     [rsp-38h+arg_18], r9
0x140076512  push    rbp
0x140076513  push    rsi
0x140076514  push    rdi
0x140076515  push    r12
0x140076517  push    r13
0x140076519  push    r14
0x14007651b  push    r15
0x14007651d  mov     rbp, rsp
0x140076520  sub     rsp, 70h
0x140076524  mov     r15, rdx
0x140076527  mov     r14, rcx
0x14007652a  movzx   edx, word ptr [rdx]
0x14007652d  xor     r12b, r12b
0x140076530  movzx   ecx, word ptr [r8]
0x140076534  mov     r10d, edx
0x140076537  shr     r10, 1
0x14007653a  mov     rsi, r8
0x14007653d  mov     rax, [r15+8]
0x140076541  shr     rcx, 1
0x140076544  cmp     word ptr [rax+r10*2-2], 5Ch ; '\'
0x14007654b  mov     rax, [r8+8]
0x14007654f  jnz     short loc_140076563
0x140076551  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140076557  jz      short loc_14007655E
0x140076559  mov     dil, 1
0x14007655c  jmp     short loc_140076577
0x14007655e  xor     dil, dil
0x140076561  jmp     short loc_140076577
0x140076563  xor     dil, dil
0x140076566  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14007656c  jnz     short loc_140076577
0x14007656e  cmp     [r14], dx
0x140076572  jz      short loc_140076577
0x140076574  mov     r12b, 1
0x140076577  mov     r8b, 1; struct _UNICODE_STRING *
0x14007657a  mov     rdx, r15; struct _UNICODE_STRING *
0x14007657d  mov     rcx, r14; this
0x140076580  call    ?FindUnicodeSubstring@Rtl@UnionFs@@YAPEAGPEBU_UNICODE_STRING@@0E@Z; UnionFs::Rtl::FindUnicodeSubstring(_UNICODE_STRING const *,_UNICODE_STRING const *,uchar)
0x140076585  mov     r13, rax
0x140076588  test    rax, rax
0x14007658b  jnz     short loc_1400765BF
0x14007658d  mov     rdx, qword ptr [rbp+arg_20]; int
0x140076591  lea     rax, aOriginCouldNot_1; "ORIGIN: Could not find old substring in"...
0x140076598  mov     ebx, 0C0000225h
0x14007659d  mov     [rsp+70h+var_50], rax; char *
0x1400765a2  mov     ecx, ebx; this
0x1400765a4  lea     r9, aUnionfsUtilsRe; "UnionFs::Utils::ReplaceFirstSubstring"
0x1400765ab  mov     r8, 0D70021075Fh; struct UnionFs::StackEventTracer *
0x1400765b5  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400765ba  jmp     loc_14007683E
0x1400765bf  movzx   eax, word ptr [r15]
0x1400765c3  mov     rbx, [r14+8]
0x1400765c7  movzx   edx, word ptr [r14]
0x1400765cb  cmp     [rsi], ax
0x1400765ce  jz      short loc_14007663A
0x1400765d0  cmp     dx, ax
0x1400765d3  jnb     short loc_1400765E1
0x1400765d5  lea     rcx, aSourceLengthOl; "Source.Length >= OldSubstr.Length"
0x1400765dc  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400765e1  movzx   ecx, word ptr [r15]
0x1400765e5  movzx   eax, word ptr [r14]
0x1400765e9  cmp     ax, cx
0x1400765ec  jb      short loc_14007662E
0x1400765ee  sub     ax, cx
0x1400765f1  movzx   edx, ax
0x1400765f4  add     dx, [rsi]
0x1400765f7  cmp     dx, ax
0x1400765fa  jnb     short loc_14007663A
0x1400765fc  mov     r8, 0D900210778h; struct UnionFs::StackEventTracer *
0x140076606  mov     rdx, qword ptr [rbp+arg_20]; int
0x14007660a  lea     rax, aApiArithmeticE; "API: Arithmetic error"
0x140076611  mov     ebx, 0C0000095h
0x140076616  mov     [rsp+70h+var_50], rax; char *
0x14007661b  mov     ecx, ebx; this
0x14007661d  lea     r9, aUnionfsUtilsRe; "UnionFs::Utils::ReplaceFirstSubstring"
0x140076624  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076629  jmp     loc_14007683E
0x14007662e  mov     r8, 0D800210773h
0x140076638  jmp     short loc_140076606
0x14007663a  mov     ecx, 2
0x14007663f  mov     eax, 0FFFEh
0x140076644  test    dil, dil
0x140076647  jz      short loc_14007664E
0x140076649  add     dx, cx
0x14007664c  jmp     short loc_140076656
0x14007664e  test    r12b, r12b
0x140076651  jz      short loc_140076656
0x140076653  add     dx, ax
0x140076656  mov     r8d, 4C467346h
0x14007665c  lea     rcx, [rbp+Destination]
0x140076660  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x140076665  cmp     [rbp+Destination.Buffer], 0
0x14007666a  jnz     short loc_14007669E
0x14007666c  mov     rdx, qword ptr [rbp+arg_20]; int
0x140076670  lea     rax, aOriginAllocati_24; "ORIGIN: Allocating destination string"
0x140076677  mov     ebx, 0C000009Ah
0x14007667c  mov     [rsp+70h+var_50], rax; char *
0x140076681  mov     ecx, ebx; this
0x140076683  lea     r9, aUnionfsUtilsRe; "UnionFs::Utils::ReplaceFirstSubstring"
0x14007668a  mov     r8, 0DA00210790h; struct UnionFs::StackEventTracer *
0x140076694  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076699  jmp     loc_140076835
0x14007669e  xorps   xmm0, xmm0
0x1400766a1  lea     rdx, [rbp+Source]; Source
0x1400766a5  movups  xmmword ptr [rbp+Source.Length], xmm0
0x1400766a9  sub     r13, rbx
0x1400766ac  lea     rcx, [rbp+Destination]; Destination
0x1400766b0  sar     r13, 1
0x1400766b3  movzx   eax, r13w
0x1400766b7  add     ax, ax
0x1400766ba  mov     [rbp+Source.MaximumLength], ax
0x1400766be  mov     [rbp+Source.Length], ax
0x1400766c2  mov     rax, [r14+8]
0x1400766c6  mov     [rbp+Source.Buffer], rax
0x1400766ca  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400766d1  nop     dword ptr [rax+rax+00h]
0x1400766d6  mov     ebx, eax
0x1400766d8  test    eax, eax
0x1400766da  jns     short loc_140076709
0x1400766dc  lea     rax, aApiCopyingPref_0; "API: Copying prefix into destination"
0x1400766e3  mov     r8, 0DB0021079Bh; struct UnionFs::StackEventTracer *
0x1400766ed  mov     rdx, qword ptr [rbp+arg_20]; int
0x1400766f1  lea     r9, aUnionfsUtilsRe; "UnionFs::Utils::ReplaceFirstSubstring"
0x1400766f8  mov     ecx, ebx; this
0x1400766fa  mov     [rsp+70h+var_50], rax; char *
0x1400766ff  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076704  jmp     loc_140076835
0x140076709  mov     rdx, rsi; Source
0x14007670c  lea     rcx, [rbp+Destination]; Destination
0x140076710  call    cs:__imp_RtlAppendUnicodeStringToString
0x140076717  nop     dword ptr [rax+rax+00h]
0x14007671c  mov     ebx, eax
0x14007671e  test    eax, eax
0x140076720  jns     short loc_140076735
0x140076722  lea     rax, aApiCopyingSubs; "API: Copying substring into destination"
0x140076729  mov     r8, 0DC002107A1h
0x140076733  jmp     short loc_1400766ED
0x140076735  test    dil, dil
0x140076738  jz      short loc_140076783
0x14007673a  mov     eax, dword ptr cs:Source; "\\"
0x140076740  lea     rdx, [rbp+var_20]; Source
0x140076744  mov     [rbp+arg_8], eax
0x140076747  lea     rcx, [rbp+Destination]; Destination
0x14007674b  lea     rax, [rbp+arg_8]
0x14007674f  mov     qword ptr [rbp+var_20.Length], 40002h
0x140076757  mov     [rbp+var_20.Buffer], rax
0x14007675b  call    cs:__imp_RtlAppendUnicodeStringToString
0x140076762  nop     dword ptr [rax+rax+00h]
0x140076767  mov     ebx, eax
0x140076769  test    eax, eax
0x14007676b  jns     short loc_1400767B9
0x14007676d  lea     rax, aApiCopyingWhac; "API: Copying whack into destination"
0x140076774  mov     r8, 0DD002107ABh
0x14007677e  jmp     loc_1400766ED
0x140076783  test    r12b, r12b
0x140076786  jz      short loc_1400767B9
0x140076788  movzx   edx, [rbp+Destination.Length]
0x14007678c  mov     rax, [rbp+Destination.Buffer]
0x140076790  mov     ecx, edx
0x140076792  shr     rcx, 1
0x140076795  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14007679b  jz      short loc_1400767AD
0x14007679d  lea     rcx, aWeExpectATermi; "We expect a terminal \\ here."
0x1400767a4  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400767a9  movzx   edx, [rbp+Destination.Length]
0x1400767ad  mov     eax, 0FFFEh
0x1400767b2  add     dx, ax
0x1400767b5  mov     [rbp+Destination.Length], dx
0x1400767b9  movzx   eax, word ptr [r15]
0x1400767bd  xorps   xmm0, xmm0
0x1400767c0  movzx   ecx, word ptr [r14]
0x1400767c4  shr     ax, 1
0x1400767c7  add     ax, r13w
0x1400767cb  movzx   edx, ax
0x1400767ce  movzx   eax, dx
0x1400767d1  movups  xmmword ptr [rbp+var_10.Length], xmm0
0x1400767d5  add     ax, ax
0x1400767d8  sub     cx, ax
0x1400767db  mov     rax, [r14+8]
0x1400767df  mov     [rbp+var_10.MaximumLength], cx
0x1400767e3  mov     [rbp+var_10.Length], cx
0x1400767e7  lea     rcx, [rax+rdx*2]
0x1400767eb  mov     [rbp+var_10.Buffer], rcx
0x1400767ef  lea     rdx, [rbp+var_10]; Source
0x1400767f3  lea     rcx, [rbp+Destination]; Destination
0x1400767f7  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400767fe  nop     dword ptr [rax+rax+00h]
0x140076803  mov     ebx, eax
0x140076805  test    eax, eax
0x140076807  jns     short loc_14007681F
0x140076809  lea     rax, aApiCopyingSuff_0; "API: Copying suffix into destination"
0x140076810  mov     r8, 0DE002107BEh
0x14007681a  jmp     loc_1400766ED
0x14007681f  mov     rax, [rbp+arg_18]
0x140076823  xor     ebx, ebx
0x140076825  movaps  xmm0, xmmword ptr [rbp+Destination.Length]
0x140076829  movups  xmm1, xmmword ptr [rax]
0x14007682c  movdqu  xmmword ptr [rax], xmm0
0x140076830  movdqa  xmmword ptr [rbp+Destination.Length], xmm1
0x140076835  lea     rcx, [rbp+Destination]; UnicodeString
0x140076839  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14007683e  mov     eax, ebx
0x140076840  mov     rbx, [rsp+70h+arg_0]
0x140076848  add     rsp, 70h
0x14007684c  pop     r15
0x14007684e  pop     r14
0x140076850  pop     r13
0x140076852  pop     r12
0x140076854  pop     rdi
0x140076855  pop     rsi
0x140076856  pop     rbp
0x140076857  retn
```
