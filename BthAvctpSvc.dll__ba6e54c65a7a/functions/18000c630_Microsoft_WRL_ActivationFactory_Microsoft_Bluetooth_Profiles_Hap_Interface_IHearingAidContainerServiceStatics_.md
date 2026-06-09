# Microsoft::WRL::ActivationFactory<Microsoft::Bluetooth::Profiles::Hap::Interface::IHearingAidContainerServiceStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x18000c630`
- end: `0x18000c691`
- name: `?GetIids@?$ActivationFactory@UIHearingAidContainerServiceStatics@Interface@Hap@Profiles@Bluetooth@Microsoft@@VNil@Details@WRL@6@V7896@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c6a0`

## callees

- `0x18000c630`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c652`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c652`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::Bluetooth::Profiles::Hap::Interface::IHearingAidContainerServiceStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  v5[1] = GUID_f4d80279_9819_57e4_be08_d7d3d9ea3939;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000c630  mov     [rsp+arg_0], rbx
0x18000c635  push    rdi
0x18000c636  sub     rsp, 20h
0x18000c63a  mov     qword ptr [r8], 0
0x18000c641  mov     ecx, 20h ; ' '; cb
0x18000c646  mov     dword ptr [rdx], 0
0x18000c64c  mov     rbx, r8
0x18000c64f  mov     rdi, rdx
0x18000c652  call    cs:__imp_CoTaskMemAlloc
0x18000c658  test    rax, rax
0x18000c65b  jnz     short loc_18000C664
0x18000c65d  mov     eax, 8007000Eh
0x18000c662  jmp     short loc_18000C686
0x18000c664  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000c66b  movdqu  xmmword ptr [rax], xmm0
0x18000c66f  movups  xmm1, xmmword ptr cs:_GUID_f4d80279_9819_57e4_be08_d7d3d9ea3939.Data1
0x18000c676  movdqu  xmmword ptr [rax+10h], xmm1
0x18000c67b  mov     dword ptr [rdi], 2
0x18000c681  mov     [rbx], rax
0x18000c684  xor     eax, eax
0x18000c686  mov     rbx, [rsp+28h+arg_0]
0x18000c68b  add     rsp, 20h
0x18000c68f  pop     rdi
0x18000c690  retn
```
