# CallerIdentity::GetPackageSidFromProcessToken(void *,void * *)

- ea: `0x14001ddec`
- end: `0x14001df15`
- name: `?GetPackageSidFromProcessToken@CallerIdentity@@YAJPEAXPEAPEAX@Z`
- size: `297`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, _QWORD *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001dd70`

## callees

- `0x140013600`
- `0x14001ddec`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x14001de18`
- `ADVAPI32!GetTokenInformation` at `0x14001de89`
- `ADVAPI32!GetTokenInformation` at `0x14001de18`
- `ADVAPI32!GetTokenInformation` at `0x14001de89`
- `KERNEL32!GetLastError` at `0x14001de2c`
- `KERNEL32!GetLastError` at `0x14001de2c`
- `KERNEL32!LocalFree` at `0x14001defa`
- `KERNEL32!LocalFree` at `0x14001df03`
- `KERNEL32!LocalFree` at `0x14001defa`
- `KERNEL32!LocalFree` at `0x14001df03`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14001dead`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14001dead`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14001ded9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14001ded9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001de57`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001debc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001de57`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001debc`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageSidFromProcessToken(HANDLE TokenHandle, _QWORD *a2, void **a3)
{
  signed int Error; // ebx
  signed int LastError; // eax
  PSID *v7; // rdi
  DWORD LengthSid; // ebx
  HLOCAL v9; // rax
  void *v10; // rsi
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) )
    return (unsigned int)-2147418113;
  LastError = GetLastError();
  Error = LastError;
  if ( LastError == 122 )
    goto LABEL_24;
  if ( LastError > 0 )
    Error = (unsigned __int16)LastError | 0x80070000;
  if ( Error >= 0 )
  {
LABEL_24:
    v7 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( !v7 )
      return (unsigned int)-2147024882;
    if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, v7, TokenInformationLength, &TokenInformationLength)
      || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      if ( *v7 )
      {
        LengthSid = GetLengthSid(*v7);
        v9 = LocalAlloc(0x40u, LengthSid);
        v10 = v9;
        if ( v9 )
        {
          if ( CopySid(LengthSid, v9, *v7) )
          {
            Error = 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
            if ( Error < 0 )
            {
              LocalFree(v10);
              goto LABEL_20;
            }
          }
          *a2 = v10;
        }
        else
        {
          Error = -2147024882;
        }
      }
      else
      {
        Error = -2147023728;
      }
LABEL_20:
      LocalFree(v7);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x14001ddec  push    rbx
0x14001ddee  push    rsi
0x14001ddef  push    rdi
0x14001ddf0  push    r14
0x14001ddf2  sub     rsp, 38h
0x14001ddf6  xor     r9d, r9d; TokenInformationLength
0x14001ddf9  mov     [rsp+58h+TokenInformationLength], 0
0x14001de01  mov     r14, rdx
0x14001de04  lea     rax, [rsp+58h+TokenInformationLength]
0x14001de09  xor     r8d, r8d; TokenInformation
0x14001de0c  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x14001de11  mov     rsi, rcx
0x14001de14  lea     edx, [r9+1Fh]; TokenInformationClass
0x14001de18  call    cs:__imp_GetTokenInformation
0x14001de1e  test    eax, eax
0x14001de20  jz      short loc_14001DE2C
0x14001de22  mov     ebx, 8000FFFFh
0x14001de27  jmp     loc_14001DF09
0x14001de2c  call    cs:__imp_GetLastError
0x14001de32  mov     ebx, eax
0x14001de34  cmp     eax, 7Ah ; 'z'
0x14001de37  jz      short loc_14001DE4E
0x14001de39  test    eax, eax
0x14001de3b  jle     short loc_14001DE46
0x14001de3d  movzx   ebx, ax
0x14001de40  or      ebx, 80070000h
0x14001de46  test    ebx, ebx
0x14001de48  js      loc_14001DF09
0x14001de4e  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x14001de52  mov     ecx, 40h ; '@'; uFlags
0x14001de57  call    cs:__imp_LocalAlloc
0x14001de5d  mov     rdi, rax
0x14001de60  test    rax, rax
0x14001de63  jnz     short loc_14001DE6F
0x14001de65  mov     ebx, 8007000Eh
0x14001de6a  jmp     loc_14001DF09
0x14001de6f  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x14001de74  lea     rax, [rsp+58h+TokenInformationLength]
0x14001de79  mov     r8, rdi; TokenInformation
0x14001de7c  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x14001de81  mov     edx, 1Fh; TokenInformationClass
0x14001de86  mov     rcx, rsi; TokenHandle
0x14001de89  call    cs:__imp_GetTokenInformation
0x14001de8f  test    eax, eax
0x14001de91  jnz     short loc_14001DE9E
0x14001de93  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001de98  mov     ebx, eax
0x14001de9a  test    eax, eax
0x14001de9c  js      short loc_14001DF09
0x14001de9e  mov     rcx, [rdi]; pSid
0x14001dea1  test    rcx, rcx
0x14001dea4  jnz     short loc_14001DEAD
0x14001dea6  mov     ebx, 80070490h
0x14001deab  jmp     short loc_14001DF00
0x14001dead  call    cs:__imp_GetLengthSid
0x14001deb3  mov     edx, eax; uBytes
0x14001deb5  mov     ecx, 40h ; '@'; uFlags
0x14001deba  mov     ebx, eax
0x14001debc  call    cs:__imp_LocalAlloc
0x14001dec2  mov     rsi, rax
0x14001dec5  test    rax, rax
0x14001dec8  jnz     short loc_14001DED1
0x14001deca  mov     ebx, 8007000Eh
0x14001decf  jmp     short loc_14001DF00
0x14001ded1  mov     r8, [rdi]; pSourceSid
0x14001ded4  mov     rdx, rsi; pDestinationSid
0x14001ded7  mov     ecx, ebx; nDestinationSidLength
0x14001ded9  call    cs:__imp_CopySid
0x14001dedf  test    eax, eax
0x14001dee1  jz      short loc_14001DEE7
0x14001dee3  xor     ebx, ebx
0x14001dee5  jmp     short loc_14001DEF2
0x14001dee7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001deec  mov     ebx, eax
0x14001deee  test    eax, eax
0x14001def0  js      short loc_14001DEF7
0x14001def2  mov     [r14], rsi
0x14001def5  jmp     short loc_14001DF00
0x14001def7  mov     rcx, rsi; hMem
0x14001defa  call    cs:__imp_LocalFree
0x14001df00  mov     rcx, rdi; hMem
0x14001df03  call    cs:__imp_LocalFree
0x14001df09  mov     eax, ebx
0x14001df0b  add     rsp, 38h
0x14001df0f  pop     r14
0x14001df11  pop     rdi
0x14001df12  pop     rsi
0x14001df13  pop     rbx
0x14001df14  retn
```
