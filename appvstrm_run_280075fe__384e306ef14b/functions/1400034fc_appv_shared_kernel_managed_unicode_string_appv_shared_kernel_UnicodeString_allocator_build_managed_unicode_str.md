# appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(_UNICODE_STRING const &)

- ea: `0x1400034fc`
- end: `0x140003649`
- name: `?build_managed_unicode_string@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z`
- size: `333`
- prototype: ``
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x140002cb8`
- `0x140002de4`
- `0x1400064e4`
- `0x1400065d0`
- `0x14000935c`
- `0x14000ad80`
- `0x14000bbd4`
- `0x14000bd34`
- `0x14000d718`
- `0x140012b18`
- `0x140013030`
- `0x140014a50`

## callees

- `0x1400034fc`
- `0x140003770`
- `0x140015c00`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140003554`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000362a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003554`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000362a`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(
        __int64 a1,
        unsigned __int16 *a2)
{
  const void *v2; // rbp
  signed int v4; // esi
  const WCHAR *v5; // rdx
  unsigned int v6; // ecx
  __int16 v7; // dx
  __int16 v8; // ax
  unsigned __int64 v9; // r14
  unsigned int v10; // eax
  unsigned __int16 v11; // cx
  unsigned int v12; // ecx
  __int16 v13; // dx
  __int16 v14; // ax
  __int64 v15; // r8
  __int16 v16; // dx
  unsigned __int16 v17; // ax
  const WCHAR *v18; // rdx
  unsigned int v19; // ecx
  __int16 v20; // dx
  __int16 v21; // ax

  v2 = (const void *)*((_QWORD *)a2 + 1);
  if ( v2 )
  {
    v9 = (unsigned __int64)*a2 >> 1;
    v10 = 2 * v9 + 2;
    if ( v10 > 0xFFFF )
      v11 = -1;
    else
      v11 = 2 * v9 + 2;
    v4 = v10 > 0xFFFF ? 0xC0000095 : 0;
    if ( v10 <= 0xFFFF )
    {
      v4 = appv::shared::kernel::buffer<appv::shared::kernel::UnicodeString_allocator>::resize(a1, v11);
      if ( v4 >= 0 )
      {
        memmove(*(void **)(a1 + 8), v2, 2 * v9);
        if ( *(_DWORD *)a1 )
        {
          v12 = *(_DWORD *)a1 >> 1;
          if ( v12 > 0xFFFF )
            v13 = -1;
          else
            v13 = *(_DWORD *)a1 >> 1;
          v14 = 0;
          v15 = 0;
          if ( v12 <= 0xFFFF )
            v14 = v13;
          if ( v14 )
            v15 = *(_QWORD *)(a1 + 8);
          if ( v12 > 0xFFFF )
            v16 = -1;
          else
            v16 = *(_DWORD *)a1 >> 1;
          v17 = 0;
          if ( v12 <= 0xFFFF )
            v17 = v16;
          *(_WORD *)(v15 + 2LL * v17 - 2) = 0;
        }
        if ( *(_DWORD *)a1 )
        {
          v19 = *(_DWORD *)a1 >> 1;
          if ( v19 > 0xFFFF )
            v20 = -1;
          else
            v20 = *(_DWORD *)a1 >> 1;
          v21 = 0;
          if ( v19 <= 0xFFFF )
            v21 = v20;
          v18 = 0;
          if ( v21 )
            v18 = *(const WCHAR **)(a1 + 8);
        }
        else
        {
          v18 = 0;
        }
        RtlInitUnicodeString((PUNICODE_STRING)(a1 + 16), v18);
        return 0;
      }
    }
  }
  else
  {
    v4 = appv::shared::kernel::buffer<appv::shared::kernel::UnicodeString_allocator>::resize(a1, 0);
    if ( *(_DWORD *)a1 )
    {
      v6 = *(_DWORD *)a1 >> 1;
      if ( v6 > 0xFFFF )
        v7 = -1;
      else
        v7 = *(_DWORD *)a1 >> 1;
      v8 = 0;
      if ( v6 <= 0xFFFF )
        v8 = v7;
      v5 = 0;
      if ( v8 )
        v5 = *(const WCHAR **)(a1 + 8);
    }
    else
    {
      v5 = 0;
    }
    RtlInitUnicodeString((PUNICODE_STRING)(a1 + 16), v5);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400034fc  push    rbx
0x1400034fe  push    rbp
0x1400034ff  push    rsi
0x140003500  push    rdi
0x140003501  push    r14
0x140003503  push    r15
0x140003505  sub     rsp, 28h
0x140003509  mov     rbp, [rdx+8]
0x14000350d  xor     r15d, r15d
0x140003510  mov     rdi, rcx
0x140003513  test    rbp, rbp
0x140003516  jnz     short loc_140003565
0x140003518  xor     edx, edx
0x14000351a  call    ?resize@?$buffer@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::UnicodeString_allocator>::resize(ulong)
0x14000351f  mov     ecx, [rdi]
0x140003521  mov     esi, eax
0x140003523  test    ecx, ecx
0x140003525  jnz     short loc_14000352B
0x140003527  xor     edx, edx
0x140003529  jmp     short loc_140003550
0x14000352b  shr     ecx, 1
0x14000352d  mov     ebx, 0FFFFh
0x140003532  cmp     ecx, ebx
0x140003534  ja      short loc_14000353B
0x140003536  movzx   edx, cx
0x140003539  jmp     short loc_14000353D
0x14000353b  mov     edx, ebx
0x14000353d  mov     eax, r15d
0x140003540  cmovbe  ax, dx
0x140003544  mov     rdx, r15
0x140003547  test    ax, ax
0x14000354a  jz      short loc_140003550
0x14000354c  mov     rdx, [rdi+8]; SourceString
0x140003550  lea     rcx, [rdi+10h]; DestinationString
0x140003554  call    cs:__imp_RtlInitUnicodeString
0x14000355b  nop     dword ptr [rax+rax+00h]
0x140003560  jmp     loc_140003639
0x140003565  movzx   r14d, word ptr [rdx]
0x140003569  mov     ebx, 0FFFFh
0x14000356e  shr     r14, 1
0x140003571  lea     eax, ds:2[r14*2]
0x140003579  cmp     eax, ebx
0x14000357b  ja      short loc_140003582
0x14000357d  movzx   ecx, ax
0x140003580  jmp     short loc_140003584
0x140003582  mov     ecx, ebx
0x140003584  cmp     ebx, eax
0x140003586  sbb     esi, esi
0x140003588  and     esi, 0C0000095h
0x14000358e  cmp     eax, ebx
0x140003590  ja      loc_140003639
0x140003596  movzx   edx, cx
0x140003599  mov     rcx, rdi
0x14000359c  call    ?resize@?$buffer@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::UnicodeString_allocator>::resize(ulong)
0x1400035a1  mov     esi, eax
0x1400035a3  test    eax, eax
0x1400035a5  js      loc_140003639
0x1400035ab  mov     rcx, [rdi+8]; void *
0x1400035af  lea     r8, [r14+r14]; Size
0x1400035b3  mov     rdx, rbp; Src
0x1400035b6  call    memmove
0x1400035bb  mov     ecx, [rdi]
0x1400035bd  test    ecx, ecx
0x1400035bf  jz      short loc_1400035FC
0x1400035c1  shr     ecx, 1
0x1400035c3  cmp     ecx, ebx
0x1400035c5  ja      short loc_1400035CC
0x1400035c7  movzx   edx, cx
0x1400035ca  jmp     short loc_1400035CE
0x1400035cc  mov     edx, ebx
0x1400035ce  mov     eax, r15d
0x1400035d1  mov     r8, r15
0x1400035d4  cmovbe  ax, dx
0x1400035d8  test    ax, ax
0x1400035db  jz      short loc_1400035E1
0x1400035dd  mov     r8, [rdi+8]
0x1400035e1  cmp     ecx, ebx
0x1400035e3  ja      short loc_1400035EA
0x1400035e5  movzx   edx, cx
0x1400035e8  jmp     short loc_1400035EC
0x1400035ea  mov     edx, ebx
0x1400035ec  mov     eax, r15d
0x1400035ef  cmovbe  ax, dx
0x1400035f3  movzx   ecx, ax
0x1400035f6  mov     [r8+rcx*2-2], r15w
0x1400035fc  mov     ecx, [rdi]
0x1400035fe  test    ecx, ecx
0x140003600  jnz     short loc_140003606
0x140003602  xor     edx, edx
0x140003604  jmp     short loc_140003626
0x140003606  shr     ecx, 1
0x140003608  cmp     ecx, ebx
0x14000360a  ja      short loc_140003611
0x14000360c  movzx   edx, cx
0x14000360f  jmp     short loc_140003613
0x140003611  mov     edx, ebx
0x140003613  mov     eax, r15d
0x140003616  cmovbe  ax, dx
0x14000361a  mov     rdx, r15
0x14000361d  test    ax, ax
0x140003620  jz      short loc_140003626
0x140003622  mov     rdx, [rdi+8]; SourceString
0x140003626  lea     rcx, [rdi+10h]; DestinationString
0x14000362a  call    cs:__imp_RtlInitUnicodeString
0x140003631  nop     dword ptr [rax+rax+00h]
0x140003636  mov     esi, r15d
0x140003639  mov     eax, esi
0x14000363b  add     rsp, 28h
0x14000363f  pop     r15
0x140003641  pop     r14
0x140003643  pop     rdi
0x140003644  pop     rsi
0x140003645  pop     rbp
0x140003646  pop     rbx
0x140003647  retn
```
