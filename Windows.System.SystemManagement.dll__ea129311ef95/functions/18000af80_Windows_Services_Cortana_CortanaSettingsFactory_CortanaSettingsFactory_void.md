# Windows::Services::Cortana::CortanaSettingsFactory::~CortanaSettingsFactory(void)

- ea: `0x18000af80`
- end: `0x18000afc7`
- name: `??1CortanaSettingsFactory@Cortana@Services@Windows@@UEAA@XZ`
- size: `71`
- prototype: `void __fastcall(Windows::Services::Cortana::CortanaSettingsFactory *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b2d0`

## callees

- `0x180007248`
- `0x18000af80`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000af8d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000af8d`

## pseudocode

```c
void __fastcall Windows::Services::Cortana::CortanaSettingsFactory::~CortanaSettingsFactory(
        Windows::Services::Cortana::CortanaSettingsFactory *this)
{
  __int64 v2; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v2 = *((_QWORD *)this + 12);
  if ( v2 )
  {
    *((_QWORD *)this + 12) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  *((_DWORD *)this + 17) = -1073741823;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 32);
}

```

## disassembly

```asm
0x18000af80  push    rbx
0x18000af82  sub     rsp, 20h
0x18000af86  mov     rbx, rcx
0x18000af89  add     rcx, 68h ; 'h'; lpCriticalSection
0x18000af8d  call    cs:__imp_DeleteCriticalSection
0x18000af93  nop
0x18000af94  mov     rcx, [rbx+60h]
0x18000af98  test    rcx, rcx
0x18000af9b  jz      short loc_18000AFB2
0x18000af9d  mov     qword ptr [rbx+60h], 0
0x18000afa5  mov     rax, [rcx]
0x18000afa8  mov     rax, [rax+10h]
0x18000afac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afb1  nop
0x18000afb2  mov     dword ptr [rbx+44h], 0C0000001h
0x18000afb9  lea     rcx, [rbx+20h]
0x18000afbd  add     rsp, 20h
0x18000afc1  pop     rbx
0x18000afc2  jmp     ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
```
