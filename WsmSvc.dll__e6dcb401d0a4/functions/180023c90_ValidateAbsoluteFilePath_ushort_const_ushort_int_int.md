# ValidateAbsoluteFilePath(ushort const *,ushort * *,int,int)

- ea: `0x180023c90`
- end: `0x180024121`
- name: `?ValidateAbsoluteFilePath@@YAHPEBGPEAPEAGHH@Z`
- size: `1169`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, unsigned __int16 **, int, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180023920`
- `0x18019bb08`

## callees

- `0x180005d10`
- `0x180008920`
- `0x180023c90`
- `0x18004a900`
- `0x180071400`
- `0x1800973c0`
- `0x1800c9928`
- `0x18011a6d4`
- `0x18019f980`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180023ddd`
- `msvcrt!_wcsicmp` at `0x180023ddd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023dec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023edb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023f3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023f9c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800240b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023dec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023edb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023f3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023f9c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800240b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002402f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002402f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023e95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023e95`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023d3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023d9e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023d3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023d9e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180023cfa`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180023d5c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180023cfa`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180023d5c`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180023dc4`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180023dc4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023e56`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024089`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023e56`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024089`

## string_xrefs

- `0x180023f86`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x180023fbb`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x180023f61`: `onecore\admin\wmi\wmx\config\configutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ValidateAbsoluteFilePath(LPCWSTR lpSrc, unsigned __int16 **a2, int a3, int a4)
{
  WCHAR *v6; // r14
  __int64 v7; // rax
  DWORD v8; // eax
  CHeap *v9; // rcx
  DWORD v10; // edi
  SIZE_T v11; // rsi
  CHeap *v12; // rcx
  void *Handle; // rax
  CHeap *v14; // rcx
  SIZE_T v15; // rbx
  CHeap *v16; // rcx
  void *v17; // rax
  WCHAR *v18; // rbx
  DWORD FullPathNameW; // ecx
  int v20; // edi
  unsigned __int16 *v21; // rsi
  const WCHAR *v22; // rcx
  HANDLE FileW; // rax
  void *v24; // rdi
  int v26; // eax
  DWORD v27; // ecx
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  int v31; // eax
  DWORD LastError; // eax
  unsigned int v33; // edi
  HANDLE v34; // rax
  DWORD v35; // ecx
  unsigned __int16 *v36; // [rsp+40h] [rbp-20h] BYREF
  WCHAR *v37; // [rsp+48h] [rbp-18h] BYREF
  HANDLE v38; // [rsp+50h] [rbp-10h] BYREF
  LPWSTR FilePart; // [rsp+58h] [rbp-8h] BYREF
  WCHAR *v40; // [rsp+A0h] [rbp+40h] BYREF
  int v41; // [rsp+B0h] [rbp+50h]
  int v42; // [rsp+B8h] [rbp+58h]

  v42 = a4;
  v41 = a3;
  v6 = 0;
  if ( !lpSrc )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 1792, L"1792", 0x54Fu, 0);
    return 0;
  }
  v7 = -1;
  do
    ++v7;
  while ( lpSrc[v7] );
  if ( !v7 || *lpSrc == 32 || *lpSrc == 9 )
  {
    SetLastError(0x80338191);
    return 0;
  }
  v8 = ExpandEnvironmentStringsW(lpSrc, 0, 0);
  v10 = v8;
  if ( !v8 )
    return 0;
  v11 = 2LL * v8;
  if ( !is_mul_ok(v8, 2u) )
    v11 = -1;
  if ( CHeap::GetHandle(v9) )
  {
    Handle = CHeap::GetHandle(v12);
    v6 = (WCHAR *)HeapAlloc(Handle, 0, v11);
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
  }
  v40 = v6;
  if ( !v6 )
  {
    SetLastError(0xEu);
    goto LABEL_26;
  }
  if ( !ExpandEnvironmentStringsW(lpSrc, v6, v10) )
  {
LABEL_26:
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v40);
    return 0;
  }
  v15 = 2LL * v10;
  if ( !is_mul_ok(v10, 2u) )
    v15 = -1;
  if ( CHeap::GetHandle(v14) )
  {
    v17 = CHeap::GetHandle(v16);
    v18 = (WCHAR *)HeapAlloc(v17, 0, v15);
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
    v18 = 0;
  }
  v37 = v18;
  if ( !v18 )
  {
    v27 = 14;
    goto LABEL_45;
  }
  FilePart = 0;
  FullPathNameW = GetFullPathNameW(v6, v10, v18, &FilePart);
  if ( !FullPathNameW )
    goto LABEL_23;
  if ( FullPathNameW != v10 - 1 || _wcsicmp(v6, v18) )
  {
    SetLastError(0x80338191);
LABEL_23:
    if ( a2 )
    {
      *a2 = v6;
      v40 = 0;
    }
    goto LABEL_25;
  }
  if ( !v42 || (unsigned int)StrongPathValidate(v18, 37) )
  {
    v20 = v41;
  }
  else
  {
    v26 = StrongPathValidate(v18, 38);
    v20 = v41;
    if ( !v26 && (!v41 || !(unsigned int)StrongPathValidate(v18, 41) && !(unsigned int)StrongPathValidate(v18, 42)) )
    {
      v27 = -2144108143;
LABEL_45:
      SetLastError(v27);
LABEL_25:
      AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v37);
      goto LABEL_26;
    }
  }
  v21 = 0;
  v36 = 0;
  v22 = v18;
  if ( v20 )
  {
    v28 = StrongPathValidate(v18, 37);
    v22 = v18;
    if ( v28 )
    {
      v29 = 37;
      v30 = 41;
    }
    else
    {
      v31 = StrongPathValidate(v18, 38);
      v22 = v18;
      if ( !v31 )
        goto LABEL_30;
      v30 = 42;
      v29 = 38;
    }
    if ( !(unsigned int)RedirectPath(v22, v29, v30, &v36) )
    {
LABEL_73:
      v33 = 0;
      goto LABEL_74;
    }
    v21 = v36;
    v22 = v36;
  }
LABEL_30:
  FileW = CreateFileW(v22, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v24 = FileW;
  v38 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError == 32 )
    {
      AutoCleanup<AutoHandle,void *>::ReleasePtr(&v38);
      v33 = 1;
LABEL_74:
      AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v36);
      AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v37);
      AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v40);
      return v33;
    }
    if ( LastError - 2 <= 1 )
    {
      v35 = -2144108142;
      goto LABEL_66;
    }
    if ( LastError != 123 )
    {
      if ( LastError != 5 )
      {
        v35 = 1359;
        goto LABEL_66;
      }
      v34 = CreateFileW(v18, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
      AutoHandle::operator=(&v38, v34);
      if ( v38 == (HANDLE)-1LL )
      {
LABEL_67:
        if ( a2 )
        {
          if ( v21 )
          {
            v36 = 0;
          }
          else
          {
            v40 = 0;
            v21 = v6;
          }
          *a2 = v21;
        }
        AutoCleanup<AutoHandle,void *>::ReleasePtr(&v38);
        goto LABEL_73;
      }
    }
    v35 = -2144108143;
LABEL_66:
    SetLastError(v35);
    goto LABEL_67;
  }
  if ( FileW )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4bcfcb6bc4c53d70488bc6bf4d078fb8_Traceguids, FileW);
    CloseHandle(v24);
  }
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v36);
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v37);
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v40);
  return 1;
}

```

