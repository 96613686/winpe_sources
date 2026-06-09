# UnionFs::Utils::PrependVolumeName(_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)

- ea: `0x1400751dc`
- end: `0x14007544e`
- name: `?PrependVolumeName@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z`
- size: `626`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, PCUNICODE_STRING, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140075454`

## callees

- `0x140056bd0`
- `0x140056c44`
- `0x1400751dc`
- `0x140079f68`
- `0x14007a02c`
- `0x14007b2b0`
- `0x14007bc40`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140075271`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007529e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140075271`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007529e`

## string_xrefs

- `0x140075414`: `API: Getting temp string length`
- `0x140075209`: `Caller attempting to use zero-length component`
- `0x140075283`: `API: Appending volume name to temp string`
- `0x14007523b`: `ORIGIN: Allocating temp string`
- `0x140075401`: `API: Copying volume name to path from root`
- `0x1400752b0`: `API: Appending path to temp string`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::PrependVolumeName(PCUNICODE_STRING Source, struct _UNICODE_STRING *a2, int a3)
{
  USHORT Length; // cx
  USHORT v7; // ax
  USHORT v8; // bp
  NTSTATUS appended; // ebx
  struct _UNICODE_STRING *v10; // rdx
  const char *v11; // rax
  __int64 v12; // r8
  struct _UNICODE_STRING *v13; // rdx
  struct _UNICODE_STRING v14; // xmm0
  unsigned __int64 MaximumLength; // rcx
  USHORT v16; // dx
  PWSTR v17; // r10
  unsigned __int64 v18; // rdx
  USHORT v19; // ax
  PWSTR Buffer; // r8
  unsigned __int64 v21; // rdx
  bool v22; // zf
  unsigned __int64 v23; // r9
  __int16 v24; // cx
  USHORT v25; // cx
  const char *v27; // rax
  __int64 v28; // r8
  const char *v29; // [rsp+28h] [rbp-40h]
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-38h] BYREF

  Length = a2->Length;
  v7 = Source->Length;
  v8 = a2->Length + Source->Length;
  if ( (unsigned __int16)(a2->Length + v7) < v7 )
  {
    v27 = "API: Getting temp string length";
    v28 = 0x35800210301LL;
    appended = -1073741675;
    goto LABEL_40;
  }
  if ( (unsigned __int16)(Length + v7) <= v7 || v8 <= Length )
    MicrosoftTelemetryAssertTriggeredMsgKM("Caller attempting to use zero-length component");
  if ( a2->MaximumLength >= v8 )
  {
    memmove((char *)a2->Buffer + Source->Length, a2->Buffer, a2->Length);
    MaximumLength = a2->MaximumLength;
    v16 = a2->Length;
    if ( ((a2->Length | (unsigned __int16)MaximumLength) & 1) != 0
      || v16 > (unsigned __int16)MaximumLength
      || (_WORD)MaximumLength == 0xFFFF
      || (v17 = a2->Buffer) == 0 && __PAIR32__(MaximumLength, v16) )
    {
      appended = -1073741811;
    }
    else
    {
      v18 = Source->Length;
      if ( (v18 & 1) != 0
        || (v19 = Source->MaximumLength, (v19 & 1) != 0)
        || (unsigned __int16)v18 > v19
        || v19 == 0xFFFF
        || (Buffer = Source->Buffer) == 0 && ((_WORD)v18 || v19) )
      {
        v24 = 0;
        appended = -1073741811;
      }
      else
      {
        v21 = v18 >> 1;
        v23 = MaximumLength >> 1;
        v22 = MaximumLength >> 1 == 0;
        appended = 0;
        v24 = 0;
        if ( v22 )
        {
LABEL_30:
          if ( v21 )
            appended = -2147483643;
        }
        else
        {
          while ( v21 )
          {
            --v21;
            *v17++ = *Buffer++;
            ++v24;
            if ( !--v23 )
              goto LABEL_30;
          }
        }
      }
      v25 = 2 * v24;
      a2->Length = v25;
      if ( appended >= 0 )
      {
        a2->Buffer[(unsigned __int64)v25 >> 1] = 92;
        a2->Length = v8;
        return 0;
      }
    }
    v27 = "API: Copying volume name to path from root";
    v28 = 0x35C00210329LL;
LABEL_40:
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)appended,
      a3,
      (struct UnionFs::StackEventTracer *)v28,
      (unsigned __int64)"UnionFs::Utils::PrependVolumeName",
      v27,
      v29);
    return (unsigned int)appended;
  }
  FsFltWil::MakeUniqueUnicodeString(&Destination, v8, 1279685446);
  if ( Destination.Buffer )
  {
    appended = RtlAppendUnicodeStringToString(&Destination, Source);
    if ( appended < 0 )
    {
      v11 = "API: Appending volume name to temp string";
      v12 = 0x35A00210314LL;
LABEL_12:
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)appended,
        a3,
        (struct UnionFs::StackEventTracer *)v12,
        (unsigned __int64)"UnionFs::Utils::PrependVolumeName",
        v11,
        v29);
      goto LABEL_13;
    }
    appended = RtlAppendUnicodeStringToString(&Destination, a2);
    if ( appended < 0 )
    {
      v11 = "API: Appending path to temp string";
      v12 = 0x35B00210319LL;
      goto LABEL_12;
    }
    v14 = Destination;
    Destination = *a2;
    *a2 = v14;
    FsFltWil::Details::FreeUnicodeString(&Destination, v13);
    return 0;
  }
  appended = -1073741670;
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)0xC000009ALL,
    a3,
    (struct UnionFs::StackEventTracer *)0x3590021030FLL,
    (unsigned __int64)"UnionFs::Utils::PrependVolumeName",
    "ORIGIN: Allocating temp string",
    v29);
