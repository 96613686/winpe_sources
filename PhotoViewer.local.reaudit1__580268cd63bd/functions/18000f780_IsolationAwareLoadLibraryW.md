# IsolationAwareLoadLibraryW

- ea: `0x18000f780`
- end: `0x18000f899`
- name: `IsolationAwareLoadLibraryW`
- size: `281`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f5f0`
- `0x18002cbc0`
- `0x180077270`

## callees

- `0x18000f780`
- `0x180023d18`

## import_xrefs

- `KERNEL32!OutputDebugStringA` at `0x18000f848`
- `KERNEL32!OutputDebugStringA` at `0x18000f848`
- `KERNEL32!ActivateActCtx` at `0x18000f809`
- `KERNEL32!ActivateActCtx` at `0x18000f809`
- `KERNEL32!LoadLibraryW` at `0x18000f7ae`
- `KERNEL32!LoadLibraryW` at `0x18000f7ae`
- `KERNEL32!GetLastError` at `0x18000f81a`
- `KERNEL32!GetLastError` at `0x18000f865`
- `KERNEL32!GetLastError` at `0x18007be89`
- `KERNEL32!GetLastError` at `0x18000f81a`
- `KERNEL32!GetLastError` at `0x18000f865`
- `KERNEL32!GetLastError` at `0x18007be89`
- `KERNEL32!DeactivateActCtx` at `0x18000f829`
- `KERNEL32!DeactivateActCtx` at `0x18007be9d`
- `KERNEL32!DeactivateActCtx` at `0x18000f829`
- `KERNEL32!DeactivateActCtx` at `0x18007be9d`
- `KERNEL32!SetLastError` at `0x18000f835`
- `KERNEL32!SetLastError` at `0x18007bea9`
- `KERNEL32!SetLastError` at `0x18000f835`
- `KERNEL32!SetLastError` at `0x18007bea9`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryW(LPCWSTR lpLibFileName)
{
  DWORD v2; // esi
  int v3; // edi
  HMODULE LibraryW; // rax
  HMODULE v5; // rbx
  int v7; // eax
  int v8; // ecx
  DWORD LastError; // eax
  ULONG_PTR Cookie; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  Cookie = 0;
  if ( IsolationAwarePrivateT_SAbnPgpgk )
    goto LABEL_2;
  v7 = IsolationAwarePrivateT_SqbjaYRiRY;
  if ( IsolationAwarePrivateT_SqbjaYRiRY )
    goto LABEL_2;
  v8 = WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ;
  if ( WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ )
  {
    OutputDebugStringA("IsolationAware function called after IsolationAwareCleanup\n");
    v7 = IsolationAwarePrivateT_SqbjaYRiRY;
    v8 = WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ;
  }
  if ( v7
    || (v8 || (unsigned int)WinbaseIsolationAwarePrivatetRgzlnPgpgk())
    && ActivateActCtx(WinbaseIsolationAwarePrivateT_UnPgpgk, &Cookie) )
  {
LABEL_2:
    v3 = 1;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 120 && LastError != 50 && LastError != 1 && LastError - 126 > 1 )
      return 0;
    v3 = 1;
    IsolationAwarePrivateT_SqbjaYRiRY = 1;
  }
  LibraryW = LoadLibraryW(lpLibFileName);
  v5 = LibraryW;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( LibraryW )
      v3 = 0;
    else
      v2 = GetLastError();
    DeactivateActCtx(0, Cookie);
    if ( v3 )
      SetLastError(v2);
  }
  return v5;
}

```

## disassembly

