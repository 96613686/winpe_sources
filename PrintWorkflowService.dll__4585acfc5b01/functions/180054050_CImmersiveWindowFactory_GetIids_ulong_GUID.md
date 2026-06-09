# CImmersiveWindowFactory::GetIids(ulong *,_GUID * *)

- ea: `0x180054050`
- end: `0x1800540af`
- name: `?GetIids@CImmersiveWindowFactory@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(CImmersiveWindowFactory *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180053eac`
- `0x180054050`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054072`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054072`

## pseudocode

```c
__int64 __fastcall CImmersiveWindowFactory::GetIids(CImmersiveWindowFactory *this, unsigned int *a2, struct _GUID **a3)
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveWindowFactoryBase>,IWeakReferenceSource>::FillArrayWithIid(
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
0x180054050  mov     [rsp+arg_0], rbx
0x180054055  push    rdi
0x180054056  sub     rsp, 20h
0x18005405a  mov     qword ptr [r8], 0
0x180054061  mov     ecx, 20h ; ' '; cb
0x180054066  mov     dword ptr [rdx], 0
0x18005406c  mov     rbx, r8
0x18005406f  mov     rdi, rdx
0x180054072  call    cs:__imp_CoTaskMemAlloc
0x180054078  mov     r8, rax
0x18005407b  test    rax, rax
0x18005407e  jnz     short loc_180054087
0x180054080  mov     eax, 8007000Eh
0x180054085  jmp     short loc_1800540A4
0x180054087  lea     rdx, [rsp+28h+arg_8]
0x18005408c  mov     [rsp+28h+arg_8], 0
0x180054094  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCImmersiveWindowFactoryBase@@@Details@23@UIWeakReferenceSource@@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveWindowFactoryBase>,IWeakReferenceSource>::FillArrayWithIid(ulong *,_GUID *)
0x180054099  mov     dword ptr [rdi], 2
0x18005409f  xor     eax, eax
0x1800540a1  mov     [rbx], r8
0x1800540a4  mov     rbx, [rsp+28h+arg_0]
0x1800540a9  add     rsp, 20h
0x1800540ad  pop     rdi
0x1800540ae  retn
```
