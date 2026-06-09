# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>)

- ea: `0x140007dfc`
- end: `0x140007e94`
- name: `??$ActivateInstance@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140008758`

## callees

- `0x140003f68`
- `0x140007dfc`
- `0x1400098dc`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x140007e2c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x140007e2c`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
        __int64 a1,
        _QWORD *a2)
{
  int v4; // edi
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(a2);
  *a2 = 0;
  v6 = 0;
  v4 = RoActivateInstance(a1, &v6);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_ee89017c_6b2d_4c86_9d83_821c4f38e2ef, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v6;
    }
    else
    {
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v6)(
             v6,
             &GUID_ee89017c_6b2d_4c86_9d83_821c4f38e2ef,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140007dfc  mov     [rsp+arg_0], rbx
0x140007e01  push    rdi
0x140007e02  sub     rsp, 20h
0x140007e06  mov     rbx, rdx
0x140007e09  mov     rdi, rcx
0x140007e0c  mov     rcx, rdx
0x140007e0f  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140007e14  mov     qword ptr [rbx], 0
0x140007e1b  mov     [rsp+28h+arg_8], 0
0x140007e24  lea     rdx, [rsp+28h+arg_8]
0x140007e29  mov     rcx, rdi
0x140007e2c  call    cs:__imp_RoActivateInstance
0x140007e32  mov     edi, eax
0x140007e34  test    eax, eax
0x140007e36  js      short loc_140007E87
0x140007e38  mov     r8d, 10h; Size
0x140007e3e  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x140007e45  lea     rcx, _GUID_ee89017c_6b2d_4c86_9d83_821c4f38e2ef; Buf1
0x140007e4c  call    memcmp_0
0x140007e51  mov     rcx, [rsp+28h+arg_8]
0x140007e56  test    eax, eax
0x140007e58  jnz     short loc_140007E5F
0x140007e5a  mov     [rbx], rcx
0x140007e5d  jmp     short loc_140007E87
0x140007e5f  mov     rax, [rcx]
0x140007e62  mov     r8, rbx
0x140007e65  lea     rdx, _GUID_ee89017c_6b2d_4c86_9d83_821c4f38e2ef
0x140007e6c  mov     rax, [rax]
0x140007e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e74  mov     edi, eax
0x140007e76  mov     rcx, [rsp+28h+arg_8]
0x140007e7b  mov     rax, [rcx]
0x140007e7e  mov     rax, [rax+10h]
0x140007e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e87  mov     eax, edi
0x140007e89  mov     rbx, [rsp+28h+arg_0]
0x140007e8e  add     rsp, 20h
0x140007e92  pop     rdi
0x140007e93  retn
```
