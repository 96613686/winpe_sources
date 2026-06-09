# Mso::Logging::Logger::CopyWriters(void)

- ea: `0x180013518`
- end: `0x180013624`
- name: `?CopyWriters@Logger@Logging@Mso@@AEAA?AV?$vector@V?$TCntPtr@UILogWriter@Logging@Mso@@@Mso@@V?$allocator@V?$TCntPtr@UILogWriter@Logging@Mso@@@Mso@@@std@@@std@@XZ`
- size: `268`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: ``

## callers

- `0x180012dd0`
- `0x180012ec0`
- `0x180012ff0`
- `0x180013080`
- `0x180013100`
- `0x1800133b0`
- `0x180013460`
- `0x1800134c0`

## callees

- `0x180005224`
- `0x18000ab0c`
- `0x18000ae48`
- `0x180013518`
- `0x1800261c8`
- `0x1800261d8`
- `0x18002b3c0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800135bb`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800135bb`

## pseudocode

```c
_QWORD *__fastcall Mso::Logging::Logger::CopyWriters(__int64 a1, _QWORD *a2)
{
  unsigned __int64 v4; // rdi
  size_t v5; // rdi
  _QWORD *v6; // rbx
  void (__fastcall ****v7)(_QWORD); // rbp
  void (__fastcall ****i)(_QWORD); // rdi
  void (__fastcall ***v9)(_QWORD); // rcx

  Smtx_lock_shared((_Smtx_t *)(a1 + 8));
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v4 = (__int64)(*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 16)) >> 3;
  if ( v4 )
  {
    if ( v4 > 0x1FFFFFFFFFFFFFFFLL )
      std::vector<std::tuple<Mso::Logging::TraceHeader,std::wstring,std::shared_ptr<Mso::Logging::IStructuredTrace>>>::_Xlength();
    v5 = 8 * v4;
    if ( v5 )
    {
      _mm_lfence();
      if ( v5 < 0x1000 )
      {
        v6 = malloc(v5);
        if ( !v6 )
          std::_Xbad_alloc();
      }
      else
      {
        v6 = (_QWORD *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v5);
      }
    }
    else
    {
      v6 = 0;
    }
    *a2 = v6;
    a2[1] = v6;
    a2[2] = &v6[v5 / 8];
    v7 = *(void (__fastcall *****)(_QWORD))(a1 + 24);
    for ( i = *(void (__fastcall *****)(_QWORD))(a1 + 16); i != v7; ++i )
    {
      v9 = *i;
      *v6 = *i;
      if ( v9 )
        (**v9)(v9);
      ++v6;
    }
    a2[1] = v6;
  }
  Smtx_unlock_shared((_Smtx_t *)(a1 + 8));
  return a2;
}

```

## disassembly

```asm
0x180013518  mov     [rsp+arg_0], rbx
0x18001351d  mov     [rsp+arg_8], rbp
0x180013522  mov     [rsp+arg_10], rsi
0x180013527  push    rdi
0x180013528  push    r14
0x18001352a  push    r15
0x18001352c  sub     rsp, 20h
0x180013530  mov     rsi, rdx
0x180013533  mov     r14, rcx
0x180013536  add     rcx, 8; _Smtx_t *
0x18001353a  call    _Smtx_lock_shared
0x18001353f  mov     qword ptr [rsi], 0
0x180013546  mov     qword ptr [rsi+8], 0
0x18001354e  mov     qword ptr [rsi+10h], 0
0x180013556  mov     rdi, [r14+18h]
0x18001355a  sub     rdi, [r14+10h]
0x18001355e  sar     rdi, 3
0x180013562  test    rdi, rdi
0x180013565  jz      loc_1800135F3
0x18001356b  mov     rax, 1FFFFFFFFFFFFFFFh
0x180013575  cmp     rdi, rax
0x180013578  ja      loc_180013618
0x18001357e  shl     rdi, 3
0x180013582  test    rdi, rdi
0x180013585  jnz     short loc_1800135A2
0x180013587  xor     ebx, ebx
0x180013589  mov     [rsi], rbx
0x18001358c  mov     [rsi+8], rbx
0x180013590  lea     rax, [rdi+rbx]
0x180013594  mov     [rsi+10h], rax
0x180013598  mov     rbp, [r14+18h]
0x18001359c  mov     rdi, [r14+10h]
0x1800135a0  jmp     short loc_1800135EA
0x1800135a2  lfence
0x1800135a5  mov     rcx, rdi; Size
0x1800135a8  cmp     rdi, 1000h
0x1800135af  jb      short loc_1800135BB
0x1800135b1  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x1800135b6  mov     rbx, rax
0x1800135b9  jmp     short loc_180013589
0x1800135bb  call    cs:__imp_malloc
0x1800135c1  mov     rbx, rax
0x1800135c4  test    rax, rax
0x1800135c7  jz      short loc_18001361E
0x1800135c9  jmp     short loc_180013589
0x1800135cb  mov     rcx, [rdi]
0x1800135ce  mov     [rbx], rcx
0x1800135d1  test    rcx, rcx
0x1800135d4  jz      short loc_1800135E2
0x1800135d6  mov     rax, [rcx]
0x1800135d9  mov     rax, [rax]
0x1800135dc  call    cs:__guard_dispatch_icall_fptr
0x1800135e2  add     rbx, 8
0x1800135e6  add     rdi, 8
0x1800135ea  cmp     rdi, rbp
0x1800135ed  jnz     short loc_1800135CB
0x1800135ef  mov     [rsi+8], rbx
0x1800135f3  lea     rcx, [r14+8]; _Smtx_t *
0x1800135f7  call    _Smtx_unlock_shared
0x1800135fc  mov     rax, rsi
0x1800135ff  mov     rbx, [rsp+38h+arg_0]
0x180013604  mov     rbp, [rsp+38h+arg_8]
0x180013609  mov     rsi, [rsp+38h+arg_10]
0x18001360e  add     rsp, 20h
0x180013612  pop     r15
0x180013614  pop     r14
0x180013616  pop     rdi
0x180013617  retn
0x180013618  call    ?_Xlength@?$vector@V?$tuple@UTraceHeader@Logging@Mso@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIStructuredTrace@Logging@Mso@@@5@@std@@V?$allocator@V?$tuple@UTraceHeader@Logging@Mso@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIStructuredTrace@Logging@Mso@@@5@@std@@@2@@std@@CAXXZ; std::vector<std::tuple<Mso::Logging::TraceHeader,std::wstring,std::shared_ptr<Mso::Logging::IStructuredTrace>>>::_Xlength(void)
0x18001361e  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
