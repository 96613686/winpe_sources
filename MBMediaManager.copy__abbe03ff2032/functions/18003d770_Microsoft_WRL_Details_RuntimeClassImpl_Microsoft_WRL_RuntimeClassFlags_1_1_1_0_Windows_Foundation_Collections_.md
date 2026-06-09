# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Networking::UX::MbOperatorInfo>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18003d770`
- end: `0x18003d7cf`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@UMbOperatorInfo@UX@Networking@Windows@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003d3b8`
- `0x18003d770`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d792`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d792`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Networking::UX::MbOperatorInfo>,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Networking::UX::MbOperatorInfo>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18003d770  mov     [rsp+arg_0], rbx
0x18003d775  push    rdi
0x18003d776  sub     rsp, 20h
0x18003d77a  mov     qword ptr [r8], 0
0x18003d781  mov     ecx, 20h ; ' '; cb
0x18003d786  mov     dword ptr [rdx], 0
0x18003d78c  mov     rbx, r8
0x18003d78f  mov     rdi, rdx
0x18003d792  call    cs:__imp_CoTaskMemAlloc
0x18003d798  mov     r8, rax
0x18003d79b  test    rax, rax
0x18003d79e  jnz     short loc_18003D7A7
0x18003d7a0  mov     eax, 8007000Eh
0x18003d7a5  jmp     short loc_18003D7C4
0x18003d7a7  lea     rdx, [rsp+28h+arg_8]
0x18003d7ac  mov     [rsp+28h+arg_8], 0
0x18003d7b4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$IIterator@UMbOperatorInfo@UX@Networking@Windows@@@Collections@Foundation@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Networking::UX::MbOperatorInfo>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18003d7b9  mov     dword ptr [rdi], 2
0x18003d7bf  xor     eax, eax
0x18003d7c1  mov     [rbx], r8
0x18003d7c4  mov     rbx, [rsp+28h+arg_0]
0x18003d7c9  add     rsp, 20h
0x18003d7cd  pop     rdi
0x18003d7ce  retn
```