## disassembly

```asm
0x180023c90  mov     [rsp-38h+arg_8], rbx
0x180023c95  mov     [rsp-38h+arg_18], r9d
0x180023c9a  mov     [rsp-38h+arg_10], r8d
0x180023c9f  push    rbp
0x180023ca0  push    rsi
0x180023ca1  push    rdi
0x180023ca2  push    r12
0x180023ca4  push    r13
0x180023ca6  push    r14
0x180023ca8  push    r15
0x180023caa  mov     rbp, rsp
0x180023cad  sub     rsp, 60h
0x180023cb1  mov     r15, rdx
0x180023cb4  mov     rbx, rcx
0x180023cb7  xor     r14d, r14d
0x180023cba  test    rcx, rcx
0x180023cbd  jz      loc_180023F4A
0x180023cc3  or      r12, 0FFFFFFFFFFFFFFFFh
0x180023cc7  mov     rax, r12
0x180023cca  inc     rax
0x180023ccd  cmp     [rcx+rax*2], r14w
0x180023cd2  jnz     short loc_180023CCA
0x180023cd4  test    rax, rax
0x180023cd7  jz      loc_180023ED6
0x180023cdd  mov     eax, 20h ; ' '
0x180023ce2  cmp     [rcx], ax
0x180023ce5  jz      loc_180023ED6
0x180023ceb  cmp     word ptr [rcx], 9
0x180023cef  jz      loc_180023ED6
0x180023cf5  xor     r8d, r8d; nSize
0x180023cf8  xor     edx, edx; lpDst
0x180023cfa  call    cs:__imp_ExpandEnvironmentStringsW
0x180023d00  mov     edi, eax
0x180023d02  test    eax, eax
0x180023d04  jz      loc_180023EE1
0x180023d0a  mov     r13d, edi
0x180023d0d  mov     eax, 2
0x180023d12  mul     rdi
0x180023d15  mov     rsi, rax
0x180023d18  cmovb   rsi, r12
0x180023d1c  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180023d21  mov     r12d, 54Fh
0x180023d27  test    rax, rax
0x180023d2a  jz      loc_180023F72
0x180023d30  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180023d35  mov     r8, rsi; dwBytes
0x180023d38  xor     edx, edx; dwFlags
0x180023d3a  mov     rcx, rax; hHeap
0x180023d3d  call    cs:__imp_HeapAlloc
0x180023d43  mov     r14, rax
0x180023d46  mov     [rbp+arg_0], r14
0x180023d4a  test    r14, r14
0x180023d4d  jz      loc_180023F97
0x180023d53  mov     r8d, edi; nSize
0x180023d56  mov     rdx, r14; lpDst
0x180023d59  mov     rcx, rbx; lpSrc
0x180023d5c  call    cs:__imp_ExpandEnvironmentStringsW
0x180023d62  test    eax, eax
0x180023d64  jz      loc_180023E08
0x180023d6a  mov     eax, 2
0x180023d6f  mul     r13
0x180023d72  mov     rbx, rax
0x180023d75  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180023d7c  cmovb   rbx, rax
0x180023d80  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180023d85  xor     r13d, r13d
0x180023d88  test    rax, rax
0x180023d8b  jz      loc_180023FA7
0x180023d91  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180023d96  mov     r8, rbx; dwBytes
0x180023d99  xor     edx, edx; dwFlags
0x180023d9b  mov     rcx, rax; hHeap
0x180023d9e  call    cs:__imp_HeapAlloc
0x180023da4  mov     rbx, rax
0x180023da7  mov     [rbp+var_18], rbx
0x180023dab  test    rbx, rbx
0x180023dae  jz      loc_180023FCF
0x180023db4  mov     [rbp+FilePart], r13
0x180023db8  lea     r9, [rbp+FilePart]; lpFilePart
0x180023dbc  mov     r8, rbx; lpBuffer
0x180023dbf  mov     edx, edi; nBufferLength
0x180023dc1  mov     rcx, r14; lpFileName
0x180023dc4  call    cs:__imp_GetFullPathNameW
0x180023dca  mov     ecx, eax
0x180023dcc  test    eax, eax
0x180023dce  jz      short loc_180023DF2
0x180023dd0  lea     eax, [rdi-1]
0x180023dd3  cmp     ecx, eax
0x180023dd5  jnz     short loc_180023DE7
0x180023dd7  mov     rdx, rbx; String2
0x180023dda  mov     rcx, r14; String1
0x180023ddd  call    cs:__imp__wcsicmp
0x180023de3  test    eax, eax
0x180023de5  jz      short loc_180023E16
0x180023de7  mov     ecx, 80338191h; dwErrCode
0x180023dec  call    cs:__imp_SetLastError
0x180023df2  test    r15, r15
0x180023df5  jz      short loc_180023DFE
0x180023df7  mov     [r15], r14
0x180023dfa  mov     [rbp+arg_0], r13
0x180023dfe  lea     rcx, [rbp+var_18]
0x180023e02  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180023e07  nop
0x180023e08  lea     rcx, [rbp+arg_0]
0x180023e0c  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180023e11  jmp     loc_180023EE1
0x180023e16  cmp     [rbp+arg_18], r13d
0x180023e1a  jnz     loc_180023EE5
0x180023e20  mov     edi, [rbp+arg_10]
0x180023e23  mov     rsi, r13
0x180023e26  mov     [rbp+var_20], r13
0x180023e2a  mov     rcx, rbx; String1
0x180023e2d  test    edi, edi
0x180023e2f  jnz     loc_180023FD9
0x180023e35  mov     [rsp+60h+hTemplateFile], r13; hTemplateFile
0x180023e3a  mov     [rsp+60h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180023e42  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x180023e4a  xor     r9d, r9d; lpSecurityAttributes
0x180023e4d  mov     edx, 80000000h; dwDesiredAccess
0x180023e52  lea     r8d, [r9+7]; dwShareMode
0x180023e56  call    cs:__imp_CreateFileW
0x180023e5c  mov     rdi, rax
0x180023e5f  mov     [rbp+var_10], rax
0x180023e63  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023e67  jz      loc_18002402F
0x180023e6d  test    rax, rax
0x180023e70  jz      short loc_180023E9C
0x180023e72  lea     rax, WPP_GLOBAL_Control
0x180023e79  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e80  cmp     rcx, rax
0x180023e83  jz      short loc_180023E92
0x180023e85  test    dword ptr [rcx+1Ch], 1000000h
0x180023e8c  jnz     loc_180024103
0x180023e92  mov     rcx, rdi; hObject
0x180023e95  call    cs:__imp_CloseHandle
0x180023e9b  nop
0x180023e9c  lea     rcx, [rbp+var_20]
0x180023ea0  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180023ea5  nop
0x180023ea6  lea     rcx, [rbp+var_18]
0x180023eaa  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180023eaf  nop
0x180023eb0  lea     rcx, [rbp+arg_0]
0x180023eb4  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180023eb9  mov     eax, 1
0x180023ebe  mov     rbx, [rsp+60h+arg_8]
0x180023ec6  add     rsp, 60h
0x180023eca  pop     r15
0x180023ecc  pop     r14
0x180023ece  pop     r13
0x180023ed0  pop     r12
0x180023ed2  pop     rdi
0x180023ed3  pop     rsi
0x180023ed4  pop     rbp
0x180023ed5  retn
0x180023ed6  mov     ecx, 80338191h; dwErrCode
0x180023edb  call    cs:__imp_SetLastError
0x180023ee1  xor     eax, eax
0x180023ee3  jmp     short loc_180023EBE
0x180023ee5  mov     edx, 25h ; '%'; int
0x180023eea  mov     rcx, rbx; String1
0x180023eed  call    ?StrongPathValidate@@YAHPEBGH@Z; StrongPathValidate(ushort const *,int)
0x180023ef2  test    eax, eax
0x180023ef4  jnz     loc_180023E20
0x180023efa  lea     edx, [rax+26h]; int
0x180023efd  mov     rcx, rbx; String1
0x180023f00  call    ?StrongPathValidate@@YAHPEBGH@Z; StrongPathValidate(ushort const *,int)
0x180023f05  mov     edi, [rbp+arg_10]
0x180023f08  test    eax, eax
0x180023f0a  jnz     loc_180023E23
0x180023f10  test    edi, edi
0x180023f12  jz      short loc_180023F3A
0x180023f14  lea     edx, [rax+29h]; int
0x180023f17  mov     rcx, rbx; String1
0x180023f1a  call    ?StrongPathValidate@@YAHPEBGH@Z; StrongPathValidate(ushort const *,int)
0x180023f1f  test    eax, eax
0x180023f21  jnz     loc_180023E23
0x180023f27  lea     edx, [rax+2Ah]; int
0x180023f2a  mov     rcx, rbx; String1
0x180023f2d  call    ?StrongPathValidate@@YAHPEBGH@Z; StrongPathValidate(ushort const *,int)
0x180023f32  test    eax, eax
0x180023f34  jnz     loc_180023E23
0x180023f3a  mov     ecx, 80338191h; dwErrCode
0x180023f3f  call    cs:__imp_SetLastError
0x180023f45  jmp     loc_180023DFE
0x180023f4a  mov     qword ptr [rsp+60h+dwCreationDisposition], r14; struct IRequestContext *
0x180023f4f  mov     r9d, 54Fh; unsigned int
0x180023f55  lea     r8, a1792; "1792"
0x180023f5c  mov     edx, 700h; unsigned int
0x180023f61  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x180023f68  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180023f6d  jmp     loc_180023EE1
0x180023f72  mov     qword ptr [rsp+60h+dwCreationDisposition], r14; struct IRequestContext *
0x180023f77  mov     r9d, r12d; unsigned int
0x180023f7a  lea     r8, a170; "170"
0x180023f81  mov     edx, 0AAh; unsigned int
0x180023f86  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x180023f8d  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180023f92  jmp     loc_180023D46
0x180023f97  mov     ecx, 0Eh; dwErrCode
0x180023f9c  call    cs:__imp_SetLastError
0x180023fa2  jmp     loc_180023E08
0x180023fa7  mov     qword ptr [rsp+60h+dwCreationDisposition], r13; struct IRequestContext *
0x180023fac  mov     r9d, r12d; unsigned int
0x180023faf  lea     r8, a170; "170"
0x180023fb6  mov     edx, 0AAh; unsigned int
0x180023fbb  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x180023fc2  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180023fc7  mov     rbx, r13
0x180023fca  jmp     loc_180023DA7
0x180023fcf  mov     ecx, 0Eh
0x180023fd4  jmp     loc_180023F3F
0x180023fd9  mov     edx, 25h ; '%'; int
0x180023fde  call    ?StrongPathValidate@@YAHPEBGH@Z; StrongPathValidate(ushort const *,int)
0x180023fe3  mov     rcx, rbx; String1
0x180023fe6  test    eax, eax
0x180023fe8  jz      short loc_180023FF5
0x180023fea  mov     edx, 25h ; '%'
0x180023fef  lea     r8d, [rdx+4]
0x180023ff3  jmp     short loc_180024012
0x180023ff5  mov     edi, 26h ; '&'
0x180023ffa  mov     edx, edi; int
0x180023ffc  call    ?StrongPathValidate@@YAHPEBGH@Z; StrongPathValidate(ushort const *,int)
0x180024001  mov     rcx, rbx
0x180024004  test    eax, eax
0x180024006  jz      loc_180023E35
0x18002400c  lea     r8d, [rdi+4]
0x180024010  mov     edx, edi
0x180024012  lea     r9, [rbp+var_20]
0x180024016  call    ?RedirectPath@@YAHPEBGHHAEAV?$AutoDeleteVector@G@@@Z; RedirectPath(ushort const *,int,int,AutoDeleteVector<ushort> &)
0x18002401b  test    eax, eax
0x18002401d  jz      loc_1800240DC
0x180024023  mov     rsi, [rbp+var_20]
0x180024027  mov     rcx, rsi
0x18002402a  jmp     loc_180023E35
0x18002402f  call    cs:__imp_GetLastError
0x180024035  mov     ecx, eax
0x180024037  cmp     eax, 20h ; ' '
0x18002403a  jnz     short loc_18002404F
0x18002403c  lea     rcx, [rbp+var_10]
0x180024040  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x180024045  mov     edi, 1
0x18002404a  jmp     loc_1800240DF
0x18002404f  add     eax, 0FFFFFFFEh
0x180024052  mov     edi, 1
0x180024057  cmp     eax, edi
0x180024059  jbe     short loc_1800240AE
0x18002405b  cmp     ecx, 7Bh ; '{'
0x18002405e  jz      short loc_1800240A2
0x180024060  cmp     ecx, 5
0x180024063  jnz     short loc_1800240A9
0x180024065  mov     [rsp+60h+hTemplateFile], r13; hTemplateFile
0x18002406a  mov     [rsp+60h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180024072  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x18002407a  xor     r9d, r9d; lpSecurityAttributes
0x18002407d  mov     edx, 80000000h; dwDesiredAccess
0x180024082  lea     r8d, [rdi+6]; dwShareMode
0x180024086  mov     rcx, rbx; lpFileName
0x180024089  call    cs:__imp_CreateFileW
0x18002408f  mov     rdx, rax
0x180024092  lea     rcx, [rbp+var_10]
0x180024096  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x18002409b  cmp     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x1800240a0  jz      short loc_1800240B9
0x1800240a2  mov     ecx, 80338191h
0x1800240a7  jmp     short loc_1800240B3
0x1800240a9  mov     ecx, r12d
0x1800240ac  jmp     short loc_1800240B3
0x1800240ae  mov     ecx, 80338192h; dwErrCode
0x1800240b3  call    cs:__imp_SetLastError
0x1800240b9  test    r15, r15
0x1800240bc  jz      short loc_1800240D3
0x1800240be  test    rsi, rsi
0x1800240c1  jz      short loc_1800240C9
0x1800240c3  mov     [rbp+var_20], r13
0x1800240c7  jmp     short loc_1800240D0
0x1800240c9  mov     [rbp+arg_0], r13
0x1800240cd  mov     rsi, r14
0x1800240d0  mov     [r15], rsi
0x1800240d3  lea     rcx, [rbp+var_10]
0x1800240d7  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1800240dc  mov     edi, r13d
0x1800240df  lea     rcx, [rbp+var_20]
0x1800240e3  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800240e8  nop
0x1800240e9  lea     rcx, [rbp+var_18]
0x1800240ed  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800240f2  nop
0x1800240f3  lea     rcx, [rbp+arg_0]
0x1800240f7  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800240fc  mov     eax, edi
0x1800240fe  jmp     loc_180023EBE
0x180024103  mov     edx, 0Ch
0x180024108  mov     r9, rdi
0x18002410b  lea     r8, WPP_4bcfcb6bc4c53d70488bc6bf4d078fb8_Traceguids
0x180024112  mov     rcx, [rcx+10h]
0x180024116  call    WPP_SF_q
0x18002411b  jmp     loc_180023E92
```
