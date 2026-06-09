# Windows::Storage::FileProperties::GeotagHelper::GetIids(ulong *,_GUID * *)

- ea: `0x18002bdc0`
- end: `0x18002be1f`
- name: `?GetIids@GeotagHelper@FileProperties@Storage@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(Windows::Storage::FileProperties::GeotagHelper *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002be30`

## callees

- `0x18002a8c4`
- `0x18002bdc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bde2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bde2`

## pseudocode

```c
__int64 __fastcall Windows::Storage::FileProperties::GeotagHelper::GetIids(
        Windows::Storage::FileProperties::GeotagHelper *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Storage::FileProperties::IGeotagHelperStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18002bdc0  mov     [rsp+arg_0], rbx
0x18002bdc5  push    rdi
0x18002bdc6  sub     rsp, 20h
0x18002bdca  mov     qword ptr [r8], 0
0x18002bdd1  mov     ecx, 20h ; ' '; cb
0x18002bdd6  mov     dword ptr [rdx], 0
0x18002bddc  mov     rbx, r8
0x18002bddf  mov     rdi, rdx
0x18002bde2  call    cs:__imp_CoTaskMemAlloc
0x18002bde8  mov     r8, rax
0x18002bdeb  test    rax, rax
0x18002bdee  jnz     short loc_18002BDF7
0x18002bdf0  mov     eax, 8007000Eh
0x18002bdf5  jmp     short loc_18002BE14
0x18002bdf7  lea     rdx, [rsp+28h+arg_8]
0x18002bdfc  mov     [rsp+28h+arg_8], 0
0x18002be04  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIGeotagHelperStatics@FileProperties@Storage@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Storage::FileProperties::IGeotagHelperStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x18002be09  mov     dword ptr [rdi], 2
0x18002be0f  xor     eax, eax
0x18002be11  mov     [rbx], r8
0x18002be14  mov     rbx, [rsp+28h+arg_0]
0x18002be19  add     rsp, 20h
0x18002be1d  pop     rdi
0x18002be1e  retn
```
