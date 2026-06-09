# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>::GetIids(ulong *,_GUID * *)

- ea: `0x180031800`
- end: `0x180031861`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180031800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031822`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031822`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>::GetIids(
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
  *v5 = GUID_3c08dbe7_11c3_56d9_bafc_da794d923aba;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180031800  mov     [rsp+arg_0], rbx
0x180031805  push    rdi
0x180031806  sub     rsp, 20h
0x18003180a  mov     qword ptr [r8], 0
0x180031811  mov     ecx, 20h ; ' '; cb
0x180031816  mov     dword ptr [rdx], 0
0x18003181c  mov     rbx, r8
0x18003181f  mov     rdi, rdx
0x180031822  call    cs:__imp_CoTaskMemAlloc
0x180031828  test    rax, rax
0x18003182b  jnz     short loc_180031834
0x18003182d  mov     eax, 8007000Eh
0x180031832  jmp     short loc_180031856
0x180031834  movups  xmm0, xmmword ptr cs:_GUID_3c08dbe7_11c3_56d9_bafc_da794d923aba.Data1
0x18003183b  movdqu  xmmword ptr [rax], xmm0
0x18003183f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180031846  movdqu  xmmword ptr [rax+10h], xmm1
0x18003184b  mov     dword ptr [rdi], 2
0x180031851  mov     [rbx], rax
0x180031854  xor     eax, eax
0x180031856  mov     rbx, [rsp+28h+arg_0]
0x18003185b  add     rsp, 20h
0x18003185f  pop     rdi
0x180031860  retn
```
