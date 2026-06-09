# CodeIntegrity::Management::AuthorizationToken::ReportTokenLoad(void)

- ea: `0x1800188c0`
- end: `0x180018b3b`
- name: `?ReportTokenLoad@AuthorizationToken@Management@CodeIntegrity@@QEBAXXZ`
- size: `635`
- prototype: `void __fastcall(CodeIntegrity::Management::AuthorizationToken *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018774`
- `0x180018834`

## callees

- `0x180002a90`
- `0x18000828c`
- `0x180008474`
- `0x180015a6c`
- `0x1800188c0`
- `0x180019464`
- `0x180019540`
- `0x1800195e0`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::AuthorizationToken::ReportTokenLoad(
        CodeIntegrity::Management::AuthorizationToken *this)
{
  unsigned int v1; // edi
  int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 *v7; // r12
  char v8; // bl
  __int64 v9; // rdi
  unsigned __int64 v10; // rbp
  __int64 v11; // r14
  __int64 v12; // rsi
  int v13; // eax
  int v14; // edx
  int v15; // ecx
  __int64 v16; // rdi
  __int64 v17; // rsi
  int v18; // eax
  int v19; // edx
  int v20; // ecx
  __int64 v21; // rdi
  __int64 v22; // rsi
  int v23; // eax
  int v24; // edx
  int v25; // ecx
  __int64 v26; // rdi
  __int64 v27; // rsi
  int v28; // eax
  int v29; // edx
  int v30; // ecx
  _BYTE v31[32]; // [rsp+48h] [rbp-50h] BYREF

  v1 = *((unsigned __int16 *)this + 4);
  v3 = 0;
  if ( (_WORD)v1 )
  {
    if ( (Microsoft_Windows_DeviceGuardEnableBits & 1) != 0 )
    {
      CodeIntegrity::Management::detail::SbcpTokenView::name(this, v31);
      v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      McTemplateU0zq_EventWriteTransfer(v6, v5, v4, v1);
      LOBYTE(v3) = 1;
    }
    if ( (v3 & 1) != 0 )
      std::wstring::_Tidy_deallocate((__int64)v31);
  }
  else
  {
    v7 = (__int64 *)((char *)this + 136);
    if ( (Microsoft_Windows_DeviceGuardEnableBits & 2) != 0 )
    {
      v8 = *((_BYTE *)this + 224);
      v9 = *((_QWORD *)this + 27);
      v10 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 21) - *((_QWORD *)this + 20)) >> 4);
      v11 = (__int64)(*((_QWORD *)this + 24) - *((_QWORD *)this + 23)) >> 6;
      v12 = (__int64)(*((_QWORD *)this + 18) - *((_QWORD *)this + 17)) >> 5;
      CodeIntegrity::Management::detail::SbcpTokenView::name(this, v31);
      v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      McTemplateU0zjqqqq_EventWriteTransfer(v15, v14, v13, v9, v8, v12, v10, v11, 0);
      v3 = 2;
    }
    if ( (v3 & 2) != 0 )
    {
      v3 &= ~2u;
      std::wstring::_Tidy_deallocate((__int64)v31);
    }
    v16 = *v7;
    v17 = v7[1];
    while ( v16 != v17 )
    {
      if ( (Microsoft_Windows_DeviceGuardEnableBits & 2) != 0 )
      {
        v3 |= 4u;
        CodeIntegrity::Management::detail::SbcpTokenView::name(this, v31);
        v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
        McTemplateU0zzqbr2_EventWriteTransfer(v20, v19, v18, (unsigned int)L"SHA256", 32, v16);
      }
      if ( (v3 & 4) != 0 )
      {
        v3 &= ~4u;
        std::wstring::_Tidy_deallocate((__int64)v31);
      }
      v16 += 32;
    }
    v21 = *((_QWORD *)this + 20);
    v22 = *((_QWORD *)this + 21);
    while ( v21 != v22 )
    {
      if ( (Microsoft_Windows_DeviceGuardEnableBits & 2) != 0 )
      {
        v3 |= 8u;
        CodeIntegrity::Management::detail::SbcpTokenView::name(this, v31);
        v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
        McTemplateU0zzqbr2_EventWriteTransfer(v25, v24, v23, (unsigned int)L"SHA384", 48, v21);
      }
      if ( (v3 & 8) != 0 )
      {
        v3 &= ~8u;
        std::wstring::_Tidy_deallocate((__int64)v31);
      }
      v21 += 48;
    }
    v26 = *((_QWORD *)this + 23);
    v27 = *((_QWORD *)this + 24);
    while ( v26 != v27 )
    {
      if ( (Microsoft_Windows_DeviceGuardEnableBits & 2) != 0 )
      {
        v3 |= 0x10u;
        CodeIntegrity::Management::detail::SbcpTokenView::name(this, v31);
        v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
        McTemplateU0zzqbr2_EventWriteTransfer(v30, v29, v28, (unsigned int)L"SHA512", 64, v26);
      }
      if ( (v3 & 0x10) != 0 )
      {
        v3 &= ~0x10u;
        std::wstring::_Tidy_deallocate((__int64)v31);
      }
      v26 += 64;
    }
  }
}

