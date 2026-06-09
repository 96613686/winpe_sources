# BthUsb_QuerySelectiveSuspend(_BTDEVICE *)

- ea: `0x1400179ac`
- end: `0x140017c03`
- name: `?BthUsb_QuerySelectiveSuspend@@YAEPEAU_BTDEVICE@@@Z`
- size: `599`
- prototype: `unsigned __int8 __fastcall(struct _BTDEVICE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x140018b90`

## callees

- `0x1400017d4`
- `0x14000ddc0`
- `0x14000e1c0`
- `0x1400179ac`
- `0x14001bd90`
- `0x14001c0a4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140017a53`
- `ntoskrnl!ZwClose` at `0x140017b7c`
- `ntoskrnl!ZwClose` at `0x140017a53`
- `ntoskrnl!ZwClose` at `0x140017b7c`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140017a17`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140017b3c`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140017a17`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140017b3c`

## pseudocode

```c
unsigned __int8 __fastcall BthUsb_QuerySelectiveSuspend(struct _BTDEVICE *a1)
{
  char *MiniportContext; // rsi
  unsigned __int8 v3; // di
  __int64 v4; // rdx
  __int64 v5; // rcx
  char v6; // cl
  __int16 v8; // [rsp+50h] [rbp-B0h] BYREF
  int v9; // [rsp+54h] [rbp-ACh]
  void *DeviceRegKey; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v11[18]; // [rsp+60h] [rbp-A0h] BYREF

  MiniportContext = (char *)a1->MiniportContext;
  DeviceRegKey = 0;
  v8 = 0;
  v9 = 1;
  v3 = 0;
  memset(v11, 0, 0x88u);
  if ( IoOpenDeviceRegistryKey(a1->PhysicalDeviceObject, 1u, 0x20000u, &DeviceRegKey) >= 0 )
  {
    v3 = (int)BthQueryKeyValue(DeviceRegKey) >= 0;
    ZwClose(DeviceRegKey);
    if ( v3 )
    {
      *(_BYTE *)(*((_QWORD *)MiniportContext + 13) + 7LL) |= 0x60u;
      v5 = *((_QWORD *)MiniportContext + 13);
      MiniportContext[1170] = 1;
      MiniportContext[1168] = (*(_BYTE *)(v5 + 7) & 0x20) != 0;
      MiniportContext[1169] = (*(_BYTE *)(v5 + 7) & 0x40) != 0;
LABEL_12:
      MiniportContext[1172] = 1;
      goto LABEL_13;
    }
  }
  LODWORD(v11[0]) = 1245320;
  v11[5] = &v8;
  HIDWORD(v11[4]) = 2;
  WORD2(v11[16]) = 0;
  v11[7] = 0;
  v11[6] = 0;
  if ( (int)USBCallSyncEx(
              *((struct _DEVICE_OBJECT **)MiniportContext + 5),
              (unsigned __int64)v11,
              500,
              (struct _IO_REMOVE_LOCK *)(MiniportContext + 48)) >= 0 )
  {
    v4 = *((_QWORD *)MiniportContext + 13);
    v6 = v8 & 1;
    MiniportContext[1170] = v8 & 1;
    MiniportContext[1168] = (*(_BYTE *)(v4 + 7) & 0x20) != 0;
    MiniportContext[1169] = (*(_BYTE *)(v4 + 7) & 0x40) != 0;
    if ( v6 )
    {
      if ( (*(_BYTE *)(v4 + 7) & 0x60) == 0x60 )
      {
        MiniportContext[1171] = 0;
        v3 = 1;
        if ( IoOpenDeviceRegistryKey(a1->PhysicalDeviceObject, 1u, 0x20000u, &DeviceRegKey) < 0 )
          goto LABEL_12;
        if ( (int)BthQueryKeyValue(DeviceRegKey) >= 0 && !v9 )
        {
          MiniportContext[1171] = 1;
          v3 = 0;
        }
        ZwClose(DeviceRegKey);
        if ( v3 )
          goto LABEL_12;
      }
    }
  }
LABEL_13:
  LOBYTE(v4) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_D(
    WPP_GLOBAL_Control->AttachedDevice,
    v4,
    v3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    1,
    29,
    (__int64)WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids,
    v3);
  return v3;
}

```

