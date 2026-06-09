# _anonymous_namespace_::GetFullNameAndPath

- ea: `0x18004b938`
- end: `0x18004bc4e`
- name: `_anonymous_namespace_::GetFullNameAndPath`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18004bc88`

## callees

- `0x180006ee0`
- `0x180008d50`
- `0x18000947c`
- `0x18000ecc0`
- `0x180035e0c`
- `0x18004b938`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ba5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ba9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ba5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ba9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ba07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ba16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ba07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ba16`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall anonymous_namespace_::GetFullNameAndPath(__int64 a1, __int64 a2)
{
  int v4; // eax
  int v5; // edi
  int v6; // eax
  int v7; // edi
  int v8; // eax
  int v9; // edi
  int v10; // eax
  int v11; // edi
  int v12; // eax
  int v13; // edi
  PCWSTR StringRawBuffer; // rdi
  PCWSTR v15; // rax
  unsigned __int64 v16; // r8
  __int64 v17; // rcx
  __int64 (__fastcall ***v18)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v19; // rcx
  HSTRING string; // [rsp+28h] [rbp-38h] BYREF
  HSTRING v22; // [rsp+30h] [rbp-30h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v24; // [rsp+98h] [rbp+38h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // [rsp+A0h] [rbp+40h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+48h] BYREF

  v26 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 48LL))(a2, &v26);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        12,
        WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
        (unsigned int)v4);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v5);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v22 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 96LL))(v26, &v22);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        13,
        WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
        (unsigned int)v6);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v7);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v25 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a2 + 56LL))(
         a2,
         &v25);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        14,
        WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
        (unsigned int)v8);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v9);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v24 = 0;
  v10 = (**v25)(v25, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v24);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        15,
        WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
        (unsigned int)v10);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v11);
    throw (ErrorCodeException *)pExceptionObject;
  }
  string = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 96LL))(v24, &string);
  v13 = v12;
  if ( v12 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        16,
        WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
        (unsigned int)v12);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v13);
    throw (ErrorCodeException *)pExceptionObject;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v15 = WindowsGetStringRawBuffer(v22, 0);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v16 = -1;
  do
    ++v16;
  while ( v15[v16] );
  std::wstring::_Construct<1,unsigned short const *>((char **)a1, v15, v16);
  std::wstring::wstring(a1 + 32, StringRawBuffer);
  if ( string )
    WindowsDeleteString(string);
  v17 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = v25;
  if ( v25 )
  {
    v25 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v18)[2])(v18);
  }
  if ( v22 )
    WindowsDeleteString(v22);
  v19 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return a1;
}

