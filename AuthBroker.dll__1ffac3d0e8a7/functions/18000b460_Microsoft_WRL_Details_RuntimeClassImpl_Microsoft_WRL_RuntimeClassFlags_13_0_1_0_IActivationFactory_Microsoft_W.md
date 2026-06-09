# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(ulong *,_GUID * *)

- ea: `0x18000b460`
- end: `0x18000b4b5`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@$00$0A@UIActivationFactory@@VNil@Details@23@V5623@V5623@V5623@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `85`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil> *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000b460`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b482`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b482`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil> *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x10u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  *iidCount = 1;
  *iids = v5;
  return 0;
}

```

## disassembly

```asm
0x18000b460  mov     [rsp+arg_0], rbx
0x18000b465  push    rdi
0x18000b466  sub     rsp, 20h
0x18000b46a  mov     qword ptr [iids], 0
0x18000b471  mov     ecx, 10h; cb
0x18000b476  mov     dword ptr [iidCount], 0
0x18000b47c  mov     rbx, iids
0x18000b47f  mov     rdi, iidCount
0x18000b482  call    cs:__imp_CoTaskMemAlloc
0x18000b488  test    rax, rax
0x18000b48b  jnz     short loc_18000B494
0x18000b48d  mov     eax, 8007000Eh
0x18000b492  jmp     short loc_18000B4AA
0x18000b494  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000b49b  movdqu  xmmword ptr [rax], xmm0
0x18000b49f  mov     dword ptr [rdi], 1
0x18000b4a5  mov     [rbx], rax
0x18000b4a8  xor     eax, eax
0x18000b4aa  mov     rbx, [rsp+28h+arg_0]
0x18000b4af  add     rsp, 20h
0x18000b4b3  pop     rdi
0x18000b4b4  retn
```
