# AppReadiness::Api::IsCallerLowIL(unsigned __int64)

- ea: `0x180012028`
- end: `0x18001211d`
- name: `?IsCallerLowIL@Api@AppReadiness@@AEAA_N_K@Z`
- size: `245`
- prototype: `bool __fastcall(AppReadiness::Api *this, __int64)`
- caller_count: `8`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003a690`
- `0x1800454f8`
- `0x180045730`
- `0x180045894`
- `0x1800459f8`
- `0x180045b14`
- `0x180045e04`
- `0x180045f74`

## callees

- `0x180012028`
- `0x180012124`
- `0x18001218c`
- `0x180012610`
- `0x180027a4c`
- `0x18003ecb4`
- `0x18003eec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012106`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012106`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120e8`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180012060`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180012060`

## string_xrefs

- `0x180012085`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x180012091`: `AppReadiness::Api::IsCallerLowIL`
- `0x180012098`: `InferUserContext(userContextToken, callingUser.GetAddressOf())`

## pseudocode

```c
bool __fastcall AppReadiness::Api::IsCallerLowIL(AppReadiness::Api *this, __int64 a2)
{
  int CallingUserToken; // eax
  bool v4; // bl
  int LastError; // eax
  void **v7; // [rsp+30h] [rbp-48h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-40h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+40h] [rbp-38h] BYREF

  v7 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  TokenHandle = 0;
  if ( a2 )
  {
    if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent(this) )
      CallingUserToken = UMgrQueryUserToken(a2, &TokenHandle);
    else
      CallingUserToken = -2147467263;
  }
  else
  {
    CallingUserToken = AppReadiness::GetCallingUserToken(this, &TokenHandle);
  }
  if ( CallingUserToken < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      CallingUserToken,
      "InferUserContext(userContextToken, callingUser.GetAddressOf())",
      "AppReadiness::Api::IsCallerLowIL",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      355);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v4 = (unsigned int)IsTokenLowIL(TokenHandle) == 0;
  v7 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( TokenHandle
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits>::InternalClose(&v7) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
  return v4;
}

```

## disassembly

```asm
0x180012028  mov     [rsp+arg_0], rbx
0x18001202d  push    rdi
0x18001202e  sub     rsp, 70h
0x180012032  mov     rbx, rdx
0x180012035  lea     rdi, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18001203c  mov     [rsp+78h+var_48], rdi
0x180012041  mov     [rsp+78h+TokenHandle], 0
0x18001204a  test    rdx, rdx
0x18001204d  jz      short loc_18001206F
0x18001204f  call    IsUMgrEnumerateSessionUsersPresent
0x180012054  test    al, al
0x180012056  jz      short loc_180012068
0x180012058  lea     rdx, [rsp+78h+TokenHandle]
0x18001205d  mov     rcx, rbx
0x180012060  call    cs:__imp_UMgrQueryUserToken
0x180012066  jmp     short loc_180012079
0x180012068  mov     eax, 80004001h
0x18001206d  jmp     short loc_180012079
0x18001206f  lea     rdx, [rsp+78h+TokenHandle]
0x180012074  call    AppReadiness__GetCallingUserToken
0x180012079  test    eax, eax
0x18001207b  jns     short loc_1800120BD
0x18001207d  mov     [rsp+78h+var_50], 163h; int
0x180012085  lea     rcx, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18001208c  mov     [rsp+78h+var_58], rcx; char *
0x180012091  lea     r9, aAppreadinessAp_0; "AppReadiness::Api::IsCallerLowIL"
0x180012098  lea     r8, aInferuserconte; "InferUserContext(userContextToken, call"...
0x18001209f  mov     edx, eax; int
0x1800120a1  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800120a6  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800120ab  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800120b2  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800120b7  call    _CxxThrowException_0
0x1800120bd  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x1800120c2  call    ?IsTokenLowIL@@YAJPEAX@Z; IsTokenLowIL(void *)
0x1800120c7  nop
0x1800120c8  test    eax, eax
0x1800120ca  setz    bl
0x1800120cd  mov     [rsp+78h+var_48], rdi
0x1800120d2  cmp     [rsp+78h+TokenHandle], 0
0x1800120d8  jz      short loc_18001210D
0x1800120da  lea     rcx, [rsp+78h+var_48]
0x1800120df  call    ?InternalClose@?$HandleT@USemaphoreTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits>::InternalClose(void)
0x1800120e4  test    al, al
0x1800120e6  jnz     short loc_18001210D
0x1800120e8  call    cs:__imp_GetLastError
0x1800120ee  test    eax, eax
0x1800120f0  jle     short loc_1800120FA
0x1800120f2  movzx   eax, ax
0x1800120f5  or      eax, 80070000h
0x1800120fa  xor     r9d, r9d; lpArguments
0x1800120fd  xor     r8d, r8d; nNumberOfArguments
0x180012100  lea     edx, [r9+1]; dwExceptionFlags
0x180012104  mov     ecx, eax; dwExceptionCode
0x180012106  call    cs:__imp_RaiseException
0x18001210c  int     3; Trap to Debugger
0x18001210d  mov     al, bl
0x18001210f  mov     rbx, [rsp+78h+arg_0]
0x180012117  add     rsp, 70h
0x18001211b  pop     rdi
0x18001211c  retn
```
