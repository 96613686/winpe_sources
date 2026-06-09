# SplitPath(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x18007e758`
- end: `0x18007e9f3`
- name: `?SplitPath@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAV12@1@Z`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x18007faa0`

## callees

- `0x18001f4ac`
- `0x18001f5d4`
- `0x1800293a0`
- `0x18007e758`
- `0x18007ef14`
- `0x18007eff0`
- `0x18007f0e8`
- `0x18007f214`
- `0x18007f2b4`

## string_xrefs

- `0x18007e79d`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e82f`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e86e`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e8cd`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e91f`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e96f`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e7c7`: `FullPath.length() > 0`
- `0x18007e7b7`: `SplitPath`
- `0x18007e846`: `SplitPath`
- `0x18007e888`: `SplitPath`
- `0x18007e8e7`: `SplitPath`
- `0x18007e939`: `SplitPath`
- `0x18007e986`: `SplitPath`
- `0x18007e894`: `LocalDirectoryPart.resize(SplitIndex)`
- `0x18007e851`: `LocalFilePart.assign(FullPath.c_str())`
- `0x18007e8f3`: `FullPath.copy(LocalDirectoryPart.data(), SplitIndex)`
- `0x18007e991`: `FullPath.copy(LocalFilePart.data(), FilePartLength, SplitIndex + 1)`

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
0x18007e758  mov     [rsp-8+arg_18], rbx
0x18007e75d  push    rbp
0x18007e75e  push    rsi
0x18007e75f  push    rdi
0x18007e760  push    r14
0x18007e762  push    r15
0x18007e764  lea     rbp, [rsp-10h]
0x18007e769  sub     rsp, 110h
0x18007e770  mov     rax, cs:__security_cookie
0x18007e777  xor     rax, rsp
0x18007e77a  mov     [rbp+30h+var_28], rax
0x18007e77e  mov     rbx, [rcx+8]
0x18007e782  mov     r14, rdx
0x18007e785  mov     rdx, [rcx]
0x18007e788  mov     r15, r8
0x18007e78b  sub     rbx, rdx
0x18007e78e  mov     [rbp+30h+var_70], 0
0x18007e795  sar     rbx, 1
0x18007e798  mov     rdi, rcx
0x18007e79b  jnz     short loc_18007E7DD
0x18007e79d  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e7a4  mov     [rsp+130h+var_100], 58h ; 'X'
0x18007e7ad  mov     [rsp+130h+var_110], rax
0x18007e7b2  lea     rdx, [rsp+130h+var_110]
0x18007e7b7  lea     rax, aSplitpath; "SplitPath"
0x18007e7be  mov     [rsp+130h+var_108], rax
0x18007e7c3  lea     rcx, [rbp+30h+var_70]
0x18007e7c7  lea     rax, aFullpathLength; "FullPath.length() > 0"
0x18007e7ce  mov     [rsp+130h+var_F8], rax
0x18007e7d3  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007e7d8  jmp     loc_18007E9CF
0x18007e7dd  lea     rax, [rbp+30h+var_38]
0x18007e7e1  mov     [rbp+30h+var_48], rax
0x18007e7e5  lea     rax, [rbp+30h+var_38]
0x18007e7e9  mov     [rbp+30h+var_40], rax
0x18007e7ed  xor     eax, eax
0x18007e7ef  mov     [rbp+30h+var_38], ax
0x18007e7f3  lea     rax, [rbp+30h+var_58]
0x18007e7f7  mov     [rbp+30h+var_68], rax
0x18007e7fb  lea     rax, [rbp+30h+var_58]
0x18007e7ff  mov     [rbp+30h+var_60], rax
0x18007e803  xor     eax, eax
0x18007e805  mov     [rbp+30h+var_58], ax
0x18007e809  dec     rbx
0x18007e80c  jmp     short loc_18007E818
0x18007e80e  cmp     word ptr [rdx+rbx*2], 5Ch ; '\'
0x18007e813  jz      short loc_18007E85E
0x18007e815  dec     rbx
0x18007e818  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18007e81c  jnz     short loc_18007E80E
0x18007e81e  lea     rcx, [rbp+30h+var_68]
0x18007e822  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18007e827  test    al, al
0x18007e829  jnz     loc_18007E9A1
0x18007e82f  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e836  mov     [rbp+30h+var_80], 62h ; 'b'
0x18007e83e  mov     [rbp+30h+var_90], rax
0x18007e842  lea     rdx, [rbp+30h+var_90]
0x18007e846  lea     rax, aSplitpath; "SplitPath"
0x18007e84d  mov     [rbp+30h+var_88], rax
0x18007e851  lea     rax, aLocalfilepartA; "LocalFilePart.assign(FullPath.c_str())"
0x18007e858  mov     [rbp+30h+var_78], rax
0x18007e85c  jmp     short loc_18007E8A0
0x18007e85e  mov     rdx, rbx
0x18007e861  lea     rcx, [rbp+30h+var_48]
0x18007e865  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18007e86a  test    al, al
0x18007e86c  jnz     short loc_18007E8B6
0x18007e86e  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e875  mov     [rsp+130h+var_100], 66h ; 'f'
0x18007e87e  mov     [rsp+130h+var_110], rax
0x18007e883  lea     rdx, [rsp+130h+var_110]
0x18007e888  lea     rax, aSplitpath; "SplitPath"
0x18007e88f  mov     [rsp+130h+var_108], rax
0x18007e894  lea     rax, aLocaldirectory; "LocalDirectoryPart.resize(SplitIndex)"
0x18007e89b  mov     [rsp+130h+var_F8], rax
0x18007e8a0  mov     r8d, 0C0000017h
0x18007e8a6  lea     rcx, [rbp+30h+var_70]
0x18007e8aa  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007e8af  mov     ebx, eax
0x18007e8b1  jmp     loc_18007E9BB
0x18007e8b6  mov     rdx, [rbp+30h+var_48]
0x18007e8ba  xor     r9d, r9d
0x18007e8bd  mov     r8, rbx
0x18007e8c0  mov     rcx, rdi
0x18007e8c3  call    ?copy@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_KPEA_W_K1@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::copy(wchar_t *,unsigned __int64,unsigned __int64)
0x18007e8c8  test    rax, rax
0x18007e8cb  jnz     short loc_18007E901
0x18007e8cd  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e8d4  mov     [rsp+130h+var_E0], 67h ; 'g'
0x18007e8dd  mov     [rsp+130h+var_F0], rax
0x18007e8e2  lea     rdx, [rsp+130h+var_F0]
0x18007e8e7  lea     rax, aSplitpath; "SplitPath"
0x18007e8ee  mov     [rsp+130h+var_E8], rax
0x18007e8f3  lea     rax, aFullpathCopyLo; "FullPath.copy(LocalDirectoryPart.data()"...
0x18007e8fa  mov     [rsp+130h+var_D8], rax
0x18007e8ff  jmp     short loc_18007E8A0
0x18007e901  mov     rsi, [rdi+8]
0x18007e905  lea     rcx, [rbp+30h+var_68]
0x18007e909  sub     rsi, [rdi]
0x18007e90c  sar     rsi, 1
0x18007e90f  sub     rsi, rbx
0x18007e912  lea     rdx, [rsi-1]
0x18007e916  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18007e91b  test    al, al
0x18007e91d  jnz     short loc_18007E956
0x18007e91f  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e926  mov     [rsp+130h+var_C0], 6Ah ; 'j'
0x18007e92f  mov     [rsp+130h+var_D0], rax
0x18007e934  lea     rdx, [rsp+130h+var_D0]
0x18007e939  lea     rax, aSplitpath; "SplitPath"
0x18007e940  mov     [rsp+130h+var_C8], rax
0x18007e945  lea     rax, aLocalfilepartR; "LocalFilePart.resize(FilePartLength)"
0x18007e94c  mov     [rsp+130h+var_B8], rax
0x18007e951  jmp     loc_18007E8A0
0x18007e956  mov     rdx, [rbp+30h+var_68]
0x18007e95a  lea     r9, [rbx+1]
0x18007e95e  lea     r8, [rsi-1]
0x18007e962  mov     rcx, rdi
0x18007e965  call    ?copy@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_KPEA_W_K1@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::copy(wchar_t *,unsigned __int64,unsigned __int64)
0x18007e96a  test    rax, rax
0x18007e96d  jnz     short loc_18007E9A1
0x18007e96f  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e976  mov     [rbp+30h+var_A0], 6Bh ; 'k'
0x18007e97e  mov     [rbp+30h+var_B0], rax
0x18007e982  lea     rdx, [rbp+30h+var_B0]
0x18007e986  lea     rax, aSplitpath; "SplitPath"
0x18007e98d  mov     [rbp+30h+var_A8], rax
0x18007e991  lea     rax, aFullpathCopyLo_0; "FullPath.copy(LocalFilePart.data(), Fil"...
0x18007e998  mov     [rbp+30h+var_98], rax
0x18007e99c  jmp     loc_18007E8A0
0x18007e9a1  lea     rdx, [rbp+30h+var_48]
0x18007e9a5  mov     rcx, r14
0x18007e9a8  call    ?swap@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAXAEAV12@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18007e9ad  lea     rdx, [rbp+30h+var_68]
0x18007e9b1  mov     rcx, r15
0x18007e9b4  call    ?swap@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAXAEAV12@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18007e9b9  xor     ebx, ebx
0x18007e9bb  lea     rcx, [rbp+30h+var_68]
0x18007e9bf  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007e9c4  lea     rcx, [rbp+30h+var_48]
0x18007e9c8  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007e9cd  mov     eax, ebx
0x18007e9cf  mov     rcx, [rbp+30h+var_28]
0x18007e9d3  xor     rcx, rsp; StackCookie
0x18007e9d6  call    __security_check_cookie
0x18007e9db  mov     rbx, [rsp+130h+arg_18]
0x18007e9e3  add     rsp, 110h
0x18007e9ea  pop     r15
0x18007e9ec  pop     r14
0x18007e9ee  pop     rdi
0x18007e9ef  pop     rsi
0x18007e9f0  pop     rbp
0x18007e9f1  retn
```
