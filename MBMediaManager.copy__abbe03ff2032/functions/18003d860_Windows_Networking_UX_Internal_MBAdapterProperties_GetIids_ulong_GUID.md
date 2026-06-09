# Windows::Networking::UX::Internal::MBAdapterProperties::GetIids(ulong *,_GUID * *)

- ea: `0x18003d860`
- end: `0x18003d8cd`
- name: `?GetIids@MBAdapterProperties@Internal@UX@Networking@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::MBAdapterProperties *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003d8e0`

## callees

- `0x18003d860`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d882`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::MBAdapterProperties::GetIids(
        Windows::Networking::UX::Internal::MBAdapterProperties *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_93652a8b_62a3_41b3_a265_927b6ce7c07e;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_f0e3338a_7fac_5557_926d_147d4b3d9e10;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18003d860  mov     [rsp+arg_0], rbx
0x18003d865  push    rdi
0x18003d866  sub     rsp, 20h
0x18003d86a  mov     qword ptr [r8], 0
0x18003d871  mov     ecx, 30h ; '0'; cb
0x18003d876  mov     dword ptr [rdx], 0
0x18003d87c  mov     rbx, r8
0x18003d87f  mov     rdi, rdx
0x18003d882  call    cs:__imp_CoTaskMemAlloc
0x18003d888  test    rax, rax
0x18003d88b  jnz     short loc_18003D894
0x18003d88d  mov     eax, 8007000Eh
0x18003d892  jmp     short loc_18003D8C2
0x18003d894  movups  xmm0, xmmword ptr cs:_GUID_93652a8b_62a3_41b3_a265_927b6ce7c07e.Data1
0x18003d89b  movdqu  xmmword ptr [rax], xmm0
0x18003d89f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18003d8a6  movdqu  xmmword ptr [rax+10h], xmm1
0x18003d8ab  movups  xmm0, xmmword ptr cs:_GUID_f0e3338a_7fac_5557_926d_147d4b3d9e10.Data1
0x18003d8b2  movdqu  xmmword ptr [rax+20h], xmm0
0x18003d8b7  mov     dword ptr [rdi], 3
0x18003d8bd  mov     [rbx], rax
0x18003d8c0  xor     eax, eax
0x18003d8c2  mov     rbx, [rsp+28h+arg_0]
0x18003d8c7  add     rsp, 20h
0x18003d8cb  pop     rdi
0x18003d8cc  retn
```
