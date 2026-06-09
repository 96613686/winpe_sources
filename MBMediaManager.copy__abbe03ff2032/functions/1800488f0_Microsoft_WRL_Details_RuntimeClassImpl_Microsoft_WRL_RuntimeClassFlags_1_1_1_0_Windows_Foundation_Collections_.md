# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Networking::UX::NetworkMediaType>>::GetIids(ulong *,_GUID * *)

- ea: `0x1800488f0`
- end: `0x180048951`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@W4NetworkMediaType@UX@Networking@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800488f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180048912`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180048912`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<enum Windows::Networking::UX::NetworkMediaType>>::GetIids(
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
  *v5 = GUID_b6b89422_2717_512f_a610_ef9cebff447b;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800488f0  mov     [rsp+arg_0], rbx
0x1800488f5  push    rdi
0x1800488f6  sub     rsp, 20h
0x1800488fa  mov     qword ptr [r8], 0
0x180048901  mov     ecx, 20h ; ' '; cb
0x180048906  mov     dword ptr [rdx], 0
0x18004890c  mov     rbx, r8
0x18004890f  mov     rdi, rdx
0x180048912  call    cs:__imp_CoTaskMemAlloc
0x180048918  test    rax, rax
0x18004891b  jnz     short loc_180048924
0x18004891d  mov     eax, 8007000Eh
0x180048922  jmp     short loc_180048946
0x180048924  movups  xmm0, xmmword ptr cs:_GUID_b6b89422_2717_512f_a610_ef9cebff447b.Data1
0x18004892b  movdqu  xmmword ptr [rax], xmm0
0x18004892f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180048936  movdqu  xmmword ptr [rax+10h], xmm1
0x18004893b  mov     dword ptr [rdi], 2
0x180048941  mov     [rbx], rax
0x180048944  xor     eax, eax
0x180048946  mov     rbx, [rsp+28h+arg_0]
0x18004894b  add     rsp, 20h
0x18004894f  pop     rdi
0x180048950  retn
```
