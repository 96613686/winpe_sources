# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextTextUpdatingEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001d8c0`
- end: `0x18001d921`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextTextUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001d8c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d8e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d8e2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextTextUpdatingEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_891a94a0_6faf_4a94_a17c_122f633c2751;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001d8c0  mov     [rsp+arg_0], rbx
0x18001d8c5  push    rdi
0x18001d8c6  sub     rsp, 20h
0x18001d8ca  mov     qword ptr [r8], 0
0x18001d8d1  mov     ecx, 20h ; ' '; cb
0x18001d8d6  mov     dword ptr [rdx], 0
0x18001d8dc  mov     rbx, r8
0x18001d8df  mov     rdi, rdx
0x18001d8e2  call    cs:__imp_CoTaskMemAlloc
0x18001d8e8  test    rax, rax
0x18001d8eb  jnz     short loc_18001D8F4
0x18001d8ed  mov     eax, 8007000Eh
0x18001d8f2  jmp     short loc_18001D916
0x18001d8f4  movups  xmm0, xmmword ptr cs:_GUID_891a94a0_6faf_4a94_a17c_122f633c2751.Data1
0x18001d8fb  movdqu  xmmword ptr [rax], xmm0
0x18001d8ff  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001d906  movdqu  xmmword ptr [rax+10h], xmm1
0x18001d90b  mov     dword ptr [rdi], 2
0x18001d911  mov     [rbx], rax
0x18001d914  xor     eax, eax
0x18001d916  mov     rbx, [rsp+28h+arg_0]
0x18001d91b  add     rsp, 20h
0x18001d91f  pop     rdi
0x18001d920  retn
```
