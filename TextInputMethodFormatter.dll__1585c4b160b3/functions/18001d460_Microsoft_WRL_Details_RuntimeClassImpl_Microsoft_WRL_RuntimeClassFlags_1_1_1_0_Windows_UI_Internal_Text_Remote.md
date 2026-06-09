# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadStartingEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001d460`
- end: `0x18001d4c1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextKeyEventPayloadStartingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001d460`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d482`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d482`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadStartingEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_7cf092ee_a571_46e6_9d1c_be746d79f8eb;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001d460  mov     [rsp+arg_0], rbx
0x18001d465  push    rdi
0x18001d466  sub     rsp, 20h
0x18001d46a  mov     qword ptr [r8], 0
0x18001d471  mov     ecx, 20h ; ' '; cb
0x18001d476  mov     dword ptr [rdx], 0
0x18001d47c  mov     rbx, r8
0x18001d47f  mov     rdi, rdx
0x18001d482  call    cs:__imp_CoTaskMemAlloc
0x18001d488  test    rax, rax
0x18001d48b  jnz     short loc_18001D494
0x18001d48d  mov     eax, 8007000Eh
0x18001d492  jmp     short loc_18001D4B6
0x18001d494  movups  xmm0, xmmword ptr cs:_GUID_7cf092ee_a571_46e6_9d1c_be746d79f8eb.Data1
0x18001d49b  movdqu  xmmword ptr [rax], xmm0
0x18001d49f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001d4a6  movdqu  xmmword ptr [rax+10h], xmm1
0x18001d4ab  mov     dword ptr [rdi], 2
0x18001d4b1  mov     [rbx], rax
0x18001d4b4  xor     eax, eax
0x18001d4b6  mov     rbx, [rsp+28h+arg_0]
0x18001d4bb  add     rsp, 20h
0x18001d4bf  pop     rdi
0x18001d4c0  retn
```
