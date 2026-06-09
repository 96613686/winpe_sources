# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x180003b00`
- end: `0x180003b6d`
- name: `?GetIids@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003b80`
- `0x180003c10`

## callees

- `0x180003b00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003b22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003b22`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  v5[1] = GUID_495958d0_37b1_494b_90a4_07258caf648f;
  v5[2] = GUID_53e31837_6600_4a81_9395_75cffe746f94;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180003b00  mov     [rsp+arg_0], rbx
0x180003b05  push    rdi
0x180003b06  sub     rsp, 20h
0x180003b0a  mov     qword ptr [r8], 0
0x180003b11  mov     ecx, 30h ; '0'; cb
0x180003b16  mov     dword ptr [rdx], 0
0x180003b1c  mov     rbx, r8
0x180003b1f  mov     rdi, rdx
0x180003b22  call    cs:__imp_CoTaskMemAlloc
0x180003b28  test    rax, rax
0x180003b2b  jnz     short loc_180003B34
0x180003b2d  mov     eax, 8007000Eh
0x180003b32  jmp     short loc_180003B62
0x180003b34  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x180003b3b  movdqu  xmmword ptr [rax], xmm0
0x180003b3f  movups  xmm1, xmmword ptr cs:_GUID_495958d0_37b1_494b_90a4_07258caf648f.Data1
0x180003b46  movdqu  xmmword ptr [rax+10h], xmm1
0x180003b4b  movups  xmm0, xmmword ptr cs:_GUID_53e31837_6600_4a81_9395_75cffe746f94.Data1
0x180003b52  movdqu  xmmword ptr [rax+20h], xmm0
0x180003b57  mov     dword ptr [rdi], 3
0x180003b5d  mov     [rbx], rax
0x180003b60  xor     eax, eax
0x180003b62  mov     rbx, [rsp+28h+arg_0]
0x180003b67  add     rsp, 20h
0x180003b6b  pop     rdi
0x180003b6c  retn
```
