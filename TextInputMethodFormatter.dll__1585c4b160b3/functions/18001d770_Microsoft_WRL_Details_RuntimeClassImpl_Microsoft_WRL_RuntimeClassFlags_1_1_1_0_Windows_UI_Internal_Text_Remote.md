# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextReregistrationRequestedEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001d770`
- end: `0x18001d7d1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextReregistrationRequestedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001d770`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d792`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d792`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextReregistrationRequestedEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_432ff3c4_6fe2_4a71_abbb_3bc9f1c56959;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001d770  mov     [rsp+arg_0], rbx
0x18001d775  push    rdi
0x18001d776  sub     rsp, 20h
0x18001d77a  mov     qword ptr [r8], 0
0x18001d781  mov     ecx, 20h ; ' '; cb
0x18001d786  mov     dword ptr [rdx], 0
0x18001d78c  mov     rbx, r8
0x18001d78f  mov     rdi, rdx
0x18001d792  call    cs:__imp_CoTaskMemAlloc
0x18001d798  test    rax, rax
0x18001d79b  jnz     short loc_18001D7A4
0x18001d79d  mov     eax, 8007000Eh
0x18001d7a2  jmp     short loc_18001D7C6
0x18001d7a4  movups  xmm0, xmmword ptr cs:_GUID_432ff3c4_6fe2_4a71_abbb_3bc9f1c56959.Data1
0x18001d7ab  movdqu  xmmword ptr [rax], xmm0
0x18001d7af  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001d7b6  movdqu  xmmword ptr [rax+10h], xmm1
0x18001d7bb  mov     dword ptr [rdi], 2
0x18001d7c1  mov     [rbx], rax
0x18001d7c4  xor     eax, eax
0x18001d7c6  mov     rbx, [rsp+28h+arg_0]
0x18001d7cb  add     rsp, 20h
0x18001d7cf  pop     rdi
0x18001d7d0  retn
```
