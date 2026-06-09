# ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,ushort const *,ushort,ushort const *,ushort,long,ulong,unsigned __int64,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,ushort const *,ulong,_GUID const *)

- ea: `0x180005d5c`
- end: `0x180005fe2`
- name: `??0ON_CREATE_PROC_DATA@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGG1GJK_KPEBEK3K3K1KPEBU_GUID@@@Z`
- size: `646`
- prototype: `__int64 __fastcall(__int64, _QWORD *, void *, __int16, void *, __int16, int, int, __int64, __int64, unsigned int, const void *, int, __int64, unsigned int, _WORD *, int, _OWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180008578`

## callees

- `0x180001ba8`
- `0x180001bb6`
- `0x180005b38`
- `0x180005d5c`
- `0x180006018`
- `0x1800063f4`
- `0x180007f9c`
- `0x18000c0a2`
- `0x18000c0e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005ef2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005f4e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005ef2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005f4e`

## pseudocode

```c
__int64 __fastcall ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA(
        __int64 a1,
        _QWORD *a2,
        void *a3,
        __int16 a4,
        void *a5,
        __int16 a6,
        int a7,
        int a8,
        __int64 a9,
        __int64 a10,
        unsigned int a11,
        const void *a12,
        int a13,
        __int64 a14,
        unsigned int a15,
        _WORD *a16,
        int a17,
        _OWORD *a18)
{
  __int64 v19; // r8
  unsigned int v20; // eax
  void *pExceptionObject[2]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v25; // [rsp+58h] [rbp-20h]
  unsigned __int64 v26; // [rsp+60h] [rbp-18h]

  *(_QWORD *)a1 = *a2;
  *a2 = 0;
  *(_QWORD *)(a1 + 32) = 7;
  *(_QWORD *)(a1 + 24) = 0;
  *(_WORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 64) = 7;
  *(_QWORD *)(a1 + 56) = 0;
  *(_WORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 72) = a7;
  *(_DWORD *)(a1 + 76) = a8;
  *(_QWORD *)(a1 + 80) = a9;
  memset_0((void *)(a1 + 88), 0, 0x40u);
  *(_DWORD *)(a1 + 152) = a13;
  *(_QWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  std::vector<unsigned char>::_Construct<unsigned char const *>(a1 + 160, a10, a10 + a11);
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  std::vector<unsigned char>::_Construct<unsigned char const *>(a1 + 184, a14, a14 + a15);
  *(_QWORD *)(a1 + 232) = 7;
  *(_QWORD *)(a1 + 224) = 0;
  *(_WORD *)(a1 + 208) = 0;
  *(_DWORD *)(a1 + 240) = a17;
  *(_OWORD *)(a1 + 244) = *a18;
  if ( a3 )
  {
    v26 = 7;
    v25 = 0;
    LOWORD(pExceptionObject[0]) = 0;
    if ( a4 )
      std::wstring::assign(pExceptionObject, a3);
    std::wstring::operator=((void *)(a1 + 8), pExceptionObject);
    if ( v26 >= 8 )
      operator delete(pExceptionObject[0]);
    v26 = 7;
    v25 = 0;
    LOWORD(pExceptionObject[0]) = 0;
  }
  if ( a5 )
  {
    v26 = 7;
    v25 = 0;
    LOWORD(pExceptionObject[0]) = 0;
    if ( a6 )
      std::wstring::assign(pExceptionObject, a5);
    std::wstring::operator=((void *)(a1 + 40), pExceptionObject);
    if ( v26 >= 8 )
      operator delete(pExceptionObject[0]);
    v26 = 7;
    v25 = 0;
    LOWORD(pExceptionObject[0]) = 0;
  }
  if ( a16 )
  {
    if ( *a16 )
    {
      v19 = -1;
      do
        ++v19;
      while ( a16[v19] );
    }
    std::wstring::assign((void *)(a1 + 208), a16);
  }
  v20 = *(_DWORD *)(a1 + 152);
  if ( v20 > 0x40 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
  memcpy_0((void *)(a1 + 88), a12, v20);
  return a1;
}

```

## disassembly

