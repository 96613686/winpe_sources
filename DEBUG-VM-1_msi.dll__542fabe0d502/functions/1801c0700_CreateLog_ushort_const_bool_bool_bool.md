# CreateLog(ushort const *,bool,bool,bool)

- ea: `0x1801c0700`
- end: `0x1801c0af0`
- name: `?CreateLog@@YA_NPEBG_N11@Z`
- size: `1008`
- prototype: `bool __fastcall(const unsigned __int16 *, bool, bool, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1801123bc`
- `0x1801b3bc0`

## callees

- `0x18006bd18`
- `0x180146548`
- `0x1801c0700`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x1801c0840`
- `ADVAPI32!SetThreadToken` at `0x1801c08ac`
- `ADVAPI32!SetThreadToken` at `0x1801c0840`
- `ADVAPI32!SetThreadToken` at `0x1801c08ac`
- `ADVAPI32!OpenThreadToken` at `0x1801c082e`
- `ADVAPI32!OpenThreadToken` at `0x1801c082e`
- `KERNEL32!CloseHandle` at `0x1801c0732`
- `KERNEL32!CloseHandle` at `0x1801c0744`
- `KERNEL32!CloseHandle` at `0x1801c08bd`
- `KERNEL32!CloseHandle` at `0x1801c0a42`
- `KERNEL32!CloseHandle` at `0x1801c0a5f`
- `KERNEL32!CloseHandle` at `0x1801c0732`
- `KERNEL32!CloseHandle` at `0x1801c0744`
- `KERNEL32!CloseHandle` at `0x1801c08bd`
- `KERNEL32!CloseHandle` at `0x1801c0a42`
- `KERNEL32!CloseHandle` at `0x1801c0a5f`
- `KERNEL32!GetLastError` at `0x1801c07fd`
- `KERNEL32!GetLastError` at `0x1801c098a`
- `KERNEL32!GetLastError` at `0x1801c07fd`
- `KERNEL32!GetLastError` at `0x1801c098a`
- `KERNEL32!GlobalAlloc` at `0x1801c0a21`
- `KERNEL32!GlobalAlloc` at `0x1801c0a21`
- `KERNEL32!WaitForSingleObject` at `0x1801c09a5`
- `KERNEL32!WaitForSingleObject` at `0x1801c09a5`
- `KERNEL32!GetCurrentThread` at `0x1801c080c`
- `KERNEL32!GetCurrentThread` at `0x1801c080c`
- `KERNEL32!GetSystemInfo` at `0x1801c0ace`
- `KERNEL32!GetSystemInfo` at `0x1801c0ace`
- `KERNEL32!lstrcmpiW` at `0x1801c0925`
- `KERNEL32!lstrcmpiW` at `0x1801c0925`
- `KERNEL32!CreateFileW` at `0x1801c07c6`
- `KERNEL32!CreateFileW` at `0x1801c0884`
- `KERNEL32!CreateFileW` at `0x1801c07c6`
- `KERNEL32!CreateFileW` at `0x1801c0884`
- `KERNEL32!SetFilePointer` at `0x1801c093e`
- `KERNEL32!SetFilePointer` at `0x1801c093e`
- `KERNEL32!Wow64DisableWow64FsRedirection` at `0x1801c077f`
- `KERNEL32!Wow64DisableWow64FsRedirection` at `0x1801c0857`
- `KERNEL32!Wow64DisableWow64FsRedirection` at `0x1801c077f`
- `KERNEL32!Wow64DisableWow64FsRedirection` at `0x1801c0857`
- `KERNEL32!Wow64RevertWow64FsRedirection` at `0x1801c07e0`
- `KERNEL32!Wow64RevertWow64FsRedirection` at `0x1801c089e`
- `KERNEL32!Wow64RevertWow64FsRedirection` at `0x1801c07e0`
- `KERNEL32!Wow64RevertWow64FsRedirection` at `0x1801c089e`
- `KERNEL32!WriteFile` at `0x1801c0980`
- `KERNEL32!WriteFile` at `0x1801c0980`
- `KERNEL32!GetOverlappedResult` at `0x1801c09c2`
- `KERNEL32!GetOverlappedResult` at `0x1801c09c2`

## pseudocode

```c
char __fastcall CreateLog(const unsigned __int16 *a1, unsigned __int8 a2, char a3, char a4)
{
  int v5; // r15d
  char v8; // di
  BOOL v9; // ebx
  DWORD v11; // eax
  _DWORD *v12; // rax
  _DWORD *v13; // rbx
  HANDLE v14; // rcx
  int v15; // edx
  void *TokenHandle; // [rsp+40h] [rbp-29h] BYREF
  void *Thread; // [rsp+48h] [rbp-21h] BYREF
  struct _SYSTEM_INFO Overlapped[2]; // [rsp+50h] [rbp-19h] BYREF
  PVOID OldValue; // [rsp+D0h] [rbp+67h] BYREF

  v5 = a2;
  if ( hObject )
    CloseHandle(hObject);
  if ( hMutex )
  {
    CloseHandle(hMutex);
    hMutex = 0;
  }
  if ( a1 )
  {
    if ( g_fWoW || !g_fWinNT64 )
    {
      v9 = 1;
      OldValue = 0;
      v8 = 0;
    }
    else
    {
      OldValue = 0;
      v8 = 1;
      v9 = Wow64DisableWow64FsRedirection(&OldValue);
    }
    hObject = CreateFileW(a1, 0x40000000u, 3u, 0, 2 * v5 + 2, 0x40100080u, 0);
    if ( v8 && v9 )
      Wow64RevertWow64FsRedirection(OldValue);
    if ( a4 )
    {
      if ( hObject != (HANDLE)-1LL )
        goto LABEL_32;
      if ( GetLastError() == 5 )
      {
        TokenHandle = (void *)-1LL;
        Thread = GetCurrentThread();
        if ( !OpenThreadToken(Thread, 0xEu, 1, &TokenHandle) || !SetThreadToken(0, 0) )
          goto LABEL_26;
        if ( v8 && v9 )
          v9 = Wow64DisableWow64FsRedirection(&OldValue);
        hObject = CreateFileW(a1, 0x40000000u, 3u, 0, 2 * v5 + 2, 0x40100080u, 0);
        if ( v8 && v9 )
          Wow64RevertWow64FsRedirection(OldValue);
        if ( !SetThreadToken(&Thread, TokenHandle) )
        {
          CloseHandle(hObject);
LABEL_26:
          hObject = 0;
          CHandle::~CHandle((CHandle *)&TokenHandle);
          return 0;
        }
        CHandle::~CHandle((CHandle *)&TokenHandle);
      }
    }
  }
  else
  {
    hObject = (HANDLE)-1LL;
  }
  if ( hObject == (HANDLE)-1LL )
  {
    hObject = 0;
    return 0;
  }
LABEL_32:
  if ( (_BYTE)v5 && lstrcmpiW(a1, L"NUL") )
  {
    v11 = SetFilePointer(hObject, 0, 0, 2u);
    if ( v11 == -1 )
      goto LABEL_48;
    if ( v11 )
      goto LABEL_42;
  }
  LOWORD(OldValue) = -257;
  LODWORD(TokenHandle) = 0;
  memset(Overlapped, 0, 32);
  if ( !WriteFile(hObject, &OldValue, 2u, (LPDWORD)&TokenHandle, (LPOVERLAPPED)Overlapped) )
  {
    if ( GetLastError() != 997 )
      goto LABEL_48;
    while ( Overlapped[0].dwOemId == 259 )
      WaitForSingleObject(hObject, 0xFFFFFFFF);
    if ( !GetOverlappedResult(hObject, (LPOVERLAPPED)Overlapped, (LPDWORD)&TokenHandle, 0) )
    {
LABEL_48:
      if ( hObject )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      if ( hMutex )
      {
        CloseHandle(hMutex);
        hMutex = 0;
      }
      return 0;
    }
  }
LABEL_42:
  if ( CreatePerUserFileLockMutex(a1, hObject, &hMutex) )
    qword_180309748 = 0x100000003LL;
  else
    qword_180309748 = 0;
  if ( !g_fFlushEachLine && !a3 )
  {
    v12 = GlobalAlloc(0x40u, 0x70u);
    *((_QWORD *)&xmmword_180309760 + 1) = v12;
    v13 = v12;
    if ( !v12 )
      goto LABEL_48;
    v14 = hObject;
    v15 = (unsigned __int8)byte_180309770;
    *(_QWORD *)v12 = 0;
    v12[2] = 0;
    v12[6] = 1;
    *((_QWORD *)v12 + 2) = v12 + 8;
    *((_QWORD *)v12 + 5) = 0;
    v12[12] = 0;
    *((_QWORD *)v12 + 7) = v12 + 18;
    v12[16] = 1;
    *((_QWORD *)v12 + 10) = v14;
    v12[26] = v15;
    v12[22] = 0;
    *((_BYTE *)v12 + 96) = 0;
    v12[25] = 0;
    memset(Overlapped, 0, 48);
    GetSystemInfo(Overlapped);
    v13[23] = Overlapped[0].dwPageSize;
  }
  return 1;
}

