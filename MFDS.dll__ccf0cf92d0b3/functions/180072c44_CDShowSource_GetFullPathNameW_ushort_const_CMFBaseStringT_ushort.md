# CDShowSource::GetFullPathNameW(ushort const *,CMFBaseStringT<ushort> *)

- ea: `0x180072c44`
- end: `0x180072e82`
- name: `?GetFullPathNameW@CDShowSource@@IEAAJPEBGPEAV?$CMFBaseStringT@G@@@Z`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180052ca8`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x180032a50`
- `0x180051ce4`
- `0x180072c44`
- `0x180074160`
- `0x180076504`
- `0x18007bd58`
- `0x180087408`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072d2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072d2e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180072d1c`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180072d1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072d79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072d79`

## string_xrefs

- `0x180072c6c`: `CDShowSource::GetFullPathNameW`
- `0x180072dd6`: `CDShowSource::GetFullPathNameW`

## pseudocode

```c
__int64 __fastcall CDShowSource::GetFullPathNameW(__int64 a1, const WCHAR *a2, __int64 a3)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v7; // ebx
  __int128 v8; // xmm0
  __int64 v9; // rdi
  DWORD FullPathNameW; // ebx
  DWORD v11; // ebp
  WCHAR *Buffer; // rax
  signed int LastError; // eax
  signed int v14; // ebx
  __int64 v15; // rdx
  CallStackTracing *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  _BYTE v20[8]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v21[16]; // [rsp+38h] [rbp-40h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v20, "CDShowSource::GetFullPathNameW", 426);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *(_QWORD *)(a1 + 1096) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 1096) + 296LL))(*(_QWORD *)(a1 + 1096));
    v8 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 1096) + 280LL))(
                      *(_QWORD *)(a1 + 1096),
                      v21);
    *((_DWORD *)ThreadRelativeContext + 504) = v7;
    *((_OWORD *)ThreadRelativeContext + 125) = v8;
  }
  v9 = 0;
  FullPathNameW = 128;
  v11 = 0;
  while ( 1 )
  {
    if ( v11 >= FullPathNameW )
    {
      v14 = 0;
      if ( (unsigned __int8)byte_1800EACCB >= 4u )
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          31,
          (unsigned int)&WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids,
          a1,
          v9);
      goto LABEL_26;
    }
    Buffer = (WCHAR *)CMFBaseStringT<unsigned short>::GetBuffer(a3, FullPathNameW);
    v9 = (__int64)Buffer;
    if ( !Buffer )
      break;
    v11 = FullPathNameW;
    FullPathNameW = GetFullPathNameW(a2, FullPathNameW, Buffer, 0);
    if ( !FullPathNameW )
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      if ( v14 < 0 && g_wppLevels )
      {
        v15 = 30;
LABEL_23:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids, a1, v14);
        goto LABEL_26;
      }
      goto LABEL_26;
    }
  }
  v16 = CallStackTracing::s_wpInstance;
  v14 = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
    CallStackTracing::s_wpInstance = v17;
    if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
    {
      v16 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v16 = (CallStackTracing *)&qword_1800EB130;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
    }
  }
  if ( *((_BYTE *)v16 + 8) )
  {
    v18 = CallStackTracing::GetThreadRelativeContext(v16);
    if ( *((_DWORD *)v18 + 499) != -2147024882 )
      CallStackContext::TraceFailure(v18, "CDShowSource::GetFullPathNameW", 440, -2147024882);
  }
  if ( g_wppLevels )
  {
    v15 = 29;
    goto LABEL_23;
  }
LABEL_26:
  CMFBaseStringT<unsigned short>::ReleaseBuffer(a3, 0xFFFFFFFFLL);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v20);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180072c44  mov     [rsp+arg_18], rbx
0x180072c49  push    rbp
0x180072c4a  push    rsi
0x180072c4b  push    rdi
0x180072c4c  push    r14
0x180072c4e  push    r15
0x180072c50  sub     rsp, 50h
0x180072c54  mov     rax, cs:__security_cookie
0x180072c5b  xor     rax, rsp
0x180072c5e  mov     [rsp+78h+var_30], rax
0x180072c63  mov     r14, r8
0x180072c66  mov     r15, rdx
0x180072c69  mov     rsi, rcx
0x180072c6c  lea     rdx, aCdshowsourceGe_4; "CDShowSource::GetFullPathNameW"
0x180072c73  mov     r8d, 1AAh; int
0x180072c79  lea     rcx, [rsp+78h+var_48]; this
0x180072c7e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180072c83  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180072c8a  cmp     byte ptr [rcx+8], 0
0x180072c8e  jz      short loc_180072CEC
0x180072c90  cmp     qword ptr [rsi+448h], 0
0x180072c98  jz      short loc_180072CEC
0x180072c9a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072c9f  mov     rdx, [rsi+448h]
0x180072ca6  mov     rdi, rax
0x180072ca9  mov     rcx, [rdx]
0x180072cac  mov     rax, [rcx+128h]
0x180072cb3  mov     rcx, rdx
0x180072cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072cbb  mov     r8, [rsi+448h]
0x180072cc2  lea     rdx, [rsp+78h+var_40]
0x180072cc7  mov     ebx, eax
0x180072cc9  mov     rcx, [r8]
0x180072ccc  mov     rax, [rcx+118h]
0x180072cd3  mov     rcx, r8
0x180072cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072cdb  movups  xmm0, xmmword ptr [rax]
0x180072cde  mov     [rdi+7E0h], ebx
0x180072ce4  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180072cec  xor     edi, edi
0x180072cee  mov     ebx, 80h
0x180072cf3  xor     ebp, ebp
0x180072cf5  cmp     ebp, ebx
0x180072cf7  jnb     loc_180072E19
0x180072cfd  mov     edx, ebx
0x180072cff  mov     rcx, r14
0x180072d02  call    ?GetBuffer@?$CMFBaseStringT@G@@QEAAPEAGJ@Z; CMFBaseStringT<ushort>::GetBuffer(long)
0x180072d07  mov     rdi, rax
0x180072d0a  test    rax, rax
0x180072d0d  jz      short loc_180072D68
0x180072d0f  xor     r9d, r9d; lpFilePart
0x180072d12  mov     r8, rax; lpBuffer
0x180072d15  mov     edx, ebx; nBufferLength
0x180072d17  mov     rcx, r15; lpFileName
0x180072d1a  mov     ebp, ebx
0x180072d1c  call    cs:__imp_GetFullPathNameW
0x180072d23  nop     dword ptr [rax+rax+00h]
0x180072d28  mov     ebx, eax
0x180072d2a  test    eax, eax
0x180072d2c  jnz     short loc_180072CF5
0x180072d2e  call    cs:__imp_GetLastError
0x180072d35  nop     dword ptr [rax+rax+00h]
0x180072d3a  mov     ebx, eax
0x180072d3c  test    eax, eax
0x180072d3e  jle     short loc_180072D49
0x180072d40  movzx   ebx, ax
0x180072d43  or      ebx, 80070000h
0x180072d49  test    ebx, ebx
0x180072d4b  jns     loc_180072E49
0x180072d51  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072d58  jb      loc_180072E49
0x180072d5e  mov     edx, 1Eh
0x180072d63  jmp     loc_180072DF9
0x180072d68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072d6f  mov     ebx, 8007000Eh
0x180072d74  test    rcx, rcx
0x180072d77  jnz     short loc_180072DC0
0x180072d79  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072d80  nop     dword ptr [rax+rax+00h]
0x180072d85  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072d8c  mov     rcx, rax
0x180072d8f  test    rax, rax
0x180072d92  jz      short loc_180072DB2
0x180072d94  mov     rax, [rax]
0x180072d97  mov     edx, 7F0h
0x180072d9c  mov     rax, [rax+8]
0x180072da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072da5  test    eax, eax
0x180072da7  jz      short loc_180072DB2
0x180072da9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072db0  jmp     short loc_180072DC0
0x180072db2  lea     rcx, qword_1800EB130; this
0x180072db9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180072dc0  cmp     byte ptr [rcx+8], 0
0x180072dc4  jz      short loc_180072DEB
0x180072dc6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072dcb  cmp     [rax+7CCh], ebx
0x180072dd1  jz      short loc_180072DEB
0x180072dd3  mov     r9d, ebx; int
0x180072dd6  lea     rdx, aCdshowsourceGe_4; "CDShowSource::GetFullPathNameW"
0x180072ddd  mov     r8d, 1B8h; int
0x180072de3  mov     rcx, rax; this
0x180072de6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072deb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072df2  jb      short loc_180072E49
0x180072df4  mov     edx, 1Dh
0x180072df9  mov     rcx, cs:WPP_GLOBAL_Control
0x180072e00  lea     r8, WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids
0x180072e07  mov     r9, rsi
0x180072e0a  mov     dword ptr [rsp+78h+var_58], ebx
0x180072e0e  mov     rcx, [rcx+10h]
0x180072e12  call    WPP_SF_qD
0x180072e17  jmp     short loc_180072E49
0x180072e19  xor     ebx, ebx
0x180072e1b  cmp     cs:byte_1800EACCB, 4
0x180072e22  jb      short loc_180072E49
0x180072e24  mov     rcx, cs:WPP_GLOBAL_Control
0x180072e2b  lea     edx, [rbx+1Fh]
0x180072e2e  mov     r9, rsi
0x180072e31  mov     [rsp+78h+var_58], rdi
0x180072e36  lea     r8, WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids
0x180072e3d  mov     rcx, [rcx+88h]
0x180072e44  call    WPP_SF_qS
0x180072e49  or      edx, 0FFFFFFFFh
0x180072e4c  mov     rcx, r14
0x180072e4f  call    ?ReleaseBuffer@?$CMFBaseStringT@G@@QEAAJJ@Z; CMFBaseStringT<ushort>::ReleaseBuffer(long)
0x180072e54  lea     rcx, [rsp+78h+var_48]; this
0x180072e59  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180072e5e  mov     eax, ebx
0x180072e60  mov     rcx, [rsp+78h+var_30]
0x180072e65  xor     rcx, rsp; StackCookie
0x180072e68  call    __security_check_cookie
0x180072e6d  mov     rbx, [rsp+78h+arg_18]
0x180072e75  add     rsp, 50h
0x180072e79  pop     r15
0x180072e7b  pop     r14
0x180072e7d  pop     rdi
0x180072e7e  pop     rsi
0x180072e7f  pop     rbp
0x180072e80  retn
```
