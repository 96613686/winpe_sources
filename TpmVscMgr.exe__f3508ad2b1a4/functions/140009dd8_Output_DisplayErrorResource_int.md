# Output::DisplayErrorResource(int)

- ea: `0x140009dd8`
- end: `0x140009e8b`
- name: `?DisplayErrorResource@Output@@QEBAXH@Z`
- size: `179`
- prototype: `void __fastcall(Output *__hidden this, int)`
- caller_count: `6`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140006298`
- `0x140008784`
- `0x140009fa4`
- `0x14000ded8`
- `0x14000f54c`
- `0x140010c90`

## callees

- `0x1400016a0`
- `0x140001934`
- `0x140005ed8`
- `0x140008454`
- `0x140009dd8`
- `0x14000a388`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140009dfa`
- `KERNEL32!GetModuleHandleW` at `0x140009dfa`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140009e49`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140009e49`
- `msvcp_win!?wcerr@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x140009e33`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Output::DisplayErrorResource(Output *this, UINT a2)
{
  HMODULE ModuleHandleW; // rax
  unsigned int v4; // edx
  __int64 *v5; // rax
  __int128 v6; // [rsp+20h] [rbp-38h] BYREF
  void *v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  v6 = 0;
  ModuleHandleW = GetModuleHandleW(0);
  LoadStringNoThrow((__int64)&v7, ModuleHandleW, a2, &v6);
  if ( (v8 || (HIDWORD(v7) = 3, !(_DWORD)v7))
    && (v5 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(std::wcerr, v6),
        std::basic_ostream<unsigned short>::operator<<(v5, std::endl<unsigned short,std::char_traits<unsigned short>>),
        v8) )
  {
    if ( v8 == 1 )
    {
      if ( v7 )
        operator delete(v7);
    }
  }
  else
  {
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v7, v4);
  }
}

```

## disassembly

```asm
0x140009dd8  push    rbx
0x140009dda  sub     rsp, 50h
0x140009dde  mov     rax, cs:__security_cookie
0x140009de5  xor     rax, rsp
0x140009de8  mov     [rsp+58h+var_18], rax
0x140009ded  mov     ebx, edx
0x140009def  xorps   xmm0, xmm0
0x140009df2  movdqu  [rsp+58h+var_38], xmm0
0x140009df8  xor     ecx, ecx; lpModuleName
0x140009dfa  call    cs:__imp_GetModuleHandleW
0x140009e00  mov     rdx, rax
0x140009e03  lea     r9, [rsp+58h+var_38]
0x140009e08  mov     r8d, ebx
0x140009e0b  lea     rcx, [rsp+58h+var_28]
0x140009e10  call    ?LoadStringNoThrow@@YA?AV?$one_of@U?$typevec@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@Unil@typbldlib@@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@@typveclib@@U?$metavalue@$0A@@typbldlib@@U?$vec_size@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@Unil@typbldlib@@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@@detail@2@U34@@oneoflib@@PEAUHINSTANCE__@@IPEAV?$range@PEAG@rangelib@@@Z; LoadStringNoThrow(HINSTANCE__ *,uint,rangelib::range<ushort *> *)
0x140009e15  nop
0x140009e16  cmp     [rsp+58h+var_20], 0
0x140009e1b  jnz     short loc_140009E2E
0x140009e1d  mov     dword ptr [rsp+58h+var_28+4], 3
0x140009e25  cmp     dword ptr [rsp+58h+var_28], 0
0x140009e2a  jz      short loc_140009E2E
0x140009e2c  jmp     short loc_140009E58
0x140009e2e  mov     rdx, qword ptr [rsp+58h+var_38]
0x140009e33  mov     rcx, cs:__imp_?wcerr@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcerr
0x140009e3a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140009e3f  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x140009e46  mov     rcx, rax
0x140009e49  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x140009e4f  nop
0x140009e50  mov     eax, [rsp+58h+var_20]
0x140009e54  test    eax, eax
0x140009e56  jnz     short loc_140009E64
0x140009e58  lea     rcx, [rsp+58h+var_28]
0x140009e5d  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x140009e62  jmp     short loc_140009E78
0x140009e64  cmp     eax, 1
0x140009e67  jnz     short loc_140009E78
0x140009e69  mov     rcx, [rsp+58h+var_28]; void *
0x140009e6e  test    rcx, rcx
0x140009e71  jz      short loc_140009E78
0x140009e73  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140009e78  mov     rcx, [rsp+58h+var_18]
0x140009e7d  xor     rcx, rsp; StackCookie
0x140009e80  call    __security_check_cookie
0x140009e85  add     rsp, 50h
0x140009e89  pop     rbx
0x140009e8a  retn
```
