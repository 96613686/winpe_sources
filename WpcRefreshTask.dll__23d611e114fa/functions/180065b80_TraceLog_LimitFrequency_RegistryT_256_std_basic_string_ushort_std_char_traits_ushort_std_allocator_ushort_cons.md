# TraceLog::LimitFrequency(RegistryT<256> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,TimeSpan const &,std::function<void (void)> const &)

- ea: `0x180065b80`
- end: `0x180065e5c`
- name: `?LimitFrequency@TraceLog@@YAXAEAV?$RegistryT@$0BAA@@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVTimeSpan@@AEBV?$function@$$A6AXXZ@4@@Z`
- size: `732`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028950`
- `0x180071e94`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x180008d50`
- `0x180009a80`
- `0x180035e0c`
- `0x18003ee0c`
- `0x180040888`
- `0x1800409b4`
- `0x1800654fc`
- `0x180065618`
- `0x180065b80`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180065bcb`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180065d70`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180065bcb`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180065d70`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180065d19`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180065d45`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180065d19`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180065d45`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
LONG __fastcall TraceLog::LimitFrequency(
        __int64 (__fastcall ***a1)(_QWORD, __int64 *, _OWORD *),
        __int64 a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 v8; // rcx
  LONG result; // eax
  __int64 (__fastcall *v10)(_QWORD, __int64 *, _OWORD *); // rbx
  _QWORD *v11; // rax
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  char v13; // bl
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 (__fastcall ***v16)(_QWORD, __int64); // rcx
  __int64 v17; // rcx
  const FILETIME *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdi
  void (__fastcall *v22)(__int64, _BYTE *); // rbx
  __int64 (__fastcall ***v23)(_QWORD, __int64); // rcx
  __int64 (__fastcall ***v24)(_QWORD, __int64); // rcx
  __int64 v25; // [rsp+20h] [rbp-99h] BYREF
  _QWORD v26[2]; // [rsp+28h] [rbp-91h] BYREF
  FILETIME FileTime2; // [rsp+38h] [rbp-81h] BYREF
  __int64 v28; // [rsp+48h] [rbp-71h] BYREF
  __int64 v29; // [rsp+50h] [rbp-69h] BYREF
  _BYTE v30[16]; // [rsp+58h] [rbp-61h] BYREF
  FILETIME *lpFileTime1; // [rsp+68h] [rbp-51h]
  _OWORD pExceptionObject[2]; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v33[40]; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v34; // [rsp+C8h] [rbp+Fh]

  v25 = a2;
  if ( (unsigned __int8)lambda_970c1268d4d3e21c45305266ae53b436_::operator()(&v25) )
  {
    v8 = *(_QWORD *)(a4 + 56);
    if ( !v8 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  else
  {
    v10 = **a1;
    memset(pExceptionObject, 0, sizeof(pExceptionObject));
    std::wstring::_Construct<1,unsigned short const *>(pExceptionObject, L"Squelch", 7);
    v11 = (_QWORD *)v10(a1, &v28, pExceptionObject);
    (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v11 + 48LL))(*v11, &v25);
    if ( v28 )
    {
      v12 = (void (__fastcall ***)(_QWORD, __int64))(v28 + *(int *)(*(_QWORD *)(v28 + 8) + 4LL) + 8LL);
      (**v12)(v12, 1);
    }
    std::wstring::~wstring(pExceptionObject);
    v13 = 1;
    DateTime::GetCurrent(&FileTime2);
    v14 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64))v25)(v25, &v29, a2);
    v15 = *(_QWORD *)v14 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v14 + 8LL) + 4LL);
    result = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v15 + 40LL))(v15, v33);
    if ( v29 )
    {
      v16 = (__int64 (__fastcall ***)(_QWORD, __int64))(v29 + *(int *)(*(_QWORD *)(v29 + 8) + 4LL) + 8LL);
      result = (**v16)(v16, 1);
    }
    v17 = v34;
    if ( v34 )
    {
      v26[0] = v33;
      result = stdext::try_execute__lambda_6d459bc6bb4e76a2d403c7867349fa72___(v30, v26);
      if ( lpFileTime1 )
      {
        result = TimeSpan::Zero;
        if ( *a3 >= TimeSpan::Zero && *a3 <= TimeSpan::Zero )
          goto LABEL_16;
        result = CompareFileTime(lpFileTime1, &FileTime2);
        if ( result < 0 )
        {
          if ( !lpFileTime1 )
          {
            ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
            throw (ErrorCodeException *)pExceptionObject;
          }
          v18 = (const FILETIME *)DateTime::operator+(lpFileTime1, v26, a3);
          result = CompareFileTime(v18, &FileTime2);
          if ( result > 0 )
LABEL_16:
            v13 = 0;
        }
      }
      v17 = v34;
    }
    if ( v17 )
      result = std::wstring::~wstring(v17);
    if ( v13 )
    {
      v19 = *(_QWORD *)(a4 + 56);
      if ( !v19 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v20 = (**(__int64 (__fastcall ***)(__int64, _QWORD *, __int64))v25)(v25, v26, a2);
      v21 = *(_QWORD *)v20;
      v22 = *(void (__fastcall **)(__int64, _BYTE *))(**(_QWORD **)v20 + 32LL);
      DateTime::ToDebugString(&FileTime2, v30, 0);
      v22(v21, v30);
      result = std::wstring::~wstring(v30);
      if ( v26[0] )
      {
        v23 = (__int64 (__fastcall ***)(_QWORD, __int64))(v26[0] + *(int *)(*(_QWORD *)(v26[0] + 8LL) + 4LL) + 8LL);
        result = (**v23)(v23, 1);
      }
    }
    if ( v25 )
    {
      v24 = (__int64 (__fastcall ***)(_QWORD, __int64))(v25 + 8 + *(int *)(*(_QWORD *)(v25 + 8) + 4LL));
      return (**v24)(v24, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180065b80  push    rbp
0x180065b82  push    rbx
0x180065b83  push    rsi
0x180065b84  push    rdi
0x180065b85  push    r14
0x180065b87  push    r15
0x180065b89  lea     rbp, [rsp-2Fh]
0x180065b8e  sub     rsp, 0E8h
0x180065b95  mov     rax, cs:__security_cookie
0x180065b9c  xor     rax, rsp
0x180065b9f  mov     [rbp+57h+var_40], rax
0x180065ba3  mov     rdi, r9
0x180065ba6  mov     rsi, r8
0x180065ba9  mov     r15, rdx
0x180065bac  mov     r14, rcx
0x180065baf  mov     [rsp+110h+var_F0], rdx
0x180065bb4  lea     rcx, [rsp+110h+var_F0]
0x180065bb9  call    _lambda_970c1268d4d3e21c45305266ae53b436___operator__
0x180065bbe  test    al, al
0x180065bc0  jz      short loc_180065BE3
0x180065bc2  mov     rcx, [rdi+38h]
0x180065bc6  test    rcx, rcx
0x180065bc9  jnz     short loc_180065BD2
0x180065bcb  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180065bd1  int     3; Trap to Debugger
0x180065bd2  mov     rax, [rcx]
0x180065bd5  mov     rax, [rax+10h]
0x180065bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065bde  jmp     loc_180065E21
0x180065be3  mov     rax, [r14]
0x180065be6  mov     rbx, [rax]
0x180065be9  xorps   xmm0, xmm0
0x180065bec  movups  [rbp+57h+pExceptionObject], xmm0
0x180065bf0  xorps   xmm1, xmm1
0x180065bf3  movdqu  [rbp+57h+var_88], xmm1
0x180065bf8  mov     r8d, 7
0x180065bfe  lea     rdx, aSquelch; "Squelch"
0x180065c05  lea     rcx, [rbp+57h+pExceptionObject]
0x180065c09  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180065c0e  nop
0x180065c0f  lea     r8, [rbp+57h+pExceptionObject]
0x180065c13  lea     rdx, [rbp+57h+var_C8]
0x180065c17  mov     rcx, r14
0x180065c1a  mov     rax, rbx
0x180065c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c22  nop
0x180065c23  mov     rcx, [rax]
0x180065c26  mov     rax, [rcx]
0x180065c29  lea     rdx, [rsp+110h+var_F0]
0x180065c2e  mov     rax, [rax+30h]
0x180065c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c37  nop
0x180065c38  mov     r14d, 1
0x180065c3e  mov     rdx, [rbp+57h+var_C8]
0x180065c42  test    rdx, rdx
0x180065c45  jz      short loc_180065C65
0x180065c47  mov     rax, [rdx+8]
0x180065c4b  movsxd  rcx, dword ptr [rax+4]
0x180065c4f  add     rcx, 8
0x180065c53  add     rcx, rdx
0x180065c56  mov     rax, [rcx]
0x180065c59  mov     edx, r14d
0x180065c5c  mov     rax, [rax]
0x180065c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c64  nop
0x180065c65  lea     rcx, [rbp+57h+pExceptionObject]
0x180065c69  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180065c6e  mov     bl, r14b
0x180065c71  lea     rcx, [rsp+110h+FileTime2]
0x180065c76  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x180065c7b  mov     rcx, [rsp+110h+var_F0]
0x180065c80  mov     rax, [rcx]
0x180065c83  mov     r8, r15
0x180065c86  lea     rdx, [rbp+57h+var_C0]
0x180065c8a  mov     rax, [rax]
0x180065c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c92  nop
0x180065c93  mov     rdx, [rax]
0x180065c96  mov     rax, [rdx+8]
0x180065c9a  movsxd  rcx, dword ptr [rax+4]
0x180065c9e  add     rdx, 8
0x180065ca2  add     rcx, rdx
0x180065ca5  mov     rax, [rcx]
0x180065ca8  lea     rdx, [rbp+57h+var_70]
0x180065cac  mov     rax, [rax+28h]
0x180065cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065cb5  nop
0x180065cb6  mov     rdx, [rbp+57h+var_C0]
0x180065cba  test    rdx, rdx
0x180065cbd  jz      short loc_180065CDC
0x180065cbf  mov     rax, [rdx+8]
0x180065cc3  movsxd  rcx, dword ptr [rax+4]
0x180065cc7  add     rcx, 8
0x180065ccb  add     rcx, rdx
0x180065cce  mov     rax, [rcx]
0x180065cd1  mov     edx, r14d
0x180065cd4  mov     rax, [rax]
0x180065cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065cdc  mov     rcx, [rbp+57h+var_48]
0x180065ce0  test    rcx, rcx
0x180065ce3  jz      short loc_180065D55
0x180065ce5  lea     rax, [rbp+57h+var_70]
0x180065ce9  mov     [rsp+110h+var_E8], rax
0x180065cee  lea     rdx, [rsp+110h+var_E8]
0x180065cf3  lea     rcx, [rbp+57h+var_B8]
0x180065cf7  call    stdext__try_execute__lambda_6d459bc6bb4e76a2d403c7867349fa72___
0x180065cfc  nop
0x180065cfd  mov     rcx, [rbp+57h+lpFileTime1]; lpFileTime1
0x180065d01  test    rcx, rcx
0x180065d04  jz      short loc_180065D51
0x180065d06  mov     rax, cs:?Zero@TimeSpan@@2V1@B; TimeSpan const TimeSpan::Zero
0x180065d0d  cmp     [rsi], rax
0x180065d10  jb      short loc_180065D14
0x180065d12  jbe     short loc_180065D4F
0x180065d14  lea     rdx, [rsp+110h+FileTime2]; lpFileTime2
0x180065d19  call    cs:__imp_CompareFileTime
0x180065d1f  test    eax, eax
0x180065d21  jns     short loc_180065D51
0x180065d23  mov     rcx, [rbp+57h+lpFileTime1]
0x180065d27  test    rcx, rcx
0x180065d2a  jz      loc_180065E3D
0x180065d30  mov     r8, rsi
0x180065d33  lea     rdx, [rsp+110h+var_E8]
0x180065d38  call    ??HDateTime@@QEBA?AV0@AEBVTimeSpan@@@Z; DateTime::operator+(TimeSpan const &)
0x180065d3d  lea     rdx, [rsp+110h+FileTime2]; lpFileTime2
0x180065d42  mov     rcx, rax; lpFileTime1
0x180065d45  call    cs:__imp_CompareFileTime
0x180065d4b  test    eax, eax
0x180065d4d  jle     short loc_180065D51
0x180065d4f  xor     bl, bl
0x180065d51  mov     rcx, [rbp+57h+var_48]
0x180065d55  test    rcx, rcx
0x180065d58  jz      short loc_180065D5F
0x180065d5a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180065d5f  test    bl, bl
0x180065d61  jz      loc_180065DFA
0x180065d67  mov     rcx, [rdi+38h]
0x180065d6b  test    rcx, rcx
0x180065d6e  jnz     short loc_180065D77
0x180065d70  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180065d76  int     3; Trap to Debugger
0x180065d77  mov     rax, [rcx]
0x180065d7a  mov     rax, [rax+10h]
0x180065d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d83  mov     rcx, [rsp+110h+var_F0]
0x180065d88  mov     rax, [rcx]
0x180065d8b  mov     r8, r15
0x180065d8e  lea     rdx, [rsp+110h+var_E8]
0x180065d93  mov     rax, [rax]
0x180065d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d9b  nop
0x180065d9c  mov     rdi, [rax]
0x180065d9f  mov     rax, [rdi]
0x180065da2  mov     rbx, [rax+20h]
0x180065da6  xor     r8d, r8d
0x180065da9  lea     rdx, [rbp+57h+var_B8]
0x180065dad  lea     rcx, [rsp+110h+FileTime2]
0x180065db2  call    ?ToDebugString@DateTime@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4TimeType@@@Z; DateTime::ToDebugString(TimeType)
0x180065db7  nop
0x180065db8  lea     rdx, [rbp+57h+var_B8]
0x180065dbc  mov     rcx, rdi
0x180065dbf  mov     rax, rbx
0x180065dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065dc7  nop
0x180065dc8  lea     rcx, [rbp+57h+var_B8]
0x180065dcc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180065dd1  nop
0x180065dd2  mov     rdx, [rsp+110h+var_E8]
0x180065dd7  test    rdx, rdx
0x180065dda  jz      short loc_180065DFA
0x180065ddc  mov     rax, [rdx+8]
0x180065de0  movsxd  rcx, dword ptr [rax+4]
0x180065de4  add     rcx, 8
0x180065de8  add     rcx, rdx
0x180065deb  mov     rax, [rcx]
0x180065dee  mov     edx, r14d
0x180065df1  mov     rax, [rax]
0x180065df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065df9  nop
0x180065dfa  mov     r8, [rsp+110h+var_F0]
0x180065dff  test    r8, r8
0x180065e02  jz      short loc_180065E21
0x180065e04  mov     rax, [r8+8]
0x180065e08  movsxd  rcx, dword ptr [rax+4]
0x180065e0c  add     r8, 8
0x180065e10  add     rcx, r8
0x180065e13  mov     rax, [rcx]
0x180065e16  mov     edx, r14d
0x180065e19  mov     rax, [rax]
0x180065e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e21  mov     rcx, [rbp+57h+var_40]
0x180065e25  xor     rcx, rsp; StackCookie
0x180065e28  call    __security_check_cookie
0x180065e2d  add     rsp, 0E8h
0x180065e34  pop     r15
0x180065e36  pop     r14
0x180065e38  pop     rdi
0x180065e39  pop     rsi
0x180065e3a  pop     rbx
0x180065e3b  pop     rbp
0x180065e3c  retn
0x180065e3d  mov     edx, 80004003h; int
0x180065e42  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180065e46  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180065e4b  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180065e52  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180065e56  call    _CxxThrowException_0
```
