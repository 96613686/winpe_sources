# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Microsoft::WRL::CloakedIid<ICaptureSessionCom>,Microsoft::WRL::CloakedIid<ICaptureSessionCom_Old>,Windows::Graphics::Capture::Server::ICaptureSession>::GetIids(ulong *,_GUID * *)

- ea: `0x1800114e0`
- end: `0x18001154d`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$CloakedIid@UIFastRundown@@@23@U?$CloakedIid@UICaptureSessionCom@@@23@U?$CloakedIid@UICaptureSessionCom_Old@@@23@UICaptureSession@Server@Capture@Graphics@Windows@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011560`
- `0x1800116c0`

## callees

- `0x1800114e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011502`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011502`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Microsoft::WRL::CloakedIid<ICaptureSessionCom>,Microsoft::WRL::CloakedIid<ICaptureSessionCom_Old>,Windows::Graphics::Capture::Server::ICaptureSession>::GetIids(
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
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_3076e6ae_be1d_5fcd_8887_89f057c3c383;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800114e0  mov     [rsp+arg_0], rbx
0x1800114e5  push    rdi
0x1800114e6  sub     rsp, 20h
0x1800114ea  mov     qword ptr [r8], 0
0x1800114f1  mov     ecx, 30h ; '0'; cb
0x1800114f6  mov     dword ptr [rdx], 0
0x1800114fc  mov     rbx, r8
0x1800114ff  mov     rdi, rdx
0x180011502  call    cs:__imp_CoTaskMemAlloc
0x180011508  test    rax, rax
0x18001150b  jnz     short loc_180011514
0x18001150d  mov     eax, 8007000Eh
0x180011512  jmp     short loc_180011542
0x180011514  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18001151b  movdqu  xmmword ptr [rax], xmm0
0x18001151f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180011526  movdqu  xmmword ptr [rax+10h], xmm1
0x18001152b  movups  xmm0, xmmword ptr cs:_GUID_3076e6ae_be1d_5fcd_8887_89f057c3c383.Data1
0x180011532  movdqu  xmmword ptr [rax+20h], xmm0
0x180011537  mov     dword ptr [rdi], 3
0x18001153d  mov     [rbx], rax
0x180011540  xor     eax, eax
0x180011542  mov     rbx, [rsp+28h+arg_0]
0x180011547  add     rsp, 20h
0x18001154b  pop     rdi
0x18001154c  retn
```
