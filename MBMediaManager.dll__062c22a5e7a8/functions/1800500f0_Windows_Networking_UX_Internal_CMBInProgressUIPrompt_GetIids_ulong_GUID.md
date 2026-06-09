# Windows::Networking::UX::Internal::CMBInProgressUIPrompt::GetIids(ulong *,_GUID * *)

- ea: `0x1800500f0`
- end: `0x18005015d`
- name: `?GetIids@CMBInProgressUIPrompt@Internal@UX@Networking@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CMBInProgressUIPrompt *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180050170`

## callees

- `0x1800500f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050112`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050112`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CMBInProgressUIPrompt::GetIids(
        Windows::Networking::UX::Internal::CMBInProgressUIPrompt *this,
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
  v5[2] = GUID_dc2dca6f_669b_4378_b5db_68345ce65756;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800500f0  mov     [rsp+arg_0], rbx
0x1800500f5  push    rdi
0x1800500f6  sub     rsp, 20h
0x1800500fa  mov     qword ptr [r8], 0
0x180050101  mov     ecx, 30h ; '0'; cb
0x180050106  mov     dword ptr [rdx], 0
0x18005010c  mov     rbx, r8
0x18005010f  mov     rdi, rdx
0x180050112  call    cs:__imp_CoTaskMemAlloc
0x180050118  test    rax, rax
0x18005011b  jnz     short loc_180050124
0x18005011d  mov     eax, 8007000Eh
0x180050122  jmp     short loc_180050152
0x180050124  movups  xmm0, xmmword ptr cs:_GUID_70dba485_cd56_4f15_9f82_86b1460e09a8.Data1
0x18005012b  movdqu  xmmword ptr [rax], xmm0
0x18005012f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180050136  movdqu  xmmword ptr [rax+10h], xmm1
0x18005013b  movups  xmm0, xmmword ptr cs:_GUID_dc2dca6f_669b_4378_b5db_68345ce65756.Data1
0x180050142  movdqu  xmmword ptr [rax+20h], xmm0
0x180050147  mov     dword ptr [rdi], 3
0x18005014d  mov     [rbx], rax
0x180050150  xor     eax, eax
0x180050152  mov     rbx, [rsp+28h+arg_0]
0x180050157  add     rsp, 20h
0x18005015b  pop     rdi
0x18005015c  retn
```
