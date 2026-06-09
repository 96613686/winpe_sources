# IsolationAwareLoadLibraryExW

- ea: `0x180006d3c`
- end: `0x180006df3`
- name: `IsolationAwareLoadLibraryExW`
- size: `183`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004998`
- `0x180005588`

## callees

- `0x180006d3c`
- `0x180006dfc`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180006d9f`
- `KERNEL32!LoadLibraryExW` at `0x180006d9f`
- `KERNEL32!SetLastError` at `0x180006de8`
- `KERNEL32!SetLastError` at `0x18000afd3`
- `KERNEL32!SetLastError` at `0x180006de8`
- `KERNEL32!SetLastError` at `0x18000afd3`
- `KERNEL32!DeactivateActCtx` at `0x180006ddc`
- `KERNEL32!DeactivateActCtx` at `0x18000afc7`
- `KERNEL32!DeactivateActCtx` at `0x180006ddc`
- `KERNEL32!DeactivateActCtx` at `0x18000afc7`
- `KERNEL32!GetLastError` at `0x180006dc7`
- `KERNEL32!GetLastError` at `0x18000afb3`
- `KERNEL32!GetLastError` at `0x180006dc7`
- `KERNEL32!GetLastError` at `0x18000afb3`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryExW(LPCWSTR lpLibFileName, __int64 a2, DWORD a3)
{
  HMODULE Library; // rax
  HMODULE v7; // rbx
  int v8; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Library = LoadLibraryExW(lpLibFileName, 0, a3);
  v7 = Library;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Library )
    {
      v8 = 0;
      LastError = 0;
    }
    else
    {
      v8 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v8 )
      SetLastError(LastError);
  }
  return v7;
}

```

## disassembly

```asm
0x180006d3c  mov     rax, rsp
0x180006d3f  mov     [rax+8], rbx
0x180006d43  mov     [rax+18h], rsi
0x180006d47  mov     [rax+10h], rdx
0x180006d4b  push    rdi
0x180006d4c  sub     rsp, 30h
0x180006d50  mov     ebx, r8d
0x180006d53  mov     rdi, rcx
0x180006d56  mov     qword ptr [rax-18h], 0
0x180006d5e  mov     qword ptr [rax+10h], 0
0x180006d66  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180006d6d  jnz     short loc_180006D97
0x180006d6f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180006d76  jnz     short loc_180006D97
0x180006d78  lea     rcx, [rax+10h]; lpCookie
0x180006d7c  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180006d81  test    eax, eax
0x180006d83  jnz     short loc_180006D97
0x180006d85  xor     eax, eax
0x180006d87  mov     rbx, [rsp+38h+arg_0]
0x180006d8c  mov     rsi, [rsp+38h+arg_10]
0x180006d91  add     rsp, 30h
0x180006d95  pop     rdi
0x180006d96  retn
0x180006d97  mov     r8d, ebx; dwFlags
0x180006d9a  xor     edx, edx; hFile
0x180006d9c  mov     rcx, rdi; lpLibFileName
0x180006d9f  call    cs:__imp_LoadLibraryExW
0x180006da5  mov     rbx, rax
0x180006da8  mov     [rsp+38h+var_18], rax
0x180006dad  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180006db4  jz      short loc_180006DBF
0x180006db6  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180006dbd  jnz     short loc_180006DEE
0x180006dbf  test    rbx, rbx
0x180006dc2  jnz     short loc_180006DD1
0x180006dc4  lea     esi, [rbx+1]
0x180006dc7  call    cs:__imp_GetLastError
0x180006dcd  mov     edi, eax
0x180006dcf  jmp     short loc_180006DD5
0x180006dd1  xor     esi, esi
0x180006dd3  xor     edi, edi
0x180006dd5  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180006dda  xor     ecx, ecx; dwFlags
0x180006ddc  call    cs:__imp_DeactivateActCtx
0x180006de2  test    esi, esi
0x180006de4  jz      short loc_180006DEE
0x180006de6  mov     ecx, edi; dwErrCode
0x180006de8  call    cs:__imp_SetLastError
0x180006dee  mov     rax, rbx
0x180006df1  jmp     short loc_180006D87
0x18000af8a  push    rbx
0x18000af8c  push    rbp
0x18000af8d  push    rdi
0x18000af8e  sub     rsp, 20h
0x18000af92  mov     rbp, rdx
0x18000af95  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000af9c  jz      short loc_18000AFA7
0x18000af9e  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000afa5  jnz     short loc_18000AFDA
0x18000afa7  cmp     qword ptr [rbp+20h], 0
0x18000afac  jnz     short loc_18000AFBD
0x18000afae  mov     edi, 1
0x18000afb3  call    cs:__imp_GetLastError
0x18000afb9  mov     ebx, eax
0x18000afbb  jmp     short loc_18000AFC1
0x18000afbd  xor     edi, edi
0x18000afbf  xor     ebx, ebx
0x18000afc1  mov     rdx, [rbp+48h]; ulCookie
0x18000afc5  xor     ecx, ecx; dwFlags
0x18000afc7  call    cs:__imp_DeactivateActCtx
0x18000afcd  test    edi, edi
0x18000afcf  jz      short loc_18000AFDA
0x18000afd1  mov     ecx, ebx; dwErrCode
0x18000afd3  call    cs:__imp_SetLastError
0x18000afd9  nop
0x18000afda  add     rsp, 20h
0x18000afde  pop     rdi
0x18000afdf  pop     rbp
0x18000afe0  pop     rbx
0x18000afe1  retn
```
