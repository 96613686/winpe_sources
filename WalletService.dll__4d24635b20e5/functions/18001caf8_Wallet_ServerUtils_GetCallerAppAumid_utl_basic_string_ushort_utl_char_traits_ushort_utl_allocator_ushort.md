# Wallet::ServerUtils::GetCallerAppAumid(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x18001caf8`
- end: `0x18001cc49`
- name: `?GetCallerAppAumid@ServerUtils@Wallet@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001cdf8`

## callees

- `0x18001400c`
- `0x18001caf8`
- `0x180043052`
- `0x180043090`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001cb84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001cb84`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001cb9b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001cb9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cbad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cbad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc25`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001cba3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001cba3`
- `RPCRT4!RpcImpersonateClient` at `0x18001cb6a`
- `RPCRT4!RpcImpersonateClient` at `0x18001cb6a`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18001cbd3`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18001cbd3`

## pseudocode

```c
__int64 __fastcall Wallet::ServerUtils::GetCallerAppAumid(__int64 a1)
{
  unsigned int v2; // edi
  int LastError; // eax
  HANDLE CurrentThread; // rax
  BOOL v5; // ebx
  bool v6; // sf
  __int64 v7; // r8
  char v8; // al
  int v9; // ecx
  UINT32 applicationUserModelIdLength; // [rsp+20h] [rbp-158h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-150h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+30h] [rbp-148h] BYREF

  TokenHandle = 0;
  v2 = 0;
  memset_0(applicationUserModelId, 0, 0x104u);
  applicationUserModelIdLength = 130;
  if ( g_fUnitTestContext )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             a1,
                             &sourceString) )
      v2 = -2147024882;
    goto LABEL_21;
  }
  LastError = RpcImpersonateClient(0);
  if ( LastError )
  {
    if ( LastError > 0 )
      goto LABEL_6;
    goto LABEL_15;
  }
  CurrentThread = GetCurrentThread();
  v5 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
  RevertToSelf();
  if ( !v5 )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( !LastError )
    {
      v2 = -2143748092;
      goto LABEL_21;
    }
    if ( LastError <= 0 )
      goto LABEL_21;
LABEL_6:
    v2 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_21;
  }
  LastError = GetApplicationUserModelIdFromToken(TokenHandle, &applicationUserModelIdLength, applicationUserModelId);
  v6 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = LastError < 0;
  }
  if ( v6 )
  {
LABEL_15:
    v2 = LastError;
    goto LABEL_21;
  }
  v7 = -1;
  do
    ++v7;
  while ( applicationUserModelId[v7] );
  v8 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
         a1,
         applicationUserModelId);
  v9 = 0;
  if ( !v8 )
    v9 = -2147024882;
  v2 = v9;
LABEL_21:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v2;
}

