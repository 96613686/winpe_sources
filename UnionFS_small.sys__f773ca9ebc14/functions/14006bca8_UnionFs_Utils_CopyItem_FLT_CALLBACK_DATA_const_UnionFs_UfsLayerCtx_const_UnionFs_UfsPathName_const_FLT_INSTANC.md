# UnionFs::Utils::CopyItem(_FLT_CALLBACK_DATA const &,UnionFs::UfsLayerCtx const &,UnionFs::UfsPathName const &,_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::Utils::CopyItemParams const &,UnionFs::StackEventTracer &,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> *)

- ea: `0x14006bca8`
- end: `0x14006be60`
- name: `?CopyItem@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBVUfsLayerCtx@2@AEBVUfsPathName@2@AEBU_FLT_INSTANCE@@2AEBUCopyItemParams@12@AEAVStackEventTracer@2@PEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@@Z`
- size: `440`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140013bb0`
- `0x1400156a8`
- `0x140017370`
- `0x14001834c`
- `0x14002e3c8`
- `0x140031c5c`
- `0x1400605e4`

## callees

- `0x140056a50`
- `0x140056afc`
- `0x14006bca8`
- `0x14006c1fc`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x14006bce1`
- `ntoskrnl!IoGetStackLimits` at `0x14006bce1`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14006bdab`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14006bdab`

## string_xrefs

- `0x14006bdfb`: `PUSH: CopyItemPriv`
- `0x14006bddc`: `UnionFs::Utils::CopyItemPrivOnNewStack`
- `0x14006be0c`: `UnionFs::Utils::CopyItemPrivOnNewStack`
- `0x14006be33`: `UnionFs::Utils::CopyItem`
- `0x14006be22`: `PUSH: Copy from layer on new stack`
- `0x14006bd3c`: `PUSH: Copy from layer (direct)`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::CopyItem(
        const struct _UNICODE_STRING *a1,
        __int64 a2,
        __int128 *a3,
        struct _FLT_INSTANCE *a4,
        PCUNICODE_STRING SourceString,
        __int64 *a6,
        struct _FILE_OBJECT *a7,
        void **a8)
{
  unsigned int v12; // ebx
  const char *v13; // rax
  __int64 v14; // r8
  NTSTATUS v15; // eax
  const char *v17; // [rsp+28h] [rbp-71h]
  const char *v18; // [rsp+28h] [rbp-71h]
  unsigned __int64 HighLimit; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int64 LowLimit; // [rsp+48h] [rbp-51h] BYREF
  _QWORD Parameter[9]; // [rsp+50h] [rbp-49h] BYREF
  UnionFs *v22; // [rsp+98h] [rbp-1h]

  HighLimit = 0;
  LowLimit = 0;
  IoGetStackLimits(&LowLimit, &HighLimit);
  if ( (unsigned __int64)&HighLimit - LowLimit <= 0x3000 )
  {
    Parameter[4] = SourceString;
    Parameter[5] = a6;
    Parameter[8] = a8;
    Parameter[6] = 0;
    v22 = 0;
    Parameter[0] = a1;
    Parameter[1] = a2;
    Parameter[2] = a3;
    Parameter[3] = a4;
    Parameter[7] = a7;
    v15 = KeExpandKernelStackAndCalloutEx(UnionFs::Utils::CopyItemPrivCallout, Parameter, 0x6000u, 0, 0);
    v12 = v15;
    if ( v15 == -1073741801 )
    {
      v12 = -1073741670;
    }
    else if ( v15 >= 0 )
    {
      v12 = (unsigned int)v22;
      if ( (int)v22 >= 0 )
        return 0;
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v22,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x8A00211D47LL,
        (unsigned __int64)"UnionFs::Utils::CopyItemPrivOnNewStack",
        "PUSH: CopyItemPriv",
        v17);
LABEL_10:
      v13 = "PUSH: Copy from layer on new stack";
      v14 = 0x28200211D69LL;
      goto LABEL_11;
    }
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)v12,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x8900211D44LL,
      (unsigned __int64)"UnionFs::Utils::CopyItemPrivOnNewStack",
      "API: KeExpandKernelStackAndCalloutEx",
      v17);
    goto LABEL_10;
  }
  v12 = UnionFs::Utils::CopyItemPriv(a1, a2, a3, a4, SourceString, a6, a7, a8);
  if ( (v12 & 0x80000000) != 0 )
  {
    v13 = "PUSH: Copy from layer (direct)";
    v14 = 0x26100211D77LL;
LABEL_11:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)v12,
      (int)a7,
      (struct UnionFs::StackEventTracer *)v14,
      (unsigned __int64)"UnionFs::Utils::CopyItem",
      v13,
      v18);
    return v12;
  }
  return 0;
}

