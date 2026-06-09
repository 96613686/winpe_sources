# SplitPath(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x18007d7cc`
- end: `0x18007da67`
- name: `?SplitPath@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAV12@1@Z`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x18007eb20`

## callees

- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x18007d7cc`
- `0x18007df88`
- `0x18007e064`
- `0x18007e15c`
- `0x18007e288`
- `0x18007e328`

## string_xrefs

- `0x18007d811`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007d8a3`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007d8e2`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007d941`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007d993`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007d9e3`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007d82b`: `SplitPath`
- `0x18007d8ba`: `SplitPath`
- `0x18007d8fc`: `SplitPath`
- `0x18007d95b`: `SplitPath`
- `0x18007d9ad`: `SplitPath`
- `0x18007d9fa`: `SplitPath`
- `0x18007d8c5`: `LocalFilePart.assign(FullPath.c_str())`
- `0x18007d83b`: `FullPath.length() > 0`
- `0x18007d967`: `FullPath.copy(LocalDirectoryPart.data(), SplitIndex)`
- `0x18007d908`: `LocalDirectoryPart.resize(SplitIndex)`
- `0x18007da05`: `FullPath.copy(LocalFilePart.data(), FilePartLength, SplitIndex + 1)`

## pseudocode

```c
__int64 __fastcall SplitPath(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  __int64 v6; // rbx
  __int64 v7; // rbx
  __int64 i; // rbx
  const char **v11; // rdx
  unsigned int v12; // ebx
  __int64 v13; // rsi
  const char *v14; // [rsp+20h] [rbp-E0h] BYREF
  const char *v15; // [rsp+28h] [rbp-D8h]
  __int64 v16; // [rsp+30h] [rbp-D0h]
  const char *v17; // [rsp+38h] [rbp-C8h]
  _QWORD v18[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v19[4]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v20[4]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v21[4]; // [rsp+A0h] [rbp-60h] BYREF
  int v22; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v23[2]; // [rsp+C8h] [rbp-38h] BYREF
  _WORD v24[8]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v25[2]; // [rsp+E8h] [rbp-18h] BYREF
  _WORD v26[8]; // [rsp+F8h] [rbp-8h] BYREF

  v4 = *a1;
  v6 = a1[1] - *a1;
  v22 = 0;
  v7 = v6 >> 1;
  if ( v7 )
  {
    v25[0] = v26;
    v25[1] = v26;
    v26[0] = 0;
    v23[0] = v24;
    v23[1] = v24;
    v24[0] = 0;
    for ( i = v7 - 1; ; --i )
    {
      if ( i == -1 )
      {
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                 v23,
                                 v4) )
        {
          v21[2] = 98;
          v21[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
          v11 = (const char **)v21;
          v21[1] = "SplitPath";
          v21[3] = "LocalFilePart.assign(FullPath.c_str())";
LABEL_11:
          v12 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                  &v22,
                  v11,
                  3221225495LL);
          goto LABEL_19;
        }
        goto LABEL_18;
      }
      if ( *(_WORD *)(v4 + 2 * i) == 92 )
        break;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(v25, i) )
    {
      v16 = 102;
      v14 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v11 = &v14;
      v15 = "SplitPath";
      v17 = "LocalDirectoryPart.resize(SplitIndex)";
      goto LABEL_11;
    }
    if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::copy(a1, v25[0], i, 0) )
    {
      v18[2] = 103;
      v18[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v11 = (const char **)v18;
      v18[1] = "SplitPath";
      v18[3] = "FullPath.copy(LocalDirectoryPart.data(), SplitIndex)";
      goto LABEL_11;
    }
    v13 = ((a1[1] - *a1) >> 1) - i;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                             v23,
                             v13 - 1) )
    {
      v19[2] = 106;
      v19[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v11 = (const char **)v19;
      v19[1] = "SplitPath";
      v19[3] = "LocalFilePart.resize(FilePartLength)";
      goto LABEL_11;
    }
    if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::copy(a1, v23[0], v13 - 1, i + 1) )
    {
      v20[2] = 107;
      v20[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v11 = (const char **)v20;
      v20[1] = "SplitPath";
      v20[3] = "FullPath.copy(LocalFilePart.data(), FilePartLength, SplitIndex + 1)";
      goto LABEL_11;
    }
LABEL_18:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(a2, v25);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(a3, v23);
    v12 = 0;
LABEL_19:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v23);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v25);
    return v12;
  }
  else
  {
    v16 = 88;
    v14 = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v15 = "SplitPath";
    v17 = "FullPath.length() > 0";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v22,
             &v14);
  }
}

```

