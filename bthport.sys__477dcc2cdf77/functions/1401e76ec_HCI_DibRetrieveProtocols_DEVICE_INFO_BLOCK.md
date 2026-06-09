# HCI_DibRetrieveProtocols(DEVICE_INFO_BLOCK *)

- ea: `0x1401e76ec`
- end: `0x1401e7bc7`
- name: `?HCI_DibRetrieveProtocols@@YAJPEAUDEVICE_INFO_BLOCK@@@Z`
- size: `1243`
- prototype: `__int64 __fastcall(struct DEVICE_INFO_BLOCK *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400515b0`

## callees

- `0x140004368`
- `0x140020330`
- `0x140020414`
- `0x140130d4c`
- `0x140130dac`
- `0x140130e80`
- `0x140165540`
- `0x140165e60`
- `0x1401c18d0`
- `0x1401c1c04`
- `0x1401e7098`
- `0x1401e76ec`
- `0x1401e7bd0`
- `0x1401e8ea0`
- `0x1402093a8`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1401e783d`
- `ntoskrnl!ZwQueryValueKey` at `0x1401e78d3`
- `ntoskrnl!ZwQueryValueKey` at `0x1401e783d`
- `ntoskrnl!ZwQueryValueKey` at `0x1401e78d3`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1401e7a58`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1401e7a58`
- `ntoskrnl!ZwSetValueKey` at `0x1401e7b12`
- `ntoskrnl!ZwSetValueKey` at `0x1401e7b12`
- `ntoskrnl!ZwClose` at `0x1401e77d3`
- `ntoskrnl!ZwClose` at `0x1401e7b24`
- `ntoskrnl!ZwClose` at `0x1401e7b71`
- `ntoskrnl!ZwClose` at `0x1401e7b82`
- `ntoskrnl!ZwClose` at `0x1401e77d3`
- `ntoskrnl!ZwClose` at `0x1401e7b24`
- `ntoskrnl!ZwClose` at `0x1401e7b71`
- `ntoskrnl!ZwClose` at `0x1401e7b82`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401e7b98`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401e7b98`
- `ntoskrnl!ExAllocatePool2` at `0x1401e7894`
- `ntoskrnl!ExAllocatePool2` at `0x1401e7894`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401e77ec`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401e7ae6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401e77ec`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401e7ae6`

## string_xrefs

- `0x1401e7770`: `DibServiceVersion`
- `0x1401e7adb`: `DibServiceVersion`

## pseudocode

