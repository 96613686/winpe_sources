# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::IDiagnosticActionResult,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18000f030`
- end: `0x18000f091`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIDiagnosticActionResult@Diagnostics@System@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000f030`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f052`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::IDiagnosticActionResult,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_c265a296_e73b_4097_b28f_3442f03dd831;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000f030  mov     [rsp+arg_0], rbx
0x18000f035  push    rdi
0x18000f036  sub     rsp, 20h
0x18000f03a  mov     qword ptr [r8], 0
0x18000f041  mov     ecx, 20h ; ' '; cb
0x18000f046  mov     dword ptr [rdx], 0
0x18000f04c  mov     rbx, r8
0x18000f04f  mov     rdi, rdx
0x18000f052  call    cs:__imp_CoTaskMemAlloc
0x18000f058  test    rax, rax
0x18000f05b  jnz     short loc_18000F064
0x18000f05d  mov     eax, 8007000Eh
0x18000f062  jmp     short loc_18000F086
0x18000f064  movups  xmm0, xmmword ptr cs:_GUID_c265a296_e73b_4097_b28f_3442f03dd831.Data1
0x18000f06b  movdqu  xmmword ptr [rax], xmm0
0x18000f06f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18000f076  movdqu  xmmword ptr [rax+10h], xmm1
0x18000f07b  mov     dword ptr [rdi], 2
0x18000f081  mov     [rbx], rax
0x18000f084  xor     eax, eax
0x18000f086  mov     rbx, [rsp+28h+arg_0]
0x18000f08b  add     rsp, 20h
0x18000f08f  pop     rdi
0x18000f090  retn
```
