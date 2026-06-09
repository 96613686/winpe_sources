# UstCommon::CImpersonator::Impersonate(void *)

- ea: `0x18005000c`
- end: `0x1800500a3`
- name: `?Impersonate@CImpersonator@UstCommon@@QEAAJPEAX@Z`
- size: `151`
- prototype: `int(UstCommon::CImpersonator *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002fd70`

## callees

- `0x18005000c`
- `0x1800500ac`
- `0x18005020c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050052`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180050041`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180050041`

## pseudocode

```c
__int64 __fastcall UstCommon::CImpersonator::Impersonate(UstCommon::CImpersonator *this, void *a2, __int64 a3)
{
  unsigned int v5; // ebx
  signed int LastError; // eax

  v5 = 1;
  if ( !*(_BYTE *)this && !UstCommon::CImpersonator::_IsThreadImpersonating(this) )
  {
    v5 = -2147024809;
    if ( a2 )
    {
      if ( ImpersonateLoggedOnUser(a2) )
      {
        *(_BYTE *)this = 1;
        v5 = 0;
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, a3, v5);
  return v5;
}

```

## disassembly

```asm
0x18005000c  mov     [rsp+arg_0], rbx
0x180050011  mov     [rsp+arg_8], rsi
0x180050016  push    rdi
0x180050017  sub     rsp, 20h
0x18005001b  cmp     byte ptr [rcx], 0
0x18005001e  mov     rdi, rdx
0x180050021  mov     rsi, rcx
0x180050024  mov     ebx, 1
0x180050029  jnz     short loc_180050067
0x18005002b  call    ?_IsThreadImpersonating@CImpersonator@UstCommon@@AEAA_NXZ; UstCommon::CImpersonator::_IsThreadImpersonating(void)
0x180050030  test    al, al
0x180050032  jnz     short loc_180050067
0x180050034  mov     ebx, 80070057h
0x180050039  test    rdi, rdi
0x18005003c  jz      short loc_180050067
0x18005003e  mov     rcx, rdi; hToken
0x180050041  call    cs:__imp_ImpersonateLoggedOnUser
0x180050047  test    eax, eax
0x180050049  jz      short loc_180050052
0x18005004b  mov     byte ptr [rsi], 1
0x18005004e  xor     ebx, ebx
0x180050050  jmp     short loc_180050067
0x180050052  call    cs:__imp_GetLastError
0x180050058  mov     ebx, eax
0x18005005a  test    eax, eax
0x18005005c  jle     short loc_180050067
0x18005005e  movzx   ebx, ax
0x180050061  or      ebx, 80070000h
0x180050067  mov     rcx, cs:WPP_GLOBAL_Control
0x18005006e  lea     rax, WPP_GLOBAL_Control
0x180050075  cmp     rcx, rax
0x180050078  jz      short loc_180050091
0x18005007a  test    byte ptr [rcx+1Ch], 2
0x18005007e  jz      short loc_180050091
0x180050080  mov     rcx, [rcx+10h]
0x180050084  mov     edx, 0Dh
0x180050089  mov     r9d, ebx
0x18005008c  call    WPP_SF_D
0x180050091  mov     rsi, [rsp+28h+arg_8]
0x180050096  mov     eax, ebx
0x180050098  mov     rbx, [rsp+28h+arg_0]
0x18005009d  add     rsp, 20h
0x1800500a1  pop     rdi
0x1800500a2  retn
```
