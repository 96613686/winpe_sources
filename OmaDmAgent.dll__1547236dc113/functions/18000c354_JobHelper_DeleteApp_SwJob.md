# JobHelper::DeleteApp(_SwJob &)

- ea: `0x18000c354`
- end: `0x18000c580`
- name: `?DeleteApp@JobHelper@@AEAAJAEAU_SwJob@@@Z`
- size: `556`
- prototype: `__int64 __fastcall(JobHelper *__hidden this, struct _SwJob *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18000cb4c`

## callees

- `0x18000702c`
- `0x18000a290`
- `0x18000a3c0`
- `0x18000a6a4`
- `0x18000b468`
- `0x18000bb58`
- `0x18000c354`
- `0x180015298`
- `0x180017690`
- `0x1800187f4`
- `0x180018a44`
- `0x18001a958`
- `0x18001f420`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JobHelper::DeleteApp(JobHelper *this, struct _SwJob *a2)
{
  LPCWSTR v3; // rcx
  int v4; // r8d
  int DoesWebLinkExist; // ebx
  _QWORD *v6; // r9
  _QWORD *v7; // rdi
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  int v10; // eax
  LPCWSTR v11; // rcx
  int v12; // edx
  HSTRING v13; // rax
  _QWORD *v14; // rax
  __int64 *v15; // rax
  __int64 v16; // rcx
  _BYTE v18[40]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v19[304]; // [rsp+60h] [rbp-A0h] BYREF

  PackageInfo::PackageInfo((PackageInfo *)v19);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 214, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  v4 = *((_DWORD *)a2 + 17);
  if ( v4 != 1 )
  {
    if ( *((_DWORD *)a2 + 17) != 2 )
    {
      DoesWebLinkExist = -2147467263;
      if ( v3 != (LPCWSTR)&WPP_GLOBAL_Control && (v3[14] & 4) != 0 )
      {
        v6 = (_QWORD *)((char *)a2 + 32);
        if ( *((_QWORD *)a2 + 7) >= 8u )
          v6 = (_QWORD *)*v6;
        WPP_SF_SdD(
          *((_QWORD *)v3 + 2),
          218,
          (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
          (_DWORD)v6,
          v4,
          1);
      }
      goto LABEL_31;
    }
    v7 = (_QWORD *)((char *)a2 + 32);
    v8 = (_QWORD *)std::wstring::wstring(v18, v7);
    DoesWebLinkExist = WebAppUtil::DoesWebLinkExist(v8);
    if ( DoesWebLinkExist < 0 )
      goto LABEL_31;
    v9 = (_QWORD *)std::wstring::wstring(v18, v7);
    v10 = WebAppUtil::DeleteWebApp(v9);
    DoesWebLinkExist = v10;
    if ( v10 >= 0 )
      goto LABEL_31;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_31;
    if ( v7[3] >= 8u )
      v7 = (_QWORD *)*v7;
    v12 = 217;
LABEL_25:
    WPP_SF_Sd(
      *((_QWORD *)v11 + 2),
      v12,
      (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      (_DWORD)v7,
      v10);
    goto LABEL_31;
  }
  v7 = (_QWORD *)((char *)a2 + 32);
  v13 = (HSTRING)std::wstring::wstring(v18, v7);
  DoesWebLinkExist = FindPackage(v19, v13);
  if ( DoesWebLinkExist < 0 )
    goto LABEL_31;
  v14 = (_QWORD *)std::wstring::wstring(v18, v7);
  v10 = RemovePackage(v14);
  DoesWebLinkExist = v10;
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_31;
    if ( v7[3] >= 8u )
      v7 = (_QWORD *)*v7;
    v12 = 215;
    goto LABEL_25;
  }
  v15 = (__int64 *)std::wstring::wstring(v18, v7);
  DoesWebLinkExist = AppRegistry::DeleteApp(v16, v15);
  if ( DoesWebLinkExist < 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 216, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids);
    DoesWebLinkExist = 0;
  }
LABEL_31:
  PackageInfo::~PackageInfo((PackageInfo *)v19);
  return (unsigned int)DoesWebLinkExist;
}

