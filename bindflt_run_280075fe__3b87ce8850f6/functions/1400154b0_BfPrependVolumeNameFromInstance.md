# BfPrependVolumeNameFromInstance

- ea: `0x1400154b0`
- end: `0x140015795`
- name: `BfPrependVolumeNameFromInstance`
- size: `741`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140001dd0`
- `0x1400152f0`
- `0x1400157a0`

## callees

- `0x140001348`
- `0x1400045c4`
- `0x1400154b0`
- `0x1400172f0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400155bb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400155bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400155ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015631`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400155ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015631`
- `ntoskrnl!ExAllocatePool2` at `0x140015536`
- `ntoskrnl!ExAllocatePool2` at `0x140015596`
- `ntoskrnl!ExAllocatePool2` at `0x140015536`
- `ntoskrnl!ExAllocatePool2` at `0x140015596`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400155ce`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400155ce`
- `FLTMGR!FltGetVolumeFromInstance` at `0x1400154e8`
- `FLTMGR!FltGetVolumeFromInstance` at `0x1400154e8`
- `FLTMGR!FltObjectDereference` at `0x140015653`
- `FLTMGR!FltObjectDereference` at `0x140015653`
- `FLTMGR!FltGetVolumeName` at `0x140015508`
- `FLTMGR!FltGetVolumeName` at `0x14001555e`
- `FLTMGR!FltGetVolumeName` at `0x140015508`
- `FLTMGR!FltGetVolumeName` at `0x14001555e`

## pseudocode

```c
__int64 __fastcall BfPrependVolumeNameFromInstance(struct _FLT_INSTANCE *a1, UNICODE_STRING *a2)
{
  int v3; // edx
  NTSTATUS VolumeFromInstance; // ebx
  USHORT v5; // bx
  USHORT v6; // si
  USHORT v7; // cx
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  int v12; // r9d
  char v13; // [rsp+30h] [rbp-48h]
  int v14; // [rsp+38h] [rbp-40h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-28h] BYREF
  struct _UNICODE_STRING VolumeName; // [rsp+60h] [rbp-18h] BYREF
  ULONG BufferSizeNeeded; // [rsp+A0h] [rbp+28h] BYREF
  PFLT_VOLUME RetVolume; // [rsp+A8h] [rbp+30h] BYREF

  RetVolume = 0;
  BufferSizeNeeded = 0;
  VolumeName = 0;
  DestinationString = 0;
  VolumeFromInstance = FltGetVolumeFromInstance(a1, &RetVolume);
  if ( VolumeFromInstance < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_11;
    v14 = VolumeFromInstance;
    v12 = 32;
    v13 = -109;
    goto LABEL_27;
  }
  FltGetVolumeName(RetVolume, 0, &BufferSizeNeeded);
  v5 = BufferSizeNeeded;
  v6 = 1;
  *(_DWORD *)&VolumeName.Length = 0;
  if ( !(_WORD)BufferSizeNeeded )
    v5 = 1;
  VolumeName.Buffer = (PWSTR)ExAllocatePool2(256, v5, 1953711682);
  if ( !VolumeName.Buffer )
  {
    VolumeFromInstance = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_11;
    v14 = -1073741670;
    v12 = 33;
    v13 = -92;
    goto LABEL_27;
  }
  VolumeName.MaximumLength = v5;
  FltGetVolumeName(RetVolume, &VolumeName, 0);
  v7 = a2->Length + VolumeName.Length;
  if ( v7 < VolumeName.Length )
  {
    VolumeFromInstance = -1073741675;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_11;
    v14 = -1073741675;
    v12 = 34;
    v13 = -78;
LABEL_27:
    LOBYTE(v3) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v3,
      8,
      v12,
      (__int64)WPP_529f93b0825532f67776c14f74ba0846_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\utils.c",
      v13,
      v14);
    goto LABEL_11;
  }
  *(_DWORD *)&DestinationString.Length = 0;
  if ( v7 )
    v6 = v7;
  DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, v6, 1953711682);
  if ( !DestinationString.Buffer )
  {
    VolumeFromInstance = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_11;
    v14 = -1073741670;
    v12 = 35;
    v13 = -70;
    goto LABEL_27;
  }
  DestinationString.MaximumLength = v6;
  RtlCopyUnicodeString(&DestinationString, &VolumeName);
  VolumeFromInstance = RtlAppendUnicodeStringToString(&DestinationString, a2);
  if ( VolumeFromInstance < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sDZZd(WPP_GLOBAL_Control->DeviceExtension, v8, v9, v10);
    BfFreeUnicodeString(&DestinationString);
  }
  else
  {
    ExFreePoolWithTag(a2->Buffer, 0x74734642u);
    VolumeFromInstance = 0;
    a2->Buffer = DestinationString.Buffer;
    a2->Length = DestinationString.Length;
    a2->MaximumLength = DestinationString.MaximumLength;
  }
LABEL_11:
  if ( VolumeName.Buffer )
  {
    ExFreePoolWithTag(VolumeName.Buffer, 0x74734642u);
    VolumeName.Buffer = 0;
  }
  *(_DWORD *)&VolumeName.Length = 0;
  if ( RetVolume )
    FltObjectDereference(RetVolume);
  return (unsigned int)VolumeFromInstance;
}

```

