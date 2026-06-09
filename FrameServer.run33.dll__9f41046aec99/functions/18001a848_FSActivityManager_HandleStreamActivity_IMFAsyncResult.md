# FSActivityManager::HandleStreamActivity(IMFAsyncResult *)

- ea: `0x18001a848`
- end: `0x18001aad3`
- name: `?HandleStreamActivity@FSActivityManager@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `651`
- prototype: `void __fastcall(FSActivityManager *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18001afe0`

## callees

- `0x18000920c`
- `0x1800095c8`
- `0x180009608`
- `0x180009f50`
- `0x18000a91c`
- `0x180017a3c`
- `0x18001a848`
- `0x18001c8b4`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aabc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aabc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a867`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a934`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a934`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001a9cd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001a9cd`

## pseudocode

```c
void __fastcall FSActivityManager::HandleStreamActivity(FSActivityManager *this, struct IMFAsyncResult *a2)
{
  void *v3; // rdx
  __int64 v4; // r8
  unsigned int v5; // r13d
  signed int v6; // esi
  char *v7; // r14
  DWORD v8; // r12d
  __int64 v9; // r15
  __int64 *v10; // rax
  __int64 v11; // rax
  __int64 unique; // rax
  __int64 v13; // rdx
  DWORD CurrentProcessId; // eax
  __int64 v15; // r15
  __int64 v16; // rdx
  signed int LastError; // eax
  _QWORD *v18; // [rsp+40h] [rbp-18h]
  int v19; // [rsp+A0h] [rbp+48h]
  struct IMFAsyncResult *v20; // [rsp+A8h] [rbp+50h] BYREF
  DWORD BytesReturned; // [rsp+B0h] [rbp+58h] BYREF
  LPVOID lpInBuffer; // [rsp+B8h] [rbp+60h] BYREF

  v20 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v5 = *((_DWORD *)this + 82);
  v6 = 0;
  --*((_DWORD *)this + 38);
  v7 = 0;
  lpInBuffer = 0;
  BytesReturned = 0;
  v8 = 8;
  *((_QWORD *)this + 20) = 0;
  if ( *((_BYTE *)this + 168) )
    goto LABEL_20;
  v9 = 0;
  v10 = (__int64 *)((char *)this + 320);
  v18 = (_QWORD *)((char *)this + 320);
  if ( !v5 )
  {
    v18 = (_QWORD *)((char *)this + 320);
LABEL_7:
    unique = wil::make_unique_nothrow<unsigned char [0]>(&v20, v8);
    wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(&lpInBuffer, unique);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v20);
    v7 = (char *)lpInBuffer;
    if ( lpInBuffer )
    {
      CurrentProcessId = GetCurrentProcessId();
      v15 = 0;
      v16 = 8;
      v19 = 8;
      *(_DWORD *)v7 = CurrentProcessId;
      for ( *((_DWORD *)v7 + 1) = 1; (unsigned int)v15 < v5; v19 += (int)v20 )
      {
        LODWORD(v20) = 0;
        v6 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, struct IMFAsyncResult **))(**(_QWORD **)(*v18 + 8 * v15)
                                                                                         + 96LL))(
               *(_QWORD *)(*v18 + 8 * v15),
               &v7[v16],
               v8 - (unsigned int)v16,
               &v20);
        if ( v6 < 0 )
          goto LABEL_20;
        v15 = (unsigned int)(v15 + 1);
        v16 = (unsigned int)((_DWORD)v20 + v19);
      }
      if ( DeviceIoControl(*((HANDLE *)this + 12), 0x2F0428u, v7, v8, 0, 0, &BytesReturned, 0) )
        goto LABEL_20;
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 || !g_wppLevels )
        goto LABEL_20;
      v13 = 82;
    }
    else
    {
      v6 = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_20;
      v13 = (unsigned int)((_DWORD)lpInBuffer + 81);
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids, this, v6);
    goto LABEL_20;
  }
  while ( 1 )
  {
    v11 = *v10;
    LODWORD(v20) = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD, struct IMFAsyncResult **))(**(_QWORD **)(v11 + 8 * v9) + 88LL))(
           *(_QWORD *)(v11 + 8 * v9),
           &v20);
    if ( v6 < 0 )
      break;
    v8 += (unsigned int)v20;
    v10 = (__int64 *)((char *)this + 320);
    v9 = (unsigned int)(v9 + 1);
    if ( (unsigned int)v9 >= v5 )
      goto LABEL_7;
  }
