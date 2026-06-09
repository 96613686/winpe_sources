# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::Bluetooth::Profiles::A2dp::Private::IA2dpSinkPlaybackConnectionStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(ulong *,_GUID * *)

- ea: `0x18000c4b0`
- end: `0x18000c511`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@$00$0A@UIActivationFactory@@UIA2dpSinkPlaybackConnectionStatics@Private@A2dp@Profiles@Bluetooth@3@VNil@Details@23@VNil@Details@23@VNil@Details@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c520`

## callees

- `0x18000c4b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c4d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c4d2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::Bluetooth::Profiles::A2dp::Private::IA2dpSinkPlaybackConnectionStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(
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
  v5[1] = GUID_ee3b8cce_1d10_562d_8b0b_2e838abc5795;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000c4b0  mov     [rsp+arg_0], rbx
0x18000c4b5  push    rdi
0x18000c4b6  sub     rsp, 20h
0x18000c4ba  mov     qword ptr [r8], 0
0x18000c4c1  mov     ecx, 20h ; ' '; cb
0x18000c4c6  mov     dword ptr [rdx], 0
0x18000c4cc  mov     rbx, r8
0x18000c4cf  mov     rdi, rdx
0x18000c4d2  call    cs:__imp_CoTaskMemAlloc
0x18000c4d8  test    rax, rax
0x18000c4db  jnz     short loc_18000C4E4
0x18000c4dd  mov     eax, 8007000Eh
0x18000c4e2  jmp     short loc_18000C506
0x18000c4e4  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000c4eb  movdqu  xmmword ptr [rax], xmm0
0x18000c4ef  movups  xmm1, xmmword ptr cs:_GUID_ee3b8cce_1d10_562d_8b0b_2e838abc5795.Data1
0x18000c4f6  movdqu  xmmword ptr [rax+10h], xmm1
0x18000c4fb  mov     dword ptr [rdi], 2
0x18000c501  mov     [rbx], rax
0x18000c504  xor     eax, eax
0x18000c506  mov     rbx, [rsp+28h+arg_0]
0x18000c50b  add     rsp, 20h
0x18000c50f  pop     rdi
0x18000c510  retn
```
