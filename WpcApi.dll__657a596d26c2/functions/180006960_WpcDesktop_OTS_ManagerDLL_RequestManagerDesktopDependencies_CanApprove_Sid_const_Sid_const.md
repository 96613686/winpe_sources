# WpcDesktop::OTS::ManagerDLL::RequestManagerDesktopDependencies::CanApprove(Sid const &,Sid const &)

- ea: `0x180006960`
- end: `0x180006aef`
- name: `?CanApprove@RequestManagerDesktopDependencies@ManagerDLL@OTS@WpcDesktop@@EEBA_NAEBVSid@@0@Z`
- size: `399`
- prototype: `bool __fastcall(WpcDesktop::OTS::ManagerDLL::RequestManagerDesktopDependencies *__hidden this, const struct Sid *, const struct Sid *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800032a0`
- `0x180003d20`
- `0x180004bb0`
- `0x180005f9c`
- `0x180006960`
- `0x18000b29c`
- `0x1800195c4`
- `0x180027bd4`
- `0x180027e70`
- `0x180028044`
- `0x18002883c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a8a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180006a09`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180006a09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a61`

## pseudocode

```c
bool __fastcall WpcDesktop::OTS::ManagerDLL::RequestManagerDesktopDependencies::CanApprove(
        WpcDesktop::OTS::ManagerDLL::RequestManagerDesktopDependencies *this,
        const struct Sid *a2,
        const struct Sid *a3)
{
  char *v3; // rbx
  char *v4; // rdi
  bool result; // al
  void *v6; // rbx
  int Elevated; // eax
  int v8; // r8d
  int v9; // r9d
  HANDLE *v10; // rax
  BOOL v11; // ebx
  bool v12; // bl
  signed int LastError; // eax
  unsigned int v14; // ebx
  WINBOOL IsMember; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v16; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v18; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v19[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h]
  _BYTE pExceptionObject[40]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v22[72]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v23[40]; // [rsp+D8h] [rbp-28h] BYREF

  v3 = (char *)a3 + 72;
  v4 = (char *)a2 + 72;
  if ( (unsigned __int8)std::operator<<unsigned short>((char *)a2 + 72, (char *)a3 + 72)
    || (result = std::operator<<unsigned short>(v3, v4)) )
  {
    Token::FromComClient(&v16);
    IsMember = 0;
    v6 = (void *)Sid::FromWellKnownSid(v22);
    Elevated = Token::GetElevated(&v16, &v18);
    v20 = 0;
    v10 = (HANDLE *)Token::Duplicate(Elevated, (unsigned int)&hObject, v8, v9, (__int64)v19);
    v11 = CheckTokenMembership(*v10, v6, &IsMember);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( (char *)v18 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v18);
    std::wstring::~wstring(v23);
    if ( !v11 )
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, &WPP_1255abf0ecc2316176ef827e071b6c4e_Traceguids, v14);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v14);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v12 = IsMember != 0;
    if ( (char *)v16 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v16);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x180006960  mov     [rsp-8+arg_0], rbx
