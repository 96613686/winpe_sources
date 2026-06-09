# std::vector<web::json::value,std::allocator<web::json::value>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x180004560`
- end: `0x180004728`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x1800069e0`

## callees

- `0x180002c74`
- `0x180002cac`
- `0x180004560`
- `0x1800047b0`
- `0x180005e40`
- `0x18001da08`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180004715`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180004715`

## pseudocode

```c
char *__fastcall std::vector<web::json::value>::_Resize_reallocate<std::_Value_init_tag>(
        char **a1,
        unsigned __int64 a2)
{
  __int64 v4; // r14
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // r15
  void *v9; // rax
  unsigned __int64 v10; // rdx
  char *v11; // rcx
  _QWORD *v12; // rdi
  char *v13; // r8
  _QWORD *v14; // rdx
  char *i; // rcx
  __int64 v16; // rax
  char *v17; // rbx
  char *j; // r14
  char *v19; // rcx
  unsigned __int64 v20; // rdx
  char *v21; // r8
  char *result; // rax
  unsigned __int64 v23; // [rsp+20h] [rbp-38h]
  __int64 v25; // [rsp+78h] [rbp+20h]

  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    std::vector<std::pair<std::wstring,web::json::value>>::_Xlength();
  v4 = (a1[1] - *a1) >> 3;
  v5 = (a1[2] - *a1) >> 3;
  v6 = v5 >> 1;
  if ( v5 > 0x1FFFFFFFFFFFFFFFLL - (v5 >> 1) )
    goto LABEL_28;
  v7 = v6 + v5;
  if ( v6 + v5 >= a2 )
  {
    v23 = v6 + v5;
    if ( v7 > 0x1FFFFFFFFFFFFFFFLL )
      goto LABEL_28;
  }
  else
  {
    v7 = a2;
    v23 = a2;
  }
  v8 = 8 * v7;
  if ( 8 * v7 < 0x1000 )
  {
    if ( v8 )
      v12 = operator new(8 * v7);
    else
      v12 = 0;
    goto LABEL_30;
  }
  if ( v8 + 39 < v8 )
LABEL_28:
    __scrt_throw_std_bad_array_new_length();
  v9 = operator new(v8 + 39);
  if ( !v9 )
    goto LABEL_27;
  v12 = (_QWORD *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v12 - 1) = v9;
LABEL_30:
  try
  {
    v25 = std::_Uninitialized_value_construct_n<std::allocator<web::json::value>>(&v12[v4], a2 - v4, a1);
    v13 = a1[1];
    v14 = v12;
    for ( i = *a1; i != v13; i += 8 )
    {
      v16 = *(_QWORD *)i;
      *(_QWORD *)i = 0;
      *v14++ = v16;
    }
  }
  catch ( ... )
  {
    std::_Destroy_range<std::allocator<web::json::value>>(&v12[v4], v25, a1);
    std::allocator<web::json::value>::deallocate(a1, v12, v23);
    throw;
  }
  v17 = *a1;
  if ( *a1 )
  {
    for ( j = a1[1]; v17 != j; v17 += 8 )
    {
      if ( *(_QWORD *)v17 )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v17 + 192LL))(*(_QWORD *)v17, 1);
    }
    v19 = *a1;
    v20 = (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL;
    if ( v20 < 0x1000 )
      goto LABEL_25;
    v10 = v20 + 39;
    v21 = (char *)*((_QWORD *)v19 - 1);
    v11 = (char *)(v19 - v21);
    if ( (unsigned __int64)(v11 - 8) <= 0x1F )
    {
      v19 = v21;
LABEL_25:
      operator delete(v19);
      goto LABEL_26;
    }
LABEL_27:
    _o__invalid_parameter_noinfo_noreturn(v11, v10);
    __debugbreak();
  }
LABEL_26:
  *a1 = (char *)v12;
  a1[1] = (char *)&v12[a2];
  result = (char *)&v12[v8 / 8];
  a1[2] = (char *)&v12[v8 / 8];
  return result;
}

