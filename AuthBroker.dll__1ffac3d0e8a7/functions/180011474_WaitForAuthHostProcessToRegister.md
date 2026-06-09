# _WaitForAuthHostProcessToRegister

- ea: `0x180011474`
- end: `0x180011620`
- name: `_WaitForAuthHostProcessToRegister`
- size: `428`
- prototype: `HRESULT __fastcall(void *appContainerSid, void *processHandle, const wchar_t *authHostIdString)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ed84`

## callees

- `0x180004940`
- `0x1800053f8`
- `0x18000737c`
- `0x180011474`
- `0x180011b30`
- `0x180020520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001152d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001152d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011544`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011544`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800115f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800115f5`
- `api-ms-win-security-appcontainer-l1-1-0!GetAppContainerNamedObjectPath` at `0x1800114dc`
- `api-ms-win-security-appcontainer-l1-1-0!GetAppContainerNamedObjectPath` at `0x1800114dc`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800115b1`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800115b1`

## string_xrefs

- `0x1800114f1`: `\AuthHostCompleteRegisterEvent`

## pseudocode

```c
__int64 __fastcall WaitForAuthHostProcessToRegister(
        void *appContainerSid,
        void *processHandle,
        const wchar_t *authHostIdString)
{
  DWORD v4; // edi
  signed int LastError; // eax
  unsigned int v6; // ebx
  int AuthHostRegDWORDValue; // eax
  unsigned int returnLength; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE waitHandles[3]; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t eventName[264]; // [rsp+50h] [rbp-B0h] BYREF

  waitHandles[0] = processHandle;
  eventName[0] = 0;
  waitHandles[1] = 0;
  returnLength = 0;
  v4 = 1;
  if ( (unsigned int)GetAppContainerNamedObjectPath(0, appContainerSid, 260, eventName, &returnLength)
    && StringCchCatW(eventName, 0x104u, L"\\AuthHostCompleteRegisterEvent") >= 0
    && StringCchCatW(eventName, 0x104u, authHostIdString) >= 0 )
  {
    waitHandles[1] = CreateEventW(0, 0, 0, eventName);
    if ( waitHandles[1] )
    {
      v4 = 2;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control[1].Control.Logger,
          0x48u,
          WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
          LastError);
      }
    }
  }
  v6 = 0;
  AuthHostRegDWORDValue = GetAuthHostRegDWORDValue(L"DisableActivateTimeout");
  if ( !WaitForMultipleObjects(v4, waitHandles, 0, AuthHostRegDWORDValue != 0 ? -1 : 60000) )
  {
    v6 = -2147023829;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0x49u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids);
    }
  }
  if ( waitHandles[1] )
    CloseHandle(waitHandles[1]);
  return v6;
}

```

## disassembly

