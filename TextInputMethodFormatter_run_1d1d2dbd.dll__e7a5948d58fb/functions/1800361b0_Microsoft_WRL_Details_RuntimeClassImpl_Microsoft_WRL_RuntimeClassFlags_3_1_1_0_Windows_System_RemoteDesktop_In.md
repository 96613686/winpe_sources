# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::System::RemoteDesktop::Input::IRemoteTextConnection,Windows::System::RemoteDesktop::Input::IRemoteTextConnection2,IMessageProxyReconnectAdapterOwner,Windows::Foundation::IClosable>::GetIids(ulong *,_GUID * *)

- ea: `0x1800361b0`
- end: `0x180036235`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIRemoteTextConnection@Input@RemoteDesktop@System@Windows@@UIRemoteTextConnection2@5678@UIMessageProxyReconnectAdapterOwner@@UIClosable@Foundation@8@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `133`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180036240`
- `0x180036250`
- `0x180036260`

## callees

- `0x1800361b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800361d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800361d2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::System::RemoteDesktop::Input::IRemoteTextConnection,Windows::System::RemoteDesktop::Input::IRemoteTextConnection2,IMessageProxyReconnectAdapterOwner,Windows::Foundation::IClosable>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x50u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_4e7bb02a_183e_5e66_b5e4_3e6e5c570cf1;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_05f99345_84c8_56c5_934f_73ea00f8c2d5;
  v5[3] = GUID_f40c54d9_03bb_449c_83a5_6796bd8f9dc5;
  v5[4] = GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e;
  *a2 = 5;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800361b0  mov     [rsp+arg_0], rbx
0x1800361b5  push    rdi
0x1800361b6  sub     rsp, 20h
0x1800361ba  mov     qword ptr [r8], 0
0x1800361c1  mov     ecx, 50h ; 'P'; cb
0x1800361c6  mov     dword ptr [rdx], 0
0x1800361cc  mov     rbx, r8
0x1800361cf  mov     rdi, rdx
0x1800361d2  call    cs:__imp_CoTaskMemAlloc
0x1800361d8  test    rax, rax
0x1800361db  jnz     short loc_1800361E4
0x1800361dd  mov     eax, 8007000Eh
0x1800361e2  jmp     short loc_18003622A
0x1800361e4  movups  xmm0, xmmword ptr cs:_GUID_4e7bb02a_183e_5e66_b5e4_3e6e5c570cf1.Data1
0x1800361eb  movdqu  xmmword ptr [rax], xmm0
0x1800361ef  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800361f6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800361fb  movups  xmm0, xmmword ptr cs:_GUID_05f99345_84c8_56c5_934f_73ea00f8c2d5.Data1
0x180036202  movdqu  xmmword ptr [rax+20h], xmm0
0x180036207  movups  xmm1, xmmword ptr cs:_GUID_f40c54d9_03bb_449c_83a5_6796bd8f9dc5.Data1
0x18003620e  movdqu  xmmword ptr [rax+30h], xmm1
0x180036213  movups  xmm0, xmmword ptr cs:_GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e.Data1
0x18003621a  movdqu  xmmword ptr [rax+40h], xmm0
0x18003621f  mov     dword ptr [rdi], 5
0x180036225  mov     [rbx], rax
0x180036228  xor     eax, eax
0x18003622a  mov     rbx, [rsp+28h+arg_0]
0x18003622f  add     rsp, 20h
0x180036233  pop     rdi
0x180036234  retn
```