```

## disassembly

```asm
0x18000c354  mov     [rsp-8+arg_0], rbx
0x18000c359  mov     [rsp-8+arg_10], rsi
0x18000c35e  push    rbp
0x18000c35f  push    rdi
0x18000c360  push    r14
0x18000c362  lea     rbp, [rsp-0A0h]
0x18000c36a  sub     rsp, 1A0h
0x18000c371  mov     rax, cs:__security_cookie
0x18000c378  xor     rax, rsp
0x18000c37b  mov     [rbp+0B0h+var_20], rax
0x18000c382  mov     rdi, rdx
0x18000c385  lea     rcx, [rsp+1B0h+var_150]; this
0x18000c38a  call    ??0PackageInfo@@QEAA@XZ; PackageInfo::PackageInfo(void)
0x18000c38f  nop
0x18000c390  lea     rsi, WPP_GLOBAL_Control
0x18000c397  lea     r14, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000c39e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3a5  cmp     rcx, rsi
0x18000c3a8  jz      short loc_18000C3C8
0x18000c3aa  test    byte ptr [rcx+1Ch], 1
0x18000c3ae  jz      short loc_18000C3C8
0x18000c3b0  mov     edx, 0D6h
0x18000c3b5  mov     r8, r14
0x18000c3b8  mov     rcx, [rcx+10h]
0x18000c3bc  call    WPP_SF_
0x18000c3c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3c8  mov     r8d, [rdi+44h]
0x18000c3cc  mov     edx, r8d
0x18000c3cf  sub     edx, 1
0x18000c3d2  jz      loc_18000C493
0x18000c3d8  cmp     edx, 1
0x18000c3db  jz      short loc_18000C426
0x18000c3dd  mov     ebx, 80004001h
0x18000c3e2  cmp     rcx, rsi
0x18000c3e5  jz      loc_18000C54C
0x18000c3eb  test    byte ptr [rcx+1Ch], 4
0x18000c3ef  jz      loc_18000C54C
0x18000c3f5  lea     r9, [rdi+20h]
0x18000c3f9  cmp     qword ptr [r9+18h], 8
0x18000c3fe  jb      short loc_18000C403
0x18000c400  mov     r9, [r9]
0x18000c403  mov     edx, 0DAh
0x18000c408  mov     [rsp+1B0h+var_188], 80004001h
0x18000c410  mov     [rsp+1B0h+var_190], r8d
0x18000c415  mov     r8, r14
0x18000c418  mov     rcx, [rcx+10h]
0x18000c41c  call    WPP_SF_SdD
0x18000c421  jmp     loc_18000C54C
0x18000c426  add     rdi, 20h ; ' '
0x18000c42a  mov     rdx, rdi
0x18000c42d  lea     rcx, [rsp+1B0h+var_178]
0x18000c432  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c437  mov     rcx, rax
0x18000c43a  call    ?DoesWebLinkExist@WebAppUtil@@SAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WebAppUtil::DoesWebLinkExist(std::wstring)
0x18000c43f  mov     ebx, eax
0x18000c441  test    eax, eax
0x18000c443  js      loc_18000C54C
0x18000c449  mov     rdx, rdi
0x18000c44c  lea     rcx, [rsp+1B0h+var_178]
0x18000c451  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c456  mov     rcx, rax
0x18000c459  call    ?DeleteWebApp@WebAppUtil@@SAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WebAppUtil::DeleteWebApp(std::wstring)
0x18000c45e  mov     ebx, eax
0x18000c460  test    eax, eax
0x18000c462  jns     loc_18000C54C
0x18000c468  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c46f  cmp     rcx, rsi
0x18000c472  jz      loc_18000C54C
0x18000c478  test    byte ptr [rcx+1Ch], 4
0x18000c47c  jz      loc_18000C54C
0x18000c482  cmp     qword ptr [rdi+18h], 8
0x18000c487  jb      short loc_18000C48C
0x18000c489  mov     rdi, [rdi]
0x18000c48c  mov     edx, 0D9h
0x18000c491  jmp     short loc_18000C4F7
0x18000c493  add     rdi, 20h ; ' '
0x18000c497  mov     rdx, rdi
0x18000c49a  lea     rcx, [rsp+1B0h+var_178]
0x18000c49f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c4a4  mov     rdx, rax
0x18000c4a7  lea     rcx, [rsp+1B0h+var_150]
0x18000c4ac  call    ?FindPackage@@YAJAEAUPackageInfo@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FindPackage(PackageInfo &,std::wstring)
0x18000c4b1  mov     ebx, eax
0x18000c4b3  test    eax, eax
0x18000c4b5  js      loc_18000C54C
0x18000c4bb  mov     rdx, rdi
0x18000c4be  lea     rcx, [rsp+1B0h+var_178]
0x18000c4c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c4c8  mov     rcx, rax
0x18000c4cb  call    ?RemovePackage@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RemovePackage(std::wstring)
0x18000c4d0  mov     ebx, eax
0x18000c4d2  test    eax, eax
0x18000c4d4  jns     short loc_18000C50C
0x18000c4d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4dd  cmp     rcx, rsi
0x18000c4e0  jz      short loc_18000C54C
0x18000c4e2  test    byte ptr [rcx+1Ch], 4
0x18000c4e6  jz      short loc_18000C54C
0x18000c4e8  cmp     qword ptr [rdi+18h], 8
0x18000c4ed  jb      short loc_18000C4F2
0x18000c4ef  mov     rdi, [rdi]
0x18000c4f2  mov     edx, 0D7h
0x18000c4f7  mov     [rsp+1B0h+var_190], eax
0x18000c4fb  mov     r9, rdi
0x18000c4fe  mov     r8, r14
0x18000c501  mov     rcx, [rcx+10h]
0x18000c505  call    WPP_SF_Sd
0x18000c50a  jmp     short loc_18000C54C
0x18000c50c  mov     rdx, rdi
0x18000c50f  lea     rcx, [rsp+1B0h+var_178]
0x18000c514  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c519  mov     rdx, rax
0x18000c51c  call    ?DeleteApp@AppRegistry@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AppRegistry::DeleteApp(std::wstring)
0x18000c521  mov     ebx, eax
0x18000c523  test    eax, eax
0x18000c525  jns     short loc_18000C54C
0x18000c527  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c52e  cmp     rcx, rsi
0x18000c531  jz      short loc_18000C54A
0x18000c533  test    byte ptr [rcx+1Ch], 2
0x18000c537  jz      short loc_18000C54A
0x18000c539  mov     edx, 0D8h
0x18000c53e  mov     r8, r14
0x18000c541  mov     rcx, [rcx+10h]
0x18000c545  call    WPP_SF_
0x18000c54a  xor     ebx, ebx
0x18000c54c  lea     rcx, [rsp+1B0h+var_150]; this
0x18000c551  call    ??1PackageInfo@@QEAA@XZ; PackageInfo::~PackageInfo(void)
0x18000c556  mov     eax, ebx
0x18000c558  mov     rcx, [rbp+0B0h+var_20]
0x18000c55f  xor     rcx, rsp; StackCookie
0x18000c562  call    __security_check_cookie
0x18000c567  lea     r11, [rsp+1B0h+var_10]
0x18000c56f  mov     rbx, [r11+20h]
0x18000c573  mov     rsi, [r11+30h]
0x18000c577  mov     rsp, r11
0x18000c57a  pop     r14
0x18000c57c  pop     rdi
0x18000c57d  pop     rbp
0x18000c57e  retn
```
