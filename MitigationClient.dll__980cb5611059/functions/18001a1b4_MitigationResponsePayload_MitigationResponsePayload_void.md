# MitigationResponsePayload::~MitigationResponsePayload(void)

- ea: `0x18001a1b4`
- end: `0x18001a22e`
- name: `??1MitigationResponsePayload@@UEAA@XZ`
- size: `122`
- prototype: `void __fastcall(MitigationResponsePayload *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a7a0`

## callees

- `0x18001055c`
- `0x18001a1b4`
- `0x18002407c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1fa`

## pseudocode

```c
void __fastcall MitigationResponsePayload::~MitigationResponsePayload(MitigationResponsePayload *this)
{
  unsigned __int64 *v2; // rdi
  unsigned __int64 i; // rsi

  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)this + 48);
  v2 = (unsigned __int64 *)((char *)this + 24);
  if ( *((_QWORD *)this + 2) )
  {
    for ( i = 0; i < *v2; ++i )
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(*((_QWORD *)this + 2) + 8 * i);
    CoTaskMemFree(*((LPVOID *)this + 2));
    *((_QWORD *)this + 2) = 0;
  }
  *((_QWORD *)this + 5) = 0;
  *v2 = 0;
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18001a1b4  mov     [rsp+arg_0], rbx
0x18001a1b9  mov     [rsp+arg_8], rsi
0x18001a1be  push    rdi
0x18001a1bf  sub     rsp, 20h
0x18001a1c3  mov     rbx, rcx
0x18001a1c6  add     rcx, 30h ; '0'
0x18001a1ca  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001a1cf  cmp     qword ptr [rbx+10h], 0
0x18001a1d4  lea     rdi, [rbx+18h]
0x18001a1d8  jz      short loc_18001A208
0x18001a1da  xor     esi, esi
0x18001a1dc  cmp     [rdi], rsi
0x18001a1df  jbe     short loc_18001A1F6
0x18001a1e1  mov     rax, [rbx+10h]
0x18001a1e5  lea     rcx, [rax+rsi*8]
0x18001a1e9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001a1ee  inc     rsi
0x18001a1f1  cmp     rsi, [rdi]
0x18001a1f4  jb      short loc_18001A1E1
0x18001a1f6  mov     rcx, [rbx+10h]; pv
0x18001a1fa  call    cs:__imp_CoTaskMemFree
0x18001a200  mov     qword ptr [rbx+10h], 0
0x18001a208  mov     rsi, [rsp+28h+arg_8]
0x18001a20d  mov     qword ptr [rbx+28h], 0
0x18001a215  mov     qword ptr [rdi], 0
0x18001a21c  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18001a223  mov     rbx, [rsp+28h+arg_0]
0x18001a228  add     rsp, 20h
0x18001a22c  pop     rdi
0x18001a22d  retn
```
