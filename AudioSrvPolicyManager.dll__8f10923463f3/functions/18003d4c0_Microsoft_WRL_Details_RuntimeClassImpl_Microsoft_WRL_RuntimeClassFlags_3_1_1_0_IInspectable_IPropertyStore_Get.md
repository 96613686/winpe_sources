# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable,IPropertyStore>::GetIids(ulong *,_GUID * *)

- ea: `0x18003d4c0`
- end: `0x18003d52d`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIInspectable@@UIPropertyStore@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003d4c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d4e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d4e2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable,IPropertyStore>::GetIids(
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
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18003d4c0  mov     [rsp+arg_0], rbx
0x18003d4c5  push    rdi
0x18003d4c6  sub     rsp, 20h
0x18003d4ca  mov     qword ptr [r8], 0
0x18003d4d1  mov     ecx, 30h ; '0'; cb
0x18003d4d6  mov     dword ptr [rdx], 0
0x18003d4dc  mov     rbx, r8
0x18003d4df  mov     rdi, rdx
0x18003d4e2  call    cs:__imp_CoTaskMemAlloc
0x18003d4e8  test    rax, rax
0x18003d4eb  jnz     short loc_18003D4F4
0x18003d4ed  mov     eax, 8007000Eh
0x18003d4f2  jmp     short loc_18003D522
0x18003d4f4  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18003d4fb  movdqu  xmmword ptr [rax], xmm0
0x18003d4ff  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18003d506  movdqu  xmmword ptr [rax+10h], xmm1
0x18003d50b  movups  xmm0, xmmword ptr cs:_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99.Data1
0x18003d512  movdqu  xmmword ptr [rax+20h], xmm0
0x18003d517  mov     dword ptr [rdi], 3
0x18003d51d  mov     [rbx], rax
0x18003d520  xor     eax, eax
0x18003d522  mov     rbx, [rsp+28h+arg_0]
0x18003d527  add     rsp, 20h
0x18003d52b  pop     rdi
0x18003d52c  retn
```
