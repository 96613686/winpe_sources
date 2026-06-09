# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::IDiagnosticInvoker,Windows::System::Diagnostics::IDiagnosticInvoker2,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18000b270`
- end: `0x18000b2dd`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIDiagnosticInvoker@Diagnostics@System@Windows@@UIDiagnosticInvoker2@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b2f0`
- `0x18000b3a0`

## callees

- `0x18000b270`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b292`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b292`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::IDiagnosticInvoker,Windows::System::Diagnostics::IDiagnosticInvoker2,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_187b270a_02e3_4f86_84fc_fdd892b5940f;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_e3bf945c_155a_4b52_a8ec_070c44f95000;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000b270  mov     [rsp+arg_0], rbx
0x18000b275  push    rdi
0x18000b276  sub     rsp, 20h
0x18000b27a  mov     qword ptr [r8], 0
0x18000b281  mov     ecx, 30h ; '0'; cb
0x18000b286  mov     dword ptr [rdx], 0
0x18000b28c  mov     rbx, r8
0x18000b28f  mov     rdi, rdx
0x18000b292  call    cs:__imp_CoTaskMemAlloc
0x18000b298  test    rax, rax
0x18000b29b  jnz     short loc_18000B2A4
0x18000b29d  mov     eax, 8007000Eh
0x18000b2a2  jmp     short loc_18000B2D2
0x18000b2a4  movups  xmm0, xmmword ptr cs:_GUID_187b270a_02e3_4f86_84fc_fdd892b5940f.Data1
0x18000b2ab  movdqu  xmmword ptr [rax], xmm0
0x18000b2af  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18000b2b6  movdqu  xmmword ptr [rax+10h], xmm1
0x18000b2bb  movups  xmm0, xmmword ptr cs:_GUID_e3bf945c_155a_4b52_a8ec_070c44f95000.Data1
0x18000b2c2  movdqu  xmmword ptr [rax+20h], xmm0
0x18000b2c7  mov     dword ptr [rdi], 3
0x18000b2cd  mov     [rbx], rax
0x18000b2d0  xor     eax, eax
0x18000b2d2  mov     rbx, [rsp+28h+arg_0]
0x18000b2d7  add     rsp, 20h
0x18000b2db  pop     rdi
0x18000b2dc  retn
```
