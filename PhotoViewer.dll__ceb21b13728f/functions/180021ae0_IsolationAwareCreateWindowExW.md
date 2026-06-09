# IsolationAwareCreateWindowExW

- ea: `0x180021ae0`
- end: `0x180021bf9`
- name: `IsolationAwareCreateWindowExW`
- size: `281`
- prototype: `__int64 __fastcall(DWORD dwExStyle, LPCWSTR lpClassName, LPCWSTR lpWindowName, DWORD dwStyle, int, int, int, int, HWND, HMENU, HINSTANCE, ULONG_PTR ulCookie)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800043a4`
- `0x1800210ec`
- `0x180021364`
- `0x18002b768`
- `0x18002c6c0`
- `0x180035650`
- `0x180038164`
- `0x180068764`

## callees

- `0x180021ae0`
- `0x180022af0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180021bbe`
- `KERNEL32!GetLastError` at `0x18007c399`
- `KERNEL32!GetLastError` at `0x180021bbe`
- `KERNEL32!GetLastError` at `0x18007c399`
- `KERNEL32!DeactivateActCtx` at `0x180021bd8`
- `KERNEL32!DeactivateActCtx` at `0x18007c3b0`
- `KERNEL32!DeactivateActCtx` at `0x180021bd8`
- `KERNEL32!DeactivateActCtx` at `0x18007c3b0`
- `KERNEL32!SetLastError` at `0x180021be4`
- `KERNEL32!SetLastError` at `0x18007c3bc`
- `KERNEL32!SetLastError` at `0x180021be4`
- `KERNEL32!SetLastError` at `0x18007c3bc`
- `USER32!CreateWindowExW` at `0x180021b94`
- `USER32!CreateWindowExW` at `0x180021b94`

## pseudocode

```c
HWND __fastcall IsolationAwareCreateWindowExW(
        DWORD dwExStyle,
        LPCWSTR lpClassName,
        LPCWSTR lpWindowName,
        DWORD dwStyle,
        int X,
        int Y,
        int nWidth,
        int nHeight,
        HWND hWndParent,
        HMENU hMenu,
        HINSTANCE hInstance,
        ULONG_PTR ulCookie)
{
  HWND Window; // rax
  HWND v18; // rbx
  int v19; // edi
  DWORD LastError; // esi

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Window = CreateWindowExW(
             dwExStyle,
             lpClassName,
             lpWindowName,
             dwStyle,
             X,
             Y,
             nWidth,
             nHeight,
             hWndParent,
             hMenu,
             hInstance,
             0);
  v18 = Window;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Window )
    {
      v19 = 0;
      LastError = 0;
    }
    else
    {
      v19 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v19 )
      SetLastError(LastError);
  }
  return v18;
}

```

## disassembly

