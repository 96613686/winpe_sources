# appv::shared::kernel::sid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(void *,ulong)

- ea: `0x18000ab2c`
- end: `0x18000abcc`
- name: `?assign@?$sid@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJPEAXK@Z`
- size: `160`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000e960`
- `0x180013b78`
- `0x180019624`

## callees

- `0x18000ab2c`
- `0x18000e8d4`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x18000ab64`
- `ntoskrnl!RtlLengthSid` at `0x18000ab64`
- `ntoskrnl!RtlCopySid` at `0x18000ab94`
- `ntoskrnl!RtlCopySid` at `0x18000ab94`
- `ntoskrnl!RtlValidSid` at `0x18000ab51`
- `ntoskrnl!RtlValidSid` at `0x18000ab51`

## pseudocode

```c
NTSTATUS __fastcall appv::shared::kernel::sid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
        __int64 a1,
        void *a2,
        unsigned int a3)
{
  NTSTATUS result; // eax

  if ( !a2 || !a3 || !RtlValidSid(a2) || RtlLengthSid(a2) != a3 )
    return -1073741704;
  result = appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(a1, a3);
  if ( (result & 0xC0000000) != 0xC0000000 )
  {
    result = RtlCopySid(*(_DWORD *)a1, *(PSID *)(a1 + 8), a2);
    if ( (result & 0xC0000000) != 0xC0000000 )
      *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 8);
  }
  return result;
}

```

## disassembly

```asm
0x18000ab2c  mov     [rsp+arg_0], rbx
0x18000ab31  mov     [rsp+arg_8], rsi
0x18000ab36  push    rdi
0x18000ab37  sub     rsp, 20h
0x18000ab3b  mov     esi, r8d
0x18000ab3e  mov     rdi, rdx
0x18000ab41  mov     rbx, rcx
0x18000ab44  test    rdx, rdx
0x18000ab47  jz      short loc_18000ABB6
0x18000ab49  test    r8d, r8d
0x18000ab4c  jz      short loc_18000ABB6
0x18000ab4e  mov     rcx, rdx; Sid
0x18000ab51  call    cs:__imp_RtlValidSid
0x18000ab58  nop     dword ptr [rax+rax+00h]
0x18000ab5d  test    al, al
0x18000ab5f  jz      short loc_18000ABB6
0x18000ab61  mov     rcx, rdi; Sid
0x18000ab64  call    cs:__imp_RtlLengthSid
0x18000ab6b  nop     dword ptr [rax+rax+00h]
0x18000ab70  cmp     eax, esi
0x18000ab72  jnz     short loc_18000ABB6
0x18000ab74  mov     edx, esi
0x18000ab76  mov     rcx, rbx
0x18000ab79  call    ?resize@?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(ulong)
0x18000ab7e  mov     esi, 0C0000000h
0x18000ab83  mov     ecx, eax
0x18000ab85  and     ecx, esi
0x18000ab87  cmp     ecx, esi
0x18000ab89  jz      short loc_18000ABBB
0x18000ab8b  mov     rdx, [rbx+8]; DestinationSid
0x18000ab8f  mov     r8, rdi; SourceSid
0x18000ab92  mov     ecx, [rbx]; DestinationSidLength
0x18000ab94  call    cs:__imp_RtlCopySid
0x18000ab9b  nop     dword ptr [rax+rax+00h]
0x18000aba0  mov     ecx, eax
0x18000aba2  mov     edx, eax
0x18000aba4  and     ecx, esi
0x18000aba6  cmp     ecx, esi
0x18000aba8  jz      short loc_18000ABBB
0x18000abaa  mov     rax, [rbx+8]
0x18000abae  mov     [rbx+10h], rax
0x18000abb2  mov     eax, edx
0x18000abb4  jmp     short loc_18000ABBB
0x18000abb6  mov     eax, 0C0000078h
0x18000abbb  mov     rbx, [rsp+28h+arg_0]
0x18000abc0  mov     rsi, [rsp+28h+arg_8]
0x18000abc5  add     rsp, 20h
0x18000abc9  pop     rdi
0x18000abca  retn
```
