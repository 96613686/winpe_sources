# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextNonComponentUIHostDetectedEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001d540`
- end: `0x18001d5a1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextNonComponentUIHostDetectedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001d540`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d562`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d562`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextNonComponentUIHostDetectedEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_fa1b5c62_da6f_4785_8345_423f13311cd1;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001d540  mov     [rsp+arg_0], rbx
0x18001d545  push    rdi
0x18001d546  sub     rsp, 20h
0x18001d54a  mov     qword ptr [r8], 0
0x18001d551  mov     ecx, 20h ; ' '; cb
0x18001d556  mov     dword ptr [rdx], 0
0x18001d55c  mov     rbx, r8
0x18001d55f  mov     rdi, rdx
0x18001d562  call    cs:__imp_CoTaskMemAlloc
0x18001d568  test    rax, rax
0x18001d56b  jnz     short loc_18001D574
0x18001d56d  mov     eax, 8007000Eh
0x18001d572  jmp     short loc_18001D596
0x18001d574  movups  xmm0, xmmword ptr cs:_GUID_fa1b5c62_da6f_4785_8345_423f13311cd1.Data1
0x18001d57b  movdqu  xmmword ptr [rax], xmm0
0x18001d57f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001d586  movdqu  xmmword ptr [rax+10h], xmm1
0x18001d58b  mov     dword ptr [rdi], 2
0x18001d591  mov     [rbx], rax
0x18001d594  xor     eax, eax
0x18001d596  mov     rbx, [rsp+28h+arg_0]
0x18001d59b  add     rsp, 20h
0x18001d59f  pop     rdi
0x18001d5a0  retn
```
