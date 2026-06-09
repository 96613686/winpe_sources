# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputTouchInfo,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18000f730`
- end: `0x18000f791`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectedInputTouchInfo@Injection@Preview@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000f730`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f752`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f752`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputTouchInfo,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_224fd1df_43e8_5ef5_510a_69ca8c9b4c28;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000f730  mov     [rsp+arg_0], rbx
0x18000f735  push    rdi
0x18000f736  sub     rsp, 20h
0x18000f73a  mov     qword ptr [r8], 0
0x18000f741  mov     ecx, 20h ; ' '; cb
0x18000f746  mov     dword ptr [rdx], 0
0x18000f74c  mov     rbx, r8
0x18000f74f  mov     rdi, rdx
0x18000f752  call    cs:__imp_CoTaskMemAlloc
0x18000f758  test    rax, rax
0x18000f75b  jnz     short loc_18000F764
0x18000f75d  mov     eax, 8007000Eh
0x18000f762  jmp     short loc_18000F786
0x18000f764  movups  xmm0, xmmword ptr cs:_GUID_224fd1df_43e8_5ef5_510a_69ca8c9b4c28.Data1
0x18000f76b  movdqu  xmmword ptr [rax], xmm0
0x18000f76f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18000f776  movdqu  xmmword ptr [rax+10h], xmm1
0x18000f77b  mov     dword ptr [rdi], 2
0x18000f781  mov     [rbx], rax
0x18000f784  xor     eax, eax
0x18000f786  mov     rbx, [rsp+28h+arg_0]
0x18000f78b  add     rsp, 20h
0x18000f78f  pop     rdi
0x18000f790  retn
```
