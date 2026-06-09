# HCI_DibSetPersonal(DEVICE_INFO_BLOCK *,void *,_BTH_DEVICE_INFO *,ulong)

- ea: `0x1401c053c`
- end: `0x1401c069d`
- name: `?HCI_DibSetPersonal@@YAXPEAUDEVICE_INFO_BLOCK@@PEAXPEAU_BTH_DEVICE_INFO@@K@Z`
- size: `353`
- prototype: `void __fastcall(struct DEVICE_INFO_BLOCK *, HANDLE KeyHandle, struct _BTH_DEVICE_INFO *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140059d10`
- `0x14005d3a0`
- `0x14005e480`

## callees

- `0x140020414`
- `0x14005b478`
- `0x140165540`
- `0x1401c053c`
- `0x1401c091c`

## import_xrefs

- `ntoskrnl!ZwQueryKey` at `0x1401c0652`
- `ntoskrnl!ZwQueryKey` at `0x1401c0652`
- `ntoskrnl!ZwDeleteKey` at `0x1401c0671`
- `ntoskrnl!ZwDeleteKey` at `0x1401c0671`
- `ntoskrnl!ZwDeleteValueKey` at `0x1401c0619`
- `ntoskrnl!ZwDeleteValueKey` at `0x1401c0619`
- `ntoskrnl!ZwSetValueKey` at `0x1401c05f3`
- `ntoskrnl!ZwSetValueKey` at `0x1401c05f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c05c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c05c1`

## pseudocode

```c
void __fastcall HCI_DibSetPersonal(struct DEVICE_INFO_BLOCK *a1, HANDLE KeyHandle, struct _BTH_DEVICE_INFO *a3)
{
  __int64 v4; // r9
  int address; // eax
  _BYTE Data[4]; // [rsp+30h] [rbp-29h] BYREF
  ULONG ResultLength; // [rsp+34h] [rbp-25h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-21h] BYREF
  __int128 KeyInformation; // [rsp+48h] [rbp-11h] BYREF
  __int128 v12; // [rsp+58h] [rbp-1h]
  __int128 v13; // [rsp+68h] [rbp+Fh]
  WCHAR SourceString[16]; // [rsp+78h] [rbp+1Fh] BYREF

  v4 = (unsigned __int16)WORD2(a1->DeviceInfo.address);
  address = a1->DeviceInfo.address;
  Data[0] = 0;
  ResultLength = 0;
  DestinationString = 0;
  KeyInformation = 0;
  v12 = 0;
  v13 = 0;
  if ( (int)RtlStringCbPrintfW(SourceString, 0x1Au, L"%04x%08x", v4, address) >= 0 )
  {
    Data[0] = 0;
    RtlInitUnicodeString(&DestinationString, SourceString);
    if ( a3 )
    {
      ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, Data, 0);
      HCI_DibStoreInfo(a1, a3);
      HCI_DibSetFlags(a1, a3->flags, 1u);
    }
    else
    {
      ZwDeleteValueKey(KeyHandle, &DestinationString);
      ResultLength = 48;
      KeyInformation = 0;
      v12 = 0;
      v13 = 0;
      if ( ZwQueryKey(KeyHandle, KeyFullInformation, &KeyInformation, 0x30u, &ResultLength) >= 0
        && !DWORD1(v12)
        && !(_DWORD)v13 )
      {
        ZwDeleteKey(KeyHandle);
      }
    }
  }
}

```

## disassembly

