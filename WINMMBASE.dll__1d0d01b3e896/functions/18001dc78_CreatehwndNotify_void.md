# CreatehwndNotify(void)

- ea: `0x18001dc78`
- end: `0x18001de81`
- name: `?CreatehwndNotify@@YAHXZ`
- size: `521`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180017d30`

## callees

- `0x180011d6c`
- `0x180011dac`
- `0x180012d08`
- `0x1800174ec`
- `0x18001db44`
- `0x18001db94`
- `0x18001dc78`
- `0x18001de88`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001dd81`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001dd81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dd8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001de59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dd8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001de59`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001de1d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001de1d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001dd4d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001dd4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ddbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ddbf`

## pseudocode

```c
_BOOL8 CreatehwndNotify(void)
{
  BOOL v0; // ebx
  DWORD v1; // eax
  HANDLE EventA; // r14
  HANDLE Thread; // rbx
  DWORD LastError; // eax
  struct _RTL_CRITICAL_SECTION *v6; // [rsp+30h] [rbp-38h] BYREF
  char v7; // [rsp+38h] [rbp-30h]

  v7 = 0;
  v6 = &mmwndCritSec;
  ATL::CCritSecLock::Lock((ATL::CCritSecLock *)&v6);
  if ( hwndNotify )
  {
    v0 = 1;
  }
  else if ( (unsigned int)CreateMMClass() )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_0c7fc82a53b231168ee6f0523baae1e5_Traceguids);
    }
    EventA = CreateEventA(0, 0, 0, 0);
    if ( EventA )
    {
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)mciwindow, EventA, 0, &mciWindowThreadId);
      CloseHandle(Thread);
      if ( Thread )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            &WPP_0c7fc82a53b231168ee6f0523baae1e5_Traceguids,
            mciWindowThreadId);
        }
        WaitForSingleObject(EventA, 0xFFFFFFFF);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            &WPP_0c7fc82a53b231168ee6f0523baae1e5_Traceguids,
            hwndNotify);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        LastError = GetLastError();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_0c7fc82a53b231168ee6f0523baae1e5_Traceguids, LastError);
      }
      CloseHandle(EventA);
    }
    v0 = hwndNotify != 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v1 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_0c7fc82a53b231168ee6f0523baae1e5_Traceguids, v1);
    }
    v0 = 0;
  }
  ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&v6);
  return v0;
}

```

## disassembly

