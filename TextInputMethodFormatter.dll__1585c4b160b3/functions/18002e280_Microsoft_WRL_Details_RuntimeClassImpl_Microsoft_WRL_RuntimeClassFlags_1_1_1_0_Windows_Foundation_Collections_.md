# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputViewOcclusion>>::GetIids(ulong *,_GUID * *)

- ea: `0x18002e280`
- end: `0x18002e2e1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@URemoteTextCoreInputViewOcclusion@Remote@Text@Internal@UI@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002e280`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e2a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e2a2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputViewOcclusion>>::GetIids(
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
  *v5 = GUID_79bce525_b73a_5daa_a33e_5fd3237d383b;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18002e280  mov     [rsp+arg_0], rbx
0x18002e285  push    rdi
0x18002e286  sub     rsp, 20h
0x18002e28a  mov     qword ptr [r8], 0
0x18002e291  mov     ecx, 20h ; ' '; cb
0x18002e296  mov     dword ptr [rdx], 0
0x18002e29c  mov     rbx, r8
0x18002e29f  mov     rdi, rdx
0x18002e2a2  call    cs:__imp_CoTaskMemAlloc
0x18002e2a8  test    rax, rax
0x18002e2ab  jnz     short loc_18002E2B4
0x18002e2ad  mov     eax, 8007000Eh
0x18002e2b2  jmp     short loc_18002E2D6
0x18002e2b4  movups  xmm0, xmmword ptr cs:_GUID_79bce525_b73a_5daa_a33e_5fd3237d383b.Data1
0x18002e2bb  movdqu  xmmword ptr [rax], xmm0
0x18002e2bf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18002e2c6  movdqu  xmmword ptr [rax+10h], xmm1
0x18002e2cb  mov     dword ptr [rdi], 2
0x18002e2d1  mov     [rbx], rax
0x18002e2d4  xor     eax, eax
0x18002e2d6  mov     rbx, [rsp+28h+arg_0]
0x18002e2db  add     rsp, 20h
0x18002e2df  pop     rdi
0x18002e2e0  retn
```
