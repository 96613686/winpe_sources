# FSGetUserToken_Internal(void *,wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &,ulong &)

- ea: `0x18002ee1c`
- end: `0x18002ef2e`
- name: `?FSGetUserToken_Internal@@YAJPEAXAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@AEAK@Z`
- size: `274`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002ed08`

## callees

- `0x180009608`
- `0x180009f50`
- `0x18000a91c`
- `0x180017a3c`
- `0x18002ee1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eede`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002ee4b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002eed4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002ee4b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002eed4`

## pseudocode

```c
__int64 __fastcall FSGetUserToken_Internal(HANDLE TokenHandle, LPVOID *a2, DWORD *a3)
{
  signed int v6; // ebx
  signed int LastError; // eax
  __int64 v8; // rdx
  __int64 unique; // rax
  signed int v10; // eax
  char v12; // [rsp+70h] [rbp+18h] BYREF

  v6 = 0;
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(a2);
  *a3 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, a3) )
    goto LABEL_9;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError != -2147024774 )
    v6 = LastError;
  if ( v6 >= 0 )
  {
LABEL_9:
    unique = wil::make_unique_nothrow<unsigned char [0]>(&v12, *a3);
    wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(a2, unique);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v12);
    if ( *a2 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenUser, *a2, *a3, a3) )
      {
        v10 = GetLastError();
        v6 = v10;
        if ( v10 > 0 )
          v6 = (unsigned __int16)v10 | 0x80070000;
        if ( v6 < 0 && g_wppLevels )
        {
          v8 = 35;
          goto LABEL_18;
        }
      }
    }
    else
    {
      v6 = -2147024882;
      if ( g_wppLevels )
      {
        v8 = 34;
        goto LABEL_18;
      }
    }
  }
  else if ( g_wppLevels >= 8u )
  {
    v8 = 33;
LABEL_18:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002ee1c  push    rbx
0x18002ee1e  push    rbp
0x18002ee1f  push    rsi
0x18002ee20  push    rdi
0x18002ee21  sub     rsp, 38h
0x18002ee25  mov     rbp, rcx
0x18002ee28  mov     rdi, r8
0x18002ee2b  mov     rcx, rdx
0x18002ee2e  mov     rsi, rdx
0x18002ee31  xor     ebx, ebx
0x18002ee33  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18002ee38  xor     r9d, r9d; TokenInformationLength
0x18002ee3b  mov     [rdi], ebx
0x18002ee3d  xor     r8d, r8d; TokenInformation
0x18002ee40  mov     [rsp+58h+ReturnLength], rdi; ReturnLength
0x18002ee45  lea     edx, [rbx+1]; TokenInformationClass
0x18002ee48  mov     rcx, rbp; TokenHandle
0x18002ee4b  call    cs:__imp_GetTokenInformation
0x18002ee51  test    eax, eax
0x18002ee53  jnz     short loc_18002EE87
0x18002ee55  call    cs:__imp_GetLastError
0x18002ee5b  test    eax, eax
0x18002ee5d  jle     short loc_18002EE67
0x18002ee5f  movzx   eax, ax
0x18002ee62  or      eax, 80070000h
0x18002ee67  cmp     eax, 8007007Ah
0x18002ee6c  cmovnz  ebx, eax
0x18002ee6f  test    ebx, ebx
0x18002ee71  jns     short loc_18002EE87
0x18002ee73  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x18002ee7a  jb      loc_18002EF23
0x18002ee80  mov     edx, 21h ; '!'
0x18002ee85  jmp     short loc_18002EF05
0x18002ee87  mov     edx, [rdi]
0x18002ee89  lea     rcx, [rsp+58h+arg_10]
0x18002ee8e  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18002ee93  mov     rdx, rax
0x18002ee96  mov     rcx, rsi
0x18002ee99  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x18002ee9e  lea     rcx, [rsp+58h+arg_10]
0x18002eea3  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18002eea8  mov     r8, [rsi]; TokenInformation
0x18002eeab  test    r8, r8
0x18002eeae  jnz     short loc_18002EEC4
0x18002eeb0  mov     ebx, 8007000Eh
0x18002eeb5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002eebc  jb      short loc_18002EF23
0x18002eebe  lea     edx, [r8+22h]
0x18002eec2  jmp     short loc_18002EF05
0x18002eec4  mov     r9d, [rdi]; TokenInformationLength
0x18002eec7  mov     edx, 1; TokenInformationClass
0x18002eecc  mov     rcx, rbp; TokenHandle
0x18002eecf  mov     [rsp+58h+ReturnLength], rdi; ReturnLength
0x18002eed4  call    cs:__imp_GetTokenInformation
0x18002eeda  test    eax, eax
0x18002eedc  jnz     short loc_18002EF23
0x18002eede  call    cs:__imp_GetLastError
0x18002eee4  mov     ebx, eax
0x18002eee6  test    eax, eax
0x18002eee8  jle     short loc_18002EEF3
0x18002eeea  movzx   ebx, ax
0x18002eeed  or      ebx, 80070000h
0x18002eef3  test    ebx, ebx
0x18002eef5  jns     short loc_18002EF23
0x18002eef7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002eefe  jb      short loc_18002EF23
0x18002ef00  mov     edx, 23h ; '#'
0x18002ef05  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef0c  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18002ef13  xor     r9d, r9d
0x18002ef16  mov     dword ptr [rsp+58h+ReturnLength], ebx
0x18002ef1a  mov     rcx, [rcx+10h]
0x18002ef1e  call    WPP_SF_qD
0x18002ef23  mov     eax, ebx
0x18002ef25  add     rsp, 38h
0x18002ef29  pop     rdi
0x18002ef2a  pop     rsi
0x18002ef2b  pop     rbp
0x18002ef2c  pop     rbx
0x18002ef2d  retn
```
