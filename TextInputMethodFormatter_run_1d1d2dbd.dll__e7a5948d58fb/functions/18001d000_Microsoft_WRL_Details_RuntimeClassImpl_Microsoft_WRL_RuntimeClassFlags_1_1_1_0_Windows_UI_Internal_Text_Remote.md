# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextEnabledInputProfilesUpdatingEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001d000`
- end: `0x18001d061`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextEnabledInputProfilesUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001d000`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d022`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d022`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextEnabledInputProfilesUpdatingEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_3cdad9ea_8120_43e9_bc6b_83410d558d0a;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001d000  mov     [rsp+arg_0], rbx
0x18001d005  push    rdi
0x18001d006  sub     rsp, 20h
0x18001d00a  mov     qword ptr [r8], 0
0x18001d011  mov     ecx, 20h ; ' '; cb
0x18001d016  mov     dword ptr [rdx], 0
0x18001d01c  mov     rbx, r8
0x18001d01f  mov     rdi, rdx
0x18001d022  call    cs:__imp_CoTaskMemAlloc
0x18001d028  test    rax, rax
0x18001d02b  jnz     short loc_18001D034
0x18001d02d  mov     eax, 8007000Eh
0x18001d032  jmp     short loc_18001D056
0x18001d034  movups  xmm0, xmmword ptr cs:_GUID_3cdad9ea_8120_43e9_bc6b_83410d558d0a.Data1
0x18001d03b  movdqu  xmmword ptr [rax], xmm0
0x18001d03f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001d046  movdqu  xmmword ptr [rax+10h], xmm1
0x18001d04b  mov     dword ptr [rdi], 2
0x18001d051  mov     [rbx], rax
0x18001d054  xor     eax, eax
0x18001d056  mov     rbx, [rsp+28h+arg_0]
0x18001d05b  add     rsp, 20h
0x18001d05f  pop     rdi
0x18001d060  retn
```
