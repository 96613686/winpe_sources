# BinXmlExtractor::AddPath(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,int,ulong,BinXmlVarType,bool)

- ea: `0x18001e1e0`
- end: `0x18001e37d`
- name: `?AddPath@BinXmlExtractor@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@HKW4BinXmlVarType@@_N@Z`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180017864`

## callees

- `0x180007180`
- `0x180008fd4`
- `0x180009cf8`
- `0x18000a100`
- `0x18001e1e0`
- `0x180023548`
- `0x180038fb4`
- `0x180038fcc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BinXmlExtractor::AddPath(_QWORD *a1, __int64 a2, int a3, int a4, unsigned int a5, char a6)
{
  unsigned __int64 v11; // r14
  void *v12; // rax
  void *v13; // rsi
  void *v14[2]; // [rsp+30h] [rbp-40h] BYREF
  __int128 pExceptionObject; // [rsp+40h] [rbp-30h] BYREF
  __int64 v16; // [rsp+50h] [rbp-20h]
  int v17; // [rsp+58h] [rbp-18h]
  int v18; // [rsp+5Ch] [rbp-14h]
  int v19; // [rsp+60h] [rbp-10h]

  if ( a6 )
  {
    v11 = *(_QWORD *)(a2 + 8);
    v12 = MIDL_user_allocate(saturated_mul(v11, 2u));
    v13 = v12;
    v14[0] = v12;
    if ( !v12 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 14);
      }
      pExceptionObject = 0;
      v16 = 0;
      v17 = 14;
      v18 = -1;
      v19 = 96;
      throw (EvtException *)&pExceptionObject;
    }
    memcpy_0(v12, *(const void **)a2, 2 * v11);
    *(_QWORD *)a2 = v13;
    *(_QWORD *)(a2 + 8) = v11;
    if ( !(unsigned __int8)utl::vector<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>>::emplace_back<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,0>(
                             a1,
                             v14) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 14);
      }
      pExceptionObject = 0;
      v16 = 0;
      v17 = 14;
      v18 = -1;
      v19 = 105;
      throw (EvtException *)&pExceptionObject;
    }
    if ( v14[0] )
      operator delete(v14[0]);
  }
  *(_OWORD *)v14 = *(_OWORD *)a2;
  return BinXmlExtractor::CreateOrUpdateNode(a1, (__int128 *)v14, a3, a4, a5, 0);
}

