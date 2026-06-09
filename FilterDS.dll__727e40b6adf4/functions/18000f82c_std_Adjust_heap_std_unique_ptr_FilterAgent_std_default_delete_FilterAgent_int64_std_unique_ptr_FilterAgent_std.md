# std::_Adjust_heap_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________int64_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent_____lambda_4e00c4f2fc8604fa547e688629cc8b0c___

- ea: `0x18000f82c`
- end: `0x18000f9b3`
- name: `std::_Adjust_heap_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________int64_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent_____lambda_4e00c4f2fc8604fa547e688629cc8b0c___`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x18000fe3c`

## callees

- `0x18000ef28`
- `0x18000f82c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f8a8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f8fa`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f95d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f999`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f8a8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f8fa`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f95d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f999`

## pseudocode

```c
void __fastcall std::_Adjust_heap_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________int64_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent_____lambda_4e00c4f2fc8604fa547e688629cc8b0c___(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        FilterAgent **a4)
{
  __int64 v4; // r11
  __int64 i; // r10
  __int64 v10; // rbp
  FilterAgent **v11; // r12
  FilterAgent **v12; // rax
  FilterAgent *v13; // r14
  FilterAgent *v14; // rsi
  FilterAgent **v15; // rax
  FilterAgent **v16; // r14
  FilterAgent *v17; // rbp
  FilterAgent *v18; // rsi
  __int64 v19; // rbx
  __int64 v20; // rbx
  FilterAgent **v21; // r8
  FilterAgent *v22; // rbp
  FilterAgent **v23; // r14
  FilterAgent *v24; // rsi
  FilterAgent **v25; // rdi
  FilterAgent *v26; // rsi
  FilterAgent *v27; // rbx

  v4 = 2 * a2 + 2;
  for ( i = a2; v4 < a3; i = v10 )
  {
    v10 = v4 - 1;
    v11 = (FilterAgent **)(a1 + 8 * i);
    if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 8 * v4) + 16LL) + 8LL) >= *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 8 * v4 - 8)
                                                                                                + 16LL)
                                                                                    + 8LL) )
      v10 = v4;
    v12 = (FilterAgent **)(a1 + 8 * v10);
    if ( v11 != v12 )
    {
      v13 = *v12;
      *v12 = 0;
      v14 = *v11;
      if ( v13 != *v11 )
      {
        if ( v14 )
        {
          FilterAgent::~FilterAgent(*v11);
          operator delete(v14);
        }
        *v11 = v13;
      }
    }
    v4 = 2 * v10 + 2;
  }
  if ( v4 == a3 )
  {
    v15 = (FilterAgent **)(a1 + 8 * (a3 - 1));
    v16 = (FilterAgent **)(a1 + 8 * i);
    if ( v16 != v15 )
    {
      v17 = *v15;
      *v15 = 0;
      v18 = *v16;
      if ( v17 != *v16 )
      {
        if ( v18 )
        {
          FilterAgent::~FilterAgent(*v16);
          operator delete(v18);
        }
        *v16 = v17;
      }
    }
    i = a3 - 1;
  }
  if ( a2 < i )
  {
    do
    {
      v19 = i - 1;
      if ( i - 1 < 0 )
        v19 = i;
      v20 = v19 >> 1;
      v21 = (FilterAgent **)(a1 + 8 * v20);
      v22 = *v21;
      if ( *(_BYTE *)(*((_QWORD *)*v21 + 2) + 8LL) >= *(_BYTE *)(*((_QWORD *)*a4 + 2) + 8LL) )
        break;
      v23 = (FilterAgent **)(a1 + 8 * i);
      if ( v23 != v21 )
      {
        *v21 = 0;
        v24 = *v23;
        if ( v22 != *v23 )
        {
          if ( v24 )
          {
            FilterAgent::~FilterAgent(*v23);
            operator delete(v24);
          }
          *v23 = v22;
        }
      }
      i = v20;
    }
    while ( a2 < v20 );
  }
  v25 = (FilterAgent **)(a1 + 8 * i);
  if ( v25 != a4 )
  {
    v26 = *a4;
    *a4 = 0;
    v27 = *v25;
    if ( v26 != *v25 )
    {
      if ( v27 )
      {
        FilterAgent::~FilterAgent(*v25);
        operator delete(v27);
      }
      *v25 = v26;
    }
  }
}

```

## disassembly