```asm
0x180005d5c  push    rbp
0x180005d5e  push    rbx
0x180005d5f  push    rsi
0x180005d60  push    rdi
0x180005d61  push    r12
0x180005d63  push    r13
0x180005d65  push    r14
0x180005d67  push    r15
0x180005d69  mov     rbp, rsp
0x180005d6c  sub     rsp, 78h
0x180005d70  mov     rax, cs:__security_cookie
0x180005d77  xor     rax, rsp
0x180005d7a  mov     [rbp+var_10], rax
0x180005d7e  mov     [rbp+var_58], r9w
0x180005d83  mov     [rbp+var_50], r8
0x180005d87  mov     r12, rcx
0x180005d8a  mov     [rbp+var_40], rcx
0x180005d8e  mov     r13, [rbp+arg_20]
0x180005d92  movzx   eax, [rbp+arg_28]
0x180005d96  mov     [rbp+var_56], ax
0x180005d9a  mov     rdi, [rbp+arg_48]
0x180005da1  mov     ebx, [rbp+arg_50]
0x180005da7  mov     rax, [rbp+arg_58]
0x180005dae  mov     [rbp+Src], rax
0x180005db2  mov     r14, [rbp+arg_68]
0x180005db9  mov     esi, [rbp+arg_70]
0x180005dbf  mov     r15, [rbp+arg_78]
0x180005dc6  mov     [rbp+var_38], rcx
0x180005dca  mov     rax, [rdx]
0x180005dcd  mov     [rcx], rax
0x180005dd0  xor     r8d, r8d
0x180005dd3  mov     [rdx], r8
0x180005dd6  lea     edx, [r8+7]
0x180005dda  mov     [rcx+20h], rdx
0x180005dde  mov     [rcx+18h], r8
0x180005de2  mov     [rcx+8], r8w
0x180005de7  mov     [rcx+40h], rdx
0x180005deb  mov     [rcx+38h], r8
0x180005def  mov     [rcx+28h], r8w
0x180005df4  mov     eax, [rbp+arg_30]
0x180005df7  mov     [rcx+48h], eax
0x180005dfa  mov     eax, [rbp+arg_38]
0x180005e00  mov     [rcx+4Ch], eax
0x180005e03  mov     rax, [rbp+arg_40]
0x180005e0a  mov     [rcx+50h], rax
0x180005e0e  add     rcx, 58h ; 'X'; void *
0x180005e12  xor     edx, edx; Val
0x180005e14  lea     r8d, [rdx+40h]; Size
0x180005e18  call    memset_0
0x180005e1d  mov     eax, [rbp+arg_60]
0x180005e23  mov     [r12+98h], eax
0x180005e2b  lea     rcx, [r12+0A0h]
0x180005e33  xor     eax, eax
0x180005e35  mov     [rcx], rax
0x180005e38  mov     [rcx+8], rax
0x180005e3c  mov     [rcx+10h], rax
0x180005e40  lea     r8, [rdi+rbx]
0x180005e44  mov     rdx, rdi
0x180005e47  call    ??$_Construct@PEBE@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEBE0@Z; std::vector<uchar>::_Construct<uchar const *>(uchar const *,uchar const *)
0x180005e4c  nop
0x180005e4d  lea     rcx, [r12+0B8h]
0x180005e55  xor     edi, edi
0x180005e57  mov     [rcx], rdi
0x180005e5a  mov     [rcx+8], rdi
0x180005e5e  mov     [rcx+10h], rdi
0x180005e62  lea     r8, [r14+rsi]
0x180005e66  mov     rdx, r14
0x180005e69  call    ??$_Construct@PEBE@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEBE0@Z; std::vector<uchar>::_Construct<uchar const *>(uchar const *,uchar const *)
0x180005e6e  nop
0x180005e6f  lea     rbx, [r12+0D0h]
0x180005e77  lea     esi, [rdi+7]
0x180005e7a  mov     [rbx+18h], rsi
0x180005e7e  mov     [rbx+10h], rdi
0x180005e82  mov     [rbx], di
0x180005e85  mov     eax, [rbp+arg_80]
0x180005e8b  mov     [r12+0F0h], eax
0x180005e93  mov     rax, [rbp+arg_88]
0x180005e9a  movups  xmm0, xmmword ptr [rax]
0x180005e9d  movdqu  xmmword ptr [r12+0F4h], xmm0
0x180005ea7  mov     rdx, [rbp+var_50]; Src
0x180005eab  test    rdx, rdx
0x180005eae  jz      short loc_180005F04
0x180005eb0  movzx   r8d, [rbp+var_58]
0x180005eb5  mov     [rbp+var_20], rdi
0x180005eb9  mov     [rbp+var_18], rdi
0x180005ebd  mov     [rbp+var_18], rsi
0x180005ec1  mov     [rbp+var_20], rdi
0x180005ec5  mov     word ptr [rbp+pExceptionObject], di
0x180005ec9  test    r8, r8
0x180005ecc  jz      short loc_180005ED8
0x180005ece  lea     rcx, [rbp+pExceptionObject]; void *
0x180005ed2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180005ed7  nop
0x180005ed8  lea     rdx, [rbp+pExceptionObject]; Src
0x180005edc  lea     rcx, [r12+8]; void *
0x180005ee1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180005ee6  nop
0x180005ee7  cmp     [rbp+var_18], 8
0x180005eec  jb      short loc_180005EF8
0x180005eee  mov     rcx, [rbp+pExceptionObject]
0x180005ef2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005ef8  mov     [rbp+var_18], rsi
0x180005efc  mov     [rbp+var_20], rdi
0x180005f00  mov     word ptr [rbp+pExceptionObject], di
0x180005f04  test    r13, r13
0x180005f07  jz      short loc_180005F60
0x180005f09  movzx   r8d, [rbp+var_56]
0x180005f0e  mov     [rbp+var_20], rdi
0x180005f12  mov     [rbp+var_18], rdi
0x180005f16  mov     [rbp+var_18], rsi
0x180005f1a  mov     [rbp+var_20], rdi
0x180005f1e  mov     word ptr [rbp+pExceptionObject], di
0x180005f22  test    r8, r8
0x180005f25  jz      short loc_180005F34
0x180005f27  mov     rdx, r13; Src
0x180005f2a  lea     rcx, [rbp+pExceptionObject]; void *
0x180005f2e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180005f33  nop
0x180005f34  lea     rdx, [rbp+pExceptionObject]; Src
0x180005f38  lea     rcx, [r12+28h]; void *
0x180005f3d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180005f42  nop
0x180005f43  cmp     [rbp+var_18], 8
0x180005f48  jb      short loc_180005F54
0x180005f4a  mov     rcx, [rbp+pExceptionObject]
0x180005f4e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005f54  mov     [rbp+var_18], rsi
0x180005f58  mov     [rbp+var_20], rdi
0x180005f5c  mov     word ptr [rbp+pExceptionObject], di
0x180005f60  test    r15, r15
0x180005f63  jz      short loc_180005F89
0x180005f65  cmp     [r15], di
0x180005f69  jnz     short loc_180005F70
0x180005f6b  mov     r8, rdi
0x180005f6e  jmp     short loc_180005F7E
0x180005f70  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005f74  inc     r8
0x180005f77  cmp     [r15+r8*2], di
0x180005f7c  jnz     short loc_180005F74
0x180005f7e  mov     rdx, r15; Src
0x180005f81  mov     rcx, rbx; void *
0x180005f84  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180005f89  mov     eax, [r12+98h]
0x180005f91  cmp     eax, 40h ; '@'
0x180005f94  ja      short loc_180005FC8
0x180005f96  mov     r8d, eax; Size
0x180005f99  mov     rdx, [rbp+Src]; Src
0x180005f9d  lea     rcx, [r12+58h]; void *
0x180005fa2  call    memcpy_0
0x180005fa7  nop
0x180005fa8  mov     rax, r12
0x180005fab  mov     rcx, [rbp+var_10]
0x180005faf  xor     rcx, rsp; StackCookie
0x180005fb2  call    __security_check_cookie
0x180005fb7  add     rsp, 78h
0x180005fbb  pop     r15
0x180005fbd  pop     r14
0x180005fbf  pop     r13
0x180005fc1  pop     r12
0x180005fc3  pop     rdi
0x180005fc4  pop     rsi
0x180005fc5  pop     rbx
0x180005fc6  pop     rbp
0x180005fc7  retn
0x180005fc8  lea     rcx, [rbp+pExceptionObject]; this
0x180005fcc  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180005fd1  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180005fd8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180005fdc  call    _CxxThrowException_0
```
