# OneCore::Base::Telemetry::OneSettingsQuery::GetCredentialsForBasicProxyIfPresent(ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x18001b8ec`
- end: `0x18001ba17`
- name: `?GetCredentialsForBasicProxyIfPresent@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAG_K12@Z`
- size: `299`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *this, const unsigned __int16 *, unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ae7c`
- `0x180022678`

## callees

- `0x18001b8ec`
- `0x180022f34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b920`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x18001b916`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x18001b916`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18001b9ff`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18001b9ff`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::GetCredentialsForBasicProxyIfPresent(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5)
{
  signed int LastError; // eax
  signed int v7; // ebx
  const unsigned __int16 **v8; // rdx
  unsigned __int16 *v9; // rcx
  unsigned __int64 v10; // rax
  unsigned __int16 *v11; // r9
  __int64 v12; // r8
  unsigned __int16 *v13; // rcx
  int v14; // eax
  PVOID Buffer; // [rsp+48h] [rbp+20h] BYREF

  Buffer = 0;
  if ( CredReadW(a2, 1u, 0, (PCREDENTIALW *)&Buffer) )
  {
    v8 = (const unsigned __int16 **)Buffer;
    v9 = (unsigned __int16 *)*((_QWORD *)Buffer + 5);
    if ( v9 && *((_QWORD *)Buffer + 9) )
    {
      v10 = (unsigned __int64)*((unsigned int *)Buffer + 8) >> 1;
      if ( v10 <= 0x7FFFFFFE )
      {
        v11 = a5;
        v12 = 260;
        do
        {
          if ( !v10 )
            break;
          if ( !*v9 )
            break;
          *v11++ = *v9++;
          --v10;
          --v12;
        }
        while ( v12 );
        v13 = v11 - 1;
        v7 = v12 == 0 ? 0x8007007A : 0;
        if ( v12 )
          v13 = v11;
        *v13 = 0;
        if ( v12 )
        {
          v14 = StringCchCopyW(a3, 0x104u, v8[9]);
          v8 = (const unsigned __int16 **)Buffer;
          v7 = v14;
          if ( v14 >= 0 )
            v7 = 0;
        }
      }
      else
      {
        v7 = -2147024809;
        *a5 = 0;
      }
    }
    else
    {
      v7 = -2147467259;
    }
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = (const unsigned __int16 **)Buffer;
    if ( v7 >= 0 )
      v7 = -2147467259;
  }
  if ( v8 )
    CredFree(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001b8ec  mov     rax, rsp
0x18001b8ef  mov     [rax+8], rbx
0x18001b8f3  mov     [rax+10h], rsi
0x18001b8f7  mov     [rax+20h], r9
0x18001b8fb  push    rdi
0x18001b8fc  sub     rsp, 20h
0x18001b900  xor     esi, esi
0x18001b902  lea     r9, [rax+20h]; Credential
0x18001b906  mov     rdi, r8
0x18001b909  mov     [rax+20h], rsi
0x18001b90d  mov     rcx, rdx; TargetName
0x18001b910  xor     r8d, r8d; Flags
0x18001b913  lea     edx, [rsi+1]; Type
0x18001b916  call    cs:__imp_CredReadW
0x18001b91c  test    eax, eax
0x18001b91e  jnz     short loc_18001B949
0x18001b920  call    cs:__imp_GetLastError
0x18001b926  mov     ebx, eax
0x18001b928  test    eax, eax
0x18001b92a  jle     short loc_18001B935
0x18001b92c  movzx   ebx, ax
0x18001b92f  or      ebx, 80070000h
0x18001b935  mov     rdx, [rsp+28h+Buffer]
0x18001b93a  test    ebx, ebx
0x18001b93c  mov     eax, 80004005h
0x18001b941  cmovns  ebx, eax
0x18001b944  jmp     loc_18001B9F7
0x18001b949  mov     rdx, [rsp+28h+Buffer]
0x18001b94e  mov     rcx, [rdx+28h]
0x18001b952  test    rcx, rcx
0x18001b955  jz      loc_18001B9F2
0x18001b95b  cmp     [rdx+48h], rsi
0x18001b95f  jz      loc_18001B9F2
0x18001b965  mov     eax, [rdx+20h]
0x18001b968  shr     rax, 1
0x18001b96b  cmp     rax, 7FFFFFFEh
0x18001b971  jbe     short loc_18001B982
0x18001b973  mov     rax, [rsp+28h+arg_20]
0x18001b978  mov     ebx, 80070057h
0x18001b97d  mov     [rax], si
0x18001b980  jmp     short loc_18001B9F7
0x18001b982  mov     r9, [rsp+28h+arg_20]
0x18001b987  mov     r11d, 104h
0x18001b98d  mov     r8d, r11d
0x18001b990  test    rax, rax
0x18001b993  jz      short loc_18001B9B4
0x18001b995  movzx   r10d, word ptr [rcx]
0x18001b999  test    r10w, r10w
0x18001b99d  jz      short loc_18001B9B4
0x18001b99f  mov     [r9], r10w
0x18001b9a3  add     rcx, 2
0x18001b9a7  add     r9, 2
0x18001b9ab  dec     rax
0x18001b9ae  sub     r8, 1
0x18001b9b2  jnz     short loc_18001B990
0x18001b9b4  mov     rax, r8
0x18001b9b7  lea     rcx, [r9-2]
0x18001b9bb  neg     rax
0x18001b9be  sbb     ebx, ebx
0x18001b9c0  not     ebx
0x18001b9c2  and     ebx, 8007007Ah
0x18001b9c8  test    r8, r8
0x18001b9cb  cmovnz  rcx, r9
0x18001b9cf  mov     [rcx], si
0x18001b9d2  jz      short loc_18001B9F7
0x18001b9d4  mov     r8, [rdx+48h]; unsigned __int16 *
0x18001b9d8  mov     rcx, rdi; unsigned __int16 *
0x18001b9db  mov     rdx, r11; unsigned __int64
0x18001b9de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b9e3  mov     rdx, [rsp+28h+Buffer]
0x18001b9e8  mov     ebx, eax
0x18001b9ea  test    eax, eax
0x18001b9ec  js      short loc_18001B9F7
0x18001b9ee  mov     ebx, esi
0x18001b9f0  jmp     short loc_18001B9F7
0x18001b9f2  mov     ebx, 80004005h
0x18001b9f7  test    rdx, rdx
0x18001b9fa  jz      short loc_18001BA05
0x18001b9fc  mov     rcx, rdx; Buffer
0x18001b9ff  call    cs:__imp_CredFree
0x18001ba05  mov     rsi, [rsp+28h+arg_8]
0x18001ba0a  mov     eax, ebx
0x18001ba0c  mov     rbx, [rsp+28h+arg_0]
0x18001ba11  add     rsp, 20h
0x18001ba15  pop     rdi
0x18001ba16  retn
```
