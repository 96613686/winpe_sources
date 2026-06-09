# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputViewOcclusion>,Windows::Foundation::Collections::IIterable<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputViewOcclusion>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>>::GetIids(ulong *,_GUID * *)

- ea: `0x18002e380`
- end: `0x18002e3ed`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$IVector@URemoteTextCoreInputViewOcclusion@Remote@Text@Internal@UI@Windows@@@Collections@Foundation@Windows@@U?$IIterable@URemoteTextCoreInputViewOcclusion@Remote@Text@Internal@UI@Windows@@@567@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e400`
- `0x18002e430`

## callees

- `0x18002e380`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e3a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e3a2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputViewOcclusion>,Windows::Foundation::Collections::IIterable<Windows::UI::Internal::Text::Remote::RemoteTextCoreInputViewOcclusion>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>>::GetIids(
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
  *v5 = GUID_7b33b54e_d7c8_5193_956b_647af4d3438c;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_91c120c3_c105_5555_9793_c4fb54e1901f;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18002e380  mov     [rsp+arg_0], rbx
0x18002e385  push    rdi
0x18002e386  sub     rsp, 20h
0x18002e38a  mov     qword ptr [r8], 0
0x18002e391  mov     ecx, 30h ; '0'; cb
0x18002e396  mov     dword ptr [rdx], 0
0x18002e39c  mov     rbx, r8
0x18002e39f  mov     rdi, rdx
0x18002e3a2  call    cs:__imp_CoTaskMemAlloc
0x18002e3a8  test    rax, rax
0x18002e3ab  jnz     short loc_18002E3B4
0x18002e3ad  mov     eax, 8007000Eh
0x18002e3b2  jmp     short loc_18002E3E2
0x18002e3b4  movups  xmm0, xmmword ptr cs:_GUID_7b33b54e_d7c8_5193_956b_647af4d3438c.Data1
0x18002e3bb  movdqu  xmmword ptr [rax], xmm0
0x18002e3bf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18002e3c6  movdqu  xmmword ptr [rax+10h], xmm1
0x18002e3cb  movups  xmm0, xmmword ptr cs:_GUID_91c120c3_c105_5555_9793_c4fb54e1901f.Data1
0x18002e3d2  movdqu  xmmword ptr [rax+20h], xmm0
0x18002e3d7  mov     dword ptr [rdi], 3
0x18002e3dd  mov     [rbx], rax
0x18002e3e0  xor     eax, eax
0x18002e3e2  mov     rbx, [rsp+28h+arg_0]
0x18002e3e7  add     rsp, 20h
0x18002e3eb  pop     rdi
0x18002e3ec  retn
```
