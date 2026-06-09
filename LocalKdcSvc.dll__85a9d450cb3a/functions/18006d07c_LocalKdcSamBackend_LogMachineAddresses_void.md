# LocalKdcSamBackend::LogMachineAddresses(void)

- ea: `0x18006d07c`
- end: `0x18006d1fa`
- name: `?LogMachineAddresses@LocalKdcSamBackend@@QEAAXXZ`
- size: `382`
- prototype: `void __fastcall(LocalKdcSamBackend *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006d2e0`

## callees

- `0x180002f00`
- `0x180003908`
- `0x18000aab8`
- `0x18000e9e8`
- `0x18000eae0`
- `0x18006d07c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18006d1ce`
- `ntdll!EtwEventWrite` at `0x18006d1ce`

## pseudocode

```c
void __fastcall LocalKdcSamBackend::LogMachineAddresses(LocalKdcSamBackend *this)
{
  unsigned int v2; // r15d
  unsigned __int64 v3; // rdi
  unsigned int **v4; // rax
  unsigned int **v5; // rbx
  unsigned int v6; // esi
  __int64 v7; // rax
  __int64 v8; // rdi
  unsigned int *v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  const struct std::nothrow_t *v14; // rdx
  unsigned int *v15; // [rsp+20h] [rbp-20h] BYREF
  unsigned int *v16; // [rsp+28h] [rbp-18h]
  _WORD v17[8]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+70h] [rbp+30h] BYREF
  unsigned int **v19; // [rsp+78h] [rbp+38h] BYREF

  v18 = (__int64)(*((_QWORD *)this + 10) - *((_QWORD *)this + 9)) >> 5;
  v2 = v18 + 2;
  v3 = 16LL * (v18 + 2);
  if ( !is_mul_ok(v18 + 2, 0x10u) )
    v3 = -1;
  v4 = (unsigned int **)operator new[](v3, (const struct std::nothrow_t *)std::nothrow);
  v5 = v4;
  if ( v4 )
    memset_0(v4, 0, v3);
  else
    v5 = 0;
  v19 = v5;
  v15 = (unsigned int *)v17;
  v6 = 0;
  v16 = (unsigned int *)v17;
  v17[0] = 0;
  *v5 = &v18;
  v5[1] = (unsigned int *)4;
  while ( v6 < v18 )
  {
    v7 = *((_QWORD *)this + 9);
    v8 = 32LL * v6;
    v9 = *(unsigned int **)(v8 + v7);
    v10 = (__int64)(*(_QWORD *)(v8 + v7 + 8) - (_QWORD)v9) >> 1;
    v11 = 2LL * ++v6;
    v5[v11] = v9;
    v5[v11 + 1] = (unsigned int *)(unsigned int)(2 * v10 + 2);
    if ( v15 != v16 )
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
        &v15,
        L", ",
        2);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
      &v15,
      *(_QWORD *)(v8 + *((_QWORD *)this + 9)),
      (__int64)(*(_QWORD *)(v8 + *((_QWORD *)this + 9) + 8) - *(_QWORD *)(v8 + *((_QWORD *)this + 9))) >> 1);
  }
  v12 = 2LL * (v2 - 1);
  v13 = ((char *)v16 - (char *)v15) >> 1;
  v5[v12] = v15;
  HIDWORD(v5[v12 + 1]) = 0;
  LODWORD(v5[v12 + 1]) = 2 * v13 + 2;
  EtwEventWrite(S_Microsoft_Windows_Kerberos_Key_Distribution_Center_Context, MachineAddresses, v2, v5);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((void **)&v15);
  utl::unique_ptr<unsigned long [0],utl::default_delete<unsigned long [0]>>::~unique_ptr<unsigned long [0],utl::default_delete<unsigned long [0]>>(
    (void **)&v19,
    v14);
}

```

## disassembly

