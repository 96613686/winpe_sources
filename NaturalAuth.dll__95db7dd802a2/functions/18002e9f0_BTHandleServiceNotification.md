# BTHandleServiceNotification

- ea: `0x18002e9f0`
- end: `0x18002ec81`
- name: `BTHandleServiceNotification`
- size: `657`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x180004170`
- `0x18000a7f8`
- `0x18002e7b4`
- `0x18002e9f0`
- `0x18002fc80`
- `0x18002fce0`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18002eb2e`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18002eb2e`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18002eb66`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18002eb66`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PVOID *__fastcall BTHandleServiceNotification(__int64 a1, int a2, unsigned int a3, __int64 a4)
{
  PVOID *result; // rax
  __int64 v6; // rax
  PVOID v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // edi
  unsigned int v11; // esi
  PVOID v12; // rcx
  unsigned int v13; // [rsp+40h] [rbp-59h] BYREF
  __int64 v14; // [rsp+48h] [rbp-51h] BYREF
  _QWORD v15[3]; // [rsp+50h] [rbp-49h] BYREF
  char v16; // [rsp+68h] [rbp-31h]
  __int128 v17; // [rsp+70h] [rbp-29h] BYREF
  int v18; // [rsp+80h] [rbp-19h]
  int v19; // [rsp+84h] [rbp-15h]
  __int64 v20; // [rsp+88h] [rbp-11h]
  __int128 v21; // [rsp+90h] [rbp-9h]
  int v22; // [rsp+A0h] [rbp+7h]
  int v23; // [rsp+A4h] [rbp+Bh]
  __int64 v24; // [rsp+A8h] [rbp+Fh]
  __int128 v25; // [rsp+B0h] [rbp+17h]
  int v26; // [rsp+C0h] [rbp+27h]
  int v27; // [rsp+C4h] [rbp+2Bh]
  __int64 v28; // [rsp+C8h] [rbp+2Fh]

  v17 = DEVPKEY_Bluetooth_DeviceAddress;
  v18 = 1;
  v19 = 0;
  v20 = 0;
  v21 = DEVPKEY_Bluetooth_DeviceFlags;
  v22 = 3;
  v23 = 0;
  v24 = 0;
  v25 = DEVPKEY_Bluetooth_ClassOfDevice;
  v26 = 10;
  v27 = 0;
  v28 = 0;
  v13 = 0;
  v14 = 0;
  v15[1] = &v13;
  result = (PVOID *)&v14;
  v15[2] = &v14;
  v16 = 1;
  if ( a2 != 11 || *(_DWORD *)(a4 + 4) != 5 )
    return result;
  v6 = *(_QWORD *)&GUID_BTHPORT_DEVICE_INTERFACE.Data1 - *(_QWORD *)(a4 + 12);
  if ( *(_QWORD *)&GUID_BTHPORT_DEVICE_INTERFACE.Data1 == *(_QWORD *)(a4 + 12) )
    v6 = *(_QWORD *)GUID_BTHPORT_DEVICE_INTERFACE.Data4 - *(_QWORD *)(a4 + 20);
  if ( !v6 )
  {
    result = &WPP_GLOBAL_Control;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      result = (PVOID *)WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          10,
                          WPP_ed07d2fb5a9b306b316314772f279bae_Traceguids,
                          a3);
    if ( a3 == 32772 )
    {
      v7 = 0;
    }
    else
    {
      if ( a3 != 0x8000 )
      {
LABEL_14:
        v8 = v13;
LABEL_15:
        if ( !(_DWORD)v8 )
          return result;
        v9 = v14;
        return (PVOID *)DevFreeObjectProperties(v8, v9);
      }
      LOBYTE(v7) = 1;
    }
    result = (PVOID *)HandleRadioToggle(v7);
    goto LABEL_14;
  }
  result = (PVOID *)DevGetObjectProperties(1, a4 + 28, 0, 3, &v17, &v13, &v14);
  v8 = v13;
  if ( (int)result < 0 || v13 != 3 )
    goto LABEL_15;
  if ( *(_DWORD *)(v14 + 32) != 18 || *(_DWORD *)(v14 + 36) <= 2u )
  {
    v9 = v14;
    v8 = 3;
    return (PVOID *)DevFreeObjectProperties(v8, v9);
  }
  v15[0] = 0;
  result = (PVOID *)AddressFromDevPropString(*(_QWORD *)(v14 + 40), v15);
  if ( (int)result < 0 )
    goto LABEL_14;
  v9 = v14;
  if ( *(_DWORD *)(v14 + 80) == 7
    && *(_DWORD *)(v14 + 84) > 2u
    && *(_DWORD *)(v14 + 128) == 7
    && *(_DWORD *)(v14 + 132) > 2u )
  {
    v10 = **(_DWORD **)(v14 + 88);
    v11 = **(_DWORD **)(v14 + 136);
    result = &WPP_GLOBAL_Control;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      result = (PVOID *)WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          11,
                          WPP_ed07d2fb5a9b306b316314772f279bae_Traceguids,
                          a3);
      v9 = v14;
    }
    if ( a3 == 32772 )
    {
      v12 = 0;
    }
    else
    {
      if ( a3 != 0x8000 )
        goto LABEL_35;
      LOBYTE(v12) = 1;
    }
    result = (PVOID *)HandleDeviceToggle(v12, v15[0], v10, v11);
    v9 = v14;
  }
LABEL_35:
  v8 = v13;
  if ( v13 )
    return (PVOID *)DevFreeObjectProperties(v8, v9);
  return result;
}

```

