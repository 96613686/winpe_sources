# appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> const &)

- ea: `0x140003650`
- end: `0x1400036db`
- name: `?build_managed_unicode_string@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBV1234@@Z`
- size: `139`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400037fc`
- `0x14000be10`
- `0x140011a90`
- `0x140011f30`

## callees

- `0x140003650`
- `0x140003770`
- `0x140015c00`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400036c3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400036c3`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(
        __int64 a1,
        unsigned int *a2)
{
  size_t v2; // rdi
  const void *v4; // rsi
  unsigned int v5; // edi
  const WCHAR *v6; // rdx
  unsigned int v7; // ecx
  __int16 v8; // dx
  __int16 v9; // ax

  v2 = *a2;
  v4 = (const void *)*((_QWORD *)a2 + 1);
  if ( (appv::shared::kernel::buffer<appv::shared::kernel::UnicodeString_allocator>::resize(a1, v2) & 0xC0000000) == 0xC0000000 )
  {
    v5 = -1073741670;
  }
  else
  {
    memmove(*(void **)(a1 + 8), v4, v2);
    v5 = 0;
  }
  if ( *(_DWORD *)a1 )
  {
    v7 = *(_DWORD *)a1 >> 1;
    if ( v7 > 0xFFFF )
      v8 = -1;
    else
      v8 = *(_DWORD *)a1 >> 1;
    v9 = 0;
    if ( v7 <= 0xFFFF )
      v9 = v8;
    v6 = 0;
    if ( v9 )
      v6 = *(const WCHAR **)(a1 + 8);
  }
  else
  {
    v6 = 0;
  }
  RtlInitUnicodeString((PUNICODE_STRING)(a1 + 16), v6);
  return v5;
}

```

## disassembly

```asm
0x140003650  push    rbx
0x140003652  push    rbp
0x140003653  push    rsi
0x140003654  push    rdi
0x140003655  sub     rsp, 28h
0x140003659  mov     edi, [rdx]
0x14000365b  mov     rbx, rcx
0x14000365e  mov     rsi, [rdx+8]
0x140003662  mov     edx, edi
0x140003664  call    ?resize@?$buffer@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::UnicodeString_allocator>::resize(ulong)
0x140003669  mov     ecx, 0C0000000h
0x14000366e  xor     ebp, ebp
0x140003670  and     eax, ecx
0x140003672  cmp     eax, ecx
0x140003674  jnz     short loc_14000367D
0x140003676  mov     edi, 0C000009Ah
0x14000367b  jmp     short loc_14000368E
0x14000367d  mov     rcx, [rbx+8]; void *
0x140003681  mov     r8, rdi; Size
0x140003684  mov     rdx, rsi; Src
0x140003687  call    memmove
0x14000368c  mov     edi, ebp
0x14000368e  mov     ecx, [rbx]
0x140003690  test    ecx, ecx
0x140003692  jnz     short loc_140003698
0x140003694  xor     edx, edx
0x140003696  jmp     short loc_1400036BF
0x140003698  shr     ecx, 1
0x14000369a  mov     r8d, 0FFFFh
0x1400036a0  cmp     ecx, r8d
0x1400036a3  ja      short loc_1400036AA
0x1400036a5  movzx   edx, cx
0x1400036a8  jmp     short loc_1400036AD
0x1400036aa  mov     edx, r8d
0x1400036ad  mov     eax, ebp
0x1400036af  cmovbe  ax, dx
0x1400036b3  mov     rdx, rbp
0x1400036b6  test    ax, ax
0x1400036b9  jz      short loc_1400036BF
0x1400036bb  mov     rdx, [rbx+8]; SourceString
0x1400036bf  lea     rcx, [rbx+10h]; DestinationString
0x1400036c3  call    cs:__imp_RtlInitUnicodeString
0x1400036ca  nop     dword ptr [rax+rax+00h]
0x1400036cf  mov     eax, edi
0x1400036d1  add     rsp, 28h
0x1400036d5  pop     rdi
0x1400036d6  pop     rsi
0x1400036d7  pop     rbp
0x1400036d8  pop     rbx
0x1400036d9  retn
```
