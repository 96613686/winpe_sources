# LicenseManagerUserContext::ImpersonateUserContext::~ImpersonateUserContext(void)

- ea: `0x180034e60`
- end: `0x180034ef0`
- name: `??1ImpersonateUserContext@LicenseManagerUserContext@@QEAA@XZ`
- size: `144`
- prototype: `void __fastcall(LicenseManagerUserContext::ImpersonateUserContext *__hidden this)`
- caller_count: `32`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180034930`
- `0x1800349f0`
- `0x180034ad0`
- `0x180034b30`
- `0x180049430`
- `0x180049550`
- `0x1800496e0`
- `0x180056410`
- `0x1800565b0`
- `0x180056680`
- `0x180056750`
- `0x180056b60`
- `0x18006bf60`
- `0x180071c50`
- `0x180071d50`
- `0x180072260`
- `0x180072370`
- `0x180072480`
- `0x180072590`
- `0x180091100`
- `0x1800927d0`
- `0x1800928d0`
- `0x180092a00`
- `0x180092aa0`
- `0x180092ba0`
- `0x180092e00`
- `0x180093280`
- `0x1800b05bb`
- `0x1800b060c`
- `0x1800b0660`
- `0x1800b3ead`
- `0x1800b3f85`

## callees

- `0x1800119e0`
- `0x180034e60`
- `0x18008a400`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ebd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ebd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180034edb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180034edb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180034e79`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180034e79`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180034e98`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180034e98`

## pseudocode

```c
void __fastcall LicenseManagerUserContext::ImpersonateUserContext::~ImpersonateUserContext(
        LicenseManagerUserContext::ImpersonateUserContext *this)
{
  void *v2; // rdx
  const char *v3; // r9
  int LastError; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_BYTE *)this )
  {
    v2 = (void *)*((_QWORD *)this + 2);
    if ( v2 )
    {
      if ( !SetThreadToken(0, v2) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x6F,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\usercontexthelper.h",
          v3);
    }
    else
    {
      RevertToSelf();
    }
  }
  *((_QWORD *)this + 1) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( *((_QWORD *)this + 2) )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose((char *)this + 8) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RaiseException(LastError, 1u, 0, 0);
      __debugbreak();
    }
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x180034e60  push    rbx
0x180034e62  sub     rsp, 20h
0x180034e66  mov     rbx, rcx
0x180034e69  cmp     byte ptr [rcx], 0
0x180034e6c  jz      short loc_180034E9E
0x180034e6e  mov     rdx, [rcx+10h]; Token
0x180034e72  test    rdx, rdx
0x180034e75  jz      short loc_180034E98
0x180034e77  xor     ecx, ecx; Thread
0x180034e79  call    cs:__imp_SetThreadToken
0x180034e7f  test    eax, eax
0x180034e81  jnz     short loc_180034E9E
0x180034e83  mov     rcx, [rsp+28h]; this
0x180034e88  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\licensem"...
0x180034e8f  lea     edx, [rax+6Fh]; void *
0x180034e92  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180034e98  call    cs:__imp_RevertToSelf
0x180034e9e  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180034ea5  mov     [rbx+8], rax
0x180034ea9  cmp     qword ptr [rbx+10h], 0
0x180034eae  jz      short loc_180034EEA
0x180034eb0  lea     rcx, [rbx+8]
0x180034eb4  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x180034eb9  test    al, al
0x180034ebb  jnz     short loc_180034EE2
0x180034ebd  call    cs:__imp_GetLastError
0x180034ec3  test    eax, eax
0x180034ec5  jle     short loc_180034ECF
0x180034ec7  movzx   eax, ax
0x180034eca  or      eax, 80070000h
0x180034ecf  xor     r9d, r9d; lpArguments
0x180034ed2  xor     r8d, r8d; nNumberOfArguments
0x180034ed5  lea     edx, [r9+1]; dwExceptionFlags
0x180034ed9  mov     ecx, eax; dwExceptionCode
0x180034edb  call    cs:__imp_RaiseException
0x180034ee1  int     3; Trap to Debugger
0x180034ee2  mov     qword ptr [rbx+10h], 0
0x180034eea  add     rsp, 20h
0x180034eee  pop     rbx
0x180034eef  retn
```
