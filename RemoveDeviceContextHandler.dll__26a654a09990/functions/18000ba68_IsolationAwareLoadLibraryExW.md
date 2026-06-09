# IsolationAwareLoadLibraryExW

- ea: `0x18000ba68`
- end: `0x18000bb1f`
- name: `IsolationAwareLoadLibraryExW`
- size: `183`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007948`
- `0x1800096c8`

## callees

- `0x18000ba68`
- `0x18000bb28`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000bacb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000bacb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000baf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000baf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce1d`
- `KERNEL32!DeactivateActCtx` at `0x18000bb08`
- `KERNEL32!DeactivateActCtx` at `0x18000ce31`
- `KERNEL32!DeactivateActCtx` at `0x18000bb08`
- `KERNEL32!DeactivateActCtx` at `0x18000ce31`

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
0x18000ba68  mov     rax, rsp
0x18000ba6b  mov     [rax+8], rbx
0x18000ba6f  mov     [rax+18h], rsi
0x18000ba73  mov     [rax+10h], rdx
0x18000ba77  push    rdi
0x18000ba78  sub     rsp, 30h
0x18000ba7c  mov     ebx, r8d
0x18000ba7f  mov     rdi, rcx
0x18000ba82  mov     qword ptr [rax-18h], 0
0x18000ba8a  mov     qword ptr [rax+10h], 0
0x18000ba92  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000ba99  jnz     short loc_18000BAC3
0x18000ba9b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000baa2  jnz     short loc_18000BAC3
0x18000baa4  lea     rcx, [rax+10h]; lpCookie
0x18000baa8  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000baad  test    eax, eax
0x18000baaf  jnz     short loc_18000BAC3
0x18000bab1  xor     eax, eax
0x18000bab3  mov     rbx, [rsp+38h+arg_0]
0x18000bab8  mov     rsi, [rsp+38h+arg_10]
0x18000babd  add     rsp, 30h
0x18000bac1  pop     rdi
0x18000bac2  retn
0x18000bac3  mov     r8d, ebx; dwFlags
0x18000bac6  xor     edx, edx; hFile
0x18000bac8  mov     rcx, rdi; lpLibFileName
0x18000bacb  call    cs:__imp_LoadLibraryExW
0x18000bad1  mov     rbx, rax
0x18000bad4  mov     [rsp+38h+var_18], rax
0x18000bad9  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000bae0  jz      short loc_18000BAEB
0x18000bae2  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000bae9  jnz     short loc_18000BB1A
0x18000baeb  test    rbx, rbx
0x18000baee  jnz     short loc_18000BAFD
0x18000baf0  lea     esi, [rbx+1]
0x18000baf3  call    cs:__imp_GetLastError
0x18000baf9  mov     edi, eax
0x18000bafb  jmp     short loc_18000BB01
0x18000bafd  xor     esi, esi
0x18000baff  xor     edi, edi
0x18000bb01  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000bb06  xor     ecx, ecx; dwFlags
0x18000bb08  call    cs:__imp_DeactivateActCtx
0x18000bb0e  test    esi, esi
0x18000bb10  jz      short loc_18000BB1A
0x18000bb12  mov     ecx, edi; dwErrCode
0x18000bb14  call    cs:__imp_SetLastError
0x18000bb1a  mov     rax, rbx
0x18000bb1d  jmp     short loc_18000BAB3
0x18000cdf4  push    rbx
0x18000cdf6  push    rbp
0x18000cdf7  push    rdi
0x18000cdf8  sub     rsp, 20h
0x18000cdfc  mov     rbp, rdx
0x18000cdff  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000ce06  jz      short loc_18000CE11
0x18000ce08  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000ce0f  jnz     short loc_18000CE44
0x18000ce11  cmp     qword ptr [rbp+20h], 0
0x18000ce16  jnz     short loc_18000CE27
0x18000ce18  mov     edi, 1
0x18000ce1d  call    cs:__imp_GetLastError
0x18000ce23  mov     ebx, eax
0x18000ce25  jmp     short loc_18000CE2B
0x18000ce27  xor     edi, edi
0x18000ce29  xor     ebx, ebx
0x18000ce2b  mov     rdx, [rbp+48h]; ulCookie
0x18000ce2f  xor     ecx, ecx; dwFlags
0x18000ce31  call    cs:__imp_DeactivateActCtx
0x18000ce37  test    edi, edi
0x18000ce39  jz      short loc_18000CE44
0x18000ce3b  mov     ecx, ebx; dwErrCode
0x18000ce3d  call    cs:__imp_SetLastError
0x18000ce43  nop
0x18000ce44  add     rsp, 20h
0x18000ce48  pop     rdi
0x18000ce49  pop     rbp
0x18000ce4a  pop     rbx
0x18000ce4b  retn
```
