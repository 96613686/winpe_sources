# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputProfile>>::GetIids(ulong *,_GUID * *)

- ea: `0x180052e20`
- end: `0x180052e81`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@URemoteTextCoreInputProfile@Remote@Text@Internal@UI@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180052e20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052e42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052e42`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputProfile>>::GetIids(
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
  *v5 = GUID_ce8e0dab_72b0_51a7_93a1_371fea0d92da;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180052e20  mov     [rsp+arg_0], rbx
0x180052e25  push    rdi
0x180052e26  sub     rsp, 20h
0x180052e2a  mov     qword ptr [r8], 0
0x180052e31  mov     ecx, 20h ; ' '; cb
0x180052e36  mov     dword ptr [rdx], 0
0x180052e3c  mov     rbx, r8
0x180052e3f  mov     rdi, rdx
0x180052e42  call    cs:__imp_CoTaskMemAlloc
0x180052e48  test    rax, rax
0x180052e4b  jnz     short loc_180052E54
0x180052e4d  mov     eax, 8007000Eh
0x180052e52  jmp     short loc_180052E76
0x180052e54  movups  xmm0, xmmword ptr cs:_GUID_ce8e0dab_72b0_51a7_93a1_371fea0d92da.Data1
0x180052e5b  movdqu  xmmword ptr [rax], xmm0
0x180052e5f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180052e66  movdqu  xmmword ptr [rax+10h], xmm1
0x180052e6b  mov     dword ptr [rdi], 2
0x180052e71  mov     [rbx], rax
0x180052e74  xor     eax, eax
0x180052e76  mov     rbx, [rsp+28h+arg_0]
0x180052e7b  add     rsp, 20h
0x180052e7f  pop     rdi
0x180052e80  retn
```