```

## disassembly

```asm
0x18001caf8  push    rbx
0x18001cafa  push    rbp
0x18001cafb  push    rsi
0x18001cafc  push    rdi
0x18001cafd  sub     rsp, 158h
0x18001cb04  mov     rax, cs:__security_cookie
0x18001cb0b  xor     rax, rsp
0x18001cb0e  mov     [rsp+178h+var_38], rax
0x18001cb16  mov     rsi, rcx
0x18001cb19  xor     ebp, ebp
0x18001cb1b  lea     rcx, [rsp+178h+applicationUserModelId]; void *
0x18001cb20  mov     [rsp+178h+TokenHandle], rbp
0x18001cb25  xor     edx, edx; Val
0x18001cb27  mov     r8d, 104h; Size
0x18001cb2d  mov     edi, ebp
0x18001cb2f  call    memset_0
0x18001cb34  cmp     cs:?g_fUnitTestContext@@3HA, ebp; int g_fUnitTestContext
0x18001cb3a  mov     [rsp+178h+applicationUserModelIdLength], 82h
0x18001cb42  jz      short loc_18001CB68
0x18001cb44  xor     r8d, r8d
0x18001cb47  lea     rdx, sourceString
0x18001cb4e  mov     rcx, rsi
0x18001cb51  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18001cb56  test    al, al
0x18001cb58  jnz     loc_18001CC1B
0x18001cb5e  mov     edi, 8007000Eh
0x18001cb63  jmp     loc_18001CC1B
0x18001cb68  xor     ecx, ecx; BindingHandle
0x18001cb6a  call    cs:__imp_RpcImpersonateClient
0x18001cb70  test    eax, eax
0x18001cb72  jz      short loc_18001CB84
0x18001cb74  jle     short loc_18001CBE9
0x18001cb76  movzx   edi, ax
0x18001cb79  or      edi, 80070000h
0x18001cb7f  jmp     loc_18001CC1B
0x18001cb84  call    cs:__imp_GetCurrentThread
0x18001cb8a  mov     edx, 8; DesiredAccess
0x18001cb8f  lea     r9, [rsp+178h+TokenHandle]; TokenHandle
0x18001cb94  mov     rcx, rax; ThreadHandle
0x18001cb97  lea     r8d, [rdx-7]; OpenAsSelf
0x18001cb9b  call    cs:__imp_OpenThreadToken
0x18001cba1  mov     ebx, eax
0x18001cba3  call    cs:__imp_RevertToSelf
0x18001cba9  test    ebx, ebx
0x18001cbab  jnz     short loc_18001CBC4
0x18001cbad  call    cs:__imp_GetLastError
0x18001cbb3  mov     edi, eax
0x18001cbb5  test    eax, eax
0x18001cbb7  jz      short loc_18001CBBD
0x18001cbb9  jle     short loc_18001CC1B
0x18001cbbb  jmp     short loc_18001CB76
0x18001cbbd  mov     edi, 80390004h
0x18001cbc2  jmp     short loc_18001CC1B
0x18001cbc4  mov     rcx, [rsp+178h+TokenHandle]; token
0x18001cbc9  lea     r8, [rsp+178h+applicationUserModelId]; applicationUserModelId
0x18001cbce  lea     rdx, [rsp+178h+applicationUserModelIdLength]; applicationUserModelIdLength
0x18001cbd3  call    cs:__imp_GetApplicationUserModelIdFromToken
0x18001cbd9  test    eax, eax
0x18001cbdb  jle     short loc_18001CBE7
0x18001cbdd  movzx   eax, ax
0x18001cbe0  or      eax, 80070000h
0x18001cbe5  test    eax, eax
0x18001cbe7  jns     short loc_18001CBED
0x18001cbe9  mov     edi, eax
0x18001cbeb  jmp     short loc_18001CC1B
0x18001cbed  lea     rax, [rsp+178h+applicationUserModelId]
0x18001cbf2  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001cbf6  inc     r8
0x18001cbf9  cmp     [rax+r8*2], bp
0x18001cbfe  jnz     short loc_18001CBF6
0x18001cc00  lea     rdx, [rsp+178h+applicationUserModelId]
0x18001cc05  mov     rcx, rsi
0x18001cc08  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18001cc0d  mov     edi, 8007000Eh
0x18001cc12  test    al, al
0x18001cc14  mov     ecx, ebp
0x18001cc16  cmovz   ecx, edi
0x18001cc19  mov     edi, ecx
0x18001cc1b  mov     rcx, [rsp+178h+TokenHandle]; hObject
0x18001cc20  test    rcx, rcx
0x18001cc23  jz      short loc_18001CC2B
0x18001cc25  call    cs:__imp_CloseHandle
0x18001cc2b  mov     eax, edi
0x18001cc2d  mov     rcx, [rsp+178h+var_38]
0x18001cc35  xor     rcx, rsp; StackCookie
0x18001cc38  call    __security_check_cookie
0x18001cc3d  add     rsp, 158h
0x18001cc44  pop     rdi
0x18001cc45  pop     rsi
0x18001cc46  pop     rbp
0x18001cc47  pop     rbx
0x18001cc48  retn
```
