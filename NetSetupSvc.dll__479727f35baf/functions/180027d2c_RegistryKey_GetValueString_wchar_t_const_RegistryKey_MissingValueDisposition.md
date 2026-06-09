# RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)

- ea: `0x180027d2c`
- end: `0x180027eee`
- name: `?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z`
- size: `450`
- prototype: `__int64 __fastcall(HKEY *, __int64, const WCHAR *, int)`
- caller_count: `12`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180009cfc`
- `0x18001d9c0`
- `0x18001e828`
- `0x18001eb14`
- `0x18001f2e4`
- `0x18001f984`
- `0x18001fe58`
- `0x1800207bc`
- `0x1800209dc`
- `0x180021580`
- `0x180021650`
- `0x1800275e4`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078d0`
- `0x180008854`
- `0x18000d974`
- `0x180017558`
- `0x180018490`
- `0x180024930`
- `0x18002729c`
- `0x180027d2c`
- `0x180028894`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RegistryKey::GetValueString(HKEY *a1, __int64 a2, const WCHAR *a3, int a4)
{
  int v5; // esi
  _DWORD v8[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+110h] [rbp+10h] BYREF
  __int64 v11; // [rsp+118h] [rbp+18h]

  v5 = (int)a3;
  v8[1] = HIDWORD(a2);
  v8[0] = 0;
  RegistryKey::GetValueBlob(a1, &v10, a3, v8, a4);
  if ( v10 == v11 && !v8[0] )
  {
    if ( a4 != 1 )
    {
LABEL_6:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_SDP(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)&WPP_GLOBAL_Control,
          (_DWORD)WPP_GLOBAL_Control,
          v5,
          v8[0],
          v11 - v10);
      HResultException::HResultException((HResultException *)pExceptionObject, -2147023267);
      throw (HResultException *)pExceptionObject;
    }
LABEL_11:
    std::wstring::wstring(a2);
    goto LABEL_23;
  }
  if ( v8[0] != 1 )
    goto LABEL_6;
  if ( v10 == v11 )
    goto LABEL_11;
  if ( (((_BYTE)v11 - (_BYTE)v10) & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids, v11 - v10);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024883);
    throw (HResultException *)pExceptionObject;
  }
  if ( *(_BYTE *)(v11 - 1) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024883);
    throw (HResultException *)pExceptionObject;
  }
  std::wstring::wstring(a2, v10);
LABEL_23:
  std::vector<unsigned char>::_Tidy((__int64)&v10);
  return a2;
}