LABEL_20:
  if ( *((_BYTE *)this + 168) )
  {
    if ( !*((_DWORD *)this + 38) )
    {
      wil::details::SetEvent(*((wil::details **)this + 18), v3);
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 83, &WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids, this);
    }
  }
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147024882 && (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qDqdq(*((_QWORD *)WPP_GLOBAL_Control + 27), v3, v4, this, v6, *((_QWORD *)this + 12), v8, v7);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&lpInBuffer);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
}

```

## disassembly

```asm
0x18001a848  mov     [rsp-40h+arg_8], rdx
0x18001a84d  push    rbp
0x18001a84e  push    rbx
0x18001a84f  push    rsi
0x18001a850  push    rdi
0x18001a851  push    r12
0x18001a853  push    r13
0x18001a855  push    r14
0x18001a857  push    r15
0x18001a859  mov     rbp, rsp
0x18001a85c  sub     rsp, 58h
0x18001a860  mov     rdi, rcx
0x18001a863  add     rcx, 68h ; 'h'; lpCriticalSection
0x18001a867  call    cs:__imp_EnterCriticalSection
0x18001a86d  mov     r13d, [rdi+148h]
0x18001a874  xor     esi, esi
0x18001a876  dec     dword ptr [rdi+98h]
0x18001a87c  xor     r14d, r14d
0x18001a87f  mov     [rbp+lpInBuffer], r14
0x18001a883  mov     [rbp+BytesReturned], esi
0x18001a886  lea     r12d, [rsi+8]
0x18001a88a  mov     [rdi+0A0h], rsi
0x18001a891  cmp     [rdi+0A8h], sil
0x18001a898  jnz     loc_18001AA1C
0x18001a89e  xor     r15d, r15d
0x18001a8a1  lea     rax, [rdi+140h]
0x18001a8a8  mov     [rbp+var_18], rax
0x18001a8ac  test    r13d, r13d
0x18001a8af  jz      short loc_18001A8EB
0x18001a8b1  mov     rax, [rax]
0x18001a8b4  lea     rdx, [rbp+arg_8]
0x18001a8b8  mov     dword ptr [rbp+arg_8], r14d
0x18001a8bc  mov     rcx, [rax+r15*8]
0x18001a8c0  mov     rax, [rcx]
0x18001a8c3  mov     rax, [rax+58h]
0x18001a8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8cc  mov     esi, eax
0x18001a8ce  test    eax, eax
0x18001a8d0  js      loc_18001AA1C
0x18001a8d6  add     r12d, dword ptr [rbp+arg_8]
0x18001a8da  lea     rax, [rdi+140h]
0x18001a8e1  inc     r15d
0x18001a8e4  cmp     r15d, r13d
0x18001a8e7  jb      short loc_18001A8B1
0x18001a8e9  jmp     short loc_18001A8EF
0x18001a8eb  mov     [rbp+var_18], rax
0x18001a8ef  mov     edx, r12d
0x18001a8f2  lea     rcx, [rbp+arg_8]
0x18001a8f6  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18001a8fb  mov     rdx, rax
0x18001a8fe  lea     rcx, [rbp+lpInBuffer]
0x18001a902  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x18001a907  lea     rcx, [rbp+arg_8]
0x18001a90b  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18001a910  mov     r14, [rbp+lpInBuffer]
0x18001a914  test    r14, r14
0x18001a917  jnz     short loc_18001A934
0x18001a919  mov     esi, 8007000Eh
0x18001a91e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a925  jb      loc_18001AA1C
0x18001a92b  lea     edx, [r14+51h]
0x18001a92f  jmp     loc_18001A9FE
0x18001a934  call    cs:__imp_GetCurrentProcessId
0x18001a93a  xor     r15d, r15d
0x18001a93d  mov     edx, 8
0x18001a942  mov     [rbp+arg_0], edx
0x18001a945  mov     [r14], eax
0x18001a948  mov     dword ptr [r14+4], 1
0x18001a950  test    r13d, r13d
0x18001a953  jz      short loc_18001A99B
0x18001a955  mov     rax, [rbp+var_18]
0x18001a959  lea     r9, [rbp+arg_8]
0x18001a95d  mov     dword ptr [rbp+arg_8], 0
0x18001a964  mov     r8d, r12d
0x18001a967  sub     r8d, edx
0x18001a96a  add     rdx, r14
0x18001a96d  mov     rax, [rax]
0x18001a970  mov     rcx, [rax+r15*8]
0x18001a974  mov     rax, [rcx]
0x18001a977  mov     rax, [rax+60h]
0x18001a97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a980  mov     esi, eax
0x18001a982  test    eax, eax
0x18001a984  js      loc_18001AA1C
0x18001a98a  mov     edx, [rbp+arg_0]
0x18001a98d  inc     r15d
0x18001a990  add     edx, dword ptr [rbp+arg_8]
0x18001a993  mov     [rbp+arg_0], edx
0x18001a996  cmp     r15d, r13d
0x18001a999  jb      short loc_18001A955
0x18001a99b  mov     rcx, [rdi+60h]; hDevice
0x18001a99f  lea     rax, [rbp+BytesReturned]
0x18001a9a3  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18001a9ac  mov     r9d, r12d; nInBufferSize
0x18001a9af  mov     [rsp+58h+lpBytesReturned], rax; lpBytesReturned
0x18001a9b4  mov     r8, r14; lpInBuffer
0x18001a9b7  mov     [rsp+58h+nOutBufferSize], 0; nOutBufferSize
0x18001a9bf  mov     edx, 2F0428h; dwIoControlCode
0x18001a9c4  mov     [rsp+58h+lpOutBuffer], 0; lpOutBuffer
0x18001a9cd  call    cs:__imp_DeviceIoControl
0x18001a9d3  test    eax, eax
0x18001a9d5  jnz     short loc_18001AA1C
0x18001a9d7  call    cs:__imp_GetLastError
0x18001a9dd  mov     esi, eax
0x18001a9df  test    eax, eax
0x18001a9e1  jle     short loc_18001A9EC
0x18001a9e3  movzx   esi, ax
0x18001a9e6  or      esi, 80070000h
0x18001a9ec  test    esi, esi
0x18001a9ee  jns     short loc_18001AA1C
0x18001a9f0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a9f7  jb      short loc_18001AA1C
0x18001a9f9  mov     edx, 52h ; 'R'
0x18001a9fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa05  lea     r8, WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids
0x18001aa0c  mov     r9, rdi
0x18001aa0f  mov     dword ptr [rsp+58h+lpOutBuffer], esi
0x18001aa13  mov     rcx, [rcx+10h]
0x18001aa17  call    WPP_SF_qD
0x18001aa1c  cmp     byte ptr [rdi+0A8h], 0
0x18001aa23  jz      short loc_18001AA65
0x18001aa25  cmp     dword ptr [rdi+98h], 0
0x18001aa2c  jnz     short loc_18001AA65
0x18001aa2e  mov     rcx, [rdi+90h]; this
0x18001aa35  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18001aa3a  cmp     cs:byte_18010EC4D, 8
0x18001aa41  jb      short loc_18001AA65
0x18001aa43  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa4a  lea     r8, WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids
0x18001aa51  mov     edx, 53h ; 'S'
0x18001aa56  mov     r9, rdi
0x18001aa59  mov     rcx, [rcx+0D8h]
0x18001aa60  call    WPP_SF_q
0x18001aa65  mov     ecx, 80000000h
0x18001aa6a  lea     eax, [rsi+rcx]
0x18001aa6d  test    ecx, eax
0x18001aa6f  jnz     short loc_18001AAAF
0x18001aa71  cmp     esi, 8007000Eh
0x18001aa77  jz      short loc_18001AAAF
0x18001aa79  cmp     cs:byte_18010EC4D, 8
0x18001aa80  jb      short loc_18001AAAF
0x18001aa82  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa89  mov     r9, rdi
0x18001aa8c  mov     rax, [rdi+60h]
0x18001aa90  mov     [rsp+58h+lpOverlapped], r14
0x18001aa95  mov     dword ptr [rsp+58h+lpBytesReturned], r12d
0x18001aa9a  mov     rcx, [rcx+0D8h]
0x18001aaa1  mov     qword ptr [rsp+58h+nOutBufferSize], rax
0x18001aaa6  mov     dword ptr [rsp+58h+lpOutBuffer], esi
0x18001aaaa  call    WPP_SF_qDqdq
0x18001aaaf  lea     rcx, [rbp+lpInBuffer]
0x18001aab3  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18001aab8  lea     rcx, [rdi+68h]; lpCriticalSection
0x18001aabc  call    cs:__imp_LeaveCriticalSection
0x18001aac2  add     rsp, 58h
0x18001aac6  pop     r15
0x18001aac8  pop     r14
0x18001aaca  pop     r13
0x18001aacc  pop     r12
0x18001aace  pop     rdi
0x18001aacf  pop     rsi
0x18001aad0  pop     rbx
0x18001aad1  pop     rbp
0x18001aad2  retn
```