```asm
0x18000f82c  push    rbx
0x18000f82e  push    rbp
0x18000f82f  push    rsi
0x18000f830  push    rdi
0x18000f831  push    r12
0x18000f833  push    r13
0x18000f835  push    r14
0x18000f837  push    r15
0x18000f839  sub     rsp, 28h
0x18000f83d  lea     r11, ds:2[rdx*2]
0x18000f845  mov     r15, r9
0x18000f848  mov     rbx, r8
0x18000f84b  mov     r10, rdx
0x18000f84e  mov     rdi, rcx
0x18000f851  mov     r13, rdx
0x18000f854  cmp     r11, r8
0x18000f857  jge     short loc_18000F8C2
0x18000f859  mov     rax, [rdi+r11*8]
0x18000f85d  lea     rbp, [r11-1]
0x18000f861  lea     r12, [rdi+r10*8]
0x18000f865  mov     rdx, [rax+10h]
0x18000f869  mov     rax, [rdi+r11*8-8]
0x18000f86e  mov     rcx, [rax+10h]
0x18000f872  mov     al, [rdx+8]
0x18000f875  cmp     al, [rcx+8]
0x18000f878  cmovnb  rbp, r11
0x18000f87c  lea     rax, [rdi+rbp*8]
0x18000f880  cmp     r12, rax
0x18000f883  jz      short loc_18000F8B2
0x18000f885  mov     r14, [rax]
0x18000f888  mov     qword ptr [rax], 0
0x18000f88f  mov     rsi, [r12]
0x18000f893  cmp     r14, rsi
0x18000f896  jz      short loc_18000F8B2
0x18000f898  test    rsi, rsi
0x18000f89b  jz      short loc_18000F8AE
0x18000f89d  mov     rcx, rsi; this
0x18000f8a0  call    ??1FilterAgent@@QEAA@XZ; FilterAgent::~FilterAgent(void)
0x18000f8a5  mov     rcx, rsi
0x18000f8a8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f8ae  mov     [r12], r14
0x18000f8b2  lea     r11, ds:2[rbp*2]
0x18000f8ba  mov     r10, rbp
0x18000f8bd  cmp     r11, rbx
0x18000f8c0  jl      short loc_18000F859
0x18000f8c2  cmp     r11, rbx
0x18000f8c5  jnz     short loc_18000F907
0x18000f8c7  lea     rax, [rbx-1]
0x18000f8cb  lea     rax, [rdi+rax*8]
0x18000f8cf  lea     r14, [rdi+r10*8]
0x18000f8d3  cmp     r14, rax
0x18000f8d6  jz      short loc_18000F903
0x18000f8d8  mov     rbp, [rax]
0x18000f8db  mov     qword ptr [rax], 0
0x18000f8e2  mov     rsi, [r14]
0x18000f8e5  cmp     rbp, rsi
0x18000f8e8  jz      short loc_18000F903
0x18000f8ea  test    rsi, rsi
0x18000f8ed  jz      short loc_18000F900
0x18000f8ef  mov     rcx, rsi; this
0x18000f8f2  call    ??1FilterAgent@@QEAA@XZ; FilterAgent::~FilterAgent(void)
0x18000f8f7  mov     rcx, rsi
0x18000f8fa  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f900  mov     [r14], rbp
0x18000f903  lea     r10, [rbx-1]
0x18000f907  cmp     r13, r10
0x18000f90a  jge     short loc_18000F96E
0x18000f90c  lea     rbx, [r10-1]
0x18000f910  test    rbx, rbx
0x18000f913  jns     short loc_18000F918
0x18000f915  inc     rbx
0x18000f918  mov     rax, [r15]
0x18000f91b  sar     rbx, 1
0x18000f91e  mov     rcx, [rax+10h]
0x18000f922  lea     r8, [rdi+rbx*8]
0x18000f926  mov     rbp, [r8]
0x18000f929  mov     al, [rcx+8]
0x18000f92c  mov     rdx, [rbp+10h]
0x18000f930  cmp     [rdx+8], al
0x18000f933  jnb     short loc_18000F96E
0x18000f935  lea     r14, [rdi+r10*8]
0x18000f939  cmp     r14, r8
0x18000f93c  jz      short loc_18000F966
0x18000f93e  mov     qword ptr [r8], 0
0x18000f945  mov     rsi, [r14]
0x18000f948  cmp     rbp, rsi
0x18000f94b  jz      short loc_18000F966
0x18000f94d  test    rsi, rsi
0x18000f950  jz      short loc_18000F963
0x18000f952  mov     rcx, rsi; this
0x18000f955  call    ??1FilterAgent@@QEAA@XZ; FilterAgent::~FilterAgent(void)
0x18000f95a  mov     rcx, rsi
0x18000f95d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f963  mov     [r14], rbp
0x18000f966  mov     r10, rbx
0x18000f969  cmp     r13, rbx
0x18000f96c  jl      short loc_18000F90C
0x18000f96e  lea     rdi, [rdi+r10*8]
0x18000f972  cmp     rdi, r15
0x18000f975  jz      short loc_18000F9A2
0x18000f977  mov     rsi, [r15]
0x18000f97a  mov     qword ptr [r15], 0
0x18000f981  mov     rbx, [rdi]
0x18000f984  cmp     rsi, rbx
0x18000f987  jz      short loc_18000F9A2
0x18000f989  test    rbx, rbx
0x18000f98c  jz      short loc_18000F99F
0x18000f98e  mov     rcx, rbx; this
0x18000f991  call    ??1FilterAgent@@QEAA@XZ; FilterAgent::~FilterAgent(void)
0x18000f996  mov     rcx, rbx
0x18000f999  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f99f  mov     [rdi], rsi
0x18000f9a2  add     rsp, 28h
0x18000f9a6  pop     r15
0x18000f9a8  pop     r14
0x18000f9aa  pop     r13
0x18000f9ac  pop     r12
0x18000f9ae  pop     rdi
0x18000f9af  pop     rsi
0x18000f9b0  pop     rbp
0x18000f9b1  pop     rbx
0x18000f9b2  retn
```
