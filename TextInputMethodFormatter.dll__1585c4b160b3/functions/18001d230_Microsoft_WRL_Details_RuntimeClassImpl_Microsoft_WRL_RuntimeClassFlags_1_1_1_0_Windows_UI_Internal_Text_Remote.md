# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextFormatUpdatingEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001d230`
- end: `0x18001d291`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextFormatUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001d230`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d252`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d252`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextFormatUpdatingEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_c56469d8_96ba_4e1e_9a9e_57af907fba25;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001d230  mov     [rsp+arg_0], rbx
0x18001d235  push    rdi
0x18001d236  sub     rsp, 20h
0x18001d23a  mov     qword ptr [r8], 0
0x18001d241  mov     ecx, 20h ; ' '; cb
0x18001d246  mov     dword ptr [rdx], 0
0x18001d24c  mov     rbx, r8
0x18001d24f  mov     rdi, rdx
0x18001d252  call    cs:__imp_CoTaskMemAlloc
0x18001d258  test    rax, rax
0x18001d25b  jnz     short loc_18001D264
0x18001d25d  mov     eax, 8007000Eh
0x18001d262  jmp     short loc_18001D286
0x18001d264  movups  xmm0, xmmword ptr cs:_GUID_c56469d8_96ba_4e1e_9a9e_57af907fba25.Data1
0x18001d26b  movdqu  xmmword ptr [rax], xmm0
0x18001d26f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001d276  movdqu  xmmword ptr [rax+10h], xmm1
0x18001d27b  mov     dword ptr [rdi], 2
0x18001d281  mov     [rbx], rax
0x18001d284  xor     eax, eax
0x18001d286  mov     rbx, [rsp+28h+arg_0]
0x18001d28b  add     rsp, 20h
0x18001d28f  pop     rdi
0x18001d290  retn
```