```asm
0x180021ae0  mov     rax, rsp
0x180021ae3  push    rbx
0x180021ae4  push    rsi
0x180021ae5  push    rdi
0x180021ae6  push    r14
0x180021ae8  push    r15
0x180021aea  sub     rsp, 70h
0x180021aee  mov     edi, r9d
0x180021af1  mov     rsi, r8
0x180021af4  mov     r14, rdx
0x180021af7  mov     ebx, ecx
0x180021af9  xor     r15d, r15d
0x180021afc  mov     [rax-38h], r15
0x180021b00  mov     [rax+60h], r15
0x180021b04  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, r15d
0x180021b0b  jnz     short loc_180021B31
0x180021b0d  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, r15d
0x180021b14  jnz     short loc_180021B31
0x180021b16  lea     rcx, [rax+60h]; lpCookie
0x180021b1a  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180021b1f  test    eax, eax
0x180021b21  jnz     short loc_180021B31
0x180021b23  xor     eax, eax
0x180021b25  add     rsp, 70h
0x180021b29  pop     r15
0x180021b2b  pop     r14
0x180021b2d  pop     rdi
0x180021b2e  pop     rsi
0x180021b2f  pop     rbx
0x180021b30  retn
0x180021b31  mov     [rsp+98h+lpParam], r15; lpParam
0x180021b36  mov     rax, [rsp+98h+arg_50]
0x180021b3e  mov     [rsp+98h+hInstance], rax; hInstance
0x180021b43  mov     rax, [rsp+98h+arg_48]
0x180021b4b  mov     [rsp+98h+hMenu], rax; hMenu
0x180021b50  mov     rax, [rsp+98h+arg_40]
0x180021b58  mov     [rsp+98h+hWndParent], rax; hWndParent
0x180021b5d  mov     eax, [rsp+98h+arg_38]
0x180021b64  mov     [rsp+98h+nHeight], eax; nHeight
0x180021b68  mov     eax, [rsp+98h+arg_30]
0x180021b6f  mov     [rsp+98h+nWidth], eax; nWidth
0x180021b73  mov     eax, [rsp+98h+arg_28]
0x180021b7a  mov     [rsp+98h+Y], eax; Y
0x180021b7e  mov     eax, [rsp+98h+arg_20]
0x180021b85  mov     [rsp+98h+X], eax; X
0x180021b89  mov     r9d, edi; dwStyle
0x180021b8c  mov     r8, rsi; lpWindowName
0x180021b8f  mov     rdx, r14; lpClassName
0x180021b92  mov     ecx, ebx; dwExStyle
0x180021b94  call    cs:__imp_CreateWindowExW
0x180021b9a  mov     rbx, rax
0x180021b9d  mov     [rsp+98h+var_38], rax
0x180021ba2  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180021ba9  jz      short loc_180021BB4
0x180021bab  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180021bb2  jnz     short loc_180021BEA
0x180021bb4  test    rbx, rbx
0x180021bb7  jnz     short loc_180021BC8
0x180021bb9  mov     edi, 1
0x180021bbe  call    cs:__imp_GetLastError
0x180021bc4  mov     esi, eax
0x180021bc6  jmp     short loc_180021BCE
0x180021bc8  mov     edi, r15d
0x180021bcb  mov     esi, r15d
0x180021bce  mov     rdx, [rsp+98h+ulCookie]; ulCookie
0x180021bd6  xor     ecx, ecx; dwFlags
0x180021bd8  call    cs:__imp_DeactivateActCtx
0x180021bde  test    edi, edi
0x180021be0  jz      short loc_180021BEA
0x180021be2  mov     ecx, esi; dwErrCode
0x180021be4  call    cs:__imp_SetLastError
0x180021bea  mov     rax, rbx
0x180021bed  add     rsp, 70h
0x180021bf1  pop     r15
0x180021bf3  pop     r14
0x180021bf5  pop     rdi
0x180021bf6  pop     rsi
0x180021bf7  pop     rbx
0x180021bf8  retn
0x18007c370  push    rbx
0x18007c372  push    rbp
0x18007c373  push    rdi
0x18007c374  sub     rsp, 60h
0x18007c378  mov     rbp, rdx
0x18007c37b  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18007c382  jz      short loc_18007C38D
0x18007c384  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18007c38b  jnz     short loc_18007C3C3
0x18007c38d  cmp     qword ptr [rbp+60h], 0
0x18007c392  jnz     short loc_18007C3A3
0x18007c394  mov     edi, 1
0x18007c399  call    cs:__imp_GetLastError
0x18007c39f  mov     ebx, eax
0x18007c3a1  jmp     short loc_18007C3A7
0x18007c3a3  xor     edi, edi
0x18007c3a5  xor     ebx, ebx
0x18007c3a7  mov     rdx, [rbp+0F8h]; ulCookie
0x18007c3ae  xor     ecx, ecx; dwFlags
0x18007c3b0  call    cs:__imp_DeactivateActCtx
0x18007c3b6  test    edi, edi
0x18007c3b8  jz      short loc_18007C3C3
0x18007c3ba  mov     ecx, ebx; dwErrCode
0x18007c3bc  call    cs:__imp_SetLastError
0x18007c3c2  nop
0x18007c3c3  add     rsp, 60h
0x18007c3c7  pop     rdi
0x18007c3c8  pop     rbp
0x18007c3c9  pop     rbx
0x18007c3ca  retn
```
