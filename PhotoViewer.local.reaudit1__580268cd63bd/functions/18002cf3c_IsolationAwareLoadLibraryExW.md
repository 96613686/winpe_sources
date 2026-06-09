# IsolationAwareLoadLibraryExW

- ea: `0x18002cf3c`
- end: `0x18002cff3`
- name: `IsolationAwareLoadLibraryExW`
- size: `183`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002cbc0`
- `0x180043014`
- `0x180043ba4`
- `0x180062c7c`

## callees

- `0x180022af0`
- `0x18002cf3c`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18002cf9f`
- `KERNEL32!LoadLibraryExW` at `0x18002cf9f`
- `KERNEL32!GetLastError` at `0x18002cfc7`
- `KERNEL32!GetLastError` at `0x18007caf2`
- `KERNEL32!GetLastError` at `0x18002cfc7`
- `KERNEL32!GetLastError` at `0x18007caf2`
- `KERNEL32!DeactivateActCtx` at `0x18002cfdc`
- `KERNEL32!DeactivateActCtx` at `0x18007cb06`
- `KERNEL32!DeactivateActCtx` at `0x18002cfdc`
- `KERNEL32!DeactivateActCtx` at `0x18007cb06`
- `KERNEL32!SetLastError` at `0x18002cfe8`
- `KERNEL32!SetLastError` at `0x18007cb12`
- `KERNEL32!SetLastError` at `0x18002cfe8`
- `KERNEL32!SetLastError` at `0x18007cb12`

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
0x18002cf3c  mov     rax, rsp
0x18002cf3f  mov     [rax+8], rbx
0x18002cf43  mov     [rax+18h], rsi
0x18002cf47  mov     [rax+10h], rdx
0x18002cf4b  push    rdi
0x18002cf4c  sub     rsp, 30h
0x18002cf50  mov     ebx, r8d
0x18002cf53  mov     rdi, rcx
0x18002cf56  mov     qword ptr [rax-18h], 0
0x18002cf5e  mov     qword ptr [rax+10h], 0
0x18002cf66  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002cf6d  jnz     short loc_18002CF97
0x18002cf6f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002cf76  jnz     short loc_18002CF97
0x18002cf78  lea     rcx, [rax+10h]; lpCookie
0x18002cf7c  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18002cf81  test    eax, eax
0x18002cf83  jnz     short loc_18002CF97
0x18002cf85  xor     eax, eax
0x18002cf87  mov     rbx, [rsp+38h+arg_0]
0x18002cf8c  mov     rsi, [rsp+38h+arg_10]
0x18002cf91  add     rsp, 30h
0x18002cf95  pop     rdi
0x18002cf96  retn
0x18002cf97  mov     r8d, ebx; dwFlags
0x18002cf9a  xor     edx, edx; hFile
0x18002cf9c  mov     rcx, rdi; lpLibFileName
0x18002cf9f  call    cs:__imp_LoadLibraryExW
0x18002cfa5  mov     rbx, rax
0x18002cfa8  mov     [rsp+38h+var_18], rax
0x18002cfad  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002cfb4  jz      short loc_18002CFBF
0x18002cfb6  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002cfbd  jnz     short loc_18002CFEE
0x18002cfbf  test    rbx, rbx
0x18002cfc2  jnz     short loc_18002CFD1
0x18002cfc4  lea     esi, [rbx+1]
0x18002cfc7  call    cs:__imp_GetLastError
0x18002cfcd  mov     edi, eax
0x18002cfcf  jmp     short loc_18002CFD5
0x18002cfd1  xor     esi, esi
0x18002cfd3  xor     edi, edi
0x18002cfd5  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18002cfda  xor     ecx, ecx; dwFlags
0x18002cfdc  call    cs:__imp_DeactivateActCtx
0x18002cfe2  test    esi, esi
0x18002cfe4  jz      short loc_18002CFEE
0x18002cfe6  mov     ecx, edi; dwErrCode
0x18002cfe8  call    cs:__imp_SetLastError
0x18002cfee  mov     rax, rbx
0x18002cff1  jmp     short loc_18002CF87
0x18007cac9  push    rbx
0x18007cacb  push    rbp
0x18007cacc  push    rdi
0x18007cacd  sub     rsp, 20h
0x18007cad1  mov     rbp, rdx
0x18007cad4  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18007cadb  jz      short loc_18007CAE6
0x18007cadd  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18007cae4  jnz     short loc_18007CB19
0x18007cae6  cmp     qword ptr [rbp+20h], 0
0x18007caeb  jnz     short loc_18007CAFC
0x18007caed  mov     edi, 1
0x18007caf2  call    cs:__imp_GetLastError
0x18007caf8  mov     ebx, eax
0x18007cafa  jmp     short loc_18007CB00
0x18007cafc  xor     edi, edi
0x18007cafe  xor     ebx, ebx
0x18007cb00  mov     rdx, [rbp+48h]; ulCookie
0x18007cb04  xor     ecx, ecx; dwFlags
0x18007cb06  call    cs:__imp_DeactivateActCtx
0x18007cb0c  test    edi, edi
0x18007cb0e  jz      short loc_18007CB19
0x18007cb10  mov     ecx, ebx; dwErrCode
0x18007cb12  call    cs:__imp_SetLastError
0x18007cb18  nop
0x18007cb19  add     rsp, 20h
0x18007cb1d  pop     rdi
0x18007cb1e  pop     rbp
0x18007cb1f  pop     rbx
0x18007cb20  retn
```
