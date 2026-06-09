# std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal,std::allocator<WindowsMidiServicesInternal::GroupTerminalBlockInternal>>::_Emplace_reallocate<WindowsMidiServicesInternal::GroupTerminalBlockInternal const &>(WindowsMidiServicesInternal::GroupTerminalBlockInternal * const,WindowsMidiServicesInternal::GroupTerminalBlockInternal const &)

- ea: `0x18001bd50`
- end: `0x18001bfc2`
- name: `??$_Emplace_reallocate@AEBUGroupTerminalBlockInternal@WindowsMidiServicesInternal@@@?$vector@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@V?$allocator@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@@std@@@std@@AEAAPEAUGroupTerminalBlockInternal@WindowsMidiServicesInternal@@QEAU23@AEBU23@@Z`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task`

## callers

- `0x18001d454`

## callees

- `0x1800041a4`
- `0x1800041d0`
- `0x18000b740`
- `0x18000c290`
- `0x18000f0a4`
- `0x180013954`
- `0x18001bd50`
- `0x18001c544`
- `0x18001cc2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal>::_Emplace_reallocate<WindowsMidiServicesInternal::GroupTerminalBlockInternal const &>(
        _QWORD *a1,
        __int64 a2,
        char *a3)
{
  void *v5; // rbx
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // r12
  unsigned __int64 v10; // r15
  unsigned __int64 v11; // r14
  _QWORD *v12; // rdi
  void *v13; // rax
  __int64 v14; // r13
  char *v15; // rbx
  __int64 v16; // rdx
  _QWORD *v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rbp
  __int64 v21; // rcx
  void *v22; // rax
  _QWORD *v24; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v25; // [rsp+28h] [rbp-70h]
  unsigned __int64 v26; // [rsp+30h] [rbp-68h]
  _QWORD *v27; // [rsp+38h] [rbp-60h]
  char *v28; // [rsp+40h] [rbp-58h]

  v5 = (void *)*a1;
  v6 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(a1[1] - *a1) >> 4);
  if ( v6 == 0x555555555555555LL )
    std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::_Xlength();
  v7 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(a1[2] - (_QWORD)v5) >> 4);
  v8 = v7 >> 1;
  if ( v7 > 0x555555555555555LL - (v7 >> 1) )
    goto LABEL_27;
  v9 = v6 + 1;
  v10 = v6 + 1;
  if ( v7 + v8 >= v6 + 1 )
    v10 = v7 + v8;
  if ( v10 > 0x555555555555555LL )
    goto LABEL_27;
  v11 = 48 * v10;
  if ( !(48 * v10) )
  {
    v12 = 0;
    goto LABEL_14;
  }
  if ( v11 < 0x1000 )
  {
    v12 = operator new(48 * v10);
    goto LABEL_14;
  }
  if ( v11 + 39 < v11 )
LABEL_27:
    __scrt_throw_std_bad_array_new_length();
  v13 = operator new(v11 + 39);
  if ( !v13 )
    __fastfail(5u);
  v12 = (_QWORD *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v12 - 1) = v13;
