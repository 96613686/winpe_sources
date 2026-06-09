# StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,ushort const *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> &)

- ea: `0x18002393c`
- end: `0x180023abc`
- name: `?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG1AEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@4@@Z`
- size: `384`
- prototype: `__int64 __fastcall(Common::RegistryKey *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800236c4`
- `0x180023ccc`

## callees

- `0x1800041cc`
- `0x180007f28`
- `0x18000a3c0`
- `0x18000a77c`
- `0x18000c584`
- `0x180014ca0`
- `0x18002393c`
- `0x18002c0c4`

## string_xrefs

- `0x180023999`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180023aa7`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::GetSetting(
        Common::RegistryKey *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        void **a4)
{
  BYTE *v8; // rdi
  __int64 v9; // rdx
  int StringValue; // eax
  unsigned int v12; // edi
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned __int64 v15; // rsi
  unsigned __int64 v16; // rax
  void *v17; // rdi
  int v18; // eax
  int v19; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned int v21; // [rsp+88h] [rbp+20h] BYREF

  v21 = 260;
  v8 = (BYTE *)operator new[](0x208u, (const struct std::nothrow_t *)&std::nothrow);
  if ( *a4 == v8 )
  {
    v8 = (BYTE *)*a4;
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
  StringValue = Common::RegistryKey::GetStringValue(this, a2, 0x104u, &v21, v8, 0);
  v12 = StringValue;
  if ( StringValue >= 0 )
    return 0;
  v13 = (unsigned int)(StringValue + 2147024894);
  if ( (unsigned int)v13 <= 1 )
  {
    if ( a3 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a3[v14] );
      v15 = v14 + 1;
      if ( v14 + 1 > (unsigned __int64)v21 )
      {
        v16 = 2 * v15;
        if ( !is_mul_ok(v15, 2u) )
          v16 = -1;
        v17 = operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
        if ( *a4 == v17 )
        {
          v17 = *a4;
        }
        else
        {
          operator delete(*a4);
          *a4 = v17;
        }
        if ( !v17 )
        {
          v9 = 1378;
          goto LABEL_6;
        }
      }
      v18 = StringCchCopyW((unsigned __int16 *)*a4, v15, a3);
      if ( v18 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x564,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
          (const char *)(unsigned int)v18,
          v19);
    }
    else if ( *a4 )
    {
      operator delete(*a4);
      *a4 = 0;
    }
    return 0;
  }
  if ( (Microsoft_Windows_StateRepositoryEnableBits & 1) != 0 )
    McTemplateU0dz_EventWriteTransfer(v13, ReadSettingError, (unsigned int)StringValue, a2);
  return v12;
}

```

## disassembly

