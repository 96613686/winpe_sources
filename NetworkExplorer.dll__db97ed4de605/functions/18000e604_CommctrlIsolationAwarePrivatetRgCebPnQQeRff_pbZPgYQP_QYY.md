# CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY

- ea: `0x18000e604`
- end: `0x18000e6c6`
- name: `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY`
- size: `194`
- prototype: `__int64 __fastcall(LPCSTR lpProcName)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e6cc`
- `0x18000e790`
- `0x18000e87c`
- `0x18000e948`
- `0x18000ea20`

## callees

- `0x18000e604`
- `0x18000eaf0`
- `0x18000eb80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e68d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e68d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f584`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e6ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f5a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e6ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f5a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e66d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e66d`
- `KERNEL32!DeactivateActCtx` at `0x18000e6a0`
- `KERNEL32!DeactivateActCtx` at `0x18000f596`
- `KERNEL32!DeactivateActCtx` at `0x18000e6a0`
- `KERNEL32!DeactivateActCtx` at `0x18000f596`

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
0x18000e604  mov     rax, rsp
0x18000e607  mov     [rax+8], rbx
0x18000e60b  mov     [rax+18h], rsi
0x18000e60f  push    rdi
0x18000e610  sub     rsp, 30h
0x18000e614  mov     rsi, rcx
0x18000e617  xor     ebx, ebx
0x18000e619  mov     [rax-10h], rbx
0x18000e61d  xor     edi, edi
0x18000e61f  mov     [rax-18h], edi
0x18000e622  mov     [rax+10h], rbx
0x18000e626  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x18000e62c  jnz     short loc_18000E641
0x18000e62e  lea     rcx, [rax+10h]; lpCookie
0x18000e632  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000e637  mov     edi, eax
0x18000e639  mov     [rsp+38h+var_18], eax
0x18000e63d  test    eax, eax
0x18000e63f  jz      short loc_18000E67B
0x18000e641  mov     rax, cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x18000e648  test    rax, rax
0x18000e64b  jnz     short loc_18000E667
0x18000e64d  xor     ebx, ebx
0x18000e64f  mov     rcx, cs:lpLibFileName; lpLibFileName
0x18000e656  call    IsolationAwarePrivatezlybNQyVOeNelJ
0x18000e65b  test    rax, rax
0x18000e65e  jz      short loc_18000E676
0x18000e660  mov     cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A, rax; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x18000e667  mov     rdx, rsi; lpProcName
0x18000e66a  mov     rcx, rax; hModule
0x18000e66d  call    cs:__imp_GetProcAddress
0x18000e673  mov     rbx, rax
0x18000e676  mov     [rsp+38h+var_10], rbx
0x18000e67b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000e682  jnz     short loc_18000E6B3
0x18000e684  test    edi, edi
0x18000e686  jz      short loc_18000E6B3
0x18000e688  test    rbx, rbx
0x18000e68b  jnz     short loc_18000E697
0x18000e68d  call    cs:__imp_GetLastError
0x18000e693  mov     edi, eax
0x18000e695  jmp     short loc_18000E699
0x18000e697  xor     edi, edi
0x18000e699  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000e69e  xor     ecx, ecx; dwFlags
0x18000e6a0  call    cs:__imp_DeactivateActCtx
0x18000e6a6  test    rbx, rbx
0x18000e6a9  jnz     short loc_18000E6B3
0x18000e6ab  mov     ecx, edi; dwErrCode
0x18000e6ad  call    cs:__imp_SetLastError
0x18000e6b3  mov     rax, rbx
0x18000e6b6  mov     rbx, [rsp+38h+arg_0]
0x18000e6bb  mov     rsi, [rsp+38h+arg_10]
0x18000e6c0  add     rsp, 30h
0x18000e6c4  pop     rdi
0x18000e6c5  retn
0x18000f561  push    rbx
0x18000f563  push    rbp
0x18000f564  push    rdi
0x18000f565  sub     rsp, 20h
0x18000f569  mov     rbp, rdx
0x18000f56c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000f573  jnz     short loc_18000F5AA
0x18000f575  cmp     dword ptr [rbp+20h], 0
0x18000f579  jz      short loc_18000F5AA
0x18000f57b  mov     rbx, [rbp+28h]
0x18000f57f  test    rbx, rbx
0x18000f582  jnz     short loc_18000F58E
0x18000f584  call    cs:__imp_GetLastError
0x18000f58a  mov     edi, eax
0x18000f58c  jmp     short loc_18000F590
0x18000f58e  xor     edi, edi
0x18000f590  mov     rdx, [rbp+48h]; ulCookie
0x18000f594  xor     ecx, ecx; dwFlags
0x18000f596  call    cs:__imp_DeactivateActCtx
0x18000f59c  test    rbx, rbx
0x18000f59f  jnz     short loc_18000F5AA
0x18000f5a1  mov     ecx, edi; dwErrCode
0x18000f5a3  call    cs:__imp_SetLastError
0x18000f5a9  nop
0x18000f5aa  add     rsp, 20h
0x18000f5ae  pop     rdi
0x18000f5af  pop     rbp
0x18000f5b0  pop     rbx
0x18000f5b1  retn
```
