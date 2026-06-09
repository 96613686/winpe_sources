# CodeIntegrity::Management::detail::SbcpTokenView::CheckSignature(void)

- ea: `0x180016958`
- end: `0x180016b1e`
- name: `?CheckSignature@SbcpTokenView@detail@Management@CodeIntegrity@@AEAAXXZ`
- size: `454`
- prototype: `void __fastcall(CodeIntegrity::Management::detail::SbcpTokenView *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009970`
- `0x180016780`
- `0x1800184d8`

## callees

- `0x180003888`
- `0x180003c5c`
- `0x18000830c`
- `0x18000f008`
- `0x1800105e4`
- `0x180016804`
- `0x180016884`
- `0x180016958`
- `0x1800218d0`
- `0x180028178`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::detail::SbcpTokenView::CheckSignature(
        CodeIntegrity::Management::detail::SbcpTokenView *this)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  bool v4; // zf
  _DWORD v5[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v6; // [rsp+48h] [rbp-B8h]
  __int128 v7; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v8; // [rsp+60h] [rbp-A0h]
  __int64 v9[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v10; // [rsp+78h] [rbp-88h]
  __int128 v11; // [rsp+88h] [rbp-78h]
  __int64 v12; // [rsp+98h] [rbp-68h]
  __int64 v13; // [rsp+A0h] [rbp-60h] BYREF
  int v14; // [rsp+A8h] [rbp-58h]
  const char *v15; // [rsp+B0h] [rbp-50h]
  __int64 v16; // [rsp+140h] [rbp+40h] BYREF
  __int64 v17; // [rsp+148h] [rbp+48h] BYREF
  char v18; // [rsp+150h] [rbp+50h] BYREF

  v16 = 0;
  v17 = 0;
  *(_OWORD *)v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  memset_0(&v13, 0, 0x80u);
  v5[0] = 67175979;
  v5[1] = 1329037825;
  v6 = 4;
  v13 = 0x100000080LL;
  v14 = 1;
  v15 = "1.3.6.1.4.1.311.10.3.6";
  if ( (int)SIPolicyVerifySignedData(
              *((BYTE **)this + 11),
              *((_DWORD *)this + 24) - (unsigned int)*((_QWORD *)this + 11),
              (__int64)&v13,
              (__int64)&v16,
              (__int64)&v17,
              (__int64)v9) < 0 )
  {
    *((_WORD *)this + 4) |= 2u;
    return;
  }
  v2 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v18, v9);
  wil::ScopeExit__lambda_61314298f69a15c54dd23c2e7edd4611___(v5, v2);
  v3 = v16 + v17;
  v7 = 0;
  v8 = 0;
  v17 = v16;
  v16 = v3;
  std::vector<unsigned char>::_Construct_n<unsigned char * const &,unsigned char * const &>(&v7, v3 - v17, &v17, &v16);
  std::vector<unsigned char>::operator=((char *)this + 112, &v7);
  std::vector<unsigned char>::_Tidy(&v7);
  if ( DWORD1(v11) > 0xA )
  {
    if ( DWORD1(v11) > 0x10 )
    {
      if ( DWORD1(v11) == 17 )
        goto LABEL_20;
      v4 = DWORD1(v11) == 18;
    }
    else
    {
      if ( DWORD1(v11) == 16 )
        goto LABEL_8;
      if ( DWORD1(v11) == 11 || DWORD1(v11) == 12 || DWORD1(v11) == 13 )
        goto LABEL_20;
      v4 = DWORD1(v11) == 14;
    }
    if ( !v4 )
      goto LABEL_20;
  }
  else
  {
    if ( DWORD1(v11) == 10 )
    {
LABEL_8:
      LOBYTE(v16) = 0;
      if ( (int)SIPolicyGetTestsigningPolicy(&v16, 0) >= 0 && (_BYTE)v16 )
        goto LABEL_21;
      goto LABEL_20;
    }
    if ( DWORD1(v11) <= 5 )
    {
LABEL_20:
      *((_WORD *)this + 4) |= 1u;
      goto LABEL_21;
    }
    if ( DWORD1(v11) != 6 )
    {
      if ( DWORD1(v11) == 9 )
        goto LABEL_8;
      goto LABEL_20;
    }
  }
LABEL_21:
  wil::details::ScopeExitFn__lambda_61314298f69a15c54dd23c2e7edd4611___::_ScopeExitFn__lambda_61314298f69a15c54dd23c2e7edd4611___(v5);
}

