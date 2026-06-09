# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::IReference<Windows::Foundation::TimeSpan>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180039330`
- end: `0x18003938f`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IReference@UTimeSpan@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180039300`
- `0x180039330`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039352`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039352`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::IReference<Windows::Foundation::TimeSpan>,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::IReference<Windows::Foundation::TimeSpan>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x180039330  mov     [rsp+arg_0], rbx
0x180039335  push    rdi
0x180039336  sub     rsp, 20h
0x18003933a  mov     qword ptr [r8], 0
0x180039341  mov     ecx, 20h ; ' '; cb
0x180039346  mov     dword ptr [rdx], 0
0x18003934c  mov     rbx, r8
0x18003934f  mov     rdi, rdx
0x180039352  call    cs:__imp_CoTaskMemAlloc
0x180039358  mov     r8, rax
0x18003935b  test    rax, rax
0x18003935e  jnz     short loc_180039367
0x180039360  mov     eax, 8007000Eh
0x180039365  jmp     short loc_180039384
0x180039367  lea     rdx, [rsp+28h+arg_8]
0x18003936c  mov     [rsp+28h+arg_8], 0
0x180039374  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$IReference@UTimeSpan@Foundation@Windows@@@Foundation@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::IReference<Windows::Foundation::TimeSpan>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180039379  mov     dword ptr [rdi], 2
0x18003937f  xor     eax, eax
0x180039381  mov     [rbx], r8
0x180039384  mov     rbx, [rsp+28h+arg_0]
0x180039389  add     rsp, 20h
0x18003938d  pop     rdi
0x18003938e  retn
```