LABEL_13:
  FsFltWil::Details::FreeUnicodeString(&Destination, v10);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1400751dc  push    rbx
0x1400751de  push    rbp
0x1400751df  push    rsi
0x1400751e0  push    rdi
0x1400751e1  push    r14
0x1400751e3  sub     rsp, 40h
0x1400751e7  mov     rbx, rcx
0x1400751ea  mov     r14, r8
0x1400751ed  movzx   ecx, word ptr [rdx]
0x1400751f0  mov     rsi, rdx
0x1400751f3  movzx   eax, word ptr [rbx]
0x1400751f6  lea     ebp, [rcx+rax]
0x1400751f9  cmp     bp, ax
0x1400751fc  jb      loc_140075414
0x140075202  jbe     short loc_140075209
0x140075204  cmp     bp, cx
0x140075207  ja      short loc_140075215
0x140075209  lea     rcx, aCallerAttempti; "Caller attempting to use zero-length co"...
0x140075210  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140075215  cmp     [rsi+2], bp
0x140075219  jnb     loc_140075307
0x14007521f  mov     r8d, 4C467346h
0x140075225  lea     rcx, [rsp+68h+Destination]
0x14007522a  movzx   edx, bp
0x14007522d  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x140075232  xor     edi, edi
0x140075234  cmp     [rsp+68h+Destination.Buffer], rdi
0x140075239  jnz     short loc_140075269
0x14007523b  lea     rax, aOriginAllocati_25; "ORIGIN: Allocating temp string"
0x140075242  mov     ebx, 0C000009Ah
0x140075247  mov     ecx, ebx; this
0x140075249  mov     [rsp+68h+var_48], rax; char *
0x14007524e  lea     r9, aUnionfsUtilsPr_0; "UnionFs::Utils::PrependVolumeName"
0x140075255  mov     r8, 3590021030Fh; struct UnionFs::StackEventTracer *
0x14007525f  mov     rdx, r14; int
0x140075262  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075267  jmp     short loc_1400752D7
0x140075269  mov     rdx, rbx; Source
0x14007526c  lea     rcx, [rsp+68h+Destination]; Destination
0x140075271  call    cs:__imp_RtlAppendUnicodeStringToString
0x140075278  nop     dword ptr [rax+rax+00h]
0x14007527d  mov     ebx, eax
0x14007527f  test    eax, eax
0x140075281  jns     short loc_140075296
0x140075283  lea     rax, aApiAppendingVo_0; "API: Appending volume name to temp stri"...
0x14007528a  mov     r8, 35A00210314h
0x140075294  jmp     short loc_1400752C1
0x140075296  mov     rdx, rsi; Source
0x140075299  lea     rcx, [rsp+68h+Destination]; Destination
0x14007529e  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400752a5  nop     dword ptr [rax+rax+00h]
0x1400752aa  mov     ebx, eax
0x1400752ac  test    eax, eax
0x1400752ae  jns     short loc_1400752E6
0x1400752b0  lea     rax, aApiAppendingPa; "API: Appending path to temp string"
0x1400752b7  mov     r8, 35B00210319h; struct UnionFs::StackEventTracer *
0x1400752c1  lea     r9, aUnionfsUtilsPr_0; "UnionFs::Utils::PrependVolumeName"
0x1400752c8  mov     [rsp+68h+var_48], rax; char *
0x1400752cd  mov     rdx, r14; int
0x1400752d0  mov     ecx, ebx; this
0x1400752d2  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400752d7  lea     rcx, [rsp+68h+Destination]; UnicodeString
0x1400752dc  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400752e1  jmp     loc_140075440
0x1400752e6  movups  xmm1, xmmword ptr [rsi]
0x1400752e9  lea     rcx, [rsp+68h+Destination]; UnicodeString
0x1400752ee  movaps  xmm0, xmmword ptr [rsp+68h+Destination.Length]
0x1400752f3  movdqa  xmmword ptr [rsp+68h+Destination.Length], xmm1
0x1400752f9  movdqu  xmmword ptr [rsi], xmm0
0x1400752fd  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140075302  jmp     loc_1400753F8
0x140075307  mov     rdx, [rsi+8]; Src
0x14007530b  movzx   ecx, word ptr [rbx]
0x14007530e  movzx   r8d, word ptr [rsi]; Size
0x140075312  add     rcx, rdx; void *
0x140075315  call    memmove
0x14007531a  movzx   ecx, word ptr [rsi+2]
0x14007531e  xor     edi, edi
0x140075320  movzx   edx, word ptr [rsi]
0x140075323  movzx   eax, cx
0x140075326  or      ax, dx
0x140075329  bt      ax, di
0x14007532d  jb      loc_1400753FC
0x140075333  cmp     dx, cx
0x140075336  ja      loc_1400753FC
0x14007533c  mov     r8d, 0FFFEh
0x140075342  cmp     cx, r8w
0x140075346  ja      loc_1400753FC
0x14007534c  mov     r10, [rsi+8]
0x140075350  test    r10, r10
0x140075353  jnz     short loc_140075367
0x140075355  test    dx, dx
0x140075358  jnz     loc_1400753FC
0x14007535e  test    cx, cx
0x140075361  jnz     loc_1400753FC
0x140075367  movzx   edx, word ptr [rbx]
0x14007536a  test    dl, 1
0x14007536d  jnz     short loc_1400753D3
0x14007536f  movzx   eax, word ptr [rbx+2]
0x140075373  test    al, 1
0x140075375  jnz     short loc_1400753D3
0x140075377  cmp     dx, ax
0x14007537a  ja      short loc_1400753D3
0x14007537c  cmp     ax, r8w
0x140075380  ja      short loc_1400753D3
0x140075382  mov     r8, [rbx+8]
0x140075386  test    r8, r8
0x140075389  jnz     short loc_140075395
0x14007538b  test    dx, dx
0x14007538e  jnz     short loc_1400753D3
0x140075390  test    ax, ax
0x140075393  jnz     short loc_1400753D3
0x140075395  mov     r9, rcx
0x140075398  shr     rdx, 1
0x14007539b  shr     r9, 1
0x14007539e  mov     ebx, edi
0x1400753a0  mov     rcx, rdi
0x1400753a3  jz      short loc_1400753C6
0x1400753a5  test    rdx, rdx
0x1400753a8  jz      short loc_1400753DB
0x1400753aa  movzx   eax, word ptr [r8]
0x1400753ae  dec     rdx
0x1400753b1  mov     [r10], ax
0x1400753b5  add     r8, 2
0x1400753b9  add     r10, 2
0x1400753bd  inc     rcx
0x1400753c0  sub     r9, 1
0x1400753c4  jnz     short loc_1400753A5
0x1400753c6  test    rdx, rdx
0x1400753c9  mov     eax, 80000005h
0x1400753ce  cmovnz  ebx, eax
0x1400753d1  jmp     short loc_1400753DB
0x1400753d3  mov     rcx, rdi
0x1400753d6  mov     ebx, 0C000000Dh
0x1400753db  add     cx, cx
0x1400753de  mov     [rsi], cx
0x1400753e1  test    ebx, ebx
0x1400753e3  js      short loc_140075401
0x1400753e5  mov     rax, [rsi+8]
0x1400753e9  movzx   ecx, cx
0x1400753ec  shr     rcx, 1
0x1400753ef  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x1400753f5  mov     [rsi], bp
0x1400753f8  xor     eax, eax
0x1400753fa  jmp     short loc_140075442
0x1400753fc  mov     ebx, 0C000000Dh
0x140075401  lea     rax, aApiCopyingVolu; "API: Copying volume name to path from r"...
0x140075408  mov     r8, 35C00210329h
0x140075412  jmp     short loc_14007542A
0x140075414  lea     rax, aApiGettingTemp; "API: Getting temp string length"
0x14007541b  mov     r8, 35800210301h; struct UnionFs::StackEventTracer *
0x140075425  mov     ebx, 0C0000095h
0x14007542a  lea     r9, aUnionfsUtilsPr_0; "UnionFs::Utils::PrependVolumeName"
0x140075431  mov     [rsp+68h+var_48], rax; char *
0x140075436  mov     rdx, r14; int
0x140075439  mov     ecx, ebx; this
0x14007543b  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075440  mov     eax, ebx
0x140075442  add     rsp, 40h
0x140075446  pop     r14
0x140075448  pop     rdi
0x140075449  pop     rsi
0x14007544a  pop     rbp
0x14007544b  pop     rbx
0x14007544c  retn
```
