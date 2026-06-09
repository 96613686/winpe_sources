# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::IIterable<Windows::Networking::UX::NetworkMediaType>>::GetIids(ulong *,_GUID * *)

- ea: `0x180048960`
- end: `0x1800489cd`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IVectorView@W4NetworkMediaType@UX@Networking@Windows@@@Collections@Foundation@Windows@@U?$IIterable@W4NetworkMediaType@UX@Networking@Windows@@@567@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800489e0`

## callees

- `0x180048960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180048982`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180048982`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::IIterable<enum Windows::Networking::UX::NetworkMediaType>>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_28f9f624_c289_55c4_82a4_99153e5dc533;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_cbc84f97_31e2_52f7_bdac_e9c22b4968e4;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180048960  mov     [rsp+arg_0], rbx
0x180048965  push    rdi
0x180048966  sub     rsp, 20h
0x18004896a  mov     qword ptr [r8], 0
0x180048971  mov     ecx, 30h ; '0'; cb
0x180048976  mov     dword ptr [rdx], 0
0x18004897c  mov     rbx, r8
0x18004897f  mov     rdi, rdx
0x180048982  call    cs:__imp_CoTaskMemAlloc
0x180048988  test    rax, rax
0x18004898b  jnz     short loc_180048994
0x18004898d  mov     eax, 8007000Eh
0x180048992  jmp     short loc_1800489C2
0x180048994  movups  xmm0, xmmword ptr cs:_GUID_28f9f624_c289_55c4_82a4_99153e5dc533.Data1
0x18004899b  movdqu  xmmword ptr [rax], xmm0
0x18004899f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800489a6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800489ab  movups  xmm0, xmmword ptr cs:_GUID_cbc84f97_31e2_52f7_bdac_e9c22b4968e4.Data1
0x1800489b2  movdqu  xmmword ptr [rax+20h], xmm0
0x1800489b7  mov     dword ptr [rdi], 3
0x1800489bd  mov     [rbx], rax
0x1800489c0  xor     eax, eax
0x1800489c2  mov     rbx, [rsp+28h+arg_0]
0x1800489c7  add     rsp, 20h
0x1800489cb  pop     rdi
0x1800489cc  retn
```