```asm
0x1401c053c  mov     [rsp-8+arg_18], rbx
0x1401c0541  push    rbp
0x1401c0542  push    rsi
0x1401c0543  push    rdi
0x1401c0544  lea     rbp, [rsp-47h]
0x1401c0549  sub     rsp, 0A0h
0x1401c0550  mov     rax, cs:__security_cookie
0x1401c0557  xor     rax, rsp
0x1401c055a  mov     [rbp+57h+var_18], rax
0x1401c055e  mov     rax, [rcx+20h]
0x1401c0562  xorps   xmm0, xmm0
0x1401c0565  shr     rax, 20h
0x1401c0569  mov     rdi, r8
0x1401c056c  movzx   r9d, ax
0x1401c0570  lea     r8, a04x08x; "%04x%08x"
0x1401c0577  mov     eax, [rcx+20h]
0x1401c057a  mov     rbx, rdx
0x1401c057d  mov     rsi, rcx
0x1401c0580  mov     [rbp+57h+var_80], 0
0x1401c0584  lea     rcx, [rbp+57h+SourceString]; unsigned __int16 *
0x1401c0588  mov     [rbp+57h+ResultLength], 0
0x1401c058f  mov     edx, 1Ah; unsigned __int64
0x1401c0594  mov     dword ptr [rsp+0B0h+Data], eax
0x1401c0598  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1401c059c  movups  [rbp+57h+KeyInformation], xmm0
0x1401c05a0  movups  [rbp+57h+var_58], xmm0
0x1401c05a4  movups  [rbp+57h+var_48], xmm0
0x1401c05a8  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401c05ad  test    eax, eax
0x1401c05af  js      loc_1401C067D
0x1401c05b5  lea     rdx, [rbp+57h+SourceString]; SourceString
0x1401c05b9  mov     [rbp+57h+var_80], 0
0x1401c05bd  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1401c05c1  call    cs:__imp_RtlInitUnicodeString
0x1401c05c8  nop     dword ptr [rax+rax+00h]
0x1401c05cd  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1401c05d1  mov     rcx, rbx; KeyHandle
0x1401c05d4  test    rdi, rdi
0x1401c05d7  jz      short loc_1401C0619
0x1401c05d9  lea     rax, [rbp+57h+var_80]
0x1401c05dd  mov     [rsp+0B0h+DataSize], 0; DataSize
0x1401c05e5  mov     r9d, 3; Type
0x1401c05eb  mov     [rsp+0B0h+Data], rax; Data
0x1401c05f0  xor     r8d, r8d; TitleIndex
0x1401c05f3  call    cs:__imp_ZwSetValueKey
0x1401c05fa  nop     dword ptr [rax+rax+00h]
0x1401c05ff  mov     rdx, rdi; struct _BTH_DEVICE_INFO *
0x1401c0602  mov     rcx, rsi; struct DEVICE_INFO_BLOCK *
0x1401c0605  call    ?HCI_DibStoreInfo@@YAXPEAUDEVICE_INFO_BLOCK@@PEAU_BTH_DEVICE_INFO@@@Z; HCI_DibStoreInfo(DEVICE_INFO_BLOCK *,_BTH_DEVICE_INFO *)
0x1401c060a  mov     edx, [rdi]; unsigned int
0x1401c060c  mov     r8b, 1; unsigned __int8
0x1401c060f  mov     rcx, rsi; struct DEVICE_INFO_BLOCK *
0x1401c0612  call    ?HCI_DibSetFlags@@YAEPEAUDEVICE_INFO_BLOCK@@KE@Z; HCI_DibSetFlags(DEVICE_INFO_BLOCK *,ulong,uchar)
0x1401c0617  jmp     short loc_1401C067D
0x1401c0619  call    cs:__imp_ZwDeleteValueKey
0x1401c0620  nop     dword ptr [rax+rax+00h]
0x1401c0625  xorps   xmm0, xmm0
0x1401c0628  lea     rax, [rbp+57h+ResultLength]
0x1401c062c  mov     r9d, 30h ; '0'; Length
0x1401c0632  mov     [rsp+0B0h+Data], rax; ResultLength
0x1401c0637  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x1401c063b  mov     [rbp+57h+ResultLength], r9d
0x1401c063f  mov     rcx, rbx; KeyHandle
0x1401c0642  movups  [rbp+57h+KeyInformation], xmm0
0x1401c0646  lea     edx, [r9-2Eh]; KeyInformationClass
0x1401c064a  movups  [rbp+57h+var_58], xmm0
0x1401c064e  movups  [rbp+57h+var_48], xmm0
0x1401c0652  call    cs:__imp_ZwQueryKey
0x1401c0659  nop     dword ptr [rax+rax+00h]
0x1401c065e  test    eax, eax
0x1401c0660  js      short loc_1401C067D
0x1401c0662  cmp     dword ptr [rbp+57h+var_58+4], 0
0x1401c0666  jnz     short loc_1401C067D
0x1401c0668  cmp     dword ptr [rbp+57h+var_48], 0
0x1401c066c  jnz     short loc_1401C067D
0x1401c066e  mov     rcx, rbx; KeyHandle
0x1401c0671  call    cs:__imp_ZwDeleteKey
0x1401c0678  nop     dword ptr [rax+rax+00h]
0x1401c067d  mov     rcx, [rbp+57h+var_18]
0x1401c0681  xor     rcx, rsp; StackCookie
0x1401c0684  call    __security_check_cookie
0x1401c0689  mov     rbx, [rsp+0B0h+arg_18]
0x1401c0691  add     rsp, 0A0h
0x1401c0698  pop     rdi
0x1401c0699  pop     rsi
0x1401c069a  pop     rbp
0x1401c069b  retn
```
