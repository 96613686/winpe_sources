# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(ulong *,_GUID * *)

- ea: `0x1800181c0`
- end: `0x180018215`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@$00$0A@UIActivationFactory@@VNil@Details@23@V5623@V5623@V5623@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800181c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800181e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800181e2`

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
0x1800181c0  mov     [rsp+arg_0], rbx
0x1800181c5  push    rdi
0x1800181c6  sub     rsp, 20h
0x1800181ca  mov     qword ptr [r8], 0
0x1800181d1  mov     ecx, 10h; cb
0x1800181d6  mov     dword ptr [rdx], 0
0x1800181dc  mov     rbx, r8
0x1800181df  mov     rdi, rdx
0x1800181e2  call    cs:__imp_CoTaskMemAlloc
0x1800181e8  test    rax, rax
0x1800181eb  jnz     short loc_1800181F4
0x1800181ed  mov     eax, 8007000Eh
0x1800181f2  jmp     short loc_18001820A
0x1800181f4  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x1800181fb  movdqu  xmmword ptr [rax], xmm0
0x1800181ff  mov     dword ptr [rdi], 1
0x180018205  mov     [rbx], rax
0x180018208  xor     eax, eax
0x18001820a  mov     rbx, [rsp+28h+arg_0]
0x18001820f  add     rsp, 20h
0x180018213  pop     rdi
0x180018214  retn
```
