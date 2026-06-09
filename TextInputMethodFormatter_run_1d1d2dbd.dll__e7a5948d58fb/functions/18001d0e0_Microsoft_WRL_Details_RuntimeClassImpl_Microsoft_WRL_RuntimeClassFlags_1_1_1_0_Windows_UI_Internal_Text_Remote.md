# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextFeatureModeUpdatingEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001d0e0`
- end: `0x18001d141`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextFeatureModeUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001d0e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d102`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextFeatureModeUpdatingEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_708e63da_c83f_4fd1_ae41_ede00d7f20fe;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001d0e0  mov     [rsp+arg_0], rbx
0x18001d0e5  push    rdi
0x18001d0e6  sub     rsp, 20h
0x18001d0ea  mov     qword ptr [r8], 0
0x18001d0f1  mov     ecx, 20h ; ' '; cb
0x18001d0f6  mov     dword ptr [rdx], 0
0x18001d0fc  mov     rbx, r8
0x18001d0ff  mov     rdi, rdx
0x18001d102  call    cs:__imp_CoTaskMemAlloc
0x18001d108  test    rax, rax
0x18001d10b  jnz     short loc_18001D114
0x18001d10d  mov     eax, 8007000Eh
0x18001d112  jmp     short loc_18001D136
0x18001d114  movups  xmm0, xmmword ptr cs:_GUID_708e63da_c83f_4fd1_ae41_ede00d7f20fe.Data1
0x18001d11b  movdqu  xmmword ptr [rax], xmm0
0x18001d11f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001d126  movdqu  xmmword ptr [rax+10h], xmm1
0x18001d12b  mov     dword ptr [rdi], 2
0x18001d131  mov     [rbx], rax
0x18001d134  xor     eax, eax
0x18001d136  mov     rbx, [rsp+28h+arg_0]
0x18001d13b  add     rsp, 20h
0x18001d13f  pop     rdi
0x18001d140  retn
```
