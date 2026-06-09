# HCI_AddStoredDevicesWorker(HCI_INTERFACE *,void *,DibStoreInfoType)

- ea: `0x1401be10c`
- end: `0x1401be34b`
- name: `?HCI_AddStoredDevicesWorker@@YAXPEAUHCI_INTERFACE@@PEAXW4DibStoreInfoType@@@Z`
- size: `575`
- prototype: `void __high(struct HCI_INTERFACE *, void *, enum DibStoreInfoType)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1401bdf58`

## callees

- `0x140020414`
- `0x140063d5c`
- `0x140165540`
- `0x1401be10c`

## import_xrefs

- `ntoskrnl!ZwQueryKey` at `0x1401be17c`
- `ntoskrnl!ZwQueryKey` at `0x1401be17c`
- `ntoskrnl!ZwEnumerateKey` at `0x1401be24d`
- `ntoskrnl!ZwEnumerateKey` at `0x1401be24d`
- `ntoskrnl!ZwDeleteValueKey` at `0x1401be307`
- `ntoskrnl!ZwDeleteValueKey` at `0x1401be307`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401be318`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401be318`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401be2f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401be2f4`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1401be1d1`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1401be1d1`

## pseudocode

```c
int __fastcall HCI_AddStoredDevicesWorker(__int64 a1, void *a2, unsigned int a3)
{
  PVOID *v6; // rax
  ULONG i; // ebx
  ULONG j; // ebx
  __int64 v9; // r9
  _DWORD *v10; // rbx
  __int64 v11; // rax
  PULONG ResultLength; // [rsp+20h] [rbp-99h]
  ULONG v14; // [rsp+30h] [rbp-89h] BYREF
  PVOID P[2]; // [rsp+38h] [rbp-81h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-71h] BYREF
  __int128 KeyInformation; // [rsp+58h] [rbp-61h] BYREF
  __int128 v18; // [rsp+68h] [rbp-51h]
  __int128 v19; // [rsp+78h] [rbp-41h]
  __int128 KeyValueInformation; // [rsp+88h] [rbp-31h] BYREF
  _OWORD v21[2]; // [rsp+98h] [rbp-21h] BYREF
  __int16 v22; // [rsp+B8h] [rbp-1h]
  WCHAR SourceString[16]; // [rsp+C0h] [rbp+7h] BYREF

  P[1] = P;
  v14 = 48;
  P[0] = P;
  DestinationString = 0;
  KeyInformation = 0;
  v18 = 0;
  v19 = 0;
  LODWORD(v6) = ZwQueryKey(a2, KeyFullInformation, &KeyInformation, 0x30u, &v14);
  if ( (int)v6 >= 0 )
  {
    if ( a3 != 2 )
    {
      for ( i = 0; i < (unsigned int)v19; ++i )
      {
        v14 = 42;
        memset(v21, 0, 26);
        KeyValueInformation = 0;
        if ( ZwEnumerateValueKey(a2, i, KeyValueBasicInformation, &KeyValueInformation, 0x2Au, &v14) >= 0 )
          HCI_ProcessStoredDevice(a1, P, a3, 0, (char *)&KeyValueInformation + 12, DWORD2(KeyValueInformation));
      }
    }
    for ( j = 0; j < DWORD1(v18); ++j )
    {
      v14 = 50;
      v22 = 0;
      KeyValueInformation = 0;
      memset(v21, 0, sizeof(v21));
      if ( ZwEnumerateKey(a2, j, KeyBasicInformation, &KeyValueInformation, 0x32u, &v14) >= 0 )
      {
        LOBYTE(v9) = 1;
        HCI_ProcessStoredDevice(a1, P, a3, v9, v21, HIDWORD(KeyValueInformation));
      }
    }
    while ( 1 )
    {
      v10 = P[0];
      v6 = P;
      if ( P[0] == P )
        break;
      if ( *((PVOID **)P[0] + 1) != P || (v11 = *(_QWORD *)P[0], *(PVOID *)(*(_QWORD *)P[0] + 8LL) != P[0]) )
        __fastfail(3u);
      P[0] = *(PVOID *)P[0];
      *(_QWORD *)(v11 + 8) = P;
      LODWORD(ResultLength) = v10[4];
      if ( (int)RtlStringCbPrintfW(
                  SourceString,
                  0x1Au,
                  L"%04x%08x",
                  (unsigned __int16)WORD2(*((_QWORD *)v10 + 2)),
                  ResultLength) >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, SourceString);
        ZwDeleteValueKey(a2, &DestinationString);
      }
      ExFreePoolWithTag(v10, 0);
    }
  }
  return (int)v6;
}

