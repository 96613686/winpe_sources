# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x1800053d0`
- end: `0x180005431`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UISWDDeviceStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005440`

## callees

- `0x1800053d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800053f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800053f2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  v5[1] = GUID_5189313c_fc43_41b2_82cc_271a0ee29e80;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800053d0  mov     [rsp+arg_0], rbx
0x1800053d5  push    rdi
0x1800053d6  sub     rsp, 20h
0x1800053da  mov     qword ptr [r8], 0
0x1800053e1  mov     ecx, 20h ; ' '; cb
0x1800053e6  mov     dword ptr [rdx], 0
0x1800053ec  mov     rbx, r8
0x1800053ef  mov     rdi, rdx
0x1800053f2  call    cs:__imp_CoTaskMemAlloc
0x1800053f8  test    rax, rax
0x1800053fb  jnz     short loc_180005404
0x1800053fd  mov     eax, 8007000Eh
0x180005402  jmp     short loc_180005426
0x180005404  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000540b  movdqu  xmmword ptr [rax], xmm0
0x18000540f  movups  xmm1, xmmword ptr cs:_GUID_5189313c_fc43_41b2_82cc_271a0ee29e80.Data1
0x180005416  movdqu  xmmword ptr [rax+10h], xmm1
0x18000541b  mov     dword ptr [rdi], 2
0x180005421  mov     [rbx], rax
0x180005424  xor     eax, eax
0x180005426  mov     rbx, [rsp+28h+arg_0]
0x18000542b  add     rsp, 20h
0x18000542f  pop     rdi
0x180005430  retn
```
