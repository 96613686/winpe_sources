# ThreadUILanguage::ThreadUILanguage(void)

- ea: `0x180080300`
- end: `0x18008048b`
- name: `??0ThreadUILanguage@@QEAA@XZ`
- size: `395`
- prototype: `ThreadUILanguage *__fastcall(ThreadUILanguage *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800639a8`

## callees

- `0x18001dfe8`
- `0x18005097c`
- `0x18005b034`
- `0x180065035`
- `0x180080300`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080407`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18008036a`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x1800803fd`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18008036a`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x1800803fd`

## pseudocode

```c
ThreadUILanguage *__fastcall ThreadUILanguage::ThreadUILanguage(ThreadUILanguage *this)
{
  signed int LastError; // ebx
  signed int v3; // ebx
  _BYTE pExceptionObject[208]; // [rsp+38h] [rbp-D0h] BYREF
  ULONG pcchLanguagesBuffer; // [rsp+108h] [rbp+0h] BYREF
  ULONG pulNumLanguages; // [rsp+10Ch] [rbp+4h] BYREF

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_BYTE *)this + 24) = 0;
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( !GetThreadPreferredUILanguages(0x48u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_5846ae62d686398b3f2d59aafea183e9_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, LastError);
    throw (HResultException *)pExceptionObject;
  }
  if ( pulNumLanguages )
  {
    std::vector<wchar_t>::resize(this, pcchLanguagesBuffer);
    if ( !GetThreadPreferredUILanguages(0x48u, &pulNumLanguages, *(PZZWSTR *)this, &pcchLanguagesBuffer) )
    {
      v3 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_5846ae62d686398b3f2d59aafea183e9_Traceguids,
          (unsigned int)v3);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      HResultException::HResultException((HResultException *)pExceptionObject, v3);
      throw (HResultException *)pExceptionObject;
    }
  }
  return this;
}

```

## disassembly

```asm
0x180080300  mov     rax, rsp
0x180080303  push    rbp
0x180080304  lea     rbp, [rax-18h]
0x180080308  sub     rsp, 110h
0x18008030f  mov     [rsp+110h+var_F0], 0FFFFFFFFFFFFFFFEh
0x180080318  mov     [rax+10h], rbx
0x18008031c  mov     rax, cs:__security_cookie
0x180080323  xor     rax, rsp
0x180080326  mov     [rbp+10h+var_8], rax
0x18008032a  mov     rbx, rcx
0x18008032d  mov     qword ptr [rsp+110h+var_E8], rcx
0x180080332  mov     qword ptr [rcx], 0
0x180080339  mov     qword ptr [rcx+8], 0
0x180080341  mov     qword ptr [rcx+10h], 0
0x180080349  mov     byte ptr [rcx+18h], 0
0x18008034d  mov     [rbp+10h+pulNumLanguages], 0
0x180080354  mov     [rbp+10h+pcchLanguagesBuffer], 0
0x18008035b  lea     r9, [rbp+10h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18008035f  xor     r8d, r8d; pwszLanguagesBuffer
0x180080362  lea     rdx, [rbp+10h+pulNumLanguages]; pulNumLanguages
0x180080366  lea     ecx, [r8+48h]; dwFlags
0x18008036a  call    cs:__imp_GetThreadPreferredUILanguages
0x180080370  test    eax, eax
0x180080372  jnz     short loc_1800803D8
0x180080374  call    cs:__imp_GetLastError
0x18008037a  mov     ebx, eax
0x18008037c  lea     rax, WPP_GLOBAL_Control
0x180080383  mov     rcx, cs:WPP_GLOBAL_Control
0x18008038a  cmp     rcx, rax
0x18008038d  jz      short loc_1800803AD
0x18008038f  cmp     byte ptr [rcx+19h], 2
0x180080393  jb      short loc_1800803AD
0x180080395  mov     edx, 0Ah
0x18008039a  mov     r9d, ebx
0x18008039d  lea     r8, WPP_5846ae62d686398b3f2d59aafea183e9_Traceguids
0x1800803a4  mov     rcx, [rcx+10h]
0x1800803a8  call    WPP_SF_d
0x1800803ad  test    ebx, ebx
0x1800803af  jle     short loc_1800803BA
0x1800803b1  movzx   ebx, bx
0x1800803b4  or      ebx, 80070000h
0x1800803ba  mov     edx, ebx; int
0x1800803bc  lea     rcx, [rsp+110h+pExceptionObject]; this
0x1800803c1  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800803c6  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800803cd  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x1800803d2  call    _CxxThrowException_0
0x1800803d8  cmp     [rbp+10h+pulNumLanguages], 0
0x1800803dc  jz      loc_18008046B
0x1800803e2  mov     edx, [rbp+10h+pcchLanguagesBuffer]
0x1800803e5  mov     rcx, rbx
0x1800803e8  call    ?resize@?$vector@_WV?$allocator@_W@std@@@std@@QEAAX_K@Z; std::vector<wchar_t>::resize(unsigned __int64)
0x1800803ed  lea     r9, [rbp+10h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800803f1  mov     r8, [rbx]; pwszLanguagesBuffer
0x1800803f4  lea     rdx, [rbp+10h+pulNumLanguages]; pulNumLanguages
0x1800803f8  mov     ecx, 48h ; 'H'; dwFlags
0x1800803fd  call    cs:__imp_GetThreadPreferredUILanguages
0x180080403  test    eax, eax
0x180080405  jnz     short loc_18008046B
0x180080407  call    cs:__imp_GetLastError
0x18008040d  mov     ebx, eax
0x18008040f  lea     rax, WPP_GLOBAL_Control
0x180080416  mov     rcx, cs:WPP_GLOBAL_Control
0x18008041d  cmp     rcx, rax
0x180080420  jz      short loc_180080440
0x180080422  cmp     byte ptr [rcx+19h], 2
0x180080426  jb      short loc_180080440
0x180080428  mov     edx, 0Bh
0x18008042d  mov     r9d, ebx
0x180080430  lea     r8, WPP_5846ae62d686398b3f2d59aafea183e9_Traceguids
0x180080437  mov     rcx, [rcx+10h]
0x18008043b  call    WPP_SF_d
0x180080440  test    ebx, ebx
0x180080442  jle     short loc_18008044D
0x180080444  movzx   ebx, bx
0x180080447  or      ebx, 80070000h
0x18008044d  mov     edx, ebx; int
0x18008044f  lea     rcx, [rsp+110h+pExceptionObject]; this
0x180080454  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180080459  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180080460  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180080465  call    _CxxThrowException_0
0x18008046b  mov     rax, rbx
0x18008046e  mov     rcx, [rbp+10h+var_8]
0x180080472  xor     rcx, rsp; StackCookie
0x180080475  call    __security_check_cookie
0x18008047a  mov     rbx, [rsp+110h+arg_8]
0x180080482  add     rsp, 110h
0x180080489  pop     rbp
0x18008048a  retn
```