0x180006965  mov     [rsp-8+arg_18], rdi
0x18000696a  push    rbp
0x18000696b  lea     rbp, [rsp-10h]
0x180006970  sub     rsp, 110h
0x180006977  mov     rax, cs:__security_cookie
0x18000697e  xor     rax, rsp
0x180006981  mov     [rbp+10h+var_10], rax
0x180006985  lea     rbx, [r8+48h]
0x180006989  lea     rdi, [rdx+48h]
0x18000698d  mov     rdx, rbx
0x180006990  mov     rcx, rdi
0x180006993  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180006998  test    al, al
0x18000699a  jnz     short loc_1800069AF
0x18000699c  mov     rdx, rdi
0x18000699f  mov     rcx, rbx
0x1800069a2  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x1800069a7  test    al, al
0x1800069a9  jz      loc_180006A69
0x1800069af  lea     rcx, [rsp+110h+var_D8]
0x1800069b4  call    ?FromComClient@Token@@SA?AV1@_N@Z; Token::FromComClient(bool)
0x1800069b9  nop
0x1800069ba  mov     [rsp+110h+IsMember], 0
0x1800069c2  lea     rcx, [rbp+10h+var_80]
0x1800069c6  call    ?FromWellKnownSid@Sid@@SA?AV1@W4WELL_KNOWN_SID_TYPE@@@Z; Sid::FromWellKnownSid(WELL_KNOWN_SID_TYPE)
0x1800069cb  mov     rbx, rax
0x1800069ce  lea     rdx, [rsp+110h+var_C8]
0x1800069d3  lea     rcx, [rsp+110h+var_D8]
0x1800069d8  call    ?GetElevated@Token@@QEBA?AV1@XZ; Token::GetElevated(void)
0x1800069dd  nop
0x1800069de  mov     [rsp+110h+var_B8], 0
0x1800069e7  lea     rcx, [rsp+110h+var_C0]
0x1800069ec  mov     [rsp+110h+var_F0], rcx
0x1800069f1  lea     rdx, [rsp+110h+hObject]
0x1800069f6  mov     rcx, rax
0x1800069f9  call    ?Duplicate@Token@@QEBA?AV1@W4_TOKEN_TYPE@@W4_SECURITY_IMPERSONATION_LEVEL@@V?$Optional@W4IntegrityLevel@@@@@Z; Token::Duplicate(_TOKEN_TYPE,_SECURITY_IMPERSONATION_LEVEL,Optional<IntegrityLevel>)
0x1800069fe  lea     r8, [rsp+110h+IsMember]; IsMember
0x180006a03  mov     rdx, rbx; SidToCheck
0x180006a06  mov     rcx, [rax]; TokenHandle
0x180006a09  call    cs:__imp_CheckTokenMembership
0x180006a0f  mov     ebx, eax
0x180006a11  mov     rcx, [rsp+110h+hObject]; hObject
0x180006a16  lea     rdx, [rcx-1]
0x180006a1a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180006a1e  ja      short loc_180006A27
0x180006a20  call    cs:__imp_CloseHandle
0x180006a26  nop
0x180006a27  mov     rcx, [rsp+110h+var_C8]; hObject
0x180006a2c  lea     rdx, [rcx-1]
0x180006a30  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180006a34  ja      short loc_180006A3D
0x180006a36  call    cs:__imp_CloseHandle
0x180006a3c  nop
0x180006a3d  lea     rcx, [rbp+10h+var_38]
0x180006a41  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006a46  test    ebx, ebx
0x180006a48  jz      short loc_180006A8A
0x180006a4a  cmp     [rsp+110h+IsMember], 0
0x180006a4f  setnz   bl
0x180006a52  mov     rcx, [rsp+110h+var_D8]; hObject
0x180006a57  lea     rdx, [rcx-1]
0x180006a5b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180006a5f  ja      short loc_180006A67
0x180006a61  call    cs:__imp_CloseHandle
0x180006a67  mov     al, bl
0x180006a69  mov     rcx, [rbp+10h+var_10]
0x180006a6d  xor     rcx, rsp; StackCookie
0x180006a70  call    __security_check_cookie
0x180006a75  lea     r11, [rsp+110h+var_s0]
0x180006a7d  mov     rbx, [r11+10h]
0x180006a81  mov     rdi, [r11+28h]
0x180006a85  mov     rsp, r11
0x180006a88  pop     rbp
0x180006a89  retn
0x180006a8a  call    cs:__imp_GetLastError
0x180006a90  nop
0x180006a91  mov     ebx, eax
0x180006a93  test    eax, eax
0x180006a95  jle     short loc_180006AA0
0x180006a97  movzx   ebx, ax
0x180006a9a  or      ebx, 80070000h
0x180006aa0  lea     rax, WPP_GLOBAL_Control
0x180006aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180006aae  cmp     rcx, rax
0x180006ab1  jz      short loc_180006AD1
0x180006ab3  test    byte ptr [rcx+1Ch], 1
0x180006ab7  jz      short loc_180006AD1
0x180006ab9  mov     edx, 0Ah
0x180006abe  mov     r9d, ebx
0x180006ac1  lea     r8, WPP_1255abf0ecc2316176ef827e071b6c4e_Traceguids
0x180006ac8  mov     rcx, [rcx+10h]
0x180006acc  call    WPP_SF_d
0x180006ad1  mov     edx, ebx; int
0x180006ad3  lea     rcx, [rsp+110h+pExceptionObject]; this
0x180006ad8  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180006add  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180006ae4  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180006ae9  call    _CxxThrowException_0
```
