# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(ulong *,_GUID * *)

- ea: `0x18001e540`
- end: `0x18001e595`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@$00$0A@UIActivationFactory@@VNil@Details@23@V5623@V5623@V5623@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001e540`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e562`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e562`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(
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
0x18001e540  mov     [rsp+arg_0], rbx
0x18001e545  push    rdi
0x18001e546  sub     rsp, 20h
0x18001e54a  mov     qword ptr [r8], 0
0x18001e551  mov     ecx, 10h; cb
0x18001e556  mov     dword ptr [rdx], 0
0x18001e55c  mov     rbx, r8
0x18001e55f  mov     rdi, rdx
0x18001e562  call    cs:__imp_CoTaskMemAlloc
0x18001e568  test    rax, rax
0x18001e56b  jnz     short loc_18001E574
0x18001e56d  mov     eax, 8007000Eh
0x18001e572  jmp     short loc_18001E58A
0x18001e574  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18001e57b  movdqu  xmmword ptr [rax], xmm0
0x18001e57f  mov     dword ptr [rdi], 1
0x18001e585  mov     [rbx], rax
0x18001e588  xor     eax, eax
0x18001e58a  mov     rbx, [rsp+28h+arg_0]
0x18001e58f  add     rsp, 20h
0x18001e593  pop     rdi
0x18001e594  retn
```
