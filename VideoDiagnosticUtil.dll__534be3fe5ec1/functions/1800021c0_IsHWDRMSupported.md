# IsHWDRMSupported

- ea: `0x1800021c0`
- end: `0x180002278`
- name: `IsHWDRMSupported`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800021c0`
- `0x18000a010`

## import_xrefs

- `MFPlat!MFCreateContentProtectionDevice` at `0x180002228`
- `MFPlat!MFCreateContentProtectionDevice` at `0x180002228`
- `MFPlat!MFIsContentProtectionDeviceSupported` at `0x180002203`
- `MFPlat!MFIsContentProtectionDeviceSupported` at `0x180002203`
- `MFPlat!MFStartup` at `0x1800021e5`
- `MFPlat!MFStartup` at `0x1800021e5`

## pseudocode

```c
__int64 __fastcall IsHWDRMSupported(BOOL *a1)
{
  HRESULT v2; // ebx
  HRESULT v3; // eax
  IMFContentProtectionDevice *v4; // rcx
  BOOL isSupported; // [rsp+30h] [rbp+8h] BYREF
  IMFContentProtectionDevice *ContentProtectionDevice; // [rsp+38h] [rbp+10h] BYREF

  isSupported = 0;
  ContentProtectionDevice = 0;
  v2 = MFStartup(0x20070u, 0);
  if ( v2 >= 0
    && (v2 = MFIsContentProtectionDeviceSupported(&CLSID_PlayReadySystemID, &isSupported), v2 >= 0)
    && isSupported )
  {
    v3 = MFCreateContentProtectionDevice(&CLSID_PlayReadySystemID, &ContentProtectionDevice);
    v4 = ContentProtectionDevice;
    v2 = v3;
    if ( v3 < 0 || !ContentProtectionDevice )
      isSupported = 0;
  }
  else
  {
    v4 = ContentProtectionDevice;
  }
  *a1 = isSupported;
  if ( v4 )
    ((void (__fastcall *)(IMFContentProtectionDevice *))v4->lpVtbl->Release)(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800021c0  mov     [rsp+arg_10], rbx
0x1800021c5  push    rdi
0x1800021c6  sub     rsp, 20h
0x1800021ca  mov     rdi, rcx
0x1800021cd  mov     [rsp+28h+isSupported], 0
0x1800021d5  mov     ecx, 20070h; Version
0x1800021da  mov     [rsp+28h+ContentProtectionDevice], 0
0x1800021e3  xor     edx, edx; dwFlags
0x1800021e5  call    cs:__imp_MFStartup
0x1800021ec  nop     dword ptr [rax+rax+00h]
0x1800021f1  mov     ebx, eax
0x1800021f3  test    eax, eax
0x1800021f5  js      short loc_18000224E
0x1800021f7  lea     rdx, [rsp+28h+isSupported]; isSupported
0x1800021fc  lea     rcx, CLSID_PlayReadySystemID; ProtectionSystemId
0x180002203  call    cs:__imp_MFIsContentProtectionDeviceSupported
0x18000220a  nop     dword ptr [rax+rax+00h]
0x18000220f  mov     ebx, eax
0x180002211  test    eax, eax
0x180002213  js      short loc_18000224E
0x180002215  cmp     [rsp+28h+isSupported], 0
0x18000221a  jz      short loc_18000224E
0x18000221c  lea     rdx, [rsp+28h+ContentProtectionDevice]; ContentProtectionDevice
0x180002221  lea     rcx, CLSID_PlayReadySystemID; ProtectionSystemId
0x180002228  call    cs:__imp_MFCreateContentProtectionDevice
0x18000222f  nop     dword ptr [rax+rax+00h]
0x180002234  mov     rcx, [rsp+28h+ContentProtectionDevice]
0x180002239  mov     ebx, eax
0x18000223b  test    eax, eax
0x18000223d  js      short loc_180002244
0x18000223f  test    rcx, rcx
0x180002242  jnz     short loc_180002253
0x180002244  mov     [rsp+28h+isSupported], 0
0x18000224c  jmp     short loc_180002253
0x18000224e  mov     rcx, [rsp+28h+ContentProtectionDevice]
0x180002253  mov     eax, [rsp+28h+isSupported]
0x180002257  mov     [rdi], eax
0x180002259  test    rcx, rcx
0x18000225c  jz      short loc_18000226A
0x18000225e  mov     rax, [rcx]
0x180002261  mov     rax, [rax+10h]
0x180002265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000226a  mov     eax, ebx
0x18000226c  mov     rbx, [rsp+28h+arg_10]
0x180002271  add     rsp, 20h
0x180002275  pop     rdi
0x180002276  retn
```
