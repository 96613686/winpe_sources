# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800154e0`
- end: `0x18001554a`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@UIBufferByteAccess@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800147b8`
- `0x1800154e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015502`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015502`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_905a0fe0_bc53_11df_8c49_001e4fc686da;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x1800154e0  mov     [rsp+arg_0], rbx
0x1800154e5  push    rdi
0x1800154e6  sub     rsp, 20h
0x1800154ea  mov     qword ptr [r8], 0
0x1800154f1  mov     ecx, 30h ; '0'; cb
0x1800154f6  mov     dword ptr [rdx], 0
0x1800154fc  mov     rbx, r8
0x1800154ff  mov     rdi, rdx
0x180015502  call    cs:__imp_CoTaskMemAlloc
0x180015508  mov     r8, rax
0x18001550b  test    rax, rax
0x18001550e  jnz     short loc_180015517
0x180015510  mov     eax, 8007000Eh
0x180015515  jmp     short loc_18001553F
0x180015517  movups  xmm0, xmmword ptr cs:_GUID_905a0fe0_bc53_11df_8c49_001e4fc686da.Data1
0x18001551e  lea     rdx, [rsp+28h+arg_8]
0x180015523  mov     [rsp+28h+arg_8], 1
0x18001552b  movdqu  xmmword ptr [rax], xmm0
0x18001552f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIBufferByteAccess@Streams@Storage@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180015534  mov     dword ptr [rdi], 3
0x18001553a  xor     eax, eax
0x18001553c  mov     [rbx], r8
0x18001553f  mov     rbx, [rsp+28h+arg_0]
0x180015544  add     rsp, 20h
0x180015548  pop     rdi
0x180015549  retn
```
