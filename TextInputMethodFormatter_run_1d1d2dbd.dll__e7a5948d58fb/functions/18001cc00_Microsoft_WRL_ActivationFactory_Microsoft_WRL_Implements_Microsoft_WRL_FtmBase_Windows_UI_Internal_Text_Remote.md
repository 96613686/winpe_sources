# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegrationStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x18001cc00`
- end: `0x18001cc61`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIRemoteTextAppIntegrationStatics@Remote@Text@Internal@UI@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001cc70`

## callees

- `0x18001cc00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cc22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cc22`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegrationStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  v5[1] = GUID_e43158d1_8fc2_4ddc_9b23_7dcd37aeec1f;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001cc00  mov     [rsp+arg_0], rbx
0x18001cc05  push    rdi
0x18001cc06  sub     rsp, 20h
0x18001cc0a  mov     qword ptr [r8], 0
0x18001cc11  mov     ecx, 20h ; ' '; cb
0x18001cc16  mov     dword ptr [rdx], 0
0x18001cc1c  mov     rbx, r8
0x18001cc1f  mov     rdi, rdx
0x18001cc22  call    cs:__imp_CoTaskMemAlloc
0x18001cc28  test    rax, rax
0x18001cc2b  jnz     short loc_18001CC34
0x18001cc2d  mov     eax, 8007000Eh
0x18001cc32  jmp     short loc_18001CC56
0x18001cc34  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18001cc3b  movdqu  xmmword ptr [rax], xmm0
0x18001cc3f  movups  xmm1, xmmword ptr cs:_GUID_e43158d1_8fc2_4ddc_9b23_7dcd37aeec1f.Data1
0x18001cc46  movdqu  xmmword ptr [rax+10h], xmm1
0x18001cc4b  mov     dword ptr [rdi], 2
0x18001cc51  mov     [rbx], rax
0x18001cc54  xor     eax, eax
0x18001cc56  mov     rbx, [rsp+28h+arg_0]
0x18001cc5b  add     rsp, 20h
0x18001cc5f  pop     rdi
0x18001cc60  retn
```