```

## disassembly

```asm
0x180004560  mov     [rsp+arg_10], rbx
0x180004565  mov     [rsp+arg_0], rcx
0x18000456a  push    rsi
0x18000456b  push    rdi
0x18000456c  push    r12
0x18000456e  push    r14
0x180004570  push    r15
0x180004572  sub     rsp, 30h
0x180004576  mov     r12, rdx
0x180004579  mov     rsi, rcx
0x18000457c  mov     r8, 1FFFFFFFFFFFFFFFh
0x180004586  cmp     rdx, r8
0x180004589  ja      loc_180004722
0x18000458f  mov     r14, [rcx+8]
0x180004593  sub     r14, [rcx]
0x180004596  sar     r14, 3
0x18000459a  mov     rcx, [rcx+10h]
0x18000459e  sub     rcx, [rsi]
0x1800045a1  sar     rcx, 3
0x1800045a5  mov     rdx, rcx
0x1800045a8  shr     rdx, 1
0x1800045ab  mov     rax, r8
0x1800045ae  sub     rax, rdx
0x1800045b1  cmp     rcx, rax
0x1800045b4  ja      loc_18000471C
0x1800045ba  lea     rax, [rdx+rcx]
0x1800045be  cmp     rax, r12
0x1800045c1  jnb     short loc_1800045CD
0x1800045c3  mov     rax, r12
0x1800045c6  mov     [rsp+58h+var_38], rax
0x1800045cb  jmp     short loc_1800045DB
0x1800045cd  mov     [rsp+58h+var_38], rax
0x1800045d2  cmp     rax, r8
0x1800045d5  ja      loc_18000471C
0x1800045db  lea     r15, ds:0[rax*8]
0x1800045e3  cmp     r15, 1000h
0x1800045ea  jb      short loc_180004617
0x1800045ec  lea     rcx, [r15+27h]; Size
0x1800045f0  cmp     rcx, r15
0x1800045f3  jbe     loc_18000471C
0x1800045f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800045fe  test    rax, rax
0x180004601  jz      loc_180004715
0x180004607  lea     rdi, [rax+27h]
0x18000460b  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18000460f  mov     [rdi-8], rax
0x180004613  xor     ebx, ebx
0x180004615  jmp     short loc_18000462F
0x180004617  test    r15, r15
0x18000461a  jz      short loc_18000462B
0x18000461c  mov     rcx, r15; Size
0x18000461f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004624  mov     rdi, rax
0x180004627  xor     ebx, ebx
0x180004629  jmp     short loc_18000462F
0x18000462b  xor     ebx, ebx
0x18000462d  mov     edi, ebx
0x18000462f  mov     [rsp+58h+arg_8], rdi
0x180004634  lea     rcx, [rdi+r14*8]
0x180004638  mov     [rsp+58h+var_30], rcx
0x18000463d  mov     [rsp+58h+arg_18], rcx
0x180004642  mov     rdx, r12
0x180004645  sub     rdx, r14
0x180004648  mov     r8, rsi
0x18000464b  call    ??$_Uninitialized_value_construct_n@V?$allocator@Vvalue@json@web@@@std@@@std@@YAPEAVvalue@json@web@@PEAV123@_KAEAV?$allocator@Vvalue@json@web@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<web::json::value>>(web::json::value *,unsigned __int64,std::allocator<web::json::value> &)
0x180004650  mov     [rsp+58h+arg_18], rax
0x180004655  mov     r8, [rsi+8]
0x180004659  mov     rdx, rdi
0x18000465c  mov     rcx, [rsi]
0x18000465f  cmp     rcx, r8
0x180004662  jz      short loc_180004686
0x180004664  nop     dword ptr [rax+00h]
0x180004668  nop     dword ptr [rax+rax+00000000h]
0x180004670  mov     rax, [rcx]
0x180004673  mov     [rcx], rbx
0x180004676  mov     [rdx], rax
0x180004679  lea     rdx, [rdx+8]
0x18000467d  add     rcx, 8
0x180004681  cmp     rcx, r8
0x180004684  jnz     short loc_180004670
0x180004686  mov     rbx, [rsi]
0x180004689  test    rbx, rbx
0x18000468c  jz      short loc_1800046F0
0x18000468e  mov     r14, [rsi+8]
0x180004692  cmp     rbx, r14
0x180004695  jz      short loc_1800046BC
0x180004697  mov     rcx, [rbx]
0x18000469a  test    rcx, rcx
0x18000469d  jz      short loc_1800046B3
0x18000469f  mov     rax, [rcx]
0x1800046a2  mov     edx, 1
0x1800046a7  mov     rax, [rax+0C0h]
0x1800046ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046b3  add     rbx, 8
0x1800046b7  cmp     rbx, r14
0x1800046ba  jnz     short loc_180004697
0x1800046bc  mov     rcx, [rsi]
0x1800046bf  mov     rdx, [rsi+10h]
0x1800046c3  sub     rdx, rcx
0x1800046c6  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800046ca  cmp     rdx, 1000h
0x1800046d1  jb      short loc_1800046EB
0x1800046d3  add     rdx, 27h ; '''; unsigned __int64
0x1800046d7  mov     r8, [rcx-8]
0x1800046db  sub     rcx, r8
0x1800046de  lea     rax, [rcx-8]
0x1800046e2  cmp     rax, 1Fh
0x1800046e6  ja      short loc_180004715
0x1800046e8  mov     rcx, r8; void *
0x1800046eb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800046f0  mov     [rsi], rdi
0x1800046f3  lea     rax, [rdi+r12*8]
0x1800046f7  mov     [rsi+8], rax
0x1800046fb  lea     rax, [r15+rdi]
0x1800046ff  mov     [rsi+10h], rax
0x180004703  mov     rbx, [rsp+58h+arg_10]
0x180004708  add     rsp, 30h
0x18000470c  pop     r15
0x18000470e  pop     r14
0x180004710  pop     r12
0x180004712  pop     rdi
0x180004713  pop     rsi
0x180004714  retn
0x180004715  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x18000471b  int     3; Trap to Debugger
0x18000471c  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x180004722  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,web::json::value>>::_Xlength(void)
```
