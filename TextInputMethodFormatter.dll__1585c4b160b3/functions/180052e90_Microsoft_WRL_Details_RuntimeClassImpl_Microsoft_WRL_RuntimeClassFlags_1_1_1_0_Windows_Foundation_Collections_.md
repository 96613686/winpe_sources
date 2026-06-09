# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputProfile>,Windows::Foundation::Collections::IIterable<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputProfile>>::GetIids(ulong *,_GUID * *)

- ea: `0x180052e90`
- end: `0x180052efd`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IVectorView@URemoteTextCoreInputProfile@Remote@Text@Internal@UI@Windows@@@Collections@Foundation@Windows@@U?$IIterable@URemoteTextCoreInputProfile@Remote@Text@Internal@UI@Windows@@@567@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180052f10`
- `0x180052fb0`

## callees

- `0x180052e90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052eb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052eb2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputProfile>,Windows::Foundation::Collections::IIterable<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputProfile>>::GetIids(
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
  *v5 = GUID_86a376cb_cb9b_5515_9442_ff8dd3b723a9;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_1d81c34d_075e_52bd_9994_7a9ab877cd6d;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180052e90  mov     [rsp+arg_0], rbx
0x180052e95  push    rdi
0x180052e96  sub     rsp, 20h
0x180052e9a  mov     qword ptr [r8], 0
0x180052ea1  mov     ecx, 30h ; '0'; cb
0x180052ea6  mov     dword ptr [rdx], 0
0x180052eac  mov     rbx, r8
0x180052eaf  mov     rdi, rdx
0x180052eb2  call    cs:__imp_CoTaskMemAlloc
0x180052eb8  test    rax, rax
0x180052ebb  jnz     short loc_180052EC4
0x180052ebd  mov     eax, 8007000Eh
0x180052ec2  jmp     short loc_180052EF2
0x180052ec4  movups  xmm0, xmmword ptr cs:_GUID_86a376cb_cb9b_5515_9442_ff8dd3b723a9.Data1
0x180052ecb  movdqu  xmmword ptr [rax], xmm0
0x180052ecf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180052ed6  movdqu  xmmword ptr [rax+10h], xmm1
0x180052edb  movups  xmm0, xmmword ptr cs:_GUID_1d81c34d_075e_52bd_9994_7a9ab877cd6d.Data1
0x180052ee2  movdqu  xmmword ptr [rax+20h], xmm0
0x180052ee7  mov     dword ptr [rdi], 3
0x180052eed  mov     [rbx], rax
0x180052ef0  xor     eax, eax
0x180052ef2  mov     rbx, [rsp+28h+arg_0]
0x180052ef7  add     rsp, 20h
0x180052efb  pop     rdi
0x180052efc  retn
```
