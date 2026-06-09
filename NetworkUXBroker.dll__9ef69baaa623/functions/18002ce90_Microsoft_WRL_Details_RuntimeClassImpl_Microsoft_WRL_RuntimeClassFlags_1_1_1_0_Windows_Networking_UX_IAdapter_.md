# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IAdapter,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18002ce90`
- end: `0x18002ceef`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAdapter@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002a848`
- `0x18002ce90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ceb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ceb2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IAdapter,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Networking::UX::IAdapter,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18002ce90  mov     [rsp+arg_0], rbx
0x18002ce95  push    rdi
0x18002ce96  sub     rsp, 20h
0x18002ce9a  mov     qword ptr [r8], 0
0x18002cea1  mov     ecx, 20h ; ' '; cb
0x18002cea6  mov     dword ptr [rdx], 0
0x18002ceac  mov     rbx, r8
0x18002ceaf  mov     rdi, rdx
0x18002ceb2  call    cs:__imp_CoTaskMemAlloc
0x18002ceb8  mov     r8, rax
0x18002cebb  test    rax, rax
0x18002cebe  jnz     short loc_18002CEC7
0x18002cec0  mov     eax, 8007000Eh
0x18002cec5  jmp     short loc_18002CEE4
0x18002cec7  lea     rdx, [rsp+28h+arg_8]
0x18002cecc  mov     [rsp+28h+arg_8], 0
0x18002ced4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIAdapter@UX@Networking@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Networking::UX::IAdapter,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18002ced9  mov     dword ptr [rdi], 2
0x18002cedf  xor     eax, eax
0x18002cee1  mov     [rbx], r8
0x18002cee4  mov     rbx, [rsp+28h+arg_0]
0x18002cee9  add     rsp, 20h
0x18002ceed  pop     rdi
0x18002ceee  retn
```
