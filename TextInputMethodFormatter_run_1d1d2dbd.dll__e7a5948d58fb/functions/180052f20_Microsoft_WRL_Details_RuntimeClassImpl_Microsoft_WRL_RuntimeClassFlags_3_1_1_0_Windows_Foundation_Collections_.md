# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputProfile>,Windows::Foundation::Collections::IIterable<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputProfile>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>>::GetIids(ulong *,_GUID * *)

- ea: `0x180052f20`
- end: `0x180052f8d`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$IVector@URemoteTextCoreInputProfile@Remote@Text@Internal@UI@Windows@@@Collections@Foundation@Windows@@U?$IIterable@URemoteTextCoreInputProfile@Remote@Text@Internal@UI@Windows@@@567@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180052fa0`
- `0x180052fd0`

## callees

- `0x180052f20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052f42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052f42`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputProfile>,Windows::Foundation::Collections::IIterable<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputProfile>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>>::GetIids(
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
  *v5 = GUID_003546ac_fdd9_5a8c_8202_c2aa66821567;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_1d81c34d_075e_52bd_9994_7a9ab877cd6d;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180052f20  mov     [rsp+arg_0], rbx
0x180052f25  push    rdi
0x180052f26  sub     rsp, 20h
0x180052f2a  mov     qword ptr [r8], 0
0x180052f31  mov     ecx, 30h ; '0'; cb
0x180052f36  mov     dword ptr [rdx], 0
0x180052f3c  mov     rbx, r8
0x180052f3f  mov     rdi, rdx
0x180052f42  call    cs:__imp_CoTaskMemAlloc
0x180052f48  test    rax, rax
0x180052f4b  jnz     short loc_180052F54
0x180052f4d  mov     eax, 8007000Eh
0x180052f52  jmp     short loc_180052F82
0x180052f54  movups  xmm0, xmmword ptr cs:_GUID_003546ac_fdd9_5a8c_8202_c2aa66821567.Data1
0x180052f5b  movdqu  xmmword ptr [rax], xmm0
0x180052f5f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180052f66  movdqu  xmmword ptr [rax+10h], xmm1
0x180052f6b  movups  xmm0, xmmword ptr cs:_GUID_1d81c34d_075e_52bd_9994_7a9ab877cd6d.Data1
0x180052f72  movdqu  xmmword ptr [rax+20h], xmm0
0x180052f77  mov     dword ptr [rdi], 3
0x180052f7d  mov     [rbx], rax
0x180052f80  xor     eax, eax
0x180052f82  mov     rbx, [rsp+28h+arg_0]
0x180052f87  add     rsp, 20h
0x180052f8b  pop     rdi
0x180052f8c  retn
```
