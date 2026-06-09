# CRsopContext::GetExclusiveLoggingAccess(int)

- ea: `0x1800295b4`
- end: `0x180029623`
- name: `?GetExclusiveLoggingAccess@CRsopContext@@QEAAJH@Z`
- size: `111`
- prototype: `__int64 __fastcall(CRsopContext *this, BOOL)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002310`
- `0x18000239c`
- `0x180002d40`
- `0x180011fc0`

## callees

- `0x1800295b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295df`
- `USERENV!EnterCriticalPolicySection` at `0x1800295d0`
- `USERENV!EnterCriticalPolicySection` at `0x1800295d0`

## pseudocode

```c
__int64 __fastcall CRsopContext::GetExclusiveLoggingAccess(CRsopContext *this, BOOL a2)
{
  signed int v2; // ebx
  HANDLE v4; // rax
  signed int LastError; // eax
  signed int *v6; // rax

  v2 = 0;
  if ( *((_DWORD *)this + 8) )
  {
    if ( *((_DWORD *)this + 9) == 2 )
    {
      v4 = EnterCriticalPolicySection(a2);
      *((_QWORD *)this + 8) = v4;
      if ( !v4 )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        if ( v2 >= 0 )
          v2 = -2147467259;
        if ( *((_DWORD *)this + 8) )
        {
          v6 = (signed int *)*((_QWORD *)this + 5);
          if ( v6 )
            *v6 = v2;
        }
        *((_DWORD *)this + 8) = 0;
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800295b4  mov     [rsp+arg_0], rbx
0x1800295b9  push    rdi
0x1800295ba  sub     rsp, 20h
0x1800295be  xor     ebx, ebx
0x1800295c0  mov     rdi, rcx
0x1800295c3  cmp     [rcx+20h], ebx
0x1800295c6  jz      short loc_180029616
0x1800295c8  cmp     dword ptr [rcx+24h], 2
0x1800295cc  jnz     short loc_180029616
0x1800295ce  mov     ecx, edx; bMachine
0x1800295d0  call    cs:__imp_EnterCriticalPolicySection
0x1800295d6  mov     [rdi+40h], rax
0x1800295da  test    rax, rax
0x1800295dd  jnz     short loc_180029616
0x1800295df  call    cs:__imp_GetLastError
0x1800295e5  mov     ebx, eax
0x1800295e7  test    eax, eax
0x1800295e9  jle     short loc_1800295F4
0x1800295eb  movzx   ebx, ax
0x1800295ee  or      ebx, 80070000h
0x1800295f4  test    ebx, ebx
0x1800295f6  mov     eax, 80004005h
0x1800295fb  cmovns  ebx, eax
0x1800295fe  cmp     dword ptr [rdi+20h], 0
0x180029602  jz      short loc_18002960F
0x180029604  mov     rax, [rdi+28h]
0x180029608  test    rax, rax
0x18002960b  jz      short loc_18002960F
0x18002960d  mov     [rax], ebx
0x18002960f  mov     dword ptr [rdi+20h], 0
0x180029616  mov     eax, ebx
0x180029618  mov     rbx, [rsp+28h+arg_0]
0x18002961d  add     rsp, 20h
0x180029621  pop     rdi
0x180029622  retn
```
