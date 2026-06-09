# Microsoft::WRL::ActivationFactory<Windows::System::Diagnostics::IDiagnosticInvokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x180007450`
- end: `0x1800074b1`
- name: `?GetIids@?$ActivationFactory@UIDiagnosticInvokerStatics@Diagnostics@System@Windows@@VNil@Details@WRL@Microsoft@@V5678@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800074c0`

## callees

- `0x180007450`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007472`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007472`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Windows::System::Diagnostics::IDiagnosticInvokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  v5[1] = GUID_5cfad8de_f15c_4554_a813_c113c3881b09;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180007450  mov     [rsp+arg_0], rbx
0x180007455  push    rdi
0x180007456  sub     rsp, 20h
0x18000745a  mov     qword ptr [r8], 0
0x180007461  mov     ecx, 20h ; ' '; cb
0x180007466  mov     dword ptr [rdx], 0
0x18000746c  mov     rbx, r8
0x18000746f  mov     rdi, rdx
0x180007472  call    cs:__imp_CoTaskMemAlloc
0x180007478  test    rax, rax
0x18000747b  jnz     short loc_180007484
0x18000747d  mov     eax, 8007000Eh
0x180007482  jmp     short loc_1800074A6
0x180007484  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000748b  movdqu  xmmword ptr [rax], xmm0
0x18000748f  movups  xmm1, xmmword ptr cs:_GUID_5cfad8de_f15c_4554_a813_c113c3881b09.Data1
0x180007496  movdqu  xmmword ptr [rax+10h], xmm1
0x18000749b  mov     dword ptr [rdi], 2
0x1800074a1  mov     [rbx], rax
0x1800074a4  xor     eax, eax
0x1800074a6  mov     rbx, [rsp+28h+arg_0]
0x1800074ab  add     rsp, 20h
0x1800074af  pop     rdi
0x1800074b0  retn
```
