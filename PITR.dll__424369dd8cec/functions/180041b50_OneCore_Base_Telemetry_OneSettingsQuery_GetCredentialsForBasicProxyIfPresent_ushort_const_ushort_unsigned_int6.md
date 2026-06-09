# OneCore::Base::Telemetry::OneSettingsQuery::GetCredentialsForBasicProxyIfPresent(ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x180041b50`
- end: `0x180041c7b`
- name: `?GetCredentialsForBasicProxyIfPresent@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAG_K12@Z`
- size: `299`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *this, const unsigned __int16 *, unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004175c`
- `0x1800467b8`

## callees

- `0x18001c548`
- `0x180041b50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041b84`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x180041c63`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x180041c63`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x180041b7a`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x180041b7a`

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
0x180041b50  mov     rax, rsp
0x180041b53  mov     [rax+8], rbx
0x180041b57  mov     [rax+10h], rsi
0x180041b5b  mov     [rax+20h], r9
0x180041b5f  push    rdi
0x180041b60  sub     rsp, 20h
0x180041b64  xor     esi, esi
0x180041b66  lea     r9, [rax+20h]; Credential
0x180041b6a  mov     rdi, r8
0x180041b6d  mov     [rax+20h], rsi
0x180041b71  mov     rcx, rdx; TargetName
0x180041b74  xor     r8d, r8d; Flags
0x180041b77  lea     edx, [rsi+1]; Type
0x180041b7a  call    cs:__imp_CredReadW
0x180041b80  test    eax, eax
0x180041b82  jnz     short loc_180041BAD
0x180041b84  call    cs:__imp_GetLastError
0x180041b8a  mov     ebx, eax
0x180041b8c  test    eax, eax
0x180041b8e  jle     short loc_180041B99
0x180041b90  movzx   ebx, ax
0x180041b93  or      ebx, 80070000h
0x180041b99  mov     rdx, [rsp+28h+Buffer]
0x180041b9e  test    ebx, ebx
0x180041ba0  mov     eax, 80004005h
0x180041ba5  cmovns  ebx, eax
0x180041ba8  jmp     loc_180041C5B
0x180041bad  mov     rdx, [rsp+28h+Buffer]
0x180041bb2  mov     rcx, [rdx+28h]
0x180041bb6  test    rcx, rcx
0x180041bb9  jz      loc_180041C56
0x180041bbf  cmp     [rdx+48h], rsi
0x180041bc3  jz      loc_180041C56
0x180041bc9  mov     eax, [rdx+20h]
0x180041bcc  shr     rax, 1
0x180041bcf  cmp     rax, 7FFFFFFEh
0x180041bd5  jbe     short loc_180041BE6
0x180041bd7  mov     rax, [rsp+28h+arg_20]
0x180041bdc  mov     ebx, 80070057h
0x180041be1  mov     [rax], si
0x180041be4  jmp     short loc_180041C5B
0x180041be6  mov     r9, [rsp+28h+arg_20]
0x180041beb  mov     r11d, 104h
0x180041bf1  mov     r8d, r11d
0x180041bf4  test    rax, rax
0x180041bf7  jz      short loc_180041C18
0x180041bf9  movzx   r10d, word ptr [rcx]
0x180041bfd  test    r10w, r10w
0x180041c01  jz      short loc_180041C18
0x180041c03  mov     [r9], r10w
0x180041c07  add     rcx, 2
0x180041c0b  add     r9, 2
0x180041c0f  dec     rax
0x180041c12  sub     r8, 1
0x180041c16  jnz     short loc_180041BF4
0x180041c18  mov     rax, r8
0x180041c1b  lea     rcx, [r9-2]
0x180041c1f  neg     rax
0x180041c22  sbb     ebx, ebx
0x180041c24  not     ebx
0x180041c26  and     ebx, 8007007Ah
0x180041c2c  test    r8, r8
0x180041c2f  cmovnz  rcx, r9
0x180041c33  mov     [rcx], si
0x180041c36  jz      short loc_180041C5B
0x180041c38  mov     r8, [rdx+48h]; unsigned __int16 *
0x180041c3c  mov     rcx, rdi; unsigned __int16 *
0x180041c3f  mov     rdx, r11; unsigned __int64
0x180041c42  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041c47  mov     rdx, [rsp+28h+Buffer]
0x180041c4c  mov     ebx, eax
0x180041c4e  test    eax, eax
0x180041c50  js      short loc_180041C5B
0x180041c52  mov     ebx, esi
0x180041c54  jmp     short loc_180041C5B
0x180041c56  mov     ebx, 80004005h
0x180041c5b  test    rdx, rdx
0x180041c5e  jz      short loc_180041C69
0x180041c60  mov     rcx, rdx; Buffer
0x180041c63  call    cs:__imp_CredFree
0x180041c69  mov     rsi, [rsp+28h+arg_8]
0x180041c6e  mov     eax, ebx
0x180041c70  mov     rbx, [rsp+28h+arg_0]
0x180041c75  add     rsp, 20h
0x180041c79  pop     rdi
0x180041c7a  retn
```
