# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180010168`
- end: `0x1800101f5`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `141`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c81c`
- `0x18000c914`
- `0x18000ee00`
- `0x18000ee24`
- `0x18000f074`
- `0x18000f160`
- `0x180010008`

## callees

- `0x1800067fc`
- `0x180010168`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800101a4`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800101a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  v2 = (char *)this + 24;
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v3, &GUID_00000003_0000_0000_c000_000000000046, v2);
  }
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&ppunkMarshal);
  return this;
}

```

## disassembly

```asm
0x180010168  push    rbx
0x18001016a  push    rsi
0x18001016b  push    rdi
0x18001016c  push    r14
0x18001016e  sub     rsp, 28h
0x180010172  mov     rsi, rcx
0x180010175  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18001017c  mov     [rcx], rax
0x18001017f  lea     r14, [rcx+18h]
0x180010183  mov     qword ptr [r14], 0
0x18001018a  mov     [rsp+48h+ppunkMarshal], 0
0x180010193  lea     rcx, [rsp+48h+ppunkMarshal]
0x180010198  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18001019d  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800101a2  xor     ecx, ecx; punkOuter
0x1800101a4  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800101ab  nop     dword ptr [rax+rax+00h]
0x1800101b0  test    eax, eax
0x1800101b2  js      short loc_1800101DD
0x1800101b4  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800101b9  mov     rax, [rbx]
0x1800101bc  mov     rdi, [rax]
0x1800101bf  mov     rcx, r14
0x1800101c2  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800101c7  mov     r8, r14
0x1800101ca  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800101d1  mov     rcx, rbx
0x1800101d4  mov     rax, rdi
0x1800101d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101dc  nop
0x1800101dd  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800101e2  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800101e7  mov     rax, rsi
0x1800101ea  add     rsp, 28h
0x1800101ee  pop     r14
0x1800101f0  pop     rdi
0x1800101f1  pop     rsi
0x1800101f2  pop     rbx
0x1800101f3  retn
```
