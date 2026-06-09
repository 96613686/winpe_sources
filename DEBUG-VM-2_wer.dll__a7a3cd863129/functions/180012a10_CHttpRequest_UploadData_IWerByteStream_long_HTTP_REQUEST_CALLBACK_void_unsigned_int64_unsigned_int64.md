# CHttpRequest::UploadData(IWerByteStream *,long (*)(_HTTP_REQUEST_CALLBACK *),void *,unsigned __int64,unsigned __int64)

- ea: `0x180012a10`
- end: `0x180012ee5`
- name: `?UploadData@CHttpRequest@@IEAAJPEAUIWerByteStream@@P6AJPEAU_HTTP_REQUEST_CALLBACK@@@ZPEAX_K4@Z`
- size: `1237`
- prototype: `__int64 __usercall@<rax>(CHttpRequest *__hidden this@<rcx>, struct IWerByteStream *@<rdx>, int (*)(struct _HTTP_REQUEST_CALLBACK *)@<r8>, void *@<r9>, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18009b1e8`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x180012a10`
- `0x180012fe0`
- `0x18001fe24`
- `0x180026a68`
- `0x180039eb4`
- `0x18004c6ac`
- `0x180050db0`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012af0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012af0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012b66`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012b66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012a66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012a79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012acb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012a66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012a79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012acb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180012a87`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180012ad8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180012a87`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180012ad8`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180012a6f`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180012a6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012bca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012bca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012bf3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012bf3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012cda`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012cda`
- `WINHTTP!WinHttpWriteData` at `0x180012bdf`
- `WINHTTP!WinHttpWriteData` at `0x180012bdf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHttpRequest::UploadData(
        CHttpRequest *this,
        struct IWerByteStream *a2,
        __int64 (__fastcall *a3)(__int128 *),
        void *a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  struct IWerByteStream *v7; // rbp
  void *v9; // r12
  HANDLE CurrentThread; // rax
  HANDLE v11; // rax
  unsigned __int64 v12; // r14
  int v13; // edi
  wchar_t *v14; // rcx
  HANDLE v15; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned __int64 v19; // r15
  void *v20; // rcx
  BOOL v21; // edi
  DWORD LastError; // ebp
  bool v23; // r9
  unsigned int v24; // eax
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r9
  wchar_t *v30; // rcx
  __int64 v31; // rdx
  DWORD v32; // eax
  DWORD dwNumberOfBytesToWrite; // [rsp+30h] [rbp-A8h] BYREF
  int nPriority; // [rsp+34h] [rbp-A4h]
  struct IWerByteStream *v35; // [rsp+38h] [rbp-A0h]
  void *v36; // [rsp+40h] [rbp-98h]
  void *v37; // [rsp+48h] [rbp-90h]
  __int128 v38; // [rsp+50h] [rbp-88h] BYREF
  __int128 v39; // [rsp+60h] [rbp-78h]
  void *v40[2]; // [rsp+70h] [rbp-68h] BYREF
  __int64 v41; // [rsp+80h] [rbp-58h]

  v37 = a4;
  v7 = a2;
  v35 = a2;
  dwNumberOfBytesToWrite = 0;
  v38 = 0;
  v39 = 0;
  v9 = 0;
  v36 = 0;
  CurrentThread = GetCurrentThread();
  nPriority = GetThreadPriority(CurrentThread);
  v11 = GetCurrentThread();
  SetThreadPriority(v11, -1);
  v12 = a5;
  v13 = (*(__int64 (__fastcall **)(struct IWerByteStream *, unsigned __int64, _QWORD, _QWORD))(*(_QWORD *)v7 + 16LL))(
          v7,
          a5,
          0,
          0);
  if ( v13 >= 0 )
  {
    v19 = (*(__int64 (__fastcall **)(struct IWerByteStream *))(*(_QWORD *)v7 + 32LL))(v7);
    if ( a6 && a5 + a6 < (*(__int64 (__fastcall **)(struct IWerByteStream *))(*(_QWORD *)v7 + 32LL))(v7) )
      v19 = a5 + a6;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_III(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, a5, v19, a6);
    v9 = HeapAlloc(g_hWerheap, 0, 0x1000u);
    v36 = v9;
    if ( v9 )
    {
      while ( 1 )
      {
        if ( v12 >= v19 )
        {
          v13 = 0;
          goto LABEL_3;
        }
        v20 = (void *)*((_QWORD *)this + 5);
        if ( v20 && !WaitForSingleObject(v20, 0) )
        {
          v13 = -2147467260;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v31 = 98;
            goto LABEL_28;
          }
          goto LABEL_3;
        }
        v13 = (**(__int64 (__fastcall ***)(struct IWerByteStream *, void *, __int64, DWORD *, _QWORD))v7)(
                v7,
                v9,
                4096,
                &dwNumberOfBytesToWrite,
                *((_QWORD *)this + 4));
        if ( v13 < 0 )
          break;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
        v21 = WinHttpWriteData(*((HINTERNET *)this + 2), v9, dwNumberOfBytesToWrite, 0);
        LastError = GetLastError();
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
        if ( !v21 )
        {
          v13 = ERROR_HR_FROM_WIN32(LastError);
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v28 = 100;
            goto LABEL_23;
          }
          goto LABEL_3;
        }
        v40[0] = *((void **)this + 3);
        v40[1] = *((void **)this + 4);
        v41 = *((_QWORD *)this + 5);
        v24 = UtilWaitForMultipleObjects(
                L"CHttpRequest async operation",
                (v41 != 0) + 2,
                v40,
                v23,
                *((_DWORD *)this + 216));
        if ( v24 )
        {
          switch ( v24 )
          {
            case 1u:
              goto LABEL_54;
            case 2u:
              CHttpRequest::AbortRequest(this);
LABEL_54:
              v13 = -2147467260;
LABEL_49:
              v26 = v13;
LABEL_50:
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v28 = 101;
                v29 = (unsigned int)v26;
                goto LABEL_32;
              }
              goto LABEL_3;
            case 0x102u:
              CHttpRequest::AbortRequest(this);
              v13 = -2147023436;
              goto LABEL_49;
          }
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v24);
          v32 = GetLastError();
          v26 = ERROR_HR_FROM_WIN32(v32);
        }
        else
        {
          v26 = *((_DWORD *)this + 14);
        }
        v13 = v26;
        if ( v26 < 0 )
          goto LABEL_50;
        v27 = dwNumberOfBytesToWrite;
        if ( dwNumberOfBytesToWrite != *((_DWORD *)this + 258) )
        {
          MicrosoftTelemetryAssertTriggeredArgs(v25, dwNumberOfBytesToWrite);
          v27 = dwNumberOfBytesToWrite;
        }
        v12 += v27;
        LODWORD(v38) = 1;
        *((_QWORD *)&v38 + 1) = v37;
        *(_QWORD *)&v39 = v12;
        v7 = v35;
        if ( a3 )
        {
          v13 = a3(&v38);
          if ( v13 < 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v28 = 102;
              goto LABEL_23;
            }
            goto LABEL_3;
          }
        }
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v28 = 99;
        goto LABEL_23;
      }
    }
    else
    {
      v13 = -2147024882;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v31 = 97;
LABEL_28:
        WPP_SF_(*((_QWORD *)v30 + 2), v31, WPP_158c1c2611d1379e0dd259997317728c_Traceguids);
      }
    }
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v28 = 95;
LABEL_23:
      v29 = (unsigned int)v13;
LABEL_32:
      WPP_SF_d(*((_QWORD *)v14 + 2), v28, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v29);
    }
  }
LABEL_3:
  v15 = GetCurrentThread();
  SetThreadPriority(v15, nPriority);
  if ( v9 )
    HeapFree(g_hWerheap, 0, v9);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180012a10  push    rbx
0x180012a12  push    rbp
0x180012a13  push    rsi
0x180012a14  push    rdi
0x180012a15  push    r12
0x180012a17  push    r13
0x180012a19  push    r14
0x180012a1b  push    r15
0x180012a1d  sub     rsp, 98h
0x180012a24  mov     rax, cs:__security_cookie
0x180012a2b  xor     rax, rsp
0x180012a2e  mov     [rsp+0D8h+var_50], rax
0x180012a36  mov     [rsp+0D8h+var_90], r9
0x180012a3b  mov     r13, r8
0x180012a3e  mov     rbp, rdx
0x180012a41  mov     [rsp+0D8h+var_A0], rdx
0x180012a46  mov     rbx, rcx
0x180012a49  mov     [rsp+0D8h+dwNumberOfBytesToWrite], 0
0x180012a51  xorps   xmm0, xmm0
0x180012a54  movups  [rsp+0D8h+var_88], xmm0
0x180012a59  movups  [rsp+0D8h+var_78], xmm0
0x180012a5e  xor     r12d, r12d
0x180012a61  mov     [rsp+0D8h+var_98], r12
0x180012a66  call    cs:__imp_GetCurrentThread
0x180012a6c  mov     rcx, rax; hThread
0x180012a6f  call    cs:__imp_GetThreadPriority
0x180012a75  mov     [rsp+0D8h+nPriority], eax
0x180012a79  call    cs:__imp_GetCurrentThread
0x180012a7f  mov     rcx, rax; hThread
0x180012a82  mov     edx, 0FFFFFFFFh; nPriority
0x180012a87  call    cs:__imp_SetThreadPriority
0x180012a8d  mov     rcx, [rbp+0]
0x180012a91  mov     rax, [rcx+10h]
0x180012a95  xor     r9d, r9d
0x180012a98  xor     r8d, r8d
0x180012a9b  mov     r14, [rsp+0D8h+arg_20]
0x180012aa3  mov     rdx, r14
0x180012aa6  mov     rcx, rbp
0x180012aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012aae  mov     edi, eax
0x180012ab0  test    eax, eax
0x180012ab2  jns     short loc_180012B1C
0x180012ab4  lea     rax, WPP_GLOBAL_Control
0x180012abb  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ac2  cmp     rcx, rax
0x180012ac5  jnz     loc_180012D2F
0x180012acb  call    cs:__imp_GetCurrentThread
0x180012ad1  mov     rcx, rax; hThread
0x180012ad4  mov     edx, [rsp+0D8h+nPriority]; nPriority
0x180012ad8  call    cs:__imp_SetThreadPriority
0x180012ade  nop
0x180012adf  test    r12, r12
0x180012ae2  jz      short loc_180012AF6
0x180012ae4  mov     r8, r12; lpMem
0x180012ae7  xor     edx, edx; dwFlags
0x180012ae9  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180012af0  call    cs:__imp_HeapFree
0x180012af6  mov     eax, edi
0x180012af8  mov     rcx, [rsp+0D8h+var_50]
0x180012b00  xor     rcx, rsp; StackCookie
0x180012b03  call    __security_check_cookie
0x180012b08  add     rsp, 98h
0x180012b0f  pop     r15
0x180012b11  pop     r14
0x180012b13  pop     r13
0x180012b15  pop     r12
0x180012b17  pop     rdi
0x180012b18  pop     rsi
0x180012b19  pop     rbp
0x180012b1a  pop     rbx
0x180012b1b  retn
0x180012b1c  mov     rax, [rbp+0]
0x180012b20  mov     rcx, rbp
0x180012b23  mov     rax, [rax+20h]
0x180012b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b2c  mov     r15, rax
0x180012b2f  mov     rsi, [rsp+0D8h+arg_28]
0x180012b37  test    rsi, rsi
0x180012b3a  jnz     loc_180012D5D
0x180012b40  lea     rax, WPP_GLOBAL_Control
0x180012b47  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b4e  cmp     rcx, rax
0x180012b51  jnz     loc_180012D7D
0x180012b57  xor     edx, edx; dwFlags
0x180012b59  mov     r8d, 1000h; dwBytes
0x180012b5f  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180012b66  call    cs:__imp_HeapAlloc
0x180012b6c  mov     r12, rax
0x180012b6f  mov     [rsp+0D8h+var_98], rax
0x180012b74  test    rax, rax
0x180012b77  jz      loc_180012DA2
0x180012b7d  nop     dword ptr [rax]
0x180012b80  cmp     r14, r15
0x180012b83  jnb     loc_180012D28
0x180012b89  mov     rcx, [rbx+28h]; hHandle
0x180012b8d  test    rcx, rcx
0x180012b90  jnz     loc_180012CD8
0x180012b96  mov     rax, [rbp+0]
0x180012b9a  mov     rcx, [rbx+20h]
0x180012b9e  mov     qword ptr [rsp+0D8h+var_B8], rcx
0x180012ba3  lea     r9, [rsp+0D8h+dwNumberOfBytesToWrite]
0x180012ba8  mov     r8d, 1000h
0x180012bae  mov     rdx, r12
0x180012bb1  mov     rcx, rbp
0x180012bb4  mov     rax, [rax]
0x180012bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bbc  mov     edi, eax
0x180012bbe  test    eax, eax
0x180012bc0  js      loc_180012EB9
0x180012bc6  lea     rcx, [rbx+48h]; lpCriticalSection
0x180012bca  call    cs:__imp_EnterCriticalSection
0x180012bd0  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x180012bd3  mov     r8d, [rsp+0D8h+dwNumberOfBytesToWrite]; dwNumberOfBytesToWrite
0x180012bd8  mov     rdx, r12; lpBuffer
0x180012bdb  mov     rcx, [rbx+10h]; hRequest
0x180012bdf  call    cs:__imp_WinHttpWriteData
0x180012be5  mov     edi, eax
0x180012be7  call    cs:__imp_GetLastError
0x180012bed  mov     ebp, eax
0x180012bef  lea     rcx, [rbx+48h]; lpCriticalSection
0x180012bf3  call    cs:__imp_LeaveCriticalSection
0x180012bf9  test    edi, edi
0x180012bfb  jz      loc_180012E85
0x180012c01  mov     rax, [rbx+18h]
0x180012c05  mov     [rsp+0D8h+var_68], rax
0x180012c0a  mov     rax, [rbx+20h]
0x180012c0e  mov     [rsp+0D8h+var_60], rax
0x180012c13  mov     rax, [rbx+28h]
0x180012c17  mov     [rsp+0D8h+var_58], rax
0x180012c1f  xor     edx, edx
0x180012c21  test    rax, rax
0x180012c24  setnz   dl
0x180012c27  add     edx, 2; unsigned int
0x180012c2a  mov     eax, [rbx+360h]
0x180012c30  mov     [rsp+0D8h+var_B8], eax; unsigned int
0x180012c34  lea     r8, [rsp+0D8h+var_68]; void **
0x180012c39  lea     rcx, aChttprequestAs; "CHttpRequest async operation"
0x180012c40  call    ?UtilWaitForMultipleObjects@@YAKPEB_WKQEAPEAX_NK@Z; UtilWaitForMultipleObjects(wchar_t const *,ulong,void * * const,bool,ulong)
0x180012c45  test    eax, eax
0x180012c47  jnz     loc_180012DD2
0x180012c4d  mov     eax, [rbx+38h]
0x180012c50  mov     edi, eax
0x180012c52  test    eax, eax
0x180012c54  js      loc_180012E50
0x180012c5a  mov     r8d, [rbx+408h]
0x180012c61  mov     eax, [rsp+0D8h+dwNumberOfBytesToWrite]
0x180012c65  cmp     eax, r8d
0x180012c68  jnz     loc_180012E31
0x180012c6e  add     r14, rax
0x180012c71  mov     dword ptr [rsp+0D8h+var_88], 1
0x180012c79  mov     rax, [rsp+0D8h+var_90]
0x180012c7e  mov     qword ptr [rsp+0D8h+var_88+8], rax
0x180012c83  mov     qword ptr [rsp+0D8h+var_78], r14
0x180012c88  test    r13, r13
0x180012c8b  mov     rbp, [rsp+0D8h+var_A0]
0x180012c90  jz      loc_180012B80
0x180012c96  lea     rcx, [rsp+0D8h+var_88]
0x180012c9b  mov     rax, r13
0x180012c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ca3  mov     edi, eax
0x180012ca5  test    eax, eax
0x180012ca7  jns     loc_180012B80
0x180012cad  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cb4  lea     rax, WPP_GLOBAL_Control
0x180012cbb  cmp     rcx, rax
0x180012cbe  jz      loc_180012ACB
0x180012cc4  test    byte ptr [rcx+1Ch], 1
0x180012cc8  jz      loc_180012ACB
0x180012cce  mov     edx, 66h ; 'f'
0x180012cd3  mov     r9d, edi
0x180012cd6  jmp     short loc_180012D48
0x180012cd8  xor     edx, edx; dwMilliseconds
0x180012cda  call    cs:__imp_WaitForSingleObject
0x180012ce0  test    eax, eax
0x180012ce2  jnz     loc_180012B96
0x180012ce8  mov     edi, 80004004h
0x180012ced  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cf4  lea     rax, WPP_GLOBAL_Control
0x180012cfb  cmp     rcx, rax
0x180012cfe  jz      loc_180012ACB
0x180012d04  test    byte ptr [rcx+1Ch], 1
0x180012d08  jz      loc_180012ACB
0x180012d0e  mov     edx, 62h ; 'b'
0x180012d13  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x180012d1a  mov     rcx, [rcx+10h]
0x180012d1e  call    WPP_SF_
0x180012d23  jmp     loc_180012ACB
0x180012d28  xor     edi, edi
0x180012d2a  jmp     loc_180012ACB
0x180012d2f  test    byte ptr [rcx+1Ch], 1
0x180012d33  jz      loc_180012ACB
0x180012d39  mov     edx, 5Fh ; '_'
0x180012d3e  jmp     short loc_180012CD3
0x180012d40  mov     edx, 65h ; 'e'
0x180012d45  mov     r9d, eax
0x180012d48  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x180012d4f  mov     rcx, [rcx+10h]
0x180012d53  call    WPP_SF_d
0x180012d58  jmp     loc_180012ACB
0x180012d5d  lea     rdi, [r14+rsi]
0x180012d61  mov     rcx, [rbp+0]
0x180012d65  mov     rax, [rcx+20h]
0x180012d69  mov     rcx, rbp
0x180012d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d71  cmp     rdi, rax
0x180012d74  cmovb   r15, rdi
0x180012d78  jmp     loc_180012B40
0x180012d7d  test    byte ptr [rcx+1Ch], 1
0x180012d81  jz      loc_180012B57
0x180012d87  mov     [rsp+0D8h+var_B0], rsi
0x180012d8c  mov     qword ptr [rsp+0D8h+var_B8], r15
0x180012d91  mov     r9, r14
0x180012d94  mov     rcx, [rcx+10h]
0x180012d98  call    WPP_SF_III
0x180012d9d  jmp     loc_180012B57
0x180012da2  mov     edi, 8007000Eh
0x180012da7  mov     rcx, cs:WPP_GLOBAL_Control
0x180012dae  lea     rax, WPP_GLOBAL_Control
0x180012db5  cmp     rcx, rax
0x180012db8  jz      loc_180012ACB
0x180012dbe  test    byte ptr [rcx+1Ch], 1
0x180012dc2  jz      loc_180012ACB
0x180012dc8  mov     edx, 61h ; 'a'
0x180012dcd  jmp     loc_180012D13
0x180012dd2  mov     ecx, eax
0x180012dd4  sub     ecx, 1
0x180012dd7  jz      loc_180012E7E
0x180012ddd  sub     ecx, 1
0x180012de0  jz      loc_180012E76
0x180012de6  cmp     ecx, 100h
0x180012dec  jz      short loc_180012E41
0x180012dee  mov     rcx, cs:WPP_GLOBAL_Control
0x180012df5  lea     rdx, WPP_GLOBAL_Control
0x180012dfc  cmp     rcx, rdx
0x180012dff  jz      short loc_180012E1F
0x180012e01  test    byte ptr [rcx+1Ch], 1
0x180012e05  jz      short loc_180012E1F
0x180012e07  mov     edx, 10h
0x180012e0c  mov     r9d, eax
0x180012e0f  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x180012e16  mov     rcx, [rcx+10h]
0x180012e1a  call    WPP_SF_d
0x180012e1f  call    cs:__imp_GetLastError
0x180012e25  mov     ecx, eax; unsigned int
0x180012e27  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180012e2c  jmp     loc_180012C50
0x180012e31  mov     edx, eax
0x180012e33  call    MicrosoftTelemetryAssertTriggeredArgs
0x180012e38  mov     eax, [rsp+0D8h+dwNumberOfBytesToWrite]
0x180012e3c  jmp     loc_180012C6E
0x180012e41  mov     rcx, rbx; this
0x180012e44  call    ?AbortRequest@CHttpRequest@@QEAAXXZ; CHttpRequest::AbortRequest(void)
0x180012e49  mov     edi, 800705B4h
0x180012e4e  mov     eax, edi
0x180012e50  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e57  lea     rdx, WPP_GLOBAL_Control
0x180012e5e  cmp     rcx, rdx
0x180012e61  jz      loc_180012ACB
0x180012e67  test    byte ptr [rcx+1Ch], 1
0x180012e6b  jz      loc_180012ACB
0x180012e71  jmp     loc_180012D40
0x180012e76  mov     rcx, rbx; this
0x180012e79  call    ?AbortRequest@CHttpRequest@@QEAAXXZ; CHttpRequest::AbortRequest(void)
0x180012e7e  mov     edi, 80004004h
0x180012e83  jmp     short loc_180012E4E
0x180012e85  mov     ecx, ebp; unsigned int
0x180012e87  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180012e8c  mov     edi, eax
0x180012e8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e95  lea     rax, WPP_GLOBAL_Control
0x180012e9c  cmp     rcx, rax
0x180012e9f  jz      loc_180012ACB
0x180012ea5  test    byte ptr [rcx+1Ch], 1
0x180012ea9  jz      loc_180012ACB
0x180012eaf  mov     edx, 64h ; 'd'
0x180012eb4  jmp     loc_180012CD3
0x180012eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ec0  lea     rax, WPP_GLOBAL_Control
0x180012ec7  cmp     rcx, rax
0x180012eca  jz      loc_180012ACB
0x180012ed0  test    byte ptr [rcx+1Ch], 1
0x180012ed4  jz      loc_180012ACB
0x180012eda  mov     edx, 63h ; 'c'
0x180012edf  jmp     loc_180012CD3
```
