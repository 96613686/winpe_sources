# SdpInt_MigrateCache(_SDP_INTERFACE *,unsigned __int64 const *)

- ea: `0x1401f06f0`
- end: `0x1401f0a85`
- name: `?SdpInt_MigrateCache@@YAJPEAU_SDP_INTERFACE@@PEB_K@Z`
- size: `917`
- prototype: `int(struct _SDP_INTERFACE *, const unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14014b384`

## callees

- `0x140005690`
- `0x140005b4c`
- `0x1401f06f0`
- `0x1401f0fe0`
- `0x1401f270c`
- `0x140209448`

## import_xrefs

- `ntoskrnl!ZwDeleteValueKey` at `0x1401f09d3`
- `ntoskrnl!ZwDeleteValueKey` at `0x1401f09d3`
- `ntoskrnl!ZwClose` at `0x1401f0a05`
- `ntoskrnl!ZwClose` at `0x1401f0a05`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f09e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f09e9`
- `ntoskrnl!ExAllocatePool2` at `0x1401f0892`
- `ntoskrnl!ExAllocatePool2` at `0x1401f0892`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401f0793`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401f0793`

## pseudocode

```c
__int64 __fastcall SdpInt_MigrateCache(struct _SDP_INTERFACE *a1, const unsigned __int64 *a2)
{
  int v2; // r14d
  const unsigned __int64 *v3; // r15
  char v5; // di
  __int16 DeviceType; // ax
  struct _SECURITY_DATABASE *v7; // rcx
  int v8; // edx
  int updated; // ebx
  int v10; // r8d
  void *DeviceExtension; // r9
  _DEVICE_OBJECT *AttachedDevice; // rcx
  int v13; // edx
  int v14; // r8d
  int v15; // eax
  void *Pool2; // rsi
  PDEVICE_OBJECT v17; // rcx
  int v18; // edx
  __int64 *v19; // r8
  int v20; // edx
  __int64 *v21; // r8
  __int16 v22; // ax
  char v24; // [rsp+20h] [rbp-40h]
  __int16 v25; // [rsp+30h] [rbp-30h]
  char v26; // [rsp+40h] [rbp-20h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF
  __int64 v28; // [rsp+B0h] [rbp+50h] BYREF
  HANDLE KeyHandle; // [rsp+B8h] [rbp+58h] BYREF

  LODWORD(v28) = 0;
  v2 = 0;
  KeyHandle = 0;
  v3 = a2;
  DestinationString = 0;
  v5 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0 || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    LOBYTE(a2) = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( (_BYTE)a2 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      DeviceType != 0,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      8,
      51,
      (__int64)WPP_1c8b0d14a8043465701df8be11446151_Traceguids,
      *v3);
  RtlInitUnicodeString(&DestinationString, L"SdpRecord");
  updated = SecDB_OpenDeviceKey(v7, v3, &KeyHandle);
  if ( updated < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0 || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v8) = 0;
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v26 = updated;
    v25 = 52;
    v24 = 3;
    goto LABEL_12;
  }
  v15 = BthQueryKeyValueEx(KeyHandle, &DestinationString, 0, (__int64)&v28);
  updated = v15;
  if ( v15 == -1073741789 || v15 == -2147483643 )
  {
    Pool2 = (void *)ExAllocatePool2(256, (unsigned int)v28, 1346917442);
    if ( !Pool2 )
    {
      updated = -1073741670;
      v17 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0 || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v8) = 0;
      v26 = -102;
      v25 = 53;
      v24 = 2;
      goto LABEL_20;
    }
    updated = BthQueryKeyValueEx(KeyHandle, &DestinationString, Pool2, (__int64)&v28);
    if ( updated < 0 )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0 || (LOBYTE(v18) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v18) = 0;
      v19 = WPP_1c8b0d14a8043465701df8be11446151_Traceguids;
      LOBYTE(v19) = 1;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v18,
        (_DWORD)v19,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        8,
        54,
        (__int64)WPP_1c8b0d14a8043465701df8be11446151_Traceguids,
        updated);
      goto LABEL_39;
    }
    v2 = v28;
  }
  else
  {
    Pool2 = 0;
    if ( v15 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0 || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
        LOBYTE(v8) = 0;
      v26 = v15;
      v25 = 55;
      v24 = 3;
LABEL_20:
      DeviceExtension = v17->DeviceExtension;
      AttachedDevice = v17->AttachedDevice;
LABEL_12:
      LOBYTE(v10) = 1;
      WPP_RECORDER_AND_TRACE_SF_d(
        (_DWORD)AttachedDevice,
        v8,
        v10,
        (_DWORD)DeviceExtension,
        v24,
        8,
        v25,
        (__int64)WPP_1c8b0d14a8043465701df8be11446151_Traceguids,
        v26);
      goto LABEL_40;
    }
  }
  updated = SdpInt_UpdateCacheWithFullRecord(a1, v3, (unsigned __int8 *)Pool2, v2);
  if ( updated >= 0 )
  {
    ZwDeleteValueKey(KeyHandle, &DestinationString);
  }
  else
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0 || (LOBYTE(v20) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v20) = 0;
    v21 = WPP_1c8b0d14a8043465701df8be11446151_Traceguids;
    LOBYTE(v21) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v20,
      (_DWORD)v21,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      8,
      56,
      (__int64)WPP_1c8b0d14a8043465701df8be11446151_Traceguids,
      updated);
  }
  if ( Pool2 )
