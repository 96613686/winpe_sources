# NetioNcmStoreBaseSupportedSlots

- ea: `0x140042fc0`
- end: `0x14004345a`
- name: `NetioNcmStoreBaseSupportedSlots`
- size: `1178`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x140042d60`
- `0x140042fc0`
- `0x140050b00`
- `0x140050ea4`
- `0x14005bd80`
- `0x140077fa0`
- `0x140078100`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1400431b5`
- `ntoskrnl!ZwQueryValueKey` at `0x14004321f`
- `ntoskrnl!ZwQueryValueKey` at `0x1400431b5`
- `ntoskrnl!ZwQueryValueKey` at `0x14004321f`
- `ntoskrnl!ZwClose` at `0x14004334f`
- `ntoskrnl!ZwClose` at `0x14004334f`
- `ntoskrnl!ZwOpenKey` at `0x140043152`
- `ntoskrnl!ZwOpenKey` at `0x140043152`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140043043`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140043043`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400432fe`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400433fd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400432fe`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400433fd`
- `ntoskrnl!ExAllocatePool2` at `0x1400431e4`
- `ntoskrnl!ExAllocatePool2` at `0x140043252`
- `ntoskrnl!ExAllocatePool2` at `0x1400431e4`
- `ntoskrnl!ExAllocatePool2` at `0x140043252`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140043321`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140043422`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140043321`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140043422`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043285`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043335`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043285`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043335`
- `ntoskrnl!RtlInitUnicodeString` at `0x140043111`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004318c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140043111`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004318c`

## string_xrefs

- `0x14004301f`: `\Registry\Machine\System\CurrentControlSet\Services\NcbService\NCB`
- `0x140043096`: `\Registry\Machine\System\CurrentControlSet\Services\NcbService\NCB`
- `0x14004303c`: `NetworkConnectionBroker`

## pseudocode

```c
void __fastcall NetioNcmStoreBaseSupportedSlots(int a1)
{
  int PersistedStateLocation; // eax
  NTSTATUS v2; // eax
  void *v3; // r14
  int *v4; // rbx
  NTSTATUS v5; // eax
  NTSTATUS v6; // esi
  _DWORD *Pool2; // rdi
  unsigned int v8; // eax
  int *v9; // rax
  unsigned __int64 v10; // r9
  __int64 v11; // rcx
  NTSTATUS v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SourceString[256]; // [rsp+B0h] [rbp-50h] BYREF

  v17 = a1;
  KeyHandle = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !byte_14009B06C )
    return;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"NetworkConnectionBroker",
                             0,
                             L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\NcbService\\NCB",
                             0,
                             SourceString,
                             512,
                             0);
  if ( PersistedStateLocation < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        57,
        WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids,
        (unsigned int)PersistedStateLocation);
    }
    wcscpy(SourceString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\NcbServiceNCB");
  }
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(&KeyHandle, 0x40000001u, &ObjectAttributes);
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        60,
        WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids,
        (unsigned int)v2);
    }
    goto LABEL_43;
  }
  v3 = KeyHandle;
  ResultLength = 0;
  v4 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtcBaseSystemSlotNumber");
  v5 = ZwQueryValueKey(v3, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
  v6 = v5;
  if ( v5 == -2147483643 || v5 == -1073741789 )
  {
    Pool2 = (_DWORD *)ExAllocatePool2(64, ResultLength, 1835232846);
    if ( !Pool2 )
    {
LABEL_33:
      v12 = NetioWriteKey(KeyHandle, L"RtcBaseSystemSlotNumber", 4u, &v17, 4u);
      if ( v12 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          59,
          WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids,
          (unsigned int)v12);
      }
      NetioCloseKey(&KeyHandle, v13, v14, v15);
LABEL_43:
      KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
      while ( dword_14009B060 )
        ;
      dword_14009B090 = v17;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      return;
    }
    v6 = ZwQueryValueKey(v3, &DestinationString, KeyValuePartialInformation, Pool2, ResultLength, &ResultLength);
    if ( v6 >= 0 )
    {
      if ( Pool2[1] == 4 )
      {
        v8 = Pool2[2];
        if ( v8 )
        {
          v9 = (int *)ExAllocatePool2(64, v8, 1835232846);
          v4 = v9;
          if ( v9 )
            memmove(v9, Pool2 + 3, (unsigned int)Pool2[2]);
          else
            v6 = -1073741801;
        }
      }
      else
      {
        v6 = -1073741788;
      }
    }
    ExFreePoolWithTag(Pool2, 0x6D636E4Eu);
  }
  if ( v6 < 0 || !v4 )
    goto LABEL_33;
  v10 = (unsigned int)*v4;
  if ( (unsigned int)v10 > 0x20 || (v11 = 0x100410000LL, !_bittest64(&v11, v10)) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids, v10, 16);
    }
    *v4 = 16;
  }
  KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
  while ( dword_14009B060 )
    ;
  dword_14009B090 = *v4;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  ExFreePoolWithTag(v4, 0x6D636E4Eu);
  if ( KeyHandle )
    ZwClose(KeyHandle);
}

