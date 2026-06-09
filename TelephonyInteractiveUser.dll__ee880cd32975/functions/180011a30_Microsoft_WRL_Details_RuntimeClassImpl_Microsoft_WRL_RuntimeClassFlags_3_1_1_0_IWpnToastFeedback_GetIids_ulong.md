# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IWpnToastFeedback>::GetIids(ulong *,_GUID * *)

- ea: `0x180011a30`
- end: `0x180011a9d`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIWpnToastFeedback@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180011a30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011a52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011a52`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IWpnToastFeedback>::GetIids(
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
  v5[1] = GUID_4f38fd3e_2c10_4c00_9ec1_62bd536a1feb;
  v5[2] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180011a30  mov     [rsp+arg_0], rbx
0x180011a35  push    rdi
0x180011a36  sub     rsp, 20h
0x180011a3a  mov     qword ptr [r8], 0
0x180011a41  mov     ecx, 30h ; '0'; cb
0x180011a46  mov     dword ptr [rdx], 0
0x180011a4c  mov     rbx, r8
0x180011a4f  mov     rdi, rdx
0x180011a52  call    cs:__imp_CoTaskMemAlloc
0x180011a58  test    rax, rax
0x180011a5b  jnz     short loc_180011A64
0x180011a5d  mov     eax, 8007000Eh
0x180011a62  jmp     short loc_180011A92
0x180011a64  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x180011a6b  movdqu  xmmword ptr [rax], xmm0
0x180011a6f  movups  xmm1, xmmword ptr cs:_GUID_4f38fd3e_2c10_4c00_9ec1_62bd536a1feb.Data1
0x180011a76  movdqu  xmmword ptr [rax+10h], xmm1
0x180011a7b  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180011a82  movdqu  xmmword ptr [rax+20h], xmm0
0x180011a87  mov     dword ptr [rdi], 3
0x180011a8d  mov     [rbx], rax
0x180011a90  xor     eax, eax
0x180011a92  mov     rbx, [rsp+28h+arg_0]
0x180011a97  add     rsp, 20h
0x180011a9b  pop     rdi
0x180011a9c  retn
```
