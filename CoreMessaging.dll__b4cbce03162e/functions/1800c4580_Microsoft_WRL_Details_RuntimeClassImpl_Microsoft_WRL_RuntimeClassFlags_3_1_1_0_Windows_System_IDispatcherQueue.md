# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::System::IDispatcherQueue,Windows::System::IDispatcherQueue2,Windows::System::IDispatcherQueuePartnerInterop,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800c4580`
- end: `0x1800c45f6`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIDispatcherQueue@System@Windows@@UIDispatcherQueue2@56@UIDispatcherQueuePartnerInterop@56@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800c4600`

## callees

- `0x1800c41ec`
- `0x1800c4580`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c45a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c45a2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::System::IDispatcherQueue,Windows::System::IDispatcherQueue2,Windows::System::IDispatcherQueuePartnerInterop,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 2;
  *v5 = GUID_603e88e4_a338_4ffe_a457_a5cfb9ceb899;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::System::IDispatcherQueue2,Windows::System::IDispatcherQueuePartnerInterop,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 4;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x1800c4580  mov     [rsp+arg_0], rbx
0x1800c4585  push    rdi
0x1800c4586  sub     rsp, 20h
0x1800c458a  mov     qword ptr [r8], 0
0x1800c4591  mov     ecx, 40h ; '@'; cb
0x1800c4596  mov     dword ptr [rdx], 0
0x1800c459c  mov     rbx, r8
0x1800c459f  mov     rdi, rdx
0x1800c45a2  call    cs:__imp_CoTaskMemAlloc
0x1800c45a8  mov     r8, rax
0x1800c45ab  test    rax, rax
0x1800c45ae  jnz     short loc_1800C45B7
0x1800c45b0  mov     eax, 8007000Eh
0x1800c45b5  jmp     short loc_1800C45EB
0x1800c45b7  movups  xmm0, xmmword ptr cs:_GUID_603e88e4_a338_4ffe_a457_a5cfb9ceb899.Data1
0x1800c45be  lea     rdx, [rsp+28h+arg_8]
0x1800c45c3  mov     [rsp+28h+arg_8], 2
0x1800c45cb  movdqu  xmmword ptr [rax], xmm0
0x1800c45cf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800c45d6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800c45db  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIDispatcherQueue2@System@Windows@@UIDispatcherQueuePartnerInterop@56@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::System::IDispatcherQueue2,Windows::System::IDispatcherQueuePartnerInterop,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800c45e0  mov     dword ptr [rdi], 4
0x1800c45e6  xor     eax, eax
0x1800c45e8  mov     [rbx], r8
0x1800c45eb  mov     rbx, [rsp+28h+arg_0]
0x1800c45f0  add     rsp, 20h
0x1800c45f4  pop     rdi
0x1800c45f5  retn
```
