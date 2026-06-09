# Windows::Networking::UX::NetworkUXManager::GetIids(ulong *,_GUID * *)

- ea: `0x18002cf00`
- end: `0x18002cf5f`
- name: `?GetIids@NetworkUXManager@UX@Networking@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(Windows::Networking::UX::NetworkUXManager *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002a86c`
- `0x18002cf00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002cf22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002cf22`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::NetworkUXManager::GetIids(
        Windows::Networking::UX::NetworkUXManager *this,
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Networking::UX::INetworkUXManager,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18002cf00  mov     [rsp+arg_0], rbx
0x18002cf05  push    rdi
0x18002cf06  sub     rsp, 20h
0x18002cf0a  mov     qword ptr [r8], 0
0x18002cf11  mov     ecx, 20h ; ' '; cb
0x18002cf16  mov     dword ptr [rdx], 0
0x18002cf1c  mov     rbx, r8
0x18002cf1f  mov     rdi, rdx
0x18002cf22  call    cs:__imp_CoTaskMemAlloc
0x18002cf28  mov     r8, rax
0x18002cf2b  test    rax, rax
0x18002cf2e  jnz     short loc_18002CF37
0x18002cf30  mov     eax, 8007000Eh
0x18002cf35  jmp     short loc_18002CF54
0x18002cf37  lea     rdx, [rsp+28h+arg_8]
0x18002cf3c  mov     [rsp+28h+arg_8], 0
0x18002cf44  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$0A@UINetworkUXManager@UX@Networking@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Networking::UX::INetworkUXManager,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18002cf49  mov     dword ptr [rdi], 2
0x18002cf4f  xor     eax, eax
0x18002cf51  mov     [rbx], r8
0x18002cf54  mov     rbx, [rsp+28h+arg_0]
0x18002cf59  add     rsp, 20h
0x18002cf5d  pop     rdi
0x18002cf5e  retn
```