LABEL_39:
    ExFreePoolWithTag(Pool2, 0);
LABEL_40:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v5 = 0;
  v22 = WPP_GLOBAL_Control->DeviceType;
  if ( v5 || v22 )
  {
    LOBYTE(v13) = v5;
    LOBYTE(v14) = v22 != 0;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v13,
      v14,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      8,
      57,
      (__int64)WPP_1c8b0d14a8043465701df8be11446151_Traceguids,
      updated);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1401f06f0  mov     [rsp-38h+arg_0], rbx
0x1401f06f5  push    rbp
0x1401f06f6  push    rsi
0x1401f06f7  push    rdi
0x1401f06f8  push    r12
0x1401f06fa  push    r13
0x1401f06fc  push    r14
0x1401f06fe  push    r15
0x1401f0700  mov     rbp, rsp
0x1401f0703  sub     rsp, 60h
0x1401f0707  xor     r13d, r13d
0x1401f070a  xorps   xmm0, xmm0
0x1401f070d  mov     dword ptr [rbp+arg_10], r13d
0x1401f0711  mov     r14d, r13d
0x1401f0714  mov     [rbp+KeyHandle], r13
0x1401f0718  mov     r15, rdx
0x1401f071b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1401f071f  mov     r12, rcx
0x1401f0722  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401f0729  mov     dil, 1
0x1401f072c  mov     eax, [rcx+2Ch]
0x1401f072f  test    al, al
0x1401f0731  jns     short loc_1401F073C
0x1401f0733  cmp     byte ptr [rcx+29h], 5
0x1401f0737  mov     dl, dil
0x1401f073a  jnb     short loc_1401F073F
0x1401f073c  mov     dl, r13b
0x1401f073f  movzx   eax, word ptr [rcx+48h]
0x1401f0743  lea     rsi, WPP_1c8b0d14a8043465701df8be11446151_Traceguids
0x1401f074a  test    ax, ax
0x1401f074d  setnz   r8b
0x1401f0751  test    dl, dl
0x1401f0753  jnz     short loc_1401F075A
0x1401f0755  test    ax, ax
0x1401f0758  jz      short loc_1401F0788
0x1401f075a  mov     rax, [r15]
0x1401f075d  mov     r9, [rcx+40h]
0x1401f0761  mov     rcx, [rcx+18h]
0x1401f0765  mov     qword ptr [rsp+60h+var_20], rax
0x1401f076a  mov     [rsp+60h+var_28], rsi
0x1401f076f  mov     [rsp+60h+var_30], 33h ; '3'
0x1401f0776  mov     [rsp+60h+var_38], 8
0x1401f077e  mov     byte ptr [rsp+60h+var_40], 5
0x1401f0783  call    WPP_RECORDER_AND_TRACE_SF_q
0x1401f0788  lea     rdx, aSdprecord; "SdpRecord"
0x1401f078f  lea     rcx, [rbp+DestinationString]; DestinationString
0x1401f0793  call    cs:__imp_RtlInitUnicodeString
0x1401f079a  nop     dword ptr [rax+rax+00h]
0x1401f079f  lea     r8, [rbp+KeyHandle]; void **
0x1401f07a3  mov     rdx, r15; unsigned __int64 *
0x1401f07a6  call    ?SecDB_OpenDeviceKey@@YAJPEAU_SECURITY_DATABASE@@PEB_KPEAPEAX@Z; SecDB_OpenDeviceKey(_SECURITY_DATABASE *,unsigned __int64 const *,void * *)
0x1401f07ab  mov     ebx, eax
0x1401f07ad  test    eax, eax
0x1401f07af  jns     short loc_1401F07FD
0x1401f07b1  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401f07b8  mov     ecx, [rax+2Ch]
0x1401f07bb  test    cl, cl
0x1401f07bd  jns     short loc_1401F07C8
0x1401f07bf  cmp     byte ptr [rax+29h], 3
0x1401f07c3  mov     dl, dil
0x1401f07c6  jnb     short loc_1401F07CB
0x1401f07c8  mov     dl, r13b
0x1401f07cb  mov     r9, [rax+40h]
0x1401f07cf  mov     rcx, [rax+18h]
0x1401f07d3  mov     dword ptr [rsp+60h+var_20], ebx
0x1401f07d7  mov     [rsp+60h+var_28], rsi
0x1401f07dc  mov     [rsp+60h+var_30], 34h ; '4'
0x1401f07e3  mov     [rsp+60h+var_38], 8
0x1401f07eb  mov     byte ptr [rsp+60h+var_40], 3
0x1401f07f0  mov     r8b, dil
0x1401f07f3  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401f07f8  jmp     loc_1401F09FC
0x1401f07fd  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1401f0801  lea     rax, [rbp+arg_10]
0x1401f0805  xor     r9d, r9d
0x1401f0808  mov     [rsp+60h+var_40], rax; __int64
0x1401f080d  xor     r8d, r8d; void *
0x1401f0810  lea     rdx, [rbp+DestinationString]; ValueName
0x1401f0814  call    BthQueryKeyValueEx
0x1401f0819  mov     ebx, eax
0x1401f081b  cmp     eax, 0C0000023h
0x1401f0820  jz      short loc_1401F087F
0x1401f0822  cmp     eax, 80000005h
0x1401f0827  jz      short loc_1401F087F
0x1401f0829  mov     rsi, r13
0x1401f082c  test    eax, eax
0x1401f082e  jns     loc_1401F0964
0x1401f0834  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401f083b  mov     eax, [rcx+2Ch]
0x1401f083e  test    al, al
0x1401f0840  jns     short loc_1401F084B
0x1401f0842  cmp     byte ptr [rcx+29h], 3
0x1401f0846  mov     dl, dil
0x1401f0849  jnb     short loc_1401F084E
0x1401f084b  mov     dl, r13b
0x1401f084e  mov     dword ptr [rsp+60h+var_20], ebx
0x1401f0852  lea     rsi, WPP_1c8b0d14a8043465701df8be11446151_Traceguids
0x1401f0859  mov     [rsp+60h+var_28], rsi
0x1401f085e  mov     [rsp+60h+var_30], 37h ; '7'
0x1401f0865  mov     [rsp+60h+var_38], 8
0x1401f086d  mov     byte ptr [rsp+60h+var_40], 3
0x1401f0872  mov     r9, [rcx+40h]
0x1401f0876  mov     rcx, [rcx+18h]
0x1401f087a  jmp     loc_1401F07F0
0x1401f087f  mov     ebx, dword ptr [rbp+arg_10]
0x1401f0882  mov     ecx, 100h
0x1401f0887  mov     edx, ebx
0x1401f0889  mov     dword ptr [rbp+arg_10], ebx
0x1401f088c  mov     r8d, 50485442h
0x1401f0892  call    cs:__imp_ExAllocatePool2
0x1401f0899  nop     dword ptr [rax+rax+00h]
0x1401f089e  mov     rsi, rax
0x1401f08a1  test    rax, rax
0x1401f08a4  jnz     short loc_1401F08EB
0x1401f08a6  mov     ebx, 0C000009Ah
0x1401f08ab  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401f08b2  mov     eax, [rcx+2Ch]
0x1401f08b5  test    al, al
0x1401f08b7  jns     short loc_1401F08C2
0x1401f08b9  cmp     byte ptr [rcx+29h], 2
0x1401f08bd  mov     dl, dil
0x1401f08c0  jnb     short loc_1401F08C5
0x1401f08c2  mov     dl, r13b
0x1401f08c5  mov     dword ptr [rsp+60h+var_20], ebx
0x1401f08c9  lea     rsi, WPP_1c8b0d14a8043465701df8be11446151_Traceguids
0x1401f08d0  mov     [rsp+60h+var_28], rsi
0x1401f08d5  mov     [rsp+60h+var_30], 35h ; '5'
0x1401f08dc  mov     [rsp+60h+var_38], 8
0x1401f08e4  mov     byte ptr [rsp+60h+var_40], 2
0x1401f08e9  jmp     short loc_1401F0872
0x1401f08eb  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1401f08ef  lea     rax, [rbp+arg_10]
0x1401f08f3  mov     r9d, ebx
0x1401f08f6  mov     [rsp+60h+var_40], rax; __int64
0x1401f08fb  mov     r8, rsi; void *
0x1401f08fe  lea     rdx, [rbp+DestinationString]; ValueName
0x1401f0902  call    BthQueryKeyValueEx
0x1401f0907  mov     ebx, eax
0x1401f0909  test    eax, eax
0x1401f090b  jns     short loc_1401F0960
0x1401f090d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401f0914  mov     eax, [rcx+2Ch]
0x1401f0917  test    al, al
0x1401f0919  jns     short loc_1401F0924
0x1401f091b  cmp     byte ptr [rcx+29h], 2
0x1401f091f  mov     dl, dil
0x1401f0922  jnb     short loc_1401F0927
0x1401f0924  mov     dl, r13b
0x1401f0927  mov     r9, [rcx+40h]
0x1401f092b  lea     r8, WPP_1c8b0d14a8043465701df8be11446151_Traceguids
0x1401f0932  mov     rcx, [rcx+18h]
0x1401f0936  mov     dword ptr [rsp+60h+var_20], ebx
0x1401f093a  mov     [rsp+60h+var_28], r8
0x1401f093f  mov     r8b, dil
0x1401f0942  mov     [rsp+60h+var_30], 36h ; '6'
0x1401f0949  mov     [rsp+60h+var_38], 8
0x1401f0951  mov     byte ptr [rsp+60h+var_40], 2
0x1401f0956  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401f095b  jmp     loc_1401F09E4
0x1401f0960  mov     r14d, dword ptr [rbp+arg_10]
0x1401f0964  mov     r9d, r14d; unsigned int
0x1401f0967  mov     r8, rsi; unsigned __int8 *
0x1401f096a  mov     rdx, r15; unsigned __int64 *
0x1401f096d  mov     rcx, r12; struct _SDP_INTERFACE *
0x1401f0970  call    ?SdpInt_UpdateCacheWithFullRecord@@YAJPEAU_SDP_INTERFACE@@PEB_KPEAEK@Z; SdpInt_UpdateCacheWithFullRecord(_SDP_INTERFACE *,unsigned __int64 const *,uchar *,ulong)
0x1401f0975  mov     ebx, eax
0x1401f0977  test    eax, eax
0x1401f0979  jns     short loc_1401F09CB
0x1401f097b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401f0982  mov     eax, [rcx+2Ch]
0x1401f0985  test    al, al
0x1401f0987  jns     short loc_1401F0992
0x1401f0989  cmp     byte ptr [rcx+29h], 2
0x1401f098d  mov     dl, dil
0x1401f0990  jnb     short loc_1401F0995
0x1401f0992  mov     dl, r13b
0x1401f0995  mov     r9, [rcx+40h]
0x1401f0999  lea     r8, WPP_1c8b0d14a8043465701df8be11446151_Traceguids
0x1401f09a0  mov     rcx, [rcx+18h]
0x1401f09a4  mov     dword ptr [rsp+60h+var_20], ebx
0x1401f09a8  mov     [rsp+60h+var_28], r8
0x1401f09ad  mov     r8b, dil
0x1401f09b0  mov     [rsp+60h+var_30], 38h ; '8'
0x1401f09b7  mov     [rsp+60h+var_38], 8
0x1401f09bf  mov     byte ptr [rsp+60h+var_40], 2
0x1401f09c4  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401f09c9  jmp     short loc_1401F09DF
0x1401f09cb  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1401f09cf  lea     rdx, [rbp+DestinationString]; ValueName
0x1401f09d3  call    cs:__imp_ZwDeleteValueKey
0x1401f09da  nop     dword ptr [rax+rax+00h]
0x1401f09df  test    rsi, rsi
0x1401f09e2  jz      short loc_1401F09F5
0x1401f09e4  xor     edx, edx; Tag
0x1401f09e6  mov     rcx, rsi; P
0x1401f09e9  call    cs:__imp_ExFreePoolWithTag
0x1401f09f0  nop     dword ptr [rax+rax+00h]
0x1401f09f5  lea     rsi, WPP_1c8b0d14a8043465701df8be11446151_Traceguids
0x1401f09fc  mov     rcx, [rbp+KeyHandle]; Handle
0x1401f0a00  test    rcx, rcx
0x1401f0a03  jz      short loc_1401F0A11
0x1401f0a05  call    cs:__imp_ZwClose
0x1401f0a0c  nop     dword ptr [rax+rax+00h]
0x1401f0a11  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401f0a18  mov     eax, [rcx+2Ch]
0x1401f0a1b  test    al, al
0x1401f0a1d  jns     short loc_1401F0A25
0x1401f0a1f  cmp     byte ptr [rcx+29h], 5
0x1401f0a23  jnb     short loc_1401F0A28
0x1401f0a25  mov     dil, r13b
0x1401f0a28  movzx   eax, word ptr [rcx+48h]
0x1401f0a2c  test    ax, ax
0x1401f0a2f  setnz   r8b
0x1401f0a33  test    dil, dil
0x1401f0a36  jnz     short loc_1401F0A3D
0x1401f0a38  test    ax, ax
0x1401f0a3b  jz      short loc_1401F0A6A
0x1401f0a3d  mov     r9, [rcx+40h]
0x1401f0a41  mov     dl, dil
0x1401f0a44  mov     rcx, [rcx+18h]
0x1401f0a48  mov     dword ptr [rsp+60h+var_20], ebx
0x1401f0a4c  mov     [rsp+60h+var_28], rsi
0x1401f0a51  mov     [rsp+60h+var_30], 39h ; '9'
0x1401f0a58  mov     [rsp+60h+var_38], 8
0x1401f0a60  mov     byte ptr [rsp+60h+var_40], 5
0x1401f0a65  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401f0a6a  mov     eax, ebx
0x1401f0a6c  mov     rbx, [rsp+60h+arg_0]
0x1401f0a74  add     rsp, 60h
0x1401f0a78  pop     r15
0x1401f0a7a  pop     r14
0x1401f0a7c  pop     r13
0x1401f0a7e  pop     r12
0x1401f0a80  pop     rdi
0x1401f0a81  pop     rsi
0x1401f0a82  pop     rbp
0x1401f0a83  retn
```