```

## disassembly

```asm
0x1401be10c  push    rbp
0x1401be10e  push    rbx
0x1401be10f  push    rsi
0x1401be110  push    rdi
0x1401be111  push    r14
0x1401be113  lea     rbp, [rsp-37h]
0x1401be118  sub     rsp, 0F0h
0x1401be11f  mov     rax, cs:__security_cookie
0x1401be126  xor     rax, rsp
0x1401be129  mov     [rbp+57h+var_30], rax
0x1401be12d  xorps   xmm0, xmm0
0x1401be130  lea     rax, [rsp+110h+P]
0x1401be135  mov     [rbp+57h+var_D0], rax
0x1401be139  mov     r9d, 30h ; '0'; Length
0x1401be13f  mov     rsi, rdx
0x1401be142  mov     [rsp+110h+var_E0], r9d
0x1401be147  lea     rax, [rsp+110h+P]
0x1401be14c  mov     edi, r8d
0x1401be14f  mov     [rsp+110h+P], rax
0x1401be154  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x1401be158  lea     rax, [rsp+110h+var_E0]
0x1401be15d  mov     r14, rcx
0x1401be160  lea     edx, [r9-2Eh]; KeyInformationClass
0x1401be164  mov     [rsp+110h+ResultLength], rax; ResultLength
0x1401be169  mov     rcx, rsi; KeyHandle
0x1401be16c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1401be170  movups  [rbp+57h+KeyInformation], xmm0
0x1401be174  movups  [rbp+57h+var_A8], xmm0
0x1401be178  movups  [rbp+57h+var_98], xmm0
0x1401be17c  call    cs:__imp_ZwQueryKey
0x1401be183  nop     dword ptr [rax+rax+00h]
0x1401be188  test    eax, eax
0x1401be18a  js      loc_1401BE330
0x1401be190  cmp     edi, 2
0x1401be193  jz      short loc_1401BE20B
0x1401be195  xor     ebx, ebx
0x1401be197  cmp     dword ptr [rbp+57h+var_98], ebx
0x1401be19a  jbe     short loc_1401BE20B
0x1401be19c  xorps   xmm0, xmm0
0x1401be19f  mov     [rsp+110h+var_E0], 2Ah ; '*'
0x1401be1a7  lea     rax, [rsp+110h+var_E0]
0x1401be1ac  xor     r8d, r8d; KeyValueInformationClass
0x1401be1af  movups  [rbp+57h+var_78], xmm0
0x1401be1b3  mov     [rsp+110h+var_E8], rax; ResultLength
0x1401be1b8  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1401be1bc  mov     edx, ebx; Index
0x1401be1be  mov     dword ptr [rsp+110h+ResultLength], 2Ah ; '*'; Length
0x1401be1c6  mov     rcx, rsi; KeyHandle
0x1401be1c9  movups  [rbp+57h+var_78+0Ah], xmm0
0x1401be1cd  movups  [rbp+57h+KeyValueInformation], xmm0
0x1401be1d1  call    cs:__imp_ZwEnumerateValueKey
0x1401be1d8  nop     dword ptr [rax+rax+00h]
0x1401be1dd  test    eax, eax
0x1401be1df  js      short loc_1401BE204
0x1401be1e1  mov     eax, dword ptr [rbp+57h+KeyValueInformation+8]
0x1401be1e4  lea     rdx, [rsp+110h+P]
0x1401be1e9  mov     dword ptr [rsp+110h+var_E8], eax
0x1401be1ed  xor     r9d, r9d
0x1401be1f0  lea     rax, [rbp+57h+KeyValueInformation+0Ch]
0x1401be1f4  mov     r8d, edi
0x1401be1f7  mov     rcx, r14
0x1401be1fa  mov     [rsp+110h+ResultLength], rax
0x1401be1ff  call    ?HCI_ProcessStoredDevice@@YAXPEAUHCI_INTERFACE@@PEAU_LIST_ENTRY@@W4DibStoreInfoType@@W4_HCI_PHY_TYPE@@PEAGK@Z; HCI_ProcessStoredDevice(HCI_INTERFACE *,_LIST_ENTRY *,DibStoreInfoType,_HCI_PHY_TYPE,ushort *,ulong)
0x1401be204  inc     ebx
0x1401be206  cmp     ebx, dword ptr [rbp+57h+var_98]
0x1401be209  jb      short loc_1401BE19C
0x1401be20b  xor     ebx, ebx
0x1401be20d  cmp     dword ptr [rbp+57h+var_A8+4], ebx
0x1401be210  jbe     short loc_1401BE287
0x1401be212  xorps   xmm0, xmm0
0x1401be215  mov     [rsp+110h+var_E0], 32h ; '2'
0x1401be21d  xor     eax, eax
0x1401be21f  lea     r9, [rbp+57h+KeyValueInformation]; KeyInformation
0x1401be223  mov     [rbp+57h+var_58], ax
0x1401be227  xor     r8d, r8d; KeyInformationClass
0x1401be22a  lea     rax, [rsp+110h+var_E0]
0x1401be22f  mov     edx, ebx; Index
0x1401be231  mov     [rsp+110h+var_E8], rax; ResultLength
0x1401be236  mov     rcx, rsi; KeyHandle
0x1401be239  mov     dword ptr [rsp+110h+ResultLength], 32h ; '2'; Length
0x1401be241  movups  [rbp+57h+KeyValueInformation], xmm0
0x1401be245  movups  [rbp+57h+var_78], xmm0
0x1401be249  movups  [rbp+57h+var_68], xmm0
0x1401be24d  call    cs:__imp_ZwEnumerateKey
0x1401be254  nop     dword ptr [rax+rax+00h]
0x1401be259  test    eax, eax
0x1401be25b  js      short loc_1401BE280
0x1401be25d  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x1401be260  lea     rdx, [rsp+110h+P]
0x1401be265  mov     dword ptr [rsp+110h+var_E8], eax
0x1401be269  mov     r9b, 1
0x1401be26c  lea     rax, [rbp+57h+var_78]
0x1401be270  mov     r8d, edi
0x1401be273  mov     rcx, r14
0x1401be276  mov     [rsp+110h+ResultLength], rax
0x1401be27b  call    ?HCI_ProcessStoredDevice@@YAXPEAUHCI_INTERFACE@@PEAU_LIST_ENTRY@@W4DibStoreInfoType@@W4_HCI_PHY_TYPE@@PEAGK@Z; HCI_ProcessStoredDevice(HCI_INTERFACE *,_LIST_ENTRY *,DibStoreInfoType,_HCI_PHY_TYPE,ushort *,ulong)
0x1401be280  inc     ebx
0x1401be282  cmp     ebx, dword ptr [rbp+57h+var_A8+4]
0x1401be285  jb      short loc_1401BE212
0x1401be287  mov     rbx, [rsp+110h+P]
0x1401be28c  lea     rax, [rsp+110h+P]
0x1401be291  cmp     rbx, rax
0x1401be294  jz      loc_1401BE330
0x1401be29a  lea     rax, [rsp+110h+P]
0x1401be29f  cmp     [rbx+8], rax
0x1401be2a3  jnz     loc_1401BE329
0x1401be2a9  mov     rax, [rbx]
0x1401be2ac  cmp     [rax+8], rbx
0x1401be2b0  jnz     short loc_1401BE329
0x1401be2b2  mov     [rsp+110h+P], rax
0x1401be2b7  lea     rcx, [rsp+110h+P]
0x1401be2bc  mov     [rax+8], rcx
0x1401be2c0  lea     r8, a04x08x; "%04x%08x"
0x1401be2c7  mov     rax, [rbx+10h]
0x1401be2cb  lea     rcx, [rbp+57h+SourceString]; unsigned __int16 *
0x1401be2cf  shr     rax, 20h
0x1401be2d3  mov     edx, 1Ah; unsigned __int64
0x1401be2d8  movzx   r9d, ax
0x1401be2dc  mov     eax, [rbx+10h]
0x1401be2df  mov     dword ptr [rsp+110h+ResultLength], eax
0x1401be2e3  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401be2e8  test    eax, eax
0x1401be2ea  js      short loc_1401BE313
0x1401be2ec  lea     rdx, [rbp+57h+SourceString]; SourceString
0x1401be2f0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1401be2f4  call    cs:__imp_RtlInitUnicodeString
0x1401be2fb  nop     dword ptr [rax+rax+00h]
0x1401be300  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1401be304  mov     rcx, rsi; KeyHandle
0x1401be307  call    cs:__imp_ZwDeleteValueKey
0x1401be30e  nop     dword ptr [rax+rax+00h]
0x1401be313  xor     edx, edx; Tag
0x1401be315  mov     rcx, rbx; P
0x1401be318  call    cs:__imp_ExFreePoolWithTag
0x1401be31f  nop     dword ptr [rax+rax+00h]
0x1401be324  jmp     loc_1401BE287
0x1401be329  mov     ecx, 3
0x1401be32e  int     29h; Win8: RtlFailFast(ecx)
0x1401be330  mov     rcx, [rbp+57h+var_30]
0x1401be334  xor     rcx, rsp; StackCookie
0x1401be337  call    __security_check_cookie
0x1401be33c  add     rsp, 0F0h
0x1401be343  pop     r14
0x1401be345  pop     rdi
0x1401be346  pop     rsi
0x1401be347  pop     rbx
0x1401be348  pop     rbp
0x1401be349  retn
```
