# Windows::Internal::StateRepository::PrimaryTileUserNotifierServer::GetIids(ulong *,_GUID * *)

- ea: `0x1800209e0`
- end: `0x180020a3f`
- name: `?GetIids@PrimaryTileUserNotifierServer@StateRepository@Internal@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::PrimaryTileUserNotifierServer *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800209b8`
- `0x1800209e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020a02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020a02`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::PrimaryTileUserNotifierServer::GetIids(
        Windows::Internal::StateRepository::PrimaryTileUserNotifierServer *this,
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::StateRepository::IPrimaryTileUserNotifier,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x1800209e0  mov     [rsp+arg_0], rbx
0x1800209e5  push    rdi
0x1800209e6  sub     rsp, 20h
0x1800209ea  mov     qword ptr [r8], 0
0x1800209f1  mov     ecx, 20h ; ' '; cb
0x1800209f6  mov     dword ptr [rdx], 0
0x1800209fc  mov     rbx, r8
0x1800209ff  mov     rdi, rdx
0x180020a02  call    cs:__imp_CoTaskMemAlloc
0x180020a08  mov     r8, rax
0x180020a0b  test    rax, rax
0x180020a0e  jnz     short loc_180020A17
0x180020a10  mov     eax, 8007000Eh
0x180020a15  jmp     short loc_180020A34
0x180020a17  lea     rdx, [rsp+28h+arg_8]
0x180020a1c  mov     [rsp+28h+arg_8], 0
0x180020a24  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIPrimaryTileUserNotifier@StateRepository@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::StateRepository::IPrimaryTileUserNotifier,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180020a29  mov     dword ptr [rdi], 2
0x180020a2f  xor     eax, eax
0x180020a31  mov     [rbx], r8
0x180020a34  mov     rbx, [rsp+28h+arg_0]
0x180020a39  add     rsp, 20h
0x180020a3d  pop     rdi
0x180020a3e  retn
```
