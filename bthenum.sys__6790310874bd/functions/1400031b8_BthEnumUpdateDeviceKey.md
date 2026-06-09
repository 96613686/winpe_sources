# BthEnumUpdateDeviceKey

- ea: `0x1400031b8`
- end: `0x140003320`
- name: `BthEnumUpdateDeviceKey`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x140019058`

## callees

- `0x140001294`
- `0x1400031b8`

## import_xrefs

- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140003213`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140003213`
- `ntoskrnl!ZwSetValueKey` at `0x1400032e1`
- `ntoskrnl!ZwSetValueKey` at `0x1400032e1`
- `ntoskrnl!ZwClose` at `0x140003308`
- `ntoskrnl!ZwClose` at `0x140003308`
- `ntoskrnl!ExFreePool` at `0x1400032f2`
- `ntoskrnl!ExFreePool` at `0x1400032f2`
- `ntoskrnl!ExAllocatePool2` at `0x1400031e3`
- `ntoskrnl!ExAllocatePool2` at `0x1400031e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400032a5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400032a5`

## pseudocode

```c
__int64 __fastcall BthEnumUpdateDeviceKey(__int64 a1)
{
  wchar_t *Data; // rdi
  NTSTATUS v3; // ebx
  __int64 v4; // r9
  __int16 v5; // ax
  NTSTATUS v6; // eax
  __int64 v7; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  void *DeviceRegKey; // [rsp+78h] [rbp+10h] BYREF

  DeviceRegKey = 0;
  DestinationString = 0;
  Data = (wchar_t *)ExAllocatePool2(256, 618, 1330467906);
  if ( Data )
  {
    v3 = IoOpenDeviceRegistryKey(*(PDEVICE_OBJECT *)(a1 + 16), 1u, 2u, &DeviceRegKey);
    if ( v3 >= 0 )
    {
      v4 = *(_QWORD *)(a1 + 56);
      v5 = *(_WORD *)(a1 + 1076);
      if ( v5 == 76 )
        v6 = RtlStringCchPrintfW(Data, 0x135u, L"%s#%s", v4, a1 + 24);
      else
        v6 = v5
           ? RtlStringCchPrintfW(
               Data,
               0x135u,
               L"%s#%s_%s",
               v4,
               a1 + 24,
               a1 + 1076,
               *(_QWORD *)&DestinationString.Length,
               DestinationString.Buffer)
           : RtlStringCchPrintfW(
               Data,
               0x135u,
               L"%s#%s_%08x",
               v4,
               a1 + 24,
               *(unsigned __int8 *)(a1 + 1072),
               *(_QWORD *)&DestinationString.Length,
               DestinationString.Buffer);
      v3 = v6;
      if ( v6 >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"Bluetooth_UniqueID");
        v7 = -1;
        do
          ++v7;
        while ( Data[v7] );
        v3 = ZwSetValueKey(DeviceRegKey, &DestinationString, 0, 1u, Data, 2 * v7 + 2);
      }
    }
    ExFreePool(Data);
  }
  else
  {
    v3 = -1073741670;
  }
  if ( DeviceRegKey )
    ZwClose(DeviceRegKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400031b8  push    rbx
0x1400031ba  push    rbp
0x1400031bb  push    rsi
0x1400031bc  push    rdi
0x1400031bd  sub     rsp, 48h
0x1400031c1  mov     rsi, rcx
0x1400031c4  xorps   xmm0, xmm0
0x1400031c7  xor     ebp, ebp
0x1400031c9  mov     ecx, 100h
0x1400031ce  mov     edx, 26Ah
0x1400031d3  mov     [rsp+68h+DeviceRegKey], rbp
0x1400031d8  mov     r8d, 4F4D5442h
0x1400031de  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1400031e3  call    cs:__imp_ExAllocatePool2
0x1400031ea  nop     dword ptr [rax+rax+00h]
0x1400031ef  mov     rdi, rax
0x1400031f2  test    rax, rax
0x1400031f5  jnz     short loc_140003201
0x1400031f7  mov     ebx, 0C000009Ah
0x1400031fc  jmp     loc_1400032FE
0x140003201  mov     rcx, [rsi+10h]; DeviceObject
0x140003205  lea     r9, [rsp+68h+DeviceRegKey]; DeviceRegKey
0x14000320a  mov     edx, 1; DevInstKeyType
0x14000320f  lea     r8d, [rdx+1]; DesiredAccess
0x140003213  call    cs:__imp_IoOpenDeviceRegistryKey
0x14000321a  nop     dword ptr [rax+rax+00h]
0x14000321f  mov     ebx, eax
0x140003221  test    eax, eax
0x140003223  js      loc_1400032EF
0x140003229  mov     r9, [rsi+38h]
0x14000322d  lea     rdx, [rsi+434h]
0x140003234  movzx   eax, word ptr [rdx]
0x140003237  lea     rcx, [rsi+18h]
0x14000323b  cmp     ax, 4Ch ; 'L'
0x14000323f  jnz     short loc_14000325C
0x140003241  mov     [rsp+68h+Data], rcx
0x140003246  lea     r8, aSS_1; "%s#%s"
0x14000324d  mov     rcx, rdi; pszDest
0x140003250  mov     edx, 135h; cchDest
0x140003255  call    RtlStringCchPrintfW
0x14000325a  jmp     short loc_140003293
0x14000325c  test    ax, ax
0x14000325f  jnz     short loc_140003275
0x140003261  movzx   eax, byte ptr [rsi+430h]
0x140003268  lea     r8, aSS08x; "%s#%s_%08x"
0x14000326f  mov     [rsp+68h+DataSize], eax
0x140003273  jmp     short loc_140003281
0x140003275  mov     qword ptr [rsp+68h+DataSize], rdx
0x14000327a  lea     r8, aSSS_0; "%s#%s_%s"
0x140003281  mov     [rsp+68h+Data], rcx
0x140003286  mov     edx, 135h; cchDest
0x14000328b  mov     rcx, rdi; pszDest
0x14000328e  call    RtlStringCchPrintfW
0x140003293  mov     ebx, eax
0x140003295  test    eax, eax
0x140003297  js      short loc_1400032EF
0x140003299  lea     rdx, SourceString; "Bluetooth_UniqueID"
0x1400032a0  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1400032a5  call    cs:__imp_RtlInitUnicodeString
0x1400032ac  nop     dword ptr [rax+rax+00h]
0x1400032b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400032b5  inc     rax
0x1400032b8  cmp     [rdi+rax*2], bp
0x1400032bc  jnz     short loc_1400032B5
0x1400032be  mov     rcx, [rsp+68h+DeviceRegKey]; KeyHandle
0x1400032c3  lea     eax, ds:2[rax*2]
0x1400032ca  mov     [rsp+68h+DataSize], eax; DataSize
0x1400032ce  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x1400032d3  mov     r9d, 1; Type
0x1400032d9  mov     [rsp+68h+Data], rdi; Data
0x1400032de  xor     r8d, r8d; TitleIndex
0x1400032e1  call    cs:__imp_ZwSetValueKey
0x1400032e8  nop     dword ptr [rax+rax+00h]
0x1400032ed  mov     ebx, eax
0x1400032ef  mov     rcx, rdi; P
0x1400032f2  call    cs:__imp_ExFreePool
0x1400032f9  nop     dword ptr [rax+rax+00h]
0x1400032fe  mov     rcx, [rsp+68h+DeviceRegKey]; Handle
0x140003303  test    rcx, rcx
0x140003306  jz      short loc_140003314
0x140003308  call    cs:__imp_ZwClose
0x14000330f  nop     dword ptr [rax+rax+00h]
0x140003314  mov     eax, ebx
0x140003316  add     rsp, 48h
0x14000331a  pop     rdi
0x14000331b  pop     rsi
0x14000331c  pop     rbp
0x14000331d  pop     rbx
0x14000331e  retn
```
