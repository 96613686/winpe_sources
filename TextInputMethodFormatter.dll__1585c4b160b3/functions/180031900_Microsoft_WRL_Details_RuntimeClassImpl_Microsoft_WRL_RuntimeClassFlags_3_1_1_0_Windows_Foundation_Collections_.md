# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::IIterable<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>>::GetIids(ulong *,_GUID * *)

- ea: `0x180031900`
- end: `0x18003196d`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$IVector@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@Collections@Foundation@Windows@@U?$IIterable@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@567@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031980`
- `0x1800319b0`

## callees

- `0x180031900`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031922`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031922`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::IIterable<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>>::GetIids(
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
  *v5 = GUID_dc06b535_c796_55e7_8e9a_3a777678e965;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_8fc554b0_77bc_5d33_b598_a48a3f6dc233;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180031900  mov     [rsp+arg_0], rbx
0x180031905  push    rdi
0x180031906  sub     rsp, 20h
0x18003190a  mov     qword ptr [r8], 0
0x180031911  mov     ecx, 30h ; '0'; cb
0x180031916  mov     dword ptr [rdx], 0
0x18003191c  mov     rbx, r8
0x18003191f  mov     rdi, rdx
0x180031922  call    cs:__imp_CoTaskMemAlloc
0x180031928  test    rax, rax
0x18003192b  jnz     short loc_180031934
0x18003192d  mov     eax, 8007000Eh
0x180031932  jmp     short loc_180031962
0x180031934  movups  xmm0, xmmword ptr cs:_GUID_dc06b535_c796_55e7_8e9a_3a777678e965.Data1
0x18003193b  movdqu  xmmword ptr [rax], xmm0
0x18003193f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180031946  movdqu  xmmword ptr [rax+10h], xmm1
0x18003194b  movups  xmm0, xmmword ptr cs:_GUID_8fc554b0_77bc_5d33_b598_a48a3f6dc233.Data1
0x180031952  movdqu  xmmword ptr [rax+20h], xmm0
0x180031957  mov     dword ptr [rdi], 3
0x18003195d  mov     [rbx], rax
0x180031960  xor     eax, eax
0x180031962  mov     rbx, [rsp+28h+arg_0]
0x180031967  add     rsp, 20h
0x18003196b  pop     rdi
0x18003196c  retn
```
