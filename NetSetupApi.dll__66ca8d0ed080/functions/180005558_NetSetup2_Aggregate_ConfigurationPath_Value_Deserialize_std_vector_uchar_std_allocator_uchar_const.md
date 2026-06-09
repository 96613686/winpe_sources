# NetSetup2::Aggregate::ConfigurationPath_Value::Deserialize(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x180005558`
- end: `0x180005773`
- name: `?Deserialize@ConfigurationPath_Value@Aggregate@NetSetup2@@QEAAXAEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `539`
- prototype: `void __fastcall(__int64, __int64, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000edd0`

## callees

- `0x180005558`
- `0x1800059dc`
- `0x180006688`
- `0x180007274`
- `0x180007eb0`
- `0x1800080d4`
- `0x18000895c`

## pseudocode

```c
void __fastcall NetSetup2::Aggregate::ConfigurationPath_Value::Deserialize(
        __int64 a1,
        __int64 a2,
        const unsigned __int8 *a3)
{
  _DWORD *v4; // rdi
  unsigned __int64 v5; // r9
  unsigned __int64 v6; // rax
  __int64 i; // rdx
  unsigned int v8; // r10d
  char *v9; // rcx
  int v10; // ebx
  __int64 v11; // rsi
  const unsigned __int8 *v12; // r8
  unsigned __int64 v13; // rsi
  char *v14; // rbx
  void *Block[3]; // [rsp+28h] [rbp-28h] BYREF
  unsigned __int64 v16; // [rsp+40h] [rbp-10h]
  int pExceptionObject; // [rsp+78h] [rbp+28h] BYREF

  v4 = *(_DWORD **)a2;
  v5 = *(_QWORD *)(a2 + 8);
  v6 = v5 - *(_QWORD *)a2;
  if ( v6 < 4 )
  {
    pExceptionObject = 13;
    throw (long *)&pExceptionObject;
  }
  if ( *v4 != 2 )
  {
    pExceptionObject = 13;
    throw (long *)&pExceptionObject;
  }
  if ( v6 - 4 < 0x18 )
  {
    pExceptionObject = 13;
    throw (long *)&pExceptionObject;
  }
  for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
  {
    a3 = (const unsigned __int8 *)&v4[2 * i + 1 + (unsigned int)i];
    v8 = *((_DWORD *)a3 + 1) + *((_DWORD *)a3 + 2);
    if ( v8 < *((_DWORD *)a3 + 1) )
    {
      pExceptionObject = 13;
      throw (long *)&pExceptionObject;
    }
    v9 = (char *)&a3[v8];
    if ( v9 < (char *)a3 )
    {
      pExceptionObject = 13;
      throw (long *)&pExceptionObject;
    }
    if ( (unsigned __int64)v9 > v5 )
    {
      pExceptionObject = 13;
      throw (long *)&pExceptionObject;
    }
  }
  if ( v4[1] != 7 )
  {
    pExceptionObject = 13;
    throw (long *)&pExceptionObject;
  }
  v10 = v4[2];
  v11 = (unsigned int)v4[3];
  NetSetup2::Aggregate::details::EnsureAlignedTo((NetSetup2::Aggregate::details *)4, (unsigned __int64)v4 + v11 + 4, a3);
  if ( v10 != 4 )
  {
    pExceptionObject = -2147024883;
    throw (long *)&pExceptionObject;
  }
  *(_DWORD *)a1 = *(_DWORD *)((char *)v4 + v11 + 4);
  if ( v4[4] != 18 )
  {
    pExceptionObject = 13;
    throw (long *)&pExceptionObject;
  }
  v13 = (unsigned int)v4[5];
  v14 = (char *)v4 + (unsigned int)v4[6] + 16;
  NetSetup2::Aggregate::details::EnsureAlignedTo((NetSetup2::Aggregate::details *)2, (unsigned __int64)v14, v12);
  v16 = 7;
  Block[2] = 0;
  LOWORD(Block[0]) = 0;
  if ( v14 != &v14[2 * (v13 >> 1)] )
    std::wstring::assign(Block, v14);
  if ( (void **)(a1 + 8) != Block )
  {
    std::wstring::_Tidy((void **)(a1 + 8), 1, 0);
    std::wstring::_Assign_rv(a1 + 8, Block);
  }
  if ( v16 >= 8 )
    operator delete(Block[0]);
}

```

## disassembly

```asm
0x180005558  mov     rax, rsp
0x18000555b  push    rbp
0x18000555c  push    rdi
0x18000555d  push    r14
0x18000555f  mov     rbp, rsp
0x180005562  sub     rsp, 50h
0x180005566  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18000556e  mov     [rax+8], rbx
0x180005572  mov     [rax+18h], rsi
0x180005576  mov     r14, rcx
0x180005579  mov     rdi, [rdx]
0x18000557c  mov     r9, [rdx+8]
0x180005580  mov     rax, r9
0x180005583  sub     rax, rdi
0x180005586  cmp     rax, 4
0x18000558a  jnb     short loc_1800055A4
0x18000558c  mov     [rbp+pExceptionObject], 0Dh
0x180005593  lea     rdx, _TI1J; pThrowInfo
0x18000559a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000559e  call    _CxxThrowException_0
0x1800055a4  cmp     dword ptr [rdi], 2
0x1800055a7  jz      short loc_1800055C1
0x1800055a9  mov     [rbp+pExceptionObject], 0Dh
0x1800055b0  lea     rdx, _TI1J; pThrowInfo
0x1800055b7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800055bb  call    _CxxThrowException_0
0x1800055c1  add     rax, 0FFFFFFFFFFFFFFFCh
0x1800055c5  cmp     rax, 18h
0x1800055c9  jnb     short loc_1800055E3
0x1800055cb  mov     [rbp+pExceptionObject], 0Dh
0x1800055d2  lea     rdx, _TI1J; pThrowInfo
0x1800055d9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800055dd  call    _CxxThrowException_0
0x1800055e3  xor     edx, edx
0x1800055e5  cmp     edx, 2
0x1800055e8  jnb     short loc_180005665
0x1800055ea  mov     eax, edx
0x1800055ec  lea     r8, ds:1[rdx*2]
0x1800055f4  add     r8, rax
0x1800055f7  lea     r8, [rdi+r8*4]
0x1800055fb  mov     r10d, [r8+8]
0x1800055ff  add     r10d, [r8+4]
0x180005603  cmp     r10d, [r8+4]
0x180005607  jb      short loc_18000564D
0x180005609  mov     ecx, r10d
0x18000560c  add     rcx, r8
0x18000560f  cmp     rcx, r8
0x180005612  jb      short loc_180005635
0x180005614  cmp     rcx, r9
0x180005617  ja      short loc_18000561D
0x180005619  inc     edx
0x18000561b  jmp     short loc_1800055E5
0x18000561d  mov     [rbp+pExceptionObject], 0Dh
0x180005624  lea     rdx, _TI1J; pThrowInfo
0x18000562b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000562f  call    _CxxThrowException_0
0x180005635  mov     [rbp+pExceptionObject], 0Dh
0x18000563c  lea     rdx, _TI1J; pThrowInfo
0x180005643  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180005647  call    _CxxThrowException_0
0x18000564d  mov     [rbp+pExceptionObject], 0Dh
0x180005654  lea     rdx, _TI1J; pThrowInfo
0x18000565b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000565f  call    _CxxThrowException_0
0x180005665  cmp     dword ptr [rdi+4], 7
0x180005669  jz      short loc_180005683
0x18000566b  mov     [rbp+pExceptionObject], 0Dh
0x180005672  lea     rdx, _TI1J; pThrowInfo
0x180005679  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000567d  call    _CxxThrowException_0
0x180005683  mov     ebx, [rdi+8]
0x180005686  mov     esi, [rdi+0Ch]
0x180005689  lea     rdx, [rdi+4]
0x18000568d  add     rdx, rsi; unsigned __int64
0x180005690  mov     ecx, 4; this
0x180005695  call    ?EnsureAlignedTo@details@Aggregate@NetSetup2@@YAX_KPEBE@Z; NetSetup2::Aggregate::details::EnsureAlignedTo(unsigned __int64,uchar const *)
0x18000569a  cmp     ebx, 4
0x18000569d  jz      short loc_1800056B7
0x18000569f  mov     [rbp+pExceptionObject], 8007000Dh
0x1800056a6  lea     rdx, _TI1J; pThrowInfo
0x1800056ad  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800056b1  call    _CxxThrowException_0
0x1800056b7  mov     eax, [rsi+rdi+4]
0x1800056bb  mov     [r14], eax
0x1800056be  cmp     dword ptr [rdi+10h], 12h
0x1800056c2  jz      short loc_1800056DC
0x1800056c4  mov     [rbp+pExceptionObject], 0Dh
0x1800056cb  lea     rdx, _TI1J; pThrowInfo
0x1800056d2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800056d6  call    _CxxThrowException_0
0x1800056dc  mov     esi, [rdi+14h]
0x1800056df  mov     ebx, [rdi+18h]
0x1800056e2  add     rbx, 10h
0x1800056e6  add     rbx, rdi
0x1800056e9  mov     rdx, rbx; unsigned __int64
0x1800056ec  mov     ecx, 2; this
0x1800056f1  call    ?EnsureAlignedTo@details@Aggregate@NetSetup2@@YAX_KPEBE@Z; NetSetup2::Aggregate::details::EnsureAlignedTo(unsigned __int64,uchar const *)
0x1800056f6  shr     rsi, 1
0x1800056f9  mov     [rbp+var_10], 7
0x180005701  mov     [rbp+var_18], 0
0x180005709  xor     eax, eax
0x18000570b  mov     word ptr [rbp+Block], ax
0x18000570f  lea     rax, [rbx+rsi*2]
0x180005713  cmp     rbx, rax
0x180005716  jz      short loc_180005727
0x180005718  mov     r8, rsi
0x18000571b  mov     rdx, rbx; Src
0x18000571e  lea     rcx, [rbp+Block]; void *
0x180005722  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@PEB_W_K@Z; std::wstring::assign(wchar_t const *,unsigned __int64)
0x180005727  lea     rbx, [r14+8]
0x18000572b  lea     rax, [rbp+Block]
0x18000572f  cmp     rbx, rax
0x180005732  jz      short loc_18000574E
0x180005734  xor     r8d, r8d
0x180005737  mov     dl, 1
0x180005739  mov     rcx, rbx
0x18000573c  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180005741  lea     rdx, [rbp+Block]
0x180005745  mov     rcx, rbx
0x180005748  call    ?_Assign_rv@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX$$QEAV12@@Z; std::wstring::_Assign_rv(std::wstring &&)
0x18000574d  nop
0x18000574e  cmp     [rbp+var_10], 8
0x180005753  jb      short loc_18000575E
0x180005755  mov     rcx, [rbp+Block]; Block
0x180005759  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000575e  lea     r11, [rsp+50h+var_s0]
0x180005763  mov     rbx, [r11+20h]
0x180005767  mov     rsi, [r11+30h]
0x18000576b  mov     rsp, r11
0x18000576e  pop     r14
0x180005770  pop     rdi
0x180005771  pop     rbp
0x180005772  retn
```
