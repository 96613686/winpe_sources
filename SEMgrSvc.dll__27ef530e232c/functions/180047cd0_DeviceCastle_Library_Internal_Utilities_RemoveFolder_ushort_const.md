# DeviceCastle::Library::Internal::Utilities::RemoveFolder(ushort const *)

- ea: `0x180047cd0`
- end: `0x180047f81`
- name: `?RemoveFolder@Utilities@Internal@Library@DeviceCastle@@SAJPEBG@Z`
- size: `689`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180047cd0`
- `0x180049efc`
- `0x18005bcb8`

## callees

- `0x1800049a0`
- `0x18000584c`
- `0x180013014`
- `0x180013274`
- `0x1800194a8`
- `0x180047250`
- `0x18004736c`
- `0x1800474d8`
- `0x180047a04`
- `0x180047cd0`
- `0x180048048`
- `0x180048060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047f63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047f63`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180047f24`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180047f24`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180047f0e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180047f0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DeviceCastle::Library::Internal::Utilities::RemoveFolder(const unsigned __int16 *a1)
{
  signed int FileList; // ebx
  __int64 v3; // r8
  unsigned __int64 v4; // rdx
  void **v5; // rdi
  __int64 v6; // rbx
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // r8
  void **v9; // rax
  void **v10; // r9
  void **v11; // rcx
  unsigned __int64 v12; // r14
  void **v13; // rcx
  void **v14; // rcx
  __int64 i; // rdi
  void **v16; // rcx
  void **v17; // rcx
  unsigned __int64 v18; // rdx
  void **v19; // rcx
  __int64 j; // rbx
  void **v21; // rcx
  signed int LastError; // eax
  __int128 v24; // [rsp+20h] [rbp-48h] BYREF
  __int64 v25; // [rsp+30h] [rbp-38h]
  void *Src[2]; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int64 v27; // [rsp+48h] [rbp-20h]
  unsigned __int64 v28; // [rsp+50h] [rbp-18h]

  v24 = 0;
  v25 = 0;
  *(_OWORD *)Src = 0;
  v27 = 0;
  v28 = 7;
  LOWORD(Src[0]) = 0;
  if ( a1 )
  {
    if ( *a1 )
    {
      ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAX_K_Z___V___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(Src);
      v27 = 0;
      v4 = -1;
      do
        ++v4;
      while ( a1[v4] );
      if ( v4 > v28 )
      {
        ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
          Src,
          v4,
          v3,
          a1);
      }
      else
      {
        v5 = Src;
        if ( v28 > 7 )
          v5 = (void **)Src[0];
        v27 = v4;
        v6 = 2 * v4;
        memmove_0(v5, a1, 2 * v4);
        *(_WORD *)((char *)v5 + v6) = 0;
      }
      v7 = v27;
      if ( !v27 )
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
      v8 = v28;
      v9 = Src;
      v10 = (void **)Src[0];
      if ( v28 > 7 )
        v9 = (void **)Src[0];
      if ( *((_WORD *)v9 + v27 - 1) != 92 )
      {
        v11 = Src;
        if ( v27 >= v28 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
        }
        else
        {
          ++v27;
          if ( v28 > 7 )
            v11 = (void **)Src[0];
          *(_DWORD *)((char *)v11 + 2 * v7) = 92;
        }
        v10 = (void **)Src[0];
        v8 = v28;
      }
      v12 = v27;
      v13 = Src;
      if ( v27 >= v8 )
      {
        ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
      }
      else
      {
        ++v27;
        if ( v8 > 7 )
          v13 = v10;
        *(_DWORD *)((char *)v13 + 2 * v12) = 42;
      }
      v14 = Src;
      if ( v28 > 7 )
        v14 = (void **)Src[0];
      FileList = DeviceCastle::Library::Internal::Utilities::GetFileList((LPCWSTR)v14);
      if ( FileList >= 0 )
      {
        for ( i = v24; ; i += 32 )
        {
          std::wstring::resize(Src);
          v17 = Src;
          if ( i == *((_QWORD *)&v24 + 1) )
            break;
          std::wstring::operator+=(Src);
          v16 = Src;
          if ( v28 > 7 )
            v16 = (void **)Src[0];
          FileList = DeviceCastle::Library::Internal::Utilities::RemoveFolder((const unsigned __int16 *)v16);
          if ( FileList < 0 )
            goto LABEL_52;
        }
        v18 = v27;
        if ( v27 >= v28 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
        }
        else
        {
          ++v27;
          if ( v28 > 7 )
            v17 = (void **)Src[0];
          *(_DWORD *)((char *)v17 + 2 * v18) = 42;
        }
        v19 = Src;
        if ( v28 > 7 )
          v19 = (void **)Src[0];
        FileList = DeviceCastle::Library::Internal::Utilities::GetFileList((LPCWSTR)v19);
        if ( FileList >= 0 )
        {
          for ( j = v24; j != *((_QWORD *)&v24 + 1); j += 32 )
          {
            std::wstring::resize(Src);
            std::wstring::operator+=(Src);
            v21 = Src;
            if ( v28 > 7 )
              v21 = (void **)Src[0];
            if ( !DeleteFileW((LPCWSTR)v21) )
              goto LABEL_53;
          }
          if ( RemoveDirectoryW(a1) )
          {
            FileList = 0;
            goto LABEL_52;
          }
LABEL_53:
          LastError = GetLastError();
          FileList = LastError;
          if ( LastError > 0 )
            FileList = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
    else
    {
      FileList = -2147024809;
    }
  }
  else
  {
    FileList = -2147467261;
  }
LABEL_52:
  std::wstring::~wstring(Src);
  std::vector<std::wstring>::_Tidy(&v24);
  return (unsigned int)FileList;
}

```

