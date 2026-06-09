# ThreadUILanguage::SetInner(wchar_t const *)

- ea: `0x180080494`
- end: `0x180080549`
- name: `?SetInner@ThreadUILanguage@@AEAAXPEB_W@Z`
- size: `181`
- prototype: `void __fastcall(ThreadUILanguage *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800639a8`
- `0x180064098`

## callees

- `0x18005097c`
- `0x18005b034`
- `0x180065035`
- `0x180080494`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800804cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800804cc`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x1800804c2`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x1800804c2`

## pseudocode

```c
void __fastcall ThreadUILanguage::SetInner(ThreadUILanguage *this, const wchar_t *a2)
{
  signed int LastError; // ebx
  _BYTE pExceptionObject[208]; // [rsp+20h] [rbp-E8h] BYREF
  ULONG v4; // [rsp+F0h] [rbp-18h] BYREF

  v4 = 0;
  if ( !SetThreadPreferredUILanguages(8u, a2, &v4) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_5846ae62d686398b3f2d59aafea183e9_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, LastError);
    throw (HResultException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180080494  mov     r11, rsp
0x180080497  push    rbx
0x180080498  sub     rsp, 100h
0x18008049f  mov     rax, cs:__security_cookie
0x1800804a6  xor     rax, rsp
0x1800804a9  mov     [rsp+108h+var_10], rax
0x1800804b1  lea     r8, [r11-18h]; pulNumLanguages
0x1800804b5  mov     dword ptr [r11-18h], 0
0x1800804bd  mov     ecx, 8; dwFlags
0x1800804c2  call    cs:__imp_SetThreadPreferredUILanguages
0x1800804c8  test    eax, eax
0x1800804ca  jnz     short loc_180080530
0x1800804cc  call    cs:__imp_GetLastError
0x1800804d2  mov     ebx, eax
0x1800804d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800804db  lea     rax, WPP_GLOBAL_Control
0x1800804e2  cmp     rcx, rax
0x1800804e5  jz      short loc_180080505
0x1800804e7  cmp     byte ptr [rcx+19h], 2
0x1800804eb  jb      short loc_180080505
0x1800804ed  mov     rcx, [rcx+10h]
0x1800804f1  lea     r8, WPP_5846ae62d686398b3f2d59aafea183e9_Traceguids
0x1800804f8  mov     edx, 0Ch
0x1800804fd  mov     r9d, ebx
0x180080500  call    WPP_SF_d
0x180080505  test    ebx, ebx
0x180080507  jle     short loc_180080512
0x180080509  movzx   ebx, bx
0x18008050c  or      ebx, 80070000h
0x180080512  mov     edx, ebx; int
0x180080514  lea     rcx, [rsp+108h+pExceptionObject]; this
0x180080519  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18008051e  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180080525  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18008052a  call    _CxxThrowException_0
0x180080530  mov     rcx, [rsp+108h+var_10]
0x180080538  xor     rcx, rsp; StackCookie
0x18008053b  call    __security_check_cookie
0x180080540  add     rsp, 100h
0x180080547  pop     rbx
0x180080548  retn
```
