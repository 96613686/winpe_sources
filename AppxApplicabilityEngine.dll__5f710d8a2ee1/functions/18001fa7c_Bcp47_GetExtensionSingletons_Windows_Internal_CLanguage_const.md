# Bcp47::GetExtensionSingletons(Windows::Internal::CLanguage const &)

- ea: `0x18001fa7c`
- end: `0x18001fd23`
- name: `?GetExtensionSingletons@Bcp47@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVCLanguage@Internal@Windows@@@Z`
- size: `679`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180005780`
- `0x18001fd2c`
- `0x18001fd68`

## callees

- `0x180004bb4`
- `0x180005750`
- `0x18000a90c`
- `0x180013294`
- `0x18001f10c`
- `0x18001f508`
- `0x18001f658`
- `0x18001fa7c`
- `0x1800227c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Bcp47::GetExtensionSingletons(__int64 a1, __int64 a2, __int64 a3)
{
  _WORD *v4; // r15
  int SubtagFields; // eax
  _WORD *v6; // rsi
  __int64 v7; // rax
  _BYTE *v8; // r12
  _WORD *v9; // rbx
  _WORD *v10; // rdi
  _WORD *i; // r14
  __int64 v12; // rsi
  __int16 v13; // ax
  char v14; // r14
  _WORD *v15; // rcx
  _WORD *v16; // rdx
  _WORD *v17; // rdx
  __int64 v18; // rsi
  _WORD v20[3]; // [rsp+3Ah] [rbp-CEh] BYREF
  __int128 v21; // [rsp+40h] [rbp-C8h] BYREF
  _WORD *v22; // [rsp+50h] [rbp-B8h]
  _QWORD pExceptionObject[3]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v24[176]; // [rsp+78h] [rbp-90h] BYREF

  pExceptionObject[2] = -2;
  pExceptionObject[0] = a1;
  v21 = 0;
  v4 = 0;
  v22 = 0;
  SubtagFields = Windows::Internal::CLanguage::GetSubtagFields(a2, 96, a3, v24);
  if ( SubtagFields < 0 )
  {
    LODWORD(pExceptionObject[0]) = SubtagFields;
    throw (long *)pExceptionObject;
  }
  v6 = v24;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)&v24[2 * v7] );
  v8 = &v24[2 * v7 + 2];
  v9 = (_WORD *)*((_QWORD *)&v21 + 1);
  v10 = (_WORD *)v21;
  while ( v6 != (_WORD *)v8 )
  {
    for ( i = v6 + 1; i != (_WORD *)v8 && *i != 45; ++i )
      ;
    if ( (char *)i - (char *)v6 == 2 )
    {
      if ( *v6 == 120 )
      {
        v14 = 1;
        goto LABEL_27;
      }
      if ( v6 >= v9 || v10 > v6 )
      {
        if ( v9 == v4 )
        {
          std::vector<unsigned short>::_Reserve(&v21);
          v4 = v22;
          v9 = (_WORD *)*((_QWORD *)&v21 + 1);
          v10 = (_WORD *)v21;
        }
        v13 = *v6;
      }
      else
      {
        v12 = v6 - v10;
        if ( v9 == v4 )
        {
          std::vector<unsigned short>::_Reserve(&v21);
          v4 = v22;
          v9 = (_WORD *)*((_QWORD *)&v21 + 1);
          v10 = (_WORD *)v21;
        }
        v13 = v10[v12];
      }
      *v9++ = v13;
      *((_QWORD *)&v21 + 1) = v9;
    }
    v6 = i;
    if ( i != (_WORD *)v8 )
      v6 = i + 1;
  }
  v14 = 0;
LABEL_27:
  std::_Sort<unsigned short *,__int64>(v10, v9, v9 - v10);
  v15 = v10;
  if ( v10 != v9 )
  {
    while ( 1 )
    {
      v16 = v15++;
      if ( v15 == v9 )
        break;
      if ( *v16 == *v15 )
      {
        while ( ++v15 != v9 )
        {
          if ( *v16 != *v15 )
            *++v16 = *v15;
        }
        v17 = v16 + 1;
        goto LABEL_36;
      }
    }
  }
  v17 = v9;
