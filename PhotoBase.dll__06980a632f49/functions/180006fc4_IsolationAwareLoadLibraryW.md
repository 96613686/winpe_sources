# IsolationAwareLoadLibraryW

- ea: `0x180006fc4`
- end: `0x1800070f4`
- name: `IsolationAwareLoadLibraryW`
- size: `304`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002a24`
- `0x180006d68`
- `0x180006e1c`

## callees

- `0x180006fc4`
- `0x1800070fc`

## import_xrefs

- `KERNEL32!OutputDebugStringA` at `0x180007014`
- `KERNEL32!OutputDebugStringA` at `0x180007014`
- `KERNEL32!ActivateActCtx` at `0x18000704a`
- `KERNEL32!ActivateActCtx` at `0x18000704a`
- `KERNEL32!LoadLibraryW` at `0x1800070a3`
- `KERNEL32!LoadLibraryW` at `0x1800070a3`
- `KERNEL32!DeactivateActCtx` at `0x1800070dd`
- `KERNEL32!DeactivateActCtx` at `0x1800079e0`
- `KERNEL32!DeactivateActCtx` at `0x1800070dd`
- `KERNEL32!DeactivateActCtx` at `0x1800079e0`
- `KERNEL32!SetLastError` at `0x1800070e9`
- `KERNEL32!SetLastError` at `0x1800079ec`
- `KERNEL32!SetLastError` at `0x1800070e9`
- `KERNEL32!SetLastError` at `0x1800079ec`
- `KERNEL32!GetLastError` at `0x18000705e`
- `KERNEL32!GetLastError` at `0x1800070c8`
- `KERNEL32!GetLastError` at `0x1800079cc`
- `KERNEL32!GetLastError` at `0x18000705e`
- `KERNEL32!GetLastError` at `0x1800070c8`
- `KERNEL32!GetLastError` at `0x1800079cc`

## string_xrefs

- `0x18000709c`: `Ntdll.dll`

## pseudocode

```c
HMODULE IsolationAwareLoadLibraryW()
{
  int v0; // eax
  int v1; // ecx
  int v2; // edi
  int v3; // ebx
  DWORD LastError; // eax
  HMODULE LibraryW; // rax
  HMODULE v7; // rdi
  DWORD v8; // esi
  ULONG_PTR Cookie; // [rsp+40h] [rbp+8h] BYREF

  Cookie = 0;
  if ( IsolationAwarePrivateT_SAbnPgpgk )
    goto LABEL_19;
  v0 = IsolationAwarePrivateT_SqbjaYRiRY;
  if ( IsolationAwarePrivateT_SqbjaYRiRY )
    goto LABEL_19;
  v1 = WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ;
  if ( WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ )
  {
    OutputDebugStringA("IsolationAware function called after IsolationAwareCleanup\n");
    v0 = IsolationAwarePrivateT_SqbjaYRiRY;
    v1 = WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ;
  }
  if ( v0 )
  {
LABEL_19:
    v3 = 1;
  }
  else
  {
    v2 = 0;
    if ( v1 || (unsigned int)WinbaseIsolationAwarePrivatetRgzlnPgpgk() )
    {
      v3 = 1;
      if ( ActivateActCtx(WinbaseIsolationAwarePrivateT_UnPgpgk, &Cookie) )
        v2 = 1;
    }
    else
    {
      v3 = 1;
    }
    if ( !v2 )
    {
      LastError = GetLastError();
      if ( LastError - 126 <= 1 || LastError == 120 || LastError == 1 || LastError == 50 )
      {
        IsolationAwarePrivateT_SqbjaYRiRY = 1;
        v2 = 1;
      }
      if ( !v2 )
        return 0;
    }
  }
  LibraryW = LoadLibraryW(L"Ntdll.dll");
  v7 = LibraryW;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( LibraryW )
    {
      v3 = 0;
      v8 = 0;
    }
    else
    {
      v8 = GetLastError();
    }
    DeactivateActCtx(0, Cookie);
    if ( v3 )
      SetLastError(v8);
  }
  return v7;
}

