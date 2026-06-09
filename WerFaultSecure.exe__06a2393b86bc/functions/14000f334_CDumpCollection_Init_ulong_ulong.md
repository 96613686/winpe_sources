# CDumpCollection::Init(ulong,ulong)

- ea: `0x14000f334`
- end: `0x14000f4a7`
- name: `?Init@CDumpCollection@@QEAAJKK@Z`
- size: `371`
- prototype: `__int64 __fastcall(CDumpCollection *this, DWORD dwProcessId, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000628c`

## callees

- `0x1400073fc`
- `0x140007cd4`
- `0x14000e820`
- `0x14000f334`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f3ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f3ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f405`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f3a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f3a3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14000f385`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14000f385`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000f369`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000f369`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000f45f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000f45f`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x14000f3fb`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x14000f3fb`

## pseudocode

```c
__int64 __fastcall CDumpCollection::Init(CDumpCollection *this, DWORD dwProcessId, int a3)
{
  HANDLE v6; // rax
  void *v7; // rcx
  void *v8; // rcx
  signed int v9; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  signed int LastError; // eax

  if ( (unsigned __int64)(*((_QWORD *)this + 137) + 1LL) <= 1 && !*((_WORD *)this + 20) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)this);
    *((_DWORD *)this + 278) = dwProcessId;
    *((_DWORD *)this + 279) = a3;
    v6 = OpenProcess(0x100450u, 0, dwProcessId);
    v7 = (void *)*((_QWORD *)this + 137);
    *((_QWORD *)this + 137) = v6;
    if ( (unsigned __int64)v7 + 1 > 1 )
      CloseHandle(v7);
    v8 = (void *)*((_QWORD *)this + 137);
    if ( (unsigned __int64)v8 + 1 > 1 )
    {
      if ( K32GetModuleFileNameExW(v8, 0, (LPWSTR)this + 20, 0x104u) )
      {
        v10 = 0;
LABEL_21:
        LeaveCriticalSection((LPCRITICAL_SECTION)this);
        return v10;
      }
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_18:
        if ( (v10 & 0x80000000) != 0 )
          CDumpCollection::Cleanup(this);
        goto LABEL_21;
      }
      v12 = 37;
    }
    else
    {
      v9 = GetLastError();
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_18;
      v12 = 36;
    }
    WPP_SF_d(v11[2], v12, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v10);
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x14000f334  push    rbx
0x14000f336  push    rbp
0x14000f337  push    rsi
0x14000f338  push    rdi
0x14000f339  push    r14
0x14000f33b  sub     rsp, 20h
0x14000f33f  mov     rax, [rcx+448h]
0x14000f346  mov     ebp, r8d
0x14000f349  inc     rax
0x14000f34c  mov     esi, edx
0x14000f34e  mov     rdi, rcx
0x14000f351  cmp     rax, 1
0x14000f355  ja      loc_14000F469
0x14000f35b  xor     r14d, r14d
0x14000f35e  cmp     [rcx+28h], r14w
0x14000f363  jnz     loc_14000F469
0x14000f369  call    cs:__imp_EnterCriticalSection
0x14000f36f  mov     r8d, esi; dwProcessId
0x14000f372  mov     [rdi+458h], esi
0x14000f378  xor     edx, edx; bInheritHandle
0x14000f37a  mov     [rdi+45Ch], ebp
0x14000f380  mov     ecx, 100450h; dwDesiredAccess
0x14000f385  call    cs:__imp_OpenProcess
0x14000f38b  mov     rcx, [rdi+448h]; hObject
0x14000f392  mov     [rdi+448h], rax
0x14000f399  lea     rax, [rcx+1]
0x14000f39d  cmp     rax, 1
0x14000f3a1  jbe     short loc_14000F3A9
0x14000f3a3  call    cs:__imp_CloseHandle
0x14000f3a9  mov     rcx, [rdi+448h]; hProcess
0x14000f3b0  lea     rax, [rcx+1]
0x14000f3b4  cmp     rax, 1
0x14000f3b8  ja      short loc_14000F3EF
0x14000f3ba  call    cs:__imp_GetLastError
0x14000f3c0  mov     ebx, eax
0x14000f3c2  test    eax, eax
0x14000f3c4  jle     short loc_14000F3CF
0x14000f3c6  movzx   ebx, ax
0x14000f3c9  or      ebx, 80070000h
0x14000f3cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f3d6  lea     rax, WPP_GLOBAL_Control
0x14000f3dd  cmp     rcx, rax
0x14000f3e0  jz      short loc_14000F44B
0x14000f3e2  test    byte ptr [rcx+1Ch], 1
0x14000f3e6  jz      short loc_14000F44B
0x14000f3e8  mov     edx, 24h ; '$'
0x14000f3ed  jmp     short loc_14000F438
0x14000f3ef  mov     r9d, 104h; nSize
0x14000f3f5  lea     r8, [rdi+28h]; lpFilename
0x14000f3f9  xor     edx, edx; hModule
0x14000f3fb  call    cs:__imp_K32GetModuleFileNameExW
0x14000f401  test    eax, eax
0x14000f403  jnz     short loc_14000F459
0x14000f405  call    cs:__imp_GetLastError
0x14000f40b  mov     ebx, eax
0x14000f40d  test    eax, eax
0x14000f40f  jle     short loc_14000F41A
0x14000f411  movzx   ebx, ax
0x14000f414  or      ebx, 80070000h
0x14000f41a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f421  lea     rax, WPP_GLOBAL_Control
0x14000f428  cmp     rcx, rax
0x14000f42b  jz      short loc_14000F44B
0x14000f42d  test    byte ptr [rcx+1Ch], 1
0x14000f431  jz      short loc_14000F44B
0x14000f433  mov     edx, 25h ; '%'
0x14000f438  mov     rcx, [rcx+10h]
0x14000f43c  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x14000f443  mov     r9d, ebx
0x14000f446  call    WPP_SF_d
0x14000f44b  test    ebx, ebx
0x14000f44d  jns     short loc_14000F45C
0x14000f44f  mov     rcx, rdi; this
0x14000f452  call    ?Cleanup@CDumpCollection@@QEAAXXZ; CDumpCollection::Cleanup(void)
0x14000f457  jmp     short loc_14000F45C
0x14000f459  mov     ebx, r14d
0x14000f45c  mov     rcx, rdi; lpCriticalSection
0x14000f45f  call    cs:__imp_LeaveCriticalSection
0x14000f465  mov     eax, ebx
0x14000f467  jmp     short loc_14000F49C
0x14000f469  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f470  lea     rax, WPP_GLOBAL_Control
0x14000f477  cmp     rcx, rax
0x14000f47a  jz      short loc_14000F497
0x14000f47c  test    byte ptr [rcx+1Ch], 1
0x14000f480  jz      short loc_14000F497
0x14000f482  mov     rcx, [rcx+10h]
0x14000f486  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x14000f48d  mov     edx, 23h ; '#'
0x14000f492  call    WPP_SF_
0x14000f497  mov     eax, 80070057h
0x14000f49c  add     rsp, 20h
0x14000f4a0  pop     r14
0x14000f4a2  pop     rdi
0x14000f4a3  pop     rsi
0x14000f4a4  pop     rbp
0x14000f4a5  pop     rbx
0x14000f4a6  retn
```