```

## disassembly

```asm
0x180027d2c  mov     [rsp-8+arg_18], rbx
0x180027d31  push    rbp
0x180027d32  push    rsi
0x180027d33  push    rdi
0x180027d34  lea     rbp, [rsp-30h]
0x180027d39  sub     rsp, 130h
0x180027d40  mov     rax, cs:__security_cookie
0x180027d47  xor     rax, rsp
0x180027d4a  mov     [rbp+40h+var_18], rax
0x180027d4e  mov     edi, r9d
0x180027d51  mov     rsi, r8
0x180027d54  mov     rbx, rdx
0x180027d57  mov     [rsp+140h+var_110], rdx
0x180027d5c  mov     dword ptr [rsp+140h+var_110], 0
0x180027d64  mov     [rsp+140h+var_120], r9d
0x180027d69  lea     r9, [rsp+140h+var_110]
0x180027d6e  lea     rdx, [rbp+40h+var_30]
0x180027d72  call    ?GetValueBlob@RegistryKey@@QEBA?AV?$vector@EV?$allocator@E@std@@@std@@PEB_WPEAKW4MissingValueDisposition@1@@Z; RegistryKey::GetValueBlob(wchar_t const *,ulong *,RegistryKey::MissingValueDisposition)
0x180027d77  nop
0x180027d78  mov     rax, [rbp+40h+var_28]
0x180027d7c  mov     rcx, [rbp+40h+var_30]
0x180027d80  mov     r9d, dword ptr [rsp+140h+var_110]
0x180027d85  cmp     rcx, rax
0x180027d88  jnz     short loc_180027D96
0x180027d8a  test    r9d, r9d
0x180027d8d  jnz     short loc_180027D96
0x180027d8f  cmp     edi, 1
0x180027d92  jz      short loc_180027DF5
0x180027d94  jmp     short loc_180027D9C
0x180027d96  cmp     r9d, 1
0x180027d9a  jz      short loc_180027DF0
0x180027d9c  lea     rdx, WPP_GLOBAL_Control
0x180027da3  mov     r8, cs:WPP_GLOBAL_Control
0x180027daa  cmp     r8, rdx
0x180027dad  jz      short loc_180027DCF
0x180027daf  cmp     byte ptr [r8+19h], 2
0x180027db4  jb      short loc_180027DCF
0x180027db6  sub     rax, rcx
0x180027db9  mov     [rsp+140h+var_118], rax
0x180027dbe  mov     [rsp+140h+var_120], r9d
0x180027dc3  mov     r9, rsi
0x180027dc6  mov     rcx, [r8+10h]
0x180027dca  call    WPP_SF_SDP
0x180027dcf  mov     edx, 8007065Dh; int
0x180027dd4  lea     rcx, [rsp+140h+pExceptionObject]; this
0x180027dd9  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180027dde  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180027de5  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x180027dea  call    _CxxThrowException_0
0x180027df0  cmp     rcx, rax
0x180027df3  jnz     short loc_180027E02
0x180027df5  mov     rcx, rbx
0x180027df8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180027dfd  jmp     loc_180027EC3
0x180027e02  sub     rax, rcx
0x180027e05  test    al, 1
0x180027e07  jz      short loc_180027E5B
0x180027e09  lea     rdx, WPP_GLOBAL_Control
0x180027e10  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e17  cmp     rcx, rdx
0x180027e1a  jz      short loc_180027E3A
0x180027e1c  cmp     byte ptr [rcx+19h], 2
0x180027e20  jb      short loc_180027E3A
0x180027e22  mov     edx, 1Eh
0x180027e27  mov     r9, rax
0x180027e2a  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x180027e31  mov     rcx, [rcx+10h]
0x180027e35  call    WPP_SF_P
0x180027e3a  mov     edx, 8007000Dh; int
0x180027e3f  lea     rcx, [rsp+140h+pExceptionObject]; this
0x180027e44  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180027e49  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180027e50  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x180027e55  call    _CxxThrowException_0
0x180027e5b  lea     r8, [rcx-1]
0x180027e5f  add     r8, rax
0x180027e62  cmp     byte ptr [r8], 0
0x180027e66  jz      short loc_180027EB7
0x180027e68  lea     rdx, WPP_GLOBAL_Control
0x180027e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e76  cmp     rcx, rdx
0x180027e79  jz      short loc_180027E96
0x180027e7b  cmp     byte ptr [rcx+19h], 2
0x180027e7f  jb      short loc_180027E96
0x180027e81  mov     edx, 1Fh
0x180027e86  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x180027e8d  mov     rcx, [rcx+10h]
0x180027e91  call    WPP_SF_
0x180027e96  mov     edx, 8007000Dh; int
0x180027e9b  lea     rcx, [rsp+140h+pExceptionObject]; this
0x180027ea0  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180027ea5  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180027eac  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x180027eb1  call    _CxxThrowException_0
0x180027eb7  mov     rdx, rcx
0x180027eba  mov     rcx, rbx
0x180027ebd  call    ??$?0PEB_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t const *,wchar_t const *,std::allocator<wchar_t> const &)
0x180027ec2  nop
0x180027ec3  lea     rcx, [rbp+40h+var_30]
0x180027ec7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180027ecc  mov     rax, rbx
0x180027ecf  mov     rcx, [rbp+40h+var_18]
0x180027ed3  xor     rcx, rsp; StackCookie
0x180027ed6  call    __security_check_cookie
0x180027edb  mov     rbx, [rsp+140h+arg_18]
0x180027ee3  add     rsp, 130h
0x180027eea  pop     rdi
0x180027eeb  pop     rsi
0x180027eec  pop     rbp
0x180027eed  retn
```
