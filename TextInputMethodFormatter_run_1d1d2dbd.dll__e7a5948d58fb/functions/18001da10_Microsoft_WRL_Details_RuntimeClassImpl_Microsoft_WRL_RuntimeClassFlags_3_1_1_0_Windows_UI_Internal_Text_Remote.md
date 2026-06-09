# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration,IRemoteAppIntegrationOwner>::GetIids(ulong *,_GUID * *)

- ea: `0x18001da10`
- end: `0x18001da7d`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@UIRemoteAppIntegrationOwner@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001da90`

## callees

- `0x18001da10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001da32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001da32`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration,IRemoteAppIntegrationOwner>::GetIids(
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
  *v5 = GUID_ac4530f6_68f2_48b7_803c_647212e1e4be;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_bc7e2ede_2779_48f3_b489_e487d4e1baac;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001da10  mov     [rsp+arg_0], rbx
0x18001da15  push    rdi
0x18001da16  sub     rsp, 20h
0x18001da1a  mov     qword ptr [r8], 0
0x18001da21  mov     ecx, 30h ; '0'; cb
0x18001da26  mov     dword ptr [rdx], 0
0x18001da2c  mov     rbx, r8
0x18001da2f  mov     rdi, rdx
0x18001da32  call    cs:__imp_CoTaskMemAlloc
0x18001da38  test    rax, rax
0x18001da3b  jnz     short loc_18001DA44
0x18001da3d  mov     eax, 8007000Eh
0x18001da42  jmp     short loc_18001DA72
0x18001da44  movups  xmm0, xmmword ptr cs:_GUID_ac4530f6_68f2_48b7_803c_647212e1e4be.Data1
0x18001da4b  movdqu  xmmword ptr [rax], xmm0
0x18001da4f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001da56  movdqu  xmmword ptr [rax+10h], xmm1
0x18001da5b  movups  xmm0, xmmword ptr cs:_GUID_bc7e2ede_2779_48f3_b489_e487d4e1baac.Data1
0x18001da62  movdqu  xmmword ptr [rax+20h], xmm0
0x18001da67  mov     dword ptr [rdi], 3
0x18001da6d  mov     [rbx], rax
0x18001da70  xor     eax, eax
0x18001da72  mov     rbx, [rsp+28h+arg_0]
0x18001da77  add     rsp, 20h
0x18001da7b  pop     rdi
0x18001da7c  retn
```
