# std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>>::_Tidy(void)

- ea: `0x1800056c0`
- end: `0x180005792`
- name: `?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAXXZ`
- size: `210`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180004dd0`
- `0x1800054f0`

## callees

- `0x180002cc0`
- `0x1800056c0`
- `0x18001c81c`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall std::vector<std::pair<std::wstring,web::json::value>>::_Tidy(char **a1)
{
  char *v1; // rbx
  char *i; // rsi
  __int64 v4; // rcx
  char *v5; // r8
  char *v6; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( *a1 )
  {
    for ( i = a1[1]; v1 != i; v1 += 40 )
    {
      v4 = *((_QWORD *)v1 + 4);
      if ( v4 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 192LL))(v4, 1);
      std::wstring::_Tidy_deallocate(v1);
    }
    v5 = *a1;
    if ( (unsigned __int64)(40 * ((a1[2] - *a1) / 40)) < 0x1000 )
    {
      v6 = *a1;
    }
    else
    {
      v6 = (char *)*((_QWORD *)v5 - 1);
      if ( (unsigned __int64)(v5 - v6 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v6);
    result = 0;
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800056c0  mov     [rsp+arg_8], rbx
0x1800056c5  push    rdi
0x1800056c6  sub     rsp, 20h
0x1800056ca  mov     rbx, [rcx]
0x1800056cd  mov     rdi, rcx
0x1800056d0  test    rbx, rbx
0x1800056d3  jz      loc_180005787
0x1800056d9  mov     [rsp+28h+arg_0], rsi
0x1800056de  mov     rsi, [rcx+8]
0x1800056e2  cmp     rbx, rsi
0x1800056e5  jz      short loc_180005715
0x1800056e7  mov     rcx, [rbx+20h]
0x1800056eb  test    rcx, rcx
0x1800056ee  jz      short loc_180005704
0x1800056f0  mov     rax, [rcx]
0x1800056f3  mov     edx, 1
0x1800056f8  mov     rax, [rax+0C0h]
0x1800056ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005704  mov     rcx, rbx
0x180005707  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000570c  add     rbx, 28h ; '('
0x180005710  cmp     rbx, rsi
0x180005713  jnz     short loc_1800056E7
0x180005715  mov     r8, [rdi]
0x180005718  mov     rax, 6666666666666667h
0x180005722  mov     rcx, [rdi+10h]
0x180005726  mov     rsi, [rsp+28h+arg_0]
0x18000572b  sub     rcx, r8
0x18000572e  imul    rcx
0x180005731  sar     rdx, 4
0x180005735  mov     rax, rdx
0x180005738  shr     rax, 3Fh
0x18000573c  add     rdx, rax
0x18000573f  lea     rax, [rdx+rdx*4]
0x180005743  lea     rdx, ds:0[rax*8]; unsigned __int64
0x18000574b  cmp     rdx, 1000h
0x180005752  jb      short loc_180005772
0x180005754  mov     rcx, [r8-8]
0x180005758  sub     r8, rcx
0x18000575b  sub     r8, 8
0x18000575f  cmp     r8, 1Fh
0x180005763  ja      short loc_18000576B
0x180005765  add     rdx, 27h ; '''
0x180005769  jmp     short loc_180005775
0x18000576b  mov     ecx, 5
0x180005770  int     29h; Win8: RtlFailFast(ecx)
0x180005772  mov     rcx, r8; void *
0x180005775  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000577a  xor     eax, eax
0x18000577c  mov     [rdi], rax
0x18000577f  mov     [rdi+8], rax
0x180005783  mov     [rdi+10h], rax
0x180005787  mov     rbx, [rsp+28h+arg_8]
0x18000578c  add     rsp, 20h
0x180005790  pop     rdi
0x180005791  retn
```
