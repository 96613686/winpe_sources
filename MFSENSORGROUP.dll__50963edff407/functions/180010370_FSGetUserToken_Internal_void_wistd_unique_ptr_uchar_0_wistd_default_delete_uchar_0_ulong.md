# FSGetUserToken_Internal(void *,wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &,ulong &)

- ea: `0x180010370`
- end: `0x1800104a8`
- name: `?FSGetUserToken_Internal@@YAJPEAXAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@AEAK@Z`
- size: `312`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPVOID *, DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010218`

## callees

- `0x180005fa0`
- `0x18000f5a0`
- `0x180010370`
- `0x180044b28`
- `0x180045300`
- `0x180045900`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001044c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001044c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800103a4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010428`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800103a4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010428`

## pseudocode

```c
__int64 __fastcall FSGetUserToken_Internal(HANDLE TokenHandle, LPVOID *a2, DWORD *a3)
{
  signed int v6; // ebx
  signed int LastError; // eax
  __int64 v8; // rdx
  DWORD v9; // ebp
  void *v10; // rax
  void *v11; // rdi
  void *v12; // rcx
  signed int v14; // eax

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
    v9 = *a3;
    v10 = operator new[](*a3, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( v10 )
      memset_0(v10, 0, v9);
    else
      v11 = 0;
    v12 = *a2;
    *a2 = v11;
    if ( v12 )
      operator delete(v12);
    if ( !*a2 )
    {
      v6 = -2147024882;
      if ( !g_wppLevels )
        return (unsigned int)v6;
      v8 = 34;
      goto LABEL_22;
    }
    if ( !GetTokenInformation(TokenHandle, TokenUser, *a2, *a3, a3) )
    {
      v14 = GetLastError();
      v6 = v14;
      if ( v14 > 0 )
        v6 = (unsigned __int16)v14 | 0x80070000;
      if ( v6 < 0 && g_wppLevels )
      {
        v8 = 35;
        goto LABEL_22;
      }
    }
  }
  else if ( g_wppLevels >= 8u )
  {
    v8 = 33;
LABEL_22:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180010370  push    rbx
0x180010372  push    rbp
0x180010373  push    rsi
0x180010374  push    rdi
0x180010375  push    r14
0x180010377  push    r15
0x180010379  sub     rsp, 38h
0x18001037d  mov     r15, rcx
0x180010380  mov     r14, r8
0x180010383  mov     rcx, rdx
0x180010386  mov     rsi, rdx
0x180010389  xor     ebx, ebx
0x18001038b  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180010390  xor     r9d, r9d; TokenInformationLength
0x180010393  mov     [r14], ebx
0x180010396  xor     r8d, r8d; TokenInformation
0x180010399  mov     [rsp+68h+ReturnLength], r14; ReturnLength
0x18001039e  lea     edx, [rbx+1]; TokenInformationClass
0x1800103a1  mov     rcx, r15; TokenHandle
0x1800103a4  call    cs:__imp_GetTokenInformation
0x1800103aa  test    eax, eax
0x1800103ac  jnz     short loc_1800103DF
0x1800103ae  call    cs:__imp_GetLastError
0x1800103b4  test    eax, eax
0x1800103b6  jle     short loc_1800103C0
0x1800103b8  movzx   eax, ax
0x1800103bb  or      eax, 80070000h
0x1800103c0  cmp     eax, 8007007Ah
0x1800103c5  cmovnz  ebx, eax
0x1800103c8  test    ebx, ebx
0x1800103ca  jns     short loc_1800103DF
0x1800103cc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1800103d3  jb      short loc_180010432
0x1800103d5  mov     edx, 21h ; '!'
0x1800103da  jmp     loc_180010473
0x1800103df  mov     ebp, [r14]
0x1800103e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800103e9  mov     ecx, ebp; unsigned __int64
0x1800103eb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800103f0  mov     rdi, rax
0x1800103f3  test    rax, rax
0x1800103f6  jz      short loc_180010441
0x1800103f8  mov     r8d, ebp; Size
0x1800103fb  xor     edx, edx; Val
0x1800103fd  mov     rcx, rax; void *
0x180010400  call    memset_0
0x180010405  mov     rcx, [rsi]; Block
0x180010408  mov     [rsi], rdi
0x18001040b  test    rcx, rcx
0x18001040e  jnz     short loc_180010445
0x180010410  mov     r8, [rsi]; TokenInformation
0x180010413  test    r8, r8
0x180010416  jz      short loc_180010493
0x180010418  mov     r9d, [r14]; TokenInformationLength
0x18001041b  mov     edx, 1; TokenInformationClass
0x180010420  mov     rcx, r15; TokenHandle
0x180010423  mov     [rsp+68h+ReturnLength], r14; ReturnLength
0x180010428  call    cs:__imp_GetTokenInformation
0x18001042e  test    eax, eax
0x180010430  jz      short loc_18001044C
0x180010432  mov     eax, ebx
0x180010434  add     rsp, 38h
0x180010438  pop     r15
0x18001043a  pop     r14
0x18001043c  pop     rdi
0x18001043d  pop     rsi
0x18001043e  pop     rbp
0x18001043f  pop     rbx
0x180010440  retn
0x180010441  xor     edi, edi
0x180010443  jmp     short loc_180010405
0x180010445  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001044a  jmp     short loc_180010410
0x18001044c  call    cs:__imp_GetLastError
0x180010452  mov     ebx, eax
0x180010454  test    eax, eax
0x180010456  jle     short loc_180010461
0x180010458  movzx   ebx, ax
0x18001045b  or      ebx, 80070000h
0x180010461  test    ebx, ebx
0x180010463  jns     short loc_180010432
0x180010465  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001046c  jb      short loc_180010432
0x18001046e  mov     edx, 23h ; '#'
0x180010473  mov     rcx, cs:WPP_GLOBAL_Control
0x18001047a  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180010481  xor     r9d, r9d
0x180010484  mov     dword ptr [rsp+68h+ReturnLength], ebx
0x180010488  mov     rcx, [rcx+10h]
0x18001048c  call    WPP_SF_qD
0x180010491  jmp     short loc_180010432
0x180010493  mov     ebx, 8007000Eh
0x180010498  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001049f  jb      short loc_180010432
0x1800104a1  mov     edx, 22h ; '"'
0x1800104a6  jmp     short loc_180010473
```
