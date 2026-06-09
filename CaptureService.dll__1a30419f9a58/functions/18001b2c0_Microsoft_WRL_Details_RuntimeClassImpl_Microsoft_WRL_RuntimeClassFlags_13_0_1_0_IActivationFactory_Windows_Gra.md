# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Windows::Graphics::Capture::Server::ICapturableItemStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(ulong *,_GUID * *)

- ea: `0x18001b2c0`
- end: `0x18001b321`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@$00$0A@UIActivationFactory@@UICapturableItemStatics@Server@Capture@Graphics@Windows@@VNil@Details@23@VNil@Details@23@VNil@Details@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b330`

## callees

- `0x18001b2c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b2e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b2e2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Windows::Graphics::Capture::Server::ICapturableItemStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(
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
  v5[1] = GUID_2b20df88_fbce_5a40_9f7b_d0fff5e0f0e7;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001b2c0  mov     [rsp+arg_0], rbx
0x18001b2c5  push    rdi
0x18001b2c6  sub     rsp, 20h
0x18001b2ca  mov     qword ptr [r8], 0
0x18001b2d1  mov     ecx, 20h ; ' '; cb
0x18001b2d6  mov     dword ptr [rdx], 0
0x18001b2dc  mov     rbx, r8
0x18001b2df  mov     rdi, rdx
0x18001b2e2  call    cs:__imp_CoTaskMemAlloc
0x18001b2e8  test    rax, rax
0x18001b2eb  jnz     short loc_18001B2F4
0x18001b2ed  mov     eax, 8007000Eh
0x18001b2f2  jmp     short loc_18001B316
0x18001b2f4  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18001b2fb  movdqu  xmmword ptr [rax], xmm0
0x18001b2ff  movups  xmm1, xmmword ptr cs:_GUID_2b20df88_fbce_5a40_9f7b_d0fff5e0f0e7.Data1
0x18001b306  movdqu  xmmword ptr [rax+10h], xmm1
0x18001b30b  mov     dword ptr [rdi], 2
0x18001b311  mov     [rbx], rax
0x18001b314  xor     eax, eax
0x18001b316  mov     rbx, [rsp+28h+arg_0]
0x18001b31b  add     rsp, 20h
0x18001b31f  pop     rdi
0x18001b320  retn
```