```asm
0x180011474  mov     [rsp-8+arg_18], rbx
0x180011479  push    rbp
0x18001147a  push    rdi
0x18001147b  push    r14
0x18001147d  lea     rbp, [rsp-170h]
0x180011485  sub     rsp, 270h
0x18001148c  mov     rax, cs:__security_cookie
0x180011493  xor     rax, rsp
0x180011496  mov     [rbp+180h+var_20], rax
0x18001149d  xor     eax, eax
0x18001149f  mov     [rsp+280h+waitHandles], processHandle
0x1800114a4  mov     [rsp+280h+eventName], ax
0x1800114a9  lea     r9, [rsp+280h+eventName]
0x1800114ae  lea     rax, [rsp+280h+returnLength]
0x1800114b3  mov     [rsp+280h+waitHandles+8], 0
0x1800114bc  mov     rbx, authHostIdString
0x1800114bf  mov     [rsp+280h+var_260], rax
0x1800114c4  mov     processHandle, appContainerSid
0x1800114c7  mov     [rsp+280h+returnLength], 0
0x1800114cf  mov     r8d, 104h
0x1800114d5  xor     ecx, ecx
0x1800114d7  mov     edi, 1
0x1800114dc  call    cs:__imp_GetAppContainerNamedObjectPath
0x1800114e2  lea     r14, WPP_GLOBAL_Control
0x1800114e9  test    eax, eax
0x1800114eb  jz      loc_180011586
0x1800114f1  lea     authHostIdString, aAuthhostcomple; "\\AuthHostCompleteRegisterEvent"
0x1800114f8  mov     edx, 104h; cchDest
0x1800114fd  lea     appContainerSid, [rsp+280h+eventName]; pszDest
0x180011502  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011507  test    eax, eax
0x180011509  js      short loc_180011586
0x18001150b  mov     authHostIdString, rbx; pszSrc
0x18001150e  lea     appContainerSid, [rsp+280h+eventName]; pszDest
0x180011513  mov     edx, 104h; cchDest
0x180011518  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001151d  test    eax, eax
0x18001151f  js      short loc_180011586
0x180011521  lea     r9, [rsp+280h+eventName]; lpName
0x180011526  xor     r8d, r8d; bInitialState
0x180011529  xor     edx, edx; bManualReset
0x18001152b  xor     ecx, ecx; lpEventAttributes
0x18001152d  call    cs:__imp_CreateEventW
0x180011533  mov     [rsp+280h+waitHandles+8], rax
0x180011538  test    rax, rax
0x18001153b  jz      short loc_180011544
0x18001153d  mov     edi, 2
0x180011542  jmp     short loc_180011586
0x180011544  call    cs:__imp_GetLastError
0x18001154a  test    eax, eax
0x18001154c  jle     short loc_180011556
0x18001154e  movzx   eax, ax
0x180011551  or      eax, 80070000h
0x180011556  mov     appContainerSid, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001155d  cmp     appContainerSid, r14
0x180011560  jz      short loc_180011586
0x180011562  test    byte ptr [appContainerSid+44h], 10h
0x180011566  jz      short loc_180011586
0x180011568  cmp     byte ptr [appContainerSid+41h], 2
0x18001156c  jb      short loc_180011586
0x18001156e  mov     appContainerSid, [appContainerSid+38h]; Logger
0x180011572  lea     authHostIdString, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180011579  mov     edx, 48h ; 'H'; id
0x18001157e  mov     r9d, eax; _a1
0x180011581  call    WPP_SF_d
0x180011586  lea     appContainerSid, aDisableactivat; "DisableActivateTimeout"
0x18001158d  xor     ebx, ebx
0x18001158f  call    ?GetAuthHostRegDWORDValue@@YAKPEBG@Z; GetAuthHostRegDWORDValue(ushort const *)
0x180011594  neg     eax
0x180011596  lea     processHandle, [rsp+280h+waitHandles]; lpHandles
0x18001159b  mov     ecx, edi; nCount
0x18001159d  sbb     r9d, r9d
0x1800115a0  xor     r8d, r8d; bWaitAll
0x1800115a3  and     r9d, 0FFFF159Fh
0x1800115aa  add     r9d, 0EA60h; dwMilliseconds
0x1800115b1  call    cs:__imp_WaitForMultipleObjects
0x1800115b7  test    eax, eax
0x1800115b9  jnz     short loc_1800115EB
0x1800115bb  mov     ebx, 8007042Bh
0x1800115c0  mov     appContainerSid, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800115c7  cmp     appContainerSid, r14
0x1800115ca  jz      short loc_1800115EB
0x1800115cc  test    byte ptr [appContainerSid+44h], 10h
0x1800115d0  jz      short loc_1800115EB
0x1800115d2  cmp     byte ptr [appContainerSid+41h], 2
0x1800115d6  jb      short loc_1800115EB
0x1800115d8  mov     appContainerSid, [appContainerSid+38h]; Logger
0x1800115dc  lea     edx, [rax+49h]; id
0x1800115df  lea     authHostIdString, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x1800115e6  call    WPP_SF_
0x1800115eb  mov     appContainerSid, [rsp+280h+waitHandles+8]; hObject
0x1800115f0  test    appContainerSid, appContainerSid
0x1800115f3  jz      short loc_1800115FB
0x1800115f5  call    cs:__imp_CloseHandle
0x1800115fb  mov     eax, ebx
0x1800115fd  mov     appContainerSid, [rbp+180h+var_20]
0x180011604  xor     appContainerSid, rsp; StackCookie
0x180011607  call    __security_check_cookie
0x18001160c  mov     rbx, [rsp+280h+arg_18]
0x180011614  add     rsp, 270h
0x18001161b  pop     r14
0x18001161d  pop     rdi
0x18001161e  pop     rbp
0x18001161f  retn
```