```asm
0x18006d07c  mov     [rsp-28h+arg_10], rbx
0x18006d081  push    rbp
0x18006d082  push    rsi
0x18006d083  push    rdi
0x18006d084  push    r14
0x18006d086  push    r15
0x18006d088  mov     rbp, rsp
0x18006d08b  sub     rsp, 40h
0x18006d08f  mov     rax, [rcx+50h]
0x18006d093  mov     r14, rcx
0x18006d096  sub     rax, [rcx+48h]
0x18006d09a  sar     rax, 5
0x18006d09e  mov     [rbp+arg_0], eax
0x18006d0a1  lea     r15d, [rax+2]
0x18006d0a5  mov     eax, 10h
0x18006d0aa  mov     edx, r15d
0x18006d0ad  mul     rdx
0x18006d0b0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006d0b7  mov     rdi, rax
0x18006d0ba  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18006d0c1  cmovb   rdi, rax
0x18006d0c5  mov     rcx, rdi; unsigned __int64
0x18006d0c8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006d0cd  mov     rbx, rax
0x18006d0d0  test    rax, rax
0x18006d0d3  jz      short loc_18006D0E4
0x18006d0d5  mov     r8, rdi; Size
0x18006d0d8  xor     edx, edx; Val
0x18006d0da  mov     rcx, rax; void *
0x18006d0dd  call    memset_0
0x18006d0e2  jmp     short loc_18006D0E6
0x18006d0e4  xor     ebx, ebx
0x18006d0e6  lea     rax, [rbp+var_10]
0x18006d0ea  mov     [rbp+arg_8], rbx
0x18006d0ee  mov     [rbp+var_20], rax
0x18006d0f2  xor     esi, esi
0x18006d0f4  lea     rax, [rbp+var_10]
0x18006d0f8  mov     [rbp+var_18], rax
0x18006d0fc  xor     eax, eax
0x18006d0fe  mov     [rbp+var_10], ax
0x18006d102  lea     rax, [rbp+arg_0]
0x18006d106  mov     [rbx], rax
0x18006d109  mov     qword ptr [rbx+8], 4
0x18006d111  cmp     [rbp+arg_0], esi
0x18006d114  jbe     short loc_18006D18E
0x18006d116  mov     rax, [r14+48h]
0x18006d11a  mov     edi, esi
0x18006d11c  shl     rdi, 5
0x18006d120  mov     rdx, [rdi+rax]
0x18006d124  mov     rcx, [rdi+rax+8]
0x18006d129  sub     rcx, rdx
0x18006d12c  sar     rcx, 1
0x18006d12f  inc     esi
0x18006d131  mov     eax, esi
0x18006d133  add     rax, rax
0x18006d136  lea     ecx, ds:2[rcx*2]
0x18006d13d  mov     [rbx+rax*8], rdx
0x18006d141  mov     [rbx+rax*8+8], ecx
0x18006d145  mov     dword ptr [rbx+rax*8+0Ch], 0
0x18006d14d  mov     rax, [rbp+var_18]
0x18006d151  cmp     [rbp+var_20], rax
0x18006d155  jz      short loc_18006D16D
0x18006d157  mov     r8d, 2
0x18006d15d  lea     rdx, asc_1800A1958; ", "
0x18006d164  lea     rcx, [rbp+var_20]
0x18006d168  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18006d16d  mov     rax, [r14+48h]
0x18006d171  lea     rcx, [rbp+var_20]
0x18006d175  mov     rdx, [rdi+rax]
0x18006d179  mov     r8, [rdi+rax+8]
0x18006d17e  sub     r8, rdx
0x18006d181  sar     r8, 1
0x18006d184  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18006d189  cmp     esi, [rbp+arg_0]
0x18006d18c  jb      short loc_18006D116
0x18006d18e  mov     rax, [rbp+var_18]
0x18006d192  lea     ecx, [r15-1]
0x18006d196  mov     r10, [rbp+var_20]
0x18006d19a  add     rcx, rcx
0x18006d19d  sub     rax, r10
0x18006d1a0  mov     r9, rbx
0x18006d1a3  sar     rax, 1
0x18006d1a6  mov     r8d, r15d
0x18006d1a9  mov     [rbx+rcx*8], r10
0x18006d1ad  mov     dword ptr [rbx+rcx*8+0Ch], 0
0x18006d1b5  lea     edx, ds:2[rax*2]
0x18006d1bc  mov     [rbx+rcx*8+8], edx
0x18006d1c0  lea     rdx, MachineAddresses
0x18006d1c7  mov     rcx, cs:S_Microsoft_Windows_Kerberos_Key_Distribution_Center_Context
0x18006d1ce  call    cs:__imp_EtwEventWrite
0x18006d1d4  lea     rcx, [rbp+var_20]
0x18006d1d8  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18006d1dd  lea     rcx, [rbp+arg_8]
0x18006d1e1  call    ??1?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ulong [0],utl::default_delete<ulong [0]>>::~unique_ptr<ulong [0],utl::default_delete<ulong [0]>>(void)
0x18006d1e6  mov     rbx, [rsp+40h+arg_10]
0x18006d1ee  add     rsp, 40h
0x18006d1f2  pop     r15
0x18006d1f4  pop     r14
0x18006d1f6  pop     rdi
0x18006d1f7  pop     rsi
0x18006d1f8  pop     rbp
0x18006d1f9  retn
```