```

## disassembly

```asm
0x18001e1e0  push    rbp
0x18001e1e2  push    rbx
0x18001e1e3  push    rsi
0x18001e1e4  push    rdi
0x18001e1e5  push    r12
0x18001e1e7  push    r14
0x18001e1e9  push    r15
0x18001e1eb  mov     rbp, rsp
0x18001e1ee  sub     rsp, 70h
0x18001e1f2  mov     r15d, r9d
0x18001e1f5  mov     r12d, r8d
0x18001e1f8  mov     rbx, rdx
0x18001e1fb  mov     rdi, rcx
0x18001e1fe  cmp     [rbp+arg_28], 0
0x18001e202  jnz     short loc_18001E239
0x18001e204  movaps  xmm0, xmmword ptr [rbx]
0x18001e207  movdqa  xmmword ptr [rbp+var_40], xmm0
0x18001e20c  mov     [rsp+70h+var_48], 0
0x18001e211  mov     eax, [rbp+arg_20]
0x18001e214  mov     [rsp+70h+var_50], eax
0x18001e218  mov     r9d, r15d
0x18001e21b  mov     r8d, r12d
0x18001e21e  lea     rdx, [rbp+var_40]
0x18001e222  mov     rcx, rdi
0x18001e225  call    ?CreateOrUpdateNode@BinXmlExtractor@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@HKW4BinXmlVarType@@_N@Z; BinXmlExtractor::CreateOrUpdateNode(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,int,ulong,BinXmlVarType,bool)
0x18001e22a  add     rsp, 70h
0x18001e22e  pop     r15
0x18001e230  pop     r14
0x18001e232  pop     r12
0x18001e234  pop     rdi
0x18001e235  pop     rsi
0x18001e236  pop     rbx
0x18001e237  pop     rbp
0x18001e238  retn
0x18001e239  mov     r14, [rdx+8]
0x18001e23d  mov     eax, 2
0x18001e242  mul     r14
0x18001e245  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001e24c  cmovb   rax, rcx
0x18001e250  mov     rcx, rax; size
0x18001e253  call    MIDL_user_allocate
0x18001e258  mov     rsi, rax
0x18001e25b  mov     [rbp+var_40], rax
0x18001e25f  test    rax, rax
0x18001e262  jz      short loc_18001E2A5
0x18001e264  lea     r8, [r14+r14]; Size
0x18001e268  mov     rdx, [rbx]; Src
0x18001e26b  mov     rcx, rax; void *
0x18001e26e  call    memcpy_0
0x18001e273  mov     [rbx], rsi
0x18001e276  mov     [rbx+8], r14
0x18001e27a  lea     rdx, [rbp+var_40]
0x18001e27e  mov     rcx, rdi
0x18001e281  call    ??$emplace_back@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@$0A@@?$vector@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@V?$allocator@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@1@@Z; utl::vector<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>>::emplace_back<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,0>(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&)
0x18001e286  test    al, al
0x18001e288  jz      loc_18001E311
0x18001e28e  mov     rcx, [rbp+var_40]; void *
0x18001e292  test    rcx, rcx
0x18001e295  jz      loc_18001E204
0x18001e29b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e2a0  jmp     loc_18001E204
0x18001e2a5  lea     rax, WPP_GLOBAL_Control
0x18001e2ac  mov     ebx, 0Eh
0x18001e2b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e2b8  cmp     rcx, rax
0x18001e2bb  jz      short loc_18001E2DF
0x18001e2bd  test    byte ptr [rcx+1Ch], 2
0x18001e2c1  jz      short loc_18001E2DF
0x18001e2c3  cmp     byte ptr [rcx+19h], 2
0x18001e2c7  jb      short loc_18001E2DF
0x18001e2c9  lea     edx, [rbx-4]
0x18001e2cc  mov     r9d, ebx
0x18001e2cf  lea     r8, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids
0x18001e2d6  mov     rcx, [rcx+10h]
0x18001e2da  call    WPP_SF_D
0x18001e2df  xorps   xmm0, xmm0
0x18001e2e2  movdqu  [rbp+pExceptionObject], xmm0
0x18001e2e7  mov     [rbp+var_20], 0
0x18001e2ef  mov     [rbp+var_18], ebx
0x18001e2f2  mov     [rbp+var_14], 0FFFFFFFFh
0x18001e2f9  mov     [rbp+var_10], 60h ; '`'
0x18001e300  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001e307  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e30b  call    _CxxThrowException_0
0x18001e311  lea     rax, WPP_GLOBAL_Control
0x18001e318  mov     ebx, 0Eh
0x18001e31d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e324  cmp     rcx, rax
0x18001e327  jz      short loc_18001E34B
0x18001e329  test    byte ptr [rcx+1Ch], 2
0x18001e32d  jz      short loc_18001E34B
0x18001e32f  cmp     byte ptr [rcx+19h], 2
0x18001e333  jb      short loc_18001E34B
0x18001e335  lea     edx, [rbx-3]
0x18001e338  mov     r9d, ebx
0x18001e33b  lea     r8, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids
0x18001e342  mov     rcx, [rcx+10h]
0x18001e346  call    WPP_SF_D
0x18001e34b  xorps   xmm0, xmm0
0x18001e34e  movdqu  [rbp+pExceptionObject], xmm0
0x18001e353  mov     [rbp+var_20], 0
0x18001e35b  mov     [rbp+var_18], ebx
0x18001e35e  mov     [rbp+var_14], 0FFFFFFFFh
0x18001e365  mov     [rbp+var_10], 69h ; 'i'
0x18001e36c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001e373  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e377  call    _CxxThrowException_0
```
