# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>>)

- ea: `0x180024f40`
- end: `0x180024fd8`
- name: `??$ActivateInstance@V?$ComPtr@UIGeolocator@Geolocation@Devices@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIGeolocator@Geolocation@Devices@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800256ac`

## callees

- `0x1800045b4`
- `0x180009fc0`
- `0x180024f40`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180024f70`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180024f70`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>>(
        __int64 a1,
        _QWORD *a2)
{
  int v4; // edi
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  *a2 = 0;
  v6 = 0;
  v4 = RoActivateInstance(a1, &v6);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_a9c3bf62_4524_4989_8aa9_de019d2e551f, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v6;
    }
    else
    {
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v6)(
             v6,
             &GUID_a9c3bf62_4524_4989_8aa9_de019d2e551f,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180024f40  mov     [rsp+arg_0], rbx
0x180024f45  push    rdi
0x180024f46  sub     rsp, 20h
0x180024f4a  mov     rbx, rdx
0x180024f4d  mov     rdi, rcx
0x180024f50  mov     rcx, rdx
0x180024f53  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024f58  mov     qword ptr [rbx], 0
0x180024f5f  mov     [rsp+28h+arg_8], 0
0x180024f68  lea     rdx, [rsp+28h+arg_8]
0x180024f6d  mov     rcx, rdi
0x180024f70  call    cs:__imp_RoActivateInstance
0x180024f76  mov     edi, eax
0x180024f78  test    eax, eax
0x180024f7a  js      short loc_180024FCB
0x180024f7c  mov     r8d, 10h; Size
0x180024f82  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180024f89  lea     rcx, _GUID_a9c3bf62_4524_4989_8aa9_de019d2e551f; Buf1
0x180024f90  call    memcmp_0
0x180024f95  mov     rcx, [rsp+28h+arg_8]
0x180024f9a  test    eax, eax
0x180024f9c  jnz     short loc_180024FA3
0x180024f9e  mov     [rbx], rcx
0x180024fa1  jmp     short loc_180024FCB
0x180024fa3  mov     rax, [rcx]
0x180024fa6  mov     r8, rbx
0x180024fa9  lea     rdx, _GUID_a9c3bf62_4524_4989_8aa9_de019d2e551f
0x180024fb0  mov     rax, [rax]
0x180024fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fb8  mov     edi, eax
0x180024fba  mov     rcx, [rsp+28h+arg_8]
0x180024fbf  mov     rax, [rcx]
0x180024fc2  mov     rax, [rax+10h]
0x180024fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fcb  mov     eax, edi
0x180024fcd  mov     rbx, [rsp+28h+arg_0]
0x180024fd2  add     rsp, 20h
0x180024fd6  pop     rdi
0x180024fd7  retn
```