## disassembly

```asm
0x1400179ac  push    rbp
0x1400179ae  push    rbx
0x1400179af  push    rsi
0x1400179b0  push    rdi
0x1400179b1  push    r12
0x1400179b3  push    r14
0x1400179b5  lea     rbp, [rsp-8]
0x1400179ba  sub     rsp, 108h
0x1400179c1  mov     rax, cs:__security_cookie
0x1400179c8  xor     rax, rsp
0x1400179cb  mov     [rbp+30h+var_40], rax
0x1400179cf  mov     rsi, [rcx]
0x1400179d2  mov     rbx, rcx
0x1400179d5  xor     eax, eax
0x1400179d7  mov     [rsp+130h+DeviceRegKey], 0
0x1400179e0  mov     r14d, 1
0x1400179e6  mov     [rsp+130h+var_E0], ax
0x1400179eb  lea     rcx, [rsp+130h+var_D0]; void *
0x1400179f0  mov     [rsp+130h+var_DC], r14d
0x1400179f5  xor     edx, edx; Val
0x1400179f7  mov     r8d, 88h; Size
0x1400179fd  xor     dil, dil
0x140017a00  call    memset
0x140017a05  mov     rcx, [rbx+10h]; DeviceObject
0x140017a09  lea     r9, [rsp+130h+DeviceRegKey]; DeviceRegKey
0x140017a0e  mov     r8d, 20000h; DesiredAccess
0x140017a14  mov     edx, r14d; DevInstKeyType
0x140017a17  call    cs:__imp_IoOpenDeviceRegistryKey
0x140017a1e  nop     dword ptr [rax+rax+00h]
0x140017a23  test    eax, eax
0x140017a25  js      short loc_140017A9A
0x140017a27  mov     rcx, [rsp+130h+DeviceRegKey]; KeyHandle
0x140017a2c  lea     r8, [rsp+130h+var_DC]
0x140017a31  lea     rdx, aForceselective; "ForceSelectiveSuspend"
0x140017a38  call    BthQueryKeyValue
0x140017a3d  test    eax, eax
0x140017a3f  js      short loc_140017A4E
0x140017a41  cmp     [rsp+130h+var_DC], r14d
0x140017a46  movzx   edi, dil
0x140017a4a  cmovz   edi, r14d
0x140017a4e  mov     rcx, [rsp+130h+DeviceRegKey]; Handle
0x140017a53  call    cs:__imp_ZwClose
0x140017a5a  nop     dword ptr [rax+rax+00h]
0x140017a5f  test    dil, dil
0x140017a62  jz      short loc_140017A9A
0x140017a64  mov     rax, [rsi+68h]
0x140017a68  or      byte ptr [rax+7], 60h
0x140017a6c  mov     rcx, [rsi+68h]
0x140017a70  mov     [rsi+492h], r14b
0x140017a77  mov     al, [rcx+7]
0x140017a7a  shr     al, 5
0x140017a7d  and     al, r14b
0x140017a80  mov     [rsi+490h], al
0x140017a86  mov     al, [rcx+7]
0x140017a89  shr     al, 6
0x140017a8c  and     al, r14b
0x140017a8f  mov     [rsi+491h], al
0x140017a95  jmp     loc_140017B8D
0x140017a9a  lea     rax, [rsp+130h+var_E0]
0x140017a9f  mov     [rsp+130h+var_D0], 130088h
0x140017aa7  mov     [rbp+30h+var_A8], rax
0x140017aab  lea     r9, [rsi+30h]
0x140017aaf  xor     eax, eax
0x140017ab1  mov     [rbp+30h+var_AC], 2
0x140017ab8  mov     [rbp+30h+var_4C], ax
0x140017abc  lea     rdx, [rsp+130h+var_D0]
0x140017ac1  mov     [rbp+30h+var_98], rax
0x140017ac5  mov     r8d, 1F4h
0x140017acb  mov     [rbp+30h+var_A0], 0
0x140017ad3  mov     rcx, [rsi+28h]; Tag
0x140017ad7  call    USBCallSyncEx
0x140017adc  test    eax, eax
0x140017ade  js      loc_140017B94
0x140017ae4  mov     cl, byte ptr [rsp+130h+var_E0]
0x140017ae8  mov     rdx, [rsi+68h]
0x140017aec  and     cl, r14b
0x140017aef  mov     [rsi+492h], cl
0x140017af5  mov     al, [rdx+7]
0x140017af8  shr     al, 5
0x140017afb  and     al, r14b
0x140017afe  mov     [rsi+490h], al
0x140017b04  mov     al, [rdx+7]
0x140017b07  shr     al, 6
0x140017b0a  and     al, r14b
0x140017b0d  mov     [rsi+491h], al
0x140017b13  test    cl, cl
0x140017b15  jz      short loc_140017B94
0x140017b17  mov     al, [rdx+7]
0x140017b1a  and     al, 60h
0x140017b1c  cmp     al, 60h ; '`'
0x140017b1e  jnz     short loc_140017B94
0x140017b20  mov     byte ptr [rsi+493h], 0
0x140017b27  lea     r9, [rsp+130h+DeviceRegKey]; DeviceRegKey
0x140017b2c  mov     rcx, [rbx+10h]; DeviceObject
0x140017b30  mov     r8d, 20000h; DesiredAccess
0x140017b36  mov     edx, r14d; DevInstKeyType
0x140017b39  mov     dil, r14b
0x140017b3c  call    cs:__imp_IoOpenDeviceRegistryKey
0x140017b43  nop     dword ptr [rax+rax+00h]
0x140017b48  test    eax, eax
0x140017b4a  js      short loc_140017B8D
0x140017b4c  mov     rcx, [rsp+130h+DeviceRegKey]; KeyHandle
0x140017b51  lea     r8, [rsp+130h+var_DC]
0x140017b56  lea     rdx, aSelectivesuspe; "SelectiveSuspendSupported"
0x140017b5d  call    BthQueryKeyValue
0x140017b62  test    eax, eax
0x140017b64  js      short loc_140017B77
0x140017b66  cmp     [rsp+130h+var_DC], 0
0x140017b6b  jnz     short loc_140017B77
0x140017b6d  mov     [rsi+493h], r14b
0x140017b74  xor     dil, dil
0x140017b77  mov     rcx, [rsp+130h+DeviceRegKey]; Handle
0x140017b7c  call    cs:__imp_ZwClose
0x140017b83  nop     dword ptr [rax+rax+00h]
0x140017b88  test    dil, dil
0x140017b8b  jz      short loc_140017B94
0x140017b8d  mov     [rsi+494h], r14b
0x140017b94  mov     rcx, cs:WPP_GLOBAL_Control
0x140017b9b  mov     eax, [rcx+2Ch]
0x140017b9e  test    r14b, al
0x140017ba1  jz      short loc_140017BAE
0x140017ba3  cmp     byte ptr [rcx+29h], 4
0x140017ba7  jb      short loc_140017BAE
0x140017ba9  mov     dl, r14b
0x140017bac  jmp     short loc_140017BB0
0x140017bae  xor     dl, dl
0x140017bb0  mov     r9, [rcx+40h]
0x140017bb4  lea     rax, WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids
0x140017bbb  mov     rcx, [rcx+18h]
0x140017bbf  movzx   r8d, dil
0x140017bc3  mov     [rsp+130h+var_F0], r8d
0x140017bc8  mov     [rsp+130h+var_F8], rax
0x140017bcd  mov     [rsp+130h+var_100], 1Dh
0x140017bd4  mov     [rsp+130h+var_108], r14d
0x140017bd9  mov     [rsp+130h+var_110], 4
0x140017bde  call    WPP_RECORDER_AND_TRACE_SF_D
0x140017be3  mov     al, dil
0x140017be6  mov     rcx, [rbp+30h+var_40]
0x140017bea  xor     rcx, rsp; StackCookie
0x140017bed  call    __security_check_cookie
0x140017bf2  add     rsp, 108h
0x140017bf9  pop     r14
0x140017bfb  pop     r12
0x140017bfd  pop     rdi
0x140017bfe  pop     rsi
0x140017bff  pop     rbx
0x140017c00  pop     rbp
0x140017c01  retn
```