```

## disassembly

```asm
0x14006bca8  push    rbp
0x14006bcaa  push    rbx
0x14006bcab  push    rsi
0x14006bcac  push    rdi
0x14006bcad  push    r14
0x14006bcaf  push    r15
0x14006bcb1  lea     rbp, [rsp-0Fh]
0x14006bcb6  sub     rsp, 0A8h
0x14006bcbd  mov     r14, rdx
0x14006bcc0  mov     [rbp+37h+HighLimit], 0
0x14006bcc8  mov     r15, rcx
0x14006bccb  mov     [rbp+37h+LowLimit], 0
0x14006bcd3  lea     rdx, [rbp+37h+HighLimit]; HighLimit
0x14006bcd7  mov     rbx, r9
0x14006bcda  lea     rcx, [rbp+37h+LowLimit]; LowLimit
0x14006bcde  mov     rsi, r8
0x14006bce1  call    cs:__imp_IoGetStackLimits
0x14006bce8  nop     dword ptr [rax+rax+00h]
0x14006bced  mov     rdi, [rbp+37h+arg_30]
0x14006bcf1  lea     rax, [rbp+37h+HighLimit]
0x14006bcf5  sub     rax, [rbp+37h+LowLimit]
0x14006bcf9  cmp     rax, 3000h
0x14006bcff  jbe     short loc_14006BD52
0x14006bd01  mov     rax, [rbp+37h+arg_38]
0x14006bd05  mov     r9, rbx; int
0x14006bd08  mov     [rsp+0D0h+var_98], rax; __int64
0x14006bd0d  mov     r8, rsi; int
0x14006bd10  mov     rax, [rbp+37h+arg_28]
0x14006bd14  mov     rdx, r14; int
0x14006bd17  mov     [rsp+0D0h+var_A0], rdi; struct _FILE_OBJECT *
0x14006bd1c  mov     rcx, r15; int
0x14006bd1f  mov     [rsp+0D0h+var_A8], rax; __int64
0x14006bd24  mov     rax, [rbp+37h+SourceString]
0x14006bd28  mov     [rsp+0D0h+Context], rax; SourceString
0x14006bd2d  call    ?CopyItemPriv@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBVUfsLayerCtx@2@AEBVUfsPathName@2@AEBU_FLT_INSTANCE@@2AEBUCopyItemParams@12@AEAVStackEventTracer@2@PEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@@Z; UnionFs::Utils::CopyItemPriv(_FLT_CALLBACK_DATA const &,UnionFs::UfsLayerCtx const &,UnionFs::UfsPathName const &,_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::Utils::CopyItemParams const &,UnionFs::StackEventTracer &,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> *)
0x14006bd32  mov     ebx, eax
0x14006bd34  test    eax, eax
0x14006bd36  jns     loc_14006BE4D
0x14006bd3c  lea     rax, aPushCopyFromLa; "PUSH: Copy from layer (direct)"
0x14006bd43  mov     r8, 26100211D77h
0x14006bd4d  jmp     loc_14006BE33
0x14006bd52  mov     rax, [rbp+37h+SourceString]
0x14006bd56  lea     rdx, [rbp+37h+Parameter]; Parameter
0x14006bd5a  mov     [rbp+37h+var_60], rax
0x14006bd5e  lea     rcx, ?CopyItemPrivCallout@Utils@UnionFs@@YAXPEAUUFS_CALLOUT_PARAMETERS@2@@Z; Callout
0x14006bd65  mov     rax, [rbp+37h+arg_28]
0x14006bd69  xor     r9d, r9d; Wait
0x14006bd6c  mov     [rbp+37h+var_58], rax
0x14006bd70  mov     r8d, 6000h; Size
0x14006bd76  mov     rax, [rbp+37h+arg_38]
0x14006bd7a  mov     [rbp+37h+var_40], rax
0x14006bd7e  mov     [rbp+37h+var_50], 0
0x14006bd86  mov     [rbp+37h+var_38], 0
0x14006bd8e  mov     [rbp+37h+Parameter], r15
0x14006bd92  mov     [rbp+37h+var_78], r14
0x14006bd96  mov     [rbp+37h+var_70], rsi
0x14006bd9a  mov     [rbp+37h+var_68], rbx
0x14006bd9e  mov     [rbp+37h+var_48], rdi
0x14006bda2  mov     [rsp+0D0h+Context], 0; Context
0x14006bdab  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14006bdb2  nop     dword ptr [rax+rax+00h]
0x14006bdb7  mov     ebx, eax
0x14006bdb9  cmp     eax, 0C0000017h
0x14006bdbe  jnz     short loc_14006BDC7
0x14006bdc0  mov     ebx, 0C000009Ah
0x14006bdc5  jmp     short loc_14006BDCB
0x14006bdc7  test    eax, eax
0x14006bdc9  jns     short loc_14006BDF4
0x14006bdcb  lea     rax, aApiKeexpandker; "API: KeExpandKernelStackAndCalloutEx"
0x14006bdd2  mov     r8, 8900211D44h; struct UnionFs::StackEventTracer *
0x14006bddc  lea     r9, aUnionfsUtilsCo_7; "UnionFs::Utils::CopyItemPrivOnNewStack"
0x14006bde3  mov     [rsp+0D0h+Context], rax; char *
0x14006bde8  mov     rdx, rdi; int
0x14006bdeb  mov     ecx, ebx; this
0x14006bded  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006bdf2  jmp     short loc_14006BE22
0x14006bdf4  mov     ebx, dword ptr [rbp+37h+var_38]
0x14006bdf7  test    ebx, ebx
0x14006bdf9  jns     short loc_14006BE4D
0x14006bdfb  lea     rax, aPushCopyitempr; "PUSH: CopyItemPriv"
0x14006be02  mov     r8, 8A00211D47h; struct UnionFs::StackEventTracer *
0x14006be0c  lea     r9, aUnionfsUtilsCo_7; "UnionFs::Utils::CopyItemPrivOnNewStack"
0x14006be13  mov     [rsp+0D0h+Context], rax; char *
0x14006be18  mov     rdx, rdi; int
0x14006be1b  mov     ecx, ebx; this
0x14006be1d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006be22  lea     rax, aPushCopyFromLa_0; "PUSH: Copy from layer on new stack"
0x14006be29  mov     r8, 28200211D69h; struct UnionFs::StackEventTracer *
0x14006be33  lea     r9, aUnionfsUtilsCo_5; "UnionFs::Utils::CopyItem"
0x14006be3a  mov     [rsp+0D0h+Context], rax; char *
0x14006be3f  mov     rdx, rdi; int
0x14006be42  mov     ecx, ebx; this
0x14006be44  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006be49  mov     eax, ebx
0x14006be4b  jmp     short loc_14006BE4F
0x14006be4d  xor     eax, eax
0x14006be4f  add     rsp, 0A8h
0x14006be56  pop     r15
0x14006be58  pop     r14
0x14006be5a  pop     rdi
0x14006be5b  pop     rsi
0x14006be5c  pop     rbx
0x14006be5d  pop     rbp
0x14006be5e  retn
```
