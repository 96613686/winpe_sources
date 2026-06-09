# CallAudioRouting::_StartRecordingCreateAudioFile(uint,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,Microsoft::WRL::ComPtr<Windows::Storage::IStorageFolder> const &,int,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)

- ea: `0x180069efc`
- end: `0x18006a3cc`
- name: `?_StartRecordingCreateAudioFile@CallAudioRouting@@AEAAJIAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEBV?$ComPtr@UIStorageFolder@Storage@Windows@@@WRL@Microsoft@@H00@Z`
- size: `1232`
- prototype: `__int64 __usercall@<rax>(CallAudioRouting *this@<rcx>, unsigned int@<edx>, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18006b2c0`

## callees

- `0x180006e94`
- `0x180057acc`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x180063a78`
- `0x180064dac`
- `0x180066eb4`
- `0x180069efc`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a053`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a053`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a08a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a102`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a185`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a08a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a102`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a185`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069f48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069f69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069f48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069f69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006a040`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006a040`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a02a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a1fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a2fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a366`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a02a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a1fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a2fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a366`

## string_xrefs

- `0x180069f5d`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180069fd7`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006a074`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006a0f1`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006a1e3`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006a2b5`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006a34e`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_StartRecordingCreateAudioFile(
        CallAudioRouting *this,
        unsigned int a2,
        unsigned __int16 **a3,
        __int64 *a4)
{
  __int64 v7; // rcx
  unsigned __int64 v8; // rdi
  int RecordingFileName; // eax
  BackTraceCollection *v10; // rcx
  unsigned int v11; // esi
  unsigned __int64 v12; // rsi
  int v13; // eax
  BackTraceCollection *v14; // rcx
  __int64 v15; // rcx
  BackTraceCollection *v16; // rcx
  __int64 v17; // r9
  __int64 v18; // rdx
  WCHAR *v19; // r9
  BackTraceCollection *v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rdx
  BackTraceCollection *v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rbx
  __int64 (__fastcall *v26)(__int64, HSTRING, __int64, __int64 *); // rsi
  int v27; // eax
  BackTraceCollection *v28; // rcx
  unsigned int v29; // ebx
  __int64 v30; // rcx
  struct CallAudioRouting::CellularAudioState *v32; // rbx
  int v33; // eax
  BackTraceCollection *v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  struct CallAudioRouting::CellularAudioState *v37; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v38; // [rsp+48h] [rbp-B8h]
  CallAudioRouting *v39; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v40; // [rsp+58h] [rbp-A8h]
  unsigned int v41; // [rsp+60h] [rbp-A0h]
  __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  WCHAR sourceString[264]; // [rsp+80h] [rbp-80h] BYREF

  v38 = a4;
  if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v7, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1967);
    if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v8 = ((unsigned __int64)this + 8) & -(__int64)(this != 0);
  if ( v8 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v8 + 8LL))(((unsigned __int64)this + 8) & -(__int64)(this != 0));
  RecordingFileName = CallAudioRouting::_GetRecordingFileName(this, *a3, sourceString);
  v11 = RecordingFileName;
  if ( RecordingFileName < 0 )
  {
    BackTraceCollection::Capture(v10, RecordingFileName);
    Log_HREvent_17(v11, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1973);
    goto LABEL_8;
  }
  v42 = 0;
  string = 0;
  v12 = -1;
  do
    ++v12;
  while ( sourceString[v12] );
  if ( v12 > 0xFFFFFFFF )
  {
    v11 = -2147024362;
    goto LABEL_52;
  }
  WindowsDeleteString(0);
  string = 0;
  v11 = WindowsCreateString(sourceString, v12, &string);
  if ( (v11 & 0x80000000) != 0 )
  {
LABEL_52:
    BackTraceCollection::Capture(v10, v11);
    Log_HREvent_17(v11, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1977);
LABEL_53:
    WindowsDeleteString(string);
    v36 = v42;
    string = 0;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    if ( !v8 )
      return v11;
    goto LABEL_56;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v13 = CallAudioRouting::_CheckShutdown(this);
  v11 = v13;
  if ( v13 < 0 )
  {
    BackTraceCollection::Capture(v14, v13);
    Log_HREvent_17(v11, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1981);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
LABEL_16:
    WindowsDeleteString(string);
    v15 = v42;
    string = 0;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
LABEL_8:
    if ( !v8 )
      return v11;
LABEL_56:
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v8 + 16LL))(((unsigned __int64)this + 8) & -(__int64)(this != 0));
    return v11;
  }
  v37 = 0;
  if ( !(unsigned int)CallAudioRouting::_FindCellularState(this, a2, &v37) )
  {
    v11 = -2147023728;
    BackTraceCollection::Capture(v16, -2147023728);
    v17 = 1984;
    v18 = 0;
LABEL_20:
    Log_HREvent_17(v11, v18, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v17);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    goto LABEL_53;
  }
  v19 = sourceString;
  v20 = (struct CallAudioRouting::CellularAudioState *)((char *)v37 + 664);
  v21 = 2147483646;
  v22 = 260;
  do
  {
    if ( !v21 )
      break;
    if ( !*v19 )
      break;
    *(_WORD *)v20 = *v19++;
    v20 = (BackTraceCollection *)((char *)v20 + 2);
    --v21;
    --v22;
  }
  while ( v22 );
  v23 = (BackTraceCollection *)((char *)v20 - 2);
  v11 = v22 == 0 ? 0x8007007A : 0;
  if ( v22 )
    v23 = v20;
  *(_WORD *)v23 = 0;
  if ( !v22 )
  {
    BackTraceCollection::Capture(v23, v11);
    v17 = 1986;
    v18 = 1;
    goto LABEL_20;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v24 = v42;
  v25 = *v38;
  v26 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, __int64 *))(*(_QWORD *)*v38 + 56LL);
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v27 = v26(v25, string, 1, &v42);
  v29 = v27;
  if ( v27 >= 0 )
  {
    v37 = 0;
    v39 = this;
    v40 = ((unsigned __int64)this + 8) & -(__int64)(this != 0);
    if ( v8 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v8 + 8LL))(((unsigned __int64)this + 8) & -(__int64)(this != 0));
    v41 = a2;
    Microsoft::WRL::Callback_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Storage::StorageFile_____lambda_67a6c80ca531f3b70a6d549723b6730f___(
      &v37,
      &v39);
    if ( v40 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v40 + 16LL))(v40);
    v32 = v37;
    v33 = (*(__int64 (__fastcall **)(__int64, struct CallAudioRouting::CellularAudioState *))(*(_QWORD *)v42 + 48LL))(
            v42,
            v37);
    v11 = v33;
    if ( v33 < 0 )
    {
      BackTraceCollection::Capture(v34, v33);
      Log_HREvent_17(v11, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2024);
      if ( v32 )
        (*(void (__fastcall **)(struct CallAudioRouting::CellularAudioState *))(*(_QWORD *)v32 + 16LL))(v32);
      goto LABEL_16;
    }
    if ( v32 )
      (*(void (__fastcall **)(struct CallAudioRouting::CellularAudioState *))(*(_QWORD *)v32 + 16LL))(v32);
    WindowsDeleteString(string);
    v35 = v42;
    string = 0;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    if ( v8 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v8 + 16LL))(((unsigned __int64)this + 8) & -(__int64)(this != 0));
    return 0;
  }
  else
  {
    BackTraceCollection::Capture(v28, v27);
    Log_HREvent_17(v29, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1989);
    WindowsDeleteString(string);
    v30 = v42;
    string = 0;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    if ( v8 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v8 + 16LL))(((unsigned __int64)this + 8) & -(__int64)(this != 0));
    return v29;
  }
}

```

