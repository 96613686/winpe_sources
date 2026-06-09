# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x180003b90`
- end: `0x180003bf1`
- name: `?GetIids@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003c00`

## callees

- `0x180003b90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003bb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003bb2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  v5[1] = GUID_daf9b96d_b02b_4c08_a51e_bfaf8e625d67;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180003b90  mov     [rsp+arg_0], rbx
0x180003b95  push    rdi
0x180003b96  sub     rsp, 20h
0x180003b9a  mov     qword ptr [r8], 0
0x180003ba1  mov     ecx, 20h ; ' '; cb
0x180003ba6  mov     dword ptr [rdx], 0
0x180003bac  mov     rbx, r8
0x180003baf  mov     rdi, rdx
0x180003bb2  call    cs:__imp_CoTaskMemAlloc
0x180003bb8  test    rax, rax
0x180003bbb  jnz     short loc_180003BC4
0x180003bbd  mov     eax, 8007000Eh
0x180003bc2  jmp     short loc_180003BE6
0x180003bc4  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x180003bcb  movdqu  xmmword ptr [rax], xmm0
0x180003bcf  movups  xmm1, xmmword ptr cs:_GUID_daf9b96d_b02b_4c08_a51e_bfaf8e625d67.Data1
0x180003bd6  movdqu  xmmword ptr [rax+10h], xmm1
0x180003bdb  mov     dword ptr [rdi], 2
0x180003be1  mov     [rbx], rax
0x180003be4  xor     eax, eax
0x180003be6  mov     rbx, [rsp+28h+arg_0]
0x180003beb  add     rsp, 20h
0x180003bef  pop     rdi
0x180003bf0  retn
```