LABEL_36:
  if ( v17 != v9 )
  {
    LODWORD(pExceptionObject[0]) = -2147024809;
    throw (long *)pExceptionObject;
  }
  if ( v14 )
  {
    v20[0] = 120;
    if ( v20 >= v9 || v10 > v20 )
    {
      if ( v9 == v4 )
      {
        std::vector<unsigned short>::_Reserve(&v21);
        v9 = (_WORD *)*((_QWORD *)&v21 + 1);
        v10 = (_WORD *)v21;
      }
      *v9 = 120;
    }
    else
    {
      v18 = v20 - v10;
      if ( v9 == v4 )
      {
        std::vector<unsigned short>::_Reserve(&v21);
        v9 = (_WORD *)*((_QWORD *)&v21 + 1);
        v10 = (_WORD *)v21;
      }
      *v9 = v10[v18];
    }
    *((_QWORD *)&v21 + 1) = ++v9;
  }
  *(_QWORD *)(a1 + 24) = 7;
  std::wstring::_Eos(a1, 0);
  std::wstring::_Construct<std::_Vector_iterator<std::_Vector_val<unsigned short>>>(a1, v10, v9);
  std::vector<enum DX_FEATURE_LEVEL>::~vector<enum DX_FEATURE_LEVEL>(&v21);
  return a1;
}

