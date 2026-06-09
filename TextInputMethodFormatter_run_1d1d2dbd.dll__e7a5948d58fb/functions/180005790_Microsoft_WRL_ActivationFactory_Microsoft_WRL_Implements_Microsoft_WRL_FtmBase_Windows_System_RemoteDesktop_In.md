# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::RemoteDesktop::Input::IRemoteTextConnectionFactory>,Windows::System::RemoteDesktop::Input::IRemoteTextConnectionFactory2,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x180005790`
- end: `0x1800057fd`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIRemoteTextConnectionFactory@Input@RemoteDesktop@System@Windows@@@WRL@Microsoft@@UIRemoteTextConnectionFactory2@Input@RemoteDesktop@System@Windows@@VNil@Details@23@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005810`
- `0x180005820`

## callees

- `0x180005790`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800057b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800057b2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::RemoteDesktop::Input::IRemoteTextConnectionFactory>,Windows::System::RemoteDesktop::Input::IRemoteTextConnectionFactory2,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  v5[1] = GUID_88e075c2_0cae_596c_850f_78d345cd728b;
  v5[2] = GUID_9425c7d9_ed9b_5d00_99cc_b0b8dc9e4c60;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180005790  mov     [rsp+arg_0], rbx
0x180005795  push    rdi
0x180005796  sub     rsp, 20h
0x18000579a  mov     qword ptr [r8], 0
0x1800057a1  mov     ecx, 30h ; '0'; cb
0x1800057a6  mov     dword ptr [rdx], 0
0x1800057ac  mov     rbx, r8
0x1800057af  mov     rdi, rdx
0x1800057b2  call    cs:__imp_CoTaskMemAlloc
0x1800057b8  test    rax, rax
0x1800057bb  jnz     short loc_1800057C4
0x1800057bd  mov     eax, 8007000Eh
0x1800057c2  jmp     short loc_1800057F2
0x1800057c4  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x1800057cb  movdqu  xmmword ptr [rax], xmm0
0x1800057cf  movups  xmm1, xmmword ptr cs:_GUID_88e075c2_0cae_596c_850f_78d345cd728b.Data1
0x1800057d6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800057db  movups  xmm0, xmmword ptr cs:_GUID_9425c7d9_ed9b_5d00_99cc_b0b8dc9e4c60.Data1
0x1800057e2  movdqu  xmmword ptr [rax+20h], xmm0
0x1800057e7  mov     dword ptr [rdi], 3
0x1800057ed  mov     [rbx], rax
0x1800057f0  xor     eax, eax
0x1800057f2  mov     rbx, [rsp+28h+arg_0]
0x1800057f7  add     rsp, 20h
0x1800057fb  pop     rdi
0x1800057fc  retn
```
