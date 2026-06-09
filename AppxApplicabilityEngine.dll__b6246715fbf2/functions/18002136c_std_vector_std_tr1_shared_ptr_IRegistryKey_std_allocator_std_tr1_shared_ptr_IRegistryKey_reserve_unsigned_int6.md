# std::vector<std::tr1::shared_ptr<IRegistryKey>,std::allocator<std::tr1::shared_ptr<IRegistryKey>>>::reserve(unsigned __int64)

- ea: `0x18002136c`
- end: `0x180021485`
- name: `?reserve@?$vector@V?$shared_ptr@VIRegistryKey@@@tr1@std@@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@3@@std@@QEAAX_K@Z`
- size: `281`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18002101c`

## callees

- `0x180011a64`
- `0x180011b84`
- `0x180013294`
- `0x1800200a0`
- `0x180020198`
- `0x18002136c`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180021461`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180021461`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002141e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002141e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall std::vector<std::tr1::shared_ptr<IRegistryKey>>::reserve(__int64 *a1, unsigned __int64 a2)
{
  unsigned __int64 result; // rax
  __int64 v4; // rsi
  const char *v5; // rdi
  __int64 v6; // r15
  __int64 v7; // r12
  __int64 v8; // r14
  __int64 v9; // rcx
  _QWORD pExceptionObject[10]; // [rsp+38h] [rbp-50h] BYREF
  char *v11; // [rsp+98h] [rbp+10h] BYREF

  if ( a2 > 0xFFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector<T> too long");
  result = (a1[2] - *a1) >> 4;
  if ( result < a2 )
  {
    v4 = 16 * a2;
    if ( a2 )
    {
      v5 = (const char *)operator new(16 * a2);
      v11 = (char *)v5;
      if ( !v5 )
      {
        v11 = 0;
        exception::exception((exception *)pExceptionObject, (const char *const *)&v11);
        pExceptionObject[0] = &std::bad_alloc::`vftable';
        throw (std::bad_alloc *)pExceptionObject;
      }
    }
    else
    {
      v5 = 0;
      v11 = 0;
    }
    try
    {
      std::_Uninit_move<std::tr1::shared_ptr<IRegistryKey> *,std::tr1::shared_ptr<IRegistryKey> *,std::allocator<std::tr1::shared_ptr<IRegistryKey>>,std::tr1::shared_ptr<IRegistryKey>>(
        *a1,
        a1[1],
        (__int64)v5);
    }
    catch ( ... )
    {
      operator delete(v11);
      throw;
    }
    v6 = *a1;
    v7 = a1[1];
    v8 = v7 - *a1;
    if ( *a1 )
    {
      while ( v6 != v7 )
      {
        std::_Dest_val<std::allocator<std::tr1::shared_ptr<IRegistryKey>>,std::tr1::shared_ptr<IRegistryKey>>(v9, v6);
        v6 += 16;
      }
      operator delete((void *)*a1);
    }
    result = (unsigned __int64)&v5[v4];
    a1[2] = (__int64)&v5[v4];
    a1[1] = (__int64)&v5[v8 & 0xFFFFFFFFFFFFFFF0uLL];
    *a1 = (__int64)v5;
  }
  return result;
}

