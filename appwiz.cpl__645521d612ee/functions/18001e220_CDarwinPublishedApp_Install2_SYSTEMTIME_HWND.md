# CDarwinPublishedApp::Install2(_SYSTEMTIME *,HWND__ *)

- ea: `0x18001e220`
- end: `0x18001e358`
- name: `?Install2@CDarwinPublishedApp@@UEAAJPEAU_SYSTEMTIME@@PEAUHWND__@@@Z`
- size: `312`
- prototype: `int(CDarwinPublishedApp *__hidden this, struct _SYSTEMTIME *, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001e360`

## callees

- `0x18001e220`
- `0x18001e3f0`
- `0x18004fad4`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18001e2f4`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18001e2f4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001e2b7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001e2b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e2fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e2fd`

## pseudocode

```c
__int64 __fastcall CDarwinPublishedApp::Install2(CDarwinPublishedApp *this, struct _SYSTEMTIME *a2, HWND a3)
{
  bool v3; // zf
  int v6; // ecx
  __int128 v7; // xmm0
  HANDLE v8; // rax
  void *v9; // rbx
  int v10; // edx
  signed int v11; // ebx
  unsigned int lpThreadId; // [rsp+28h] [rbp-48h]
  DWORD ExitCode; // [rsp+30h] [rbp-40h] BYREF
  DWORD ThreadId; // [rsp+34h] [rbp-3Ch] BYREF
  HANDLE Handles; // [rsp+38h] [rbp-38h] BYREF
  _DWORD Parameter[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v18; // [rsp+48h] [rbp-28h]
  __int128 v19; // [rsp+50h] [rbp-20h]
  unsigned __int64 v20; // [rsp+60h] [rbp-10h]

  v3 = *((_DWORD *)this + 34) == 2;
  v19 = 0;
  Parameter[1] = 0;
  if ( v3 )
  {
    v6 = 1;
    Parameter[0] = 5;
  }
  else
  {
    v6 = 0;
    Parameter[0] = 1;
  }
  v7 = *(_OWORD *)((char *)this + 44);
  v18 = *((_QWORD *)this + 2);
  ThreadId = 0;
  v19 = v7;
  v20 = (unsigned __int64)a3 & -(__int64)(v6 != 0);
  v8 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)_Install2_ThreadProc, Parameter, 0, &ThreadId);
  v9 = v8;
  if ( v8 )
  {
    ExitCode = 5;
    Handles = v8;
    SHProcessMessagesUntilEventsEx(0, &Handles, 1u, 0xFFFFFFFF, 0x1CFFu, lpThreadId);
    GetExitCodeThread(v9, &ExitCode);
    CloseHandle(v9);
    v10 = ExitCode;
  }
  else
  {
    v10 = 8;
    ExitCode = 8;
  }
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  else
    v11 = v10;
  if ( v11 >= 0 )
    *((_DWORD *)this + 35) = 1;
  else
    _ARPErrorMessageBox(a3, v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001e220  mov     [rsp-18h+arg_8], rbx
0x18001e225  push    rbp
0x18001e226  push    rsi
0x18001e227  push    r14
0x18001e229  mov     rbp, rsp
0x18001e22c  sub     rsp, 70h
0x18001e230  mov     rax, cs:__security_cookie
0x18001e237  xor     rax, rsp
0x18001e23a  mov     [rbp+var_8], rax
0x18001e23e  cmp     dword ptr [rcx+88h], 2
0x18001e245  xorps   xmm0, xmm0
0x18001e248  movdqu  [rbp+var_20], xmm0
0x18001e24d  mov     r14, r8
0x18001e250  mov     [rbp+var_2C], 0
0x18001e257  mov     rsi, rcx
0x18001e25a  jnz     short loc_18001E26A
0x18001e25c  mov     ecx, 1
0x18001e261  mov     [rbp+Parameter], 5
0x18001e268  jmp     short loc_18001E273
0x18001e26a  xor     ecx, ecx
0x18001e26c  mov     [rbp+Parameter], 1
0x18001e273  mov     rax, [rsi+10h]
0x18001e277  lea     r9, [rbp+Parameter]; lpParameter
0x18001e27b  movups  xmm0, xmmword ptr [rsi+2Ch]
0x18001e27f  mov     [rbp+var_28], rax
0x18001e283  lea     r8, ?_Install2_ThreadProc@@YAKPEAX@Z; lpStartAddress
0x18001e28a  neg     ecx
0x18001e28c  mov     [rbp+ThreadId], 0
0x18001e293  movdqu  [rbp+var_20], xmm0
0x18001e298  sbb     rax, rax
0x18001e29b  xor     edx, edx; dwStackSize
0x18001e29d  and     rax, r14
0x18001e2a0  xor     ecx, ecx; lpThreadAttributes
0x18001e2a2  mov     [rbp+var_10], rax
0x18001e2a6  lea     rax, [rbp+ThreadId]
0x18001e2aa  mov     [rsp+70h+lpThreadId], rax; unsigned int
0x18001e2af  mov     [rsp+70h+dwCreationFlags], 0; dwCreationFlags
0x18001e2b7  call    cs:__imp_CreateThread
0x18001e2bd  mov     rbx, rax
0x18001e2c0  test    rax, rax
0x18001e2c3  jz      short loc_18001E308
0x18001e2c5  or      r9d, 0FFFFFFFFh; unsigned int
0x18001e2c9  mov     [rbp+ExitCode], 5
0x18001e2d0  mov     r8d, 1; nCount
0x18001e2d6  mov     [rbp+Handles], rax
0x18001e2da  lea     rdx, [rbp+Handles]; lpHandles
0x18001e2de  mov     [rsp+70h+dwCreationFlags], 1CFFh; dwWakeMask
0x18001e2e6  xor     ecx, ecx; hWnd
0x18001e2e8  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x18001e2ed  lea     rdx, [rbp+ExitCode]; lpExitCode
0x18001e2f1  mov     rcx, rbx; hThread
0x18001e2f4  call    cs:__imp_GetExitCodeThread
0x18001e2fa  mov     rcx, rbx; hObject
0x18001e2fd  call    cs:__imp_CloseHandle
0x18001e303  mov     edx, [rbp+ExitCode]
0x18001e306  jmp     short loc_18001E310
0x18001e308  mov     edx, 8; dwMessageId
0x18001e30d  mov     [rbp+ExitCode], edx
0x18001e310  test    edx, edx
0x18001e312  jg      short loc_18001E318
0x18001e314  mov     ebx, edx
0x18001e316  jmp     short loc_18001E321
0x18001e318  movzx   ebx, dx
0x18001e31b  or      ebx, 80070000h
0x18001e321  test    ebx, ebx
0x18001e323  jns     short loc_18001E32F
0x18001e325  mov     rcx, r14; hWnd
0x18001e328  call    ?_ARPErrorMessageBox@@YAXPEAUHWND__@@K@Z; _ARPErrorMessageBox(HWND__ *,ulong)
0x18001e32d  jmp     short loc_18001E339
0x18001e32f  mov     dword ptr [rsi+8Ch], 1
0x18001e339  mov     eax, ebx
0x18001e33b  mov     rcx, [rbp+var_8]
0x18001e33f  xor     rcx, rsp; StackCookie
0x18001e342  call    __security_check_cookie
0x18001e347  mov     rbx, [rsp+70h+arg_8]
0x18001e34f  add     rsp, 70h
0x18001e353  pop     r14
0x18001e355  pop     rsi
0x18001e356  pop     rbp
0x18001e357  retn
```
