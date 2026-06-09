# Windows::AI::IsolationEnvironment::ProvisionResult::get_Capabilities(uint *,HSTRING__ * * *)

- ea: `0x1800482b0`
- end: `0x1800483cf`
- name: `?get_Capabilities@ProvisionResult@IsolationEnvironment@AI@Windows@@UEAAJPEAIPEAPEAPEAUHSTRING__@@@Z`
- size: `287`
- prototype: `int(Windows::AI::IsolationEnvironment::ProvisionResult *__hidden this, unsigned int *, HSTRING **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a464`
- `0x18001355c`
- `0x1800482b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180048337`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180048379`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800483c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180048337`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180048379`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800483c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800483b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800483b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800482ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800482ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800483a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800483a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180048353`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180048353`

## string_xrefs

- `0x180048312`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\provisionresult.cpp`

## pseudocode

```c
__int64 __fastcall Windows::AI::IsolationEnvironment::ProvisionResult::get_Capabilities(
        Windows::AI::IsolationEnvironment::ProvisionResult *this,
        unsigned int *a2,
        HSTRING **a3)
{
  __int64 v6; // rbx
  HSTRING *v7; // rsi
  RTL_SRWLOCK *v8; // rcx
  __int64 v10; // rdi
  HRESULT v11; // ebp
  RTL_SRWLOCK *v12; // rcx
  __int64 i; // rbx
  RTL_SRWLOCK *v14; // rcx
  int v15; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  PSRWLOCK SRWLock; // [rsp+50h] [rbp+8h] BYREF

  checked_srwlock::lock_shared(this, &SRWLock);
  *a2 = 0;
  v6 = (__int64)(*((_QWORD *)this + 12) - *((_QWORD *)this + 11)) >> 3;
  if ( (_DWORD)v6 )
  {
    v7 = (HSTRING *)CoTaskMemAlloc(8LL * (unsigned int)v6);
    if ( v7 )
    {
      v10 = 0;
      while ( 1 )
      {
        v11 = WindowsDuplicateString(*(HSTRING *)(*((_QWORD *)this + 11) + 8 * v10), &v7[v10]);
        if ( v11 < 0 )
          break;
        v10 = (unsigned int)(v10 + 1);
        if ( (unsigned int)v10 >= (unsigned int)v6 )
        {
          *a2 = v6;
          *a3 = v7;
          goto LABEL_11;
        }
      }
      for ( i = 0; (unsigned int)i < (unsigned int)v10; i = (unsigned int)(i + 1) )
        WindowsDeleteString(v7[i]);
      CoTaskMemFree(v7);
      v14 = SRWLock;
      if ( SRWLock )
      {
        _InterlockedDecrement((volatile signed __int32 *)&SRWLock[1].Ptr + 1);
        ReleaseSRWLockShared(v14);
      }
      return (unsigned int)v11;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\provisionresult.cpp",
        (const char *)0x8007000ELL,
        v15);
      v8 = SRWLock;
      if ( SRWLock )
      {
        _InterlockedDecrement((volatile signed __int32 *)&SRWLock[1].Ptr + 1);
        ReleaseSRWLockShared(v8);
      }
      return 2147942414LL;
    }
  }
  else
  {
    *a3 = 0;
LABEL_11:
    v12 = SRWLock;
    if ( SRWLock )
    {
      _InterlockedDecrement((volatile signed __int32 *)&SRWLock[1].Ptr + 1);
      ReleaseSRWLockShared(v12);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800482b0  mov     [rsp+arg_8], rbx
0x1800482b5  mov     [rsp+arg_10], rbp
0x1800482ba  push    rsi
0x1800482bb  push    rdi
0x1800482bc  push    r13
0x1800482be  push    r14
0x1800482c0  push    r15; int
0x1800482c2  sub     rsp, 20h
0x1800482c6  mov     r15, rdx
0x1800482c9  mov     r14, r8
0x1800482cc  lea     rdx, [rsp+48h+SRWLock]
0x1800482d1  mov     r13, rcx
0x1800482d4  call    ?lock_shared@checked_srwlock@@QEAA?AV?$holder@USharedTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_shared(void)
0x1800482d9  mov     dword ptr [r15], 0
0x1800482e0  mov     rbx, [r13+60h]
0x1800482e4  sub     rbx, [r13+58h]
0x1800482e8  sar     rbx, 3
0x1800482ec  test    ebx, ebx
0x1800482ee  jnz     short loc_1800482F9
0x1800482f0  mov     qword ptr [r14], 0
0x1800482f7  jmp     short loc_18004836B
0x1800482f9  mov     ecx, ebx
0x1800482fb  shl     rcx, 3; cb
0x1800482ff  call    cs:__imp_CoTaskMemAlloc
0x180048305  mov     rsi, rax
0x180048308  test    rax, rax
0x18004830b  jnz     short loc_180048341
0x18004830d  mov     rcx, [rsp+48h]; this
0x180048312  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180048319  mov     ebx, 8007000Eh
0x18004831e  lea     edx, [rax+6Bh]; void *
0x180048321  mov     r9d, ebx; char *
0x180048324  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048329  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x18004832e  test    rcx, rcx
0x180048331  jz      short loc_18004833D
0x180048333  lock dec dword ptr [rcx+0Ch]
0x180048337  call    cs:__imp_ReleaseSRWLockShared
0x18004833d  mov     eax, ebx
0x18004833f  jmp     short loc_180048381
0x180048341  xor     edi, edi
0x180048343  test    ebx, ebx
0x180048345  jz      short loc_180048365
0x180048347  mov     rcx, [r13+58h]
0x18004834b  lea     rdx, [rsi+rdi*8]; newString
0x18004834f  mov     rcx, [rcx+rdi*8]; string
0x180048353  call    cs:__imp_WindowsDuplicateString
0x180048359  mov     ebp, eax
0x18004835b  test    eax, eax
0x18004835d  js      short loc_180048398
0x18004835f  inc     edi
0x180048361  cmp     edi, ebx
0x180048363  jb      short loc_180048347
0x180048365  mov     [r15], ebx
0x180048368  mov     [r14], rsi
0x18004836b  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x180048370  test    rcx, rcx
0x180048373  jz      short loc_18004837F
0x180048375  lock dec dword ptr [rcx+0Ch]
0x180048379  call    cs:__imp_ReleaseSRWLockShared
0x18004837f  xor     eax, eax
0x180048381  mov     rbx, [rsp+48h+arg_8]
0x180048386  mov     rbp, [rsp+48h+arg_10]
0x18004838b  add     rsp, 20h
0x18004838f  pop     r15
0x180048391  pop     r14
0x180048393  pop     r13
0x180048395  pop     rdi
0x180048396  pop     rsi
0x180048397  retn
0x180048398  xor     ebx, ebx
0x18004839a  test    edi, edi
0x18004839c  jz      short loc_1800483AE
0x18004839e  mov     rcx, [rsi+rbx*8]; string
0x1800483a2  call    cs:__imp_WindowsDeleteString
0x1800483a8  inc     ebx
0x1800483aa  cmp     ebx, edi
0x1800483ac  jb      short loc_18004839E
0x1800483ae  mov     rcx, rsi; pv
0x1800483b1  call    cs:__imp_CoTaskMemFree
0x1800483b7  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x1800483bc  test    rcx, rcx
0x1800483bf  jz      short loc_1800483CB
0x1800483c1  lock dec dword ptr [rcx+0Ch]
0x1800483c5  call    cs:__imp_ReleaseSRWLockShared
0x1800483cb  mov     eax, ebp
0x1800483cd  jmp     short loc_180048381
```
