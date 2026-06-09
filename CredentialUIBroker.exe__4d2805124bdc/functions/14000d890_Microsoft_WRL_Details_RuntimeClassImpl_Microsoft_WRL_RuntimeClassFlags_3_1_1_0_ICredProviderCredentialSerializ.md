# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICredProviderCredentialSerialization,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x14000d890`
- end: `0x14000d8fa`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICredProviderCredentialSerialization@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000c244`
- `0x14000d890`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000d8b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000d8b2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICredProviderCredentialSerialization,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICredProviderCredentialSerialization,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x14000d890  mov     [rsp+arg_0], rbx
0x14000d895  push    rdi
0x14000d896  sub     rsp, 20h
0x14000d89a  mov     qword ptr [r8], 0
0x14000d8a1  mov     ecx, 30h ; '0'; cb
0x14000d8a6  mov     dword ptr [rdx], 0
0x14000d8ac  mov     rbx, r8
0x14000d8af  mov     rdi, rdx
0x14000d8b2  call    cs:__imp_CoTaskMemAlloc
0x14000d8b8  mov     r8, rax
0x14000d8bb  test    rax, rax
0x14000d8be  jnz     short loc_14000D8C7
0x14000d8c0  mov     eax, 8007000Eh
0x14000d8c5  jmp     short loc_14000D8EF
0x14000d8c7  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x14000d8ce  lea     rdx, [rsp+28h+arg_8]
0x14000d8d3  mov     [rsp+28h+arg_8], 1
0x14000d8db  movdqu  xmmword ptr [rax], xmm0
0x14000d8df  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UICredProviderCredentialSerialization@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICredProviderCredentialSerialization,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14000d8e4  mov     dword ptr [rdi], 3
0x14000d8ea  xor     eax, eax
0x14000d8ec  mov     [rbx], r8
0x14000d8ef  mov     rbx, [rsp+28h+arg_0]
0x14000d8f4  add     rsp, 20h
0x14000d8f8  pop     rdi
0x14000d8f9  retn
```
