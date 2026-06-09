# CHostedWindowFactory::SetAppWindowAndGetHostProcess(long,unsigned __int64 *)

- ea: `0x18005e420`
- end: `0x18005e590`
- name: `?SetAppWindowAndGetHostProcess@CHostedWindowFactory@@UEAAJJPEA_K@Z`
- size: `368`
- prototype: `__int64 __fastcall(CHostedWindowFactory *__hidden this, int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180027d9c`
- `0x18003aa84`
- `0x18005e420`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005e515`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005e515`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005e49f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005e4f0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005e49f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005e4f0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005e540`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005e540`
- `USER32!GetWindow` at `0x18005e45e`
- `USER32!GetWindow` at `0x18005e45e`
- `USER32!GetWindowThreadProcessId` at `0x18005e47b`
- `USER32!GetWindowThreadProcessId` at `0x18005e4ce`
- `USER32!GetWindowThreadProcessId` at `0x18005e47b`
- `USER32!GetWindowThreadProcessId` at `0x18005e4ce`

## pseudocode

```c
__int64 __fastcall CHostedWindowFactory::SetAppWindowAndGetHostProcess(
        CHostedWindowFactory *this,
        unsigned int a2,
        HANDLE *a3)
{
  HWND v5; // rbx
  int Error; // esi
  HWND Window; // rax
  void *v8; // rbx
  HANDLE CurrentProcess; // rax
  HANDLE v11[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD v12; // [rsp+80h] [rbp+30h] BYREF
  DWORD dwProcessId; // [rsp+88h] [rbp+38h] BYREF
  HANDLE TargetHandle; // [rsp+90h] [rbp+40h] BYREF
  HANDLE v15; // [rsp+98h] [rbp+48h] BYREF

  *a3 = 0;
  v5 = (HWND)(int)a2;
  Error = (*(__int64 (__fastcall **)(CHostedWindowFactory *, _QWORD))(*(_QWORD *)this + 24LL))(this, a2);
  if ( Error >= 0 )
  {
    Window = GetWindow(v5, 4u);
    if ( !Window )
      Window = (HWND)*((_QWORD *)this - 5);
    dwProcessId = 0;
    if ( GetWindowThreadProcessId(Window, &dwProcessId) || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      v11[0] = OpenProcess(0x100000u, 0, dwProcessId);
      if ( !v11[0] )
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
          goto LABEL_18;
      }
      v12 = 0;
      if ( !GetWindowThreadProcessId(v5, &v12) )
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
          goto LABEL_18;
      }
      v15 = OpenProcess(0x40u, 0, v12);
      v8 = v15;
      if ( !v15 )
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
LABEL_17:
          CAutoHandle<void *>::~CAutoHandle<void *>(&v15);
LABEL_18:
          CAutoHandle<void *>::~CAutoHandle<void *>(v11);
          return (unsigned int)Error;
        }
      }
      TargetHandle = 0;
      CurrentProcess = GetCurrentProcess();
      if ( DuplicateHandle(CurrentProcess, v11[0], v8, &TargetHandle, 0x100000u, 0, 0) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
LABEL_16:
          CAutoHandle<void *>::~CAutoHandle<void *>(&TargetHandle);
          goto LABEL_17;
        }
      }
      *a3 = TargetHandle;
      TargetHandle = 0;
      goto LABEL_16;
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18005e420  push    rbp
0x18005e422  push    rbx
0x18005e423  push    rsi
0x18005e424  push    rdi
0x18005e425  push    r14
0x18005e427  mov     rbp, rsp
0x18005e42a  sub     rsp, 50h
0x18005e42e  mov     qword ptr [r8], 0
0x18005e435  mov     r14, r8
0x18005e438  mov     rax, [rcx]
0x18005e43b  mov     rdi, rcx
0x18005e43e  movsxd  rbx, edx
0x18005e441  mov     edx, ebx
0x18005e443  mov     rax, [rax+18h]
0x18005e447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e44c  mov     esi, eax
0x18005e44e  test    eax, eax
0x18005e450  js      loc_18005E583
0x18005e456  mov     edx, 4; uCmd
0x18005e45b  mov     rcx, rbx; hWnd
0x18005e45e  call    cs:__imp_GetWindow
0x18005e464  test    rax, rax
0x18005e467  jnz     short loc_18005E46D
0x18005e469  mov     rax, [rdi-28h]
0x18005e46d  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x18005e471  mov     [rbp+dwProcessId], 0
0x18005e478  mov     rcx, rax; hWnd
0x18005e47b  call    cs:__imp_GetWindowThreadProcessId
0x18005e481  test    eax, eax
0x18005e483  jnz     short loc_18005E494
0x18005e485  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005e48a  mov     esi, eax
0x18005e48c  test    eax, eax
0x18005e48e  js      loc_18005E583
0x18005e494  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x18005e498  xor     edx, edx; bInheritHandle
0x18005e49a  mov     ecx, 100000h; dwDesiredAccess
0x18005e49f  call    cs:__imp_OpenProcess
0x18005e4a5  mov     [rbp+var_10], rax
0x18005e4a9  mov     rdi, rax
0x18005e4ac  test    rax, rax
0x18005e4af  jnz     short loc_18005E4C0
0x18005e4b1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005e4b6  mov     esi, eax
0x18005e4b8  test    eax, eax
0x18005e4ba  js      loc_18005E57A
0x18005e4c0  lea     rdx, [rbp+arg_0]; lpdwProcessId
0x18005e4c4  mov     [rbp+arg_0], 0
0x18005e4cb  mov     rcx, rbx; hWnd
0x18005e4ce  call    cs:__imp_GetWindowThreadProcessId
0x18005e4d4  test    eax, eax
0x18005e4d6  jnz     short loc_18005E4E7
0x18005e4d8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005e4dd  mov     esi, eax
0x18005e4df  test    eax, eax
0x18005e4e1  js      loc_18005E57A
0x18005e4e7  mov     r8d, [rbp+arg_0]; dwProcessId
0x18005e4eb  xor     edx, edx; bInheritHandle
0x18005e4ed  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18005e4f0  call    cs:__imp_OpenProcess
0x18005e4f6  mov     [rbp+arg_18], rax
0x18005e4fa  mov     rbx, rax
0x18005e4fd  test    rax, rax
0x18005e500  jnz     short loc_18005E50D
0x18005e502  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005e507  mov     esi, eax
0x18005e509  test    eax, eax
0x18005e50b  js      short loc_18005E571
0x18005e50d  mov     [rbp+TargetHandle], 0
0x18005e515  call    cs:__imp_GetCurrentProcess
0x18005e51b  mov     [rsp+50h+dwOptions], 0; dwOptions
0x18005e523  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18005e527  mov     rcx, rax; hSourceProcessHandle
0x18005e52a  mov     [rsp+50h+bInheritHandle], 0; bInheritHandle
0x18005e532  mov     r8, rbx; hTargetProcessHandle
0x18005e535  mov     [rsp+50h+dwDesiredAccess], 100000h; dwDesiredAccess
0x18005e53d  mov     rdx, rdi; hSourceHandle
0x18005e540  call    cs:__imp_DuplicateHandle
0x18005e546  test    eax, eax
0x18005e548  jz      short loc_18005E54E
0x18005e54a  xor     esi, esi
0x18005e54c  jmp     short loc_18005E559
0x18005e54e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005e553  mov     esi, eax
0x18005e555  test    eax, eax
0x18005e557  js      short loc_18005E568
0x18005e559  mov     rax, [rbp+TargetHandle]
0x18005e55d  mov     [r14], rax
0x18005e560  mov     [rbp+TargetHandle], 0
0x18005e568  lea     rcx, [rbp+TargetHandle]
0x18005e56c  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x18005e571  lea     rcx, [rbp+arg_18]
0x18005e575  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x18005e57a  lea     rcx, [rbp+var_10]
0x18005e57e  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x18005e583  mov     eax, esi
0x18005e585  add     rsp, 50h
0x18005e589  pop     r14
0x18005e58b  pop     rdi
0x18005e58c  pop     rsi
0x18005e58d  pop     rbx
0x18005e58e  pop     rbp
0x18005e58f  retn
```
