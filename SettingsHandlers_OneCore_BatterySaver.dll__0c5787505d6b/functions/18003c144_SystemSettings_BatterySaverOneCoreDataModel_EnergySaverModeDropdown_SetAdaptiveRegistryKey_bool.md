# SystemSettings::BatterySaverOneCoreDataModel::EnergySaverModeDropdown::SetAdaptiveRegistryKey(bool)

- ea: `0x18003c144`
- end: `0x18003c27b`
- name: `?SetAdaptiveRegistryKey@EnergySaverModeDropdown@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJ_N@Z`
- size: `311`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::EnergySaverModeDropdown *__hidden this, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x18003bd30`

## callees

- `0x180009190`
- `0x18000a0f9`
- `0x18000eacc`
- `0x18001155c`
- `0x180034f58`
- `0x18003b49c`
- `0x18003b714`
- `0x18003b7c4`
- `0x18003bb80`
- `0x18003c144`
- `0x18003c388`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18003c18c`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18003c18c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::EnergySaverModeDropdown::SetAdaptiveRegistryKey(
        SystemSettings::BatterySaverOneCoreDataModel::EnergySaverModeDropdown *this,
        unsigned __int8 a2)
{
  unsigned int v2; // ebx
  __int64 *v3; // rax
  SystemSettings::DataModel *v4; // rcx
  const unsigned __int16 *v5; // r8
  __int64 v6; // rbx
  HWND v7; // rdx
  int v8; // ebx
  void *Src; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int64 v11; // [rsp+30h] [rbp-D0h]
  _BYTE v12[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[232]; // [rsp+58h] [rbp-A8h] BYREF
  HWND v15[2]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 v16; // [rsp+150h] [rbp+50h]
  unsigned __int64 v17; // [rsp+158h] [rbp+58h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v2 = a2 ^ 1;
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v12);
  v3 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v13);
  std::basic_ostream<unsigned short>::operator<<(v3, v2);
  *(_OWORD *)v15 = 0;
  v16 = 0;
  v17 = 7;
  LOWORD(v15[0]) = 0;
  std::basic_stringbuf<unsigned short>::_Get_buffer_view(v14, &Src);
  if ( Src )
  {
    if ( v11 > 7 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v15);
    }
    else
    {
      v16 = v11;
      v6 = 2 * v11;
      memmove_0(v15, Src, 2 * v11);
      *(_WORD *)((char *)v15 + v6) = 0;
    }
  }
  v7 = (HWND)v15;
  if ( v17 > 7 )
    v7 = v15[0];
  v8 = SystemSettings::DataModel::ExecuteAdminFlowWait(v4, v7, v5);
  if ( v17 > 7 )
    std::_Deallocate<16>(v15[0], (const struct std::nothrow_t *)(2 * v17 + 2));
  if ( v8 >= 0 )
    v8 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\energysaverdropdown.cpp",
      (const char *)(unsigned int)v8,
      2);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003c144  mov     [rsp-8+arg_0], rbx
0x18003c149  push    rbp
0x18003c14a  lea     rbp, [rsp-70h]
0x18003c14f  sub     rsp, 170h
0x18003c156  mov     rax, cs:__security_cookie
0x18003c15d  xor     rax, rsp
0x18003c160  mov     [rbp+70h+var_10], rax
0x18003c164  mov     [rsp+170h+var_150], 0
0x18003c16c  movzx   ebx, dl
0x18003c16f  xor     ebx, 1
0x18003c172  lea     rcx, [rsp+170h+var_130]
0x18003c177  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18003c17c  nop
0x18003c17d  lea     rcx, [rsp+170h+var_120]
0x18003c182  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18003c187  mov     edx, ebx
0x18003c189  mov     rcx, rax
0x18003c18c  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x18003c192  nop
0x18003c193  xorps   xmm0, xmm0
0x18003c196  movups  xmmword ptr [rbp+70h+var_30], xmm0
0x18003c19a  mov     [rbp+70h+var_20], 0
0x18003c1a2  mov     [rbp+70h+var_18], 7
0x18003c1aa  xor     eax, eax
0x18003c1ac  mov     word ptr [rbp+70h+var_30], ax
0x18003c1b0  mov     [rsp+170h+var_150], 2; int
0x18003c1b8  lea     rdx, [rsp+170h+Src]
0x18003c1bd  lea     rcx, [rsp+170h+var_118]
0x18003c1c2  call    ?_Get_buffer_view@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AU_Buffer_view@12@XZ; std::basic_stringbuf<ushort>::_Get_buffer_view(void)
0x18003c1c7  mov     r9, [rsp+170h+Src]
0x18003c1cc  test    r9, r9
0x18003c1cf  jz      short loc_18003C202
0x18003c1d1  mov     rdx, [rsp+170h+var_140]
0x18003c1d6  lea     rcx, [rbp+70h+var_30]; void *
0x18003c1da  cmp     rdx, 7
0x18003c1de  ja      short loc_18003C1FC
0x18003c1e0  mov     [rbp+70h+var_20], rdx
0x18003c1e4  lea     rbx, [rdx+rdx]
0x18003c1e8  mov     r8, rbx; Size
0x18003c1eb  mov     rdx, r9; Src
0x18003c1ee  call    memmove_0
0x18003c1f3  xor     eax, eax
0x18003c1f5  mov     word ptr [rbp+rbx+70h+var_30], ax
0x18003c1fa  jmp     short loc_18003C202
0x18003c1fc  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18003c201  nop
0x18003c202  lea     rdx, [rbp+70h+var_30]
0x18003c206  cmp     [rbp+70h+var_18], 7
0x18003c20b  cmova   rdx, [rbp+70h+var_30]; HWND
0x18003c210  call    ?ExecuteAdminFlowWait@DataModel@SystemSettings@@YAJPEAUHWND__@@PEBG@Z; SystemSettings::DataModel::ExecuteAdminFlowWait(HWND__ *,ushort const *)
0x18003c215  mov     ebx, eax
0x18003c217  mov     rdx, [rbp+70h+var_18]
0x18003c21b  cmp     rdx, 7
0x18003c21f  jbe     short loc_18003C232
0x18003c221  lea     rdx, ds:2[rdx*2]
0x18003c229  mov     rcx, [rbp+70h+var_30]
0x18003c22d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003c232  test    ebx, ebx
0x18003c234  jns     short loc_18003C250
0x18003c236  mov     rcx, [rbp+78h]; this
0x18003c23a  mov     r9d, ebx; char *
0x18003c23d  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\coresettinghandlers"...
0x18003c244  mov     edx, 0DDh; void *
0x18003c249  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c24e  jmp     short loc_18003C252
0x18003c250  xor     ebx, ebx
0x18003c252  lea     rcx, [rsp+170h+var_130]
0x18003c257  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x18003c25c  mov     eax, ebx
0x18003c25e  mov     rcx, [rbp+70h+var_10]
0x18003c262  xor     rcx, rsp; StackCookie
0x18003c265  call    __security_check_cookie
0x18003c26a  mov     rbx, [rsp+170h+arg_0]
0x18003c272  add     rsp, 170h
0x18003c279  pop     rbp
0x18003c27a  retn
```