```c
__int64 __fastcall HCI_DibRetrieveProtocols(struct DEVICE_INFO_BLOCK *a1)
{
  __int64 result; // rax
  char v3; // bl
  HCI_INTERFACE *Hci; // rdx
  NTSTATUS v5; // ebx
  HANDLE v6; // rcx
  int ServicesForKey; // eax
  _DWORD *Pool2; // r15
  _DWORD *v9; // rdx
  unsigned int v10; // r14d
  unsigned int v11; // edi
  unsigned int v12; // r12d
  unsigned int v13; // ecx
  int v14; // eax
  __int64 v15; // rax
  _DWORD *v16; // r13
  unsigned int v17; // edi
  struct _GUID *v18; // r14
  struct _GUID *v19; // rcx
  __int64 v20; // r8
  _RTL_RB_TREE *ProtocolRbTree; // r12
  unsigned __int64 Root; // rdi
  int v23; // r13d
  unsigned __int64 v24; // rax
  NTSTATUS RemoteServices; // eax
  HANDLE Handle; // [rsp+30h] [rbp-89h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-81h] BYREF
  unsigned int v28; // [rsp+3Ch] [rbp-7Dh]
  int Data; // [rsp+40h] [rbp-79h] BYREF
  HANDLE v30; // [rsp+48h] [rbp-71h] BYREF
  struct _GUID *v31; // [rsp+50h] [rbp-69h] BYREF
  struct _GUID *v32; // [rsp+58h] [rbp-61h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-59h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+70h] [rbp-49h] BYREF
  __int128 KeyValueInformation; // [rsp+80h] [rbp-39h] BYREF
  WCHAR SourceString[24]; // [rsp+90h] [rbp-29h] BYREF

  Handle = 0;
  ResultLength = 0;
  v30 = 0;
  Data = 0;
  KeyValueInformation = 0;
  DestinationString = 0;
  ValueName = 0;
  result = HCI_GetDeviceKey(&a1->DeviceInfo.address, &Handle, 0);
  if ( (int)result >= 0 )
  {
    v3 = 0;
    if ( (int)BthQueryKeyValue(Handle) < 0 )
    {
      v3 = 1;
      Data = 0x20000;
    }
    Hci = a1->Hci;
    if ( v3 )
    {
      v5 = RtlStringCbPrintfW(
             SourceString,
             0x2Eu,
             L"%04x%08x",
             (unsigned __int16)WORD2(Hci->LocalInfo.localInfo.address),
             LODWORD(Hci->LocalInfo.localInfo.address));
      if ( v5 < 0 )
      {
LABEL_6:
        v6 = Handle;
LABEL_7:
        ZwClose(v6);
        return (unsigned int)v5;
      }
      RtlInitUnicodeString(&DestinationString, SourceString);
      ServicesForKey = HCI_GetServicesForKey(Handle, a1->Hci, &v30, 1u);
      v6 = Handle;
      v5 = ServicesForKey;
      if ( ServicesForKey < 0 )
        goto LABEL_7;
      v5 = ZwQueryValueKey(
             Handle,
             &DestinationString,
             KeyValuePartialInformation,
             &KeyValueInformation,
             0x10u,
             &ResultLength);
      if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147483643
        || DWORD1(KeyValueInformation) != 3
        || !DWORD2(KeyValueInformation)
        || (BYTE8(KeyValueInformation) & 0xF) != 0 )
      {
        ZwClose(v30);
        goto LABEL_6;
      }
      ResultLength = DWORD2(KeyValueInformation) + 16;
      Pool2 = (_DWORD *)ExAllocatePool2(256, (unsigned int)(DWORD2(KeyValueInformation) + 16), 1346917442);
      if ( !Pool2 )
      {
        v5 = -1073741670;
LABEL_57:
        HCI_DibFreeProtocolTree(a1);
LABEL_58:
        ZwClose(v30);
        ZwClose(Handle);
        if ( Pool2 )
          ExFreePoolWithTag(Pool2, 0);
        return (unsigned int)v5;
      }
      v5 = ZwQueryValueKey(Handle, &DestinationString, KeyValuePartialInformation, Pool2, ResultLength, &ResultLength);
      if ( v5 < 0 )
        goto LABEL_57;
      v9 = Pool2 + 3;
      v10 = Pool2[2] >> 4;
      v11 = 0;
      if ( v10 != 1 )
      {
        while ( 1 )
        {
          v12 = 0;
          v13 = v11;
          v14 = v10 - v11++ - 1;
          v28 = v14;
          if ( v14 )
            break;
LABEL_23:
          if ( v11 >= v10 - 1 )
            goto LABEL_24;
        }
        v15 = v11;
        v16 = &v9[4 * v13];
        while ( memcmp(&v9[4 * v15 + 4 * v12], v16, 0x10u) )
        {
          ++v12;
          v15 = v11;
          v9 = Pool2 + 3;
          if ( v12 >= v28 )
          {
            v9 = Pool2 + 3;
            goto LABEL_23;
          }
        }
        v5 = -1073741811;
        goto LABEL_57;
      }
LABEL_24:
      v17 = 0;
      a1->NumProtocols = v10;
      v28 = 0;
      if ( v10 )
      {
        while ( 1 )
        {
          utl::make_unique<_DIB_SERVICE_DESCRIPTOR,,0>(&v31, v9);
          v18 = v31;
          if ( !v31 )
            break;
          v19 = v31;
          *v31 = *(struct _GUID *)&Pool2[4 * v17 + 3];
          *(_DWORD *)&v18[81].Data2 = 1;
          v18[81].Data4[0] = !HCI_UseDeferredActivationForService(v19);
          v5 = RtlStringCbCopyW(&v18[17].Data2, 0x200u, L"L00000000");
          if ( v5 < 0 )
            goto LABEL_47;
          ProtocolRbTree = a1->ProtocolRbTree;
          v32 = v18 + 82;
          v31 = 0;
          Root = (unsigned __int64)ProtocolRbTree->Root;
          if ( (*(_BYTE *)&ProtocolRbTree->0 & 1) == 0 )
            goto LABEL_30;
          if ( Root )
          {
            Root ^= (unsigned __int64)ProtocolRbTree;
LABEL_30:
            LOBYTE(v20) = 0;
            v23 = *(_BYTE *)&ProtocolRbTree->0 & 1;
            if ( !Root )
              goto LABEL_39;
            while ( 1 )
            {
              if ( HCI_DibServDescCompare((const WCHAR *)v18, (struct _RTL_BALANCED_NODE *)Root) < 0 )
              {
                v24 = *(_QWORD *)Root;
                if ( v23 )
                {
                  if ( !v24 )
                    break;
                  v24 ^= Root;
                }
                if ( !v24 )
                  break;
              }
              else
              {
                v24 = *(_QWORD *)(Root + 8);
                if ( v23 )
                {
                  if ( !v24 )
                    goto LABEL_36;
                  v24 ^= Root;
                }
                if ( !v24 )
                {
LABEL_36:
                  LOBYTE(v20) = 1;
                  goto LABEL_39;
                }
              }
              Root = v24;
            }
          }
          LOBYTE(v20) = 0;
LABEL_39:
          RtlRbInsertNodeEx(ProtocolRbTree, Root, v20, v32);
          utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>(&v31);
          v17 = v28 + 1;
          v28 = v17;
          if ( v17 >= a1->NumProtocols )
            goto LABEL_48;
        }
        v5 = -1073741670;
LABEL_47:
        utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>(&v31);
      }
LABEL_48:
      if ( v17 != a1->NumProtocols )
      {
        a1->NumProtocols = 0;
        goto LABEL_56;
      }
      v5 = HCI_DibWriteRemoteServices(a1, v30);
      if ( v5 < 0 )
        goto LABEL_57;
      RtlInitUnicodeString(&ValueName, L"DibServiceVersion");
      RemoteServices = ZwSetValueKey(Handle, &ValueName, 0, 4u, &Data, 4u);
    }
    else
    {
      v5 = HCI_GetServicesForKey(Handle, Hci, &v30, 0);
      if ( v5 < 0 )
        goto LABEL_6;
      Pool2 = 0;
      RemoteServices = HCI_DibReadRemoteServices(a1, v30);
    }
    v5 = RemoteServices;
LABEL_56:
    if ( v5 >= 0 )
      goto LABEL_58;
    goto LABEL_57;
  }
  return result;
}

```

