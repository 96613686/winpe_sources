# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextRemoteIntegrationStatusChangedEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001d700`
- end: `0x18001d761`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextRemoteIntegrationStatusChangedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001d700`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d722`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d722`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextRemoteIntegrationStatusChangedEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_3c3dfca4_dccf_4b1f_82cf_e46d3ee9a6fa;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001d700  mov     [rsp+arg_0], rbx
0x18001d705  push    rdi
0x18001d706  sub     rsp, 20h
0x18001d70a  mov     qword ptr [r8], 0
0x18001d711  mov     ecx, 20h ; ' '; cb
0x18001d716  mov     dword ptr [rdx], 0
0x18001d71c  mov     rbx, r8
0x18001d71f  mov     rdi, rdx
0x18001d722  call    cs:__imp_CoTaskMemAlloc
0x18001d728  test    rax, rax
0x18001d72b  jnz     short loc_18001D734
0x18001d72d  mov     eax, 8007000Eh
0x18001d732  jmp     short loc_18001D756
0x18001d734  movups  xmm0, xmmword ptr cs:_GUID_3c3dfca4_dccf_4b1f_82cf_e46d3ee9a6fa.Data1
0x18001d73b  movdqu  xmmword ptr [rax], xmm0
0x18001d73f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001d746  movdqu  xmmword ptr [rax+10h], xmm1
0x18001d74b  mov     dword ptr [rdi], 2
0x18001d751  mov     [rbx], rax
0x18001d754  xor     eax, eax
0x18001d756  mov     rbx, [rsp+28h+arg_0]
0x18001d75b  add     rsp, 20h
0x18001d75f  pop     rdi
0x18001d760  retn
```
