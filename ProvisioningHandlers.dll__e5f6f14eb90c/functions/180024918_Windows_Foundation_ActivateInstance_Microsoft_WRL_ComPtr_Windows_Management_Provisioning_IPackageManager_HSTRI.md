# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>)

- ea: `0x180024918`
- end: `0x1800249b7`
- name: `??$ActivateInstance@V?$ComPtr@UIPackageManager@Provisioning@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Provisioning@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `159`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024f40`
- `0x180026280`
- `0x180026b60`

## callees

- `0x1800067fc`
- `0x180024918`
- `0x180028826`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180024948`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180024948`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>(
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
    if ( !memcmp_0(&GUID_f6efa550_3514_4bed_800b_a2f68e0972b3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v6;
    }
    else
    {
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v6)(
             v6,
             &GUID_f6efa550_3514_4bed_800b_a2f68e0972b3,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180024918  mov     [rsp+arg_0], rbx
0x18002491d  push    rdi
0x18002491e  sub     rsp, 20h
0x180024922  mov     rbx, rdx
0x180024925  mov     rdi, rcx
0x180024928  mov     rcx, rdx
0x18002492b  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180024930  mov     qword ptr [rbx], 0
0x180024937  mov     [rsp+28h+arg_8], 0
0x180024940  lea     rdx, [rsp+28h+arg_8]
0x180024945  mov     rcx, rdi
0x180024948  call    cs:__imp_RoActivateInstance
0x18002494f  nop     dword ptr [rax+rax+00h]
0x180024954  mov     edi, eax
0x180024956  test    eax, eax
0x180024958  js      short loc_1800249A9
0x18002495a  mov     r8d, 10h; Size
0x180024960  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180024967  lea     rcx, _GUID_f6efa550_3514_4bed_800b_a2f68e0972b3; Buf1
0x18002496e  call    memcmp_0
0x180024973  mov     rcx, [rsp+28h+arg_8]
0x180024978  test    eax, eax
0x18002497a  jnz     short loc_180024981
0x18002497c  mov     [rbx], rcx
0x18002497f  jmp     short loc_1800249A9
0x180024981  mov     rax, [rcx]
0x180024984  mov     r8, rbx
0x180024987  lea     rdx, _GUID_f6efa550_3514_4bed_800b_a2f68e0972b3
0x18002498e  mov     rax, [rax]
0x180024991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024996  mov     edi, eax
0x180024998  mov     rcx, [rsp+28h+arg_8]
0x18002499d  mov     rax, [rcx]
0x1800249a0  mov     rax, [rax+10h]
0x1800249a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249a9  mov     eax, edi
0x1800249ab  mov     rbx, [rsp+28h+arg_0]
0x1800249b0  add     rsp, 20h
0x1800249b4  pop     rdi
0x1800249b5  retn
```
