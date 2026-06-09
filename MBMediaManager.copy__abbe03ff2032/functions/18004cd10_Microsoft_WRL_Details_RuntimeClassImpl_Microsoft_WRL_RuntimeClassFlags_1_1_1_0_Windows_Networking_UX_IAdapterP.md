# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IAdapterProperties>::GetIids(ulong *,_GUID * *)

- ea: `0x18004cd10`
- end: `0x18004cd71`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAdapterProperties@UX@Networking@Windows@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18004cd10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004cd32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004cd32`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IAdapterProperties>::GetIids(
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
  *v5 = GUID_93652a8b_62a3_41b3_a265_927b6ce7c07e;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18004cd10  mov     [rsp+arg_0], rbx
0x18004cd15  push    rdi
0x18004cd16  sub     rsp, 20h
0x18004cd1a  mov     qword ptr [r8], 0
0x18004cd21  mov     ecx, 20h ; ' '; cb
0x18004cd26  mov     dword ptr [rdx], 0
0x18004cd2c  mov     rbx, r8
0x18004cd2f  mov     rdi, rdx
0x18004cd32  call    cs:__imp_CoTaskMemAlloc
0x18004cd38  test    rax, rax
0x18004cd3b  jnz     short loc_18004CD44
0x18004cd3d  mov     eax, 8007000Eh
0x18004cd42  jmp     short loc_18004CD66
0x18004cd44  movups  xmm0, xmmword ptr cs:_GUID_93652a8b_62a3_41b3_a265_927b6ce7c07e.Data1
0x18004cd4b  movdqu  xmmword ptr [rax], xmm0
0x18004cd4f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18004cd56  movdqu  xmmword ptr [rax+10h], xmm1
0x18004cd5b  mov     dword ptr [rdi], 2
0x18004cd61  mov     [rbx], rax
0x18004cd64  xor     eax, eax
0x18004cd66  mov     rbx, [rsp+28h+arg_0]
0x18004cd6b  add     rsp, 20h
0x18004cd6f  pop     rdi
0x18004cd70  retn
```