## disassembly

```asm
0x180047cd0  push    rbp
0x180047cd2  push    rbx
0x180047cd3  push    rsi
0x180047cd4  push    rdi
0x180047cd5  push    r12
0x180047cd7  push    r13
0x180047cd9  push    r14
0x180047cdb  push    r15
0x180047cdd  mov     rbp, rsp
0x180047ce0  sub     rsp, 68h
0x180047ce4  mov     rax, cs:__security_cookie
0x180047ceb  xor     rax, rsp
0x180047cee  mov     [rbp+var_10], rax
0x180047cf2  mov     rsi, rcx
0x180047cf5  xorps   xmm0, xmm0
0x180047cf8  movdqu  [rbp+var_48], xmm0
0x180047cfd  xor     r13d, r13d
0x180047d00  mov     [rbp+var_38], r13
0x180047d04  movups  xmmword ptr [rbp+Src], xmm0
0x180047d08  mov     [rbp+var_20], r13
0x180047d0c  mov     [rbp+var_18], 7
0x180047d14  mov     word ptr [rbp+Src], r13w
0x180047d19  test    rcx, rcx
0x180047d1c  jnz     short loc_180047D28
0x180047d1e  mov     ebx, 80004003h
0x180047d23  jmp     loc_180047F31
0x180047d28  cmp     r13w, [rcx]
0x180047d2c  jnz     short loc_180047D38
0x180047d2e  mov     ebx, 80070057h
0x180047d33  jmp     loc_180047F31
0x180047d38  mov     edx, 104h
0x180047d3d  lea     rcx, [rbp+Src]; Src
0x180047d41  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x180047d46  mov     [rbp+var_20], r13
0x180047d4a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180047d4e  inc     rdx
0x180047d51  cmp     [rsi+rdx*2], r13w
0x180047d56  jnz     short loc_180047D4E
0x180047d58  cmp     rdx, [rbp+var_18]
0x180047d5c  ja      short loc_180047D89
0x180047d5e  lea     rdi, [rbp+Src]
0x180047d62  cmp     [rbp+var_18], 7
0x180047d67  cmova   rdi, [rbp+Src]
0x180047d6c  mov     [rbp+var_20], rdx
0x180047d70  lea     rbx, [rdx+rdx]
0x180047d74  mov     r8, rbx; Size
0x180047d77  mov     rdx, rsi; Src
0x180047d7a  mov     rcx, rdi; void *
0x180047d7d  call    memmove_0
0x180047d82  mov     [rbx+rdi], r13w
0x180047d87  jmp     short loc_180047D95
0x180047d89  mov     r9, rsi
0x180047d8c  lea     rcx, [rbp+Src]
0x180047d90  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180047d95  mov     rdx, [rbp+var_20]
0x180047d99  lea     rcx, [rdx-1]
0x180047d9d  cmp     rdx, rcx
0x180047da0  jbe     loc_180047F7B
0x180047da6  mov     r8, [rbp+var_18]
0x180047daa  lea     rax, [rbp+Src]
0x180047dae  mov     r9, [rbp+Src]
0x180047db2  cmp     r8, 7
0x180047db6  cmova   rax, r9
0x180047dba  mov     r10d, 5Ch ; '\'
0x180047dc0  cmp     r10w, [rax+rcx*2]
0x180047dc5  jz      short loc_180047DF6
0x180047dc7  lea     rcx, [rbp+Src]; Src
0x180047dcb  cmp     rdx, r8
0x180047dce  jnb     short loc_180047DE6
0x180047dd0  lea     rax, [rdx+1]
0x180047dd4  mov     [rbp+var_20], rax
0x180047dd8  cmp     r8, 7
0x180047ddc  cmova   rcx, r9
0x180047de0  mov     [rcx+rdx*2], r10d
0x180047de4  jmp     short loc_180047DEE
0x180047de6  mov     r9d, r10d
0x180047de9  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180047dee  mov     r9, [rbp+Src]
0x180047df2  mov     r8, [rbp+var_18]
0x180047df6  mov     r14, [rbp+var_20]
0x180047dfa  lea     rcx, [rbp+Src]; Src
0x180047dfe  mov     r15d, 2Ah ; '*'
0x180047e04  cmp     r14, r8
0x180047e07  jnb     short loc_180047E1F
0x180047e09  lea     rax, [r14+1]
0x180047e0d  mov     [rbp+var_20], rax
0x180047e11  cmp     r8, 7
0x180047e15  cmova   rcx, r9
0x180047e19  mov     [rcx+r14*2], r15d
0x180047e1d  jmp     short loc_180047E27
0x180047e1f  mov     r9d, r15d
0x180047e22  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180047e27  lea     rcx, [rbp+Src]
0x180047e2b  cmp     [rbp+var_18], 7
0x180047e30  cmova   rcx, [rbp+Src]; lpFileName
0x180047e35  lea     r8, [rbp+var_48]
0x180047e39  mov     dl, 1
0x180047e3b  call    ?GetFileList@Utilities@Internal@Library@DeviceCastle@@SAJPEBG_NAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; DeviceCastle::Library::Internal::Utilities::GetFileList(ushort const *,bool,std::vector<std::wstring> &)
0x180047e40  mov     ebx, eax
0x180047e42  test    eax, eax
0x180047e44  js      loc_180047F31
0x180047e4a  mov     rdi, qword ptr [rbp+var_48]
0x180047e4e  mov     r12, qword ptr [rbp+var_48+8]
0x180047e52  jmp     short loc_180047E7D
0x180047e54  mov     rdx, rdi
0x180047e57  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x180047e5c  lea     rcx, [rbp+Src]
0x180047e60  cmp     [rbp+var_18], 7
0x180047e65  cmova   rcx, [rbp+Src]; unsigned __int16 *
0x180047e6a  call    ?RemoveFolder@Utilities@Internal@Library@DeviceCastle@@SAJPEBG@Z; DeviceCastle::Library::Internal::Utilities::RemoveFolder(ushort const *)
0x180047e6f  mov     ebx, eax
0x180047e71  test    eax, eax
0x180047e73  js      loc_180047F31
0x180047e79  add     rdi, 20h ; ' '
0x180047e7d  mov     rdx, r14
0x180047e80  lea     rcx, [rbp+Src]; Src
0x180047e84  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180047e89  lea     rcx, [rbp+Src]; Src
0x180047e8d  cmp     rdi, r12
0x180047e90  jnz     short loc_180047E54
0x180047e92  mov     rdx, [rbp+var_20]
0x180047e96  cmp     rdx, [rbp+var_18]
0x180047e9a  jnb     short loc_180047EB7
0x180047e9c  lea     rax, [rdx+1]
0x180047ea0  mov     [rbp+var_20], rax
0x180047ea4  cmp     [rbp+var_18], 7
0x180047ea9  cmova   rcx, [rbp+Src]
0x180047eae  mov     dword ptr [rcx+rdx*2], 2Ah ; '*'
0x180047eb5  jmp     short loc_180047EBF
0x180047eb7  mov     r9d, r15d
0x180047eba  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180047ebf  lea     rcx, [rbp+Src]
0x180047ec3  cmp     [rbp+var_18], 7
0x180047ec8  cmova   rcx, [rbp+Src]; lpFileName
0x180047ecd  lea     r8, [rbp+var_48]
0x180047ed1  xor     edx, edx
0x180047ed3  call    ?GetFileList@Utilities@Internal@Library@DeviceCastle@@SAJPEBG_NAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; DeviceCastle::Library::Internal::Utilities::GetFileList(ushort const *,bool,std::vector<std::wstring> &)
0x180047ed8  mov     ebx, eax
0x180047eda  test    eax, eax
0x180047edc  js      short loc_180047F31
0x180047ede  mov     rbx, qword ptr [rbp+var_48]
0x180047ee2  mov     rdi, qword ptr [rbp+var_48+8]
0x180047ee6  jmp     short loc_180047F1C
0x180047ee8  mov     rdx, r14
0x180047eeb  lea     rcx, [rbp+Src]; Src
0x180047eef  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180047ef4  mov     rdx, rbx
0x180047ef7  lea     rcx, [rbp+Src]; Src
0x180047efb  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x180047f00  lea     rcx, [rbp+Src]
0x180047f04  cmp     [rbp+var_18], 7
0x180047f09  cmova   rcx, [rbp+Src]; lpFileName
0x180047f0e  call    cs:__imp_DeleteFileW
0x180047f14  test    eax, eax
0x180047f16  jz      short loc_180047F63
0x180047f18  add     rbx, 20h ; ' '
0x180047f1c  cmp     rbx, rdi
0x180047f1f  jnz     short loc_180047EE8
0x180047f21  mov     rcx, rsi; lpPathName
0x180047f24  call    cs:__imp_RemoveDirectoryW
0x180047f2a  test    eax, eax
0x180047f2c  jz      short loc_180047F63
0x180047f2e  mov     ebx, r13d
0x180047f31  lea     rcx, [rbp+Src]
0x180047f35  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180047f3a  nop
0x180047f3b  lea     rcx, [rbp+var_48]
0x180047f3f  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180047f44  mov     eax, ebx
0x180047f46  mov     rcx, [rbp+var_10]
0x180047f4a  xor     rcx, rsp; StackCookie
0x180047f4d  call    __security_check_cookie
0x180047f52  add     rsp, 68h
0x180047f56  pop     r15
0x180047f58  pop     r14
0x180047f5a  pop     r13
0x180047f5c  pop     r12
0x180047f5e  pop     rdi
0x180047f5f  pop     rsi
0x180047f60  pop     rbx
0x180047f61  pop     rbp
0x180047f62  retn
0x180047f63  call    cs:__imp_GetLastError
0x180047f69  nop
0x180047f6a  mov     ebx, eax
0x180047f6c  test    eax, eax
0x180047f6e  jle     short loc_180047F31
0x180047f70  movzx   ebx, ax
0x180047f73  or      ebx, 80070000h
0x180047f79  jmp     short loc_180047F31
0x180047f7b  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
