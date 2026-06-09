# BthUsb_GetDeviceDescriptor(_DEVICE_EXTENSION *)

- ea: `0x14001a6e8`
- end: `0x14001ac75`
- name: `?BthUsb_GetDeviceDescriptor@@_Y2PAGE@@AJPEAU_DEVICE_EXTENSION@@@Z`
- size: `1421`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140018b90`

## callees

- `0x14000175c`
- `0x1400017d4`
- `0x140001924`
- `0x14000e1c0`
- `0x14001a6e8`
- `0x14001bd90`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001a76a`
- `ntoskrnl!ExAllocatePool2` at `0x14001a76a`

## pseudocode

```c
__int64 __fastcall BthUsb_GetDeviceDescriptor(struct _DEVICE_EXTENSION *a1, __int64 a2, int a3)
{
  char v4; // bl
  bool v5; // dl
  int v6; // edx
  int v7; // r8d
  int v8; // esi
  _USB_DEVICE_DESCRIPTOR *Pool2; // rax
  int v10; // r8d
  _USB_DEVICE_DESCRIPTOR *v11; // rsi
  bool v12; // dl
  struct _DEVICE_OBJECT *TopOfStack; // rcx
  int v14; // r8d
  bool v15; // dl
  int v16; // r8d
  bool v17; // dl
  int v18; // edx
  int v19; // edx
  int v20; // edx
  int v21; // edx
  int v22; // edx
  int v23; // edx
  int v24; // edx
  int v25; // edx
  int v26; // edx
  int v27; // edx
  int v28; // r8d
  bool v29; // dl
  _QWORD v31[26]; // [rsp+50h] [rbp-79h] BYREF

  v4 = 1;
  v5 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v5,
    a3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    2,
    12,
    (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids);
  v8 = 0;
  if ( !a1->DeviceDescriptor )
  {
    Pool2 = (_USB_DEVICE_DESCRIPTOR *)ExAllocatePool2(64, 18, 1111642965);
    a1->DeviceDescriptor = Pool2;
    v11 = Pool2;
    if ( Pool2 )
    {
      memset(v31, 0, 0x98u);
      TopOfStack = a1->TopOfStack;
      LODWORD(v31[0]) = 721032;
      HIDWORD(v31[4]) = 18;
      v31[6] = 0;
      v31[5] = v11;
      *(_DWORD *)((char *)&v31[16] + 2) = 256;
      v31[7] = 0;
      v8 = USBCallSyncEx(TopOfStack, (unsigned __int64)v31, 500, &a1->RemoveLock);
      if ( v8 >= 0 )
      {
        LOBYTE(v6) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          v6,
          (_DWORD)WPP_GLOBAL_Control,
          WPP_GLOBAL_Control->DeviceExtension);
        v15 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v15,
          v14,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          2,
          15,
          (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids);
        v17 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v17,
          v16,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          2,
          16,
          (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids);
        LOBYTE(v18) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          v18,
          a1->DeviceDescriptor->bLength,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          2,
          17,
          (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
          a1->DeviceDescriptor->bLength);
        LOBYTE(v19) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          v19,
          a1->DeviceDescriptor->bcdUSB,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          2,
          18,
          (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
          a1->DeviceDescriptor->bcdUSB);
        LOBYTE(v20) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          v20,
          a1->DeviceDescriptor->bDeviceClass,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          2,
          19,
          (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
          a1->DeviceDescriptor->bDeviceClass);
        LOBYTE(v21) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          v21,
          a1->DeviceDescriptor->bDeviceSubClass,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          2,
          20,
          (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
          a1->DeviceDescriptor->bDeviceSubClass);
        LOBYTE(v22) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          v22,
          a1->DeviceDescriptor->bDeviceProtocol,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          2,
          21,
          (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
          a1->DeviceDescriptor->bDeviceProtocol);
        LOBYTE(v23) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          v23,
          a1->DeviceDescriptor->idVendor,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          2,
          22,
          (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
          a1->DeviceDescriptor->idVendor);
        LOBYTE(v24) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          v24,
          a1->DeviceDescriptor->idProduct,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          2,
          23,
          (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
          a1->DeviceDescriptor->idProduct);
        LOBYTE(v25) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          v25,
          a1->DeviceDescriptor->iManufacturer,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          2,
          24,
          (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
          a1->DeviceDescriptor->iManufacturer);
        LOBYTE(v26) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          v26,
          a1->DeviceDescriptor->iProduct,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          2,
          25,
          (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
          a1->DeviceDescriptor->iProduct);
        LOBYTE(v27) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          v27,
          a1->DeviceDescriptor->bNumConfigurations,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          2,
          26,
          (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
          a1->DeviceDescriptor->bNumConfigurations);
        v29 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v29,
          v28,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          2,
          27,
          (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids);
      }
    }
    else
    {
      v12 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v12,
        v10,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        2,
        13,
        (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids);
      v8 = -1073741670;
    }
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v4 = 0;
  LOBYTE(v6) = v4;
  WPP_RECORDER_AND_TRACE_SF_D(
    WPP_GLOBAL_Control->AttachedDevice,
    v6,
    v7,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    2,
    28,
    (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
    v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14001a6e8  push    rbp
0x14001a6ea  push    rbx
0x14001a6eb  push    rsi
0x14001a6ec  push    rdi
0x14001a6ed  push    r13
0x14001a6ef  push    r14
0x14001a6f1  push    r15
0x14001a6f3  lea     rbp, [rsp-27h]
0x14001a6f8  sub     rsp, 0F0h
0x14001a6ff  mov     rdi, rcx
0x14001a702  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a709  mov     r15d, 2
0x14001a70f  mov     bl, 1
0x14001a711  mov     r14b, 4
0x14001a714  mov     eax, [rcx+2Ch]
0x14001a717  test    r15b, al
0x14001a71a  jz      short loc_14001A726
0x14001a71c  cmp     [rcx+29h], r14b
0x14001a720  jb      short loc_14001A726
0x14001a722  mov     dl, bl
0x14001a724  jmp     short loc_14001A728
0x14001a726  xor     dl, dl
0x14001a728  mov     r9, [rcx+40h]
0x14001a72c  lea     r13, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001a733  mov     rcx, [rcx+18h]
0x14001a737  mov     [rsp+120h+var_E8], r13
0x14001a73c  mov     [rsp+120h+var_F0], 0Ch
0x14001a743  mov     [rsp+120h+var_F8], r15d
0x14001a748  mov     [rsp+120h+var_100], r14b
0x14001a74d  call    WPP_RECORDER_AND_TRACE_SF_
0x14001a752  xor     esi, esi
0x14001a754  cmp     [rdi+60h], rsi
0x14001a758  jnz     loc_14001AC20
0x14001a75e  lea     edx, [rsi+12h]
0x14001a761  mov     r8d, 42425355h
0x14001a767  lea     ecx, [rsi+40h]
0x14001a76a  call    cs:__imp_ExAllocatePool2
0x14001a771  nop     dword ptr [rax+rax+00h]
0x14001a776  mov     [rdi+60h], rax
0x14001a77a  mov     rsi, rax
0x14001a77d  test    rax, rax
0x14001a780  jnz     short loc_14001A7CA
0x14001a782  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a789  mov     eax, [rcx+2Ch]
0x14001a78c  test    r15b, al
0x14001a78f  jz      short loc_14001A79B
0x14001a791  cmp     [rcx+29h], r15b
0x14001a795  jb      short loc_14001A79B
0x14001a797  mov     dl, bl
0x14001a799  jmp     short loc_14001A79D
0x14001a79b  xor     dl, dl
0x14001a79d  mov     r9, [rcx+40h]
0x14001a7a1  mov     rcx, [rcx+18h]
0x14001a7a5  mov     [rsp+120h+var_E8], r13
0x14001a7aa  mov     [rsp+120h+var_F0], 0Dh
0x14001a7b1  mov     [rsp+120h+var_F8], r15d
0x14001a7b6  mov     [rsp+120h+var_100], r15b
0x14001a7bb  call    WPP_RECORDER_AND_TRACE_SF_
0x14001a7c0  mov     esi, 0C000009Ah
0x14001a7c5  jmp     loc_14001AC20
0x14001a7ca  xor     edx, edx; Val
0x14001a7cc  lea     rcx, [rbp+57h+var_D0]; void *
0x14001a7d0  mov     r8d, 98h; Size
0x14001a7d6  call    memset
0x14001a7db  mov     rcx, [rdi+28h]; Tag
0x14001a7df  lea     r9, [rdi+30h]
0x14001a7e3  mov     r8d, 1F4h
0x14001a7e9  mov     [rbp+57h+var_D0], 0B0088h
0x14001a7f0  lea     rdx, [rbp+57h+var_D0]
0x14001a7f4  mov     [rbp+57h+var_AC], 12h
0x14001a7fb  mov     [rbp+57h+var_A0], 0
0x14001a803  mov     [rbp+57h+var_A8], rsi
0x14001a807  mov     [rbp+57h+var_4E], 100h
0x14001a80e  mov     [rbp+57h+var_98], 0
0x14001a816  call    USBCallSyncEx
0x14001a81b  mov     esi, eax
0x14001a81d  test    eax, eax
0x14001a81f  js      loc_14001AC20
0x14001a825  mov     r8, cs:WPP_GLOBAL_Control
0x14001a82c  mov     ecx, [r8+2Ch]
0x14001a830  test    r15b, cl
0x14001a833  jz      short loc_14001A83F
0x14001a835  cmp     [r8+29h], r14b
0x14001a839  jb      short loc_14001A83F
0x14001a83b  mov     dl, bl
0x14001a83d  jmp     short loc_14001A841
0x14001a83f  xor     dl, dl
0x14001a841  mov     eax, [rbp+57h+var_AC]
0x14001a844  mov     r9, [r8+40h]
0x14001a848  mov     rcx, [r8+18h]
0x14001a84c  mov     [rsp+120h+var_D8], eax
0x14001a850  mov     rax, [rdi+60h]
0x14001a854  mov     [rsp+120h+var_E0], rax
0x14001a859  mov     [rsp+120h+var_E8], r13
0x14001a85e  mov     [rsp+120h+var_F0], 0Eh
0x14001a865  mov     [rsp+120h+var_F8], r15d
0x14001a86a  call    WPP_RECORDER_AND_TRACE_SF_qD
0x14001a86f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a876  mov     eax, [rcx+2Ch]
0x14001a879  test    r15b, al
0x14001a87c  jz      short loc_14001A888
0x14001a87e  cmp     [rcx+29h], r14b
0x14001a882  jb      short loc_14001A888
0x14001a884  mov     dl, bl
0x14001a886  jmp     short loc_14001A88A
0x14001a888  xor     dl, dl
0x14001a88a  mov     r9, [rcx+40h]
0x14001a88e  mov     rcx, [rcx+18h]
0x14001a892  mov     [rsp+120h+var_E8], r13
0x14001a897  mov     [rsp+120h+var_F0], 0Fh
0x14001a89e  mov     [rsp+120h+var_F8], r15d
0x14001a8a3  mov     [rsp+120h+var_100], r14b
0x14001a8a8  call    WPP_RECORDER_AND_TRACE_SF_
0x14001a8ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a8b4  mov     eax, [rcx+2Ch]
0x14001a8b7  test    r15b, al
0x14001a8ba  jz      short loc_14001A8C6
0x14001a8bc  cmp     [rcx+29h], r14b
0x14001a8c0  jb      short loc_14001A8C6
0x14001a8c2  mov     dl, bl
0x14001a8c4  jmp     short loc_14001A8C8
0x14001a8c6  xor     dl, dl
0x14001a8c8  mov     r9, [rcx+40h]
0x14001a8cc  mov     rcx, [rcx+18h]
0x14001a8d0  mov     [rsp+120h+var_E8], r13
0x14001a8d5  mov     [rsp+120h+var_F0], 10h
0x14001a8dc  mov     [rsp+120h+var_F8], r15d
0x14001a8e1  mov     [rsp+120h+var_100], r14b
0x14001a8e6  call    WPP_RECORDER_AND_TRACE_SF_
0x14001a8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a8f2  mov     eax, [rcx+2Ch]
0x14001a8f5  test    r15b, al
0x14001a8f8  jz      short loc_14001A904
0x14001a8fa  cmp     [rcx+29h], r14b
0x14001a8fe  jb      short loc_14001A904
0x14001a900  mov     dl, bl
0x14001a902  jmp     short loc_14001A906
0x14001a904  xor     dl, dl
0x14001a906  mov     rax, [rdi+60h]
0x14001a90a  mov     r9, [rcx+40h]
0x14001a90e  mov     rcx, [rcx+18h]
0x14001a912  movzx   r8d, byte ptr [rax]
0x14001a916  mov     dword ptr [rsp+120h+var_E0], r8d
0x14001a91b  mov     [rsp+120h+var_E8], r13
0x14001a920  mov     [rsp+120h+var_F0], 11h
0x14001a927  mov     [rsp+120h+var_F8], r15d
0x14001a92c  mov     [rsp+120h+var_100], r14b
0x14001a931  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001a936  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a93d  mov     eax, [rcx+2Ch]
0x14001a940  test    r15b, al
0x14001a943  jz      short loc_14001A94F
0x14001a945  cmp     [rcx+29h], r14b
0x14001a949  jb      short loc_14001A94F
0x14001a94b  mov     dl, bl
0x14001a94d  jmp     short loc_14001A951
0x14001a94f  xor     dl, dl
0x14001a951  mov     rax, [rdi+60h]
0x14001a955  mov     r9, [rcx+40h]
0x14001a959  mov     rcx, [rcx+18h]
0x14001a95d  movzx   r8d, word ptr [rax+2]
0x14001a962  mov     dword ptr [rsp+120h+var_E0], r8d
0x14001a967  mov     [rsp+120h+var_E8], r13
0x14001a96c  mov     [rsp+120h+var_F0], 12h
0x14001a973  mov     [rsp+120h+var_F8], r15d
0x14001a978  mov     [rsp+120h+var_100], r14b
0x14001a97d  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001a982  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a989  mov     eax, [rcx+2Ch]
0x14001a98c  test    r15b, al
0x14001a98f  jz      short loc_14001A99B
0x14001a991  cmp     [rcx+29h], r14b
0x14001a995  jb      short loc_14001A99B
0x14001a997  mov     dl, bl
0x14001a999  jmp     short loc_14001A99D
0x14001a99b  xor     dl, dl
0x14001a99d  mov     rax, [rdi+60h]
0x14001a9a1  mov     r9, [rcx+40h]
0x14001a9a5  mov     rcx, [rcx+18h]
0x14001a9a9  movzx   r8d, byte ptr [rax+4]
0x14001a9ae  mov     dword ptr [rsp+120h+var_E0], r8d
0x14001a9b3  mov     [rsp+120h+var_E8], r13
0x14001a9b8  mov     [rsp+120h+var_F0], 13h
0x14001a9bf  mov     [rsp+120h+var_F8], r15d
0x14001a9c4  mov     [rsp+120h+var_100], r14b
0x14001a9c9  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001a9ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a9d5  mov     eax, [rcx+2Ch]
0x14001a9d8  test    r15b, al
0x14001a9db  jz      short loc_14001A9E7
0x14001a9dd  cmp     [rcx+29h], r14b
0x14001a9e1  jb      short loc_14001A9E7
0x14001a9e3  mov     dl, bl
0x14001a9e5  jmp     short loc_14001A9E9
0x14001a9e7  xor     dl, dl
0x14001a9e9  mov     rax, [rdi+60h]
0x14001a9ed  mov     r9, [rcx+40h]
0x14001a9f1  mov     rcx, [rcx+18h]
0x14001a9f5  movzx   r8d, byte ptr [rax+5]
0x14001a9fa  mov     dword ptr [rsp+120h+var_E0], r8d
0x14001a9ff  mov     [rsp+120h+var_E8], r13
0x14001aa04  mov     [rsp+120h+var_F0], 14h
0x14001aa0b  mov     [rsp+120h+var_F8], r15d
0x14001aa10  mov     [rsp+120h+var_100], r14b
0x14001aa15  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001aa1a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aa21  mov     eax, [rcx+2Ch]
0x14001aa24  test    r15b, al
0x14001aa27  jz      short loc_14001AA33
0x14001aa29  cmp     [rcx+29h], r14b
0x14001aa2d  jb      short loc_14001AA33
0x14001aa2f  mov     dl, bl
0x14001aa31  jmp     short loc_14001AA35
0x14001aa33  xor     dl, dl
0x14001aa35  mov     rax, [rdi+60h]
0x14001aa39  mov     r9, [rcx+40h]
0x14001aa3d  mov     rcx, [rcx+18h]
0x14001aa41  movzx   r8d, byte ptr [rax+6]
0x14001aa46  mov     dword ptr [rsp+120h+var_E0], r8d
0x14001aa4b  mov     [rsp+120h+var_E8], r13
0x14001aa50  mov     [rsp+120h+var_F0], 15h
0x14001aa57  mov     [rsp+120h+var_F8], r15d
0x14001aa5c  mov     [rsp+120h+var_100], r14b
0x14001aa61  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001aa66  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aa6d  mov     eax, [rcx+2Ch]
0x14001aa70  test    r15b, al
0x14001aa73  jz      short loc_14001AA7F
0x14001aa75  cmp     [rcx+29h], r14b
0x14001aa79  jb      short loc_14001AA7F
0x14001aa7b  mov     dl, bl
0x14001aa7d  jmp     short loc_14001AA81
0x14001aa7f  xor     dl, dl
0x14001aa81  mov     rax, [rdi+60h]
0x14001aa85  mov     r9, [rcx+40h]
0x14001aa89  mov     rcx, [rcx+18h]
0x14001aa8d  movzx   r8d, word ptr [rax+8]
0x14001aa92  mov     dword ptr [rsp+120h+var_E0], r8d
0x14001aa97  mov     [rsp+120h+var_E8], r13
0x14001aa9c  mov     [rsp+120h+var_F0], 16h
0x14001aaa3  mov     [rsp+120h+var_F8], r15d
0x14001aaa8  mov     [rsp+120h+var_100], r14b
0x14001aaad  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001aab2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aab9  mov     eax, [rcx+2Ch]
0x14001aabc  test    r15b, al
0x14001aabf  jz      short loc_14001AACB
0x14001aac1  cmp     [rcx+29h], r14b
0x14001aac5  jb      short loc_14001AACB
0x14001aac7  mov     dl, bl
0x14001aac9  jmp     short loc_14001AACD
0x14001aacb  xor     dl, dl
0x14001aacd  mov     rax, [rdi+60h]
0x14001aad1  mov     r9, [rcx+40h]
0x14001aad5  mov     rcx, [rcx+18h]
0x14001aad9  movzx   r8d, word ptr [rax+0Ah]
0x14001aade  mov     dword ptr [rsp+120h+var_E0], r8d
0x14001aae3  mov     [rsp+120h+var_E8], r13
0x14001aae8  mov     [rsp+120h+var_F0], 17h
0x14001aaef  mov     [rsp+120h+var_F8], r15d
0x14001aaf4  mov     [rsp+120h+var_100], r14b
0x14001aaf9  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001aafe  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ab05  mov     eax, [rcx+2Ch]
0x14001ab08  test    r15b, al
0x14001ab0b  jz      short loc_14001AB17
0x14001ab0d  cmp     [rcx+29h], r14b
0x14001ab11  jb      short loc_14001AB17
0x14001ab13  mov     dl, bl
0x14001ab15  jmp     short loc_14001AB19
0x14001ab17  xor     dl, dl
0x14001ab19  mov     rax, [rdi+60h]
0x14001ab1d  mov     r9, [rcx+40h]
0x14001ab21  mov     rcx, [rcx+18h]
0x14001ab25  movzx   r8d, byte ptr [rax+0Eh]
0x14001ab2a  mov     dword ptr [rsp+120h+var_E0], r8d
0x14001ab2f  mov     [rsp+120h+var_E8], r13
0x14001ab34  mov     [rsp+120h+var_F0], 18h
0x14001ab3b  mov     [rsp+120h+var_F8], r15d
0x14001ab40  mov     [rsp+120h+var_100], r14b
0x14001ab45  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001ab4a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ab51  mov     eax, [rcx+2Ch]
0x14001ab54  test    r15b, al
0x14001ab57  jz      short loc_14001AB63
0x14001ab59  cmp     [rcx+29h], r14b
0x14001ab5d  jb      short loc_14001AB63
0x14001ab5f  mov     dl, bl
0x14001ab61  jmp     short loc_14001AB65
0x14001ab63  xor     dl, dl
0x14001ab65  mov     rax, [rdi+60h]
0x14001ab69  mov     r9, [rcx+40h]
0x14001ab6d  mov     rcx, [rcx+18h]
0x14001ab71  movzx   r8d, byte ptr [rax+0Fh]
0x14001ab76  mov     dword ptr [rsp+120h+var_E0], r8d
0x14001ab7b  mov     [rsp+120h+var_E8], r13
0x14001ab80  mov     [rsp+120h+var_F0], 19h
0x14001ab87  mov     [rsp+120h+var_F8], r15d
0x14001ab8c  mov     [rsp+120h+var_100], r14b
0x14001ab91  call    WPP_RECORDER_AND_TRACE_SF_D
  ... truncated ...
```
