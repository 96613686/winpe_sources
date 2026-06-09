# MpRegCreateHardeningList

- ea: `0x140091e3c`
- end: `0x14009240d`
- name: `MpRegCreateHardeningList`
- size: `1489`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140092410`

## callees

- `0x1400026c0`
- `0x140003d20`
- `0x140003ed0`
- `0x1400051bc`
- `0x1400118d0`
- `0x14004b6d0`
- `0x14004fcd0`
- `0x14006c960`
- `0x140091e3c`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x14009224b`
- `ntoskrnl!ZwSetValueKey` at `0x14009224b`
- `ntoskrnl!ZwOpenKey` at `0x140091ef2`
- `ntoskrnl!ZwOpenKey` at `0x140092187`
- `ntoskrnl!ZwOpenKey` at `0x140091ef2`
- `ntoskrnl!ZwOpenKey` at `0x140092187`
- `ntoskrnl!ZwQueryValueKey` at `0x1400921c8`
- `ntoskrnl!ZwQueryValueKey` at `0x1400921c8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140091eae`
- `ntoskrnl!RtlInitUnicodeString` at `0x140091fef`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009207a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009214a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140091eae`
- `ntoskrnl!RtlInitUnicodeString` at `0x140091fef`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009207a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009214a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140092110`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140092110`
- `ntoskrnl!ZwClose` at `0x1400922bf`
- `ntoskrnl!ZwClose` at `0x1400923bc`
- `ntoskrnl!ZwClose` at `0x1400922bf`
- `ntoskrnl!ZwClose` at `0x1400923bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400920eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400920eb`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14009239c`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14009239c`
- `ntoskrnl!KeBugCheck` at `0x1400923f9`
- `ntoskrnl!KeBugCheck` at `0x1400923f9`
- `ntoskrnl!ObfDereferenceObject` at `0x14009236d`
- `ntoskrnl!ObfDereferenceObject` at `0x14009236d`

## string_xrefs

- `0x140091fe4`: `\Services\WinDefend`
- `0x140091e70`: `\Registry\Machine\SYSTEM\CurrentControlSet`

## pseudocode

```c
void MpRegCreateHardeningList()
{
  char v0; // r14
  NTSTATUS KeyName; // eax
  __int64 v2; // rdx
  unsigned int v3; // esi
  _QWORD *PoolWithTag; // rdi
  int appended; // eax
  NTSTATUS v6; // ecx
  NTSTATUS v7; // ecx
  NTSTATUS v8; // eax
  __int64 v9; // rdx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  NTSTATUS Length; // [rsp+28h] [rbp-E0h]
  struct _UNICODE_STRING *v13; // [rsp+38h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-C8h] BYREF
  PVOID Entry; // [rsp+48h] [rbp-C0h]
  PVOID Object; // [rsp+50h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+58h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES v19; // [rsp+90h] [rbp-78h] BYREF
  ULONG Data; // [rsp+C0h] [rbp-48h] BYREF
  UNICODE_STRING String1; // [rsp+C8h] [rbp-40h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+D8h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E8h] [rbp-20h] BYREF
  UNICODE_STRING String2; // [rsp+F8h] [rbp-10h] BYREF
  __int128 KeyValueInformation; // [rsp+108h] [rbp+0h] BYREF

  v13 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  String1 = 0;
  KeyHandle = 0;
  v0 = 0;
  DestinationString = 0;
  Entry = 0;
  Object = 0;
  String2 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  KeyName = ZwOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes);
  if ( KeyName < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v2 = 163;
LABEL_5:
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        v2,
        WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
        KeGetCurrentThread(),
        KeyName);
      goto LABEL_47;
    }
    goto LABEL_47;
  }
  KeyName = MpReferenceObjectByHandle((int)KeyHandle, 0x80000000, 0, 0, &Object);
  if ( KeyName >= 0 )
  {
    KeyName = MpRegpGetKeyName(Object);
    if ( KeyName < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        v2 = 165;
        goto LABEL_5;
      }
      goto LABEL_47;
    }
    RtlInitUnicodeString(&String2, L"\\Services\\WinDefend");
    v3 = 0;
    while ( 1 )
    {
      PoolWithTag = (_QWORD *)MpAllocatePoolWithTag(1, 32, 1952534605);
      if ( PoolWithTag )
      {
        RtlInitUnicodeString(&String1, (&off_140026340)[2 * v3]);
        appended = MpAppendUnicodeStringToUnicodeString(Entry, &String1, &v13, 1265782861);
        if ( appended >= 0 )
        {
          if ( !v0 && !RtlCompareUnicodeString(&String1, &String2, 1u) )
          {
            Data = 0;
            Handle = 0;
            *(&v19.Length + 1) = 0;
            ValueName = 0;
            *(&v19.Attributes + 1) = 0;
            v0 = 1;
            RtlInitUnicodeString(&ValueName, L"Start");
            v19.ObjectName = v13;
            v19.Length = 48;
            v19.RootDirectory = 0;
            *(_OWORD *)&v19.SecurityDescriptor = 0;
            v19.Attributes = 576;
            v6 = ZwOpenKey(&Handle, 0x2001Fu, &v19);
            if ( v6 < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                _mm_lfence();
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  171,
                  WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
                  KeGetCurrentThread(),
                  v6);
              }
            }
            else
            {
              KeyValueInformation = 0;
              v7 = ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &Data);
              if ( v7 < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                {
                  v9 = 170;
                  Length = v7;
LABEL_39:
                  _mm_lfence();
                  WPP_SF_qD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    v9,
                    WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
                    KeGetCurrentThread(),
                    Length);
                }
              }
              else if ( HIDWORD(KeyValueInformation) == 4 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                {
                  WPP_SF_q(
                    WPP_GLOBAL_Control->AttachedDevice,
                    168,
                    WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
                    KeGetCurrentThread());
                }
                Data = 3;
                v8 = ZwSetValueKey(Handle, &ValueName, 0, 4u, &Data, 4u);
                if ( v8 < 0
                  && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                {
                  v9 = 169;
                  Length = v8;
                  goto LABEL_39;
                }
              }
              ZwClose(Handle);
            }
          }
          PoolWithTag[2] = v13;
          v10 = (char *)MpRegData + 280;
          v13 = 0;
          v11 = *((_QWORD *)MpRegData + 35);
          if ( *(PVOID *)(v11 + 8) != (char *)MpRegData + 280 )
            __fastfail(3u);
          *PoolWithTag = v11;
          PoolWithTag[1] = v10;
          *(_QWORD *)(v11 + 8) = PoolWithTag;
          *v10 = PoolWithTag;
          goto LABEL_46;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            167,
            WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
            KeGetCurrentThread(),
            appended);
        }
        ExFreePoolWithTag(PoolWithTag, 0x7461504Du);
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          166,
          WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
          KeGetCurrentThread());
      }
