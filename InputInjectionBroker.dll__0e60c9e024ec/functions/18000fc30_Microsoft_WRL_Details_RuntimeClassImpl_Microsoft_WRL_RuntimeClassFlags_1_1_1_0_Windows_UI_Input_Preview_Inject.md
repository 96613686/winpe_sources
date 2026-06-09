# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputPenInfo,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18000fc30`
- end: `0x18000fc91`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectedInputPenInfo@Injection@Preview@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000fc30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fc52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fc52`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputPenInfo,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_6b40ad03_ca1e_5527_7e02_2828540bb1d4;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000fc30  mov     [rsp+arg_0], rbx
0x18000fc35  push    rdi
0x18000fc36  sub     rsp, 20h
0x18000fc3a  mov     qword ptr [r8], 0
0x18000fc41  mov     ecx, 20h ; ' '; cb
0x18000fc46  mov     dword ptr [rdx], 0
0x18000fc4c  mov     rbx, r8
0x18000fc4f  mov     rdi, rdx
0x18000fc52  call    cs:__imp_CoTaskMemAlloc
0x18000fc58  test    rax, rax
0x18000fc5b  jnz     short loc_18000FC64
0x18000fc5d  mov     eax, 8007000Eh
0x18000fc62  jmp     short loc_18000FC86
0x18000fc64  movups  xmm0, xmmword ptr cs:_GUID_6b40ad03_ca1e_5527_7e02_2828540bb1d4.Data1
0x18000fc6b  movdqu  xmmword ptr [rax], xmm0
0x18000fc6f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18000fc76  movdqu  xmmword ptr [rax+10h], xmm1
0x18000fc7b  mov     dword ptr [rdi], 2
0x18000fc81  mov     [rbx], rax
0x18000fc84  xor     eax, eax
0x18000fc86  mov     rbx, [rsp+28h+arg_0]
0x18000fc8b  add     rsp, 20h
0x18000fc8f  pop     rdi
0x18000fc90  retn
```
