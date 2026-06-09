# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextOperationCompletedEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001d620`
- end: `0x18001d681`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextOperationCompletedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001d620`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d642`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d642`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextOperationCompletedEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_c177b8fb_372a_4e50_a52e_d56a1535b3cd;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001d620  mov     [rsp+arg_0], rbx
0x18001d625  push    rdi
0x18001d626  sub     rsp, 20h
0x18001d62a  mov     qword ptr [r8], 0
0x18001d631  mov     ecx, 20h ; ' '; cb
0x18001d636  mov     dword ptr [rdx], 0
0x18001d63c  mov     rbx, r8
0x18001d63f  mov     rdi, rdx
0x18001d642  call    cs:__imp_CoTaskMemAlloc
0x18001d648  test    rax, rax
0x18001d64b  jnz     short loc_18001D654
0x18001d64d  mov     eax, 8007000Eh
0x18001d652  jmp     short loc_18001D676
0x18001d654  movups  xmm0, xmmword ptr cs:_GUID_c177b8fb_372a_4e50_a52e_d56a1535b3cd.Data1
0x18001d65b  movdqu  xmmword ptr [rax], xmm0
0x18001d65f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001d666  movdqu  xmmword ptr [rax+10h], xmm1
0x18001d66b  mov     dword ptr [rdi], 2
0x18001d671  mov     [rbx], rax
0x18001d674  xor     eax, eax
0x18001d676  mov     rbx, [rsp+28h+arg_0]
0x18001d67b  add     rsp, 20h
0x18001d67f  pop     rdi
0x18001d680  retn
```