LABEL_14:
  v14 = (a2 - (__int64)v5) / 48;
  v15 = (char *)&v12[6 * v14];
  v24 = a1;
  v25 = v12;
  v26 = v10;
  v27 = v15 + 48;
  v28 = v15 + 48;
  *v15 = *a3;
  v15[1] = a3[1];
  v15[2] = a3[2];
  v15[3] = a3[3];
  v15[4] = a3[4];
  *((_WORD *)v15 + 3) = *((_WORD *)a3 + 3);
  *((_WORD *)v15 + 4) = *((_WORD *)a3 + 4);
  std::wstring::wstring(v15 + 16, a3 + 16);
  v27 = v15;
  v16 = a1[1];
  v17 = v12;
  v18 = *a1;
  if ( a2 != v16 )
  {
    std::_Uninitialized_move<WindowsMidiServicesInternal::GroupTerminalBlockInternal *>(v18, a2, v12);
    v27 = v12;
    v17 = v15 + 48;
    v16 = a1[1];
    v18 = a2;
  }
  std::_Uninitialized_move<WindowsMidiServicesInternal::GroupTerminalBlockInternal *>(v18, v16, v17);
  v25 = 0;
  v19 = *a1;
  if ( *a1 )
  {
    v20 = a1[1];
    while ( v19 != v20 )
    {
      std::wstring::~wstring((void *)(v19 + 16));
      v19 += 48;
    }
    v21 = *a1;
    if ( (unsigned __int64)(16 * ((__int64)(a1[2] - *a1) >> 4)) < 0x1000 )
    {
      v22 = (void *)*a1;
    }
    else
    {
      v22 = *(void **)(v21 - 8);
      if ( (unsigned __int64)(v21 - (_QWORD)v22 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v22);
  }
  *a1 = v12;
  a1[1] = &v12[6 * v9];
  a1[2] = &v12[v11 / 8];
  std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal>::_Reallocation_guard::~_Reallocation_guard(&v24);
  return (char *)&v12[6 * v14];
}

```

## disassembly

```asm
0x18001bd50  mov     [rsp+arg_10], r8
0x18001bd55  push    rbx
0x18001bd56  push    rbp
0x18001bd57  push    rsi
0x18001bd58  push    rdi
0x18001bd59  push    r12
0x18001bd5b  push    r13
0x18001bd5d  push    r14
0x18001bd5f  push    r15
0x18001bd61  sub     rsp, 58h
0x18001bd65  mov     rbp, rdx
0x18001bd68  mov     rsi, rcx
0x18001bd6b  mov     rbx, [rcx]
0x18001bd6e  mov     r9, [rcx+8]
0x18001bd72  sub     r9, rbx
0x18001bd75  sar     r9, 4
0x18001bd79  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001bd83  imul    r9, rax
0x18001bd87  mov     r8, 555555555555555h
0x18001bd91  cmp     r9, r8
0x18001bd94  jz      loc_18001BFB6
0x18001bd9a  mov     rcx, [rcx+10h]
0x18001bd9e  sub     rcx, rbx
0x18001bda1  sar     rcx, 4
0x18001bda5  imul    rcx, rax
0x18001bda9  mov     rdx, rcx
0x18001bdac  shr     rdx, 1
0x18001bdaf  mov     rax, r8
0x18001bdb2  sub     rax, rdx
0x18001bdb5  cmp     rcx, rax
0x18001bdb8  ja      loc_18001BFBC
0x18001bdbe  lea     r12, [r9+1]
0x18001bdc2  lea     rax, [rcx+rdx]
0x18001bdc6  mov     r15, r12
0x18001bdc9  cmp     rax, r12
0x18001bdcc  cmovnb  r15, rax
0x18001bdd0  cmp     r15, r8
0x18001bdd3  ja      loc_18001BFBC
0x18001bdd9  lea     r14, [r15+r15*2]
0x18001bddd  shl     r14, 4
0x18001bde1  test    r14, r14
0x18001bde4  jnz     short loc_18001BDEA
0x18001bde6  xor     edi, edi
0x18001bde8  jmp     short loc_18001BE28
0x18001bdea  cmp     r14, 1000h
0x18001bdf1  jb      short loc_18001BE1D
0x18001bdf3  lea     rcx, [r14+27h]; Size
0x18001bdf7  cmp     rcx, r14
0x18001bdfa  jbe     loc_18001BFBC
0x18001be00  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001be05  test    rax, rax
0x18001be08  jnz     short loc_18001BE0F
0x18001be0a  lea     ecx, [rax+5]
0x18001be0d  int     29h; Win8: RtlFailFast(ecx)
0x18001be0f  lea     rdi, [rax+27h]
0x18001be13  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18001be17  mov     [rdi-8], rax
0x18001be1b  jmp     short loc_18001BE28
0x18001be1d  mov     rcx, r14; Size
0x18001be20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001be25  mov     rdi, rax
0x18001be28  mov     rcx, rbp
0x18001be2b  sub     rcx, rbx
0x18001be2e  mov     rax, 2AAAAAAAAAAAAAABh
0x18001be38  imul    rcx
0x18001be3b  mov     r13, rdx
0x18001be3e  sar     r13, 3
0x18001be42  mov     rcx, r13
0x18001be45  shr     rcx, 3Fh
0x18001be49  add     r13, rcx
0x18001be4c  lea     rbx, ds:0[r13*2]
0x18001be54  add     rbx, r13
0x18001be57  shl     rbx, 4
0x18001be5b  add     rbx, rdi
0x18001be5e  lea     rax, [rbx+30h]
0x18001be62  mov     [rsp+98h+var_78], rsi
0x18001be67  mov     [rsp+98h+var_70], rdi
0x18001be6c  mov     [rsp+98h+var_68], r15
0x18001be71  mov     [rsp+98h+var_60], rax
0x18001be76  mov     [rsp+98h+var_58], rax
0x18001be7b  mov     rcx, [rsp+98h+arg_10]
0x18001be83  mov     al, [rcx]
0x18001be85  mov     [rbx], al
0x18001be87  mov     al, [rcx+1]
0x18001be8a  mov     [rbx+1], al
0x18001be8d  mov     al, [rcx+2]
0x18001be90  mov     [rbx+2], al
0x18001be93  mov     al, [rcx+3]
0x18001be96  mov     [rbx+3], al
0x18001be99  mov     al, [rcx+4]
0x18001be9c  mov     [rbx+4], al
0x18001be9f  movzx   eax, word ptr [rcx+6]
0x18001bea3  mov     [rbx+6], ax
0x18001bea7  movzx   eax, word ptr [rcx+8]
0x18001beab  mov     [rbx+8], ax
0x18001beaf  lea     rdx, [rcx+10h]
0x18001beb3  lea     rcx, [rbx+10h]
0x18001beb7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001bebc  mov     [rsp+98h+var_60], rbx
0x18001bec1  mov     rdx, [rsi+8]
0x18001bec5  mov     r8, rdi
0x18001bec8  mov     rcx, [rsi]
0x18001becb  cmp     rbp, rdx
0x18001bece  jz      short loc_18001BEE8
0x18001bed0  mov     rdx, rbp
0x18001bed3  call    ??$_Uninitialized_move@PEAUGroupTerminalBlockInternal@WindowsMidiServicesInternal@@V?$allocator@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@@std@@@std@@YAPEAUGroupTerminalBlockInternal@WindowsMidiServicesInternal@@QEAU12@0PEAU12@AEAV?$allocator@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@@0@@Z; std::_Uninitialized_move<WindowsMidiServicesInternal::GroupTerminalBlockInternal *>(WindowsMidiServicesInternal::GroupTerminalBlockInternal * const,WindowsMidiServicesInternal::GroupTerminalBlockInternal * const,WindowsMidiServicesInternal::GroupTerminalBlockInternal *,std::allocator<WindowsMidiServicesInternal::GroupTerminalBlockInternal> &)
0x18001bed8  mov     [rsp+98h+var_60], rdi
0x18001bedd  lea     r8, [rbx+30h]
0x18001bee1  mov     rdx, [rsi+8]
0x18001bee5  mov     rcx, rbp
0x18001bee8  call    ??$_Uninitialized_move@PEAUGroupTerminalBlockInternal@WindowsMidiServicesInternal@@V?$allocator@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@@std@@@std@@YAPEAUGroupTerminalBlockInternal@WindowsMidiServicesInternal@@QEAU12@0PEAU12@AEAV?$allocator@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@@0@@Z; std::_Uninitialized_move<WindowsMidiServicesInternal::GroupTerminalBlockInternal *>(WindowsMidiServicesInternal::GroupTerminalBlockInternal * const,WindowsMidiServicesInternal::GroupTerminalBlockInternal * const,WindowsMidiServicesInternal::GroupTerminalBlockInternal *,std::allocator<WindowsMidiServicesInternal::GroupTerminalBlockInternal> &)
0x18001beed  mov     [rsp+98h+var_70], 0
0x18001bef6  mov     rbx, [rsi]
0x18001bef9  test    rbx, rbx
0x18001befc  jz      short loc_18001BF6C
0x18001befe  mov     rbp, [rsi+8]
0x18001bf02  jmp     short loc_18001BF11
0x18001bf04  lea     rcx, [rbx+10h]; void *
0x18001bf08  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bf0d  add     rbx, 30h ; '0'
0x18001bf11  cmp     rbx, rbp
0x18001bf14  jnz     short loc_18001BF04
0x18001bf16  mov     rcx, [rsi]
0x18001bf19  mov     rax, [rsi+10h]
0x18001bf1d  sub     rax, rcx
0x18001bf20  sar     rax, 4
0x18001bf24  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18001bf2e  imul    rax, rdx
0x18001bf32  lea     rdx, [rax+rax*2]
0x18001bf36  shl     rdx, 4
0x18001bf3a  cmp     rdx, 1000h
0x18001bf41  jb      short loc_18001BF61
0x18001bf43  mov     rax, [rcx-8]
0x18001bf47  sub     rcx, rax
0x18001bf4a  sub     rcx, 8
0x18001bf4e  cmp     rcx, 1Fh
0x18001bf52  ja      short loc_18001BF5A
0x18001bf54  add     rdx, 27h ; '''
0x18001bf58  jmp     short loc_18001BF64
0x18001bf5a  mov     ecx, 5
0x18001bf5f  int     29h; Win8: RtlFailFast(ecx)
0x18001bf61  mov     rax, rcx
0x18001bf64  mov     rcx, rax; Block
0x18001bf67  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001bf6c  mov     [rsi], rdi
0x18001bf6f  lea     rax, [r12+r12*2]
0x18001bf73  shl     rax, 4
0x18001bf77  add     rax, rdi
0x18001bf7a  mov     [rsi+8], rax
0x18001bf7e  lea     rax, [r14+rdi]
0x18001bf82  mov     [rsi+10h], rax
0x18001bf86  lea     rbx, ds:0[r13*2]
0x18001bf8e  add     rbx, r13
0x18001bf91  shl     rbx, 4
0x18001bf95  add     rbx, rdi
0x18001bf98  lea     rcx, [rsp+98h+var_78]
0x18001bf9d  call    ??1_Reallocation_guard@?$vector@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@V?$allocator@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@@std@@@std@@QEAA@XZ; std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001bfa2  mov     rax, rbx
0x18001bfa5  add     rsp, 58h
0x18001bfa9  pop     r15
0x18001bfab  pop     r14
0x18001bfad  pop     r13
0x18001bfaf  pop     r12
0x18001bfb1  pop     rdi
0x18001bfb2  pop     rsi
0x18001bfb3  pop     rbp
0x18001bfb4  pop     rbx
0x18001bfb5  retn
0x18001bfb6  call    ?_Xlength@?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@CAXXZ; std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::_Xlength(void)
0x18001bfbc  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
