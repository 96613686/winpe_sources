# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Windows::Internal::CapabilityAccess::IAppLaunchCapabilityAccessStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(ulong *,_GUID * *)

- ea: `0x180011690`
- end: `0x1800116f1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@$00$0A@UIActivationFactory@@UIAppLaunchCapabilityAccessStatics@CapabilityAccess@Internal@Windows@@VNil@Details@23@V9Details@23@V9Details@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011700`

## callees

- `0x180011690`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800116b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800116b2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Windows::Internal::CapabilityAccess::IAppLaunchCapabilityAccessStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(
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
  v5[1] = GUID_365b4229_bffa_4446_8dc8_a293bebbe536;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180011690  mov     [rsp+arg_0], rbx
0x180011695  push    rdi
0x180011696  sub     rsp, 20h
0x18001169a  mov     qword ptr [r8], 0
0x1800116a1  mov     ecx, 20h ; ' '; cb
0x1800116a6  mov     dword ptr [rdx], 0
0x1800116ac  mov     rbx, r8
0x1800116af  mov     rdi, rdx
0x1800116b2  call    cs:__imp_CoTaskMemAlloc
0x1800116b8  test    rax, rax
0x1800116bb  jnz     short loc_1800116C4
0x1800116bd  mov     eax, 8007000Eh
0x1800116c2  jmp     short loc_1800116E6
0x1800116c4  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x1800116cb  movdqu  xmmword ptr [rax], xmm0
0x1800116cf  movups  xmm1, xmmword ptr cs:_GUID_365b4229_bffa_4446_8dc8_a293bebbe536.Data1
0x1800116d6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800116db  mov     dword ptr [rdi], 2
0x1800116e1  mov     [rbx], rax
0x1800116e4  xor     eax, eax
0x1800116e6  mov     rbx, [rsp+28h+arg_0]
0x1800116eb  add     rsp, 20h
0x1800116ef  pop     rdi
0x1800116f0  retn
```
