# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextUndoPendingKeyEventsAcknowledgedEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001d930`
- end: `0x18001d991`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextUndoPendingKeyEventsAcknowledgedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001d930`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d952`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d952`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextUndoPendingKeyEventsAcknowledgedEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_88200069_88a0_46ca_8935_eab37e2164f4;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001d930  mov     [rsp+arg_0], rbx
0x18001d935  push    rdi
0x18001d936  sub     rsp, 20h
0x18001d93a  mov     qword ptr [r8], 0
0x18001d941  mov     ecx, 20h ; ' '; cb
0x18001d946  mov     dword ptr [rdx], 0
0x18001d94c  mov     rbx, r8
0x18001d94f  mov     rdi, rdx
0x18001d952  call    cs:__imp_CoTaskMemAlloc
0x18001d958  test    rax, rax
0x18001d95b  jnz     short loc_18001D964
0x18001d95d  mov     eax, 8007000Eh
0x18001d962  jmp     short loc_18001D986
0x18001d964  movups  xmm0, xmmword ptr cs:_GUID_88200069_88a0_46ca_8935_eab37e2164f4.Data1
0x18001d96b  movdqu  xmmword ptr [rax], xmm0
0x18001d96f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001d976  movdqu  xmmword ptr [rax+10h], xmm1
0x18001d97b  mov     dword ptr [rdi], 2
0x18001d981  mov     [rbx], rax
0x18001d984  xor     eax, eax
0x18001d986  mov     rbx, [rsp+28h+arg_0]
0x18001d98b  add     rsp, 20h
0x18001d98f  pop     rdi
0x18001d990  retn
```
