# PrintConfig::CPinnedDllsPrintTicketService::Initialize(PrintConfig::IPrintTicketService *,_DRIVER_INFO_4W const *)

- ea: `0x1800978e4`
- end: `0x180097a2c`
- name: `?Initialize@CPinnedDllsPrintTicketService@PrintConfig@@IEAAJPEAUIPrintTicketService@2@PEBU_DRIVER_INFO_4W@@@Z`
- size: `328`
- prototype: `__int64 __fastcall(PrintConfig::CPinnedDllsPrintTicketService *__hidden this, struct PrintConfig::IPrintTicketService *, const struct _DRIVER_INFO_4W *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800976ec`

## callees

- `0x1800978e4`
- `0x180097d7c`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180097933`
- `KERNEL32!GetCurrentProcess` at `0x180097933`
- `KERNEL32!CloseHandle` at `0x18009795f`
- `KERNEL32!CloseHandle` at `0x1800979ab`
- `KERNEL32!CloseHandle` at `0x18009795f`
- `KERNEL32!CloseHandle` at `0x1800979ab`
- `KERNEL32!lstrcmpiW` at `0x1800979fa`
- `KERNEL32!lstrcmpiW` at `0x1800979fa`
- `ADVAPI32!GetTokenInformation` at `0x18009798a`
- `ADVAPI32!GetTokenInformation` at `0x18009798a`
- `ADVAPI32!OpenProcessToken` at `0x180097946`
- `ADVAPI32!OpenProcessToken` at `0x180097946`

## pseudocode

```c
__int64 __fastcall PrintConfig::CPinnedDllsPrintTicketService::Initialize(
        PrintConfig::CPinnedDllsPrintTicketService *this,
        struct PrintConfig::IPrintTicketService *a2,
        const struct _DRIVER_INFO_4W *a3)
{
  __int64 v6; // rcx
  HANDLE CurrentProcess; // rax
  BOOL v8; // eax
  HANDLE v9; // rcx
  char *v10; // rax
  BOOL v11; // eax
  bool v12; // zf
  bool v13; // bl
  int v14; // ebp
  LPWSTR pDependentFiles; // rbx
  __int64 v16; // rdi
  int TokenInformation; // [rsp+60h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+68h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp+20h] BYREF

  if ( *((struct PrintConfig::IPrintTicketService **)this + 8) != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(struct PrintConfig::IPrintTicketService *))(*(_QWORD *)a2 + 8LL))(a2);
    v6 = *((_QWORD *)this + 8);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 8) = a2;
  }
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  v8 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  v9 = TokenHandle;
  if ( !v8 )
  {
    v10 = (char *)TokenHandle - 1;
    goto LABEL_9;
  }
  TokenInformation = 0;
  ReturnLength = 0;
  v11 = GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
  v9 = TokenHandle;
  v12 = !v11;
  v10 = (char *)TokenHandle - 1;
  if ( v12 )
  {
LABEL_9:
    if ( (unsigned __int64)v10 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v9);
LABEL_15:
    v14 = PrintConfig::CPinnedDllsPrintTicketService::PinDll(this, a3->pDriverPath);
    if ( v14 >= 0 )
    {
      pDependentFiles = a3->pDependentFiles;
      do
      {
        if ( !pDependentFiles || !*pDependentFiles )
          break;
        v16 = -1;
        do
          ++v16;
        while ( pDependentFiles[v16] );
        if ( (int)v16 > 4 && !lstrcmpiW(L".dll", &pDependentFiles[(int)v16 - 4]) )
          v14 = PrintConfig::CPinnedDllsPrintTicketService::PinDll(this, pDependentFiles);
        pDependentFiles += (int)v16 + 1;
      }
      while ( v14 >= 0 );
    }
    return 0;
  }
  v13 = TokenInformation != 0;
  if ( (unsigned __int64)v10 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(TokenHandle);
  if ( !v13 )
    goto LABEL_15;
  return 0;
}