LABEL_46:
      if ( ++v3 >= 8 )
        goto LABEL_47;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v2 = 164;
    goto LABEL_5;
  }
LABEL_47:
  if ( Entry )
  {
    MpRegpFreeKeyName(Entry);
    Entry = 0;
  }
  if ( Object )
  {
    ObfDereferenceObject(Object);
    if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
    {
      if ( KdRefreshDebuggerNotPresent() )
        KeBugCheck(1u);
      __debugbreak();
    }
    Object = 0;
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
}

```

## disassembly

```asm
0x140091e3c  mov     rax, rsp
0x140091e3f  mov     [rax+8], rbx
0x140091e43  mov     [rax+10h], rsi
0x140091e47  mov     [rax+18h], rdi
0x140091e4b  mov     [rax+20h], r12
0x140091e4f  push    rbp
0x140091e50  push    r14
0x140091e52  push    r15
0x140091e54  lea     rbp, [rax-38h]
0x140091e58  sub     rsp, 120h
0x140091e5f  mov     rax, cs:__security_cookie
0x140091e66  xor     rax, rsp
0x140091e69  mov     [rbp+30h+var_20], rax
0x140091e6d  xor     r15d, r15d
0x140091e70  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140091e77  xorps   xmm0, xmm0
0x140091e7a  mov     [rsp+130h+var_100], r15
0x140091e7f  xorps   xmm1, xmm1
0x140091e82  mov     dword ptr [rsp+130h+ObjectAttributes+4], r15d
0x140091e87  lea     rcx, [rbp+30h+DestinationString]; DestinationString
0x140091e8b  mov     dword ptr [rsp+130h+ObjectAttributes+1Ch], r15d
0x140091e90  movups  xmmword ptr [rbp+30h+String1.Length], xmm0
0x140091e94  mov     [rsp+130h+KeyHandle], r15
0x140091e99  mov     r14b, r15b
0x140091e9c  movups  xmmword ptr [rbp+30h+DestinationString.Length], xmm1
0x140091ea0  mov     [rsp+130h+Entry], r15
0x140091ea5  mov     [rsp+130h+Object], r15
0x140091eaa  movups  xmmword ptr [rbp+30h+String2.Length], xmm0
0x140091eae  call    cs:__imp_RtlInitUnicodeString
0x140091eb5  nop     dword ptr [rax+rax+00h]
0x140091eba  lea     rax, [rbp+30h+DestinationString]
0x140091ebe  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x140091ec6  xorps   xmm0, xmm0
0x140091ec9  mov     [rsp+130h+ObjectAttributes.ObjectName], rax
0x140091ece  mov     ebx, 80000000h
0x140091ed3  mov     [rsp+130h+ObjectAttributes.RootDirectory], r15
0x140091ed8  mov     edx, ebx; DesiredAccess
0x140091eda  mov     [rsp+130h+ObjectAttributes.Attributes], 240h
0x140091ee2  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x140091ee7  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x140091eec  movdqu  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x140091ef2  call    cs:__imp_ZwOpenKey
0x140091ef9  nop     dword ptr [rax+rax+00h]
0x140091efe  lea     r12d, [r15+1]
0x140091f02  test    eax, eax
0x140091f04  jns     short loc_140091F5A
0x140091f06  mov     rcx, cs:WPP_GLOBAL_Control
0x140091f0d  lea     rbx, WPP_GLOBAL_Control
0x140091f14  cmp     rcx, rbx
0x140091f17  jz      loc_14009234F
0x140091f1d  mov     ecx, [rcx+2Ch]
0x140091f20  test    r12b, cl
0x140091f23  jz      loc_14009234F
0x140091f29  mov     edx, 0A3h
0x140091f2e  lfence
0x140091f31  mov     r9, gs:188h
0x140091f3a  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x140091f41  mov     rcx, cs:WPP_GLOBAL_Control
0x140091f48  mov     [rsp+130h+Length], eax
0x140091f4c  mov     rcx, [rcx+18h]
0x140091f50  call    WPP_SF_qD
0x140091f55  jmp     loc_14009234F
0x140091f5a  mov     rcx, [rsp+130h+KeyHandle]; int
0x140091f5f  lea     rax, [rsp+130h+Object]
0x140091f64  xor     r9d, r9d; int
0x140091f67  mov     qword ptr [rsp+130h+Length], rax; PVOID *
0x140091f6c  xor     r8d, r8d; int
0x140091f6f  mov     edx, ebx; int
0x140091f71  call    MpReferenceObjectByHandle
0x140091f76  test    eax, eax
0x140091f78  jns     short loc_140091FA4
0x140091f7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140091f81  lea     rbx, WPP_GLOBAL_Control
0x140091f88  cmp     rcx, rbx
0x140091f8b  jz      loc_14009234F
0x140091f91  mov     ecx, [rcx+2Ch]
0x140091f94  test    r12b, cl
0x140091f97  jz      loc_14009234F
0x140091f9d  mov     edx, 0A4h
0x140091fa2  jmp     short loc_140091F2E
0x140091fa4  mov     rcx, [rsp+130h+Object]; Object
0x140091fa9  lea     rdx, [rsp+130h+Entry]
0x140091fae  call    MpRegpGetKeyName
0x140091fb3  test    eax, eax
0x140091fb5  jns     short loc_140091FE4
0x140091fb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140091fbe  lea     rbx, WPP_GLOBAL_Control
0x140091fc5  cmp     rcx, rbx
0x140091fc8  jz      loc_14009234F
0x140091fce  mov     ecx, [rcx+2Ch]
0x140091fd1  test    cl, 4
0x140091fd4  jz      loc_14009234F
0x140091fda  mov     edx, 0A5h
0x140091fdf  jmp     loc_140091F2E
0x140091fe4  lea     rdx, aServicesWindef; "\\Services\\WinDefend"
0x140091feb  lea     rcx, [rbp+30h+String2]; DestinationString
0x140091fef  call    cs:__imp_RtlInitUnicodeString
0x140091ff6  nop     dword ptr [rax+rax+00h]
0x140091ffb  mov     esi, r15d
0x140091ffe  lea     rbx, WPP_GLOBAL_Control
0x140092005  mov     edx, 20h ; ' '
0x14009200a  mov     r8d, 7461504Dh
0x140092010  mov     ecx, r12d
0x140092013  call    MpAllocatePoolWithTag
0x140092018  mov     rdi, rax
0x14009201b  test    rax, rax
0x14009201e  jnz     short loc_140092066
0x140092020  mov     rax, cs:WPP_GLOBAL_Control
0x140092027  cmp     rax, rbx
0x14009202a  jz      loc_140092343
0x140092030  mov     eax, [rax+2Ch]
0x140092033  test    r12b, al
0x140092036  jz      loc_140092343
0x14009203c  mov     r9, gs:188h
0x140092045  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14009204c  mov     rcx, cs:WPP_GLOBAL_Control
0x140092053  mov     edx, 0A6h
0x140092058  mov     rcx, [rcx+18h]
0x14009205c  call    WPP_SF_q
0x140092061  jmp     loc_140092343
0x140092066  lea     rax, off_140026340; "\\Services\\MpHardCodedBlockHive"
0x14009206d  mov     edx, esi
0x14009206f  add     rdx, rdx
0x140092072  lea     rcx, [rbp+30h+String1]; DestinationString
0x140092076  mov     rdx, [rax+rdx*8]; SourceString
0x14009207a  call    cs:__imp_RtlInitUnicodeString
0x140092081  nop     dword ptr [rax+rax+00h]
0x140092086  mov     rcx, [rsp+130h+Entry]
0x14009208b  lea     r8, [rsp+130h+var_100]
0x140092090  mov     r9d, 4B72504Dh
0x140092096  lea     rdx, [rbp+30h+String1]
0x14009209a  call    MpAppendUnicodeStringToUnicodeString
0x14009209f  test    eax, eax
0x1400920a1  jns     short loc_1400920FC
0x1400920a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400920aa  cmp     rcx, rbx
0x1400920ad  jz      short loc_1400920E3
0x1400920af  mov     ecx, [rcx+2Ch]
0x1400920b2  test    r12b, cl
0x1400920b5  jz      short loc_1400920E3
0x1400920b7  lfence
0x1400920ba  mov     r9, gs:188h
0x1400920c3  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x1400920ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400920d1  mov     edx, 0A7h
0x1400920d6  mov     [rsp+130h+Length], eax
0x1400920da  mov     rcx, [rcx+18h]
0x1400920de  call    WPP_SF_qD
0x1400920e3  mov     edx, 7461504Dh; Tag
0x1400920e8  mov     rcx, rdi; P
0x1400920eb  call    cs:__imp_ExFreePoolWithTag
0x1400920f2  nop     dword ptr [rax+rax+00h]
0x1400920f7  jmp     loc_140092343
0x1400920fc  test    r14b, r14b
0x1400920ff  jnz     loc_14009230D
0x140092105  mov     r8b, r12b; CaseInSensitive
0x140092108  lea     rdx, [rbp+30h+String2]; String2
0x14009210c  lea     rcx, [rbp+30h+String1]; String1
0x140092110  call    cs:__imp_RtlCompareUnicodeString
0x140092117  nop     dword ptr [rax+rax+00h]
0x14009211c  test    eax, eax
0x14009211e  jnz     loc_14009230D
0x140092124  xorps   xmm0, xmm0
0x140092127  mov     [rbp+30h+Data], r15d
0x14009212b  lea     rdx, aStart; "Start"
0x140092132  mov     [rsp+130h+Handle], r15
0x140092137  lea     rcx, [rbp+30h+ValueName]; DestinationString
0x14009213b  mov     dword ptr [rbp+30h+var_A8+4], r15d
0x14009213f  movups  xmmword ptr [rbp+30h+ValueName.Length], xmm0
0x140092143  mov     dword ptr [rbp+30h+var_A8+1Ch], r15d
0x140092147  mov     r14b, r12b
0x14009214a  call    cs:__imp_RtlInitUnicodeString
0x140092151  nop     dword ptr [rax+rax+00h]
0x140092156  mov     rax, [rsp+130h+var_100]
0x14009215b  lea     r8, [rbp+30h+var_A8]; ObjectAttributes
0x14009215f  xorps   xmm0, xmm0
0x140092162  mov     [rbp+30h+var_A8.ObjectName], rax
0x140092166  mov     edx, 2001Fh; DesiredAccess
0x14009216b  mov     [rbp+30h+var_A8.Length], 30h ; '0'
0x140092172  lea     rcx, [rsp+130h+Handle]; KeyHandle
0x140092177  mov     [rbp+30h+var_A8.RootDirectory], r15
0x14009217b  movdqu  xmmword ptr [rbp+30h+var_A8.SecurityDescriptor], xmm0
0x140092180  mov     [rbp+30h+var_A8.Attributes], 240h
0x140092187  call    cs:__imp_ZwOpenKey
0x14009218e  nop     dword ptr [rax+rax+00h]
0x140092193  mov     ecx, eax
0x140092195  test    eax, eax
0x140092197  js      loc_1400922CD
0x14009219d  mov     rcx, [rsp+130h+Handle]; KeyHandle
0x1400921a2  lea     rax, [rbp+30h+Data]
0x1400921a6  xorps   xmm0, xmm0
0x1400921a9  mov     [rsp+130h+ResultLength], rax; ResultLength
0x1400921ae  lea     r9, [rbp+30h+KeyValueInformation]; KeyValueInformation
0x1400921b2  mov     [rsp+130h+Length], 10h; Length
0x1400921ba  mov     r8d, 2; KeyValueInformationClass
0x1400921c0  lea     rdx, [rbp+30h+ValueName]; ValueName
0x1400921c4  movups  [rbp+30h+KeyValueInformation], xmm0
0x1400921c8  call    cs:__imp_ZwQueryValueKey
0x1400921cf  nop     dword ptr [rax+rax+00h]
0x1400921d4  mov     ecx, eax
0x1400921d6  test    eax, eax
0x1400921d8  js      loc_14009227A
0x1400921de  cmp     dword ptr [rbp+30h+KeyValueInformation+0Ch], 4
0x1400921e2  jnz     loc_1400922BA
0x1400921e8  mov     rax, cs:WPP_GLOBAL_Control
0x1400921ef  cmp     rax, rbx
0x1400921f2  jz      short loc_140092221
0x1400921f4  mov     eax, [rax+2Ch]
0x1400921f7  test    r12b, al
0x1400921fa  jz      short loc_140092221
0x1400921fc  mov     r9, gs:188h
0x140092205  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14009220c  mov     rcx, cs:WPP_GLOBAL_Control
0x140092213  mov     edx, 0A8h
0x140092218  mov     rcx, [rcx+18h]
0x14009221c  call    WPP_SF_q
0x140092221  mov     rcx, [rsp+130h+Handle]; KeyHandle
0x140092226  lea     rax, [rbp+30h+Data]
0x14009222a  mov     dword ptr [rsp+130h+ResultLength], 4; DataSize
0x140092232  lea     rdx, [rbp+30h+ValueName]; ValueName
0x140092236  mov     r9d, 4; Type
0x14009223c  mov     qword ptr [rsp+130h+Length], rax; Data
0x140092241  xor     r8d, r8d; TitleIndex
0x140092244  mov     [rbp+30h+Data], 3
0x14009224b  call    cs:__imp_ZwSetValueKey
0x140092252  nop     dword ptr [rax+rax+00h]
0x140092257  test    eax, eax
0x140092259  jns     short loc_1400922BA
0x14009225b  mov     rcx, cs:WPP_GLOBAL_Control
0x140092262  cmp     rcx, rbx
0x140092265  jz      short loc_1400922BA
0x140092267  mov     ecx, [rcx+2Ch]
0x14009226a  test    r12b, cl
0x14009226d  jz      short loc_1400922BA
0x14009226f  mov     edx, 0A9h
0x140092274  mov     [rsp+130h+Length], eax
0x140092278  jmp     short loc_140092297
0x14009227a  mov     rax, cs:WPP_GLOBAL_Control
0x140092281  cmp     rax, rbx
0x140092284  jz      short loc_1400922BA
0x140092286  mov     eax, [rax+2Ch]
0x140092289  test    r12b, al
0x14009228c  jz      short loc_1400922BA
0x14009228e  mov     edx, 0AAh
0x140092293  mov     [rsp+130h+Length], ecx
0x140092297  lfence
0x14009229a  mov     r9, gs:188h
0x1400922a3  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x1400922aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400922b1  mov     rcx, [rcx+18h]
0x1400922b5  call    WPP_SF_qD
0x1400922ba  mov     rcx, [rsp+130h+Handle]; Handle
0x1400922bf  call    cs:__imp_ZwClose
0x1400922c6  nop     dword ptr [rax+rax+00h]
0x1400922cb  jmp     short loc_14009230D
0x1400922cd  mov     rax, cs:WPP_GLOBAL_Control
0x1400922d4  cmp     rax, rbx
0x1400922d7  jz      short loc_14009230D
0x1400922d9  mov     eax, [rax+2Ch]
0x1400922dc  test    r12b, al
0x1400922df  jz      short loc_14009230D
0x1400922e1  lfence
0x1400922e4  mov     r9, gs:188h
0x1400922ed  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x1400922f4  mov     [rsp+130h+Length], ecx
0x1400922f8  mov     edx, 0ABh
0x1400922fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140092304  mov     rcx, [rcx+18h]
0x140092308  call    WPP_SF_qD
0x14009230d  mov     rax, [rsp+130h+var_100]
0x140092312  mov     [rdi+10h], rax
0x140092316  mov     rax, cs:MpRegData
0x14009231d  add     rax, 118h
0x140092323  mov     [rsp+130h+var_100], r15
0x140092328  mov     rcx, [rax]
0x14009232b  cmp     [rcx+8], rax
0x14009232f  jnz     loc_140092406
0x140092335  mov     [rdi], rcx
0x140092338  mov     [rdi+8], rax
0x14009233c  mov     [rcx+8], rdi
0x140092340  mov     [rax], rdi
0x140092343  add     esi, r12d
0x140092346  cmp     esi, 8
0x140092349  jb      loc_140092005
0x14009234f  mov     rcx, [rsp+130h+Entry]; Entry
0x140092354  test    rcx, rcx
0x140092357  jz      short loc_140092363
0x140092359  call    MpRegpFreeKeyName
0x14009235e  mov     [rsp+130h+Entry], r15
0x140092363  mov     rcx, [rsp+130h+Object]; Object
0x140092368  test    rcx, rcx
0x14009236b  jz      short loc_1400923B2
0x14009236d  call    cs:__imp_ObfDereferenceObject
0x140092374  nop     dword ptr [rax+rax+00h]
0x140092379  or      rax, 0FFFFFFFFFFFFFFFFh
0x14009237d  lock xadd cs:ObTotalReferences, rax
0x140092386  cmp     rax, r12
0x140092389  jns     short loc_1400923AD
0x14009238b  mov     rax, cs:MpData
0x140092392  mov     ecx, [rax+364h]
  ... truncated ...
```
