# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x18000a9d0`
- end: `0x18000aa25`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@U?$CloakedIid@UIValueUnmarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000aa30`

## callees

- `0x18000a9d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a9f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a9f2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x10u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  *a2 = 1;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000a9d0  mov     [rsp+arg_0], rbx
0x18000a9d5  push    rdi
0x18000a9d6  sub     rsp, 20h
0x18000a9da  mov     qword ptr [r8], 0
0x18000a9e1  mov     ecx, 10h; cb
0x18000a9e6  mov     dword ptr [rdx], 0
0x18000a9ec  mov     rbx, r8
0x18000a9ef  mov     rdi, rdx
0x18000a9f2  call    cs:__imp_CoTaskMemAlloc
0x18000a9f8  test    rax, rax
0x18000a9fb  jnz     short loc_18000AA04
0x18000a9fd  mov     eax, 8007000Eh
0x18000aa02  jmp     short loc_18000AA1A
0x18000aa04  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000aa0b  movdqu  xmmword ptr [rax], xmm0
0x18000aa0f  mov     dword ptr [rdi], 1
0x18000aa15  mov     [rbx], rax
0x18000aa18  xor     eax, eax
0x18000aa1a  mov     rbx, [rsp+28h+arg_0]
0x18000aa1f  add     rsp, 20h
0x18000aa23  pop     rdi
0x18000aa24  retn
```