```

## disassembly

```asm
0x1800978e4  push    rbx
0x1800978e6  push    rbp
0x1800978e7  push    rsi
0x1800978e8  push    rdi
0x1800978e9  push    r14
0x1800978eb  sub     rsp, 30h
0x1800978ef  xor     r14d, r14d
0x1800978f2  mov     rdi, r8
0x1800978f5  mov     rbx, rdx
0x1800978f8  mov     rsi, rcx
0x1800978fb  cmp     [rcx+40h], rdx
0x1800978ff  jz      short loc_18009792E
0x180097901  test    rdx, rdx
0x180097904  jz      short loc_180097915
0x180097906  mov     rax, [rdx]
0x180097909  mov     rcx, rdx
0x18009790c  mov     rax, [rax+8]
0x180097910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097915  mov     rcx, [rsi+40h]
0x180097919  test    rcx, rcx
0x18009791c  jz      short loc_18009792A
0x18009791e  mov     rax, [rcx]
0x180097921  mov     rax, [rax+10h]
0x180097925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009792a  mov     [rsi+40h], rbx
0x18009792e  mov     [rsp+58h+TokenHandle], r14
0x180097933  call    cs:__imp_GetCurrentProcess
0x180097939  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18009793e  mov     edx, 8; DesiredAccess
0x180097943  mov     rcx, rax; ProcessHandle
0x180097946  call    cs:__imp_OpenProcessToken
0x18009794c  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180097951  test    eax, eax
0x180097953  jnz     short loc_180097967
0x180097955  lea     rax, [rcx-1]
0x180097959  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009795d  ja      short loc_1800979B5
0x18009795f  call    cs:__imp_CloseHandle
0x180097965  jmp     short loc_1800979B5
0x180097967  mov     r9d, 4; TokenInformationLength
0x18009796d  mov     [rsp+58h+TokenInformation], r14d
0x180097972  lea     rax, [rsp+58h+arg_8]
0x180097977  mov     [rsp+58h+arg_8], r14d
0x18009797c  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x180097981  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180097986  lea     edx, [r9+19h]; TokenInformationClass
0x18009798a  call    cs:__imp_GetTokenInformation
0x180097990  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180097995  test    eax, eax
0x180097997  lea     rax, [rcx-1]
0x18009799b  jz      short loc_180097959
0x18009799d  cmp     [rsp+58h+TokenInformation], r14d
0x1800979a2  setnz   bl
0x1800979a5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800979a9  ja      short loc_1800979B1
0x1800979ab  call    cs:__imp_CloseHandle
0x1800979b1  test    bl, bl
0x1800979b3  jnz     short loc_180097A1F
0x1800979b5  mov     rdx, [rdi+18h]; unsigned __int16 *
0x1800979b9  mov     rcx, rsi; this
0x1800979bc  call    ?PinDll@CPinnedDllsPrintTicketService@PrintConfig@@IEAAJPEBG@Z; PrintConfig::CPinnedDllsPrintTicketService::PinDll(ushort const *)
0x1800979c1  mov     ebp, eax
0x1800979c3  test    eax, eax
0x1800979c5  js      short loc_180097A1F
0x1800979c7  mov     rbx, [rdi+38h]
0x1800979cb  test    rbx, rbx
0x1800979ce  jz      short loc_180097A1F
0x1800979d0  cmp     [rbx], r14w
0x1800979d4  jz      short loc_180097A1F
0x1800979d6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800979da  inc     rdi
0x1800979dd  cmp     [rbx+rdi*2], r14w
0x1800979e2  jnz     short loc_1800979DA
0x1800979e4  cmp     edi, 4
0x1800979e7  jle     short loc_180097A11
0x1800979e9  lea     eax, [rdi-4]
0x1800979ec  movsxd  rcx, eax
0x1800979ef  lea     rdx, [rbx+rcx*2]; lpString2
0x1800979f3  lea     rcx, aDll; ".dll"
0x1800979fa  call    cs:__imp_lstrcmpiW
0x180097a00  test    eax, eax
0x180097a02  jnz     short loc_180097A11
0x180097a04  mov     rdx, rbx; unsigned __int16 *
0x180097a07  mov     rcx, rsi; this
0x180097a0a  call    ?PinDll@CPinnedDllsPrintTicketService@PrintConfig@@IEAAJPEBG@Z; PrintConfig::CPinnedDllsPrintTicketService::PinDll(ushort const *)
0x180097a0f  mov     ebp, eax
0x180097a11  lea     eax, [rdi+1]
0x180097a14  movsxd  rcx, eax
0x180097a17  lea     rbx, [rbx+rcx*2]
0x180097a1b  test    ebp, ebp
0x180097a1d  jns     short loc_1800979CB
0x180097a1f  xor     eax, eax
0x180097a21  add     rsp, 30h
0x180097a25  pop     r14
0x180097a27  pop     rdi
0x180097a28  pop     rsi
0x180097a29  pop     rbp
0x180097a2a  pop     rbx
0x180097a2b  retn
```
