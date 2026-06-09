# Broker::RpcClientToken::GetPackageFullName(void)

- ea: `0x1800074d0`
- end: `0x180007702`
- name: `?GetPackageFullName@RpcClientToken@Broker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `562`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007350`

## callees

- `0x180004be0`
- `0x1800074d0`
- `0x180009640`
- `0x180009e94`
- `0x180012d88`
- `0x1800139f8`
- `0x180015af0`
- `0x1800165aa`
- `0x1800165c2`
- `0x1800165da`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800076fb`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800076fb`
- `ntdll!RtlQueryPackageIdentity` at `0x18000755a`
- `ntdll!RtlQueryPackageIdentity` at `0x18000755a`
- `ntdll!RtlNtStatusToDosError` at `0x18000766f`
- `ntdll!RtlNtStatusToDosError` at `0x18000766f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Broker::RpcClientToken::GetPackageFullName(__int64 a1, _QWORD *a2)
{
  NTSTATUS v4; // eax
  unsigned __int64 v5; // rbx
  size_t v6; // rbx
  __int64 v8; // r14
  char *v9; // rdi
  size_t v10; // rbx
  ULONG v11; // eax
  char v12[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h] BYREF
  void **v15; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v16; // [rsp+58h] [rbp-A8h]
  int v17; // [rsp+68h] [rbp-98h]
  ULONG v18; // [rsp+70h] [rbp-90h]
  _QWORD pExceptionObject[3]; // [rsp+78h] [rbp-88h] BYREF
  int v20; // [rsp+90h] [rbp-70h]
  ULONG v21; // [rsp+98h] [rbp-68h]
  _WORD Src[128]; // [rsp+A0h] [rbp-60h] BYREF
  char v23[144]; // [rsp+1A0h] [rbp+A0h] BYREF

  v13 = 256;
  v14 = 130;
  v12[0] = 0;
  memset_0(Src, 0, sizeof(Src));
  v4 = ((__int64 (__fastcall *)(_QWORD, _WORD *, __int64 *, char *, __int64 *, char *))RtlQueryPackageIdentity)(
         *(_QWORD *)(a1 + 8),
         Src,
         &v13,
         v23,
         &v14,
         v12);
  if ( v4 < 0 )
  {
    if ( v4 != -1073741275 )
    {
      v11 = RtlNtStatusToDosError(v4);
      v16 = 0;
      v17 = 1;
      v15 = &Broker::Win32Error::`vftable';
      v18 = v11;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v11);
      std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)&v15);
      v20 = v17;
      pExceptionObject[0] = &Broker::Win32Error::`vftable';
      v21 = v18;
      throw (Broker::Win32Error *)pExceptionObject;
    }
    *(_OWORD *)a2 = 0;
    a2[2] = 0;
    a2[3] = 7;
    *(_WORD *)a2 = 0;
  }
  else
  {
    *(_OWORD *)a2 = 0;
    a2[2] = 0;
    a2[3] = 0;
    v5 = -1;
    do
      ++v5;
    while ( Src[v5] );
    if ( v5 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( v5 > 7 )
    {
      v8 = std::wstring::_Calculate_growth(v5, 7);
      if ( (unsigned __int64)(v8 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
      v9 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(2 * (v8 + 1));
      *a2 = v9;
      a2[2] = v5;
      a2[3] = v8;
      v10 = 2 * v5;
      memcpy_0(v9, Src, v10);
      *(_WORD *)&v9[v10] = 0;
    }
    else
    {
      a2[2] = v5;
      a2[3] = 7;
      v6 = 2 * v5;
      memcpy_0(a2, Src, v6);
      *(_WORD *)((char *)a2 + v6) = 0;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800074d0  mov     [rsp-8+arg_10], rbx
0x1800074d5  push    rbp
0x1800074d6  push    rsi
0x1800074d7  push    rdi
0x1800074d8  push    r14
0x1800074da  push    r15
0x1800074dc  lea     rbp, [rsp-140h]
0x1800074e4  sub     rsp, 240h
0x1800074eb  mov     rax, cs:__security_cookie
0x1800074f2  xor     rax, rsp
0x1800074f5  mov     [rbp+160h+var_30], rax
0x1800074fc  mov     rsi, rdx
0x1800074ff  mov     rbx, rcx
0x180007502  mov     [rsp+260h+var_228], rdx
0x180007507  xor     r15d, r15d
0x18000750a  mov     [rsp+260h+var_228], 100h
0x180007513  mov     [rsp+260h+var_218], 82h
0x18000751c  mov     [rsp+260h+var_230], r15b
0x180007521  xor     edx, edx; Val
0x180007523  mov     r8d, 100h; Size
0x180007529  lea     rcx, [rbp+160h+Src]; void *
0x18000752d  call    memset_0
0x180007532  lea     rax, [rsp+260h+var_230]
0x180007537  mov     [rsp+260h+var_238], rax
0x18000753c  lea     rax, [rsp+260h+var_218]
0x180007541  mov     [rsp+260h+var_240], rax
0x180007546  lea     r9, [rbp+160h+var_C0]
0x18000754d  lea     r8, [rsp+260h+var_228]
0x180007552  lea     rdx, [rbp+160h+Src]
0x180007556  mov     rcx, [rbx+8]
0x18000755a  call    cs:__imp_RtlQueryPackageIdentity
0x180007560  test    eax, eax
0x180007562  js      loc_18000764B
0x180007568  xorps   xmm0, xmm0
0x18000756b  movups  xmmword ptr [rsi], xmm0
0x18000756e  mov     [rsi+10h], r15
0x180007572  mov     [rsi+18h], r15
0x180007576  lea     rax, [rbp+160h+Src]
0x18000757a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180007581  inc     rbx
0x180007584  cmp     [rax+rbx*2], r15w
0x180007589  jnz     short loc_180007581
0x18000758b  mov     r8, 7FFFFFFFFFFFFFFEh
0x180007595  cmp     rbx, r8
0x180007598  ja      loc_1800076F4
0x18000759e  cmp     rbx, 7
0x1800075a2  ja      short loc_1800075F0
0x1800075a4  mov     [rsi+10h], rbx
0x1800075a8  mov     qword ptr [rsi+18h], 7
0x1800075b0  add     rbx, rbx
0x1800075b3  mov     r8, rbx; Size
0x1800075b6  lea     rdx, [rbp+160h+Src]; Src
0x1800075ba  mov     rcx, rsi; void *
0x1800075bd  call    memcpy_0
0x1800075c2  mov     [rbx+rsi], r15w
0x1800075c7  mov     rax, rsi
0x1800075ca  mov     rcx, [rbp+160h+var_30]
0x1800075d1  xor     rcx, rsp; StackCookie
0x1800075d4  call    __security_check_cookie
0x1800075d9  mov     rbx, [rsp+260h+arg_10]
0x1800075e1  add     rsp, 240h
0x1800075e8  pop     r15
0x1800075ea  pop     r14
0x1800075ec  pop     rdi
0x1800075ed  pop     rsi
0x1800075ee  pop     rbp
0x1800075ef  retn
0x1800075f0  mov     edx, 7
0x1800075f5  mov     rcx, rbx
0x1800075f8  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x1800075fd  mov     r14, rax
0x180007600  lea     rcx, [rax+1]
0x180007604  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000760e  cmp     rcx, rax
0x180007611  jbe     short loc_180007619
0x180007613  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x180007619  add     rcx, rcx
0x18000761c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180007621  mov     rdi, rax
0x180007624  mov     [rsi], rax
0x180007627  mov     [rsi+10h], rbx
0x18000762b  mov     [rsi+18h], r14
0x18000762f  add     rbx, rbx
0x180007632  mov     r8, rbx; Size
0x180007635  lea     rdx, [rbp+160h+Src]; Src
0x180007639  mov     rcx, rax; void *
0x18000763c  call    memcpy_0
0x180007641  mov     [rbx+rdi], r15w
0x180007646  jmp     loc_1800075C7
0x18000764b  cmp     eax, 0C0000225h
0x180007650  jnz     short loc_18000766D
0x180007652  xorps   xmm0, xmm0
0x180007655  movups  xmmword ptr [rsi], xmm0
0x180007658  mov     [rsi+10h], r15
0x18000765c  mov     qword ptr [rsi+18h], 7
0x180007664  mov     [rsi], r15w
0x180007668  jmp     loc_1800075C7
0x18000766d  mov     ecx, eax; Status
0x18000766f  call    cs:__imp_RtlNtStatusToDosError
0x180007675  xorps   xmm0, xmm0
0x180007678  movups  [rsp+260h+var_208], xmm0
0x18000767d  mov     [rsp+260h+var_1F8], 1
0x180007685  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000768c  mov     [rsp+260h+var_210], rbx
0x180007691  mov     [rsp+260h+var_1F0], eax
0x180007695  mov     rcx, cs:WPP_GLOBAL_Control
0x18000769c  test    byte ptr [rcx+1Ch], 8
0x1800076a0  jz      short loc_1800076C0
0x1800076a2  cmp     byte ptr [rcx+19h], 2
0x1800076a6  jb      short loc_1800076C0
0x1800076a8  mov     edx, 16h
0x1800076ad  mov     r9d, eax
0x1800076b0  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x1800076b7  mov     rcx, [rcx+10h]
0x1800076bb  call    WPP_SF_d
0x1800076c0  lea     rdx, [rsp+260h+var_210]; struct std::exception *
0x1800076c5  lea     rcx, [rsp+260h+pExceptionObject]; this
0x1800076ca  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x1800076cf  mov     eax, [rsp+260h+var_1F8]
0x1800076d3  mov     [rbp+160h+var_1D0], eax
0x1800076d6  mov     [rsp+260h+pExceptionObject], rbx
0x1800076db  mov     eax, [rsp+260h+var_1F0]
0x1800076df  mov     [rbp+160h+var_1C8], eax
0x1800076e2  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x1800076e9  lea     rcx, [rsp+260h+pExceptionObject]; pExceptionObject
0x1800076ee  call    _CxxThrowException_0
0x1800076f4  lea     rcx, aStringTooLong; "string too long"
0x1800076fb  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
