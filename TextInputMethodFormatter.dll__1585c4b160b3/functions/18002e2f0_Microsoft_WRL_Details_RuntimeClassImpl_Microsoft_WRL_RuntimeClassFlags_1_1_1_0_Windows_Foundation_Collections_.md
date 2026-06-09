# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputViewOcclusion>,Windows::Foundation::Collections::IIterable<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputViewOcclusion>>::GetIids(ulong *,_GUID * *)

- ea: `0x18002e2f0`
- end: `0x18002e35d`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IVectorView@URemoteTextCoreInputViewOcclusion@Remote@Text@Internal@UI@Windows@@@Collections@Foundation@Windows@@U?$IIterable@URemoteTextCoreInputViewOcclusion@Remote@Text@Internal@UI@Windows@@@567@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e370`
- `0x18002e410`

## callees

- `0x18002e2f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e312`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e312`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputViewOcclusion>,Windows::Foundation::Collections::IIterable<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputViewOcclusion>>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_82bf9966_f9cb_5c50_9947_4a4c6e1e988b;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_91c120c3_c105_5555_9793_c4fb54e1901f;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18002e2f0  mov     [rsp+arg_0], rbx
0x18002e2f5  push    rdi
0x18002e2f6  sub     rsp, 20h
0x18002e2fa  mov     qword ptr [r8], 0
0x18002e301  mov     ecx, 30h ; '0'; cb
0x18002e306  mov     dword ptr [rdx], 0
0x18002e30c  mov     rbx, r8
0x18002e30f  mov     rdi, rdx
0x18002e312  call    cs:__imp_CoTaskMemAlloc
0x18002e318  test    rax, rax
0x18002e31b  jnz     short loc_18002E324
0x18002e31d  mov     eax, 8007000Eh
0x18002e322  jmp     short loc_18002E352
0x18002e324  movups  xmm0, xmmword ptr cs:_GUID_82bf9966_f9cb_5c50_9947_4a4c6e1e988b.Data1
0x18002e32b  movdqu  xmmword ptr [rax], xmm0
0x18002e32f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18002e336  movdqu  xmmword ptr [rax+10h], xmm1
0x18002e33b  movups  xmm0, xmmword ptr cs:_GUID_91c120c3_c105_5555_9793_c4fb54e1901f.Data1
0x18002e342  movdqu  xmmword ptr [rax+20h], xmm0
0x18002e347  mov     dword ptr [rdi], 3
0x18002e34d  mov     [rbx], rax
0x18002e350  xor     eax, eax
0x18002e352  mov     rbx, [rsp+28h+arg_0]
0x18002e357  add     rsp, 20h
0x18002e35b  pop     rdi
0x18002e35c  retn
```
