# Output::DisplayErrorResource<ushort const *>(int,std::tuple<rangelib::range<ushort const *>,ushort const *> const &)

- ea: `0x14000641c`
- end: `0x140006531`
- name: `??$DisplayErrorResource@PEBG@Output@@QEBAXHAEBV?$tuple@V?$range@PEBG@rangelib@@PEBG@std@@@Z`
- size: `277`
- prototype: `void __fastcall(__int64, unsigned int, __int64)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x140008784`
- `0x140009434`
- `0x14000f280`
- `0x14000f54c`
- `0x140010a68`

## callees

- `0x1400016a0`
- `0x140001934`
- `0x14000641c`
- `0x140006d94`
- `0x140007210`
- `0x140007778`
- `0x140008150`
- `0x140008454`
- `0x14000a388`
- `0x14000b5b4`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140006450`
- `KERNEL32!GetModuleHandleW` at `0x140006450`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x1400064da`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x1400064da`
- `msvcp_win!?wcerr@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x1400064a6`

## pseudocode

```c
void __fastcall Output::DisplayErrorResource<unsigned short const *>(__int64 a1, unsigned int a2, __int64 a3)
{
  HMODULE ModuleHandleW; // rax
  _QWORD *v6; // rdx
  __int64 *v7; // rax
  unsigned __int64 v8; // rdx
  __int128 v9; // [rsp+20h] [rbp-49h] BYREF
  void *v10; // [rsp+30h] [rbp-39h] BYREF
  int v11; // [rsp+38h] [rbp-31h]
  _BYTE v12[40]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v13[9]; // [rsp+68h] [rbp-1h] BYREF

  v9 = 0;
  ModuleHandleW = GetModuleHandleW(0);
  LoadStringNoThrow(&v10, ModuleHandleW, a2, &v9);
  if ( !v11 )
  {
    HIDWORD(v10) = 3;
    if ( (_DWORD)v10 )
      goto LABEL_6;
  }
  TpmVscMgrMeta::basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
    v12,
    &v9);
  TpmVscMgrMeta::basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::insert<unsigned short const *>(
    v12,
    a3 + 8,
    a3);
  TpmVscMgrMeta::basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::gather(v12);
  v6 = v13;
  if ( v13[3] > 7u )
    v6 = (_QWORD *)v13[0];
  v7 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(
         std::wcerr,
         (__int64)v6,
         v13[2]);
  std::basic_ostream<unsigned short>::operator<<(v7, std::endl<unsigned short,std::char_traits<unsigned short>>);
  TpmVscMgrMeta::basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v12);
  if ( v11 )
  {
    if ( v11 == 1 )
    {
      if ( v10 )
        operator delete(v10, v8);
    }
  }
  else
  {
LABEL_6:
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v10);
  }
}