```

## disassembly

```asm
0x18004b938  mov     [rsp-28h+arg_0], rcx
0x18004b93d  push    rbp
0x18004b93e  push    rbx
0x18004b93f  push    rsi
0x18004b940  push    rdi
0x18004b941  push    r14
0x18004b943  mov     rbp, rsp
0x18004b946  sub     rsp, 60h
0x18004b94a  mov     rsi, rdx
0x18004b94d  mov     rbx, rcx
0x18004b950  xor     r14d, r14d
0x18004b953  mov     [rbp+arg_18], r14
0x18004b957  mov     rax, [rdx]
0x18004b95a  lea     rdx, [rbp+arg_18]
0x18004b95e  mov     rcx, rsi
0x18004b961  mov     rax, [rax+30h]
0x18004b965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b96a  mov     edi, eax
0x18004b96c  test    eax, eax
0x18004b96e  js      loc_18004BB1A
0x18004b974  mov     [rbp+var_30], r14
0x18004b978  mov     rcx, [rbp+arg_18]
0x18004b97c  mov     rax, [rcx]
0x18004b97f  lea     rdx, [rbp+var_30]
0x18004b983  mov     rax, [rax+60h]
0x18004b987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b98c  mov     edi, eax
0x18004b98e  test    eax, eax
0x18004b990  js      loc_18004BB67
0x18004b996  mov     [rbp+arg_10], r14
0x18004b99a  mov     rax, [rsi]
0x18004b99d  lea     rdx, [rbp+arg_10]
0x18004b9a1  mov     rcx, rsi
0x18004b9a4  mov     rax, [rax+38h]
0x18004b9a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9ad  mov     edi, eax
0x18004b9af  test    eax, eax
0x18004b9b1  js      loc_18004BBB4
0x18004b9b7  mov     [rbp+arg_8], r14
0x18004b9bb  mov     rcx, [rbp+arg_10]
0x18004b9bf  mov     rax, [rcx]
0x18004b9c2  lea     r8, [rbp+arg_8]
0x18004b9c6  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x18004b9cd  mov     rax, [rax]
0x18004b9d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9d5  mov     edi, eax
0x18004b9d7  test    eax, eax
0x18004b9d9  js      loc_18004BC01
0x18004b9df  mov     [rbp+string], r14
0x18004b9e3  mov     rcx, [rbp+arg_8]
0x18004b9e7  mov     rax, [rcx]
0x18004b9ea  lea     rdx, [rbp+string]
0x18004b9ee  mov     rax, [rax+60h]
0x18004b9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9f7  mov     edi, eax
0x18004b9f9  test    eax, eax
0x18004b9fb  js      loc_18004BACD
0x18004ba01  xor     edx, edx; length
0x18004ba03  mov     rcx, [rbp+string]; string
0x18004ba07  call    cs:__imp_WindowsGetStringRawBuffer
0x18004ba0d  mov     rdi, rax
0x18004ba10  xor     edx, edx; length
0x18004ba12  mov     rcx, [rbp+var_30]; string
0x18004ba16  call    cs:__imp_WindowsGetStringRawBuffer
0x18004ba1c  xorps   xmm0, xmm0
0x18004ba1f  movups  xmmword ptr [rbx], xmm0
0x18004ba22  mov     [rbx+10h], r14
0x18004ba26  mov     [rbx+18h], r14
0x18004ba2a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004ba2e  inc     r8
0x18004ba31  cmp     [rax+r8*2], r14w
0x18004ba36  jnz     short loc_18004BA2E
0x18004ba38  mov     rdx, rax
0x18004ba3b  mov     rcx, rbx
0x18004ba3e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004ba43  nop
0x18004ba44  lea     rcx, [rbx+20h]
0x18004ba48  mov     rdx, rdi
0x18004ba4b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004ba50  nop
0x18004ba51  mov     rcx, [rbp+string]; string
0x18004ba55  test    rcx, rcx
0x18004ba58  jz      short loc_18004BA61
0x18004ba5a  call    cs:__imp_WindowsDeleteString
0x18004ba60  nop
0x18004ba61  mov     rcx, [rbp+arg_8]
0x18004ba65  test    rcx, rcx
0x18004ba68  jz      short loc_18004BA7B
0x18004ba6a  mov     [rbp+arg_8], r14
0x18004ba6e  mov     rax, [rcx]
0x18004ba71  mov     rax, [rax+10h]
0x18004ba75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba7a  nop
0x18004ba7b  mov     rcx, [rbp+arg_10]
0x18004ba7f  test    rcx, rcx
0x18004ba82  jz      short loc_18004BA95
0x18004ba84  mov     [rbp+arg_10], r14
0x18004ba88  mov     rax, [rcx]
0x18004ba8b  mov     rax, [rax+10h]
0x18004ba8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba94  nop
0x18004ba95  mov     rcx, [rbp+var_30]; string
0x18004ba99  test    rcx, rcx
0x18004ba9c  jz      short loc_18004BAA5
0x18004ba9e  call    cs:__imp_WindowsDeleteString
0x18004baa4  nop
0x18004baa5  mov     rcx, [rbp+arg_18]
0x18004baa9  test    rcx, rcx
0x18004baac  jz      short loc_18004BABF
0x18004baae  mov     [rbp+arg_18], r14
0x18004bab2  mov     rax, [rcx]
0x18004bab5  mov     rax, [rax+10h]
0x18004bab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004babe  nop
0x18004babf  mov     rax, rbx
0x18004bac2  add     rsp, 60h
0x18004bac6  pop     r14
0x18004bac8  pop     rdi
0x18004bac9  pop     rsi
0x18004baca  pop     rbx
0x18004bacb  pop     rbp
0x18004bacc  retn
0x18004bacd  lea     rdx, WPP_GLOBAL_Control
0x18004bad4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004badb  cmp     rcx, rdx
0x18004bade  jz      short loc_18004BAFE
0x18004bae0  test    byte ptr [rcx+1Ch], 1
0x18004bae4  jz      short loc_18004BAFE
0x18004bae6  mov     edx, 10h
0x18004baeb  mov     r9d, edi
0x18004baee  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x18004baf5  mov     rcx, [rcx+10h]
0x18004baf9  call    WPP_SF_d
0x18004bafe  mov     edx, edi; int
0x18004bb00  lea     rcx, [rbp+pExceptionObject]; this
0x18004bb04  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18004bb09  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18004bb10  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004bb14  call    _CxxThrowException_0
0x18004bb1a  lea     rdx, WPP_GLOBAL_Control
0x18004bb21  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb28  cmp     rcx, rdx
0x18004bb2b  jz      short loc_18004BB4B
0x18004bb2d  test    byte ptr [rcx+1Ch], 1
0x18004bb31  jz      short loc_18004BB4B
0x18004bb33  mov     edx, 0Ch
0x18004bb38  mov     r9d, edi
0x18004bb3b  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x18004bb42  mov     rcx, [rcx+10h]
0x18004bb46  call    WPP_SF_d
0x18004bb4b  mov     edx, edi; int
0x18004bb4d  lea     rcx, [rbp+pExceptionObject]; this
0x18004bb51  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18004bb56  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18004bb5d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004bb61  call    _CxxThrowException_0
0x18004bb67  lea     rdx, WPP_GLOBAL_Control
0x18004bb6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb75  cmp     rcx, rdx
0x18004bb78  jz      short loc_18004BB98
0x18004bb7a  test    byte ptr [rcx+1Ch], 1
0x18004bb7e  jz      short loc_18004BB98
0x18004bb80  mov     edx, 0Dh
0x18004bb85  mov     r9d, edi
0x18004bb88  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x18004bb8f  mov     rcx, [rcx+10h]
0x18004bb93  call    WPP_SF_d
0x18004bb98  mov     edx, edi; int
0x18004bb9a  lea     rcx, [rbp+pExceptionObject]; this
0x18004bb9e  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18004bba3  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18004bbaa  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004bbae  call    _CxxThrowException_0
0x18004bbb4  lea     rdx, WPP_GLOBAL_Control
0x18004bbbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bbc2  cmp     rcx, rdx
0x18004bbc5  jz      short loc_18004BBE5
0x18004bbc7  test    byte ptr [rcx+1Ch], 1
0x18004bbcb  jz      short loc_18004BBE5
0x18004bbcd  mov     edx, 0Eh
0x18004bbd2  mov     r9d, edi
0x18004bbd5  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x18004bbdc  mov     rcx, [rcx+10h]
0x18004bbe0  call    WPP_SF_d
0x18004bbe5  mov     edx, edi; int
0x18004bbe7  lea     rcx, [rbp+pExceptionObject]; this
0x18004bbeb  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18004bbf0  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18004bbf7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004bbfb  call    _CxxThrowException_0
0x18004bc01  lea     rdx, WPP_GLOBAL_Control
0x18004bc08  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bc0f  cmp     rcx, rdx
0x18004bc12  jz      short loc_18004BC32
0x18004bc14  test    byte ptr [rcx+1Ch], 1
0x18004bc18  jz      short loc_18004BC32
0x18004bc1a  mov     edx, 0Fh
0x18004bc1f  mov     r9d, edi
0x18004bc22  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x18004bc29  mov     rcx, [rcx+10h]
0x18004bc2d  call    WPP_SF_d
0x18004bc32  mov     edx, edi; int
0x18004bc34  lea     rcx, [rbp+pExceptionObject]; this
0x18004bc38  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18004bc3d  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18004bc44  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004bc48  call    _CxxThrowException_0
```
