# BthUsb_PnpCreateDevice(_BTDEVICE *)

- ea: `0x140017858`
- end: `0x1400179a5`
- name: `?BthUsb_PnpCreateDevice@@YAJPEAU_BTDEVICE@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(struct _BTDEVICE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x140019008`

## callees

- `0x14000187c`
- `0x140001924`
- `0x14000e1c0`
- `0x140017210`
- `0x140017858`
- `0x14001c1c8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400178c3`
- `ntoskrnl!ExAllocatePool2` at `0x1400178c3`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1400178fe`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1400178fe`

## pseudocode

```c
__int64 __fastcall BthUsb_PnpCreateDevice(struct _BTDEVICE *a1, __int64 a2, int a3)
{
  char v4; // bl
  bool v5; // dl
  char *Pool2; // rax
  int v7; // edx
  int v8; // r8d
  char *v9; // rdi
  struct _DEVICE_OBJECT *PhysicalDeviceObject; // rcx
  __int64 v11; // rcx
  unsigned int v12; // edi

  v4 = 1;
  v5 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_q(
    WPP_GLOBAL_Control->AttachedDevice,
    v5,
    a3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    2,
    21,
    (__int64)WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids,
    (char)a1);
  Pool2 = (char *)ExAllocatePool2(64, 1176, 1111642965);
  v9 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0x498u);
    IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)(v9 + 48), 0x42425355u, 0, 0, 0x20u);
    a1->MiniportContext = v9;
    *((_QWORD *)v9 + 145) = v9 + 1152;
    *((_QWORD *)v9 + 144) = v9 + 1152;
    PhysicalDeviceObject = a1->PhysicalDeviceObject;
    *((_QWORD *)v9 + 2) = a1;
    *((_QWORD *)v9 + 5) = a1->NextDeviceObject;
    BthUsb_GetPhysicalDeviceObjectName(PhysicalDeviceObject, (struct _UNICODE_STRING *)(v9 + 24));
    v9[1173] = (BthQueryRadioCompatFlags(v11, *(_QWORD *)(*((_QWORD *)v9 + 2) + 8LL)) & 0x2000) != 0;
    v12 = 0;
  }
  else
  {
    v12 = -1073741670;
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v4 = 0;
  LOBYTE(v7) = v4;
  WPP_RECORDER_AND_TRACE_SF_qD(WPP_GLOBAL_Control->AttachedDevice, v7, v8, WPP_GLOBAL_Control->DeviceExtension);
  return v12;
}

```

## disassembly

```asm
0x140017858  push    rbx
0x14001785a  push    rsi
0x14001785b  push    rdi
0x14001785c  push    r14
0x14001785e  sub     rsp, 58h
0x140017862  mov     rsi, rcx
0x140017865  mov     rcx, cs:WPP_GLOBAL_Control
0x14001786c  mov     bl, 1
0x14001786e  mov     eax, [rcx+2Ch]
0x140017871  test    al, 2
0x140017873  jz      short loc_14001787F
0x140017875  cmp     byte ptr [rcx+29h], 4
0x140017879  jb      short loc_14001787F
0x14001787b  mov     dl, bl
0x14001787d  jmp     short loc_140017881
0x14001787f  xor     dl, dl
0x140017881  mov     r9, [rcx+40h]
0x140017885  lea     r14, WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids
0x14001788c  mov     rcx, [rcx+18h]
0x140017890  mov     [rsp+78h+var_38], rsi
0x140017895  mov     [rsp+78h+var_40], r14
0x14001789a  mov     [rsp+78h+var_48], 15h
0x1400178a1  mov     [rsp+78h+var_50], 2
0x1400178a9  mov     byte ptr [rsp+78h+RemlockSize], 4
0x1400178ae  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400178b3  mov     edx, 498h
0x1400178b8  mov     ecx, 40h ; '@'
0x1400178bd  mov     r8d, 42425355h
0x1400178c3  call    cs:__imp_ExAllocatePool2
0x1400178ca  nop     dword ptr [rax+rax+00h]
0x1400178cf  mov     rdi, rax
0x1400178d2  test    rax, rax
0x1400178d5  jz      short loc_140017951
0x1400178d7  xor     edx, edx; Val
0x1400178d9  mov     r8d, 498h; Size
0x1400178df  mov     rcx, rax; void *
0x1400178e2  call    memset
0x1400178e7  lea     rcx, [rdi+30h]; Lock
0x1400178eb  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x1400178f3  xor     r9d, r9d; HighWatermark
0x1400178f6  xor     r8d, r8d; MaxLockedMinutes
0x1400178f9  mov     edx, 42425355h; AllocateTag
0x1400178fe  call    cs:__imp_IoInitializeRemoveLockEx
0x140017905  nop     dword ptr [rax+rax+00h]
0x14001790a  lea     rcx, [rdi+480h]
0x140017911  mov     [rsi], rdi
0x140017914  mov     [rcx+8], rcx
0x140017918  lea     rdx, [rdi+18h]; struct _UNICODE_STRING *
0x14001791c  mov     [rcx], rcx
0x14001791f  mov     rcx, [rsi+10h]; DeviceObject
0x140017923  mov     [rdi+10h], rsi
0x140017927  mov     rax, [rsi+18h]
0x14001792b  mov     [rdi+28h], rax
0x14001792f  call    ?BthUsb_GetPhysicalDeviceObjectName@@YAJPEAU_DEVICE_OBJECT@@PEAU_UNICODE_STRING@@@Z; BthUsb_GetPhysicalDeviceObjectName(_DEVICE_OBJECT *,_UNICODE_STRING *)
0x140017934  mov     rdx, [rdi+10h]
0x140017938  mov     rdx, [rdx+8]
0x14001793c  call    BthQueryRadioCompatFlags
0x140017941  shr     rax, 0Dh
0x140017945  and     al, bl
0x140017947  mov     [rdi+495h], al
0x14001794d  xor     edi, edi
0x14001794f  jmp     short loc_140017956
0x140017951  mov     edi, 0C000009Ah
0x140017956  mov     rcx, cs:WPP_GLOBAL_Control
0x14001795d  mov     eax, [rcx+2Ch]
0x140017960  test    al, 2
0x140017962  jz      short loc_14001796A
0x140017964  cmp     byte ptr [rcx+29h], 4
0x140017968  jnb     short loc_14001796C
0x14001796a  xor     bl, bl
0x14001796c  mov     r9, [rcx+40h]
0x140017970  mov     dl, bl
0x140017972  mov     rcx, [rcx+18h]
0x140017976  mov     [rsp+78h+var_30], edi
0x14001797a  mov     [rsp+78h+var_38], rsi
0x14001797f  mov     [rsp+78h+var_40], r14
0x140017984  mov     [rsp+78h+var_48], 16h
0x14001798b  mov     [rsp+78h+var_50], 2
0x140017993  call    WPP_RECORDER_AND_TRACE_SF_qD
0x140017998  mov     eax, edi
0x14001799a  add     rsp, 58h
0x14001799e  pop     r14
0x1400179a0  pop     rdi
0x1400179a1  pop     rsi
0x1400179a2  pop     rbx
0x1400179a3  retn
```