```

## disassembly

```asm
0x140042fc0  mov     [rsp-8+arg_8], rbx
0x140042fc5  mov     [rsp-8+arg_10], rsi
0x140042fca  push    rbp
0x140042fcb  push    rdi
0x140042fcc  push    r12
0x140042fce  push    r13
0x140042fd0  push    r14
0x140042fd2  lea     rbp, [rsp-1C0h]
0x140042fda  sub     rsp, 2C0h
0x140042fe1  mov     rax, cs:__security_cookie
0x140042fe8  xor     rax, rsp
0x140042feb  mov     [rbp+1E0h+var_30], rax
0x140042ff2  xor     eax, eax
0x140042ff4  mov     [rsp+2E0h+var_298], ecx
0x140042ff8  cmp     cs:byte_14009B06C, al
0x140042ffe  xorps   xmm0, xmm0
0x140043001  mov     [rsp+2E0h+KeyHandle], 0
0x14004300a  movups  xmmword ptr [rsp+2E0h+LockHandle.LockQueue.Next], xmm0
0x14004300f  mov     qword ptr [rsp+2E0h+LockHandle.OldIrql], rax
0x140043014  jz      loc_14004342E
0x14004301a  mov     [rsp+2E0h+var_2B0], rax
0x14004301f  lea     r8, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140043026  lea     rax, [rbp+1E0h+SourceString]
0x14004302a  mov     dword ptr [rsp+2E0h+ResultLength], 200h
0x140043032  xor     r9d, r9d
0x140043035  mov     qword ptr [rsp+2E0h+Length], rax
0x14004303a  xor     edx, edx
0x14004303c  lea     rcx, aNetworkconnect; "NetworkConnectionBroker"
0x140043043  call    cs:__imp_RtlGetPersistedStateLocation
0x14004304a  nop     dword ptr [rax+rax+00h]
0x14004304f  lea     r13, WPP_GLOBAL_Control
0x140043056  mov     r9d, eax
0x140043059  test    eax, eax
0x14004305b  jns     loc_1400430F2
0x140043061  mov     rcx, cs:WPP_GLOBAL_Control
0x140043068  cmp     rcx, r13
0x14004306b  jz      short loc_14004308F
0x14004306d  cmp     byte ptr [rcx+29h], 3
0x140043071  jb      short loc_14004308F
0x140043073  bt      dword ptr [rcx+2Ch], 15h
0x140043078  jnb     short loc_14004308F
0x14004307a  mov     rcx, [rcx+18h]
0x14004307e  lea     r8, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids
0x140043085  mov     edx, 39h ; '9'
0x14004308a  call    WPP_SF_d
0x14004308f  movaps  xmm1, xmmword ptr cs:aRegistryMachin+10h; "y\\Machine\\System\\CurrentControlSet\\"...
0x140043096  movaps  xmm0, xmmword ptr cs:aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14004309d  mov     rax, qword ptr cs:aRegistryMachin+7Eh; "NCB"
0x1400430a4  movups  [rbp+1E0h+var_220], xmm1
0x1400430a8  movaps  xmm1, xmmword ptr cs:aRegistryMachin+30h; "\\CurrentControlSet\\Services\\NcbServi"...
0x1400430af  movups  xmmword ptr [rbp+1E0h+SourceString], xmm0
0x1400430b3  movaps  xmm0, xmmword ptr cs:aRegistryMachin+20h; "e\\System\\CurrentControlSet\\Services"...
0x1400430ba  movups  [rbp+1E0h+var_200], xmm1
0x1400430be  movaps  xmm1, xmmword ptr cs:aRegistryMachin+50h; "et\\Services\\NcbService\\NCB"
0x1400430c5  movups  [rbp+1E0h+var_210], xmm0
0x1400430c9  movaps  xmm0, xmmword ptr cs:aRegistryMachin+40h; "ControlSet\\Services\\NcbService\\NCB"
0x1400430d0  movups  [rbp+1E0h+var_1E0], xmm1
0x1400430d4  movaps  xmm1, xmmword ptr cs:aRegistryMachin+70h; "ervice\\NCB"
0x1400430db  movups  [rbp+1E0h+var_1F0], xmm0
0x1400430df  movaps  xmm0, xmmword ptr cs:aRegistryMachin+60h; "ces\\NcbService\\NCB"
0x1400430e6  movups  [rbp+1E0h+var_1C0], xmm1
0x1400430ea  mov     qword ptr [rbp+1E0h+var_1C0+0Eh], rax
0x1400430ee  movups  [rbp+1E0h+var_1D0], xmm0
0x1400430f2  xorps   xmm0, xmm0
0x1400430f5  lea     rdx, [rbp+1E0h+SourceString]; SourceString
0x1400430f9  movups  xmmword ptr [rbp+1E0h+ObjectAttributes.ObjectName], xmm0
0x1400430fd  xor     eax, eax
0x1400430ff  lea     rcx, [rsp+2E0h+DestinationString]; DestinationString
0x140043104  movups  xmmword ptr [rbp+1E0h+ObjectAttributes+1Ch], xmm0
0x140043108  movups  xmmword ptr [rsp+2E0h+DestinationString.Length], xmm0
0x14004310d  movups  xmmword ptr [rbp+1E0h+ObjectAttributes.Length], xmm0
0x140043111  call    cs:__imp_RtlInitUnicodeString
0x140043118  nop     dword ptr [rax+rax+00h]
0x14004311d  lea     rax, [rsp+2E0h+DestinationString]
0x140043122  mov     [rbp+1E0h+ObjectAttributes.Length], 30h ; '0'
0x140043129  xorps   xmm0, xmm0
0x14004312c  mov     [rbp+1E0h+ObjectAttributes.ObjectName], rax
0x140043130  lea     r8, [rbp+1E0h+ObjectAttributes]; ObjectAttributes
0x140043134  mov     [rbp+1E0h+ObjectAttributes.RootDirectory], 0
0x14004313c  mov     edx, 40000001h; DesiredAccess
0x140043141  mov     [rbp+1E0h+ObjectAttributes.Attributes], 240h
0x140043148  lea     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x14004314d  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140043152  call    cs:__imp_ZwOpenKey
0x140043159  nop     dword ptr [rax+rax+00h]
0x14004315e  mov     r9d, eax
0x140043161  test    eax, eax
0x140043163  js      loc_1400433C3
0x140043169  mov     r14, [rsp+2E0h+KeyHandle]
0x14004316e  lea     rdx, aRtcbasesystems; "RtcBaseSystemSlotNumber"
0x140043175  xorps   xmm0, xmm0
0x140043178  mov     [rsp+2E0h+var_2A0], 0
0x140043180  lea     rcx, [rsp+2E0h+DestinationString]; DestinationString
0x140043185  xor     ebx, ebx
0x140043187  movups  xmmword ptr [rsp+2E0h+DestinationString.Length], xmm0
0x14004318c  call    cs:__imp_RtlInitUnicodeString
0x140043193  nop     dword ptr [rax+rax+00h]
0x140043198  lea     rax, [rsp+2E0h+var_2A0]
0x14004319d  xor     r9d, r9d; KeyValueInformation
0x1400431a0  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x1400431a5  lea     r8d, [rbx+2]; KeyValueInformationClass
0x1400431a9  lea     rdx, [rsp+2E0h+DestinationString]; ValueName
0x1400431ae  mov     [rsp+2E0h+Length], ebx; Length
0x1400431b2  mov     rcx, r14; KeyHandle
0x1400431b5  call    cs:__imp_ZwQueryValueKey
0x1400431bc  nop     dword ptr [rax+rax+00h]
0x1400431c1  mov     esi, eax
0x1400431c3  cmp     eax, 80000005h
0x1400431c8  jz      short loc_1400431D5
0x1400431ca  cmp     eax, 0C0000023h
0x1400431cf  jnz     loc_140043291
0x1400431d5  mov     edx, [rsp+2E0h+var_2A0]
0x1400431d9  mov     ecx, 40h ; '@'
0x1400431de  mov     r8d, 6D636E4Eh
0x1400431e4  call    cs:__imp_ExAllocatePool2
0x1400431eb  nop     dword ptr [rax+rax+00h]
0x1400431f0  mov     rdi, rax
0x1400431f3  test    rax, rax
0x1400431f6  jz      loc_140043360
0x1400431fc  mov     edx, [rsp+2E0h+var_2A0]
0x140043200  lea     rax, [rsp+2E0h+var_2A0]
0x140043205  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x14004320a  mov     r9, rdi; KeyValueInformation
0x14004320d  mov     [rsp+2E0h+Length], edx; Length
0x140043211  mov     r8d, 2; KeyValueInformationClass
0x140043217  lea     rdx, [rsp+2E0h+DestinationString]; ValueName
0x14004321c  mov     rcx, r14; KeyHandle
0x14004321f  call    cs:__imp_ZwQueryValueKey
0x140043226  nop     dword ptr [rax+rax+00h]
0x14004322b  mov     esi, eax
0x14004322d  test    eax, eax
0x14004322f  js      short loc_14004327D
0x140043231  cmp     dword ptr [rdi+4], 4
0x140043235  jz      short loc_14004323E
0x140043237  mov     esi, 0C0000024h
0x14004323c  jmp     short loc_14004327D
0x14004323e  mov     eax, [rdi+8]
0x140043241  test    eax, eax
0x140043243  jz      short loc_14004327D
0x140043245  mov     edx, eax
0x140043247  mov     ecx, 40h ; '@'
0x14004324c  mov     r8d, 6D636E4Eh
0x140043252  call    cs:__imp_ExAllocatePool2
0x140043259  nop     dword ptr [rax+rax+00h]
0x14004325e  mov     rbx, rax
0x140043261  test    rax, rax
0x140043264  jnz     short loc_14004326D
0x140043266  mov     esi, 0C0000017h
0x14004326b  jmp     short loc_14004327D
0x14004326d  mov     r8d, [rdi+8]; Size
0x140043271  lea     rdx, [rdi+0Ch]; Src
0x140043275  mov     rcx, rax; void *
0x140043278  call    memmove
0x14004327d  mov     edx, 6D636E4Eh; Tag
0x140043282  mov     rcx, rdi; P
0x140043285  call    cs:__imp_ExFreePoolWithTag
0x14004328c  nop     dword ptr [rax+rax+00h]
0x140043291  test    esi, esi
0x140043293  js      loc_140043360
0x140043299  test    rbx, rbx
0x14004329c  jz      loc_140043360
0x1400432a2  mov     r9d, [rbx]
0x1400432a5  cmp     r9d, 20h ; ' '
0x1400432a9  ja      short loc_1400432BB
0x1400432ab  mov     rcx, 100410000h
0x1400432b5  bt      rcx, r9
0x1400432b9  jb      short loc_1400432F2
0x1400432bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400432c2  mov     edi, 10h
0x1400432c7  cmp     rcx, r13
0x1400432ca  jz      short loc_1400432F0
0x1400432cc  cmp     byte ptr [rcx+29h], 2
0x1400432d0  jb      short loc_1400432F0
0x1400432d2  bt      dword ptr [rcx+2Ch], 15h
0x1400432d7  jnb     short loc_1400432F0
0x1400432d9  mov     rcx, [rcx+18h]
0x1400432dd  lea     edx, [rdi+2Ah]
0x1400432e0  lea     r8, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids
0x1400432e7  mov     [rsp+2E0h+Length], edi
0x1400432eb  call    WPP_SF_Dd
0x1400432f0  mov     [rbx], edi
0x1400432f2  lea     rdx, [rsp+2E0h+LockHandle]; LockHandle
0x1400432f7  lea     rcx, SpinLock; SpinLock
0x1400432fe  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140043305  nop     dword ptr [rax+rax+00h]
0x14004330a  mov     eax, cs:dword_14009B060
0x140043310  test    eax, eax
0x140043312  jnz     short loc_14004330A
0x140043314  mov     eax, [rbx]
0x140043316  lea     rcx, [rsp+2E0h+LockHandle]; LockHandle
0x14004331b  mov     cs:dword_14009B090, eax
0x140043321  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140043328  nop     dword ptr [rax+rax+00h]
0x14004332d  mov     edx, 6D636E4Eh; Tag
0x140043332  mov     rcx, rbx; P
0x140043335  call    cs:__imp_ExFreePoolWithTag
0x14004333c  nop     dword ptr [rax+rax+00h]
0x140043341  mov     rcx, [rsp+2E0h+KeyHandle]; Handle
0x140043346  test    rcx, rcx
0x140043349  jz      loc_14004342E
0x14004334f  call    cs:__imp_ZwClose
0x140043356  nop     dword ptr [rax+rax+00h]
0x14004335b  jmp     loc_14004342E
0x140043360  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x140043365  lea     r9, [rsp+2E0h+var_298]
0x14004336a  mov     eax, 4
0x14004336f  lea     rdx, aRtcbasesystems; "RtcBaseSystemSlotNumber"
0x140043376  mov     r8d, eax
0x140043379  mov     [rsp+2E0h+Length], eax; ULONG
0x14004337d  call    NetioWriteKey
0x140043382  test    eax, eax
0x140043384  jns     short loc_1400433B7
0x140043386  mov     rcx, cs:WPP_GLOBAL_Control
0x14004338d  cmp     rcx, r13
0x140043390  jz      short loc_1400433B7
0x140043392  cmp     byte ptr [rcx+29h], 3
0x140043396  jb      short loc_1400433B7
0x140043398  bt      dword ptr [rcx+2Ch], 15h
0x14004339d  jnb     short loc_1400433B7
0x14004339f  mov     rcx, [rcx+18h]
0x1400433a3  lea     r8, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids
0x1400433aa  mov     edx, 3Bh ; ';'
0x1400433af  mov     r9d, eax
0x1400433b2  call    WPP_SF_d
0x1400433b7  lea     rcx, [rsp+2E0h+KeyHandle]
0x1400433bc  call    NetioCloseKey
0x1400433c1  jmp     short loc_1400433F1
0x1400433c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400433ca  cmp     rcx, r13
0x1400433cd  jz      short loc_1400433F1
0x1400433cf  cmp     byte ptr [rcx+29h], 3
0x1400433d3  jb      short loc_1400433F1
0x1400433d5  bt      dword ptr [rcx+2Ch], 15h
0x1400433da  jnb     short loc_1400433F1
0x1400433dc  mov     rcx, [rcx+18h]
0x1400433e0  lea     r8, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids
0x1400433e7  mov     edx, 3Ch ; '<'
0x1400433ec  call    WPP_SF_d
0x1400433f1  lea     rdx, [rsp+2E0h+LockHandle]; LockHandle
0x1400433f6  lea     rcx, SpinLock; SpinLock
0x1400433fd  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140043404  nop     dword ptr [rax+rax+00h]
0x140043409  mov     eax, cs:dword_14009B060
0x14004340f  test    eax, eax
0x140043411  jnz     short loc_140043409
0x140043413  mov     eax, [rsp+2E0h+var_298]
0x140043417  lea     rcx, [rsp+2E0h+LockHandle]; LockHandle
0x14004341c  mov     cs:dword_14009B090, eax
0x140043422  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140043429  nop     dword ptr [rax+rax+00h]
0x14004342e  mov     rcx, [rbp+1E0h+var_30]
0x140043435  xor     rcx, rsp; StackCookie
0x140043438  call    __security_check_cookie
0x14004343d  lea     r11, [rsp+2E0h+var_20]
0x140043445  mov     rbx, [r11+38h]
0x140043449  mov     rsi, [r11+40h]
0x14004344d  mov     rsp, r11
0x140043450  pop     r14
0x140043452  pop     r13
0x140043454  pop     r12
0x140043456  pop     rdi
0x140043457  pop     rbp
0x140043458  retn
```
