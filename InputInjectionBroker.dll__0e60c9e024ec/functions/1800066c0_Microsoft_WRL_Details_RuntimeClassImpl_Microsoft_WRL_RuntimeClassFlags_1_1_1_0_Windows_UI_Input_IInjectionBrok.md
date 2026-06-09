# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::IInjectionBroker,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800066c0`
- end: `0x180006721`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectionBroker@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800066c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800066e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800066e2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::IInjectionBroker,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_f484a4ba_f4b8_4202_bfac_a6e3af2b6e90;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800066c0  mov     [rsp+arg_0], rbx
0x1800066c5  push    rdi
0x1800066c6  sub     rsp, 20h
0x1800066ca  mov     qword ptr [r8], 0
0x1800066d1  mov     ecx, 20h ; ' '; cb
0x1800066d6  mov     dword ptr [rdx], 0
0x1800066dc  mov     rbx, r8
0x1800066df  mov     rdi, rdx
0x1800066e2  call    cs:__imp_CoTaskMemAlloc
0x1800066e8  test    rax, rax
0x1800066eb  jnz     short loc_1800066F4
0x1800066ed  mov     eax, 8007000Eh
0x1800066f2  jmp     short loc_180006716
0x1800066f4  movups  xmm0, xmmword ptr cs:_GUID_f484a4ba_f4b8_4202_bfac_a6e3af2b6e90.Data1
0x1800066fb  movdqu  xmmword ptr [rax], xmm0
0x1800066ff  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180006706  movdqu  xmmword ptr [rax+10h], xmm1
0x18000670b  mov     dword ptr [rdi], 2
0x180006711  mov     [rbx], rax
0x180006714  xor     eax, eax
0x180006716  mov     rbx, [rsp+28h+arg_0]
0x18000671b  add     rsp, 20h
0x18000671f  pop     rdi
0x180006720  retn
```
