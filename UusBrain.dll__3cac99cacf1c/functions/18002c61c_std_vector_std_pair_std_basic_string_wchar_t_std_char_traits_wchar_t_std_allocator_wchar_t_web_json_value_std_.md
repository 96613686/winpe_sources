# std::vector<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value>>>::_Tidy(void)

- ea: `0x18002c61c`
- end: `0x18002c6f9`
- name: `?_Tidy@?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAXXZ`
- size: `221`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18002b5f4`
- `0x18002b900`
- `0x18002c700`
- `0x180033c14`

## callees

- `0x180029644`
- `0x18002c61c`
- `0x180042bc4`
- `0x180047a30`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002c6f2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002c6f2`

## pseudocode

```c
void __fastcall std::vector<std::pair<std::wstring,web::json::value>>::_Tidy(_QWORD *a1)
{
  _QWORD *v1; // rbx
  _QWORD *v3; // rsi
  __int64 v4; // rcx
  _QWORD *v5; // rcx

  v1 = (_QWORD *)*a1;
  if ( *a1 )
  {
    v3 = (_QWORD *)a1[1];
    while ( v1 != v3 )
    {
      v4 = v1[4];
      if ( v4 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 192LL))(v4, 1);
      std::wstring::_Tidy_deallocate(v1);
      v1 += 5;
    }
    v5 = (_QWORD *)*a1;
    if ( (unsigned __int64)(8 * ((__int64)(a1[2] - *a1) >> 3)) >= 0x1000 )
    {
      if ( (unsigned __int64)v5 - *(v5 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v5 = (_QWORD *)*(v5 - 1);
    }
    operator delete(v5);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x18002c61c  mov     [rsp+arg_8], rbx
0x18002c621  mov     [rsp+arg_10], rsi
0x18002c626  push    rdi
0x18002c627  sub     rsp, 30h
0x18002c62b  mov     rbx, [rcx]
0x18002c62e  mov     rdi, rcx
0x18002c631  test    rbx, rbx
0x18002c634  jz      loc_18002C6CF
0x18002c63a  mov     rsi, [rcx+8]
0x18002c63e  jmp     short loc_18002C669
0x18002c640  mov     rcx, [rbx+20h]
0x18002c644  test    rcx, rcx
0x18002c647  jz      short loc_18002C65D
0x18002c649  mov     rax, [rcx]
0x18002c64c  mov     edx, 1
0x18002c651  mov     rax, [rax+0C0h]
0x18002c658  call    _guard_dispatch_icall
0x18002c65d  mov     rcx, rbx
0x18002c660  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c665  add     rbx, 28h ; '('
0x18002c669  cmp     rbx, rsi
0x18002c66c  jnz     short loc_18002C640
0x18002c66e  mov     rcx, [rdi]
0x18002c671  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x18002c67b  mov     rax, [rdi+10h]
0x18002c67f  sub     rax, rcx
0x18002c682  sar     rax, 3
0x18002c686  imul    rax, rdx
0x18002c68a  lea     rdx, [rax+rax*4]
0x18002c68e  shl     rdx, 3
0x18002c692  cmp     rdx, 1000h
0x18002c699  jb      short loc_18002C6B3
0x18002c69b  mov     rax, [rcx-8]
0x18002c69f  add     rdx, 27h ; '''; unsigned __int64
0x18002c6a3  sub     rcx, rax
0x18002c6a6  sub     rcx, 8
0x18002c6aa  cmp     rcx, 1Fh
0x18002c6ae  ja      short loc_18002C6DF
0x18002c6b0  mov     rcx, rax; void *
0x18002c6b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002c6b8  mov     qword ptr [rdi], 0
0x18002c6bf  mov     qword ptr [rdi+8], 0
0x18002c6c7  mov     qword ptr [rdi+10h], 0
0x18002c6cf  mov     rbx, [rsp+38h+arg_8]
0x18002c6d4  mov     rsi, [rsp+38h+arg_10]
0x18002c6d9  add     rsp, 30h
0x18002c6dd  pop     rdi
0x18002c6de  retn
0x18002c6df  xor     r9d, r9d; LineNo
0x18002c6e2  mov     [rsp+38h+Reserved], 0; Reserved
0x18002c6eb  xor     r8d, r8d; FileName
0x18002c6ee  xor     edx, edx; FunctionName
0x18002c6f0  xor     ecx, ecx; Expression
0x18002c6f2  call    cs:__imp__invoke_watson
```
