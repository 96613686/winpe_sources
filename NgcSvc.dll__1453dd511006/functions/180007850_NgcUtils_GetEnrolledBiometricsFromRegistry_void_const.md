# NgcUtils::GetEnrolledBiometricsFromRegistry(void * const)

- ea: `0x180007850`
- end: `0x18000795c`
- name: `?GetEnrolledBiometricsFromRegistry@NgcUtils@@YAIQEAX@Z`
- size: `268`
- prototype: `unsigned int __fastcall(PSID pSid, void *const)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180042e40`
- `0x1800512bc`
- `0x1800853a0`

## callees

- `0x18000782c`
- `0x180007850`
- `0x180007964`
- `0x18005cee0`
- `0x18005dd44`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800078b9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800078b9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800078ac`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800078ac`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180007889`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180007889`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioGetEnrolledFactors` at `0x1800078ee`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioGetEnrolledFactors` at `0x1800078ee`

## string_xrefs

- `0x1800078cd`: `onecore\ds\security\ngc\utils\bio\lib\bioutils.cpp`
- `0x180007908`: `onecore\ds\security\ngc\utils\bio\lib\bioutils.cpp`
- `0x180007939`: `onecore\ds\security\ngc\utils\bio\lib\bioutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::GetEnrolledBiometricsFromRegistry(PSID pSid, void *const a2)
{
  const char *v3; // r9
  int LastError; // ebx
  int EnrolledFactors; // eax
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  int v9[4]; // [rsp+20h] [rbp-78h] BYREF
  _DWORD v10[2]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE pDestinationSid[72]; // [rsp+38h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v9[0] = 0;
  memset_0(v10, 0, 0x4Cu);
  if ( !IsValidSid(pSid) )
  {
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x180,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\bioutils.cpp",
      (const char *)0x80070057LL,
      v9[0]);
    goto LABEL_10;
  }
  v10[0] = 3;
  if ( CopySid(0x44u, pDestinationSid, pSid) )
  {
    v10[1] = GetLengthSid(pSid);
    goto LABEL_5;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x183,
                (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\bioutils.cpp",
                v3);
  if ( LastError < 0 )
  {
LABEL_10:
    v6 = (unsigned int)LastError;
    v7 = 171;
    goto LABEL_7;
  }
LABEL_5:
  EnrolledFactors = WinBioGetEnrolledFactors(v10, v9);
  if ( EnrolledFactors < 0 )
  {
    v6 = (unsigned int)EnrolledFactors;
    v7 = 175;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\bioutils.cpp",
      (const char *)v6,
      v9[0]);
  }
  return (unsigned int)v9[0];
}

```

## disassembly

```asm
0x180007850  push    rbx
0x180007852  sub     rsp, 90h
0x180007859  mov     rax, cs:__security_cookie
0x180007860  xor     rax, rsp
0x180007863  mov     [rsp+98h+var_18], rax
0x18000786b  xor     edx, edx; Val
0x18000786d  mov     [rsp+98h+var_78], 0; int
0x180007875  mov     rbx, rcx
0x180007878  lea     rcx, [rsp+98h+var_68]; void *
0x18000787d  lea     r8d, [rdx+4Ch]; Size
0x180007881  call    memset_0
0x180007886  mov     rcx, rbx; pSid
0x180007889  call    cs:__imp_IsValidSid
0x18000788f  test    eax, eax
0x180007891  jz      loc_180007931
0x180007897  mov     r8, rbx; pSourceSid
0x18000789a  mov     [rsp+98h+var_68], 3
0x1800078a2  lea     rdx, [rsp+98h+pDestinationSid]; pDestinationSid
0x1800078a7  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x1800078ac  call    cs:__imp_CopySid
0x1800078b2  test    eax, eax
0x1800078b4  jz      short loc_1800078C5
0x1800078b6  mov     rcx, rbx; pSid
0x1800078b9  call    cs:__imp_GetLengthSid
0x1800078bf  mov     [rsp+98h+var_64], eax
0x1800078c3  jmp     short loc_1800078E4
0x1800078c5  mov     rcx, [rsp+98h]; this
0x1800078cd  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x1800078d4  mov     edx, 183h; void *
0x1800078d9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800078de  mov     ebx, eax
0x1800078e0  test    eax, eax
0x1800078e2  js      short loc_180007952
0x1800078e4  lea     rdx, [rsp+98h+var_78]
0x1800078e9  lea     rcx, [rsp+98h+var_68]
0x1800078ee  call    cs:__imp_WinBioGetEnrolledFactors
0x1800078f4  test    eax, eax
0x1800078f6  jns     short loc_180007914
0x1800078f8  mov     r9d, eax; char *
0x1800078fb  mov     edx, 0AFh; void *
0x180007900  mov     rcx, [rsp+98h]; this
0x180007908  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x18000790f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007914  mov     eax, [rsp+98h+var_78]
0x180007918  mov     rcx, [rsp+98h+var_18]
0x180007920  xor     rcx, rsp; StackCookie
0x180007923  call    __security_check_cookie
0x180007928  add     rsp, 90h
0x18000792f  pop     rbx
0x180007930  retn
0x180007931  mov     rcx, [rsp+98h]; this
0x180007939  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180007940  mov     ebx, 80070057h
0x180007945  mov     edx, 180h; void *
0x18000794a  mov     r9d, ebx; char *
0x18000794d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007952  mov     r9d, ebx
0x180007955  mov     edx, 0ABh
0x18000795a  jmp     short loc_180007900
```
