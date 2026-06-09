# HCI_RemoveUnpairedDeviceKeyAndSubkeys(DEVICE_INFO_BLOCK *,bool,bool)

- ea: `0x1401e8f5c`
- end: `0x1401e9192`
- name: `?HCI_RemoveUnpairedDeviceKeyAndSubkeys@@YAXPEAUDEVICE_INFO_BLOCK@@_N1@Z`
- size: `566`
- prototype: `void __fastcall(struct DEVICE_INFO_BLOCK *, bool, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14005de64`
- `0x1401e629c`

## callees

- `0x140165540`
- `0x1401be354`
- `0x1401c18d0`
- `0x1401c1c04`
- `0x1401e8f5c`
- `0x14020934c`

## import_xrefs

- `ntoskrnl!ZwQueryKey` at `0x1401e90ae`
- `ntoskrnl!ZwQueryKey` at `0x1401e90ae`
- `ntoskrnl!ZwDeleteKey` at `0x1401e9019`
- `ntoskrnl!ZwDeleteKey` at `0x1401e9122`
- `ntoskrnl!ZwDeleteKey` at `0x1401e9159`
- `ntoskrnl!ZwDeleteKey` at `0x1401e9019`
- `ntoskrnl!ZwDeleteKey` at `0x1401e9122`
- `ntoskrnl!ZwDeleteKey` at `0x1401e9159`
- `ntoskrnl!ZwClose` at `0x1401e902d`
- `ntoskrnl!ZwClose` at `0x1401e9074`
- `ntoskrnl!ZwClose` at `0x1401e9134`
- `ntoskrnl!ZwClose` at `0x1401e9169`
- `ntoskrnl!ZwClose` at `0x1401e902d`
- `ntoskrnl!ZwClose` at `0x1401e9074`
- `ntoskrnl!ZwClose` at `0x1401e9134`
- `ntoskrnl!ZwClose` at `0x1401e9169`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401e9044`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401e90fa`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401e9044`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401e90fa`

## string_xrefs

- `0x1401e9039`: `DynamicCachedServices`
- `0x1401e90ef`: `CachedServices`

## pseudocode

```c
void __fastcall HCI_RemoveUnpairedDeviceKeyAndSubkeys(struct DEVICE_INFO_BLOCK *a1, char a2, char a3)
{
  char v6; // di
  char v7; // bl
  int v8; // eax
  NTSTATUS v9; // ebx
  HANDLE v10; // [rsp+30h] [rbp-49h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-41h] BYREF
  HANDLE KeyHandle; // [rsp+40h] [rbp-39h] BYREF
  HANDLE v13; // [rsp+48h] [rbp-31h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-21h] BYREF
  __int128 KeyInformation; // [rsp+68h] [rbp-11h] BYREF
  __int128 v17; // [rsp+78h] [rbp-1h]
  __int128 v18; // [rsp+88h] [rbp+Fh]

  v10 = 0;
  KeyHandle = 0;
  v13 = 0;
  Handle = 0;
  ResultLength = 0;
  DestinationString = 0;
  KeyInformation = 0;
  v17 = 0;
  v18 = 0;
  if ( (int)HCI_GetDeviceKey(&a1->DeviceInfo.address, &v10, 0) >= 0 )
  {
    v6 = 0;
    v7 = 0;
    if ( (int)HCI_GetServicesForKey(v10, a1->Hci, &KeyHandle, 0) >= 0 )
    {
      if ( (a3 || a2) && (HCI_DeleteAllSubkeys(KeyHandle), a3) )
        ZwDeleteKey(KeyHandle);
      else
        v7 = 1;
      ZwClose(KeyHandle);
    }
    RtlInitUnicodeString(&DestinationString, L"DynamicCachedServices");
    if ( (int)BthOpenKeyEx(v10, &DestinationString, &Handle, 512) >= 0 )
    {
      v6 = 1;
      ZwClose(Handle);
    }
    KeyInformation = 0;
    ResultLength = 48;
    v17 = 0;
    v18 = 0;
    if ( ZwQueryKey(v10, KeyFullInformation, &KeyInformation, 0x30u, &ResultLength) < 0 )
      goto LABEL_26;
    if ( !a2 )
      goto LABEL_23;
    v8 = DWORD1(v17);
    if ( DWORD1(v17) != 1 && (DWORD1(v17) != 2 || !v6 && !v7) )
    {
      if ( DWORD1(v17) != 3 )
        goto LABEL_24;
      if ( !v6 || !v7 )
        goto LABEL_26;
    }
    RtlInitUnicodeString(&DestinationString, L"CachedServices");
    if ( (int)BthOpenKeyEx(v10, &DestinationString, &v13, 512) >= 0 && (v9 = ZwDeleteKey(v13), ZwClose(v13), v9 >= 0) )
      v8 = --DWORD1(v17);
    else
LABEL_23:
      v8 = DWORD1(v17);
LABEL_24:
    if ( !v8 )
      ZwDeleteKey(v10);
LABEL_26:
    ZwClose(v10);
  }
}

```