```asm
0x18001dc78  push    rbx
0x18001dc7a  push    rsi
0x18001dc7b  push    rdi
0x18001dc7c  push    r14
0x18001dc7e  sub     rsp, 48h
0x18001dc82  lea     rax, ?mmwndCritSec@@3VCCriticalSection@ATL@@A; ATL::CCriticalSection mmwndCritSec
0x18001dc89  mov     [rsp+68h+var_30], 0
0x18001dc8e  lea     rcx, [rsp+68h+var_38]; this
0x18001dc93  mov     [rsp+68h+var_38], rax
0x18001dc98  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x18001dc9d  cmp     cs:?hwndNotify@@3PEAUHWND__@@EA, 0; HWND__ * hwndNotify
0x18001dca5  jz      short loc_18001DCB1
0x18001dca7  mov     ebx, 1
0x18001dcac  jmp     loc_18001DE6B
0x18001dcb1  call    ?CreateMMClass@@YAHXZ; CreateMMClass(void)
0x18001dcb6  test    eax, eax
0x18001dcb8  jnz     short loc_18001DD0B
0x18001dcba  mov     rax, cs:WPP_GLOBAL_Control
0x18001dcc1  lea     rsi, WPP_GLOBAL_Control
0x18001dcc8  cmp     rax, rsi
0x18001dccb  jz      short loc_18001DD04
0x18001dccd  mov     edi, 400000h
0x18001dcd2  test    [rax+1Ch], edi
0x18001dcd5  jz      short loc_18001DD04
0x18001dcd7  mov     ebx, 1
0x18001dcdc  cmp     [rax+19h], bl
0x18001dcdf  jb      short loc_18001DD04
0x18001dce1  call    cs:__imp_GetLastError
0x18001dce7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dcee  lea     edx, [rbx+0Ch]
0x18001dcf1  mov     r9d, eax
0x18001dcf4  lea     r8, WPP_0c7fc82a53b231168ee6f0523baae1e5_Traceguids
0x18001dcfb  mov     rcx, [rcx+10h]
0x18001dcff  call    WPP_SF_d
0x18001dd04  xor     ebx, ebx
0x18001dd06  jmp     loc_18001DE6B
0x18001dd0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dd12  lea     rsi, WPP_GLOBAL_Control
0x18001dd19  mov     edi, 400000h
0x18001dd1e  cmp     rcx, rsi
0x18001dd21  jz      short loc_18001DD43
0x18001dd23  test    [rcx+1Ch], edi
0x18001dd26  jz      short loc_18001DD43
0x18001dd28  cmp     byte ptr [rcx+19h], 4
0x18001dd2c  jb      short loc_18001DD43
0x18001dd2e  mov     rcx, [rcx+10h]
0x18001dd32  lea     r8, WPP_0c7fc82a53b231168ee6f0523baae1e5_Traceguids
0x18001dd39  mov     edx, 0Eh
0x18001dd3e  call    WPP_SF_
0x18001dd43  xor     r9d, r9d; lpName
0x18001dd46  xor     r8d, r8d; bInitialState
0x18001dd49  xor     edx, edx; bManualReset
0x18001dd4b  xor     ecx, ecx; lpEventAttributes
0x18001dd4d  call    cs:__imp_CreateEventA
0x18001dd53  mov     r14, rax
0x18001dd56  test    rax, rax
0x18001dd59  jz      loc_18001DE5F
0x18001dd5f  lea     rax, ?mciWindowThreadId@@3KA; ulong mciWindowThreadId
0x18001dd66  mov     r9, r14; lpParameter
0x18001dd69  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x18001dd6e  lea     r8, ?mciwindow@@YAXPEAX@Z; lpStartAddress
0x18001dd75  xor     edx, edx; dwStackSize
0x18001dd77  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18001dd7f  xor     ecx, ecx; lpThreadAttributes
0x18001dd81  call    cs:__imp_CreateThread
0x18001dd87  mov     rcx, rax; hObject
0x18001dd8a  mov     rbx, rax
0x18001dd8d  call    cs:__imp_CloseHandle
0x18001dd93  test    rbx, rbx
0x18001dd96  jnz     short loc_18001DDE4
0x18001dd98  mov     rax, cs:WPP_GLOBAL_Control
0x18001dd9f  cmp     rax, rsi
0x18001dda2  jz      loc_18001DE56
0x18001dda8  test    [rax+1Ch], edi
0x18001ddab  jz      loc_18001DE56
0x18001ddb1  mov     ebx, 1
0x18001ddb6  cmp     [rax+19h], bl
0x18001ddb9  jb      loc_18001DE56
0x18001ddbf  call    cs:__imp_GetLastError
0x18001ddc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ddcc  lea     edx, [rbx+0Eh]
0x18001ddcf  mov     r9d, eax
0x18001ddd2  lea     r8, WPP_0c7fc82a53b231168ee6f0523baae1e5_Traceguids
0x18001ddd9  mov     rcx, [rcx+10h]
0x18001dddd  call    WPP_SF_D
0x18001dde2  jmp     short loc_18001DE56
0x18001dde4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ddeb  cmp     rcx, rsi
0x18001ddee  jz      short loc_18001DE17
0x18001ddf0  test    [rcx+1Ch], edi
0x18001ddf3  jz      short loc_18001DE17
0x18001ddf5  cmp     byte ptr [rcx+19h], 3
0x18001ddf9  jb      short loc_18001DE17
0x18001ddfb  mov     r9d, cs:?mciWindowThreadId@@3KA; ulong mciWindowThreadId
0x18001de02  lea     r8, WPP_0c7fc82a53b231168ee6f0523baae1e5_Traceguids
0x18001de09  mov     rcx, [rcx+10h]
0x18001de0d  mov     edx, 10h
0x18001de12  call    WPP_SF_D
0x18001de17  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001de1a  mov     rcx, r14; hHandle
0x18001de1d  call    cs:__imp_WaitForSingleObject
0x18001de23  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de2a  cmp     rcx, rsi
0x18001de2d  jz      short loc_18001DE56
0x18001de2f  test    [rcx+1Ch], edi
0x18001de32  jz      short loc_18001DE56
0x18001de34  cmp     byte ptr [rcx+19h], 3
0x18001de38  jb      short loc_18001DE56
0x18001de3a  mov     r9, cs:?hwndNotify@@3PEAUHWND__@@EA; HWND__ * hwndNotify
0x18001de41  lea     r8, WPP_0c7fc82a53b231168ee6f0523baae1e5_Traceguids
0x18001de48  mov     rcx, [rcx+10h]
0x18001de4c  mov     edx, 11h
0x18001de51  call    WPP_SF_q
0x18001de56  mov     rcx, r14; hObject
0x18001de59  call    cs:__imp_CloseHandle
0x18001de5f  xor     ebx, ebx
0x18001de61  cmp     cs:?hwndNotify@@3PEAUHWND__@@EA, rbx; HWND__ * hwndNotify
0x18001de68  setnz   bl
0x18001de6b  lea     rcx, [rsp+68h+var_38]; this
0x18001de70  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x18001de75  mov     eax, ebx
0x18001de77  add     rsp, 48h
0x18001de7b  pop     r14
0x18001de7d  pop     rdi
0x18001de7e  pop     rsi
0x18001de7f  pop     rbx
0x18001de80  retn
```