```asm
0x18000f780  mov     [rsp+arg_0], rbx
0x18000f785  mov     [rsp+arg_10], rsi
0x18000f78a  push    rdi
0x18000f78b  sub     rsp, 30h
0x18000f78f  mov     rbx, rcx
0x18000f792  xor     esi, esi
0x18000f794  mov     [rsp+38h+var_18], rsi
0x18000f799  mov     [rsp+38h+Cookie], rsi
0x18000f79e  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, esi
0x18000f7a4  jz      short loc_18000F7E1
0x18000f7a6  mov     edi, 1
0x18000f7ab  mov     rcx, rbx; lpLibFileName
0x18000f7ae  call    cs:__imp_LoadLibraryW
0x18000f7b4  mov     rbx, rax
0x18000f7b7  mov     [rsp+38h+var_18], rax
0x18000f7bc  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000f7c3  jz      short loc_18000F815
0x18000f7c5  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000f7cc  jz      short loc_18000F815
0x18000f7ce  mov     rax, rbx
0x18000f7d1  mov     rbx, [rsp+38h+arg_0]
0x18000f7d6  mov     rsi, [rsp+38h+arg_10]
0x18000f7db  add     rsp, 30h
0x18000f7df  pop     rdi
0x18000f7e0  retn
0x18000f7e1  mov     eax, cs:IsolationAwarePrivateT_SqbjaYRiRY
0x18000f7e7  test    eax, eax
0x18000f7e9  jnz     short loc_18000F7A6
0x18000f7eb  mov     ecx, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x18000f7f1  test    ecx, ecx
0x18000f7f3  jnz     short loc_18000F841
0x18000f7f5  test    eax, eax
0x18000f7f7  jnz     short loc_18000F7A6
0x18000f7f9  test    ecx, ecx
0x18000f7fb  jz      short loc_18000F85C
0x18000f7fd  lea     rdx, [rsp+38h+Cookie]; lpCookie
0x18000f802  mov     rcx, cs:WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18000f809  call    cs:__imp_ActivateActCtx
0x18000f80f  test    eax, eax
0x18000f811  jnz     short loc_18000F7A6
0x18000f813  jmp     short loc_18000F865
0x18000f815  test    rbx, rbx
0x18000f818  jnz     short loc_18000F83D
0x18000f81a  call    cs:__imp_GetLastError
0x18000f820  mov     esi, eax
0x18000f822  mov     rdx, [rsp+38h+Cookie]; ulCookie
0x18000f827  xor     ecx, ecx; dwFlags
0x18000f829  call    cs:__imp_DeactivateActCtx
0x18000f82f  test    edi, edi
0x18000f831  jz      short loc_18000F7CE
0x18000f833  mov     ecx, esi; dwErrCode
0x18000f835  call    cs:__imp_SetLastError
0x18000f83b  jmp     short loc_18000F7CE
0x18000f83d  mov     edi, esi
0x18000f83f  jmp     short loc_18000F822
0x18000f841  lea     rcx, ?debugString@?4??IsolationAwarePrivatenPgViNgRzlnPgpgk@@9@4QBDB; "IsolationAware function called after Is"...
0x18000f848  call    cs:__imp_OutputDebugStringA
0x18000f84e  mov     eax, cs:IsolationAwarePrivateT_SqbjaYRiRY
0x18000f854  mov     ecx, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x18000f85a  jmp     short loc_18000F7F5
0x18000f85c  call    WinbaseIsolationAwarePrivatetRgzlnPgpgk
0x18000f861  test    eax, eax
0x18000f863  jnz     short loc_18000F7FD
0x18000f865  call    cs:__imp_GetLastError
0x18000f86b  cmp     eax, 78h ; 'x'
0x18000f86e  jz      short loc_18000F889
0x18000f870  cmp     eax, 32h ; '2'
0x18000f873  jz      short loc_18000F889
0x18000f875  cmp     eax, 1
0x18000f878  jz      short loc_18000F889
0x18000f87a  add     eax, 0FFFFFF82h
0x18000f87d  cmp     eax, 1
0x18000f880  jbe     short loc_18000F889
0x18000f882  xor     eax, eax
0x18000f884  jmp     loc_18000F7D1
0x18000f889  mov     edi, 1
0x18000f88e  mov     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x18000f894  jmp     loc_18000F7AB
0x18007be60  push    rbx
0x18007be62  push    rbp
0x18007be63  push    rdi
0x18007be64  sub     rsp, 20h
0x18007be68  mov     rbp, rdx
0x18007be6b  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18007be72  jz      short loc_18007BE7D
0x18007be74  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18007be7b  jnz     short loc_18007BEB0
0x18007be7d  cmp     qword ptr [rbp+20h], 0
0x18007be82  jnz     short loc_18007BE93
0x18007be84  mov     edi, 1
0x18007be89  call    cs:__imp_GetLastError
0x18007be8f  mov     ebx, eax
0x18007be91  jmp     short loc_18007BE97
0x18007be93  xor     edi, edi
0x18007be95  xor     ebx, ebx
0x18007be97  mov     rdx, [rbp+48h]; ulCookie
0x18007be9b  xor     ecx, ecx; dwFlags
0x18007be9d  call    cs:__imp_DeactivateActCtx
0x18007bea3  test    edi, edi
0x18007bea5  jz      short loc_18007BEB0
0x18007bea7  mov     ecx, ebx; dwErrCode
0x18007bea9  call    cs:__imp_SetLastError
0x18007beaf  nop
0x18007beb0  add     rsp, 20h
0x18007beb4  pop     rdi
0x18007beb5  pop     rbp
0x18007beb6  pop     rbx
0x18007beb7  retn
```