## disassembly

```asm
0x1401e76ec  push    rbp
0x1401e76ee  push    rbx
0x1401e76ef  push    rsi
0x1401e76f0  push    rdi
0x1401e76f1  push    r12
0x1401e76f3  push    r13
0x1401e76f5  push    r14
0x1401e76f7  push    r15
0x1401e76f9  lea     rbp, [rsp-1Fh]
0x1401e76fe  sub     rsp, 0D8h
0x1401e7705  mov     rax, cs:__security_cookie
0x1401e770c  xor     rax, rsp
0x1401e770f  mov     [rbp+57h+var_50], rax
0x1401e7713  xorps   xmm0, xmm0
0x1401e7716  mov     [rsp+110h+Handle], 0
0x1401e771f  mov     rsi, rcx
0x1401e7722  mov     [rsp+110h+var_D8], 0
0x1401e772a  xorps   xmm1, xmm1
0x1401e772d  mov     [rbp+57h+var_C8], 0
0x1401e7735  add     rcx, 20h ; ' '; unsigned __int64 *
0x1401e7739  mov     [rbp+57h+Data], 0
0x1401e7740  xor     r8d, r8d; unsigned __int8
0x1401e7743  lea     rdx, [rsp+110h+Handle]; void **
0x1401e7748  movups  [rbp+57h+KeyValueInformation], xmm0
0x1401e774c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1401e7750  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x1401e7754  call    ?HCI_GetDeviceKey@@YAJPEB_KPEAPEAXE@Z; HCI_GetDeviceKey(unsigned __int64 const *,void * *,uchar)
0x1401e7759  test    eax, eax
0x1401e775b  js      loc_1401E7BA6
0x1401e7761  mov     rcx, [rsp+110h+Handle]; KeyHandle
0x1401e7766  lea     r8, [rbp+57h+Data]
0x1401e776a  mov     r9d, 4
0x1401e7770  lea     rdx, aDibservicevers; "DibServiceVersion"
0x1401e7777  xor     bl, bl
0x1401e7779  call    BthQueryKeyValue
0x1401e777e  test    eax, eax
0x1401e7780  jns     short loc_1401E778B
0x1401e7782  mov     bl, 1
0x1401e7784  mov     [rbp+57h+Data], 20000h
0x1401e778b  mov     rdx, [rsi+378h]; struct HCI_INTERFACE *
0x1401e7792  test    bl, bl
0x1401e7794  jz      loc_1401E7B35
0x1401e779a  mov     rax, [rdx+124h]
0x1401e77a1  lea     r8, a04x08x; "%04x%08x"
0x1401e77a8  shr     rax, 20h
0x1401e77ac  lea     rcx, [rbp+57h+SourceString]; unsigned __int16 *
0x1401e77b0  movzx   r9d, ax
0x1401e77b4  mov     eax, [rdx+124h]
0x1401e77ba  mov     edx, 2Eh ; '.'; unsigned __int64
0x1401e77bf  mov     [rsp+110h+Length], eax
0x1401e77c3  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401e77c8  mov     ebx, eax
0x1401e77ca  test    eax, eax
0x1401e77cc  jns     short loc_1401E77E4
0x1401e77ce  mov     rcx, [rsp+110h+Handle]; Handle
0x1401e77d3  call    cs:__imp_ZwClose
0x1401e77da  nop     dword ptr [rax+rax+00h]
0x1401e77df  jmp     loc_1401E7BA4
0x1401e77e4  lea     rdx, [rbp+57h+SourceString]; SourceString
0x1401e77e8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1401e77ec  call    cs:__imp_RtlInitUnicodeString
0x1401e77f3  nop     dword ptr [rax+rax+00h]
0x1401e77f8  mov     rdx, [rsi+378h]; struct HCI_INTERFACE *
0x1401e77ff  lea     r8, [rbp+57h+var_C8]; void **
0x1401e7803  mov     rcx, [rsp+110h+Handle]; void *
0x1401e7808  mov     r9b, 1; unsigned __int8
0x1401e780b  call    ?HCI_GetServicesForKey@@YAJPEAXPEAUHCI_INTERFACE@@PEAPEAXE@Z; HCI_GetServicesForKey(void *,HCI_INTERFACE *,void * *,uchar)
0x1401e7810  mov     rcx, [rsp+110h+Handle]; KeyHandle
0x1401e7815  mov     ebx, eax
0x1401e7817  test    eax, eax
0x1401e7819  js      short loc_1401E77D3
0x1401e781b  lea     rax, [rsp+110h+var_D8]
0x1401e7820  mov     edi, 2
0x1401e7825  mov     [rsp+110h+ResultLength], rax; ResultLength
0x1401e782a  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1401e782e  mov     r8d, edi; KeyValueInformationClass
0x1401e7831  mov     [rsp+110h+Length], 10h; Length
0x1401e7839  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1401e783d  call    cs:__imp_ZwQueryValueKey
0x1401e7844  nop     dword ptr [rax+rax+00h]
0x1401e7849  mov     ebx, eax
0x1401e784b  mov     eax, 80000000h
0x1401e7850  lea     ecx, [rbx+rax]
0x1401e7853  test    eax, ecx
0x1401e7855  jnz     short loc_1401E7863
0x1401e7857  cmp     ebx, 80000005h
0x1401e785d  jnz     loc_1401E7B20
0x1401e7863  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 3
0x1401e7867  jnz     loc_1401E7B20
0x1401e786d  mov     eax, dword ptr [rbp+57h+KeyValueInformation+8]
0x1401e7870  test    eax, eax
0x1401e7872  jz      loc_1401E7B20
0x1401e7878  test    al, 0Fh
0x1401e787a  jnz     loc_1401E7B20
0x1401e7880  add     eax, 10h
0x1401e7883  mov     ecx, 100h
0x1401e7888  mov     edx, eax
0x1401e788a  mov     r8d, 50485442h
0x1401e7890  mov     [rsp+110h+var_D8], eax
0x1401e7894  call    cs:__imp_ExAllocatePool2
0x1401e789b  nop     dword ptr [rax+rax+00h]
0x1401e78a0  mov     r15, rax
0x1401e78a3  test    rax, rax
0x1401e78a6  jnz     short loc_1401E78B2
0x1401e78a8  mov     ebx, 0C000009Ah
0x1401e78ad  jmp     loc_1401E7B65
0x1401e78b2  mov     rcx, [rsp+110h+Handle]; KeyHandle
0x1401e78b7  lea     rax, [rsp+110h+var_D8]
0x1401e78bc  mov     [rsp+110h+ResultLength], rax; ResultLength
0x1401e78c1  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1401e78c5  mov     eax, [rsp+110h+var_D8]
0x1401e78c9  mov     r9, r15; KeyValueInformation
0x1401e78cc  mov     r8d, edi; KeyValueInformationClass
0x1401e78cf  mov     [rsp+110h+Length], eax; Length
0x1401e78d3  call    cs:__imp_ZwQueryValueKey
0x1401e78da  nop     dword ptr [rax+rax+00h]
0x1401e78df  mov     ebx, eax
0x1401e78e1  test    eax, eax
0x1401e78e3  js      loc_1401E7B65
0x1401e78e9  mov     r14d, [r15+8]
0x1401e78ed  lea     rdx, [r15+0Ch]
0x1401e78f1  shr     r14d, 4
0x1401e78f5  xor     edi, edi
0x1401e78f7  lea     eax, [r14-1]
0x1401e78fb  test    eax, eax
0x1401e78fd  jz      short loc_1401E795E
0x1401e78ff  xor     r12d, r12d
0x1401e7902  mov     ecx, edi
0x1401e7904  mov     eax, r14d
0x1401e7907  sub     eax, edi
0x1401e7909  dec     eax
0x1401e790b  inc     edi
0x1401e790d  mov     [rbp+57h+var_D4], eax
0x1401e7910  test    eax, eax
0x1401e7912  jz      short loc_1401E7956
0x1401e7914  mov     r13d, ecx
0x1401e7917  mov     eax, edi
0x1401e7919  shl     r13, 4
0x1401e791d  add     r13, rdx
0x1401e7920  mov     ecx, r12d
0x1401e7923  mov     r8d, 10h; Size
0x1401e7929  add     rcx, rax
0x1401e792c  shl     rcx, 4
0x1401e7930  add     rcx, rdx; Buf1
0x1401e7933  mov     rdx, r13; Buf2
0x1401e7936  call    memcmp
0x1401e793b  test    eax, eax
0x1401e793d  jz      loc_1401E7A41
0x1401e7943  inc     r12d
0x1401e7946  mov     eax, edi
0x1401e7948  lea     rdx, [r15+0Ch]
0x1401e794c  cmp     r12d, [rbp+57h+var_D4]
0x1401e7950  jb      short loc_1401E7920
0x1401e7952  lea     rdx, [r15+0Ch]
0x1401e7956  lea     eax, [r14-1]
0x1401e795a  cmp     edi, eax
0x1401e795c  jb      short loc_1401E78FF
0x1401e795e  xor     edi, edi
0x1401e7960  mov     [rsi+3C0h], r14d
0x1401e7967  mov     [rbp+57h+var_D4], edi
0x1401e796a  test    r14d, r14d
0x1401e796d  jz      loc_1401E7AAE
0x1401e7973  lea     rcx, [rbp+57h+var_C0]
0x1401e7977  call    ??$make_unique@U_DIB_SERVICE_DESCRIPTOR@@$$V$0A@@utl@@YA?AV?$unique_ptr@U_DIB_SERVICE_DESCRIPTOR@@U?$default_delete@U_DIB_SERVICE_DESCRIPTOR@@@utl@@@0@XZ; utl::make_unique<_DIB_SERVICE_DESCRIPTOR,,0>(void)
0x1401e797c  mov     r14, [rbp+57h+var_C0]
0x1401e7980  test    r14, r14
0x1401e7983  jz      loc_1401E7AA0
0x1401e7989  mov     eax, edi
0x1401e798b  mov     rcx, r14; struct _GUID *
0x1401e798e  add     rax, rax
0x1401e7991  movups  xmm0, xmmword ptr [r15+rax*8+0Ch]
0x1401e7997  movdqu  xmmword ptr [r14], xmm0
0x1401e799c  mov     dword ptr [r14+514h], 1
0x1401e79a7  call    ?HCI_UseDeferredActivationForService@@YA_NAEBU_GUID@@@Z; HCI_UseDeferredActivationForService(_GUID const &)
0x1401e79ac  xor     al, 1
0x1401e79ae  lea     rcx, [r14+114h]; unsigned __int16 *
0x1401e79b5  lea     r8, aL00000000; "L00000000"
0x1401e79bc  mov     [r14+518h], al
0x1401e79c3  mov     edx, 200h; unsigned __int64
0x1401e79c8  call    ?RtlStringCbCopyW@@YAJPEAG_KPEBG@Z; RtlStringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1401e79cd  mov     ebx, eax
0x1401e79cf  test    eax, eax
0x1401e79d1  js      loc_1401E7AA5
0x1401e79d7  mov     r12, [rsi+3B8h]
0x1401e79de  lea     rax, [r14+520h]
0x1401e79e5  mov     [rbp+57h+var_B8], rax
0x1401e79e9  mov     [rbp+57h+var_C0], 0
0x1401e79f1  test    byte ptr [r12+8], 1
0x1401e79f7  mov     rdi, [r12]
0x1401e79fb  jz      short loc_1401E7A05
0x1401e79fd  test    rdi, rdi
0x1401e7a00  jz      short loc_1401E7A4B
0x1401e7a02  xor     rdi, r12
0x1401e7a05  movzx   r13d, byte ptr [r12+8]
0x1401e7a0b  xor     r8b, r8b
0x1401e7a0e  and     r13d, 1
0x1401e7a12  test    rdi, rdi
0x1401e7a15  jz      short loc_1401E7A4E
0x1401e7a17  mov     rdx, rdi; struct _RTL_BALANCED_NODE *
0x1401e7a1a  mov     rcx, r14; void *
0x1401e7a1d  call    ?HCI_DibServDescCompare@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; HCI_DibServDescCompare(void *,_RTL_BALANCED_NODE *)
0x1401e7a22  test    eax, eax
0x1401e7a24  js      short loc_1401E7A83
0x1401e7a26  mov     rax, [rdi+8]
0x1401e7a2a  test    r13d, r13d
0x1401e7a2d  jz      short loc_1401E7A37
0x1401e7a2f  test    rax, rax
0x1401e7a32  jz      short loc_1401E7A3C
0x1401e7a34  xor     rax, rdi
0x1401e7a37  test    rax, rax
0x1401e7a3a  jnz     short loc_1401E7A98
0x1401e7a3c  mov     r8b, 1
0x1401e7a3f  jmp     short loc_1401E7A4E
0x1401e7a41  mov     ebx, 0C000000Dh
0x1401e7a46  jmp     loc_1401E7B65
0x1401e7a4b  xor     r8b, r8b
0x1401e7a4e  mov     r9, [rbp+57h+var_B8]
0x1401e7a52  mov     rdx, rdi
0x1401e7a55  mov     rcx, r12
0x1401e7a58  call    cs:__imp_RtlRbInsertNodeEx
0x1401e7a5f  nop     dword ptr [rax+rax+00h]
0x1401e7a64  lea     rcx, [rbp+57h+var_C0]
0x1401e7a68  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_DlistNode@UProcedureUpdateRequest@LESelectiveConnectionEstablishmentProcedure@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>(void)
0x1401e7a6d  mov     edi, [rbp+57h+var_D4]
0x1401e7a70  inc     edi
0x1401e7a72  mov     [rbp+57h+var_D4], edi
0x1401e7a75  cmp     edi, [rsi+3C0h]
0x1401e7a7b  jb      loc_1401E7973
0x1401e7a81  jmp     short loc_1401E7AAE
0x1401e7a83  mov     rax, [rdi]
0x1401e7a86  test    r13d, r13d
0x1401e7a89  jz      short loc_1401E7A93
0x1401e7a8b  test    rax, rax
0x1401e7a8e  jz      short loc_1401E7A4B
0x1401e7a90  xor     rax, rdi
0x1401e7a93  test    rax, rax
0x1401e7a96  jz      short loc_1401E7A4B
0x1401e7a98  mov     rdi, rax
0x1401e7a9b  jmp     loc_1401E7A17
0x1401e7aa0  mov     ebx, 0C000009Ah
0x1401e7aa5  lea     rcx, [rbp+57h+var_C0]
0x1401e7aa9  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_DlistNode@UProcedureUpdateRequest@LESelectiveConnectionEstablishmentProcedure@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>(void)
0x1401e7aae  cmp     edi, [rsi+3C0h]
0x1401e7ab4  jz      short loc_1401E7AC5
0x1401e7ab6  mov     dword ptr [rsi+3C0h], 0
0x1401e7ac0  jmp     loc_1401E7B61
0x1401e7ac5  mov     rdx, [rbp+57h+var_C8]; void *
0x1401e7ac9  mov     rcx, rsi; struct DEVICE_INFO_BLOCK *
0x1401e7acc  call    ?HCI_DibWriteRemoteServices@@YAJPEAUDEVICE_INFO_BLOCK@@PEAX@Z; HCI_DibWriteRemoteServices(DEVICE_INFO_BLOCK *,void *)
0x1401e7ad1  mov     ebx, eax
0x1401e7ad3  test    eax, eax
0x1401e7ad5  js      loc_1401E7B65
0x1401e7adb  lea     rdx, aDibservicevers; "DibServiceVersion"
0x1401e7ae2  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1401e7ae6  call    cs:__imp_RtlInitUnicodeString
0x1401e7aed  nop     dword ptr [rax+rax+00h]
0x1401e7af2  mov     rcx, [rsp+110h+Handle]; KeyHandle
0x1401e7af7  lea     rax, [rbp+57h+Data]
0x1401e7afb  mov     r9d, 4; Type
0x1401e7b01  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1401e7b05  mov     dword ptr [rsp+110h+ResultLength], r9d; DataSize
0x1401e7b0a  xor     r8d, r8d; TitleIndex
0x1401e7b0d  mov     qword ptr [rsp+110h+Length], rax; Data
0x1401e7b12  call    cs:__imp_ZwSetValueKey
0x1401e7b19  nop     dword ptr [rax+rax+00h]
0x1401e7b1e  jmp     short loc_1401E7B5F
0x1401e7b20  mov     rcx, [rbp+57h+var_C8]; Handle
0x1401e7b24  call    cs:__imp_ZwClose
0x1401e7b2b  nop     dword ptr [rax+rax+00h]
0x1401e7b30  jmp     loc_1401E77CE
0x1401e7b35  mov     rcx, [rsp+110h+Handle]; void *
0x1401e7b3a  lea     r8, [rbp+57h+var_C8]; void **
0x1401e7b3e  xor     r9d, r9d; unsigned __int8
0x1401e7b41  call    ?HCI_GetServicesForKey@@YAJPEAXPEAUHCI_INTERFACE@@PEAPEAXE@Z; HCI_GetServicesForKey(void *,HCI_INTERFACE *,void * *,uchar)
0x1401e7b46  mov     ebx, eax
0x1401e7b48  test    eax, eax
0x1401e7b4a  js      loc_1401E77CE
0x1401e7b50  mov     rdx, [rbp+57h+var_C8]; void *
0x1401e7b54  xor     r15d, r15d
0x1401e7b57  mov     rcx, rsi; struct DEVICE_INFO_BLOCK *
0x1401e7b5a  call    ?HCI_DibReadRemoteServices@@YAJPEAUDEVICE_INFO_BLOCK@@PEAX@Z; HCI_DibReadRemoteServices(DEVICE_INFO_BLOCK *,void *)
0x1401e7b5f  mov     ebx, eax
0x1401e7b61  test    ebx, ebx
0x1401e7b63  jns     short loc_1401E7B6D
0x1401e7b65  mov     rcx, rsi; struct DEVICE_INFO_BLOCK *
0x1401e7b68  call    ?HCI_DibFreeProtocolTree@@YAXPEAUDEVICE_INFO_BLOCK@@@Z; HCI_DibFreeProtocolTree(DEVICE_INFO_BLOCK *)
0x1401e7b6d  mov     rcx, [rbp+57h+var_C8]; Handle
0x1401e7b71  call    cs:__imp_ZwClose
0x1401e7b78  nop     dword ptr [rax+rax+00h]
0x1401e7b7d  mov     rcx, [rsp+110h+Handle]; Handle
0x1401e7b82  call    cs:__imp_ZwClose
0x1401e7b89  nop     dword ptr [rax+rax+00h]
0x1401e7b8e  test    r15, r15
0x1401e7b91  jz      short loc_1401E7BA4
0x1401e7b93  xor     edx, edx; Tag
0x1401e7b95  mov     rcx, r15; P
0x1401e7b98  call    cs:__imp_ExFreePoolWithTag
0x1401e7b9f  nop     dword ptr [rax+rax+00h]
0x1401e7ba4  mov     eax, ebx
0x1401e7ba6  mov     rcx, [rbp+57h+var_50]
  ... truncated ...
```
