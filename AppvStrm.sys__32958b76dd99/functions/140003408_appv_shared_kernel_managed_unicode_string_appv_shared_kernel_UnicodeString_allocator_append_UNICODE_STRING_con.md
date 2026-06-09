# appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::append(_UNICODE_STRING const &)

- ea: `0x140003408`
- end: `0x1400034f4`
- name: `?append@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, const void **)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140002a14`
- `0x140002cb8`
- `0x140002de4`
- `0x14000bbd4`
- `0x140014a50`

## callees

- `0x140003408`
- `0x140003770`
- `0x140015c00`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400034dc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400034dc`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::append(
        struct _UNICODE_STRING *a1,
        const void **a2)
{
  int v2; // eax
  __int64 v5; // rsi
  __int64 v6; // rdx
  __int64 result; // rax
  PWSTR Buffer; // rcx
  unsigned int v9; // ecx
  __int16 v10; // dx
  __int16 v11; // ax
  PWSTR v12; // r8
  __int16 v13; // dx
  unsigned __int16 v14; // ax
  const WCHAR *v15; // rdx
  unsigned int v16; // ecx
  __int16 v17; // dx
  __int16 v18; // ax

  v2 = *(unsigned __int16 *)a2;
  if ( !(_WORD)v2 )
    return 0;
  v5 = *(unsigned int *)&a1->Length;
  v6 = (unsigned int)(v5 + v2);
  if ( (_DWORD)v5 )
  {
    result = appv::shared::kernel::buffer<appv::shared::kernel::UnicodeString_allocator>::resize(a1, v6);
    Buffer = (PWSTR)((char *)a1->Buffer + v5 - 2);
  }
  else
  {
    result = appv::shared::kernel::buffer<appv::shared::kernel::UnicodeString_allocator>::resize(
               a1,
               (unsigned int)(v6 + 2));
    Buffer = a1->Buffer;
  }
  if ( (int)result >= 0 )
  {
    memmove(Buffer, a2[1], *(unsigned __int16 *)a2);
    if ( *(_DWORD *)&a1->Length )
    {
      v9 = *(_DWORD *)&a1->Length >> 1;
      if ( v9 > 0xFFFF )
        v10 = -1;
      else
        v10 = *(_DWORD *)&a1->Length >> 1;
      v11 = 0;
      v12 = 0;
      if ( v9 <= 0xFFFF )
        v11 = v10;
      if ( v11 )
        v12 = a1->Buffer;
      if ( v9 > 0xFFFF )
        v13 = -1;
      else
        v13 = *(_DWORD *)&a1->Length >> 1;
      v14 = 0;
      if ( v9 <= 0xFFFF )
        v14 = v13;
      v12[v14 - 1] = 0;
    }
    if ( *(_DWORD *)&a1->Length )
    {
      v16 = *(_DWORD *)&a1->Length >> 1;
      if ( v16 > 0xFFFF )
        v17 = -1;
      else
        v17 = *(_DWORD *)&a1->Length >> 1;
      v18 = 0;
      if ( v16 <= 0xFFFF )
        v18 = v17;
      v15 = 0;
      if ( v18 )
        v15 = a1->Buffer;
    }
    else
    {
      v15 = 0;
    }
    RtlInitUnicodeString(a1 + 1, v15);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140003408  push    rbx
0x14000340a  push    rbp
0x14000340b  push    rsi
0x14000340c  push    rdi
0x14000340d  sub     rsp, 28h
0x140003411  movzx   eax, word ptr [rdx]
0x140003414  xor     ebp, ebp
0x140003416  mov     rdi, rdx
0x140003419  mov     rbx, rcx
0x14000341c  test    ax, ax
0x14000341f  jz      loc_1400034E8
0x140003425  mov     esi, [rcx]
0x140003427  lea     edx, [rsi+rax]
0x14000342a  test    esi, esi
0x14000342c  jnz     short loc_14000343C
0x14000342e  add     edx, 2
0x140003431  call    ?resize@?$buffer@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::UnicodeString_allocator>::resize(ulong)
0x140003436  mov     rcx, [rbx+8]
0x14000343a  jmp     short loc_14000344C
0x14000343c  call    ?resize@?$buffer@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::UnicodeString_allocator>::resize(ulong)
0x140003441  mov     rcx, [rbx+8]
0x140003445  add     rcx, 0FFFFFFFFFFFFFFFEh
0x140003449  add     rcx, rsi; void *
0x14000344c  mov     edx, eax
0x14000344e  test    eax, eax
0x140003450  jns     short loc_140003457
0x140003452  jmp     loc_1400034EA
0x140003457  movzx   r8d, word ptr [rdi]; Size
0x14000345b  mov     rdx, [rdi+8]; Src
0x14000345f  call    memmove
0x140003464  mov     ecx, [rbx]
0x140003466  mov     r9d, 0FFFFh
0x14000346c  test    ecx, ecx
0x14000346e  jz      short loc_1400034AD
0x140003470  shr     ecx, 1
0x140003472  cmp     ecx, r9d
0x140003475  ja      short loc_14000347C
0x140003477  movzx   edx, cx
0x14000347a  jmp     short loc_14000347F
0x14000347c  mov     edx, r9d
0x14000347f  mov     eax, ebp
0x140003481  mov     r8, rbp
0x140003484  cmovbe  ax, dx
0x140003488  test    ax, ax
0x14000348b  jz      short loc_140003491
0x14000348d  mov     r8, [rbx+8]
0x140003491  cmp     ecx, r9d
0x140003494  ja      short loc_14000349B
0x140003496  movzx   edx, cx
0x140003499  jmp     short loc_14000349E
0x14000349b  mov     edx, r9d
0x14000349e  mov     eax, ebp
0x1400034a0  cmovbe  ax, dx
0x1400034a4  movzx   ecx, ax
0x1400034a7  mov     [r8+rcx*2-2], bp
0x1400034ad  mov     ecx, [rbx]
0x1400034af  test    ecx, ecx
0x1400034b1  jnz     short loc_1400034B7
0x1400034b3  xor     edx, edx
0x1400034b5  jmp     short loc_1400034D8
0x1400034b7  shr     ecx, 1
0x1400034b9  cmp     ecx, r9d
0x1400034bc  ja      short loc_1400034C3
0x1400034be  movzx   edx, cx
0x1400034c1  jmp     short loc_1400034C6
0x1400034c3  mov     edx, r9d
0x1400034c6  mov     eax, ebp
0x1400034c8  cmovbe  ax, dx
0x1400034cc  mov     rdx, rbp
0x1400034cf  test    ax, ax
0x1400034d2  jz      short loc_1400034D8
0x1400034d4  mov     rdx, [rbx+8]; SourceString
0x1400034d8  lea     rcx, [rbx+10h]; DestinationString
0x1400034dc  call    cs:__imp_RtlInitUnicodeString
0x1400034e3  nop     dword ptr [rax+rax+00h]
0x1400034e8  xor     eax, eax
0x1400034ea  add     rsp, 28h
0x1400034ee  pop     rdi
0x1400034ef  pop     rsi
0x1400034f0  pop     rbp
0x1400034f1  pop     rbx
0x1400034f2  retn
```
