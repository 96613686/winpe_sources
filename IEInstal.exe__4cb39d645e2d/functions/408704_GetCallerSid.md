# GetCallerSid

- ea: `0x408704`
- end: `0x40883b`
- name: `GetCallerSid`
- size: `311`
- prototype: `int __thiscall(_DWORD *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x408a2f`

## callees

- `0x408704`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x408758`
- `ADVAPI32!GetTokenInformation` at `0x4087ac`
- `ADVAPI32!GetTokenInformation` at `0x408758`
- `ADVAPI32!GetTokenInformation` at `0x4087ac`
- `ADVAPI32!OpenThreadToken` at `0x408736`
- `ADVAPI32!OpenThreadToken` at `0x408736`
- `ADVAPI32!GetLengthSid` at `0x4087ce`
- `ADVAPI32!GetLengthSid` at `0x4087ce`
- `ADVAPI32!IsValidSid` at `0x4087fa`
- `ADVAPI32!IsValidSid` at `0x4087fa`
- `ADVAPI32!CopySid` at `0x4087f3`
- `ADVAPI32!CopySid` at `0x4087f3`
- `KERNEL32!CloseHandle` at `0x408828`
- `KERNEL32!CloseHandle` at `0x408828`
- `KERNEL32!LocalAlloc` at `0x408789`
- `KERNEL32!LocalAlloc` at `0x4087da`
- `KERNEL32!LocalAlloc` at `0x408789`
- `KERNEL32!LocalAlloc` at `0x4087da`
- `KERNEL32!GetCurrentThread` at `0x40872f`
- `KERNEL32!GetCurrentThread` at `0x40872f`
- `KERNEL32!LocalFree` at `0x408811`
- `KERNEL32!LocalFree` at `0x408818`
- `KERNEL32!LocalFree` at `0x408811`
- `KERNEL32!LocalFree` at `0x408818`
- `KERNEL32!GetLastError` at `0x408766`
- `KERNEL32!GetLastError` at `0x4087b6`
- `KERNEL32!GetLastError` at `0x408766`
- `KERNEL32!GetLastError` at `0x4087b6`
- `ole32!CoImpersonateClient` at `0x408713`
- `ole32!CoImpersonateClient` at `0x408713`
- `ole32!CoRevertToSelf` at `0x40882e`
- `ole32!CoRevertToSelf` at `0x40882e`

## pseudocode

```c
int __thiscall GetCallerSid(_DWORD *this)
{
  int v2; // esi
  HANDLE CurrentThread; // eax
  signed int LastError; // eax
  PSID *v5; // ebx
  signed int v6; // eax
  HLOCAL v7; // eax
  void *v8; // edi
  SIZE_T nDestinationSidLength; // [esp+Ch] [ebp-Ch]
  HANDLE TokenHandle; // [esp+10h] [ebp-8h] BYREF
  DWORD ReturnLength; // [esp+14h] [ebp-4h] BYREF

  v2 = CoImpersonateClient();
  if ( v2 >= 0 )
  {
    *this = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    {
      ReturnLength = 0;
      if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &ReturnLength) )
      {
        v2 = -2147418113;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError == 122 )
        {
          v5 = (PSID *)LocalAlloc(0x40u, ReturnLength);
          if ( v5 )
          {
            if ( GetTokenInformation(TokenHandle, TokenUser, v5, ReturnLength, &ReturnLength) )
            {
              nDestinationSidLength = GetLengthSid(*v5);
              v7 = LocalAlloc(0x40u, nDestinationSidLength);
              v8 = v7;
              if ( v7 )
              {
                CopySid(nDestinationSidLength, v7, *v5);
                if ( IsValidSid(v8) )
                {
                  *this = v8;
                }
                else
                {
                  v2 = -2147467259;
                  LocalFree(v8);
                }
              }
              else
              {
                v2 = -2147024882;
              }
            }
            else
            {
              v6 = GetLastError();
              v2 = (unsigned __int16)v6 | 0x80070000;
              if ( v6 <= 0 )
                v2 = v6;
            }
            LocalFree(v5);
          }
          else
          {
            v2 = -2147024882;
          }
        }
        else
        {
          v2 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v2 = LastError;
        }
      }
      CloseHandle(TokenHandle);
    }
    else
    {
      v2 = -2147467259;
    }
    CoRevertToSelf();
  }
  return v2;
}