```

## disassembly

```asm
0x1801c0700  push    rbp
0x1801c0702  push    rbx
0x1801c0703  push    rsi
0x1801c0704  push    rdi
0x1801c0705  push    r12
0x1801c0707  push    r13
0x1801c0709  push    r14
0x1801c070b  push    r15
0x1801c070d  lea     rbp, [rsp-1Fh]
0x1801c0712  sub     rsp, 88h
0x1801c0719  mov     rsi, rcx
0x1801c071c  movzx   r15d, dl
0x1801c0720  mov     rcx, cs:hObject; hObject
0x1801c0727  mov     r14b, r9b
0x1801c072a  mov     r13b, r8b
0x1801c072d  test    rcx, rcx
0x1801c0730  jz      short loc_1801C0738
0x1801c0732  call    cs:__imp_CloseHandle
0x1801c0738  mov     rcx, cs:hMutex; hObject
0x1801c073f  test    rcx, rcx
0x1801c0742  jz      short loc_1801C0755
0x1801c0744  call    cs:__imp_CloseHandle
0x1801c074a  mov     cs:hMutex, 0
0x1801c0755  test    rsi, rsi
0x1801c0758  jz      loc_1801C08E9
0x1801c075e  cmp     cs:?g_fWoW@@3_NA, 0; bool g_fWoW
0x1801c0765  jnz     short loc_1801C0789
0x1801c0767  cmp     cs:?g_fWinNT64@@3_NA, 0; bool g_fWinNT64
0x1801c076e  jz      short loc_1801C0789
0x1801c0770  lea     rcx, [rbp+57h+OldValue]; OldValue
0x1801c0774  mov     [rbp+57h+OldValue], 0
0x1801c077c  mov     dil, 1
0x1801c077f  call    cs:__imp_Wow64DisableWow64FsRedirection
0x1801c0785  mov     ebx, eax
0x1801c0787  jmp     short loc_1801C0799
0x1801c0789  mov     ebx, 1
0x1801c078e  mov     [rbp+57h+OldValue], 0
0x1801c0796  xor     dil, dil
0x1801c0799  xor     r9d, r9d; lpSecurityAttributes
0x1801c079c  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x1801c07a5  lea     r12d, ds:2[r15*2]
0x1801c07ad  mov     [rsp+0C0h+dwFlagsAndAttributes], 40100080h; dwFlagsAndAttributes
0x1801c07b5  mov     edx, 40000000h; dwDesiredAccess
0x1801c07ba  mov     [rsp+0C0h+dwCreationDisposition], r12d; dwCreationDisposition
0x1801c07bf  mov     rcx, rsi; lpFileName
0x1801c07c2  lea     r8d, [r9+3]; dwShareMode
0x1801c07c6  call    cs:__imp_CreateFileW
0x1801c07cc  mov     cs:hObject, rax
0x1801c07d3  test    dil, dil
0x1801c07d6  jz      short loc_1801C07E6
0x1801c07d8  test    ebx, ebx
0x1801c07da  jz      short loc_1801C07E6
0x1801c07dc  mov     rcx, [rbp+57h+OldValue]; OlValue
0x1801c07e0  call    cs:__imp_Wow64RevertWow64FsRedirection
0x1801c07e6  test    r14b, r14b
0x1801c07e9  jz      loc_1801C08F4
0x1801c07ef  cmp     cs:hObject, 0FFFFFFFFFFFFFFFFh
0x1801c07f7  jnz     loc_1801C090B
0x1801c07fd  call    cs:__imp_GetLastError
0x1801c0803  cmp     eax, 5
0x1801c0806  jnz     loc_1801C08F4
0x1801c080c  call    cs:__imp_GetCurrentThread
0x1801c0812  mov     edx, 0Eh; DesiredAccess
0x1801c0817  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1801c081f  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1801c0823  mov     [rbp+57h+Thread], rax
0x1801c0827  mov     rcx, rax; ThreadHandle
0x1801c082a  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1801c082e  call    cs:__imp_OpenThreadToken
0x1801c0834  test    eax, eax
0x1801c0836  jz      loc_1801C08C3
0x1801c083c  xor     edx, edx; Token
0x1801c083e  xor     ecx, ecx; Thread
0x1801c0840  call    cs:__imp_SetThreadToken
0x1801c0846  test    eax, eax
0x1801c0848  jz      short loc_1801C08C3
0x1801c084a  test    dil, dil
0x1801c084d  jz      short loc_1801C085F
0x1801c084f  test    ebx, ebx
0x1801c0851  jz      short loc_1801C085F
0x1801c0853  lea     rcx, [rbp+57h+OldValue]; OldValue
0x1801c0857  call    cs:__imp_Wow64DisableWow64FsRedirection
0x1801c085d  mov     ebx, eax
0x1801c085f  xor     r9d, r9d; lpSecurityAttributes
0x1801c0862  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x1801c086b  mov     [rsp+0C0h+dwFlagsAndAttributes], 40100080h; dwFlagsAndAttributes
0x1801c0873  mov     edx, 40000000h; dwDesiredAccess
0x1801c0878  mov     rcx, rsi; lpFileName
0x1801c087b  mov     [rsp+0C0h+dwCreationDisposition], r12d; dwCreationDisposition
0x1801c0880  lea     r8d, [r9+3]; dwShareMode
0x1801c0884  call    cs:__imp_CreateFileW
0x1801c088a  mov     cs:hObject, rax
0x1801c0891  test    dil, dil
0x1801c0894  jz      short loc_1801C08A4
0x1801c0896  test    ebx, ebx
0x1801c0898  jz      short loc_1801C08A4
0x1801c089a  mov     rcx, [rbp+57h+OldValue]; OlValue
0x1801c089e  call    cs:__imp_Wow64RevertWow64FsRedirection
0x1801c08a4  mov     rdx, [rbp+57h+TokenHandle]; Token
0x1801c08a8  lea     rcx, [rbp+57h+Thread]; Thread
0x1801c08ac  call    cs:__imp_SetThreadToken
0x1801c08b2  test    eax, eax
0x1801c08b4  jnz     short loc_1801C08DE
0x1801c08b6  mov     rcx, cs:hObject; hObject
0x1801c08bd  call    cs:__imp_CloseHandle
0x1801c08c3  lea     rcx, [rbp+57h+TokenHandle]; this
0x1801c08c7  mov     cs:hObject, 0
0x1801c08d2  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x1801c08d7  xor     al, al
0x1801c08d9  jmp     loc_1801C0ADC
0x1801c08de  lea     rcx, [rbp+57h+TokenHandle]; this
0x1801c08e2  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x1801c08e7  jmp     short loc_1801C08F4
0x1801c08e9  mov     cs:hObject, 0FFFFFFFFFFFFFFFFh
0x1801c08f4  cmp     cs:hObject, 0FFFFFFFFFFFFFFFFh
0x1801c08fc  jnz     short loc_1801C090B
0x1801c08fe  mov     cs:hObject, 0
0x1801c0909  jmp     short loc_1801C08D7
0x1801c090b  or      r14d, 0FFFFFFFFh
0x1801c090f  xor     edi, edi
0x1801c0911  mov     ebx, 2
0x1801c0916  test    r15b, r15b
0x1801c0919  jz      short loc_1801C0951
0x1801c091b  lea     rdx, aNul; "NUL"
0x1801c0922  mov     rcx, rsi; lpString1
0x1801c0925  call    cs:__imp_lstrcmpiW
0x1801c092b  test    eax, eax
0x1801c092d  jz      short loc_1801C0951
0x1801c092f  mov     rcx, cs:hObject; hFile
0x1801c0936  mov     r9d, ebx; dwMoveMethod
0x1801c0939  xor     r8d, r8d; lpDistanceToMoveHigh
0x1801c093c  xor     edx, edx; lDistanceToMove
0x1801c093e  call    cs:__imp_SetFilePointer
0x1801c0944  cmp     eax, r14d
0x1801c0947  jz      loc_1801C0A36
0x1801c094d  test    eax, eax
0x1801c094f  jnz     short loc_1801C09CC
0x1801c0951  mov     rcx, cs:hObject; hFile
0x1801c0958  lea     rax, [rbp+57h+Overlapped]
0x1801c095c  xorps   xmm0, xmm0
0x1801c095f  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; lpOverlapped
0x1801c0964  lea     r9, [rbp+57h+TokenHandle]; lpNumberOfBytesWritten
0x1801c0968  mov     word ptr [rbp+57h+OldValue], 0FEFFh
0x1801c096e  mov     r8d, ebx; nNumberOfBytesToWrite
0x1801c0971  mov     dword ptr [rbp+57h+TokenHandle], edi
0x1801c0974  lea     rdx, [rbp+57h+OldValue]; lpBuffer
0x1801c0978  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x1801c097c  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x1801c0980  call    cs:__imp_WriteFile
0x1801c0986  test    eax, eax
0x1801c0988  jnz     short loc_1801C09CC
0x1801c098a  call    cs:__imp_GetLastError
0x1801c0990  cmp     eax, 3E5h
0x1801c0995  jnz     loc_1801C0A36
0x1801c099b  mov     ebx, 103h
0x1801c09a0  jmp     short loc_1801C09AB
0x1801c09a2  mov     edx, r14d; dwMilliseconds
0x1801c09a5  call    cs:__imp_WaitForSingleObject
0x1801c09ab  mov     rcx, cs:hObject; hFile
0x1801c09b2  cmp     dword ptr [rbp+57h+Overlapped.Internal], ebx
0x1801c09b5  jz      short loc_1801C09A2
0x1801c09b7  xor     r9d, r9d; bWait
0x1801c09ba  lea     r8, [rbp+57h+TokenHandle]; lpNumberOfBytesTransferred
0x1801c09be  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x1801c09c2  call    cs:__imp_GetOverlappedResult
0x1801c09c8  test    eax, eax
0x1801c09ca  jz      short loc_1801C0A36
0x1801c09cc  mov     rdx, cs:hObject; void *
0x1801c09d3  lea     r8, hMutex; void **
0x1801c09da  mov     rcx, rsi; unsigned __int16 *
0x1801c09dd  call    ?CreatePerUserFileLockMutex@@YAKPEBGPEAXAEAPEAX@Z; CreatePerUserFileLockMutex(ushort const *,void *,void * &)
0x1801c09e2  test    eax, eax
0x1801c09e4  jnz     short loc_1801C09EF
0x1801c09e6  mov     cs:qword_180309748, rdi
0x1801c09ed  jmp     short loc_1801C0A03
0x1801c09ef  mov     dword ptr cs:qword_180309748, 3
0x1801c09f9  mov     dword ptr cs:qword_180309748+4, 1
0x1801c0a03  cmp     cs:?g_fFlushEachLine@@3_NA, dil; bool g_fFlushEachLine
0x1801c0a0a  jnz     loc_1801C0ADA
0x1801c0a10  test    r13b, r13b
0x1801c0a13  jnz     loc_1801C0ADA
0x1801c0a19  mov     edx, 70h ; 'p'; dwBytes
0x1801c0a1e  lea     ecx, [rdx-30h]; uFlags
0x1801c0a21  call    cs:__imp_GlobalAlloc
0x1801c0a27  mov     qword ptr cs:xmmword_180309760+8, rax
0x1801c0a2e  mov     rbx, rax
0x1801c0a31  test    rax, rax
0x1801c0a34  jnz     short loc_1801C0A71
0x1801c0a36  mov     rcx, cs:hObject; hObject
0x1801c0a3d  test    rcx, rcx
0x1801c0a40  jz      short loc_1801C0A4F
0x1801c0a42  call    cs:__imp_CloseHandle
0x1801c0a48  mov     cs:hObject, rdi
0x1801c0a4f  mov     rcx, cs:hMutex; hObject
0x1801c0a56  test    rcx, rcx
0x1801c0a59  jz      loc_1801C08D7
0x1801c0a5f  call    cs:__imp_CloseHandle
0x1801c0a65  mov     cs:hMutex, rdi
0x1801c0a6c  jmp     loc_1801C08D7
0x1801c0a71  mov     rcx, cs:hObject
0x1801c0a78  xorps   xmm0, xmm0
0x1801c0a7b  movzx   edx, cs:byte_180309770
0x1801c0a82  mov     [rax], rdi
0x1801c0a85  mov     [rax+8], edi
0x1801c0a88  mov     dword ptr [rax+18h], 1
0x1801c0a8f  add     rax, 20h ; ' '
0x1801c0a93  mov     [rbx+10h], rax
0x1801c0a97  lea     rax, [rbx+48h]
0x1801c0a9b  mov     [rbx+28h], rdi
0x1801c0a9f  mov     [rbx+30h], edi
0x1801c0aa2  mov     [rbx+38h], rax
0x1801c0aa6  mov     dword ptr [rbx+40h], 1
0x1801c0aad  mov     [rbx+50h], rcx
0x1801c0ab1  lea     rcx, [rbp+57h+Overlapped]; lpSystemInfo
0x1801c0ab5  mov     [rbx+68h], edx
0x1801c0ab8  mov     [rbx+58h], edi
0x1801c0abb  mov     [rbx+60h], dil
0x1801c0abf  mov     [rbx+64h], edi
0x1801c0ac2  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x1801c0ac6  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x1801c0aca  movups  [rbp+57h+var_50], xmm0
0x1801c0ace  call    cs:__imp_GetSystemInfo
0x1801c0ad4  mov     ecx, dword ptr [rbp+57h+Overlapped.Internal+4]
0x1801c0ad7  mov     [rbx+5Ch], ecx
0x1801c0ada  mov     al, 1
0x1801c0adc  add     rsp, 88h
0x1801c0ae3  pop     r15
0x1801c0ae5  pop     r14
0x1801c0ae7  pop     r13
0x1801c0ae9  pop     r12
0x1801c0aeb  pop     rdi
0x1801c0aec  pop     rsi
0x1801c0aed  pop     rbx
0x1801c0aee  pop     rbp
0x1801c0aef  retn
```
