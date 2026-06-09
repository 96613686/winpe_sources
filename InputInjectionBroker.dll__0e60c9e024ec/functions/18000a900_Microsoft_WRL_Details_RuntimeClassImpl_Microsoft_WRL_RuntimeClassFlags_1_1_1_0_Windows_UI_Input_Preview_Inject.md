# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInputInjector,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18000a900`
- end: `0x18000a979`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInputInjector@Injection@Preview@Input@UI@Windows@@UIInputInjector2@56789@UIInputInjector3@56789@U?$CloakedIid@UIInputInjectorPrivate@Internal@Injection@Preview@Input@UI@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a980`
- `0x18000a990`
- `0x18000a9a0`
- `0x18000a9b0`

## callees

- `0x18000a900`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a922`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a922`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInputInjector,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_8ec26f84_0b02_4bd2_ad7a_3d4658be3e18;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_8e7a905d_1453_43a7_9bcb_06d6d7b305f7;
  v5[3] = GUID_ef2c0f77_5e6a_4c4a_9db3_b6d3293cc05c;
  *a2 = 4;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000a900  mov     [rsp+arg_0], rbx
0x18000a905  push    rdi
0x18000a906  sub     rsp, 20h
0x18000a90a  mov     qword ptr [r8], 0
0x18000a911  mov     ecx, 40h ; '@'; cb
0x18000a916  mov     dword ptr [rdx], 0
0x18000a91c  mov     rbx, r8
0x18000a91f  mov     rdi, rdx
0x18000a922  call    cs:__imp_CoTaskMemAlloc
0x18000a928  test    rax, rax
0x18000a92b  jnz     short loc_18000A934
0x18000a92d  mov     eax, 8007000Eh
0x18000a932  jmp     short loc_18000A96E
0x18000a934  movups  xmm0, xmmword ptr cs:_GUID_8ec26f84_0b02_4bd2_ad7a_3d4658be3e18.Data1
0x18000a93b  movdqu  xmmword ptr [rax], xmm0
0x18000a93f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18000a946  movdqu  xmmword ptr [rax+10h], xmm1
0x18000a94b  movups  xmm0, xmmword ptr cs:_GUID_8e7a905d_1453_43a7_9bcb_06d6d7b305f7.Data1
0x18000a952  movdqu  xmmword ptr [rax+20h], xmm0
0x18000a957  movups  xmm1, xmmword ptr cs:_GUID_ef2c0f77_5e6a_4c4a_9db3_b6d3293cc05c.Data1
0x18000a95e  movdqu  xmmword ptr [rax+30h], xmm1
0x18000a963  mov     dword ptr [rdi], 4
0x18000a969  mov     [rbx], rax
0x18000a96c  xor     eax, eax
0x18000a96e  mov     rbx, [rsp+28h+arg_0]
0x18000a973  add     rsp, 20h
0x18000a977  pop     rdi
0x18000a978  retn
```