## disassembly

```asm
0x1401e8f5c  push    rbp
0x1401e8f5e  push    rbx
0x1401e8f5f  push    rsi
0x1401e8f60  push    rdi
0x1401e8f61  push    r14
0x1401e8f63  push    r15
0x1401e8f65  lea     rbp, [rsp-2Fh]
0x1401e8f6a  sub     rsp, 0A8h
0x1401e8f71  mov     rax, cs:__security_cookie
0x1401e8f78  xor     rax, rsp
0x1401e8f7b  mov     [rbp+57h+var_38], rax
0x1401e8f7f  xorps   xmm1, xmm1
0x1401e8f82  mov     [rbp+57h+var_A0], 0
0x1401e8f8a  mov     sil, r8b
0x1401e8f8d  mov     [rbp+57h+KeyHandle], 0
0x1401e8f95  mov     r14b, dl
0x1401e8f98  mov     [rbp+57h+var_88], 0
0x1401e8fa0  mov     r15, rcx
0x1401e8fa3  mov     [rbp+57h+Handle], 0
0x1401e8fab  xorps   xmm0, xmm0
0x1401e8fae  mov     [rbp+57h+var_98], 0
0x1401e8fb5  add     rcx, 20h ; ' '; unsigned __int64 *
0x1401e8fb9  lea     rdx, [rbp+57h+var_A0]; void **
0x1401e8fbd  xor     r8d, r8d; unsigned __int8
0x1401e8fc0  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1401e8fc4  movups  [rbp+57h+KeyInformation], xmm1
0x1401e8fc8  movups  [rbp+57h+var_58], xmm1
0x1401e8fcc  movups  [rbp+57h+var_48], xmm1
0x1401e8fd0  call    ?HCI_GetDeviceKey@@YAJPEB_KPEAPEAXE@Z; HCI_GetDeviceKey(unsigned __int64 const *,void * *,uchar)
0x1401e8fd5  test    eax, eax
0x1401e8fd7  js      loc_1401E9175
0x1401e8fdd  mov     rdx, [r15+378h]; struct HCI_INTERFACE *
0x1401e8fe4  lea     r8, [rbp+57h+KeyHandle]; void **
0x1401e8fe8  mov     rcx, [rbp+57h+var_A0]; void *
0x1401e8fec  xor     r9d, r9d; unsigned __int8
0x1401e8fef  xor     dil, dil
0x1401e8ff2  xor     bl, bl
0x1401e8ff4  call    ?HCI_GetServicesForKey@@YAJPEAXPEAUHCI_INTERFACE@@PEAPEAXE@Z; HCI_GetServicesForKey(void *,HCI_INTERFACE *,void * *,uchar)
0x1401e8ff9  test    eax, eax
0x1401e8ffb  js      short loc_1401E9039
0x1401e8ffd  test    sil, sil
0x1401e9000  jnz     short loc_1401E9007
0x1401e9002  test    r14b, r14b
0x1401e9005  jz      short loc_1401E9027
0x1401e9007  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1401e900b  call    ?HCI_DeleteAllSubkeys@@YAJPEAX@Z; HCI_DeleteAllSubkeys(void *)
0x1401e9010  test    sil, sil
0x1401e9013  jz      short loc_1401E9027
0x1401e9015  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1401e9019  call    cs:__imp_ZwDeleteKey
0x1401e9020  nop     dword ptr [rax+rax+00h]
0x1401e9025  jmp     short loc_1401E9029
0x1401e9027  mov     bl, 1
0x1401e9029  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1401e902d  call    cs:__imp_ZwClose
0x1401e9034  nop     dword ptr [rax+rax+00h]
0x1401e9039  lea     rdx, aDynamiccacheds; "DynamicCachedServices"
0x1401e9040  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1401e9044  call    cs:__imp_RtlInitUnicodeString
0x1401e904b  nop     dword ptr [rax+rax+00h]
0x1401e9050  mov     rcx, [rbp+57h+var_A0]
0x1401e9054  lea     r8, [rbp+57h+Handle]
0x1401e9058  mov     esi, 200h
0x1401e905d  lea     rdx, [rbp+57h+DestinationString]
0x1401e9061  mov     r9d, esi
0x1401e9064  call    BthOpenKeyEx
0x1401e9069  test    eax, eax
0x1401e906b  js      short loc_1401E9080
0x1401e906d  mov     rcx, [rbp+57h+Handle]; Handle
0x1401e9071  mov     dil, 1
0x1401e9074  call    cs:__imp_ZwClose
0x1401e907b  nop     dword ptr [rax+rax+00h]
0x1401e9080  mov     rcx, [rbp+57h+var_A0]; KeyHandle
0x1401e9084  lea     rax, [rbp+57h+var_98]
0x1401e9088  xorps   xmm0, xmm0
0x1401e908b  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1401e9090  mov     r9d, 30h ; '0'; Length
0x1401e9096  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x1401e909a  movups  [rbp+57h+KeyInformation], xmm0
0x1401e909e  mov     [rbp+57h+var_98], r9d
0x1401e90a2  movups  [rbp+57h+var_58], xmm0
0x1401e90a6  lea     edx, [r9-2Eh]; KeyInformationClass
0x1401e90aa  movups  [rbp+57h+var_48], xmm0
0x1401e90ae  call    cs:__imp_ZwQueryKey
0x1401e90b5  nop     dword ptr [rax+rax+00h]
0x1401e90ba  test    eax, eax
0x1401e90bc  js      loc_1401E9165
0x1401e90c2  test    r14b, r14b
0x1401e90c5  jz      loc_1401E914E
0x1401e90cb  mov     eax, dword ptr [rbp+57h+var_58+4]
0x1401e90ce  cmp     eax, 1
0x1401e90d1  jz      short loc_1401E90EF
0x1401e90d3  cmp     eax, 2
0x1401e90d6  jnz     short loc_1401E90E1
0x1401e90d8  test    dil, dil
0x1401e90db  jnz     short loc_1401E90EF
0x1401e90dd  test    bl, bl
0x1401e90df  jnz     short loc_1401E90EF
0x1401e90e1  cmp     eax, 3
0x1401e90e4  jnz     short loc_1401E9151
0x1401e90e6  test    dil, dil
0x1401e90e9  jz      short loc_1401E9165
0x1401e90eb  test    bl, bl
0x1401e90ed  jz      short loc_1401E9165
0x1401e90ef  lea     rdx, aCachedservices; "CachedServices"
0x1401e90f6  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1401e90fa  call    cs:__imp_RtlInitUnicodeString
0x1401e9101  nop     dword ptr [rax+rax+00h]
0x1401e9106  mov     rcx, [rbp+57h+var_A0]
0x1401e910a  lea     r8, [rbp+57h+var_88]
0x1401e910e  mov     r9d, esi
0x1401e9111  lea     rdx, [rbp+57h+DestinationString]
0x1401e9115  call    BthOpenKeyEx
0x1401e911a  test    eax, eax
0x1401e911c  js      short loc_1401E914E
0x1401e911e  mov     rcx, [rbp+57h+var_88]; KeyHandle
0x1401e9122  call    cs:__imp_ZwDeleteKey
0x1401e9129  nop     dword ptr [rax+rax+00h]
0x1401e912e  mov     rcx, [rbp+57h+var_88]; Handle
0x1401e9132  mov     ebx, eax
0x1401e9134  call    cs:__imp_ZwClose
0x1401e913b  nop     dword ptr [rax+rax+00h]
0x1401e9140  test    ebx, ebx
0x1401e9142  js      short loc_1401E914E
0x1401e9144  mov     eax, dword ptr [rbp+57h+var_58+4]
0x1401e9147  dec     eax
0x1401e9149  mov     dword ptr [rbp+57h+var_58+4], eax
0x1401e914c  jmp     short loc_1401E9151
0x1401e914e  mov     eax, dword ptr [rbp+57h+var_58+4]
0x1401e9151  test    eax, eax
0x1401e9153  jnz     short loc_1401E9165
0x1401e9155  mov     rcx, [rbp+57h+var_A0]; KeyHandle
0x1401e9159  call    cs:__imp_ZwDeleteKey
0x1401e9160  nop     dword ptr [rax+rax+00h]
0x1401e9165  mov     rcx, [rbp+57h+var_A0]; Handle
0x1401e9169  call    cs:__imp_ZwClose
0x1401e9170  nop     dword ptr [rax+rax+00h]
0x1401e9175  mov     rcx, [rbp+57h+var_38]
0x1401e9179  xor     rcx, rsp; StackCookie
0x1401e917c  call    __security_check_cookie
0x1401e9181  add     rsp, 0A8h
0x1401e9188  pop     r15
0x1401e918a  pop     r14
0x1401e918c  pop     rdi
0x1401e918d  pop     rsi
0x1401e918e  pop     rbx
0x1401e918f  pop     rbp
0x1401e9190  retn
```