## disassembly

```asm
0x18002e9f0  mov     [rsp-8+arg_0], rbx
0x18002e9f5  push    rbp
0x18002e9f6  push    rsi
0x18002e9f7  push    rdi
0x18002e9f8  lea     rbp, [rsp-47h]
0x18002e9fd  sub     rsp, 0E0h
0x18002ea04  mov     rax, cs:__security_cookie
0x18002ea0b  xor     rax, rsp
0x18002ea0e  mov     [rbp+57h+var_20], rax
0x18002ea12  mov     ebx, r8d
0x18002ea15  movups  xmm0, cs:DEVPKEY_Bluetooth_DeviceAddress
0x18002ea1c  movaps  [rbp+57h+var_80], xmm0
0x18002ea20  mov     eax, cs:dword_18004E578
0x18002ea26  mov     [rbp+57h+var_70], eax
0x18002ea29  mov     [rbp+57h+var_6C], 0
0x18002ea30  mov     [rbp+57h+var_68], 0
0x18002ea38  movups  xmm0, cs:DEVPKEY_Bluetooth_DeviceFlags
0x18002ea3f  movaps  [rbp+57h+var_60], xmm0
0x18002ea43  mov     eax, cs:dword_18004E528
0x18002ea49  mov     [rbp+57h+var_50], eax
0x18002ea4c  mov     [rbp+57h+var_4C], 0
0x18002ea53  mov     [rbp+57h+var_48], 0
0x18002ea5b  movups  xmm0, cs:DEVPKEY_Bluetooth_ClassOfDevice
0x18002ea62  movaps  [rbp+57h+var_40], xmm0
0x18002ea66  mov     eax, cs:dword_18004E560
0x18002ea6c  mov     [rbp+57h+var_30], eax
0x18002ea6f  mov     [rbp+57h+var_2C], 0
0x18002ea76  mov     [rbp+57h+var_28], 0
0x18002ea7e  mov     [rbp+57h+var_B0], 0
0x18002ea85  mov     [rbp+57h+var_A8], 0
0x18002ea8d  lea     rax, [rbp+57h+var_B0]
0x18002ea91  mov     [rbp+57h+var_98], rax
0x18002ea95  lea     rax, [rbp+57h+var_A8]
0x18002ea99  mov     [rbp+57h+var_90], rax
0x18002ea9d  mov     [rbp+57h+var_88], 1
0x18002eaa1  cmp     edx, 0Bh
0x18002eaa4  jnz     loc_18002EC62
0x18002eaaa  cmp     dword ptr [r9+4], 5
0x18002eaaf  jnz     loc_18002EC62
0x18002eab5  mov     rax, qword ptr cs:GUID_BTHPORT_DEVICE_INTERFACE.Data1
0x18002eabc  sub     rax, [r9+0Ch]
0x18002eac0  jnz     short loc_18002EACD
0x18002eac2  mov     rax, qword ptr cs:GUID_BTHPORT_DEVICE_INTERFACE.Data4
0x18002eac9  sub     rax, [r9+14h]
0x18002eacd  test    rax, rax
0x18002ead0  jnz     short loc_18002EB39
0x18002ead2  lea     rax, WPP_GLOBAL_Control
0x18002ead9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eae0  cmp     rcx, rax
0x18002eae3  jz      short loc_18002EB03
0x18002eae5  test    byte ptr [rcx+1Ch], 4
0x18002eae9  jz      short loc_18002EB03
0x18002eaeb  mov     edx, 0Ah
0x18002eaf0  mov     r9d, ebx
0x18002eaf3  lea     r8, WPP_ed07d2fb5a9b306b316314772f279bae_Traceguids
0x18002eafa  mov     rcx, [rcx+10h]
0x18002eafe  call    WPP_SF_d
0x18002eb03  cmp     ebx, 8004h
0x18002eb09  jnz     short loc_18002EB0F
0x18002eb0b  xor     ecx, ecx
0x18002eb0d  jmp     short loc_18002EB19
0x18002eb0f  cmp     ebx, 8000h
0x18002eb15  jnz     short loc_18002EB1F
0x18002eb17  mov     cl, 1
0x18002eb19  call    HandleRadioToggle
0x18002eb1e  nop
0x18002eb1f  mov     ecx, [rbp+57h+var_B0]
0x18002eb22  test    ecx, ecx
0x18002eb24  jz      loc_18002EC62
0x18002eb2a  mov     rdx, [rbp+57h+var_A8]
0x18002eb2e  call    cs:__imp_DevFreeObjectProperties
0x18002eb34  jmp     loc_18002EC62
0x18002eb39  lea     rdx, [r9+1Ch]
0x18002eb3d  lea     rax, [rbp+57h+var_A8]
0x18002eb41  mov     [rsp+0F0h+var_C0], rax
0x18002eb46  lea     rax, [rbp+57h+var_B0]
0x18002eb4a  mov     [rsp+0F0h+var_C8], rax
0x18002eb4f  lea     rax, [rbp+57h+var_80]
0x18002eb53  mov     [rsp+0F0h+var_D0], rax
0x18002eb58  mov     edi, 3
0x18002eb5d  mov     r9d, edi
0x18002eb60  xor     r8d, r8d
0x18002eb63  lea     ecx, [rdi-2]
0x18002eb66  call    cs:__imp_DevGetObjectProperties
0x18002eb6c  mov     ecx, [rbp+57h+var_B0]
0x18002eb6f  test    eax, eax
0x18002eb71  js      loc_18002EC5D
0x18002eb77  cmp     ecx, edi
0x18002eb79  jnz     loc_18002EC5D
0x18002eb7f  mov     rax, [rbp+57h+var_A8]
0x18002eb83  cmp     dword ptr [rax+20h], 12h
0x18002eb87  jnz     loc_18002EC53
0x18002eb8d  cmp     dword ptr [rax+24h], 2
0x18002eb91  jbe     loc_18002EC53
0x18002eb97  mov     [rbp+57h+var_A0], 0
0x18002eb9f  lea     rdx, [rbp+57h+var_A0]
0x18002eba3  mov     rcx, [rax+28h]
0x18002eba7  call    AddressFromDevPropString
0x18002ebac  test    eax, eax
0x18002ebae  js      loc_18002EB1F
0x18002ebb4  mov     rdx, [rbp+57h+var_A8]
0x18002ebb8  cmp     dword ptr [rdx+50h], 7
0x18002ebbc  jnz     loc_18002EC47
0x18002ebc2  cmp     dword ptr [rdx+54h], 2
0x18002ebc6  jbe     short loc_18002EC47
0x18002ebc8  cmp     dword ptr [rdx+80h], 7
0x18002ebcf  jnz     short loc_18002EC47
0x18002ebd1  cmp     dword ptr [rdx+84h], 2
0x18002ebd8  jbe     short loc_18002EC47
0x18002ebda  mov     rax, [rdx+58h]
0x18002ebde  mov     edi, [rax]
0x18002ebe0  mov     rax, [rdx+88h]
0x18002ebe7  mov     esi, [rax]
0x18002ebe9  lea     rax, WPP_GLOBAL_Control
0x18002ebf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ebf7  cmp     rcx, rax
0x18002ebfa  jz      short loc_18002EC1E
0x18002ebfc  test    byte ptr [rcx+1Ch], 4
0x18002ec00  jz      short loc_18002EC1E
0x18002ec02  mov     edx, 0Bh
0x18002ec07  mov     r9d, ebx
0x18002ec0a  lea     r8, WPP_ed07d2fb5a9b306b316314772f279bae_Traceguids
0x18002ec11  mov     rcx, [rcx+10h]
0x18002ec15  call    WPP_SF_d
0x18002ec1a  mov     rdx, [rbp+57h+var_A8]
0x18002ec1e  cmp     ebx, 8004h
0x18002ec24  jnz     short loc_18002EC2A
0x18002ec26  xor     ecx, ecx
0x18002ec28  jmp     short loc_18002EC34
0x18002ec2a  cmp     ebx, 8000h
0x18002ec30  jnz     short loc_18002EC47
0x18002ec32  mov     cl, 1
0x18002ec34  mov     r9d, esi
0x18002ec37  mov     r8d, edi
0x18002ec3a  mov     rdx, [rbp+57h+var_A0]
0x18002ec3e  call    HandleDeviceToggle
0x18002ec43  mov     rdx, [rbp+57h+var_A8]
0x18002ec47  mov     ecx, [rbp+57h+var_B0]
0x18002ec4a  test    ecx, ecx
0x18002ec4c  jz      short loc_18002EC62
0x18002ec4e  jmp     loc_18002EB2E
0x18002ec53  mov     rdx, rax
0x18002ec56  mov     ecx, edi
0x18002ec58  jmp     loc_18002EB2E
0x18002ec5d  jmp     loc_18002EB22
0x18002ec62  mov     rcx, [rbp+57h+var_20]
0x18002ec66  xor     rcx, rsp; StackCookie
0x18002ec69  call    __security_check_cookie
0x18002ec6e  mov     rbx, [rsp+0F0h+arg_0]
0x18002ec76  add     rsp, 0E0h
0x18002ec7d  pop     rdi
0x18002ec7e  pop     rsi
0x18002ec7f  pop     rbp
0x18002ec80  retn
```
