# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IAdapterProperties>::GetIids(ulong *,_GUID * *)

- ea: `0x18003c740`
- end: `0x18003c7a1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAdapterProperties@UX@Networking@Windows@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003c740`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c762`

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
0x18003c740  mov     [rsp+arg_0], rbx
0x18003c745  push    rdi
0x18003c746  sub     rsp, 20h
0x18003c74a  mov     qword ptr [r8], 0
0x18003c751  mov     ecx, 20h ; ' '; cb
0x18003c756  mov     dword ptr [rdx], 0
0x18003c75c  mov     rbx, r8
0x18003c75f  mov     rdi, rdx
0x18003c762  call    cs:__imp_CoTaskMemAlloc
0x18003c768  test    rax, rax
0x18003c76b  jnz     short loc_18003C774
0x18003c76d  mov     eax, 8007000Eh
0x18003c772  jmp     short loc_18003C796
0x18003c774  movups  xmm0, xmmword ptr cs:_GUID_93652a8b_62a3_41b3_a265_927b6ce7c07e.Data1
0x18003c77b  movdqu  xmmword ptr [rax], xmm0
0x18003c77f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18003c786  movdqu  xmmword ptr [rax+10h], xmm1
0x18003c78b  mov     dword ptr [rdi], 2
0x18003c791  mov     [rbx], rax
0x18003c794  xor     eax, eax
0x18003c796  mov     rbx, [rsp+28h+arg_0]
0x18003c79b  add     rsp, 20h
0x18003c79f  pop     rdi
0x18003c7a0  retn
```
