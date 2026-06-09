# UnionFs::Utils::CopyItem(_FLT_CALLBACK_DATA const &,UnionFs::UfsLayerCtx const &,UnionFs::UfsPathName const &,_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::Utils::CopyItemParams const &,UnionFs::StackEventTracer &,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> *)

- ea: `0x14006be98`
- end: `0x14006c050`
- name: `?CopyItem@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBVUfsLayerCtx@2@AEBVUfsPathName@2@AEBU_FLT_INSTANCE@@2AEBUCopyItemParams@12@AEAVStackEventTracer@2@PEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@@Z`
- size: `440`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x140013b60`
- `0x14001568c`
- `0x1400173f0`
- `0x1400183cc`
- `0x14002e468`
- `0x140031cfc`
- `0x140060764`

## callees

- `0x140056bd0`
- `0x140056c7c`
- `0x14006be98`
- `0x14006c3ec`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x14006bed1`
- `ntoskrnl!IoGetStackLimits` at `0x14006bed1`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14006bf9b`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14006bf9b`

## string_xrefs

- `0x14006bfeb`: `PUSH: CopyItemPriv`
- `0x14006bfcc`: `UnionFs::Utils::CopyItemPrivOnNewStack`
- `0x14006bffc`: `UnionFs::Utils::CopyItemPrivOnNewStack`
- `0x14006c023`: `UnionFs::Utils::CopyItem`
- `0x14006c012`: `PUSH: Copy from layer on new stack`
- `0x14006bf2c`: `PUSH: Copy from layer (direct)`

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
        (struct UnionFs::StackEventTracer *)0x8A00211D7DLL,
        (unsigned __int64)"UnionFs::Utils::CopyItemPrivOnNewStack",
        "PUSH: CopyItemPriv",
        v17);
