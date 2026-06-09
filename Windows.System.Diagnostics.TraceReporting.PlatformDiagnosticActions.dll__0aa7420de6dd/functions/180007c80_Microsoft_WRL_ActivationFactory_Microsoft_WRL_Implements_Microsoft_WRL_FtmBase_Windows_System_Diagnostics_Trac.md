# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x180007c80`
- end: `0x180007ce1`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007cf0`

## callees

- `0x180007c80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007ca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007ca2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  v5[1] = GUID_c1145cfa_9292_4267_890a_9ea3ed072312;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180007c80  mov     [rsp+arg_0], rbx
0x180007c85  push    rdi
0x180007c86  sub     rsp, 20h
0x180007c8a  mov     qword ptr [r8], 0
0x180007c91  mov     ecx, 20h ; ' '; cb
0x180007c96  mov     dword ptr [rdx], 0
0x180007c9c  mov     rbx, r8
0x180007c9f  mov     rdi, rdx
0x180007ca2  call    cs:__imp_CoTaskMemAlloc
0x180007ca8  test    rax, rax
0x180007cab  jnz     short loc_180007CB4
0x180007cad  mov     eax, 8007000Eh
0x180007cb2  jmp     short loc_180007CD6
0x180007cb4  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x180007cbb  movdqu  xmmword ptr [rax], xmm0
0x180007cbf  movups  xmm1, xmmword ptr cs:_GUID_c1145cfa_9292_4267_890a_9ea3ed072312.Data1
0x180007cc6  movdqu  xmmword ptr [rax+10h], xmm1
0x180007ccb  mov     dword ptr [rdi], 2
0x180007cd1  mov     [rbx], rax
0x180007cd4  xor     eax, eax
0x180007cd6  mov     rbx, [rsp+28h+arg_0]
0x180007cdb  add     rsp, 20h
0x180007cdf  pop     rdi
0x180007ce0  retn
```
