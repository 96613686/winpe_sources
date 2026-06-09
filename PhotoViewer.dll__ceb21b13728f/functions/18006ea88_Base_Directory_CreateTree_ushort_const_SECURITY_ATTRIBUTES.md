# Base::Directory::CreateTree(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18006ea88`
- end: `0x18006eb74`
- name: `?CreateTree@Directory@Base@@SAXPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `236`
- prototype: `void __fastcall(const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003b5dc`

## callees

- `0x1800271ec`
- `0x18003f800`
- `0x18006ea88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006eaef`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006eaef`
- `KERNEL32!CreateDirectoryW` at `0x18006eb2e`
- `KERNEL32!CreateDirectoryW` at `0x18006eb2e`
- `SHLWAPI!PathIsDirectoryW` at `0x18006ead9`
- `SHLWAPI!PathIsDirectoryW` at `0x18006eb02`
- `SHLWAPI!PathIsDirectoryW` at `0x18006ead9`
- `SHLWAPI!PathIsDirectoryW` at `0x18006eb02`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006eb48`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006eb48`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18006eb3c`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18006eb3c`

## pseudocode

```c
void __fastcall Base::Directory::CreateTree(const unsigned __int16 *a1, struct _SECURITY_ATTRIBUTES *a2)
{
  unsigned __int64 v2; // rax
  int v3; // ebx
  BOOL i; // eax
  wchar_t *v5; // rax
  __int64 v6; // rax
  Base *v7; // rcx
  WCHAR pszPath[264]; // [rsp+20h] [rbp-228h] BYREF

  v2 = -1;
  do
    ++v2;
  while ( a1[v2] );
  if ( v2 >= 0x104 )
  {
    Base::Throw((Base *)0x80070057LL, 260);
    __debugbreak();
  }
  v3 = 0;
  StringCchCopyW(pszPath, 0x104u, a1);
  for ( i = PathIsDirectoryW(pszPath); !i; i = PathIsDirectoryW(pszPath) )
  {
    ++v3;
    v5 = wcsrchr(pszPath, 0x5Cu);
    if ( !v5 )
      break;
    *v5 = 0;
  }
  while ( v3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( pszPath[v6] );
    pszPath[v6] = 92;
    if ( !CreateDirectoryW(pszPath, 0) )
    {
      Base::ThrowLastError(v7);
      __debugbreak();
    }
    --v3;
  }
}

```

## disassembly

```asm
0x18006ea88  mov     [rsp+arg_8], rbx
0x18006ea8d  mov     [rsp+arg_10], rbp
0x18006ea92  push    rdi
0x18006ea93  sub     rsp, 240h
0x18006ea9a  mov     rax, cs:__security_cookie
0x18006eaa1  xor     rax, rsp
0x18006eaa4  mov     [rsp+248h+var_18], rax
0x18006eaac  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006eab0  xor     edi, edi
0x18006eab2  inc     rax
0x18006eab5  cmp     [rcx+rax*2], di
0x18006eab9  jnz     short loc_18006EAB2
0x18006eabb  mov     edx, 104h; unsigned __int64
0x18006eac0  cmp     rax, rdx
0x18006eac3  jnb     short loc_18006EB43
0x18006eac5  mov     r8, rcx; unsigned __int16 *
0x18006eac8  mov     ebx, edi
0x18006eaca  lea     rcx, [rsp+248h+pszPath]; unsigned __int16 *
0x18006eacf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006ead4  lea     rcx, [rsp+248h+pszPath]; pszPath
0x18006ead9  call    cs:__imp_PathIsDirectoryW
0x18006eadf  mov     ebp, 5Ch ; '\'
0x18006eae4  jmp     short loc_18006EB08
0x18006eae6  mov     edx, ebp; Ch
0x18006eae8  lea     rcx, [rsp+248h+pszPath]; Str
0x18006eaed  inc     ebx
0x18006eaef  call    cs:__imp_wcsrchr
0x18006eaf5  test    rax, rax
0x18006eaf8  jz      short loc_18006EB0C
0x18006eafa  lea     rcx, [rsp+248h+pszPath]; pszPath
0x18006eaff  mov     [rax], di
0x18006eb02  call    cs:__imp_PathIsDirectoryW
0x18006eb08  test    eax, eax
0x18006eb0a  jz      short loc_18006EAE6
0x18006eb0c  test    ebx, ebx
0x18006eb0e  jz      short loc_18006EB4F
0x18006eb10  lea     rcx, [rsp+248h+pszPath]
0x18006eb15  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006eb19  inc     rax
0x18006eb1c  cmp     [rcx+rax*2], di
0x18006eb20  jnz     short loc_18006EB19
0x18006eb22  xor     edx, edx; lpSecurityAttributes
0x18006eb24  mov     [rsp+rax*2+248h+pszPath], bp
0x18006eb29  lea     rcx, [rsp+248h+pszPath]; lpPathName
0x18006eb2e  call    cs:__imp_CreateDirectoryW
0x18006eb34  test    eax, eax
0x18006eb36  jz      short loc_18006EB3C
0x18006eb38  dec     ebx
0x18006eb3a  jmp     short loc_18006EB0C
0x18006eb3c  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x18006eb42  int     3; Trap to Debugger
0x18006eb43  mov     ecx, 80070057h
0x18006eb48  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006eb4e  int     3; Trap to Debugger
0x18006eb4f  mov     rcx, [rsp+248h+var_18]
0x18006eb57  xor     rcx, rsp; StackCookie
0x18006eb5a  call    __security_check_cookie
0x18006eb5f  lea     r11, [rsp+248h+var_8]
0x18006eb67  mov     rbx, [r11+18h]
0x18006eb6b  mov     rbp, [r11+20h]
0x18006eb6f  mov     rsp, r11
0x18006eb72  pop     rdi
0x18006eb73  retn
```
