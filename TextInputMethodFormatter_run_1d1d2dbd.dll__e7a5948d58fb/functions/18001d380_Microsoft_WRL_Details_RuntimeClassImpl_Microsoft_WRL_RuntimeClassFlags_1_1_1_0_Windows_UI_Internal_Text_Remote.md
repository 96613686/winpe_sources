# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextInputProfileUpdatingEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001d380`
- end: `0x18001d3e1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextInputProfileUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001d380`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d3a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d3a2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextInputProfileUpdatingEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_1c5c3e01_fa44_41f7_896a_3ed311cc30ce;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001d380  mov     [rsp+arg_0], rbx
0x18001d385  push    rdi
0x18001d386  sub     rsp, 20h
0x18001d38a  mov     qword ptr [r8], 0
0x18001d391  mov     ecx, 20h ; ' '; cb
0x18001d396  mov     dword ptr [rdx], 0
0x18001d39c  mov     rbx, r8
0x18001d39f  mov     rdi, rdx
0x18001d3a2  call    cs:__imp_CoTaskMemAlloc
0x18001d3a8  test    rax, rax
0x18001d3ab  jnz     short loc_18001D3B4
0x18001d3ad  mov     eax, 8007000Eh
0x18001d3b2  jmp     short loc_18001D3D6
0x18001d3b4  movups  xmm0, xmmword ptr cs:_GUID_1c5c3e01_fa44_41f7_896a_3ed311cc30ce.Data1
0x18001d3bb  movdqu  xmmword ptr [rax], xmm0
0x18001d3bf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001d3c6  movdqu  xmmword ptr [rax+10h], xmm1
0x18001d3cb  mov     dword ptr [rdi], 2
0x18001d3d1  mov     [rbx], rax
0x18001d3d4  xor     eax, eax
0x18001d3d6  mov     rbx, [rsp+28h+arg_0]
0x18001d3db  add     rsp, 20h
0x18001d3df  pop     rdi
0x18001d3e0  retn
```
