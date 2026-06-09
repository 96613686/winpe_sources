# archive_read_format_cpio_read_header

- ea: `0x1800ce5b0`
- end: `0x1800ce7f4`
- name: `archive_read_format_cpio_read_header`
- size: `580`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path`

## callees

- `0x180005914`
- `0x180005c7c`
- `0x180006c00`
- `0x18000e764`
- `0x1800b0a70`
- `0x1800ce5b0`
- `0x1800cf828`
- `0x1800ed464`
- `0x1800ed4c8`
- `0x180119962`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ce668`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ce744`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ce668`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ce744`

## string_xrefs

- `0x1800ce673`: `Can't allocate memory for Pathname`
- `0x1800ce6a8`: `Pathname can't be converted from %s to current locale.`
- `0x1800ce70a`: `Rejecting malformed cpio archive: symlink contents exceed 1 megabyte`
- `0x1800ce74f`: `Can't allocate memory for Linkname`
- `0x1800ce766`: `Linkname can't be converted from %s to current locale.`

## pseudocode

```c
__int64 __fastcall archive_read_format_cpio_read_header(__int64 a1, __int64 a2)
{
  __int64 *v2; // rax
  __int64 v5; // rdi
  __int64 v6; // rbp
  __int64 result; // rax
  unsigned int v8; // esi
  __int64 filter_ahead; // rax
  const char *v10; // r15
  const char *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax
  const char *v14; // rax
  __int64 v15; // [rsp+60h] [rbp+8h] BYREF
  __int64 v16; // [rsp+70h] [rbp+18h] BYREF

  v2 = *(__int64 **)(a1 + 2072);
  v15 = 0;
  v16 = 0;
  v5 = *v2;
  v6 = *(_QWORD *)(*v2 + 56);
  if ( !v6 )
  {
    if ( !*(_DWORD *)(v5 + 72) )
    {
      *(_QWORD *)(v5 + 64) = archive_string_default_conversion_for_read(a1);
      *(_DWORD *)(v5 + 72) = 1;
    }
    v6 = *(_QWORD *)(v5 + 64);
  }
  result = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, __int64 *))(v5 + 8))(a1, v5, a2, &v15, &v16);
  v8 = result;
  if ( (int)result >= -20 )
  {
    filter_ahead = _archive_read_filter_ahead(*(_QWORD *)(a1 + 632), v15 + v16, 0);
    v10 = (const char *)filter_ahead;
    if ( !filter_ahead )
      return 4294967266LL;
    if ( (unsigned int)archive_mstring_copy_mbs_len_l(a2 + 488, filter_ahead, v15, v6) )
    {
      if ( *(_DWORD *)_o__errno() == 12 )
      {
        archive_set_error(a1, 12, "Can't allocate memory for Pathname");
        return 4294967266LL;
      }
      v11 = (const char *)archive_string_conversion_charset_name(v6);
      archive_set_error(a1, 42, "Pathname can't be converted from %s to current locale.", v11);
      v8 = -20;
    }
    *(_QWORD *)(v5 + 40) = 0;
    _archive_read_filter_consume(*(_QWORD *)(a1 + 632), v15 + v16);
    if ( (*(_WORD *)(a2 + 1032) & 0xF000) == 0xA000 )
    {
      v12 = *(_QWORD *)(v5 + 24);
      if ( v12 > 0x100000 )
      {
        archive_set_error(a1, 12, "Rejecting malformed cpio archive: symlink contents exceed 1 megabyte");
        return 4294967266LL;
      }
      v13 = _archive_read_filter_ahead(*(_QWORD *)(a1 + 632), v12, 0);
      if ( !v13 )
        return 4294967266LL;
      if ( (unsigned int)archive_entry_copy_symlink_l(a2, v13, *(_QWORD *)(v5 + 24), v6) )
      {
        if ( *(_DWORD *)_o__errno() == 12 )
        {
          archive_set_error(a1, 12, "Can't allocate memory for Linkname");
          return 4294967266LL;
        }
        v14 = (const char *)archive_string_conversion_charset_name(v6);
        archive_set_error(a1, 42, "Linkname can't be converted from %s to current locale.", v14);
        v8 = -20;
      }
      _archive_read_filter_consume(*(_QWORD *)(a1 + 632), *(_QWORD *)(v5 + 24));
      *(_QWORD *)(v5 + 24) = 0;
    }
    if ( v15 == 11 && !strncmp_0(v10, "TRAILER!!!", 0xAu) )
    {
      *(_DWORD *)(a1 + 36) = 0;
      result = 1;
      *(_QWORD *)(a1 + 56) = 0;
      *(_QWORD *)(a1 + 40) = 0;
    }
    else
    {
      if ( (unsigned int)record_hardlink(a1, v5, a2) )
        return (unsigned int)-30;
      return v8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800ce5b0  mov     [rsp+arg_8], rbx
0x1800ce5b5  push    rbp
0x1800ce5b6  push    rsi
0x1800ce5b7  push    rdi
0x1800ce5b8  push    r14
0x1800ce5ba  push    r15
0x1800ce5bc  sub     rsp, 30h
0x1800ce5c0  mov     rax, [rcx+818h]
0x1800ce5c7  mov     r14, rdx
0x1800ce5ca  mov     [rsp+58h+arg_0], 0
0x1800ce5d3  mov     rbx, rcx
0x1800ce5d6  mov     [rsp+58h+arg_10], 0
0x1800ce5df  mov     rdi, [rax]
0x1800ce5e2  mov     rbp, [rdi+38h]
0x1800ce5e6  test    rbp, rbp
0x1800ce5e9  jnz     short loc_1800CE604
0x1800ce5eb  cmp     [rdi+48h], ebp
0x1800ce5ee  jnz     short loc_1800CE600
0x1800ce5f0  call    archive_string_default_conversion_for_read
0x1800ce5f5  mov     [rdi+40h], rax
0x1800ce5f9  mov     dword ptr [rdi+48h], 1
0x1800ce600  mov     rbp, [rdi+40h]
0x1800ce604  lea     rax, [rsp+58h+arg_10]
0x1800ce609  mov     r8, r14
0x1800ce60c  mov     [rsp+58h+var_38], rax
0x1800ce611  lea     r9, [rsp+58h+arg_0]
0x1800ce616  mov     rax, [rdi+8]
0x1800ce61a  mov     rdx, rdi
0x1800ce61d  mov     rcx, rbx
0x1800ce620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce625  mov     esi, eax
0x1800ce627  cmp     eax, 0FFFFFFECh
0x1800ce62a  jl      short loc_1800CE68C
0x1800ce62c  mov     rdx, [rsp+58h+arg_10]
0x1800ce631  xor     r8d, r8d
0x1800ce634  add     rdx, [rsp+58h+arg_0]
0x1800ce639  mov     rcx, [rbx+278h]
0x1800ce640  call    __archive_read_filter_ahead
0x1800ce645  mov     r15, rax
0x1800ce648  test    rax, rax
0x1800ce64b  jz      short loc_1800CE687
0x1800ce64d  mov     r8, [rsp+58h+arg_0]
0x1800ce652  lea     rcx, [r14+1E8h]
0x1800ce659  mov     r9, rbp
0x1800ce65c  mov     rdx, rax
0x1800ce65f  call    archive_mstring_copy_mbs_len_l
0x1800ce664  test    eax, eax
0x1800ce666  jz      short loc_1800CE6C1
0x1800ce668  call    cs:__imp__o__errno
0x1800ce66e  cmp     dword ptr [rax], 0Ch
0x1800ce671  jnz     short loc_1800CE69D
0x1800ce673  lea     r8, aCanTAllocateMe_24; "Can't allocate memory for Pathname"
0x1800ce67a  mov     edx, 0Ch
0x1800ce67f  mov     rcx, rbx
0x1800ce682  call    archive_set_error
0x1800ce687  mov     eax, 0FFFFFFE2h
0x1800ce68c  mov     rbx, [rsp+58h+arg_8]
0x1800ce691  add     rsp, 30h
0x1800ce695  pop     r15
0x1800ce697  pop     r14
0x1800ce699  pop     rdi
0x1800ce69a  pop     rsi
0x1800ce69b  pop     rbp
0x1800ce69c  retn
0x1800ce69d  mov     rcx, rbp
0x1800ce6a0  call    archive_string_conversion_charset_name
0x1800ce6a5  mov     r9, rax
0x1800ce6a8  lea     r8, aPathnameCanTBe; "Pathname can't be converted from %s to "...
0x1800ce6af  mov     edx, 2Ah ; '*'
0x1800ce6b4  mov     rcx, rbx
0x1800ce6b7  call    archive_set_error
0x1800ce6bc  mov     esi, 0FFFFFFECh
0x1800ce6c1  mov     qword ptr [rdi+28h], 0
0x1800ce6c9  mov     rdx, [rsp+58h+arg_10]
0x1800ce6ce  add     rdx, [rsp+58h+arg_0]
0x1800ce6d3  mov     rcx, [rbx+278h]
0x1800ce6da  call    __archive_read_filter_consume
0x1800ce6df  movzx   eax, word ptr [r14+408h]
0x1800ce6e7  mov     ecx, 0F000h
0x1800ce6ec  and     ax, cx
0x1800ce6ef  mov     ecx, 0A000h
0x1800ce6f4  cmp     ax, cx
0x1800ce6f7  jnz     loc_1800CE797
0x1800ce6fd  mov     rdx, [rdi+18h]
0x1800ce701  cmp     rdx, 100000h
0x1800ce708  jle     short loc_1800CE716
0x1800ce70a  lea     r8, aRejectingMalfo; "Rejecting malformed cpio archive: symli"...
0x1800ce711  jmp     loc_1800CE67A
0x1800ce716  mov     rcx, [rbx+278h]
0x1800ce71d  xor     r8d, r8d
0x1800ce720  call    __archive_read_filter_ahead
0x1800ce725  test    rax, rax
0x1800ce728  jz      loc_1800CE687
0x1800ce72e  mov     r8, [rdi+18h]
0x1800ce732  mov     r9, rbp
0x1800ce735  mov     rdx, rax
0x1800ce738  mov     rcx, r14
0x1800ce73b  call    _archive_entry_copy_symlink_l
0x1800ce740  test    eax, eax
0x1800ce742  jz      short loc_1800CE77F
0x1800ce744  call    cs:__imp__o__errno
0x1800ce74a  cmp     dword ptr [rax], 0Ch
0x1800ce74d  jnz     short loc_1800CE75B
0x1800ce74f  lea     r8, aCanTAllocateMe_15; "Can't allocate memory for Linkname"
0x1800ce756  jmp     loc_1800CE67A
0x1800ce75b  mov     rcx, rbp
0x1800ce75e  call    archive_string_conversion_charset_name
0x1800ce763  mov     r9, rax
0x1800ce766  lea     r8, aLinknameCanTBe; "Linkname can't be converted from %s to "...
0x1800ce76d  mov     edx, 2Ah ; '*'
0x1800ce772  mov     rcx, rbx
0x1800ce775  call    archive_set_error
0x1800ce77a  mov     esi, 0FFFFFFECh
0x1800ce77f  mov     rdx, [rdi+18h]
0x1800ce783  mov     rcx, [rbx+278h]
0x1800ce78a  call    __archive_read_filter_consume
0x1800ce78f  mov     qword ptr [rdi+18h], 0
0x1800ce797  cmp     [rsp+58h+arg_0], 0Bh
0x1800ce79d  jnz     short loc_1800CE7D5
0x1800ce79f  mov     r8d, 0Ah; MaxCount
0x1800ce7a5  lea     rdx, aTrailer; "TRAILER!!!"
0x1800ce7ac  mov     rcx, r15; Str1
0x1800ce7af  call    strncmp_0
0x1800ce7b4  test    eax, eax
0x1800ce7b6  jnz     short loc_1800CE7D5
0x1800ce7b8  mov     [rbx+24h], eax
0x1800ce7bb  mov     eax, 1
0x1800ce7c0  mov     qword ptr [rbx+38h], 0
0x1800ce7c8  mov     qword ptr [rbx+28h], 0
0x1800ce7d0  jmp     loc_1800CE68C
0x1800ce7d5  mov     r8, r14
0x1800ce7d8  mov     rdx, rdi
0x1800ce7db  mov     rcx, rbx
0x1800ce7de  call    record_hardlink
0x1800ce7e3  test    eax, eax
0x1800ce7e5  mov     ecx, 0FFFFFFE2h
0x1800ce7ea  cmovnz  esi, ecx
0x1800ce7ed  mov     eax, esi
0x1800ce7ef  jmp     loc_1800CE68C
```