```

## disassembly

```asm
0x1800188c0  mov     [rsp+arg_8], rbx
0x1800188c5  mov     [rsp+arg_10], rbp
0x1800188ca  push    rsi
0x1800188cb  push    rdi
0x1800188cc  push    r12
0x1800188ce  push    r14
0x1800188d0  push    r15
0x1800188d2  sub     rsp, 70h
0x1800188d6  mov     rax, cs:__security_cookie
0x1800188dd  xor     rax, rsp
0x1800188e0  mov     [rsp+98h+var_30], rax
0x1800188e5  movzx   edi, word ptr [rcx+8]
0x1800188e9  xor     eax, eax
0x1800188eb  mov     [rsp+98h+var_58], eax
0x1800188ef  mov     r15, rcx
0x1800188f2  mov     ebx, eax
0x1800188f4  test    di, di
0x1800188f7  jz      short loc_18001893C
0x1800188f9  test    cs:Microsoft_Windows_DeviceGuardEnableBits, 1
0x180018900  jz      short loc_180018924
0x180018902  lea     rdx, [rsp+98h+var_50]
0x180018907  call    ?name@SbcpTokenView@detail@Management@CodeIntegrity@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CodeIntegrity::Management::detail::SbcpTokenView::name(void)
0x18001890c  mov     rcx, rax
0x18001890f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018914  mov     r8, rax
0x180018917  mov     r9d, edi
0x18001891a  call    McTemplateU0zq_EventWriteTransfer
0x18001891f  mov     ebx, 1
0x180018924  test    bl, 1
0x180018927  jz      loc_180018B15
0x18001892d  lea     rcx, [rsp+98h+var_50]
0x180018932  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018937  jmp     loc_180018B15
0x18001893c  test    cs:Microsoft_Windows_DeviceGuardEnableBits, 2
0x180018943  lea     r12, [rcx+88h]
0x18001894a  jz      loc_1800189D0
0x180018950  mov     rbp, [rcx+0A8h]
0x180018957  lea     rdx, [rsp+98h+var_50]
0x18001895c  sub     rbp, [rcx+0A0h]
0x180018963  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001896d  mov     r14, [rcx+0C0h]
0x180018974  mov     rsi, [r12+8]
0x180018979  sub     r14, [rcx+0B8h]
0x180018980  sub     rsi, [r12]
0x180018984  movzx   ebx, byte ptr [rcx+0E0h]
0x18001898b  mov     rdi, [rcx+0D8h]
0x180018992  sar     rbp, 4
0x180018996  imul    rbp, rax
0x18001899a  sar     r14, 6
0x18001899e  sar     rsi, 5
0x1800189a2  call    ?name@SbcpTokenView@detail@Management@CodeIntegrity@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CodeIntegrity::Management::detail::SbcpTokenView::name(void)
0x1800189a7  mov     rcx, rax
0x1800189aa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800189af  mov     [rsp+98h+var_60], r14d
0x1800189b4  mov     r9, rdi
0x1800189b7  mov     [rsp+98h+var_68], ebp
0x1800189bb  mov     r8, rax
0x1800189be  mov     dword ptr [rsp+98h+var_70], esi
0x1800189c2  mov     [rsp+98h+var_78], ebx
0x1800189c6  call    McTemplateU0zjqqqq_EventWriteTransfer
0x1800189cb  mov     ebx, 2
0x1800189d0  test    bl, 2
0x1800189d3  jz      short loc_1800189E2
0x1800189d5  and     ebx, 0FFFFFFFDh
0x1800189d8  lea     rcx, [rsp+98h+var_50]
0x1800189dd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800189e2  mov     rdi, [r12]
0x1800189e6  mov     rsi, [r12+8]
0x1800189eb  jmp     short loc_180018A40
0x1800189ed  test    cs:Microsoft_Windows_DeviceGuardEnableBits, 2
0x1800189f4  jz      short loc_180018A2A
0x1800189f6  lea     rdx, [rsp+98h+var_50]
0x1800189fb  mov     rcx, r15
0x1800189fe  or      ebx, 4
0x180018a01  call    ?name@SbcpTokenView@detail@Management@CodeIntegrity@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CodeIntegrity::Management::detail::SbcpTokenView::name(void)
0x180018a06  mov     rcx, rax
0x180018a09  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018a0e  mov     r8, rax
0x180018a11  mov     [rsp+98h+var_70], rdi
0x180018a16  lea     r9, aSha256; "SHA256"
0x180018a1d  mov     [rsp+98h+var_78], 20h ; ' '
0x180018a25  call    McTemplateU0zzqbr2_EventWriteTransfer
0x180018a2a  test    bl, 4
0x180018a2d  jz      short loc_180018A3C
0x180018a2f  and     ebx, 0FFFFFFFBh
0x180018a32  lea     rcx, [rsp+98h+var_50]
0x180018a37  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018a3c  add     rdi, 20h ; ' '
0x180018a40  cmp     rdi, rsi
0x180018a43  jnz     short loc_1800189ED
0x180018a45  mov     rdi, [r15+0A0h]
0x180018a4c  mov     rsi, [r15+0A8h]
0x180018a53  jmp     short loc_180018AA8
0x180018a55  test    cs:Microsoft_Windows_DeviceGuardEnableBits, 2
0x180018a5c  jz      short loc_180018A92
0x180018a5e  lea     rdx, [rsp+98h+var_50]
0x180018a63  mov     rcx, r15
0x180018a66  or      ebx, 8
0x180018a69  call    ?name@SbcpTokenView@detail@Management@CodeIntegrity@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CodeIntegrity::Management::detail::SbcpTokenView::name(void)
0x180018a6e  mov     rcx, rax
0x180018a71  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018a76  mov     r8, rax
0x180018a79  mov     [rsp+98h+var_70], rdi
0x180018a7e  lea     r9, aSha384; "SHA384"
0x180018a85  mov     [rsp+98h+var_78], 30h ; '0'
0x180018a8d  call    McTemplateU0zzqbr2_EventWriteTransfer
0x180018a92  test    bl, 8
0x180018a95  jz      short loc_180018AA4
0x180018a97  and     ebx, 0FFFFFFF7h
0x180018a9a  lea     rcx, [rsp+98h+var_50]
0x180018a9f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018aa4  add     rdi, 30h ; '0'
0x180018aa8  cmp     rdi, rsi
0x180018aab  jnz     short loc_180018A55
0x180018aad  mov     rdi, [r15+0B8h]
0x180018ab4  mov     rsi, [r15+0C0h]
0x180018abb  jmp     short loc_180018B10
0x180018abd  test    cs:Microsoft_Windows_DeviceGuardEnableBits, 2
0x180018ac4  jz      short loc_180018AFA
0x180018ac6  lea     rdx, [rsp+98h+var_50]
0x180018acb  mov     rcx, r15
0x180018ace  or      ebx, 10h
0x180018ad1  call    ?name@SbcpTokenView@detail@Management@CodeIntegrity@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CodeIntegrity::Management::detail::SbcpTokenView::name(void)
0x180018ad6  mov     rcx, rax
0x180018ad9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018ade  mov     r8, rax
0x180018ae1  mov     [rsp+98h+var_70], rdi
0x180018ae6  lea     r9, aSha512; "SHA512"
0x180018aed  mov     [rsp+98h+var_78], 40h ; '@'
0x180018af5  call    McTemplateU0zzqbr2_EventWriteTransfer
0x180018afa  test    bl, 10h
0x180018afd  jz      short loc_180018B0C
0x180018aff  and     ebx, 0FFFFFFEFh
0x180018b02  lea     rcx, [rsp+98h+var_50]
0x180018b07  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018b0c  add     rdi, 40h ; '@'
0x180018b10  cmp     rdi, rsi
0x180018b13  jnz     short loc_180018ABD
0x180018b15  mov     rcx, [rsp+98h+var_30]
0x180018b1a  xor     rcx, rsp; StackCookie
0x180018b1d  call    __security_check_cookie
0x180018b22  lea     r11, [rsp+98h+var_28]
0x180018b27  mov     rbx, [r11+38h]
0x180018b2b  mov     rbp, [r11+40h]
0x180018b2f  mov     rsp, r11
0x180018b32  pop     r15
0x180018b34  pop     r14
0x180018b36  pop     r12
0x180018b38  pop     rdi
0x180018b39  pop     rsi
0x180018b3a  retn
```