```

## disassembly

```asm
0x408704  mov     edi, edi
0x408706  push    ebp
0x408707  mov     ebp, esp
0x408709  sub     esp, 10h
0x40870c  push    ebx
0x40870d  mov     ebx, ecx
0x40870f  push    esi
0x408710  mov     [ebp+var_10], ebx
0x408713  call    ds:__imp__CoImpersonateClient@0; CoImpersonateClient()
0x408719  mov     esi, eax
0x40871b  test    esi, esi
0x40871d  js      loc_408835
0x408723  push    edi
0x408724  lea     eax, [ebp+TokenHandle]
0x408727  xor     edi, edi
0x408729  push    eax; TokenHandle
0x40872a  push    edi; OpenAsSelf
0x40872b  push    8; DesiredAccess
0x40872d  mov     [ebx], edi
0x40872f  call    ds:__imp__GetCurrentThread@0; GetCurrentThread()
0x408735  push    eax; ThreadHandle
0x408736  call    ds:__imp__OpenThreadToken@16; OpenThreadToken(x,x,x,x)
0x40873c  test    eax, eax
0x40873e  jnz     short loc_40874A
0x408740  mov     esi, 80004005h
0x408745  jmp     loc_40882E
0x40874a  lea     eax, [ebp+ReturnLength]
0x40874d  mov     [ebp+ReturnLength], edi
0x408750  push    eax; ReturnLength
0x408751  push    edi; TokenInformationLength
0x408752  push    edi; TokenInformation
0x408753  push    1; TokenInformationClass
0x408755  push    [ebp+TokenHandle]; TokenHandle
0x408758  call    ds:__imp__GetTokenInformation@20; GetTokenInformation(x,x,x,x,x)
0x40875e  test    eax, eax
0x408760  jnz     loc_408820
0x408766  call    ds:__imp__GetLastError@0; GetLastError()
0x40876c  cmp     eax, 7Ah ; 'z'
0x40876f  jz      short loc_408784
0x408771  movzx   esi, ax
0x408774  or      esi, 80070000h
0x40877a  test    eax, eax
0x40877c  cmovle  esi, eax
0x40877f  jmp     loc_408825
0x408784  push    [ebp+ReturnLength]; uBytes
0x408787  push    40h ; '@'; uFlags
0x408789  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x40878f  mov     ebx, eax
0x408791  test    ebx, ebx
0x408793  jnz     short loc_40879F
0x408795  mov     esi, 8007000Eh
0x40879a  jmp     loc_408825
0x40879f  lea     eax, [ebp+ReturnLength]
0x4087a2  push    eax; ReturnLength
0x4087a3  push    [ebp+ReturnLength]; TokenInformationLength
0x4087a6  push    ebx; TokenInformation
0x4087a7  push    1; TokenInformationClass
0x4087a9  push    [ebp+TokenHandle]; TokenHandle
0x4087ac  call    ds:__imp__GetTokenInformation@20; GetTokenInformation(x,x,x,x,x)
0x4087b2  test    eax, eax
0x4087b4  jnz     short loc_4087CC
0x4087b6  call    ds:__imp__GetLastError@0; GetLastError()
0x4087bc  movzx   esi, ax
0x4087bf  or      esi, 80070000h
0x4087c5  test    eax, eax
0x4087c7  cmovle  esi, eax
0x4087ca  jmp     short loc_408817
0x4087cc  push    dword ptr [ebx]; pSid
0x4087ce  call    ds:__imp__GetLengthSid@4; GetLengthSid(x)
0x4087d4  push    eax; uBytes
0x4087d5  push    40h ; '@'; uFlags
0x4087d7  mov     [ebp+nDestinationSidLength], eax
0x4087da  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x4087e0  mov     edi, eax
0x4087e2  test    edi, edi
0x4087e4  jnz     short loc_4087ED
0x4087e6  mov     esi, 8007000Eh
0x4087eb  jmp     short loc_408817
0x4087ed  push    dword ptr [ebx]; pSourceSid
0x4087ef  push    edi; pDestinationSid
0x4087f0  push    [ebp+nDestinationSidLength]; nDestinationSidLength
0x4087f3  call    ds:__imp__CopySid@12; CopySid(x,x,x)
0x4087f9  push    edi; pSid
0x4087fa  call    ds:__imp__IsValidSid@4; IsValidSid(x)
0x408800  test    eax, eax
0x408802  jz      short loc_40880B
0x408804  mov     eax, [ebp+var_10]
0x408807  mov     [eax], edi
0x408809  jmp     short loc_408817
0x40880b  push    edi; hMem
0x40880c  mov     esi, 80004005h
0x408811  call    ds:__imp__LocalFree@4; LocalFree(x)
0x408817  push    ebx; hMem
0x408818  call    ds:__imp__LocalFree@4; LocalFree(x)
0x40881e  jmp     short loc_408825
0x408820  mov     esi, 8000FFFFh
0x408825  push    [ebp+TokenHandle]; hObject
0x408828  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x40882e  call    ds:__imp__CoRevertToSelf@0; CoRevertToSelf()
0x408834  pop     edi
0x408835  mov     eax, esi
0x408837  pop     esi
0x408838  pop     ebx
0x408839  leave
0x40883a  retn
```
