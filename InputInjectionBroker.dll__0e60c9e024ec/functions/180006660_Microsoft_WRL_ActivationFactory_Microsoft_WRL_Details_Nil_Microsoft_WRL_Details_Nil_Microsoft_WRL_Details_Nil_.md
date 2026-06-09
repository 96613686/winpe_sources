# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x180006660`
- end: `0x1800066b5`
- name: `?GetIids@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `85`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006660`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006682`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006682`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
0x180006660  mov     [rsp+arg_0], rbx
0x180006665  push    rdi
0x180006666  sub     rsp, 20h
0x18000666a  mov     qword ptr [r8], 0
0x180006671  mov     ecx, 10h; cb
0x180006676  mov     dword ptr [rdx], 0
0x18000667c  mov     rbx, r8
0x18000667f  mov     rdi, rdx
0x180006682  call    cs:__imp_CoTaskMemAlloc
0x180006688  test    rax, rax
0x18000668b  jnz     short loc_180006694
0x18000668d  mov     eax, 8007000Eh
0x180006692  jmp     short loc_1800066AA
0x180006694  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000669b  movdqu  xmmword ptr [rax], xmm0
0x18000669f  mov     dword ptr [rdi], 1
0x1800066a5  mov     [rbx], rax
0x1800066a8  xor     eax, eax
0x1800066aa  mov     rbx, [rsp+28h+arg_0]
0x1800066af  add     rsp, 20h
0x1800066b3  pop     rdi
0x1800066b4  retn
```