## disassembly

```asm
0x180069efc  mov     [rsp-8+arg_8], rbx
0x180069f01  push    rbp
0x180069f02  push    rsi
0x180069f03  push    rdi
0x180069f04  push    r12
0x180069f06  push    r13
0x180069f08  push    r14
0x180069f0a  push    r15
0x180069f0c  lea     rbp, [rsp-1A0h]
0x180069f14  sub     rsp, 2A0h
0x180069f1b  mov     rax, cs:__security_cookie
0x180069f22  xor     rax, rsp
0x180069f25  mov     [rbp+1D0h+var_40], rax
0x180069f2c  mov     r15, [rbp+1D0h+arg_28]
0x180069f33  mov     rsi, r8
0x180069f36  mov     r12, [rbp+1D0h+arg_30]
0x180069f3d  mov     r13d, edx
0x180069f40  mov     [rsp+2D0h+var_288], r9
0x180069f45  mov     r14, rcx
0x180069f48  call    cs:__imp_GetCurrentThreadId
0x180069f4e  lea     rbx, [r14+58h]
0x180069f52  cmp     [rbx+10h], eax
0x180069f55  jnz     short loc_180069F7A
0x180069f57  mov     r8d, 7AFh
0x180069f5d  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180069f64  call    Log_AssertionEvent_9
0x180069f69  call    cs:__imp_GetCurrentThreadId
0x180069f6f  cmp     [r14+68h], eax
0x180069f73  jnz     short loc_180069F7A
0x180069f75  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180069f7a  mov     rax, r14
0x180069f7d  lea     rcx, [r14+8]
0x180069f81  neg     rax
0x180069f84  sbb     rdi, rdi
0x180069f87  and     rdi, rcx
0x180069f8a  jz      short loc_180069F9B
0x180069f8c  mov     rax, [rdi]
0x180069f8f  mov     rcx, rdi
0x180069f92  mov     rax, [rax+8]
0x180069f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069f9b  mov     r9d, [rbp+1D0h+arg_20]
0x180069fa2  lea     rax, [rbp+1D0h+sourceString]
0x180069fa6  mov     [rsp+2D0h+var_2A8], rax; LPWSTR
0x180069fab  mov     r8, r12
0x180069fae  mov     rax, [rsi]
0x180069fb1  mov     rdx, r15
0x180069fb4  mov     rcx, r14; this
0x180069fb7  mov     [rsp+2D0h+var_2B0], rax; unsigned __int16 *
0x180069fbc  call    ?_GetRecordingFileName@CallAudioRouting@@AEAAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@0HPEBGPEAGI@Z; CallAudioRouting::_GetRecordingFileName(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,int,ushort const *,ushort *,uint)
0x180069fc1  xor     r15d, r15d
0x180069fc4  mov     esi, eax
0x180069fc6  test    eax, eax
0x180069fc8  jns     short loc_180069FFE
0x180069fca  mov     edx, eax; int
0x180069fcc  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180069fd1  mov     r9d, 7B5h
0x180069fd7  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180069fde  lea     edx, [r15+1]
0x180069fe2  mov     ecx, esi
0x180069fe4  call    Log_HREvent_17
0x180069fe9  test    rdi, rdi
0x180069fec  jz      loc_18006A3A0
0x180069ff2  mov     rax, [rdi]
0x180069ff5  mov     rax, [rax+10h]
0x180069ff9  jmp     loc_18006A398
0x180069ffe  mov     [rsp+2D0h+var_268], r15
0x18006a003  lea     rax, [rbp+1D0h+sourceString]
0x18006a007  mov     [rsp+2D0h+string], r15
0x18006a00c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006a010  inc     rsi
0x18006a013  cmp     [rax+rsi*2], r15w
0x18006a018  jnz     short loc_18006A010
0x18006a01a  mov     eax, 0FFFFFFFFh
0x18006a01f  cmp     rsi, rax
0x18006a022  ja      loc_18006A33C
0x18006a028  xor     ecx, ecx; string
0x18006a02a  call    cs:__imp_WindowsDeleteString
0x18006a030  mov     edx, esi; length
0x18006a032  mov     [rsp+2D0h+string], r15
0x18006a037  lea     r8, [rsp+2D0h+string]; string
0x18006a03c  lea     rcx, [rbp+1D0h+sourceString]; sourceString
0x18006a040  call    cs:__imp_WindowsCreateString
0x18006a046  mov     esi, eax
0x18006a048  test    eax, eax
0x18006a04a  js      loc_18006A341
0x18006a050  mov     rcx, rbx; lpCriticalSection
0x18006a053  call    cs:__imp_EnterCriticalSection
0x18006a059  mov     rcx, r14; this
0x18006a05c  call    ?_CheckShutdown@CallAudioRouting@@AEAAJXZ; CallAudioRouting::_CheckShutdown(void)
0x18006a061  mov     esi, eax
0x18006a063  test    eax, eax
0x18006a065  jns     short loc_18006A0C4
0x18006a067  mov     edx, eax; int
0x18006a069  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006a06e  mov     r9d, 7BDh
0x18006a074  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006a07b  mov     edx, 1
0x18006a080  mov     ecx, esi
0x18006a082  call    Log_HREvent_17
0x18006a087  mov     rcx, rbx; lpCriticalSection
0x18006a08a  call    cs:__imp_LeaveCriticalSection
0x18006a090  mov     rcx, [rsp+2D0h+string]; string
0x18006a095  call    cs:__imp_WindowsDeleteString
0x18006a09b  mov     rcx, [rsp+2D0h+var_268]
0x18006a0a0  mov     [rsp+2D0h+string], r15
0x18006a0a5  test    rcx, rcx
0x18006a0a8  jz      loc_180069FE9
0x18006a0ae  mov     [rsp+2D0h+var_268], r15
0x18006a0b3  mov     rax, [rcx]
0x18006a0b6  mov     rax, [rax+10h]
0x18006a0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a0bf  jmp     loc_180069FE9
0x18006a0c4  lea     r8, [rsp+2D0h+var_290]; struct CallAudioRouting::CellularAudioState **
0x18006a0c9  mov     [rsp+2D0h+var_290], r15
0x18006a0ce  mov     edx, r13d; unsigned int
0x18006a0d1  mov     rcx, r14; this
0x18006a0d4  call    ?_FindCellularState@CallAudioRouting@@AEAAHIPEAPEAUCellularAudioState@1@@Z; CallAudioRouting::_FindCellularState(uint,CallAudioRouting::CellularAudioState * *)
0x18006a0d9  test    eax, eax
0x18006a0db  jnz     short loc_18006A10D
0x18006a0dd  mov     esi, 80070490h
0x18006a0e2  mov     edx, esi; int
0x18006a0e4  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006a0e9  mov     r9d, 7C0h
0x18006a0ef  xor     edx, edx
0x18006a0f1  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006a0f8  mov     ecx, esi
0x18006a0fa  call    Log_HREvent_17
0x18006a0ff  mov     rcx, rbx; lpCriticalSection
0x18006a102  call    cs:__imp_LeaveCriticalSection
0x18006a108  jmp     loc_18006A361
0x18006a10d  mov     r8, [rsp+2D0h+var_290]
0x18006a112  lea     r9, [rbp+1D0h+sourceString]
0x18006a116  add     r8, 298h
0x18006a11d  mov     ecx, 7FFFFFFEh
0x18006a122  mov     edx, 104h
0x18006a127  test    rcx, rcx
0x18006a12a  jz      short loc_18006A14A
0x18006a12c  movzx   eax, word ptr [r9]
0x18006a130  test    ax, ax
0x18006a133  jz      short loc_18006A14A
0x18006a135  mov     [r8], ax
0x18006a139  add     r9, 2
0x18006a13d  add     r8, 2
0x18006a141  dec     rcx
0x18006a144  sub     rdx, 1
0x18006a148  jnz     short loc_18006A127
0x18006a14a  mov     rax, rdx
0x18006a14d  lea     rcx, [r8-2]
0x18006a151  neg     rax
0x18006a154  sbb     esi, esi
0x18006a156  not     esi
0x18006a158  and     esi, 8007007Ah
0x18006a15e  test    rdx, rdx
0x18006a161  cmovnz  rcx, r8; this
0x18006a165  mov     [rcx], r15w
0x18006a169  jnz     short loc_18006A182
0x18006a16b  mov     edx, esi; int
0x18006a16d  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006a172  mov     r9d, 7C2h
0x18006a178  mov     edx, 1
0x18006a17d  jmp     loc_18006A0F1
0x18006a182  mov     rcx, rbx; lpCriticalSection
0x18006a185  call    cs:__imp_LeaveCriticalSection
0x18006a18b  mov     rbx, [rsp+2D0h+var_288]
0x18006a190  mov     rcx, [rsp+2D0h+var_268]
0x18006a195  mov     rbx, [rbx]
0x18006a198  mov     rax, [rbx]
0x18006a19b  mov     rsi, [rax+38h]
0x18006a19f  test    rcx, rcx
0x18006a1a2  jz      short loc_18006A1B5
0x18006a1a4  mov     [rsp+2D0h+var_268], r15
0x18006a1a9  mov     rdx, [rcx]
0x18006a1ac  mov     rax, [rdx+10h]
0x18006a1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a1b5  mov     rdx, [rsp+2D0h+string]
0x18006a1ba  lea     r9, [rsp+2D0h+var_268]
0x18006a1bf  mov     r8d, 1
0x18006a1c5  mov     rcx, rbx
0x18006a1c8  mov     rax, rsi
0x18006a1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a1d0  mov     ebx, eax
0x18006a1d2  test    eax, eax
0x18006a1d4  jns     short loc_18006A23C
0x18006a1d6  mov     edx, eax; int
0x18006a1d8  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006a1dd  mov     r9d, 7C5h
0x18006a1e3  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006a1ea  mov     edx, 1
0x18006a1ef  mov     ecx, ebx
0x18006a1f1  call    Log_HREvent_17
0x18006a1f6  mov     rcx, [rsp+2D0h+string]; string
0x18006a1fb  call    cs:__imp_WindowsDeleteString
0x18006a201  mov     rcx, [rsp+2D0h+var_268]
0x18006a206  mov     [rsp+2D0h+string], r15
0x18006a20b  test    rcx, rcx
0x18006a20e  jz      short loc_18006A221
0x18006a210  mov     [rsp+2D0h+var_268], r15
0x18006a215  mov     rax, [rcx]
0x18006a218  mov     rax, [rax+10h]
0x18006a21c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a221  test    rdi, rdi
0x18006a224  jz      short loc_18006A235
0x18006a226  mov     rax, [rdi]
0x18006a229  mov     rcx, rdi
0x18006a22c  mov     rax, [rax+10h]
0x18006a230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a235  mov     eax, ebx
0x18006a237  jmp     loc_18006A3A2
0x18006a23c  mov     [rsp+2D0h+var_290], r15
0x18006a241  mov     [rsp+2D0h+var_280], r14
0x18006a246  mov     [rsp+2D0h+var_278], rdi
0x18006a24b  test    rdi, rdi
0x18006a24e  jz      short loc_18006A25F
0x18006a250  mov     rax, [rdi]
0x18006a253  mov     rcx, rdi
0x18006a256  mov     rax, [rax+8]
0x18006a25a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a25f  lea     rdx, [rsp+2D0h+var_280]
0x18006a264  mov     [rsp+2D0h+var_270], r13d
0x18006a269  lea     rcx, [rsp+2D0h+var_290]
0x18006a26e  call    Microsoft__WRL__Callback_Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Storage__StorageFile_____lambda_67a6c80ca531f3b70a6d549723b6730f___
0x18006a273  mov     rcx, [rsp+2D0h+var_278]
0x18006a278  test    rcx, rcx
0x18006a27b  jz      short loc_18006A289
0x18006a27d  mov     rax, [rcx]
0x18006a280  mov     rax, [rax+10h]
0x18006a284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a289  mov     rcx, [rsp+2D0h+var_268]
0x18006a28e  mov     rbx, [rsp+2D0h+var_290]
0x18006a293  mov     rdx, rbx
0x18006a296  mov     rax, [rcx]
0x18006a299  mov     rax, [rax+30h]
0x18006a29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2a2  mov     esi, eax
0x18006a2a4  test    eax, eax
0x18006a2a6  jns     short loc_18006A2E5
0x18006a2a8  mov     edx, eax; int
0x18006a2aa  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006a2af  mov     r9d, 7E8h
0x18006a2b5  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006a2bc  mov     edx, 1
0x18006a2c1  mov     ecx, esi
0x18006a2c3  call    Log_HREvent_17
0x18006a2c8  test    rbx, rbx
0x18006a2cb  jz      loc_18006A090
0x18006a2d1  mov     rax, [rbx]
0x18006a2d4  mov     rcx, rbx
0x18006a2d7  mov     rax, [rax+10h]
0x18006a2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2e0  jmp     loc_18006A090
0x18006a2e5  test    rbx, rbx
0x18006a2e8  jz      short loc_18006A2F9
0x18006a2ea  mov     rax, [rbx]
0x18006a2ed  mov     rcx, rbx
0x18006a2f0  mov     rax, [rax+10h]
0x18006a2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2f9  mov     rcx, [rsp+2D0h+string]; string
0x18006a2fe  call    cs:__imp_WindowsDeleteString
0x18006a304  mov     rcx, [rsp+2D0h+var_268]
0x18006a309  mov     [rsp+2D0h+string], r15
0x18006a30e  test    rcx, rcx
0x18006a311  jz      short loc_18006A324
0x18006a313  mov     [rsp+2D0h+var_268], r15
0x18006a318  mov     rax, [rcx]
0x18006a31b  mov     rax, [rax+10h]
0x18006a31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a324  test    rdi, rdi
0x18006a327  jz      short loc_18006A338
0x18006a329  mov     rax, [rdi]
0x18006a32c  mov     rcx, rdi
0x18006a32f  mov     rax, [rax+10h]
0x18006a333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a338  xor     eax, eax
0x18006a33a  jmp     short loc_18006A3A2
0x18006a33c  mov     esi, 80070216h
0x18006a341  mov     edx, esi; int
0x18006a343  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006a348  mov     r9d, 7B9h
0x18006a34e  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006a355  mov     edx, 1
0x18006a35a  mov     ecx, esi
0x18006a35c  call    Log_HREvent_17
0x18006a361  mov     rcx, [rsp+2D0h+string]; string
0x18006a366  call    cs:__imp_WindowsDeleteString
0x18006a36c  mov     rcx, [rsp+2D0h+var_268]
0x18006a371  mov     [rsp+2D0h+string], r15
0x18006a376  test    rcx, rcx
0x18006a379  jz      short loc_18006A38C
0x18006a37b  mov     [rsp+2D0h+var_268], r15
0x18006a380  mov     rax, [rcx]
0x18006a383  mov     rax, [rax+10h]
0x18006a387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a38c  test    rdi, rdi
0x18006a38f  jz      short loc_18006A3A0
0x18006a391  mov     rcx, [rdi]
0x18006a394  mov     rax, [rcx+10h]
0x18006a398  mov     rcx, rdi
0x18006a39b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a3a0  mov     eax, esi
0x18006a3a2  mov     rcx, [rbp+1D0h+var_40]
  ... truncated ...
```