```

## disassembly

```asm
0x18001fa7c  mov     rax, rsp
0x18001fa7f  push    rbp
0x18001fa80  push    rsi
0x18001fa81  push    rdi
0x18001fa82  push    r12
0x18001fa84  push    r13
0x18001fa86  push    r14
0x18001fa88  push    r15
0x18001fa8a  lea     rbp, [rax-68h]
0x18001fa8e  sub     rsp, 130h
0x18001fa95  mov     qword ptr [rsp+160h+var_F8], 0FFFFFFFFFFFFFFFEh
0x18001fa9e  mov     [rax+18h], rbx
0x18001faa2  mov     rax, cs:__security_cookie
0x18001faa9  xor     rax, rsp
0x18001faac  mov     [rbp+60h+var_40], rax
0x18001fab0  mov     rax, rdx
0x18001fab3  mov     r13, rcx
0x18001fab6  mov     qword ptr [rsp+160h+pExceptionObject], rcx
0x18001fabb  xor     ebx, ebx
0x18001fabd  xorps   xmm0, xmm0
0x18001fac0  movdqu  [rsp+160h+var_130+8], xmm0
0x18001fac6  mov     r15d, ebx
0x18001fac9  mov     [rsp+160h+var_118], rbx
0x18001face  lea     r9, [rsp+70h]
0x18001fad3  lea     edx, [rbx+60h]
0x18001fad6  mov     rcx, rax
0x18001fad9  call    ?GetSubtagFields@CLanguage@Internal@Windows@@QEBAJW4BCP47_SUBTAG_FLAGS@23@_KPEAGPEA_K@Z; Windows::Internal::CLanguage::GetSubtagFields(Windows::Internal::BCP47_SUBTAG_FLAGS,unsigned __int64,ushort *,unsigned __int64 *)
0x18001fade  test    eax, eax
0x18001fae0  jns     short loc_18001FAF8
0x18001fae2  mov     dword ptr [rsp+160h+pExceptionObject], eax
0x18001fae6  lea     rdx, _TI1J; pThrowInfo
0x18001faed  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18001faf2  call    _CxxThrowException_0
0x18001faf8  lea     rsi, [rsp+70h]
0x18001fafd  lea     rcx, [rsp+70h]
0x18001fb02  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fb06  inc     rax
0x18001fb09  cmp     [rcx+rax*2], bx
0x18001fb0d  jnz     short loc_18001FB06
0x18001fb0f  lea     r12, [rsp+72h]
0x18001fb14  lea     r12, [r12+rax*2]
0x18001fb18  mov     byte ptr [rsp+160h+var_130], bl
0x18001fb1c  mov     ecx, 78h ; 'x'
0x18001fb21  mov     rbx, [rsp+160h+var_120]
0x18001fb26  mov     rdi, qword ptr [rsp+160h+var_130+8]
0x18001fb2b  cmp     rsi, r12
0x18001fb2e  jz      loc_18001FBDE
0x18001fb34  lea     r14, [rsi+2]
0x18001fb38  jmp     short loc_18001FB45
0x18001fb3a  cmp     word ptr [r14], 2Dh ; '-'
0x18001fb3f  jz      short loc_18001FB4A
0x18001fb41  add     r14, 2
0x18001fb45  cmp     r14, r12
0x18001fb48  jnz     short loc_18001FB3A
0x18001fb4a  mov     rax, r14
0x18001fb4d  sub     rax, rsi
0x18001fb50  cmp     rax, 2
0x18001fb54  jnz     short loc_18001FBC6
0x18001fb56  cmp     [rsi], cx
0x18001fb59  jz      short loc_18001FBD9
0x18001fb5b  cmp     rsi, rbx
0x18001fb5e  jnb     short loc_18001FB94
0x18001fb60  cmp     rdi, rsi
0x18001fb63  ja      short loc_18001FB94
0x18001fb65  sub     rsi, rdi
0x18001fb68  sar     rsi, 1
0x18001fb6b  cmp     rbx, r15
0x18001fb6e  jnz     short loc_18001FB8E
0x18001fb70  lea     rcx, [rsp+160h+var_130+8]
0x18001fb75  call    ?_Reserve@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reserve(unsigned __int64)
0x18001fb7a  mov     r15, [rsp+160h+var_118]
0x18001fb7f  mov     rbx, [rsp+160h+var_120]
0x18001fb84  mov     rdi, qword ptr [rsp+160h+var_130+8]
0x18001fb89  mov     ecx, 78h ; 'x'
0x18001fb8e  movzx   eax, word ptr [rdi+rsi*2]
0x18001fb92  jmp     short loc_18001FBBA
0x18001fb94  cmp     rbx, r15
0x18001fb97  jnz     short loc_18001FBB7
0x18001fb99  lea     rcx, [rsp+160h+var_130+8]
0x18001fb9e  call    ?_Reserve@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reserve(unsigned __int64)
0x18001fba3  mov     r15, [rsp+160h+var_118]
0x18001fba8  mov     rbx, [rsp+160h+var_120]
0x18001fbad  mov     rdi, qword ptr [rsp+160h+var_130+8]
0x18001fbb2  mov     ecx, 78h ; 'x'
0x18001fbb7  movzx   eax, word ptr [rsi]
0x18001fbba  mov     [rbx], ax
0x18001fbbd  add     rbx, 2
0x18001fbc1  mov     [rsp+160h+var_120], rbx
0x18001fbc6  lea     rax, [r14+2]
0x18001fbca  mov     rsi, r14
0x18001fbcd  cmp     r14, r12
0x18001fbd0  cmovnz  rsi, rax
0x18001fbd4  jmp     loc_18001FB2B
0x18001fbd9  mov     r14b, 1
0x18001fbdc  jmp     short loc_18001FBE3
0x18001fbde  mov     r14b, byte ptr [rsp+160h+var_130]
0x18001fbe3  mov     r8, rbx
0x18001fbe6  sub     r8, rdi
0x18001fbe9  sar     r8, 1
0x18001fbec  mov     rdx, rbx
0x18001fbef  mov     rcx, rdi
0x18001fbf2  call    ??$_Sort@PEAG_J@std@@YAXPEAG0_J@Z; std::_Sort<ushort *,__int64>(ushort *,ushort *,__int64)
0x18001fbf7  mov     rcx, rdi
0x18001fbfa  cmp     rdi, rbx
0x18001fbfd  jz      short loc_18001FC33
0x18001fbff  mov     rdx, rcx
0x18001fc02  add     rcx, 2
0x18001fc06  cmp     rcx, rbx
0x18001fc09  jz      short loc_18001FC33
0x18001fc0b  movzx   eax, word ptr [rcx]
0x18001fc0e  cmp     [rdx], ax
0x18001fc11  jnz     short loc_18001FBFF
0x18001fc13  jmp     short loc_18001FC24
0x18001fc15  movzx   eax, word ptr [rcx]
0x18001fc18  cmp     [rdx], ax
0x18001fc1b  jz      short loc_18001FC24
0x18001fc1d  add     rdx, 2
0x18001fc21  mov     [rdx], ax
0x18001fc24  add     rcx, 2
0x18001fc28  cmp     rcx, rbx
0x18001fc2b  jnz     short loc_18001FC15
0x18001fc2d  add     rdx, 2
0x18001fc31  jmp     short loc_18001FC36
0x18001fc33  mov     rdx, rbx
0x18001fc36  cmp     rdx, rbx
0x18001fc39  jnz     loc_18001FD09
0x18001fc3f  test    r14b, r14b
0x18001fc42  jz      short loc_18001FCB4
0x18001fc44  mov     esi, 78h ; 'x'
0x18001fc49  mov     word ptr [rsp+160h+var_130+2], si
0x18001fc4e  lea     rax, [rsp+160h+var_130+2]
0x18001fc53  cmp     rax, rbx
0x18001fc56  jnb     short loc_18001FC8F
0x18001fc58  lea     rax, [rsp+160h+var_130+2]
0x18001fc5d  cmp     rdi, rax
0x18001fc60  ja      short loc_18001FC8F
0x18001fc62  lea     rsi, [rsp+160h+var_130+2]
0x18001fc67  sub     rsi, rdi
0x18001fc6a  sar     rsi, 1
0x18001fc6d  cmp     rbx, r15
0x18001fc70  jnz     short loc_18001FC86
0x18001fc72  lea     rcx, [rsp+160h+var_130+8]
0x18001fc77  call    ?_Reserve@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reserve(unsigned __int64)
0x18001fc7c  mov     rbx, [rsp+160h+var_120]
0x18001fc81  mov     rdi, qword ptr [rsp+160h+var_130+8]
0x18001fc86  movzx   eax, word ptr [rdi+rsi*2]
0x18001fc8a  mov     [rbx], ax
0x18001fc8d  jmp     short loc_18001FCAB
0x18001fc8f  cmp     rbx, r15
0x18001fc92  jnz     short loc_18001FCA8
0x18001fc94  lea     rcx, [rsp+160h+var_130+8]
0x18001fc99  call    ?_Reserve@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reserve(unsigned __int64)
0x18001fc9e  mov     rbx, [rsp+160h+var_120]
0x18001fca3  mov     rdi, qword ptr [rsp+160h+var_130+8]
0x18001fca8  mov     [rbx], si
0x18001fcab  add     rbx, 2
0x18001fcaf  mov     [rsp+160h+var_120], rbx
0x18001fcb4  mov     qword ptr [r13+18h], 7
0x18001fcbc  xor     edx, edx
0x18001fcbe  mov     rcx, r13
0x18001fcc1  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x18001fcc6  mov     r8, rbx
0x18001fcc9  mov     rdx, rdi
0x18001fccc  mov     rcx, r13
0x18001fccf  call    ??$_Construct@V?$_Vector_iterator@V?$_Vector_val@GV?$allocator@G@std@@@std@@@std@@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXV?$_Vector_iterator@V?$_Vector_val@GV?$allocator@G@std@@@std@@@1@0Uforward_iterator_tag@1@@Z; std::wstring::_Construct<std::_Vector_iterator<std::_Vector_val<ushort>>>(std::_Vector_iterator<std::_Vector_val<ushort>>,std::_Vector_iterator<std::_Vector_val<ushort>>,std::forward_iterator_tag)
0x18001fcd4  nop
0x18001fcd5  lea     rcx, [rsp+160h+var_130+8]
0x18001fcda  call    ??1?$vector@W4DX_FEATURE_LEVEL@@V?$allocator@W4DX_FEATURE_LEVEL@@@std@@@std@@QEAA@XZ; std::vector<DX_FEATURE_LEVEL>::~vector<DX_FEATURE_LEVEL>(void)
0x18001fcdf  mov     rax, r13
0x18001fce2  mov     rcx, [rbp+60h+var_40]
0x18001fce6  xor     rcx, rsp; StackCookie
0x18001fce9  call    __security_check_cookie
0x18001fcee  mov     rbx, [rsp+160h+arg_10]
0x18001fcf6  add     rsp, 130h
0x18001fcfd  pop     r15
0x18001fcff  pop     r14
0x18001fd01  pop     r13
0x18001fd03  pop     r12
0x18001fd05  pop     rdi
0x18001fd06  pop     rsi
0x18001fd07  pop     rbp
0x18001fd08  retn
0x18001fd09  mov     dword ptr [rsp+160h+pExceptionObject], 80070057h
0x18001fd11  lea     rdx, _TI1J; pThrowInfo
0x18001fd18  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18001fd1d  call    _CxxThrowException_0
```