```asm
0x18002393c  mov     rax, rsp
0x18002393f  push    rbx
0x180023940  push    rbp
0x180023941  push    rsi
0x180023942  push    rdi
0x180023943  push    r14
0x180023945  push    r15
0x180023947  sub     rsp, 38h
0x18002394b  mov     rsi, rdx
0x18002394e  mov     dword ptr [rax+20h], 104h
0x180023955  mov     r14, rcx
0x180023958  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002395f  mov     ecx, 208h; unsigned __int64
0x180023964  mov     rbx, r9
0x180023967  mov     rbp, r8
0x18002396a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002396f  mov     rdi, rax
0x180023972  cmp     [rbx], rax
0x180023975  jz      short loc_180023984
0x180023977  mov     rcx, [rbx]; Block
0x18002397a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002397f  mov     [rbx], rdi
0x180023982  jmp     short loc_180023987
0x180023984  mov     rdi, [rbx]
0x180023987  xor     r15d, r15d
0x18002398a  test    rdi, rdi
0x18002398d  jnz     short loc_1800239B1
0x18002398f  mov     edx, 54Fh; void *
0x180023994  mov     rcx, [rsp+68h]; this
0x180023999  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x1800239a0  mov     ebx, 8007000Eh
0x1800239a5  mov     r9d, ebx; char *
0x1800239a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800239ad  mov     eax, ebx
0x1800239af  jmp     short loc_180023A1B
0x1800239b1  mov     [rsp+68h+lpType], r15; lpType
0x1800239b6  lea     r9, [rsp+68h+arg_18]; unsigned int *
0x1800239be  mov     r8d, 104h; unsigned int
0x1800239c4  mov     [rsp+68h+var_48], rdi; int
0x1800239c9  mov     rdx, rsi; unsigned __int16 *
0x1800239cc  mov     rcx, r14; this
0x1800239cf  call    ?GetStringValue@RegistryKey@Common@@QEAAJPEBGKPEAKPEAG1@Z; Common::RegistryKey::GetStringValue(ushort const *,ulong,ulong *,ushort *,ulong *)
0x1800239d4  mov     edi, eax
0x1800239d6  test    eax, eax
0x1800239d8  jns     short loc_180023A19
0x1800239da  lea     ecx, [rax+7FF8FFFEh]
0x1800239e0  cmp     ecx, 1
0x1800239e3  jbe     short loc_180023A04
0x1800239e5  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 1
0x1800239ec  jz      short loc_180023A00
0x1800239ee  mov     r9, rsi
0x1800239f1  lea     rdx, ReadSettingError
0x1800239f8  mov     r8d, eax
0x1800239fb  call    McTemplateU0dz_EventWriteTransfer
0x180023a00  mov     eax, edi
0x180023a02  jmp     short loc_180023A1B
0x180023a04  test    rbp, rbp
0x180023a07  jnz     short loc_180023A28
0x180023a09  mov     rcx, [rbx]; Block
0x180023a0c  test    rcx, rcx
0x180023a0f  jz      short loc_180023A19
0x180023a11  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023a16  mov     [rbx], r15
0x180023a19  xor     eax, eax
0x180023a1b  add     rsp, 38h
0x180023a1f  pop     r15
0x180023a21  pop     r14
0x180023a23  pop     rdi
0x180023a24  pop     rsi
0x180023a25  pop     rbp
0x180023a26  pop     rbx
0x180023a27  retn
0x180023a28  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180023a2c  mov     rax, rcx
0x180023a2f  inc     rax
0x180023a32  cmp     [rbp+rax*2+0], r15w
0x180023a38  jnz     short loc_180023A2F
0x180023a3a  lea     rsi, [rax+1]
0x180023a3e  mov     eax, [rsp+68h+arg_18]
0x180023a45  cmp     rsi, rax
0x180023a48  jbe     short loc_180023A8C
0x180023a4a  mov     eax, 2
0x180023a4f  mul     rsi
0x180023a52  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023a59  cmovb   rax, rcx
0x180023a5d  mov     rcx, rax; unsigned __int64
0x180023a60  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180023a65  mov     rdi, rax
0x180023a68  cmp     [rbx], rax
0x180023a6b  jz      short loc_180023A7A
0x180023a6d  mov     rcx, [rbx]; Block
0x180023a70  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023a75  mov     [rbx], rdi
0x180023a78  jmp     short loc_180023A7D
0x180023a7a  mov     rdi, [rbx]
0x180023a7d  test    rdi, rdi
0x180023a80  jnz     short loc_180023A8C
0x180023a82  mov     edx, 562h
0x180023a87  jmp     loc_180023994
0x180023a8c  mov     rcx, [rbx]; unsigned __int16 *
0x180023a8f  mov     r8, rbp; unsigned __int16 *
0x180023a92  mov     rdx, rsi; unsigned __int64
0x180023a95  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180023a9a  test    eax, eax
0x180023a9c  jns     loc_180023A19
0x180023aa2  mov     rcx, [rsp+68h]; this
0x180023aa7  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x180023aae  mov     r9d, eax; char *
0x180023ab1  mov     edx, 564h; void *
0x180023ab6  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
