# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::IIterable<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>::GetIids(ulong *,_GUID * *)

- ea: `0x180031870`
- end: `0x1800318dd`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IVectorView@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@Collections@Foundation@Windows@@U?$IIterable@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@567@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800318f0`
- `0x180031990`

## callees

- `0x180031870`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031892`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031892`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::IIterable<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>::GetIids(
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
  *v5 = GUID_a963b8e4_d7f5_578c_a299_a5fe08d40a55;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_8fc554b0_77bc_5d33_b598_a48a3f6dc233;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180031870  mov     [rsp+arg_0], rbx
0x180031875  push    rdi
0x180031876  sub     rsp, 20h
0x18003187a  mov     qword ptr [r8], 0
0x180031881  mov     ecx, 30h ; '0'; cb
0x180031886  mov     dword ptr [rdx], 0
0x18003188c  mov     rbx, r8
0x18003188f  mov     rdi, rdx
0x180031892  call    cs:__imp_CoTaskMemAlloc
0x180031898  test    rax, rax
0x18003189b  jnz     short loc_1800318A4
0x18003189d  mov     eax, 8007000Eh
0x1800318a2  jmp     short loc_1800318D2
0x1800318a4  movups  xmm0, xmmword ptr cs:_GUID_a963b8e4_d7f5_578c_a299_a5fe08d40a55.Data1
0x1800318ab  movdqu  xmmword ptr [rax], xmm0
0x1800318af  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800318b6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800318bb  movups  xmm0, xmmword ptr cs:_GUID_8fc554b0_77bc_5d33_b598_a48a3f6dc233.Data1
0x1800318c2  movdqu  xmmword ptr [rax+20h], xmm0
0x1800318c7  mov     dword ptr [rdi], 3
0x1800318cd  mov     [rbx], rax
0x1800318d0  xor     eax, eax
0x1800318d2  mov     rbx, [rsp+28h+arg_0]
0x1800318d7  add     rsp, 20h
0x1800318db  pop     rdi
0x1800318dc  retn
```
