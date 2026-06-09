# StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,wchar_t const *,Common::AutoArray<wchar_t,&Common::AutoArrayDeallocate<wchar_t>(wchar_t *)> &)

- ea: `0x180104d04`
- end: `0x180104ebb`
- name: `?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W1AEAV?$AutoArray@_W$1??$AutoArrayDeallocate@_W@Common@@YAXPEA_W@Z@4@@Z`
- size: `439`
- prototype: `__int64 __fastcall(Common::RegistryKey *this, unsigned __int16 *, _WORD *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180104754`
- `0x1801052a8`

## callees

- `0x1800038f0`
- `0x1800e4c28`
- `0x1800eabf4`
- `0x1800edb2c`
- `0x180104d04`
- `0x1801095b8`

## string_xrefs

- `0x180104d61`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180104ea9`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::GetSetting(
        Common::RegistryKey *this,
        unsigned __int16 *a2,
        _WORD *a3,
        void **a4)
{
  unsigned __int16 *v8; // rbx
  __int64 v9; // rdx
  __int64 result; // rax
  __int64 v11; // rbx
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rax
  void *v14; // rbp
  _WORD *v15; // rdx
  __int64 v16; // r9
  __int64 v17; // rax
  _WORD *v18; // rcx
  int v19; // [rsp+20h] [rbp-48h]
  unsigned int *v20; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned int v22; // [rsp+88h] [rbp+20h] BYREF

  v22 = 260;
  v8 = (unsigned __int16 *)operator new[](0x208u, (const struct std::nothrow_t *)&std::nothrow);
  if ( *a4 == v8 )
  {
    v8 = (unsigned __int16 *)*a4;
  }
  else
  {
    operator delete(*a4);
    *a4 = v8;
  }
  if ( !v8 )
  {
    v9 = 1359;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)0x8007000ELL,
      v19);
    return 2147942414LL;
  }
  result = Common::RegistryKey::GetStringValue(this, a2, 0x104u, &v22, v8, v20);
  if ( (int)result >= 0 )
    return 0;
  if ( (unsigned int)(result + 2147024894) > 1 )
    return result;
  if ( a3 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a3[v11] );
    v12 = v11 + 1;
    if ( v12 > v22 )
    {
      v13 = 2 * v12;
      if ( !is_mul_ok(v12, 2u) )
        v13 = -1;
      v14 = operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
      if ( *a4 == v14 )
      {
        v14 = *a4;
      }
      else
      {
        operator delete(*a4);
        *a4 = v14;
      }
      if ( !v14 )
      {
        v9 = 1378;
        goto LABEL_6;
      }
    }
    v15 = *a4;
    if ( v12 )
    {
      if ( v12 <= 0x7FFFFFFF )
      {
        v17 = 2147483646;
        do
        {
          if ( !v17 )
            break;
          if ( !*a3 )
            break;
          *v15++ = *a3++;
          --v17;
          --v12;
        }
        while ( v12 );
        v18 = v15 - 1;
        v16 = v12 == 0 ? 0x8007007A : 0;
        if ( v12 )
          v18 = v15;
        *v18 = 0;
        if ( v12 )
          return 0;
      }
      else
      {
        v16 = 2147942487LL;
        *v15 = 0;
      }
    }
    else
    {
      v16 = 2147942487LL;
    }
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x564,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)v16,
      v19);
  }
  if ( *a4 )
  {
    operator delete(*a4);
    *a4 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180104d04  mov     rax, rsp
0x180104d07  push    rbx
0x180104d08  push    rbp
0x180104d09  push    rsi
0x180104d0a  push    rdi
0x180104d0b  push    r14
0x180104d0d  push    r15
0x180104d0f  sub     rsp, 38h
0x180104d13  mov     rbp, rdx
0x180104d16  mov     dword ptr [rax+20h], 104h
0x180104d1d  mov     r14, rcx
0x180104d20  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180104d27  mov     ecx, 208h; unsigned __int64
0x180104d2c  mov     rdi, r9
0x180104d2f  mov     rsi, r8
0x180104d32  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180104d37  mov     rbx, rax
0x180104d3a  cmp     [rdi], rax
0x180104d3d  jz      short loc_180104D4C
0x180104d3f  mov     rcx, [rdi]; Block
0x180104d42  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180104d47  mov     [rdi], rbx
0x180104d4a  jmp     short loc_180104D4F
0x180104d4c  mov     rbx, [rdi]
0x180104d4f  xor     r15d, r15d
0x180104d52  test    rbx, rbx
0x180104d55  jnz     short loc_180104D79
0x180104d57  mov     edx, 54Fh; void *
0x180104d5c  mov     rcx, [rsp+68h]; this
0x180104d61  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180104d68  mov     ebx, 8007000Eh
0x180104d6d  mov     r9d, ebx; char *
0x180104d70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180104d75  mov     eax, ebx
0x180104d77  jmp     short loc_180104DBD
0x180104d79  lea     r9, [rsp+68h+arg_18]; unsigned int *
0x180104d81  mov     [rsp+68h+var_48], rbx; int
0x180104d86  mov     r8d, 104h; unsigned int
0x180104d8c  mov     rdx, rbp; unsigned __int16 *
0x180104d8f  mov     rcx, r14; this
0x180104d92  call    ?GetStringValue@RegistryKey@Common@@QEAAJPEBGKPEAKPEAG1@Z; Common::RegistryKey::GetStringValue(ushort const *,ulong,ulong *,ushort *,ulong *)
0x180104d97  test    eax, eax
0x180104d99  jns     short loc_180104DBB
0x180104d9b  lea     ecx, [rax+7FF8FFFEh]
0x180104da1  cmp     ecx, 1
0x180104da4  ja      short loc_180104DBD
0x180104da6  test    rsi, rsi
0x180104da9  jnz     short loc_180104DCA
0x180104dab  mov     rcx, [rdi]; Block
0x180104dae  test    rcx, rcx
0x180104db1  jz      short loc_180104DBB
0x180104db3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180104db8  mov     [rdi], r15
0x180104dbb  xor     eax, eax
0x180104dbd  add     rsp, 38h
0x180104dc1  pop     r15
0x180104dc3  pop     r14
0x180104dc5  pop     rdi
0x180104dc6  pop     rsi
0x180104dc7  pop     rbp
0x180104dc8  pop     rbx
0x180104dc9  retn
0x180104dca  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180104dce  mov     rbx, rcx
0x180104dd1  inc     rbx
0x180104dd4  cmp     [rsi+rbx*2], r15w
0x180104dd9  jnz     short loc_180104DD1
0x180104ddb  mov     eax, [rsp+68h+arg_18]
0x180104de2  inc     rbx
0x180104de5  cmp     rbx, rax
0x180104de8  jbe     short loc_180104E2C
0x180104dea  mov     eax, 2
0x180104def  mul     rbx
0x180104df2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180104df9  cmovb   rax, rcx
0x180104dfd  mov     rcx, rax; unsigned __int64
0x180104e00  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180104e05  mov     rbp, rax
0x180104e08  cmp     [rdi], rax
0x180104e0b  jz      short loc_180104E1A
0x180104e0d  mov     rcx, [rdi]; Block
0x180104e10  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180104e15  mov     [rdi], rbp
0x180104e18  jmp     short loc_180104E1D
0x180104e1a  mov     rbp, [rdi]
0x180104e1d  test    rbp, rbp
0x180104e20  jnz     short loc_180104E2C
0x180104e22  mov     edx, 562h
0x180104e27  jmp     loc_180104D5C
0x180104e2c  mov     rdx, [rdi]
0x180104e2f  test    rbx, rbx
0x180104e32  jz      short loc_180104E95
0x180104e34  cmp     rbx, 7FFFFFFFh
0x180104e3b  jbe     short loc_180104E45
0x180104e3d  mov     r9d, 80070057h
0x180104e43  jmp     short loc_180104EA0
0x180104e45  mov     eax, 7FFFFFFEh
0x180104e4a  test    rax, rax
0x180104e4d  jz      short loc_180104E6B
0x180104e4f  movzx   ecx, word ptr [rsi]
0x180104e52  test    cx, cx
0x180104e55  jz      short loc_180104E6B
0x180104e57  mov     [rdx], cx
0x180104e5a  add     rsi, 2
0x180104e5e  add     rdx, 2
0x180104e62  dec     rax
0x180104e65  sub     rbx, 1
0x180104e69  jnz     short loc_180104E4A
0x180104e6b  mov     rax, rbx
0x180104e6e  lea     rcx, [rdx-2]
0x180104e72  neg     rax
0x180104e75  sbb     r9d, r9d
0x180104e78  not     r9d
0x180104e7b  and     r9d, 8007007Ah
0x180104e82  test    rbx, rbx
0x180104e85  cmovnz  rcx, rdx
0x180104e89  mov     [rcx], r15w
0x180104e8d  jnz     loc_180104DBB
0x180104e93  jmp     short loc_180104EA4
0x180104e95  mov     r9d, 80070057h; char *
0x180104e9b  test    rbx, rbx
0x180104e9e  jz      short loc_180104EA4
0x180104ea0  mov     [rdx], r15w
0x180104ea4  mov     rcx, [rsp+68h]; this
0x180104ea9  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180104eb0  mov     edx, 564h; void *
0x180104eb5  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