```

## disassembly

```asm
0x180016958  push    rbp
0x18001695a  push    rbx
0x18001695b  push    r14
0x18001695d  lea     rbp, [rsp-20h]
0x180016962  sub     rsp, 120h
0x180016969  mov     rbx, rcx
0x18001696c  mov     [rbp+30h+arg_0], 0
0x180016974  mov     [rbp+30h+arg_8], 0
0x18001697c  xorps   xmm0, xmm0
0x18001697f  xor     eax, eax
0x180016981  movups  xmmword ptr [rsp+130h+var_C8], xmm0
0x180016986  movups  [rsp+130h+var_B8], xmm0
0x18001698b  movups  [rbp+30h+var_A8], xmm0
0x18001698f  mov     [rbp+30h+var_98], rax
0x180016993  xor     edx, edx; Val
0x180016995  mov     r8d, 80h; Size
0x18001699b  lea     rcx, [rbp+30h+var_90]; void *
0x18001699f  call    memset_0
0x1800169a4  mov     [rsp+130h+var_F0], 401062Bh
0x1800169ac  mov     r14d, 1
0x1800169b2  mov     [rsp+130h+var_EC], 4F378201h
0x1800169ba  mov     [rsp+130h+var_E8], 4
0x1800169bf  mov     dword ptr [rbp+30h+var_90], 80h
0x1800169c6  mov     dword ptr [rbp+30h+var_90+4], r14d
0x1800169ca  mov     [rbp+30h+var_88], r14d
0x1800169ce  lea     rax, a1361413111036; "1.3.6.1.4.1.311.10.3.6"
0x1800169d5  mov     [rbp+30h+var_80], rax
0x1800169d9  mov     rcx, [rbx+58h]; pbSignedBlob
0x1800169dd  mov     edx, [rbx+60h]
0x1800169e0  sub     edx, ecx; cbSignedBlob
0x1800169e2  lea     rax, [rsp+130h+var_C8]
0x1800169e7  mov     [rsp+130h+var_F8], rax; __int64
0x1800169ec  lea     rax, [rbp+30h+arg_8]
0x1800169f0  mov     [rsp+130h+var_100], rax; __int64
0x1800169f5  lea     rax, [rbp+30h+arg_0]
0x1800169f9  mov     [rsp+130h+var_108], rax; __int64
0x1800169fe  lea     rax, [rbp+30h+var_90]
0x180016a02  mov     [rsp+130h+var_110], rax; __int64
0x180016a07  lea     r8, [rsp+130h+var_F0]
0x180016a0c  call    SIPolicyVerifySignedData
0x180016a11  test    eax, eax
0x180016a13  jns     short loc_180016A22
0x180016a15  lea     ecx, [r14+1]
0x180016a19  or      [rbx+8], cx
0x180016a1d  jmp     loc_180016B12
0x180016a22  lea     rdx, [rsp+130h+var_C8]
0x180016a27  lea     rcx, [rbp+30h+arg_10]
0x180016a2b  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180016a30  mov     rdx, rax
0x180016a33  lea     rcx, [rsp+130h+var_F0]
0x180016a38  call    wil__ScopeExit__lambda_61314298f69a15c54dd23c2e7edd4611___
0x180016a3d  nop
0x180016a3e  mov     rcx, [rbp+30h+arg_0]
0x180016a42  mov     rdx, [rbp+30h+arg_8]
0x180016a46  add     rdx, rcx
0x180016a49  xorps   xmm0, xmm0
0x180016a4c  movdqu  [rsp+130h+var_E0], xmm0
0x180016a52  mov     [rsp+130h+var_D0], 0
0x180016a5b  mov     [rbp+30h+arg_8], rcx
0x180016a5f  mov     [rbp+30h+arg_0], rdx
0x180016a63  sub     rdx, rcx
0x180016a66  lea     r9, [rbp+30h+arg_0]
0x180016a6a  lea     r8, [rbp+30h+arg_8]
0x180016a6e  lea     rcx, [rsp+130h+var_E0]
0x180016a73  call    ??$_Construct_n@AEBQEAEAEBQEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBQEAE1@Z; std::vector<uchar>::_Construct_n<uchar * const &,uchar * const &>(unsigned __int64,uchar * const &,uchar * const &)
0x180016a78  lea     rcx, [rbx+70h]
0x180016a7c  lea     rdx, [rsp+130h+var_E0]
0x180016a81  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180016a86  lea     rcx, [rsp+130h+var_E0]
0x180016a8b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180016a90  mov     eax, dword ptr [rbp+30h+var_A8+4]
0x180016a93  cmp     eax, 0Ah
0x180016a96  ja      short loc_180016ADE
0x180016a98  jz      short loc_180016AC3
0x180016a9a  cmp     eax, 5
0x180016a9d  ja      short loc_180016AAF
0x180016a9f  jz      short loc_180016B03
0x180016aa1  test    eax, eax
0x180016aa3  jz      short loc_180016B03
0x180016aa5  sub     eax, 1
0x180016aa8  jz      short loc_180016B03
0x180016aaa  sub     eax, 1
0x180016aad  jmp     short loc_180016B03
0x180016aaf  sub     eax, 6
0x180016ab2  jz      short loc_180016B08
0x180016ab4  sub     eax, 1
0x180016ab7  jz      short loc_180016B03
0x180016ab9  sub     eax, 1
0x180016abc  jz      short loc_180016B03
0x180016abe  cmp     eax, 1
0x180016ac1  jnz     short loc_180016B03
0x180016ac3  mov     byte ptr [rbp+30h+arg_0], 0
0x180016ac7  xor     edx, edx
0x180016ac9  lea     rcx, [rbp+30h+arg_0]
0x180016acd  call    SIPolicyGetTestsigningPolicy
0x180016ad2  test    eax, eax
0x180016ad4  js      short loc_180016B03
0x180016ad6  cmp     byte ptr [rbp+30h+arg_0], 0
0x180016ada  jnz     short loc_180016B08
0x180016adc  jmp     short loc_180016B03
0x180016ade  cmp     eax, 10h
0x180016ae1  ja      short loc_180016AF9
0x180016ae3  jz      short loc_180016AC3
0x180016ae5  sub     eax, 0Bh
0x180016ae8  jz      short loc_180016B03
0x180016aea  sub     eax, 1
0x180016aed  jz      short loc_180016B03
0x180016aef  sub     eax, 1
0x180016af2  jz      short loc_180016B03
0x180016af4  cmp     eax, 1
0x180016af7  jmp     short loc_180016B01
0x180016af9  sub     eax, 11h
0x180016afc  jz      short loc_180016B03
0x180016afe  sub     eax, 1
0x180016b01  jz      short loc_180016B08
0x180016b03  or      [rbx+8], r14w
0x180016b08  lea     rcx, [rsp+130h+var_F0]
0x180016b0d  call    wil__details__ScopeExitFn__lambda_61314298f69a15c54dd23c2e7edd4611______ScopeExitFn__lambda_61314298f69a15c54dd23c2e7edd4611___
0x180016b12  add     rsp, 120h
0x180016b19  pop     r14
0x180016b1b  pop     rbx
0x180016b1c  pop     rbp
0x180016b1d  retn
```
