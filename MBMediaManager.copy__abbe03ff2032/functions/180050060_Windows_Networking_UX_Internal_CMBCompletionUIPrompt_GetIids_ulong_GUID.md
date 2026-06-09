# Windows::Networking::UX::Internal::CMBCompletionUIPrompt::GetIids(ulong *,_GUID * *)

- ea: `0x180050060`
- end: `0x1800500cd`
- name: `?GetIids@CMBCompletionUIPrompt@Internal@UX@Networking@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CMBCompletionUIPrompt *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800500e0`

## callees

- `0x180050060`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050082`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050082`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CMBCompletionUIPrompt::GetIids(
        Windows::Networking::UX::Internal::CMBCompletionUIPrompt *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_70dba485_cd56_4f15_9f82_86b1460e09a8;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_2e1f98f5_c3cc_4924_96e8_f7cea7698841;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180050060  mov     [rsp+arg_0], rbx
0x180050065  push    rdi
0x180050066  sub     rsp, 20h
0x18005006a  mov     qword ptr [r8], 0
0x180050071  mov     ecx, 30h ; '0'; cb
0x180050076  mov     dword ptr [rdx], 0
0x18005007c  mov     rbx, r8
0x18005007f  mov     rdi, rdx
0x180050082  call    cs:__imp_CoTaskMemAlloc
0x180050088  test    rax, rax
0x18005008b  jnz     short loc_180050094
0x18005008d  mov     eax, 8007000Eh
0x180050092  jmp     short loc_1800500C2
0x180050094  movups  xmm0, xmmword ptr cs:_GUID_70dba485_cd56_4f15_9f82_86b1460e09a8.Data1
0x18005009b  movdqu  xmmword ptr [rax], xmm0
0x18005009f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800500a6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800500ab  movups  xmm0, xmmword ptr cs:_GUID_2e1f98f5_c3cc_4924_96e8_f7cea7698841.Data1
0x1800500b2  movdqu  xmmword ptr [rax+20h], xmm0
0x1800500b7  mov     dword ptr [rdi], 3
0x1800500bd  mov     [rbx], rax
0x1800500c0  xor     eax, eax
0x1800500c2  mov     rbx, [rsp+28h+arg_0]
0x1800500c7  add     rsp, 20h
0x1800500cb  pop     rdi
0x1800500cc  retn
```