LABEL_10:
      v13 = "PUSH: Copy from layer on new stack";
      v14 = 0x28200211D9FLL;
      goto LABEL_11;
    }
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)v12,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x8900211D7ALL,
      (unsigned __int64)"UnionFs::Utils::CopyItemPrivOnNewStack",
      "API: KeExpandKernelStackAndCalloutEx",
      v17);
    goto LABEL_10;
  }
  v12 = UnionFs::Utils::CopyItemPriv(a1, a2, a3, a4, SourceString, a6, a7, a8);
  if ( (v12 & 0x80000000) != 0 )
  {
    v13 = "PUSH: Copy from layer (direct)";
    v14 = 0x26100211DADLL;
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
0x14006be98  push    rbp
0x14006be9a  push    rbx
0x14006be9b  push    rsi
0x14006be9c  push    rdi
0x14006be9d  push    r14
0x14006be9f  push    r15
0x14006bea1  lea     rbp, [rsp-0Fh]
0x14006bea6  sub     rsp, 0A8h
0x14006bead  mov     r14, rdx
0x14006beb0  mov     [rbp+37h+HighLimit], 0
0x14006beb8  mov     r15, rcx
0x14006bebb  mov     [rbp+37h+LowLimit], 0
0x14006bec3  lea     rdx, [rbp+37h+HighLimit]; HighLimit
0x14006bec7  mov     rbx, r9
0x14006beca  lea     rcx, [rbp+37h+LowLimit]; LowLimit
0x14006bece  mov     rsi, r8
0x14006bed1  call    cs:__imp_IoGetStackLimits
0x14006bed8  nop     dword ptr [rax+rax+00h]
0x14006bedd  mov     rdi, [rbp+37h+arg_30]
0x14006bee1  lea     rax, [rbp+37h+HighLimit]
0x14006bee5  sub     rax, [rbp+37h+LowLimit]
0x14006bee9  cmp     rax, 3000h
0x14006beef  jbe     short loc_14006BF42
0x14006bef1  mov     rax, [rbp+37h+arg_38]
0x14006bef5  mov     r9, rbx; int
0x14006bef8  mov     [rsp+0D0h+var_98], rax; __int64
0x14006befd  mov     r8, rsi; int
0x14006bf00  mov     rax, [rbp+37h+arg_28]
0x14006bf04  mov     rdx, r14; int
0x14006bf07  mov     [rsp+0D0h+var_A0], rdi; struct _FILE_OBJECT *
0x14006bf0c  mov     rcx, r15; int
0x14006bf0f  mov     [rsp+0D0h+var_A8], rax; __int64
0x14006bf14  mov     rax, [rbp+37h+SourceString]
0x14006bf18  mov     [rsp+0D0h+Context], rax; SourceString
0x14006bf1d  call    ?CopyItemPriv@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBVUfsLayerCtx@2@AEBVUfsPathName@2@AEBU_FLT_INSTANCE@@2AEBUCopyItemParams@12@AEAVStackEventTracer@2@PEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@@Z; UnionFs::Utils::CopyItemPriv(_FLT_CALLBACK_DATA const &,UnionFs::UfsLayerCtx const &,UnionFs::UfsPathName const &,_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::Utils::CopyItemParams const &,UnionFs::StackEventTracer &,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> *)
0x14006bf22  mov     ebx, eax
0x14006bf24  test    eax, eax
0x14006bf26  jns     loc_14006C03D
0x14006bf2c  lea     rax, aPushCopyFromLa; "PUSH: Copy from layer (direct)"
0x14006bf33  mov     r8, 26100211DADh
0x14006bf3d  jmp     loc_14006C023
0x14006bf42  mov     rax, [rbp+37h+SourceString]
0x14006bf46  lea     rdx, [rbp+37h+Parameter]; Parameter
0x14006bf4a  mov     [rbp+37h+var_60], rax
0x14006bf4e  lea     rcx, ?CopyItemPrivCallout@Utils@UnionFs@@YAXPEAUUFS_CALLOUT_PARAMETERS@2@@Z; Callout
0x14006bf55  mov     rax, [rbp+37h+arg_28]
0x14006bf59  xor     r9d, r9d; Wait
0x14006bf5c  mov     [rbp+37h+var_58], rax
0x14006bf60  mov     r8d, 6000h; Size
0x14006bf66  mov     rax, [rbp+37h+arg_38]
0x14006bf6a  mov     [rbp+37h+var_40], rax
0x14006bf6e  mov     [rbp+37h+var_50], 0
0x14006bf76  mov     [rbp+37h+var_38], 0
0x14006bf7e  mov     [rbp+37h+Parameter], r15
0x14006bf82  mov     [rbp+37h+var_78], r14
0x14006bf86  mov     [rbp+37h+var_70], rsi
0x14006bf8a  mov     [rbp+37h+var_68], rbx
0x14006bf8e  mov     [rbp+37h+var_48], rdi
0x14006bf92  mov     [rsp+0D0h+Context], 0; Context
0x14006bf9b  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14006bfa2  nop     dword ptr [rax+rax+00h]
0x14006bfa7  mov     ebx, eax
0x14006bfa9  cmp     eax, 0C0000017h
0x14006bfae  jnz     short loc_14006BFB7
0x14006bfb0  mov     ebx, 0C000009Ah
0x14006bfb5  jmp     short loc_14006BFBB
0x14006bfb7  test    eax, eax
0x14006bfb9  jns     short loc_14006BFE4
0x14006bfbb  lea     rax, aApiKeexpandker; "API: KeExpandKernelStackAndCalloutEx"
0x14006bfc2  mov     r8, 8900211D7Ah; struct UnionFs::StackEventTracer *
0x14006bfcc  lea     r9, aUnionfsUtilsCo_7; "UnionFs::Utils::CopyItemPrivOnNewStack"
0x14006bfd3  mov     [rsp+0D0h+Context], rax; char *
0x14006bfd8  mov     rdx, rdi; int
0x14006bfdb  mov     ecx, ebx; this
0x14006bfdd  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006bfe2  jmp     short loc_14006C012
0x14006bfe4  mov     ebx, dword ptr [rbp+37h+var_38]
0x14006bfe7  test    ebx, ebx
0x14006bfe9  jns     short loc_14006C03D
0x14006bfeb  lea     rax, aPushCopyitempr; "PUSH: CopyItemPriv"
0x14006bff2  mov     r8, 8A00211D7Dh; struct UnionFs::StackEventTracer *
0x14006bffc  lea     r9, aUnionfsUtilsCo_7; "UnionFs::Utils::CopyItemPrivOnNewStack"
0x14006c003  mov     [rsp+0D0h+Context], rax; char *
0x14006c008  mov     rdx, rdi; int
0x14006c00b  mov     ecx, ebx; this
0x14006c00d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c012  lea     rax, aPushCopyFromLa_0; "PUSH: Copy from layer on new stack"
0x14006c019  mov     r8, 28200211D9Fh; struct UnionFs::StackEventTracer *
0x14006c023  lea     r9, aUnionfsUtilsCo_5; "UnionFs::Utils::CopyItem"
0x14006c02a  mov     [rsp+0D0h+Context], rax; char *
0x14006c02f  mov     rdx, rdi; int
0x14006c032  mov     ecx, ebx; this
0x14006c034  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c039  mov     eax, ebx
0x14006c03b  jmp     short loc_14006C03F
0x14006c03d  xor     eax, eax
0x14006c03f  add     rsp, 0A8h
0x14006c046  pop     r15
0x14006c048  pop     r14
0x14006c04a  pop     rdi
0x14006c04b  pop     rsi
0x14006c04c  pop     rbx
0x14006c04d  pop     rbp
0x14006c04e  retn
```
