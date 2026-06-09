# Microsoft::WRL::ActivationFactory<Windows::UI::Input::Preview::Injection::IInputInjectorStatics,Windows::UI::Input::Preview::Injection::IInputInjectorStatics2,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x180008430`
- end: `0x18000849d`
- name: `?GetIids@?$ActivationFactory@UIInputInjectorStatics@Injection@Preview@Input@UI@Windows@@UIInputInjectorStatics2@23456@VNil@Details@WRL@Microsoft@@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800084b0`
- `0x1800084c0`
- `0x180008540`

## callees

- `0x180008430`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008452`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008452`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Windows::UI::Input::Preview::Injection::IInputInjectorStatics,Windows::UI::Input::Preview::Injection::IInputInjectorStatics2,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  v5[1] = GUID_deae6943_7402_4141_a5c6_0c01aa57b16a;
  v5[2] = GUID_a4db38fb_dd8c_414f_95ea_f87ef4c0ae6c;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180008430  mov     [rsp+arg_0], rbx
0x180008435  push    rdi
0x180008436  sub     rsp, 20h
0x18000843a  mov     qword ptr [r8], 0
0x180008441  mov     ecx, 30h ; '0'; cb
0x180008446  mov     dword ptr [rdx], 0
0x18000844c  mov     rbx, r8
0x18000844f  mov     rdi, rdx
0x180008452  call    cs:__imp_CoTaskMemAlloc
0x180008458  test    rax, rax
0x18000845b  jnz     short loc_180008464
0x18000845d  mov     eax, 8007000Eh
0x180008462  jmp     short loc_180008492
0x180008464  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000846b  movdqu  xmmword ptr [rax], xmm0
0x18000846f  movups  xmm1, xmmword ptr cs:_GUID_deae6943_7402_4141_a5c6_0c01aa57b16a.Data1
0x180008476  movdqu  xmmword ptr [rax+10h], xmm1
0x18000847b  movups  xmm0, xmmword ptr cs:_GUID_a4db38fb_dd8c_414f_95ea_f87ef4c0ae6c.Data1
0x180008482  movdqu  xmmword ptr [rax+20h], xmm0
0x180008487  mov     dword ptr [rdi], 3
0x18000848d  mov     [rbx], rax
0x180008490  xor     eax, eax
0x180008492  mov     rbx, [rsp+28h+arg_0]
0x180008497  add     rsp, 20h
0x18000849b  pop     rdi
0x18000849c  retn
```
