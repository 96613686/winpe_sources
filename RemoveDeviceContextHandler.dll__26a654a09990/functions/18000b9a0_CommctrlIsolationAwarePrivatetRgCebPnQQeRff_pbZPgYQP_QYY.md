# CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY

- ea: `0x18000b9a0`
- end: `0x18000ba62`
- name: `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY`
- size: `194`
- prototype: `__int64 __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bbd0`
- `0x18000bcf4`

## callees

- `0x18000b9a0`
- `0x18000bb28`
- `0x18000bbc0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ba09`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ba09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cdde`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cdde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdbf`
- `KERNEL32!DeactivateActCtx` at `0x18000ba3c`
- `KERNEL32!DeactivateActCtx` at `0x18000cdd1`
- `KERNEL32!DeactivateActCtx` at `0x18000ba3c`
- `KERNEL32!DeactivateActCtx` at `0x18000cdd1`

## pseudocode

```c
FARPROC __fastcall CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY(LPCSTR lpProcName)
{
  FARPROC ProcAddress; // rbx
  int v3; // edi
  HMODULE v4; // rax
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ProcAddress = 0;
  v3 = 0;
  ulCookie = 0;
  if ( IsolationAwarePrivateT_SqbjaYRiRY || (v3 = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie)) != 0 )
  {
    v4 = `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m;
    if ( `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m )
    {
LABEL_6:
      ProcAddress = GetProcAddress(v4, lpProcName);
      goto LABEL_7;
    }
    ProcAddress = 0;
    v4 = IsolationAwarePrivatezlybNQyVOeNelJ(L"Comctl32.dll");
    if ( v4 )
    {
      `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m = v4;
      goto LABEL_6;
    }
  }
LABEL_7:
  if ( !IsolationAwarePrivateT_SqbjaYRiRY && v3 )
  {
    if ( ProcAddress )
      LastError = 0;
    else
      LastError = GetLastError();
    DeactivateActCtx(0, ulCookie);
    if ( !ProcAddress )
      SetLastError(LastError);
  }
  return ProcAddress;
}

```

## disassembly

```asm
0x18000b9a0  mov     rax, rsp
0x18000b9a3  mov     [rax+8], rbx
0x18000b9a7  mov     [rax+18h], rsi
0x18000b9ab  push    rdi
0x18000b9ac  sub     rsp, 30h
0x18000b9b0  mov     rsi, rcx
0x18000b9b3  xor     ebx, ebx
0x18000b9b5  mov     [rax-10h], rbx
0x18000b9b9  xor     edi, edi
0x18000b9bb  mov     [rax-18h], edi
0x18000b9be  mov     [rax+10h], rbx
0x18000b9c2  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x18000b9c8  jnz     short loc_18000B9DD
0x18000b9ca  lea     rcx, [rax+10h]; lpCookie
0x18000b9ce  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000b9d3  mov     edi, eax
0x18000b9d5  mov     [rsp+38h+var_18], eax
0x18000b9d9  test    eax, eax
0x18000b9db  jz      short loc_18000BA17
0x18000b9dd  mov     rax, cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x18000b9e4  test    rax, rax
0x18000b9e7  jnz     short loc_18000BA03
0x18000b9e9  xor     ebx, ebx
0x18000b9eb  mov     rcx, cs:lpLibFileName; lpLibFileName
0x18000b9f2  call    IsolationAwarePrivatezlybNQyVOeNelJ
0x18000b9f7  test    rax, rax
0x18000b9fa  jz      short loc_18000BA12
0x18000b9fc  mov     cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A, rax; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x18000ba03  mov     rdx, rsi; lpProcName
0x18000ba06  mov     rcx, rax; hModule
0x18000ba09  call    cs:__imp_GetProcAddress
0x18000ba0f  mov     rbx, rax
0x18000ba12  mov     [rsp+38h+var_10], rbx
0x18000ba17  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000ba1e  jnz     short loc_18000BA4F
0x18000ba20  test    edi, edi
0x18000ba22  jz      short loc_18000BA4F
0x18000ba24  test    rbx, rbx
0x18000ba27  jnz     short loc_18000BA33
0x18000ba29  call    cs:__imp_GetLastError
0x18000ba2f  mov     edi, eax
0x18000ba31  jmp     short loc_18000BA35
0x18000ba33  xor     edi, edi
0x18000ba35  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000ba3a  xor     ecx, ecx; dwFlags
0x18000ba3c  call    cs:__imp_DeactivateActCtx
0x18000ba42  test    rbx, rbx
0x18000ba45  jnz     short loc_18000BA4F
0x18000ba47  mov     ecx, edi; dwErrCode
0x18000ba49  call    cs:__imp_SetLastError
0x18000ba4f  mov     rax, rbx
0x18000ba52  mov     rbx, [rsp+38h+arg_0]
0x18000ba57  mov     rsi, [rsp+38h+arg_10]
0x18000ba5c  add     rsp, 30h
0x18000ba60  pop     rdi
0x18000ba61  retn
0x18000cd9c  push    rbx
0x18000cd9e  push    rbp
0x18000cd9f  push    rdi
0x18000cda0  sub     rsp, 20h
0x18000cda4  mov     rbp, rdx
0x18000cda7  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000cdae  jnz     short loc_18000CDE5
0x18000cdb0  cmp     dword ptr [rbp+20h], 0
0x18000cdb4  jz      short loc_18000CDE5
0x18000cdb6  mov     rbx, [rbp+28h]
0x18000cdba  test    rbx, rbx
0x18000cdbd  jnz     short loc_18000CDC9
0x18000cdbf  call    cs:__imp_GetLastError
0x18000cdc5  mov     edi, eax
0x18000cdc7  jmp     short loc_18000CDCB
0x18000cdc9  xor     edi, edi
0x18000cdcb  mov     rdx, [rbp+48h]; ulCookie
0x18000cdcf  xor     ecx, ecx; dwFlags
0x18000cdd1  call    cs:__imp_DeactivateActCtx
0x18000cdd7  test    rbx, rbx
0x18000cdda  jnz     short loc_18000CDE5
0x18000cddc  mov     ecx, edi; dwErrCode
0x18000cdde  call    cs:__imp_SetLastError
0x18000cde4  nop
0x18000cde5  add     rsp, 20h
0x18000cde9  pop     rdi
0x18000cdea  pop     rbp
0x18000cdeb  pop     rbx
0x18000cdec  retn
```
