# _EncryptOrDecryptSspiAuthenticationBuffer(bool,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18002cf68`
- end: `0x18002d018`
- name: `?_EncryptOrDecryptSspiAuthenticationBuffer@@YAJ_NPEAEKPEAPEAEPEAK@Z`
- size: `176`
- prototype: `int(bool, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002c4f8`

## callees

- `0x18002cf68`

## import_xrefs

- `SspiCli!SspiDecryptAuthIdentityEx` at `0x18002cfd1`
- `SspiCli!SspiDecryptAuthIdentityEx` at `0x18002cfd1`
- `SspiCli!SspiFreeAuthIdentity` at `0x18002cff5`
- `SspiCli!SspiFreeAuthIdentity` at `0x18002d000`
- `SspiCli!SspiFreeAuthIdentity` at `0x18002cff5`
- `SspiCli!SspiFreeAuthIdentity` at `0x18002d000`
- `SspiCli!SspiUnmarshalAuthIdentity` at `0x18002cf9c`
- `SspiCli!SspiUnmarshalAuthIdentity` at `0x18002cf9c`
- `SspiCli!SspiCopyAuthIdentity` at `0x18002cfbb`
- `SspiCli!SspiCopyAuthIdentity` at `0x18002cfbb`
- `SspiCli!SspiMarshalAuthIdentity` at `0x18002cfe8`
- `SspiCli!SspiMarshalAuthIdentity` at `0x18002cfe8`

## pseudocode

```c
__int64 __fastcall _EncryptOrDecryptSspiAuthenticationBuffer(
        __int64 a1,
        char *a2,
        unsigned int a3,
        char **a4,
        unsigned int *AuthDataCopy)
{
  unsigned int *v5; // rsi
  SECURITY_STATUS v7; // ebx
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData; // [rsp+48h] [rbp+20h] BYREF

  v5 = AuthDataCopy;
  *a4 = 0;
  AuthData = 0;
  *v5 = 0;
  v7 = SspiUnmarshalAuthIdentity(a3, a2, &AuthData);
  if ( v7 >= 0 )
  {
    AuthDataCopy = 0;
    v7 = SspiCopyAuthIdentity(AuthData, (PSEC_WINNT_AUTH_IDENTITY_OPAQUE *)&AuthDataCopy);
    if ( v7 >= 0 )
    {
      v7 = SspiDecryptAuthIdentityEx(1u, AuthDataCopy);
      if ( v7 >= 0 )
        v7 = SspiMarshalAuthIdentity(AuthDataCopy, v5, a4);
      SspiFreeAuthIdentity(AuthDataCopy);
    }
    SspiFreeAuthIdentity(AuthData);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002cf68  mov     rax, rsp
0x18002cf6b  mov     [rax+8], rbx
0x18002cf6f  mov     [rax+10h], rsi
0x18002cf73  push    rdi
0x18002cf74  sub     rsp, 20h
0x18002cf78  mov     rsi, [rsp+28h+AuthDataCopy]
0x18002cf7d  mov     ecx, r8d; AuthIdentityLength
0x18002cf80  mov     qword ptr [r9], 0
0x18002cf87  lea     r8, [rax+20h]; ppAuthIdentity
0x18002cf8b  mov     rdi, r9
0x18002cf8e  mov     qword ptr [rax+20h], 0
0x18002cf96  mov     dword ptr [rsi], 0
0x18002cf9c  call    cs:__imp_SspiUnmarshalAuthIdentity
0x18002cfa2  mov     ebx, eax
0x18002cfa4  test    eax, eax
0x18002cfa6  js      short loc_18002D006
0x18002cfa8  mov     rcx, [rsp+28h+AuthData]; AuthData
0x18002cfad  lea     rdx, [rsp+28h+AuthDataCopy]; AuthDataCopy
0x18002cfb2  mov     [rsp+28h+AuthDataCopy], 0
0x18002cfbb  call    cs:__imp_SspiCopyAuthIdentity
0x18002cfc1  mov     ebx, eax
0x18002cfc3  test    eax, eax
0x18002cfc5  js      short loc_18002CFFB
0x18002cfc7  mov     rdx, [rsp+28h+AuthDataCopy]; EncryptedAuthData
0x18002cfcc  mov     ecx, 1; Options
0x18002cfd1  call    cs:__imp_SspiDecryptAuthIdentityEx
0x18002cfd7  mov     ebx, eax
0x18002cfd9  test    eax, eax
0x18002cfdb  js      short loc_18002CFF0
0x18002cfdd  mov     rcx, [rsp+28h+AuthDataCopy]; AuthIdentity
0x18002cfe2  mov     r8, rdi; AuthIdentityByteArray
0x18002cfe5  mov     rdx, rsi; AuthIdentityLength
0x18002cfe8  call    cs:__imp_SspiMarshalAuthIdentity
0x18002cfee  mov     ebx, eax
0x18002cff0  mov     rcx, [rsp+28h+AuthDataCopy]; AuthData
0x18002cff5  call    cs:__imp_SspiFreeAuthIdentity
0x18002cffb  mov     rcx, [rsp+28h+AuthData]; AuthData
0x18002d000  call    cs:__imp_SspiFreeAuthIdentity
0x18002d006  mov     rsi, [rsp+28h+arg_8]
0x18002d00b  mov     eax, ebx
0x18002d00d  mov     rbx, [rsp+28h+arg_0]
0x18002d012  add     rsp, 20h
0x18002d016  pop     rdi
0x18002d017  retn
```
