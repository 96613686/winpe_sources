# CTnoCfgMgr::Start(TnoStartContext const *,void *)

- ea: `0x180026c60`
- end: `0x18002705b`
- name: `?Start@CTnoCfgMgr@@UEAAJPEBUTnoStartContext@@PEAX@Z`
- size: `1019`
- prototype: `__int64 __fastcall(CTnoCfgMgr *__hidden this, const struct TnoStartContext *, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180004374`
- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x180018efc`
- `0x180020278`
- `0x18002200c`
- `0x18002314c`
- `0x180026c60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180026e02`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180026e02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f12`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180026daf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180026daf`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180026e83`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180026e83`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTnoCfgMgr::Start(CTnoCfgMgr *this, const struct TnoStartContext *a2, void *a3)
{
  _DWORD *v5; // r13
  __int64 v6; // r9
  int PolicyDll; // eax
  int v8; // r14d
  HANDLE Thread; // r15
  __int64 v10; // rdx
  DWORD v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  int LastError; // eax
  signed int v15; // ebx
  __int64 result; // rax
  DWORD v17; // eax
  struct CritSec *v18; // [rsp+30h] [rbp-68h]
  _DWORD *v19; // [rsp+38h] [rbp-60h]
  Exception *v20; // [rsp+40h] [rbp-58h] BYREF
  __int128 Handles; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v22[64]; // [rsp+58h] [rbp-40h] BYREF
  DWORD ExitCode; // [rsp+B8h] [rbp+20h] BYREF

  ExitCode = 0;
  Handles = 0;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 21, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids);
  }
  v18 = (CTnoCfgMgr *)((char *)this - 48);
  InCritSec::InCritSec((InCritSec *)v22, (CTnoCfgMgr *)((char *)this - 48), 1);
  try
  {
    v5 = (_DWORD *)((char *)this + 16);
    v19 = (_DWORD *)((char *)this + 16);
    v6 = *((unsigned int *)this + 4);
    if ( (((_DWORD)v6 - 1) & 0xFFFFFFFA) != 0 || (_DWORD)v6 == 2 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 22, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids, v6);
      }
      SystemError::ThrowHelper(L"CTnoCfgMgr::Start", -2147020841);
    }
    *v5 = 2;
    PolicyDll = CTnoCfgMgr::LoadPolicyDll((CTnoCfgMgr *)((char *)this - 48));
    v8 = PolicyDll;
    if ( PolicyDll < 0 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 105) )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            23,
            WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids,
            (unsigned int)PolicyDll);
      }
      SystemError::ThrowHelper(L"CTnoCfgMgr::Start", v8);
    }
    InCritSec::~InCritSec((InCritSec *)v22);
    if ( !a2 || (*((_QWORD *)this + 44) = *((_QWORD *)a2 + 16), !*((_BYTE *)a2 + 157)) )
    {
      Thread = CreateThread(0, 0, CTnoCfgMgr::StaticWorkerThreadProc, (char *)this - 48, 0, (LPDWORD)this + 5);
      ObjectHandle::Close((CTnoCfgMgr *)((char *)this + 248));
      *((_QWORD *)this + 32) = Thread;
      v10 = *((_QWORD *)this + 32);
      if ( (unsigned __int64)(v10 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        v15 = LastError;
        ExitCode = LastError;
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            24,
            WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids,
            (unsigned int)v15);
        }
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        SystemError::ThrowHelper(L"CTnoCfgMgr::Start", v15);
      }
      *(_QWORD *)&Handles = *((_QWORD *)this + 29);
      *((_QWORD *)&Handles + 1) = v10;
      v11 = WaitForMultipleObjectsEx(2u, (const HANDLE *)&Handles, 0, 0xFFFFFFFF, 0);
      ExitCode = v11;
      if ( v11 )
      {
        if ( v11 == 1 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 25, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids);
          }
          if ( GetExitCodeThread(*((HANDLE *)this + 32), &ExitCode) )
            v12 = ExitCode;
          else
            v12 = GetLastError();
          if ( v12 > 0 )
            v12 = (unsigned __int16)v12 | 0x80070000;
          SystemError::ThrowHelper(L"CTnoCfgMgr::Start", v12);
        }
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 26, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids);
        }
        v13 = GetLastError();
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        SystemError::ThrowHelper(L"CTnoCfgMgr::Start", v13);
      }
      ExitCode = 0;
    }
    InCritSec::InCritSec((InCritSec *)v22, (CTnoCfgMgr *)((char *)this - 48), 1);
    *v5 = 3;
    InCritSec::~InCritSec((InCritSec *)v22);
  }
  catch ( Exception *v20 )
  {
    *((_DWORD *)this + 4) = 5;
    v17 = (*(__int64 (__fastcall **)(Exception *))(*(_QWORD *)v20 + 16LL))(v20);
    ExitCode = v17;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 27, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids, v17);
    }
  }
  catch ( std::bad_alloc )
  {
    *((_DWORD *)this + 4) = 6;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 28, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids);
    }
    ExitCode = 8;
  }
  catch ( ... )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 29, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids);
    }
    ExitCode = 774;
  }
  InCritSec::InCritSec((InCritSec *)v22, v18, 1);
  if ( *v19 != 3 )
    CTnoCfgMgr::FreePolicyLibrary(v18);
  InCritSec::~InCritSec((InCritSec *)v22);
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 30, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids, ExitCode);
  }
  result = ExitCode;
  if ( (int)ExitCode > 0 )
    return (unsigned __int16)ExitCode | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180026c60  mov     rax, rsp
0x180026c63  mov     [rax+10h], rbx
0x180026c67  mov     [rax+8], rcx
0x180026c6b  push    rsi
0x180026c6c  push    r12
0x180026c6e  push    r13
0x180026c70  push    r14
0x180026c72  push    r15
0x180026c74  sub     rsp, 70h
0x180026c78  mov     r15, rdx
0x180026c7b  mov     rbx, rcx
0x180026c7e  mov     dword ptr [rax+20h], 0
0x180026c85  xorps   xmm0, xmm0
0x180026c88  movups  xmmword ptr [rax-50h], xmm0
0x180026c8c  lea     rsi, WPP_GLOBAL_Control
0x180026c93  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c9a  cmp     rcx, rsi
0x180026c9d  jz      short loc_180026CC4
0x180026c9f  test    dword ptr [rcx+6Ch], 200h
0x180026ca6  jz      short loc_180026CC4
0x180026ca8  cmp     byte ptr [rcx+69h], 4
0x180026cac  jb      short loc_180026CC4
0x180026cae  mov     edx, 15h
0x180026cb3  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x180026cba  mov     rcx, [rcx+60h]
0x180026cbe  call    WPP_SF_
0x180026cc3  nop
0x180026cc4  lea     r12, [rbx-30h]
0x180026cc8  mov     [rsp+98h+var_68], r12
0x180026ccd  mov     r8b, 1; bool
0x180026cd0  mov     rdx, r12; struct CritSec *
0x180026cd3  lea     rcx, [rsp+98h+var_40]; this
0x180026cd8  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x180026cdd  nop
0x180026cde  lea     r13, [rbx+10h]
0x180026ce2  mov     [rsp+98h+var_60], r13
0x180026ce7  mov     r9d, [r13+0]
0x180026ceb  lea     eax, [r9-1]
0x180026cef  test    eax, 0FFFFFFFAh
0x180026cf4  jnz     loc_180026F7D
0x180026cfa  cmp     r9d, 2
0x180026cfe  jz      loc_180026F7D
0x180026d04  mov     dword ptr [r13+0], 2
0x180026d0c  mov     rcx, r12; this
0x180026d0f  call    ?LoadPolicyDll@CTnoCfgMgr@@AEAAJXZ; CTnoCfgMgr::LoadPolicyDll(void)
0x180026d14  mov     r14d, eax
0x180026d17  test    eax, eax
0x180026d19  jns     short loc_180026D5E
0x180026d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d22  cmp     rcx, rsi
0x180026d25  jz      short loc_180026D4E
0x180026d27  test    dword ptr [rcx+6Ch], 200h
0x180026d2e  jz      short loc_180026D4E
0x180026d30  cmp     byte ptr [rcx+69h], 1
0x180026d34  jb      short loc_180026D4E
0x180026d36  mov     edx, 17h
0x180026d3b  mov     r9d, eax
0x180026d3e  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x180026d45  mov     rcx, [rcx+60h]
0x180026d49  call    WPP_SF_d
0x180026d4e  mov     edx, r14d; int
0x180026d51  lea     rcx, aCtnocfgmgrStar; "CTnoCfgMgr::Start"
0x180026d58  call    ?ThrowHelper@SystemError@@CAXPEBGJ@Z; SystemError::ThrowHelper(ushort const *,long)
0x180026d5e  lea     rcx, [rsp+98h+var_40]; this
0x180026d63  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x180026d68  test    r15, r15
0x180026d6b  jz      short loc_180026D89
0x180026d6d  mov     rax, [r15+80h]
0x180026d74  mov     [rbx+160h], rax
0x180026d7b  cmp     byte ptr [r15+9Dh], 0
0x180026d83  jnz     loc_180026E1A
0x180026d89  lea     r14, [rbx+0F8h]
0x180026d90  lea     rax, [rbx+14h]
0x180026d94  mov     [rsp+98h+lpThreadId], rax; lpThreadId
0x180026d99  mov     [rsp+98h+dwCreationFlags], 0; dwCreationFlags
0x180026da1  mov     r9, r12; lpParameter
0x180026da4  lea     r8, ?StaticWorkerThreadProc@CTnoCfgMgr@@CAKPEAX@Z; lpStartAddress
0x180026dab  xor     edx, edx; dwStackSize
0x180026dad  xor     ecx, ecx; lpThreadAttributes
0x180026daf  call    cs:__imp_CreateThread
0x180026db5  mov     r15, rax
0x180026db8  mov     rcx, r14; this
0x180026dbb  call    ?Close@ObjectHandle@@QEAAXXZ; ObjectHandle::Close(void)
0x180026dc0  mov     [r14+8], r15
0x180026dc4  mov     rdx, [rbx+100h]
0x180026dcb  lea     rax, [rdx-1]
0x180026dcf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026dd3  ja      loc_180026F12
0x180026dd9  mov     rax, [rbx+0E8h]
0x180026de0  mov     [rsp+98h+Handles], rax
0x180026de5  mov     [rsp+98h+var_48], rdx
0x180026dea  mov     [rsp+98h+dwCreationFlags], 0; bAlertable
0x180026df2  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180026df6  xor     r8d, r8d; bWaitAll
0x180026df9  lea     rdx, [rsp+98h+Handles]; lpHandles
0x180026dfe  lea     ecx, [r8+2]; nCount
0x180026e02  call    cs:__imp_WaitForMultipleObjectsEx
0x180026e08  mov     [rsp+98h+ExitCode], eax
0x180026e0f  test    eax, eax
0x180026e11  jnz     short loc_180026E42
0x180026e13  mov     [rsp+98h+ExitCode], eax
0x180026e1a  mov     r8b, 1; bool
0x180026e1d  mov     rdx, r12; struct CritSec *
0x180026e20  lea     rcx, [rsp+98h+var_40]; this
0x180026e25  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x180026e2a  mov     dword ptr [r13+0], 3
0x180026e32  lea     rcx, [rsp+98h+var_40]; this
0x180026e37  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x180026e3c  nop
0x180026e3d  jmp     loc_180026FCA
0x180026e42  cmp     eax, 1
0x180026e45  jnz     short loc_180026EC2
0x180026e47  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e4e  cmp     rcx, rsi
0x180026e51  jz      short loc_180026E74
0x180026e53  test    dword ptr [rcx+6Ch], 200h
0x180026e5a  jz      short loc_180026E74
0x180026e5c  cmp     [rcx+69h], al
0x180026e5f  jb      short loc_180026E74
0x180026e61  lea     edx, [rax+18h]
0x180026e64  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x180026e6b  mov     rcx, [rcx+60h]
0x180026e6f  call    WPP_SF_
0x180026e74  lea     rdx, [rsp+98h+ExitCode]; lpExitCode
0x180026e7c  mov     rcx, [rbx+100h]; hThread
0x180026e83  call    cs:__imp_GetExitCodeThread
0x180026e89  test    eax, eax
0x180026e8b  jz      short loc_180026E96
0x180026e8d  mov     eax, [rsp+98h+ExitCode]
0x180026e94  jmp     short loc_180026E9C
0x180026e96  call    cs:__imp_GetLastError
0x180026e9c  test    eax, eax
0x180026e9e  jle     short loc_180026EB4
0x180026ea0  movzx   eax, ax
0x180026ea3  or      eax, 80070000h
0x180026ea8  test    eax, eax
0x180026eaa  jle     short loc_180026EB4
0x180026eac  movzx   eax, ax
0x180026eaf  or      eax, 80070000h
0x180026eb4  mov     edx, eax; int
0x180026eb6  lea     rcx, aCtnocfgmgrStar; "CTnoCfgMgr::Start"
0x180026ebd  call    ?ThrowHelper@SystemError@@CAXPEBGJ@Z; SystemError::ThrowHelper(ushort const *,long)
0x180026ec2  mov     rcx, cs:WPP_GLOBAL_Control
0x180026ec9  cmp     rcx, rsi
0x180026ecc  jz      short loc_180026EF2
0x180026ece  test    dword ptr [rcx+6Ch], 200h
0x180026ed5  jz      short loc_180026EF2
0x180026ed7  cmp     byte ptr [rcx+69h], 1
0x180026edb  jb      short loc_180026EF2
0x180026edd  mov     edx, 1Ah
0x180026ee2  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x180026ee9  mov     rcx, [rcx+60h]
0x180026eed  call    WPP_SF_
0x180026ef2  call    cs:__imp_GetLastError
0x180026ef8  test    eax, eax
0x180026efa  jle     short loc_180026F04
0x180026efc  movzx   eax, ax
0x180026eff  or      eax, 80070000h
0x180026f04  mov     edx, eax; int
0x180026f06  lea     rcx, aCtnocfgmgrStar; "CTnoCfgMgr::Start"
0x180026f0d  call    ?ThrowHelper@SystemError@@CAXPEBGJ@Z; SystemError::ThrowHelper(ushort const *,long)
0x180026f12  call    cs:__imp_GetLastError
0x180026f18  mov     ebx, eax
0x180026f1a  mov     [rsp+98h+ExitCode], eax
0x180026f21  test    eax, eax
0x180026f23  jle     short loc_180026F2E
0x180026f25  movzx   ebx, ax
0x180026f28  or      ebx, 80070000h
0x180026f2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f35  cmp     rcx, rsi
0x180026f38  jz      short loc_180026F61
0x180026f3a  test    dword ptr [rcx+6Ch], 200h
0x180026f41  jz      short loc_180026F61
0x180026f43  cmp     byte ptr [rcx+69h], 1
0x180026f47  jb      short loc_180026F61
0x180026f49  mov     edx, 18h
0x180026f4e  mov     r9d, ebx
0x180026f51  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x180026f58  mov     rcx, [rcx+60h]
0x180026f5c  call    WPP_SF_d
0x180026f61  test    ebx, ebx
0x180026f63  jle     short loc_180026F6E
0x180026f65  movzx   ebx, bx
0x180026f68  or      ebx, 80070000h
0x180026f6e  mov     edx, ebx; int
0x180026f70  lea     rcx, aCtnocfgmgrStar; "CTnoCfgMgr::Start"
0x180026f77  call    ?ThrowHelper@SystemError@@CAXPEBGJ@Z; SystemError::ThrowHelper(ushort const *,long)
0x180026f7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f84  cmp     rcx, rsi
0x180026f87  jz      short loc_180026FAD
0x180026f89  test    dword ptr [rcx+6Ch], 200h
0x180026f90  jz      short loc_180026FAD
0x180026f92  cmp     byte ptr [rcx+69h], 1
0x180026f96  jb      short loc_180026FAD
0x180026f98  mov     edx, 16h
0x180026f9d  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x180026fa4  mov     rcx, [rcx+60h]
0x180026fa8  call    WPP_SF_d
0x180026fad  mov     edx, 80070FD7h; int
0x180026fb2  lea     rcx, aCtnocfgmgrStar; "CTnoCfgMgr::Start"
0x180026fb9  call    ?ThrowHelper@SystemError@@CAXPEBGJ@Z; SystemError::ThrowHelper(ushort const *,long)
0x180026fbf  jmp     short loc_180026FC3
0x180026fc1  jmp     short $+2
0x180026fc3  lea     rsi, WPP_GLOBAL_Control
0x180026fca  mov     r8b, 1; bool
0x180026fcd  mov     rdx, [rsp+98h+var_68]; struct CritSec *
0x180026fd2  lea     rcx, [rsp+98h+var_40]; this
0x180026fd7  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x180026fdc  mov     rax, [rsp+98h+var_60]
0x180026fe1  cmp     dword ptr [rax], 3
0x180026fe4  jz      short loc_180026FF0
0x180026fe6  mov     rcx, [rsp+98h+var_68]; this
0x180026feb  call    ?FreePolicyLibrary@CTnoCfgMgr@@AEAAXXZ; CTnoCfgMgr::FreePolicyLibrary(void)
0x180026ff0  lea     rcx, [rsp+98h+var_40]; this
0x180026ff5  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x180026ffa  mov     rcx, cs:WPP_GLOBAL_Control
0x180027001  cmp     rcx, rsi
0x180027004  jz      short loc_180027032
0x180027006  test    dword ptr [rcx+6Ch], 200h
0x18002700d  jz      short loc_180027032
0x18002700f  cmp     byte ptr [rcx+69h], 4
0x180027013  jb      short loc_180027032
0x180027015  mov     edx, 1Eh
0x18002701a  mov     r9d, [rsp+98h+ExitCode]
0x180027022  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x180027029  mov     rcx, [rcx+60h]
0x18002702d  call    WPP_SF_d
0x180027032  mov     eax, [rsp+98h+ExitCode]
0x180027039  test    eax, eax
0x18002703b  jle     short loc_180027045
0x18002703d  movzx   eax, ax
0x180027040  or      eax, 80070000h
0x180027045  mov     rbx, [rsp+98h+arg_8]
0x18002704d  add     rsp, 70h
0x180027051  pop     r15
0x180027053  pop     r14
0x180027055  pop     r13
0x180027057  pop     r12
0x180027059  pop     rsi
0x18002705a  retn
```
