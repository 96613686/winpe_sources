# ImpersonateConsoleUser(void * *)

- ea: `0x18001d914`
- end: `0x18001d9a1`
- name: `?ImpersonateConsoleUser@@YAKPEAPEAX@Z`
- size: `141`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d7b4`
- `0x18002ba80`

## callees

- `0x18001d914`
- `0x18001d9b0`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001d92f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001d92f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d966`

## pseudocode

```c
__int64 __fastcall ImpersonateConsoleUser(void **a1)
{
  DWORD LastError; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx

  LastError = DupConsoleUserToken(a1);
  if ( LastError )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v5 = 15;
LABEL_10:
      WPP_SF_d(v4[2], v5, WPP_78b059fac4093813b2646cef9913e025_Traceguids, LastError);
    }
  }
  else if ( !ImpersonateLoggedOnUser(*a1) )
  {
    LastError = GetLastError();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v5 = 16;
      goto LABEL_10;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18001d914  mov     [rsp+arg_0], rbx
0x18001d919  push    rdi
0x18001d91a  sub     rsp, 20h
0x18001d91e  mov     rdi, rcx
0x18001d921  call    ?DupConsoleUserToken@@YAKPEAPEAX@Z; DupConsoleUserToken(void * *)
0x18001d926  mov     ebx, eax
0x18001d928  test    eax, eax
0x18001d92a  jnz     short loc_18001D946
0x18001d92c  mov     rcx, [rdi]; hToken
0x18001d92f  call    cs:__imp_ImpersonateLoggedOnUser
0x18001d935  test    eax, eax
0x18001d937  jz      short loc_18001D966
0x18001d939  mov     eax, ebx
0x18001d93b  mov     rbx, [rsp+28h+arg_0]
0x18001d940  add     rsp, 20h
0x18001d944  pop     rdi
0x18001d945  retn
0x18001d946  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d94d  lea     rax, WPP_GLOBAL_Control
0x18001d954  cmp     rcx, rax
0x18001d957  jz      short loc_18001D939
0x18001d959  test    byte ptr [rcx+1Ch], 2
0x18001d95d  jz      short loc_18001D939
0x18001d95f  mov     edx, 0Fh
0x18001d964  jmp     short loc_18001D98C
0x18001d966  call    cs:__imp_GetLastError
0x18001d96c  mov     ebx, eax
0x18001d96e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d975  lea     rax, WPP_GLOBAL_Control
0x18001d97c  cmp     rcx, rax
0x18001d97f  jz      short loc_18001D939
0x18001d981  test    byte ptr [rcx+1Ch], 2
0x18001d985  jz      short loc_18001D939
0x18001d987  mov     edx, 10h
0x18001d98c  mov     rcx, [rcx+10h]
0x18001d990  lea     r8, WPP_78b059fac4093813b2646cef9913e025_Traceguids
0x18001d997  mov     r9d, ebx
0x18001d99a  call    WPP_SF_d
0x18001d99f  jmp     short loc_18001D939
```
