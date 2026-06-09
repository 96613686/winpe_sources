# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::write_stored_string_tchar(wchar_t)

- ea: `0x18000d514`
- end: `0x18000d5fa`
- name: `?write_stored_string_tchar@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$standard_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_N_W@Z`
- size: `230`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cbfc`

## callees

- `0x18000d514`
- `0x18000d5fc`
- `0x180010690`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::write_stored_string_tchar(
        __int64 a1)
{
  const char *v2; // rsi
  int v3; // edi
  __crt_locale_pointers *v4; // r9
  int v5; // eax
  __int64 v6; // rcx
  wchar_t v7; // dx
  wchar_t DstCh; // [rsp+40h] [rbp+8h] BYREF

  if ( *(_BYTE *)(a1 + 84) || *(int *)(a1 + 80) <= 0 )
  {
    __crt_stdio_output::string_output_adapter<wchar_t>::write_string(
      a1 + 1128,
      *(_QWORD *)(a1 + 72),
      *(unsigned int *)(a1 + 80),
      a1 + 40,
      a1 + 16);
  }
  else
  {
    v2 = *(const char **)(a1 + 72);
    v3 = 0;
    while ( 1 )
    {
      v4 = *(__crt_locale_pointers **)(a1 + 8);
      DstCh = 0;
      v5 = mbtowc_l(&DstCh, v2, *((int *)v4->locinfo + 2), v4);
      if ( v5 <= 0 )
        break;
      v6 = *(_QWORD *)(a1 + 1128);
      v7 = DstCh;
      if ( *(_QWORD *)(v6 + 16) == *(_QWORD *)(v6 + 8) )
      {
        if ( *(_BYTE *)(v6 + 24) )
          ++*(_DWORD *)(a1 + 40);
        else
          *(_DWORD *)(a1 + 40) = -1;
      }
      else
      {
        ++*(_DWORD *)(a1 + 40);
        ++*(_QWORD *)(v6 + 16);
        ***(_WORD ***)(a1 + 1128) = v7;
        **(_QWORD **)(a1 + 1128) += 2LL;
      }
      v2 += v5;
      if ( ++v3 == *(_DWORD *)(a1 + 80) )
        return 1;
    }
    *(_DWORD *)(a1 + 40) = -1;
  }
  return 1;
}

```

## disassembly

```asm
0x18000d514  mov     [rsp+arg_8], rbx
0x18000d519  mov     [rsp+arg_10], rbp
0x18000d51e  mov     [rsp+arg_18], rsi
0x18000d523  push    rdi
0x18000d524  sub     rsp, 30h
0x18000d528  xor     ebp, ebp
0x18000d52a  mov     rbx, rcx
0x18000d52d  cmp     [rcx+54h], bpl
0x18000d531  jnz     loc_18000D5C2
0x18000d537  cmp     [rcx+50h], ebp
0x18000d53a  jle     loc_18000D5C2
0x18000d540  mov     rsi, [rcx+48h]
0x18000d544  mov     edi, ebp
0x18000d546  mov     r9, [rbx+8]; Locale
0x18000d54a  lea     rcx, [rsp+38h+DstCh]; DstCh
0x18000d54f  mov     [rsp+38h+DstCh], bp
0x18000d554  mov     rdx, rsi; SrcCh
0x18000d557  mov     rax, [r9]
0x18000d55a  movsxd  r8, dword ptr [rax+8]; SrcSizeInBytes
0x18000d55e  call    _mbtowc_l
0x18000d563  movsxd  r8, eax
0x18000d566  test    eax, eax
0x18000d568  jle     short loc_18000D5BC
0x18000d56a  mov     rcx, [rbx+468h]
0x18000d571  movzx   edx, [rsp+38h+DstCh]
0x18000d576  mov     rax, [rcx+8]
0x18000d57a  cmp     [rcx+10h], rax
0x18000d57e  jnz     short loc_18000D591
0x18000d580  cmp     [rcx+18h], bpl
0x18000d584  jz      short loc_18000D58B
0x18000d586  inc     dword ptr [rbx+28h]
0x18000d589  jmp     short loc_18000D5B0
0x18000d58b  or      dword ptr [rbx+28h], 0FFFFFFFFh
0x18000d58f  jmp     short loc_18000D5B0
0x18000d591  inc     dword ptr [rbx+28h]
0x18000d594  inc     qword ptr [rcx+10h]
0x18000d598  mov     rax, [rbx+468h]
0x18000d59f  mov     rcx, [rax]
0x18000d5a2  mov     [rcx], dx
0x18000d5a5  mov     rax, [rbx+468h]
0x18000d5ac  add     qword ptr [rax], 2
0x18000d5b0  add     rsi, r8
0x18000d5b3  inc     edi
0x18000d5b5  cmp     edi, [rbx+50h]
0x18000d5b8  jnz     short loc_18000D546
0x18000d5ba  jmp     short loc_18000D5E3
0x18000d5bc  or      dword ptr [rbx+28h], 0FFFFFFFFh
0x18000d5c0  jmp     short loc_18000D5E3
0x18000d5c2  mov     r8d, [rbx+50h]
0x18000d5c6  lea     rax, [rcx+10h]
0x18000d5ca  mov     rdx, [rbx+48h]
0x18000d5ce  lea     r9, [rcx+28h]
0x18000d5d2  add     rcx, 468h
0x18000d5d9  mov     [rsp+38h+var_18], rax
0x18000d5de  call    ?write_string@?$string_output_adapter@_W@__crt_stdio_output@@QEBAXQEB_WHQEAHAEAV__crt_deferred_errno_cache@@@Z; __crt_stdio_output::string_output_adapter<wchar_t>::write_string(wchar_t const * const,int,int * const,__crt_deferred_errno_cache &)
0x18000d5e3  mov     rbx, [rsp+38h+arg_8]
0x18000d5e8  mov     al, 1
0x18000d5ea  mov     rbp, [rsp+38h+arg_10]
0x18000d5ef  mov     rsi, [rsp+38h+arg_18]
0x18000d5f4  add     rsp, 30h
0x18000d5f8  pop     rdi
0x18000d5f9  retn
```
