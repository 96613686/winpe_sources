# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x18000f3a0`
- end: `0x18000f401`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIInjectedInputGamepadInfoFactory@Injection@Preview@Input@UI@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f410`

## callees

- `0x18000f3a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f3c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f3c2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  v5[1] = GUID_59596876_6c39_4ec4_8b2a_29ef7de18aca;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000f3a0  mov     [rsp+arg_0], rbx
0x18000f3a5  push    rdi
0x18000f3a6  sub     rsp, 20h
0x18000f3aa  mov     qword ptr [r8], 0
0x18000f3b1  mov     ecx, 20h ; ' '; cb
0x18000f3b6  mov     dword ptr [rdx], 0
0x18000f3bc  mov     rbx, r8
0x18000f3bf  mov     rdi, rdx
0x18000f3c2  call    cs:__imp_CoTaskMemAlloc
0x18000f3c8  test    rax, rax
0x18000f3cb  jnz     short loc_18000F3D4
0x18000f3cd  mov     eax, 8007000Eh
0x18000f3d2  jmp     short loc_18000F3F6
0x18000f3d4  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000f3db  movdqu  xmmword ptr [rax], xmm0
0x18000f3df  movups  xmm1, xmmword ptr cs:_GUID_59596876_6c39_4ec4_8b2a_29ef7de18aca.Data1
0x18000f3e6  movdqu  xmmword ptr [rax+10h], xmm1
0x18000f3eb  mov     dword ptr [rdi], 2
0x18000f3f1  mov     [rbx], rax
0x18000f3f4  xor     eax, eax
0x18000f3f6  mov     rbx, [rsp+28h+arg_0]
0x18000f3fb  add     rsp, 20h
0x18000f3ff  pop     rdi
0x18000f400  retn
```
