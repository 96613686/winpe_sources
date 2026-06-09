# GetRpcClientApplicationPackageInfo

- ea: `0x180086250`
- end: `0x18008638d`
- name: `GetRpcClientApplicationPackageInfo`
- size: `317`
- prototype: `__int64 __fastcall(BackTraceCollection *this)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180085e58`
- `0x1800883e0`
- `0x18008c040`

## callees

- `0x180006e94`
- `0x180007750`
- `0x180086250`
- `0x180086b10`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800862b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086369`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800862b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086369`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800862da`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800862da`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x180086288`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x180086288`

## pseudocode

```c
__int64 __fastcall GetRpcClientApplicationPackageInfo(BackTraceCollection *this)
{
  void **v2; // rax
  int RpcClientThreadToken; // eax
  BackTraceCollection *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v9; // rdi
  LONG ApplicationUserModelIdFromToken; // eax
  BackTraceCollection *v11; // rcx
  __int64 v12; // rax
  WCHAR *v13; // rcx
  BackTraceCollection *v14; // rcx
  HANDLE hObject; // [rsp+30h] [rbp-158h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+38h] [rbp-150h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+40h] [rbp-148h] BYREF

  hObject = 0;
  v2 = (void **)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&hObject);
  RpcClientThreadToken = GetRpcClientThreadToken(8u, v2);
  v5 = RpcClientThreadToken;
  if ( RpcClientThreadToken < 0 )
  {
    BackTraceCollection::Capture(v4, RpcClientThreadToken);
    v7 = 47;
LABEL_3:
    Log_HREvent_31(v5, 1, v6, v7);
    if ( hObject )
      CloseHandle(hObject);
    return v5;
  }
  v9 = 130;
  applicationUserModelIdLength = 130;
  ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                      hObject,
                                      &applicationUserModelIdLength,
                                      applicationUserModelId);
  v5 = ApplicationUserModelIdFromToken;
  if ( ApplicationUserModelIdFromToken > 0 )
    v5 = (unsigned __int16)ApplicationUserModelIdFromToken | 0x80070000;
  if ( (v5 & 0x80000000) != 0 )
  {
    BackTraceCollection::Capture(v11, v5);
    v7 = 52;
    goto LABEL_3;
  }
  v12 = 2147483646;
  v13 = applicationUserModelId;
  do
  {
    if ( !v12 )
      break;
    if ( !*v13 )
      break;
    *(_WORD *)this = *v13++;
    this = (BackTraceCollection *)((char *)this + 2);
    --v12;
    --v9;
  }
  while ( v9 );
  v14 = (BackTraceCollection *)((char *)this - 2);
  v5 = v9 == 0 ? 0x8007007A : 0;
  if ( v9 )
    v14 = this;
  *(_WORD *)v14 = 0;
  if ( !v9 )
  {
    BackTraceCollection::Capture(v14, v5);
    v7 = 54;
    goto LABEL_3;
  }
  if ( hObject )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x180086250  push    rbx
0x180086252  push    rbp
0x180086253  push    rsi
0x180086254  push    rdi
0x180086255  sub     rsp, 168h
0x18008625c  mov     rax, cs:__security_cookie
0x180086263  xor     rax, rsp
0x180086266  mov     [rsp+188h+var_38], rax
0x18008626e  mov     rsi, rcx
0x180086271  xor     ebp, ebp
0x180086273  lea     rcx, [rsp+188h+hObject]
0x180086278  mov     [rsp+188h+hObject], rbp
0x18008627d  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x180086282  mov     rdx, rax
0x180086285  lea     ecx, [rbp+8]
0x180086288  call    cs:__imp_?GetRpcClientThreadToken@@YAJKPEAPEAX@Z; GetRpcClientThreadToken(ulong,void * *)
0x18008628e  mov     ebx, eax
0x180086290  test    eax, eax
0x180086292  jns     short loc_1800862C2
0x180086294  mov     edx, eax; int
0x180086296  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18008629b  lea     r9d, [rbp+2Fh]
0x18008629f  mov     edx, 1
0x1800862a4  mov     ecx, ebx
0x1800862a6  call    Log_HREvent_31
0x1800862ab  mov     rcx, [rsp+188h+hObject]; hObject
0x1800862b0  test    rcx, rcx
0x1800862b3  jz      short loc_1800862BB
0x1800862b5  call    cs:__imp_CloseHandle
0x1800862bb  mov     eax, ebx
0x1800862bd  jmp     loc_180086371
0x1800862c2  mov     rcx, [rsp+188h+hObject]; token
0x1800862c7  lea     r8, [rsp+188h+applicationUserModelId]; applicationUserModelId
0x1800862cc  mov     edi, 82h
0x1800862d1  lea     rdx, [rsp+188h+applicationUserModelIdLength]; applicationUserModelIdLength
0x1800862d6  mov     [rsp+188h+applicationUserModelIdLength], edi
0x1800862da  call    cs:__imp_GetApplicationUserModelIdFromToken
0x1800862e0  mov     ebx, eax
0x1800862e2  test    eax, eax
0x1800862e4  jle     short loc_1800862EF
0x1800862e6  movzx   ebx, ax
0x1800862e9  or      ebx, 80070000h
0x1800862ef  test    ebx, ebx
0x1800862f1  jns     short loc_180086302
0x1800862f3  mov     edx, ebx; int
0x1800862f5  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800862fa  mov     r9d, 34h ; '4'
0x180086300  jmp     short loc_18008629F
0x180086302  mov     eax, 7FFFFFFEh
0x180086307  lea     rcx, [rsp+188h+applicationUserModelId]
0x18008630c  test    rax, rax
0x18008630f  jz      short loc_18008632D
0x180086311  movzx   edx, word ptr [rcx]
0x180086314  test    dx, dx
0x180086317  jz      short loc_18008632D
0x180086319  mov     [rsi], dx
0x18008631c  add     rcx, 2
0x180086320  add     rsi, 2
0x180086324  dec     rax
0x180086327  sub     rdi, 1
0x18008632b  jnz     short loc_18008630C
0x18008632d  mov     rax, rdi
0x180086330  lea     rcx, [rsi-2]
0x180086334  neg     rax
0x180086337  sbb     ebx, ebx
0x180086339  not     ebx
0x18008633b  and     ebx, 8007007Ah
0x180086341  test    rdi, rdi
0x180086344  cmovnz  rcx, rsi; this
0x180086348  mov     [rcx], bp
0x18008634b  jnz     short loc_18008635F
0x18008634d  mov     edx, ebx; int
0x18008634f  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180086354  mov     r9d, 36h ; '6'
0x18008635a  jmp     loc_18008629F
0x18008635f  mov     rcx, [rsp+188h+hObject]; hObject
0x180086364  test    rcx, rcx
0x180086367  jz      short loc_18008636F
0x180086369  call    cs:__imp_CloseHandle
0x18008636f  xor     eax, eax
0x180086371  mov     rcx, [rsp+188h+var_38]
0x180086379  xor     rcx, rsp; StackCookie
0x18008637c  call    __security_check_cookie
0x180086381  add     rsp, 168h
0x180086388  pop     rdi
0x180086389  pop     rsi
0x18008638a  pop     rbp
0x18008638b  pop     rbx
0x18008638c  retn
```
