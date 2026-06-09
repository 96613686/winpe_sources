# ServiceDrivenActionJsonDescriptor::~ServiceDrivenActionJsonDescriptor(void)

- ea: `0x18002533c`
- end: `0x1800253b6`
- name: `??1ServiceDrivenActionJsonDescriptor@@UEAA@XZ`
- size: `122`
- prototype: `void __fastcall(ServiceDrivenActionJsonDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025420`

## callees

- `0x18001055c`
- `0x18002407c`
- `0x18002533c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025379`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025379`

## pseudocode

```c
void __fastcall ServiceDrivenActionJsonDescriptor::~ServiceDrivenActionJsonDescriptor(
        ServiceDrivenActionJsonDescriptor *this)
{
  unsigned __int64 *v1; // rdi
  unsigned __int64 i; // rsi

  v1 = (unsigned __int64 *)((char *)this + 48);
  if ( *((_QWORD *)this + 5) )
  {
    for ( i = 0; i < *v1; ++i )
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(*((_QWORD *)this + 5) + 8 * i);
    CoTaskMemFree(*((LPVOID *)this + 5));
    *((_QWORD *)this + 5) = 0;
  }
  *v1 = 0;
  *((_QWORD *)this + 8) = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)this + 16);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18002533c  mov     [rsp+arg_0], rbx
0x180025341  mov     [rsp+arg_8], rsi
0x180025346  push    rdi
0x180025347  sub     rsp, 20h
0x18002534b  cmp     qword ptr [rcx+28h], 0
0x180025350  lea     rdi, [rcx+30h]
0x180025354  mov     rbx, rcx
0x180025357  jz      short loc_180025387
0x180025359  xor     esi, esi
0x18002535b  cmp     [rdi], rsi
0x18002535e  jbe     short loc_180025375
0x180025360  mov     rax, [rbx+28h]
0x180025364  lea     rcx, [rax+rsi*8]
0x180025368  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002536d  inc     rsi
0x180025370  cmp     rsi, [rdi]
0x180025373  jb      short loc_180025360
0x180025375  mov     rcx, [rbx+28h]; pv
0x180025379  call    cs:__imp_CoTaskMemFree
0x18002537f  mov     qword ptr [rbx+28h], 0
0x180025387  lea     rcx, [rbx+10h]
0x18002538b  mov     qword ptr [rdi], 0
0x180025392  mov     qword ptr [rbx+40h], 0
0x18002539a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002539f  mov     rsi, [rsp+28h+arg_8]
0x1800253a4  mov     dword ptr [rbx+0Ch], 0C0000001h
0x1800253ab  mov     rbx, [rsp+28h+arg_0]
0x1800253b0  add     rsp, 20h
0x1800253b4  pop     rdi
0x1800253b5  retn
```
