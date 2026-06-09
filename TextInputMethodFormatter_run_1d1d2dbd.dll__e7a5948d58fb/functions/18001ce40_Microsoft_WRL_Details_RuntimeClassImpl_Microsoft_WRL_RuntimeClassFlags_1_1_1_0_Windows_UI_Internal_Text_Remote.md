# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001ce40`
- end: `0x18001cea1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextCompositionUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ce40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ce62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ce62`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_314d5ad9_f1b5_4f93_b132_ec9c754c15d1;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001ce40  mov     [rsp+arg_0], rbx
0x18001ce45  push    rdi
0x18001ce46  sub     rsp, 20h
0x18001ce4a  mov     qword ptr [r8], 0
0x18001ce51  mov     ecx, 20h ; ' '; cb
0x18001ce56  mov     dword ptr [rdx], 0
0x18001ce5c  mov     rbx, r8
0x18001ce5f  mov     rdi, rdx
0x18001ce62  call    cs:__imp_CoTaskMemAlloc
0x18001ce68  test    rax, rax
0x18001ce6b  jnz     short loc_18001CE74
0x18001ce6d  mov     eax, 8007000Eh
0x18001ce72  jmp     short loc_18001CE96
0x18001ce74  movups  xmm0, xmmword ptr cs:_GUID_314d5ad9_f1b5_4f93_b132_ec9c754c15d1.Data1
0x18001ce7b  movdqu  xmmword ptr [rax], xmm0
0x18001ce7f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001ce86  movdqu  xmmword ptr [rax+10h], xmm1
0x18001ce8b  mov     dword ptr [rdi], 2
0x18001ce91  mov     [rbx], rax
0x18001ce94  xor     eax, eax
0x18001ce96  mov     rbx, [rsp+28h+arg_0]
0x18001ce9b  add     rsp, 20h
0x18001ce9f  pop     rdi
0x18001cea0  retn
```