## disassembly

```asm
0x1400154b0  mov     rax, rsp
0x1400154b3  push    rbp
0x1400154b4  push    rbx
0x1400154b5  mov     rbp, rsp
0x1400154b8  sub     rsp, 78h
0x1400154bc  mov     [rax+8], rsi
0x1400154c0  xorps   xmm0, xmm0
0x1400154c3  mov     [rax+10h], rdi
0x1400154c7  xorps   xmm1, xmm1
0x1400154ca  mov     [rax-18h], r14
0x1400154ce  mov     rdi, rdx
0x1400154d1  xor     r14d, r14d
0x1400154d4  lea     rdx, [rbp+RetVolume]; RetVolume
0x1400154d8  mov     [rbp+RetVolume], r14
0x1400154dc  mov     [rbp+BufferSizeNeeded], r14d
0x1400154e0  movups  xmmword ptr [rbp+VolumeName.Length], xmm0
0x1400154e4  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x1400154e8  call    cs:__imp_FltGetVolumeFromInstance
0x1400154ef  nop     dword ptr [rax+rax+00h]
0x1400154f4  mov     ebx, eax
0x1400154f6  test    eax, eax
0x1400154f8  js      loc_14001569D
0x1400154fe  mov     rcx, [rbp+RetVolume]; Volume
0x140015502  lea     r8, [rbp+BufferSizeNeeded]; BufferSizeNeeded
0x140015506  xor     edx, edx; VolumeName
0x140015508  call    cs:__imp_FltGetVolumeName
0x14001550f  nop     dword ptr [rax+rax+00h]
0x140015514  movzx   ebx, word ptr [rbp+BufferSizeNeeded]
0x140015518  mov     esi, 1
0x14001551d  mov     dword ptr [rbp+VolumeName.Length], r14d
0x140015521  test    bx, bx
0x140015524  jnz     short loc_140015528
0x140015526  mov     ebx, esi
0x140015528  movzx   edx, bx
0x14001552b  mov     ecx, 100h
0x140015530  mov     r8d, 74734642h
0x140015536  call    cs:__imp_ExAllocatePool2
0x14001553d  nop     dword ptr [rax+rax+00h]
0x140015542  mov     [rbp+VolumeName.Buffer], rax
0x140015546  test    rax, rax
0x140015549  jz      loc_140015735
0x14001554f  mov     rcx, [rbp+RetVolume]; Volume
0x140015553  lea     rdx, [rbp+VolumeName]; VolumeName
0x140015557  xor     r8d, r8d; BufferSizeNeeded
0x14001555a  mov     [rbp+VolumeName.MaximumLength], bx
0x14001555e  call    cs:__imp_FltGetVolumeName
0x140015565  nop     dword ptr [rax+rax+00h]
0x14001556a  movzx   ecx, [rbp+VolumeName.Length]
0x14001556e  add     cx, [rdi]
0x140015571  cmp     cx, [rbp+VolumeName.Length]
0x140015575  jb      loc_140015669
0x14001557b  mov     dword ptr [rbp+DestinationString.Length], r14d
0x14001557f  test    cx, cx
0x140015582  jnz     loc_140015695
0x140015588  movzx   edx, si
0x14001558b  mov     ecx, 100h
0x140015590  mov     r8d, 74734642h
0x140015596  call    cs:__imp_ExAllocatePool2
0x14001559d  nop     dword ptr [rax+rax+00h]
0x1400155a2  mov     [rbp+DestinationString.Buffer], rax
0x1400155a6  test    rax, rax
0x1400155a9  jz      loc_140015708
0x1400155af  lea     rdx, [rbp+VolumeName]; SourceString
0x1400155b3  mov     [rbp+DestinationString.MaximumLength], si
0x1400155b7  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400155bb  call    cs:__imp_RtlCopyUnicodeString
0x1400155c2  nop     dword ptr [rax+rax+00h]
0x1400155c7  mov     rdx, rdi; Source
0x1400155ca  lea     rcx, [rbp+DestinationString]; Destination
0x1400155ce  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400155d5  nop     dword ptr [rax+rax+00h]
0x1400155da  mov     ebx, eax
0x1400155dc  test    eax, eax
0x1400155de  js      loc_1400156C8
0x1400155e4  mov     rcx, [rdi+8]; P
0x1400155e8  mov     edx, 74734642h; Tag
0x1400155ed  call    cs:__imp_ExFreePoolWithTag
0x1400155f4  nop     dword ptr [rax+rax+00h]
0x1400155f9  mov     rax, [rbp+DestinationString.Buffer]
0x1400155fd  mov     ebx, r14d
0x140015600  mov     [rdi+8], rax
0x140015604  movzx   eax, [rbp+DestinationString.Length]
0x140015608  mov     [rdi], ax
0x14001560b  movzx   eax, [rbp+DestinationString.MaximumLength]
0x14001560f  mov     [rdi+2], ax
0x140015613  mov     rcx, [rbp+VolumeName.Buffer]; P
0x140015617  mov     rdi, [rsp+78h+arg_8]
0x14001561f  mov     rsi, [rsp+78h+arg_0]
0x140015627  test    rcx, rcx
0x14001562a  jz      short loc_140015641
0x14001562c  mov     edx, 74734642h; Tag
0x140015631  call    cs:__imp_ExFreePoolWithTag
0x140015638  nop     dword ptr [rax+rax+00h]
0x14001563d  mov     [rbp+VolumeName.Buffer], r14
0x140015641  mov     rcx, [rbp+RetVolume]; FltObject
0x140015645  mov     dword ptr [rbp+VolumeName.Length], r14d
0x140015649  mov     r14, [rsp+78h+var_8]
0x14001564e  test    rcx, rcx
0x140015651  jz      short loc_14001565F
0x140015653  call    cs:__imp_FltObjectDereference
0x14001565a  nop     dword ptr [rax+rax+00h]
0x14001565f  mov     eax, ebx
0x140015661  add     rsp, 78h
0x140015665  pop     rbx
0x140015666  pop     rbp
0x140015667  retn
0x140015669  mov     ebx, 0C0000095h
0x14001566e  lea     rax, WPP_RECORDER_INITIALIZED
0x140015675  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001567c  jz      short loc_140015613
0x14001567e  mov     dword ptr [rsp+78h+var_40], ebx
0x140015682  mov     r9d, 22h ; '"'
0x140015688  mov     dword ptr [rsp+78h+var_48], 6B2h
0x140015690  jmp     loc_140015760
0x140015695  movzx   esi, cx
0x140015698  jmp     loc_140015588
0x14001569d  lea     rax, WPP_RECORDER_INITIALIZED
0x1400156a4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400156ab  jz      loc_140015613
0x1400156b1  mov     dword ptr [rsp+78h+var_40], ebx
0x1400156b5  mov     r9d, 20h ; ' '
0x1400156bb  mov     dword ptr [rsp+78h+var_48], 693h
0x1400156c3  jmp     loc_140015760
0x1400156c8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400156cf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400156d6  jz      short loc_1400156FA
0x1400156d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400156df  lea     rax, [rbp+DestinationString]
0x1400156e3  mov     [rsp+78h+var_30], ebx
0x1400156e7  mov     [rsp+78h+var_38], rax
0x1400156ec  mov     [rsp+78h+var_40], rdi
0x1400156f1  mov     rcx, [rcx+40h]
0x1400156f5  call    WPP_RECORDER_SF_sDZZd
0x1400156fa  lea     rcx, [rbp+DestinationString]
0x1400156fe  call    BfFreeUnicodeString
0x140015703  jmp     loc_140015613
0x140015708  mov     ebx, 0C000009Ah
0x14001570d  lea     rax, WPP_RECORDER_INITIALIZED
0x140015714  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001571b  jz      loc_140015613
0x140015721  mov     dword ptr [rsp+78h+var_40], ebx
0x140015725  mov     r9d, 23h ; '#'
0x14001572b  mov     dword ptr [rsp+78h+var_48], 6BAh
0x140015733  jmp     short loc_140015760
0x140015735  mov     ebx, 0C000009Ah
0x14001573a  lea     rax, WPP_RECORDER_INITIALIZED
0x140015741  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140015748  jz      loc_140015613
0x14001574e  mov     dword ptr [rsp+78h+var_40], ebx
0x140015752  mov     r9d, 21h ; '!'
0x140015758  mov     dword ptr [rsp+78h+var_48], 6A4h
0x140015760  mov     rcx, cs:WPP_GLOBAL_Control
0x140015767  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001576e  mov     [rsp+78h+var_50], rax
0x140015773  mov     r8d, 8
0x140015779  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x140015780  mov     dl, 2
0x140015782  mov     [rsp+78h+var_58], rax
0x140015787  mov     rcx, [rcx+40h]
0x14001578b  call    WPP_RECORDER_SF_sDd
0x140015790  jmp     loc_140015613
```
