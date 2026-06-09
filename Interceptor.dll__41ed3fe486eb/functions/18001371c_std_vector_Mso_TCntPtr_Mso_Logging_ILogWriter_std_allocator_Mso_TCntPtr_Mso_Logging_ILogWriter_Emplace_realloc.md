# std::vector<Mso::TCntPtr<Mso::Logging::ILogWriter>,std::allocator<Mso::TCntPtr<Mso::Logging::ILogWriter>>>::_Emplace_reallocate<Mso::Logging::ILogWriter *>(Mso::TCntPtr<Mso::Logging::ILogWriter> * const,Mso::Logging::ILogWriter * &&)

- ea: `0x18001371c`
- end: `0x18001396d`
- name: `??$_Emplace_reallocate@PEAUILogWriter@Logging@Mso@@@?$vector@V?$TCntPtr@UILogWriter@Logging@Mso@@@Mso@@V?$allocator@V?$TCntPtr@UILogWriter@Logging@Mso@@@Mso@@@std@@@std@@AEAAPEAV?$TCntPtr@UILogWriter@Logging@Mso@@@Mso@@QEAV23@$$QEAPEAUILogWriter@Logging@3@@Z`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180013180`

## callees

- `0x180001b14`
- `0x180005224`
- `0x18000ab0c`
- `0x18000ae48`
- `0x18001371c`
- `0x180013970`
- `0x18002b3c0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180013954`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180013954`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001381a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001381a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800138f2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800138f2`

## pseudocode

```c
_QWORD *__fastcall std::vector<Mso::TCntPtr<Mso::Logging::ILogWriter>>::_Emplace_reallocate<Mso::Logging::ILogWriter *>(
        __int64 **a1,
        __int64 *a2,
        void (__fastcall ****a3)(_QWORD))
{
  __int64 v3; // rbp
  __int64 v5; // r14
  __int64 *v6; // rdi
  __int64 v7; // rax
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // r15
  _QWORD *v14; // rsi
  void (__fastcall ***v15)(_QWORD); // rcx
  _QWORD *v16; // r12
  _QWORD *v17; // r14
  __int64 *v18; // r8
  _QWORD *v19; // rdx
  __int64 *v20; // rcx
  size_t v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 *v24; // rcx
  __int64 v25; // rax
  __int64 *v26; // rdi
  __int64 *v27; // rbp
  __int64 v28; // rcx
  __int64 *v29; // rcx
  _QWORD v31[3]; // [rsp+30h] [rbp-58h] BYREF
  _QWORD *v32; // [rsp+48h] [rbp-40h]
  _QWORD *v33; // [rsp+50h] [rbp-38h]
  __int64 v34; // [rsp+90h] [rbp+8h]

  v3 = 0x1FFFFFFFFFFFFFFFLL;
  v5 = a2 - *a1;
  v6 = a2;
  v7 = a1[1] - *a1;
  if ( v7 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<std::tuple<Mso::Logging::TraceHeader,std::wstring,std::shared_ptr<Mso::Logging::IStructuredTrace>>>::_Xlength();
  v9 = v7 + 1;
  v10 = a1[2] - *a1;
  v34 = v7 + 1;
  if ( v10 <= 0x1FFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v11 = v10 + (v10 >> 1);
    v12 = v9;
    if ( v11 >= v9 )
      v12 = v11;
    if ( v12 > 0x1FFFFFFFFFFFFFFFLL )
      std::_Throw_bad_array_new_length();
    v3 = v12;
  }
  v13 = v3;
  if ( 8 * v3 )
  {
    _mm_lfence();
    v21 = 8 * v3;
    if ( v13 < 512 )
    {
      v14 = malloc(v21);
      if ( !v14 )
        std::_Xbad_alloc();
    }
    else
    {
      v14 = (_QWORD *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v21);
    }
  }
  else
  {
    v14 = 0;
  }
  v15 = *a3;
  v16 = &v14[v5];
  v31[0] = a1;
  v17 = v16 + 1;
  v33 = v16 + 1;
  v31[2] = v3;
  *v16 = v15;
  if ( v15 )
    (**v15)(v15);
  v18 = a1[1];
  v19 = v14;
  v20 = *a1;
  v32 = v16;
  if ( v6 == v18 )
  {
    while ( v20 != v18 )
    {
      v22 = *v20;
      *v20++ = 0;
      *v19++ = v22;
    }
  }
  else
  {
    while ( v20 != v6 )
    {
      v23 = *v20;
      *v20++ = 0;
      *v19++ = v23;
    }
    v24 = a1[1];
    v32 = v14;
    while ( v6 != v24 )
    {
      v25 = *v6;
      *v6++ = 0;
      *v17++ = v25;
    }
  }
  v26 = *a1;
  v31[1] = 0;
  if ( v26 )
  {
    v27 = a1[1];
    while ( v26 != v27 )
    {
      v28 = *v26;
      if ( *v26 )
      {
        *v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
      }
      ++v26;
    }
    v29 = *a1;
    if ( (((char *)a1[2] - (char *)*a1) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
    {
      _mm_lfence();
      if ( (unsigned __int64)v29 - *(v29 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v29 = (__int64 *)*(v29 - 1);
    }
    free(v29);
  }
  _mm_lfence();
  *a1 = v14;
  a1[1] = &v14[v34];
  a1[2] = &v14[v13];
  std::vector<Mso::TCntPtr<Mso::Logging::ILogWriter>>::_Reallocation_guard::~_Reallocation_guard(v31, v19);
  return v16;
}

```

## disassembly

```asm
0x18001371c  mov     [rsp+arg_8], rbx
0x180013721  mov     [rsp+arg_10], rbp
0x180013726  mov     [rsp+arg_18], rsi
0x18001372b  push    rdi
0x18001372c  push    r12
0x18001372e  push    r13
0x180013730  push    r14
0x180013732  push    r15
0x180013734  sub     rsp, 60h
0x180013738  mov     rax, [rcx+8]
0x18001373c  mov     r14, rdx
0x18001373f  sub     r14, [rcx]
0x180013742  mov     rbp, 1FFFFFFFFFFFFFFFh
0x18001374c  sub     rax, [rcx]
0x18001374f  mov     r13, r8
0x180013752  sar     r14, 3
0x180013756  mov     rdi, rdx
0x180013759  sar     rax, 3
0x18001375d  mov     rbx, rcx
0x180013760  cmp     rax, rbp
0x180013763  jz      loc_180013967
0x180013769  mov     rcx, [rcx+10h]
0x18001376d  lea     r8, [rax+1]
0x180013771  sub     rcx, [rbx]
0x180013774  mov     rax, rbp
0x180013777  sar     rcx, 3
0x18001377b  mov     rdx, rcx
0x18001377e  mov     [rsp+88h+arg_0], r8
0x180013786  shr     rdx, 1
0x180013789  sub     rax, rdx
0x18001378c  cmp     rcx, rax
0x18001378f  ja      short loc_1800137AB
0x180013791  lea     rax, [rcx+rdx]
0x180013795  mov     rcx, r8
0x180013798  cmp     rax, r8
0x18001379b  cmovnb  rcx, rax
0x18001379f  cmp     rcx, rbp
0x1800137a2  ja      loc_18001395B
0x1800137a8  mov     rbp, rcx
0x1800137ab  lea     r15, ds:0[rbp*8]
0x1800137b3  test    r15, r15
0x1800137b6  jnz     short loc_180013801
0x1800137b8  xor     esi, esi
0x1800137ba  mov     rcx, [r13+0]
0x1800137be  lea     r12, [rsi+r14*8]
0x1800137c2  mov     [rsp+88h+var_58], rbx
0x1800137c7  lea     r14, [r12+8]
0x1800137cc  mov     [rsp+88h+var_38], r14
0x1800137d1  mov     [rsp+88h+var_48], rbp
0x1800137d6  mov     [r12], rcx
0x1800137da  test    rcx, rcx
0x1800137dd  jz      short loc_1800137EB
0x1800137df  mov     rax, [rcx]
0x1800137e2  mov     rax, [rax]
0x1800137e5  call    cs:__guard_dispatch_icall_fptr
0x1800137eb  mov     r8, [rbx+8]
0x1800137ef  mov     rdx, rsi
0x1800137f2  mov     rcx, [rbx]
0x1800137f5  mov     [rsp+88h+var_40], r12
0x1800137fa  cmp     rdi, r8
0x1800137fd  jnz     short loc_18001385F
0x1800137ff  jmp     short loc_180013843
0x180013801  lfence
0x180013804  mov     rcx, r15; Size
0x180013807  cmp     r15, 1000h
0x18001380e  jb      short loc_18001381A
0x180013810  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x180013815  mov     rsi, rax
0x180013818  jmp     short loc_1800137BA
0x18001381a  call    cs:__imp_malloc
0x180013820  mov     rsi, rax
0x180013823  test    rax, rax
0x180013826  jz      loc_180013961
0x18001382c  jmp     short loc_1800137BA
0x18001382e  mov     rax, [rcx]
0x180013831  mov     qword ptr [rcx], 0
0x180013838  add     rcx, 8
0x18001383c  mov     [rdx], rax
0x18001383f  lea     rdx, [rdx+8]
0x180013843  cmp     rcx, r8
0x180013846  jnz     short loc_18001382E
0x180013848  jmp     short loc_180013889
0x18001384a  mov     rax, [rcx]
0x18001384d  mov     qword ptr [rcx], 0
0x180013854  add     rcx, 8
0x180013858  mov     [rdx], rax
0x18001385b  lea     rdx, [rdx+8]
0x18001385f  cmp     rcx, rdi
0x180013862  jnz     short loc_18001384A
0x180013864  mov     rcx, [rbx+8]
0x180013868  mov     [rsp+88h+var_40], rsi
0x18001386d  jmp     short loc_180013884
0x18001386f  mov     rax, [rdi]
0x180013872  mov     qword ptr [rdi], 0
0x180013879  add     rdi, 8
0x18001387d  mov     [r14], rax
0x180013880  lea     r14, [r14+8]
0x180013884  cmp     rdi, rcx
0x180013887  jnz     short loc_18001386F
0x180013889  mov     rdi, [rbx]
0x18001388c  mov     [rsp+88h+var_50], 0
0x180013895  test    rdi, rdi
0x180013898  jz      short loc_1800138F8
0x18001389a  mov     rbp, [rbx+8]
0x18001389e  jmp     short loc_1800138C0
0x1800138a0  mov     rcx, [rdi]
0x1800138a3  test    rcx, rcx
0x1800138a6  jz      short loc_1800138BC
0x1800138a8  mov     qword ptr [rdi], 0
0x1800138af  mov     rax, [rcx]
0x1800138b2  mov     rax, [rax+8]
0x1800138b6  call    cs:__guard_dispatch_icall_fptr
0x1800138bc  add     rdi, 8
0x1800138c0  cmp     rdi, rbp
0x1800138c3  jnz     short loc_1800138A0
0x1800138c5  mov     rcx, [rbx]
0x1800138c8  mov     rax, [rbx+10h]
0x1800138cc  sub     rax, rcx
0x1800138cf  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800138d3  cmp     rax, 1000h
0x1800138d9  jb      short loc_1800138F2
0x1800138db  lfence
0x1800138de  mov     rdx, [rcx-8]
0x1800138e2  sub     rcx, rdx
0x1800138e5  lea     rax, [rcx-8]
0x1800138e9  cmp     rax, 1Fh
0x1800138ed  ja      short loc_180013941
0x1800138ef  mov     rcx, rdx; Block
0x1800138f2  call    cs:__imp_free
0x1800138f8  lfence
0x1800138fb  mov     rax, [rsp+88h+arg_0]
0x180013903  mov     [rbx], rsi
0x180013906  lea     rcx, [rsi+rax*8]
0x18001390a  mov     [rbx+8], rcx
0x18001390e  lea     rcx, [r15+rsi]
0x180013912  mov     [rbx+10h], rcx
0x180013916  lea     rcx, [rsp+88h+var_58]
0x18001391b  call    ??1_Reallocation_guard@?$vector@V?$TCntPtr@UILogWriter@Logging@Mso@@@Mso@@V?$allocator@V?$TCntPtr@UILogWriter@Logging@Mso@@@Mso@@@std@@@std@@QEAA@XZ; std::vector<Mso::TCntPtr<Mso::Logging::ILogWriter>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180013920  lea     r11, [rsp+88h+var_28]
0x180013925  mov     rax, r12
0x180013928  mov     rbx, [r11+38h]
0x18001392c  mov     rbp, [r11+40h]
0x180013930  mov     rsi, [r11+48h]
0x180013934  mov     rsp, r11
0x180013937  pop     r15
0x180013939  pop     r14
0x18001393b  pop     r13
0x18001393d  pop     r12
0x18001393f  pop     rdi
0x180013940  retn
0x180013941  xor     r9d, r9d; LineNo
0x180013944  mov     [rsp+88h+Reserved], 0; Reserved
0x18001394d  xor     r8d, r8d; FileName
0x180013950  xor     edx, edx; FunctionName
0x180013952  xor     ecx, ecx; Expression
0x180013954  call    cs:__imp__invoke_watson
0x18001395b  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x180013961  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180013967  call    ?_Xlength@?$vector@V?$tuple@UTraceHeader@Logging@Mso@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIStructuredTrace@Logging@Mso@@@5@@std@@V?$allocator@V?$tuple@UTraceHeader@Logging@Mso@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIStructuredTrace@Logging@Mso@@@5@@std@@@2@@std@@CAXXZ; std::vector<std::tuple<Mso::Logging::TraceHeader,std::wstring,std::shared_ptr<Mso::Logging::IStructuredTrace>>>::_Xlength(void)
```