```

## disassembly

```asm
0x180006fc4  mov     rax, rsp
0x180006fc7  mov     [rax+10h], rbx
0x180006fcb  mov     [rax+18h], rsi
0x180006fcf  mov     [rax+8], rcx
0x180006fd3  push    rdi
0x180006fd4  sub     rsp, 30h
0x180006fd8  mov     qword ptr [rax-18h], 0
0x180006fe0  mov     qword ptr [rax+8], 0
0x180006fe8  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180006fef  jnz     loc_180007097
0x180006ff5  mov     eax, cs:IsolationAwarePrivateT_SqbjaYRiRY
0x180006ffb  test    eax, eax
0x180006ffd  jnz     loc_180007097
0x180007003  mov     ecx, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x180007009  test    ecx, ecx
0x18000700b  jz      short loc_180007026
0x18000700d  lea     rcx, ?debugString@?4??IsolationAwarePrivatenPgViNgRzlnPgpgk@@9@4QBDB; "IsolationAware function called after Is"...
0x180007014  call    cs:__imp_OutputDebugStringA
0x18000701a  mov     eax, cs:IsolationAwarePrivateT_SqbjaYRiRY
0x180007020  mov     ecx, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x180007026  test    eax, eax
0x180007028  jnz     short loc_180007097
0x18000702a  xor     edi, edi
0x18000702c  test    ecx, ecx
0x18000702e  jnz     short loc_18000703E
0x180007030  call    WinbaseIsolationAwarePrivatetRgzlnPgpgk
0x180007035  test    eax, eax
0x180007037  jnz     short loc_18000703E
0x180007039  lea     ebx, [rdi+1]
0x18000703c  jmp     short loc_18000705A
0x18000703e  lea     rdx, [rsp+38h+Cookie]; lpCookie
0x180007043  mov     rcx, cs:WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18000704a  call    cs:__imp_ActivateActCtx
0x180007050  mov     ebx, 1
0x180007055  test    eax, eax
0x180007057  cmovnz  edi, ebx
0x18000705a  test    edi, edi
0x18000705c  jnz     short loc_18000709C
0x18000705e  call    cs:__imp_GetLastError
0x180007064  lea     ecx, [rax-7Eh]
0x180007067  cmp     ecx, ebx
0x180007069  jbe     short loc_180007079
0x18000706b  cmp     eax, 78h ; 'x'
0x18000706e  jz      short loc_180007079
0x180007070  cmp     eax, ebx
0x180007072  jz      short loc_180007079
0x180007074  cmp     eax, 32h ; '2'
0x180007077  jnz     short loc_180007081
0x180007079  mov     cs:IsolationAwarePrivateT_SqbjaYRiRY, ebx
0x18000707f  mov     edi, ebx
0x180007081  test    edi, edi
0x180007083  jnz     short loc_18000709C
0x180007085  xor     eax, eax
0x180007087  mov     rbx, [rsp+38h+arg_8]
0x18000708c  mov     rsi, [rsp+38h+arg_10]
0x180007091  add     rsp, 30h
0x180007095  pop     rdi
0x180007096  retn
0x180007097  mov     ebx, 1
0x18000709c  lea     rcx, LibFileName; "Ntdll.dll"
0x1800070a3  call    cs:__imp_LoadLibraryW
0x1800070a9  mov     rdi, rax
0x1800070ac  mov     [rsp+38h+var_18], rax
0x1800070b1  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800070b8  jz      short loc_1800070C3
0x1800070ba  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800070c1  jnz     short loc_1800070EF
0x1800070c3  test    rdi, rdi
0x1800070c6  jnz     short loc_1800070D2
0x1800070c8  call    cs:__imp_GetLastError
0x1800070ce  mov     esi, eax
0x1800070d0  jmp     short loc_1800070D6
0x1800070d2  xor     ebx, ebx
0x1800070d4  xor     esi, esi
0x1800070d6  mov     rdx, [rsp+38h+Cookie]; ulCookie
0x1800070db  xor     ecx, ecx; dwFlags
0x1800070dd  call    cs:__imp_DeactivateActCtx
0x1800070e3  test    ebx, ebx
0x1800070e5  jz      short loc_1800070EF
0x1800070e7  mov     ecx, esi; dwErrCode
0x1800070e9  call    cs:__imp_SetLastError
0x1800070ef  mov     rax, rdi
0x1800070f2  jmp     short loc_180007087
0x1800079a3  push    rbx
0x1800079a5  push    rbp
0x1800079a6  push    rdi
0x1800079a7  sub     rsp, 20h
0x1800079ab  mov     rbp, rdx
0x1800079ae  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800079b5  jz      short loc_1800079C0
0x1800079b7  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800079be  jnz     short loc_1800079F3
0x1800079c0  cmp     qword ptr [rbp+20h], 0
0x1800079c5  jnz     short loc_1800079D6
0x1800079c7  mov     edi, 1
0x1800079cc  call    cs:__imp_GetLastError
0x1800079d2  mov     ebx, eax
0x1800079d4  jmp     short loc_1800079DA
0x1800079d6  xor     edi, edi
0x1800079d8  xor     ebx, ebx
0x1800079da  mov     rdx, [rbp+40h]; ulCookie
0x1800079de  xor     ecx, ecx; dwFlags
0x1800079e0  call    cs:__imp_DeactivateActCtx
0x1800079e6  test    edi, edi
0x1800079e8  jz      short loc_1800079F3
0x1800079ea  mov     ecx, ebx; dwErrCode
0x1800079ec  call    cs:__imp_SetLastError
0x1800079f2  nop
0x1800079f3  add     rsp, 20h
0x1800079f7  pop     rdi
0x1800079f8  pop     rbp
0x1800079f9  pop     rbx
0x1800079fa  retn
```
