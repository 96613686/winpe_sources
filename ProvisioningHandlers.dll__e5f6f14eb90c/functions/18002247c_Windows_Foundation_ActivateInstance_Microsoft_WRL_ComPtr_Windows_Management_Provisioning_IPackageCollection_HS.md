# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageCollection>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageCollection>>)

- ea: `0x18002247c`
- end: `0x18002251b`
- name: `??$ActivateInstance@V?$ComPtr@UIPackageCollection@Provisioning@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageCollection@Provisioning@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800230d8`
- `0x1800235dc`

## callees

- `0x1800067fc`
- `0x18002247c`
- `0x180028826`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800224ac`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800224ac`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageCollection>>(
        __int64 a1,
        __int64 *a2)
{
  int v4; // edi
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(a2);
  *a2 = 0;
  v6 = 0;
  v4 = RoActivateInstance(a1, &v6);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_7578134e_d30f_414e_a5c1_bf462b7841f0, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v6;
    }
    else
    {
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v6)(
             v6,
             &GUID_7578134e_d30f_414e_a5c1_bf462b7841f0,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002247c  mov     [rsp+arg_0], rbx
0x180022481  push    rdi
0x180022482  sub     rsp, 20h
0x180022486  mov     rbx, rdx
0x180022489  mov     rdi, rcx
0x18002248c  mov     rcx, rdx
0x18002248f  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180022494  mov     qword ptr [rbx], 0
0x18002249b  mov     [rsp+28h+arg_8], 0
0x1800224a4  lea     rdx, [rsp+28h+arg_8]
0x1800224a9  mov     rcx, rdi
0x1800224ac  call    cs:__imp_RoActivateInstance
0x1800224b3  nop     dword ptr [rax+rax+00h]
0x1800224b8  mov     edi, eax
0x1800224ba  test    eax, eax
0x1800224bc  js      short loc_18002250D
0x1800224be  mov     r8d, 10h; Size
0x1800224c4  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800224cb  lea     rcx, _GUID_7578134e_d30f_414e_a5c1_bf462b7841f0; Buf1
0x1800224d2  call    memcmp_0
0x1800224d7  mov     rcx, [rsp+28h+arg_8]
0x1800224dc  test    eax, eax
0x1800224de  jnz     short loc_1800224E5
0x1800224e0  mov     [rbx], rcx
0x1800224e3  jmp     short loc_18002250D
0x1800224e5  mov     rax, [rcx]
0x1800224e8  mov     r8, rbx
0x1800224eb  lea     rdx, _GUID_7578134e_d30f_414e_a5c1_bf462b7841f0
0x1800224f2  mov     rax, [rax]
0x1800224f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224fa  mov     edi, eax
0x1800224fc  mov     rcx, [rsp+28h+arg_8]
0x180022501  mov     rax, [rcx]
0x180022504  mov     rax, [rax+10h]
0x180022508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002250d  mov     eax, edi
0x18002250f  mov     rbx, [rsp+28h+arg_0]
0x180022514  add     rsp, 20h
0x180022518  pop     rdi
0x180022519  retn
```
