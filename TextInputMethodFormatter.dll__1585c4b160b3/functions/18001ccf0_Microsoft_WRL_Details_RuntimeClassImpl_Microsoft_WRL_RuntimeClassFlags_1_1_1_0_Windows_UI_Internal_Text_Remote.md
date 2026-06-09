# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextCharacterGeneratedEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001ccf0`
- end: `0x18001cd51`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextCharacterGeneratedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ccf0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cd12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cd12`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextCharacterGeneratedEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_51030886_1398_405a_9635_00e069be8b8a;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001ccf0  mov     [rsp+arg_0], rbx
0x18001ccf5  push    rdi
0x18001ccf6  sub     rsp, 20h
0x18001ccfa  mov     qword ptr [r8], 0
0x18001cd01  mov     ecx, 20h ; ' '; cb
0x18001cd06  mov     dword ptr [rdx], 0
0x18001cd0c  mov     rbx, r8
0x18001cd0f  mov     rdi, rdx
0x18001cd12  call    cs:__imp_CoTaskMemAlloc
0x18001cd18  test    rax, rax
0x18001cd1b  jnz     short loc_18001CD24
0x18001cd1d  mov     eax, 8007000Eh
0x18001cd22  jmp     short loc_18001CD46
0x18001cd24  movups  xmm0, xmmword ptr cs:_GUID_51030886_1398_405a_9635_00e069be8b8a.Data1
0x18001cd2b  movdqu  xmmword ptr [rax], xmm0
0x18001cd2f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001cd36  movdqu  xmmword ptr [rax+10h], xmm1
0x18001cd3b  mov     dword ptr [rdi], 2
0x18001cd41  mov     [rbx], rax
0x18001cd44  xor     eax, eax
0x18001cd46  mov     rbx, [rsp+28h+arg_0]
0x18001cd4b  add     rsp, 20h
0x18001cd4f  pop     rdi
0x18001cd50  retn
```