## disassembly

```asm
0x18007d7cc  mov     [rsp-8+arg_18], rbx
0x18007d7d1  push    rbp
0x18007d7d2  push    rsi
0x18007d7d3  push    rdi
0x18007d7d4  push    r14
0x18007d7d6  push    r15
0x18007d7d8  lea     rbp, [rsp-10h]
0x18007d7dd  sub     rsp, 110h
0x18007d7e4  mov     rax, cs:__security_cookie
0x18007d7eb  xor     rax, rsp
0x18007d7ee  mov     [rbp+30h+var_28], rax
0x18007d7f2  mov     rbx, [rcx+8]
0x18007d7f6  mov     r14, rdx
0x18007d7f9  mov     rdx, [rcx]
0x18007d7fc  mov     r15, r8
0x18007d7ff  sub     rbx, rdx
0x18007d802  mov     [rbp+30h+var_70], 0
0x18007d809  sar     rbx, 1
0x18007d80c  mov     rdi, rcx
0x18007d80f  jnz     short loc_18007D851
0x18007d811  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007d818  mov     [rsp+130h+var_100], 58h ; 'X'
0x18007d821  mov     [rsp+130h+var_110], rax
0x18007d826  lea     rdx, [rsp+130h+var_110]
0x18007d82b  lea     rax, aSplitpath; "SplitPath"
0x18007d832  mov     [rsp+130h+var_108], rax
0x18007d837  lea     rcx, [rbp+30h+var_70]
0x18007d83b  lea     rax, aFullpathLength; "FullPath.length() > 0"
0x18007d842  mov     [rsp+130h+var_F8], rax
0x18007d847  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007d84c  jmp     loc_18007DA43
0x18007d851  lea     rax, [rbp+30h+var_38]
0x18007d855  mov     [rbp+30h+var_48], rax
0x18007d859  lea     rax, [rbp+30h+var_38]
0x18007d85d  mov     [rbp+30h+var_40], rax
0x18007d861  xor     eax, eax
0x18007d863  mov     [rbp+30h+var_38], ax
0x18007d867  lea     rax, [rbp+30h+var_58]
0x18007d86b  mov     [rbp+30h+var_68], rax
0x18007d86f  lea     rax, [rbp+30h+var_58]
0x18007d873  mov     [rbp+30h+var_60], rax
0x18007d877  xor     eax, eax
0x18007d879  mov     [rbp+30h+var_58], ax
0x18007d87d  dec     rbx
0x18007d880  jmp     short loc_18007D88C
0x18007d882  cmp     word ptr [rdx+rbx*2], 5Ch ; '\'
0x18007d887  jz      short loc_18007D8D2
0x18007d889  dec     rbx
0x18007d88c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18007d890  jnz     short loc_18007D882
0x18007d892  lea     rcx, [rbp+30h+var_68]
0x18007d896  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18007d89b  test    al, al
0x18007d89d  jnz     loc_18007DA15
0x18007d8a3  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007d8aa  mov     [rbp+30h+var_80], 62h ; 'b'
0x18007d8b2  mov     [rbp+30h+var_90], rax
0x18007d8b6  lea     rdx, [rbp+30h+var_90]
0x18007d8ba  lea     rax, aSplitpath; "SplitPath"
0x18007d8c1  mov     [rbp+30h+var_88], rax
0x18007d8c5  lea     rax, aLocalfilepartA; "LocalFilePart.assign(FullPath.c_str())"
0x18007d8cc  mov     [rbp+30h+var_78], rax
0x18007d8d0  jmp     short loc_18007D914
0x18007d8d2  mov     rdx, rbx
0x18007d8d5  lea     rcx, [rbp+30h+var_48]
0x18007d8d9  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18007d8de  test    al, al
0x18007d8e0  jnz     short loc_18007D92A
0x18007d8e2  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007d8e9  mov     [rsp+130h+var_100], 66h ; 'f'
0x18007d8f2  mov     [rsp+130h+var_110], rax
0x18007d8f7  lea     rdx, [rsp+130h+var_110]
0x18007d8fc  lea     rax, aSplitpath; "SplitPath"
0x18007d903  mov     [rsp+130h+var_108], rax
0x18007d908  lea     rax, aLocaldirectory; "LocalDirectoryPart.resize(SplitIndex)"
0x18007d90f  mov     [rsp+130h+var_F8], rax
0x18007d914  mov     r8d, 0C0000017h
0x18007d91a  lea     rcx, [rbp+30h+var_70]
0x18007d91e  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007d923  mov     ebx, eax
0x18007d925  jmp     loc_18007DA2F
0x18007d92a  mov     rdx, [rbp+30h+var_48]
0x18007d92e  xor     r9d, r9d
0x18007d931  mov     r8, rbx
0x18007d934  mov     rcx, rdi
0x18007d937  call    ?copy@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_KPEA_W_K1@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::copy(wchar_t *,unsigned __int64,unsigned __int64)
0x18007d93c  test    rax, rax
0x18007d93f  jnz     short loc_18007D975
0x18007d941  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007d948  mov     [rsp+130h+var_E0], 67h ; 'g'
0x18007d951  mov     [rsp+130h+var_F0], rax
0x18007d956  lea     rdx, [rsp+130h+var_F0]
0x18007d95b  lea     rax, aSplitpath; "SplitPath"
0x18007d962  mov     [rsp+130h+var_E8], rax
0x18007d967  lea     rax, aFullpathCopyLo; "FullPath.copy(LocalDirectoryPart.data()"...
0x18007d96e  mov     [rsp+130h+var_D8], rax
0x18007d973  jmp     short loc_18007D914
0x18007d975  mov     rsi, [rdi+8]
0x18007d979  lea     rcx, [rbp+30h+var_68]
0x18007d97d  sub     rsi, [rdi]
0x18007d980  sar     rsi, 1
0x18007d983  sub     rsi, rbx
0x18007d986  lea     rdx, [rsi-1]
0x18007d98a  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18007d98f  test    al, al
0x18007d991  jnz     short loc_18007D9CA
0x18007d993  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007d99a  mov     [rsp+130h+var_C0], 6Ah ; 'j'
0x18007d9a3  mov     [rsp+130h+var_D0], rax
0x18007d9a8  lea     rdx, [rsp+130h+var_D0]
0x18007d9ad  lea     rax, aSplitpath; "SplitPath"
0x18007d9b4  mov     [rsp+130h+var_C8], rax
0x18007d9b9  lea     rax, aLocalfilepartR; "LocalFilePart.resize(FilePartLength)"
0x18007d9c0  mov     [rsp+130h+var_B8], rax
0x18007d9c5  jmp     loc_18007D914
0x18007d9ca  mov     rdx, [rbp+30h+var_68]
0x18007d9ce  lea     r9, [rbx+1]
0x18007d9d2  lea     r8, [rsi-1]
0x18007d9d6  mov     rcx, rdi
0x18007d9d9  call    ?copy@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_KPEA_W_K1@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::copy(wchar_t *,unsigned __int64,unsigned __int64)
0x18007d9de  test    rax, rax
0x18007d9e1  jnz     short loc_18007DA15
0x18007d9e3  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007d9ea  mov     [rbp+30h+var_A0], 6Bh ; 'k'
0x18007d9f2  mov     [rbp+30h+var_B0], rax
0x18007d9f6  lea     rdx, [rbp+30h+var_B0]
0x18007d9fa  lea     rax, aSplitpath; "SplitPath"
0x18007da01  mov     [rbp+30h+var_A8], rax
0x18007da05  lea     rax, aFullpathCopyLo_0; "FullPath.copy(LocalFilePart.data(), Fil"...
0x18007da0c  mov     [rbp+30h+var_98], rax
0x18007da10  jmp     loc_18007D914
0x18007da15  lea     rdx, [rbp+30h+var_48]
0x18007da19  mov     rcx, r14
0x18007da1c  call    ?swap@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAXAEAV12@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18007da21  lea     rdx, [rbp+30h+var_68]
0x18007da25  mov     rcx, r15
0x18007da28  call    ?swap@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAXAEAV12@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18007da2d  xor     ebx, ebx
0x18007da2f  lea     rcx, [rbp+30h+var_68]
0x18007da33  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007da38  lea     rcx, [rbp+30h+var_48]
0x18007da3c  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007da41  mov     eax, ebx
0x18007da43  mov     rcx, [rbp+30h+var_28]
0x18007da47  xor     rcx, rsp; StackCookie
0x18007da4a  call    __security_check_cookie
0x18007da4f  mov     rbx, [rsp+130h+arg_18]
0x18007da57  add     rsp, 110h
0x18007da5e  pop     r15
0x18007da60  pop     r14
0x18007da62  pop     rdi
0x18007da63  pop     rsi
0x18007da64  pop     rbp
0x18007da65  retn
```