```

## disassembly

```asm
0x18002136c  push    rbx
0x18002136e  push    rsi
0x18002136f  push    rdi
0x180021370  push    r12
0x180021372  push    r14
0x180021374  push    r15
0x180021376  sub     rsp, 58h
0x18002137a  mov     [rsp+88h+var_58], 0FFFFFFFFFFFFFFFEh
0x180021383  mov     rbx, rcx
0x180021386  mov     rax, 0FFFFFFFFFFFFFFFh
0x180021390  cmp     rdx, rax
0x180021393  jbe     short loc_1800213A2
0x180021395  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x18002139c  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800213a2  mov     rax, [rcx+10h]
0x1800213a6  sub     rax, [rcx]
0x1800213a9  sar     rax, 4
0x1800213ad  cmp     rax, rdx
0x1800213b0  jnb     loc_18002143A
0x1800213b6  mov     rsi, rdx
0x1800213b9  shl     rsi, 4
0x1800213bd  test    rdx, rdx
0x1800213c0  jnz     short loc_1800213CE
0x1800213c2  xor     edi, edi
0x1800213c4  mov     [rsp+88h+arg_8], rdi
0x1800213cc  jmp     short loc_1800213E6
0x1800213ce  mov     rcx, rsi; Size
0x1800213d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800213d6  mov     rdi, rax
0x1800213d9  mov     [rsp+88h+arg_8], rax
0x1800213e1  test    rax, rax
0x1800213e4  jz      short loc_180021448
0x1800213e6  mov     r8, rdi
0x1800213e9  mov     rdx, [rbx+8]
0x1800213ed  mov     rcx, [rbx]
0x1800213f0  call    ??$_Uninit_move@PEAV?$shared_ptr@VIRegistryKey@@@tr1@std@@PEAV123@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@3@V123@@std@@YAPEAV?$shared_ptr@VIRegistryKey@@@tr1@0@PEAV120@00AEAV?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::tr1::shared_ptr<IRegistryKey> *,std::tr1::shared_ptr<IRegistryKey> *,std::allocator<std::tr1::shared_ptr<IRegistryKey>>,std::tr1::shared_ptr<IRegistryKey>>(std::tr1::shared_ptr<IRegistryKey> *,std::tr1::shared_ptr<IRegistryKey> *,std::tr1::shared_ptr<IRegistryKey> *,std::allocator<std::tr1::shared_ptr<IRegistryKey>> &,std::tr1::shared_ptr<IRegistryKey> *,std::_Nonscalar_ptr_iterator_tag)
0x1800213f5  nop
0x1800213f6  mov     r15, [rbx]
0x1800213f9  mov     r12, [rbx+8]
0x1800213fd  mov     r14, r12
0x180021400  sub     r14, r15
0x180021403  test    r15, r15
0x180021406  jz      short loc_180021424
0x180021408  jmp     short loc_180021416
0x18002140a  mov     rdx, r15
0x18002140d  call    ??$_Dest_val@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@std@@V?$shared_ptr@VIRegistryKey@@@tr1@2@@std@@YAXAEAV?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@0@PEAV?$shared_ptr@VIRegistryKey@@@tr1@0@@Z; std::_Dest_val<std::allocator<std::tr1::shared_ptr<IRegistryKey>>,std::tr1::shared_ptr<IRegistryKey>>(std::allocator<std::tr1::shared_ptr<IRegistryKey>> &,std::tr1::shared_ptr<IRegistryKey> *)
0x180021412  add     r15, 10h
0x180021416  cmp     r15, r12
0x180021419  jnz     short loc_18002140A
0x18002141b  mov     rcx, [rbx]
0x18002141e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180021424  lea     rax, [rsi+rdi]
0x180021428  mov     [rbx+10h], rax
0x18002142c  and     r14, 0FFFFFFFFFFFFFFF0h
0x180021430  add     r14, rdi
0x180021433  mov     [rbx+8], r14
0x180021437  mov     [rbx], rdi
0x18002143a  add     rsp, 58h
0x18002143e  pop     r15
0x180021440  pop     r14
0x180021442  pop     r12
0x180021444  pop     rdi
0x180021445  pop     rsi
0x180021446  pop     rbx
0x180021447  retn
0x180021448  mov     [rsp+88h+arg_8], 0
0x180021454  lea     rdx, [rsp+88h+arg_8]
0x18002145c  lea     rcx, [rsp+88h+pExceptionObject]
0x180021461  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180021467  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18002146e  mov     [rsp+88h+pExceptionObject], rax
0x180021473  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18002147a  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18002147f  call    _CxxThrowException_0
```
