# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextErrorReportedEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001d070`
- end: `0x18001d0d1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextErrorReportedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001d070`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d092`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d092`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextErrorReportedEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_7d98ff14_38c9_4f3e_9655_f46f37f58489;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001d070  mov     [rsp+arg_0], rbx
0x18001d075  push    rdi
0x18001d076  sub     rsp, 20h
0x18001d07a  mov     qword ptr [r8], 0
0x18001d081  mov     ecx, 20h ; ' '; cb
0x18001d086  mov     dword ptr [rdx], 0
0x18001d08c  mov     rbx, r8
0x18001d08f  mov     rdi, rdx
0x18001d092  call    cs:__imp_CoTaskMemAlloc
0x18001d098  test    rax, rax
0x18001d09b  jnz     short loc_18001D0A4
0x18001d09d  mov     eax, 8007000Eh
0x18001d0a2  jmp     short loc_18001D0C6
0x18001d0a4  movups  xmm0, xmmword ptr cs:_GUID_7d98ff14_38c9_4f3e_9655_f46f37f58489.Data1
0x18001d0ab  movdqu  xmmword ptr [rax], xmm0
0x18001d0af  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001d0b6  movdqu  xmmword ptr [rax+10h], xmm1
0x18001d0bb  mov     dword ptr [rdi], 2
0x18001d0c1  mov     [rbx], rax
0x18001d0c4  xor     eax, eax
0x18001d0c6  mov     rbx, [rsp+28h+arg_0]
0x18001d0cb  add     rsp, 20h
0x18001d0cf  pop     rdi
0x18001d0d0  retn
```