```

## disassembly

```asm
0x14000641c  mov     [rsp-8+arg_0], rbx
0x140006421  mov     [rsp-8+arg_18], rdi
0x140006426  push    rbp
0x140006427  lea     rbp, [rsp-57h]
0x14000642c  sub     rsp, 0C0h
0x140006433  mov     rax, cs:__security_cookie
0x14000643a  xor     rax, rsp
0x14000643d  mov     [rbp+57h+var_10], rax
0x140006441  mov     rdi, r8
0x140006444  mov     ebx, edx
0x140006446  xorps   xmm0, xmm0
0x140006449  movdqa  [rbp+57h+var_A0], xmm0
0x14000644e  xor     ecx, ecx; lpModuleName
0x140006450  call    cs:__imp_GetModuleHandleW
0x140006456  mov     rdx, rax
0x140006459  lea     r9, [rbp+57h+var_A0]
0x14000645d  mov     r8d, ebx
0x140006460  lea     rcx, [rbp+57h+var_90]
0x140006464  call    ?LoadStringNoThrow@@YA?AV?$one_of@U?$typevec@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@Unil@typbldlib@@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@@typveclib@@U?$metavalue@$0A@@typbldlib@@U?$vec_size@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@Unil@typbldlib@@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@@detail@2@U34@@oneoflib@@PEAUHINSTANCE__@@IPEAV?$range@PEAG@rangelib@@@Z; LoadStringNoThrow(HINSTANCE__ *,uint,rangelib::range<ushort *> *)
0x140006469  nop
0x14000646a  cmp     [rbp+57h+var_88], 0
0x14000646e  jnz     short loc_14000647F
0x140006470  mov     dword ptr [rbp+57h+var_90+4], 3
0x140006477  cmp     dword ptr [rbp+57h+var_90], 0
0x14000647b  jz      short loc_14000647F
0x14000647d  jmp     short loc_1400064F2
0x14000647f  movaps  xmm0, [rbp+57h+var_A0]
0x140006483  movdqa  [rbp+57h+var_A0], xmm0
0x140006488  lea     rdx, [rbp+57h+var_A0]
0x14000648c  lea     rcx, [rbp+57h+var_80]
0x140006490  call    ??0?$basic_formatter@GU?$char_traits@G@std@@V?$allocator@G@2@@TpmVscMgrMeta@@QEAA@AEBV?$range@PEBG@rangelib@@@Z; TpmVscMgrMeta::basic_formatter<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_formatter<ushort,std::char_traits<ushort>,std::allocator<ushort>>(rangelib::range<ushort const *> const &)
0x140006495  nop
0x140006496  lea     rdx, [rdi+8]
0x14000649a  mov     r8, rdi
0x14000649d  lea     rcx, [rbp+57h+var_80]
0x1400064a1  call    ??$insert@PEBG@?$basic_formatter@GU?$char_traits@G@std@@V?$allocator@G@2@@TpmVscMgrMeta@@QEAAAEAV01@AEBV?$range@PEBG@rangelib@@AEBQEBG@Z; TpmVscMgrMeta::basic_formatter<ushort,std::char_traits<ushort>,std::allocator<ushort>>::insert<ushort const *>(rangelib::range<ushort const *> const &,ushort const * const &)
0x1400064a6  mov     rbx, cs:__imp_?wcerr@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcerr
0x1400064ad  lea     rcx, [rbp+57h+var_80]
0x1400064b1  call    ?gather@?$basic_formatter@GU?$char_traits@G@std@@V?$allocator@G@2@@TpmVscMgrMeta@@QEAAXXZ; TpmVscMgrMeta::basic_formatter<ushort,std::char_traits<ushort>,std::allocator<ushort>>::gather(void)
0x1400064b6  lea     rdx, [rbp+57h+var_58]
0x1400064ba  cmp     [rbp+57h+var_40], 7
0x1400064bf  cmova   rdx, [rbp+57h+var_58]
0x1400064c4  mov     r8, [rbp+57h+var_48]
0x1400064c8  mov     rcx, rbx
0x1400064cb  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x1400064d0  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x1400064d7  mov     rcx, rax
0x1400064da  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x1400064e0  nop
0x1400064e1  lea     rcx, [rbp+57h+var_80]
0x1400064e5  call    ??1?$basic_formatter@GU?$char_traits@G@std@@V?$allocator@G@2@@TpmVscMgrMeta@@QEAA@XZ; TpmVscMgrMeta::basic_formatter<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_formatter<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x1400064ea  nop
0x1400064eb  mov     eax, [rbp+57h+var_88]
0x1400064ee  test    eax, eax
0x1400064f0  jnz     short loc_1400064FD
0x1400064f2  lea     rcx, [rbp+57h+var_90]
0x1400064f6  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1400064fb  jmp     short loc_140006510
0x1400064fd  cmp     eax, 1
0x140006500  jnz     short loc_140006510
0x140006502  mov     rcx, [rbp+57h+var_90]; void *
0x140006506  test    rcx, rcx
0x140006509  jz      short loc_140006510
0x14000650b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006510  mov     rcx, [rbp+57h+var_10]
0x140006514  xor     rcx, rsp; StackCookie
0x140006517  call    __security_check_cookie
0x14000651c  lea     r11, [rsp+0C0h+var_s0]
0x140006524  mov     rbx, [r11+10h]
0x140006528  mov     rdi, [r11+28h]
0x14000652c  mov     rsp, r11
0x14000652f  pop     rbp
0x140006530  retn
```
