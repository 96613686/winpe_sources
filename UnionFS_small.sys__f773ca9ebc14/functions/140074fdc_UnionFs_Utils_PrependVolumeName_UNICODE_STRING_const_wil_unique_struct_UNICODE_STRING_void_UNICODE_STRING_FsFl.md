# UnionFs::Utils::PrependVolumeName(_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)

- ea: `0x140074fdc`
- end: `0x14007524e`
- name: `?PrependVolumeName@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z`
- size: `626`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, PCUNICODE_STRING, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140075254`

## callees

- `0x140056a50`
- `0x140056ac4`
- `0x140074fdc`
- `0x140079c48`
- `0x140079d0c`
- `0x14007af90`
- `0x14007b900`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140075071`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007509e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140075071`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007509e`

## string_xrefs

- `0x140075214`: `API: Getting temp string length`
- `0x14007503b`: `ORIGIN: Allocating temp string`
- `0x140075009`: `Caller attempting to use zero-length component`
- `0x1400750b0`: `API: Appending path to temp string`
- `0x140075083`: `API: Appending volume name to temp string`
- `0x140075201`: `API: Copying volume name to path from root`

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
0x140074fdc  push    rbx
0x140074fde  push    rbp
0x140074fdf  push    rsi
0x140074fe0  push    rdi
0x140074fe1  push    r14
0x140074fe3  sub     rsp, 40h
0x140074fe7  mov     rbx, rcx
0x140074fea  mov     r14, r8
0x140074fed  movzx   ecx, word ptr [rdx]
0x140074ff0  mov     rsi, rdx
0x140074ff3  movzx   eax, word ptr [rbx]
0x140074ff6  lea     ebp, [rcx+rax]
0x140074ff9  cmp     bp, ax
0x140074ffc  jb      loc_140075214
0x140075002  jbe     short loc_140075009
0x140075004  cmp     bp, cx
0x140075007  ja      short loc_140075015
0x140075009  lea     rcx, aCallerAttempti; "Caller attempting to use zero-length co"...
0x140075010  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140075015  cmp     [rsi+2], bp
0x140075019  jnb     loc_140075107
0x14007501f  mov     r8d, 4C467346h
0x140075025  lea     rcx, [rsp+68h+Destination]
0x14007502a  movzx   edx, bp
0x14007502d  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x140075032  xor     edi, edi
0x140075034  cmp     [rsp+68h+Destination.Buffer], rdi
0x140075039  jnz     short loc_140075069
0x14007503b  lea     rax, aOriginAllocati_25; "ORIGIN: Allocating temp string"
0x140075042  mov     ebx, 0C000009Ah
0x140075047  mov     ecx, ebx; this
0x140075049  mov     [rsp+68h+var_48], rax; char *
0x14007504e  lea     r9, aUnionfsUtilsPr_0; "UnionFs::Utils::PrependVolumeName"
0x140075055  mov     r8, 3590021030Fh; struct UnionFs::StackEventTracer *
0x14007505f  mov     rdx, r14; int
0x140075062  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075067  jmp     short loc_1400750D7
0x140075069  mov     rdx, rbx; Source
0x14007506c  lea     rcx, [rsp+68h+Destination]; Destination
0x140075071  call    cs:__imp_RtlAppendUnicodeStringToString
0x140075078  nop     dword ptr [rax+rax+00h]
0x14007507d  mov     ebx, eax
0x14007507f  test    eax, eax
0x140075081  jns     short loc_140075096
0x140075083  lea     rax, aApiAppendingVo_0; "API: Appending volume name to temp stri"...
0x14007508a  mov     r8, 35A00210314h
0x140075094  jmp     short loc_1400750C1
0x140075096  mov     rdx, rsi; Source
0x140075099  lea     rcx, [rsp+68h+Destination]; Destination
0x14007509e  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400750a5  nop     dword ptr [rax+rax+00h]
0x1400750aa  mov     ebx, eax
0x1400750ac  test    eax, eax
0x1400750ae  jns     short loc_1400750E6
0x1400750b0  lea     rax, aApiAppendingPa; "API: Appending path to temp string"
0x1400750b7  mov     r8, 35B00210319h; struct UnionFs::StackEventTracer *
0x1400750c1  lea     r9, aUnionfsUtilsPr_0; "UnionFs::Utils::PrependVolumeName"
0x1400750c8  mov     [rsp+68h+var_48], rax; char *
0x1400750cd  mov     rdx, r14; int
0x1400750d0  mov     ecx, ebx; this
0x1400750d2  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400750d7  lea     rcx, [rsp+68h+Destination]; UnicodeString
0x1400750dc  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400750e1  jmp     loc_140075240
0x1400750e6  movups  xmm1, xmmword ptr [rsi]
0x1400750e9  lea     rcx, [rsp+68h+Destination]; UnicodeString
0x1400750ee  movaps  xmm0, xmmword ptr [rsp+68h+Destination.Length]
0x1400750f3  movdqa  xmmword ptr [rsp+68h+Destination.Length], xmm1
0x1400750f9  movdqu  xmmword ptr [rsi], xmm0
0x1400750fd  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140075102  jmp     loc_1400751F8
0x140075107  mov     rdx, [rsi+8]; Src
0x14007510b  movzx   ecx, word ptr [rbx]
0x14007510e  movzx   r8d, word ptr [rsi]; Size
0x140075112  add     rcx, rdx; void *
0x140075115  call    memmove
0x14007511a  movzx   ecx, word ptr [rsi+2]
0x14007511e  xor     edi, edi
0x140075120  movzx   edx, word ptr [rsi]
0x140075123  movzx   eax, cx
0x140075126  or      ax, dx
0x140075129  bt      ax, di
0x14007512d  jb      loc_1400751FC
0x140075133  cmp     dx, cx
0x140075136  ja      loc_1400751FC
0x14007513c  mov     r8d, 0FFFEh
0x140075142  cmp     cx, r8w
0x140075146  ja      loc_1400751FC
0x14007514c  mov     r10, [rsi+8]
0x140075150  test    r10, r10
0x140075153  jnz     short loc_140075167
0x140075155  test    dx, dx
0x140075158  jnz     loc_1400751FC
0x14007515e  test    cx, cx
0x140075161  jnz     loc_1400751FC
0x140075167  movzx   edx, word ptr [rbx]
0x14007516a  test    dl, 1
0x14007516d  jnz     short loc_1400751D3
0x14007516f  movzx   eax, word ptr [rbx+2]
0x140075173  test    al, 1
0x140075175  jnz     short loc_1400751D3
0x140075177  cmp     dx, ax
0x14007517a  ja      short loc_1400751D3
0x14007517c  cmp     ax, r8w
0x140075180  ja      short loc_1400751D3
0x140075182  mov     r8, [rbx+8]
0x140075186  test    r8, r8
0x140075189  jnz     short loc_140075195
0x14007518b  test    dx, dx
0x14007518e  jnz     short loc_1400751D3
0x140075190  test    ax, ax
0x140075193  jnz     short loc_1400751D3
0x140075195  mov     r9, rcx
0x140075198  shr     rdx, 1
0x14007519b  shr     r9, 1
0x14007519e  mov     ebx, edi
0x1400751a0  mov     rcx, rdi
0x1400751a3  jz      short loc_1400751C6
0x1400751a5  test    rdx, rdx
0x1400751a8  jz      short loc_1400751DB
0x1400751aa  movzx   eax, word ptr [r8]
0x1400751ae  dec     rdx
0x1400751b1  mov     [r10], ax
0x1400751b5  add     r8, 2
0x1400751b9  add     r10, 2
0x1400751bd  inc     rcx
0x1400751c0  sub     r9, 1
0x1400751c4  jnz     short loc_1400751A5
0x1400751c6  test    rdx, rdx
0x1400751c9  mov     eax, 80000005h
0x1400751ce  cmovnz  ebx, eax
0x1400751d1  jmp     short loc_1400751DB
0x1400751d3  mov     rcx, rdi
0x1400751d6  mov     ebx, 0C000000Dh
0x1400751db  add     cx, cx
0x1400751de  mov     [rsi], cx
0x1400751e1  test    ebx, ebx
0x1400751e3  js      short loc_140075201
0x1400751e5  mov     rax, [rsi+8]
0x1400751e9  movzx   ecx, cx
0x1400751ec  shr     rcx, 1
0x1400751ef  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x1400751f5  mov     [rsi], bp
0x1400751f8  xor     eax, eax
0x1400751fa  jmp     short loc_140075242
0x1400751fc  mov     ebx, 0C000000Dh
0x140075201  lea     rax, aApiCopyingVolu; "API: Copying volume name to path from r"...
0x140075208  mov     r8, 35C00210329h
0x140075212  jmp     short loc_14007522A
0x140075214  lea     rax, aApiGettingTemp; "API: Getting temp string length"
0x14007521b  mov     r8, 35800210301h; struct UnionFs::StackEventTracer *
0x140075225  mov     ebx, 0C0000095h
0x14007522a  lea     r9, aUnionfsUtilsPr_0; "UnionFs::Utils::PrependVolumeName"
0x140075231  mov     [rsp+68h+var_48], rax; char *
0x140075236  mov     rdx, r14; int
0x140075239  mov     ecx, ebx; this
0x14007523b  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075240  mov     eax, ebx
0x140075242  add     rsp, 40h
0x140075246  pop     r14
0x140075248  pop     rdi
0x140075249  pop     rsi
0x14007524a  pop     rbp
0x14007524b  pop     rbx
0x14007524c  retn
```
