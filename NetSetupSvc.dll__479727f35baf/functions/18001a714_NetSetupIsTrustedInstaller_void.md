# NetSetupIsTrustedInstaller(void *)

- ea: `0x18001a714`
- end: `0x18001a7d6`
- name: `?NetSetupIsTrustedInstaller@@YA_NPEAX@Z`
- size: `194`
- prototype: `bool __fastcall(void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013acc`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078f8`
- `0x180008854`
- `0x18001a714`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a74e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a74e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001a744`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001a744`

## pseudocode

```c
bool __fastcall NetSetupIsTrustedInstaller(void *a1)
{
  signed int LastError; // ebx
  _BYTE pExceptionObject[208]; // [rsp+20h] [rbp-E8h] BYREF
  WINBOOL v4; // [rsp+F0h] [rbp-18h] BYREF

  v4 = 0;
  if ( !CheckTokenMembership(a1, qword_18003E410, &v4) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_ed900848e5123e61f3bb69b3da2f293f_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, LastError);
    throw (HResultException *)pExceptionObject;
  }
  return v4 != 0;
}

```

## disassembly

```asm
0x18001a714  mov     r11, rsp
0x18001a717  push    rbx
0x18001a718  sub     rsp, 100h
0x18001a71f  mov     rax, cs:__security_cookie
0x18001a726  xor     rax, rsp
0x18001a729  mov     [rsp+108h+var_10], rax
0x18001a731  lea     r8, [r11-18h]; IsMember
0x18001a735  mov     dword ptr [r11-18h], 0
0x18001a73d  lea     rdx, qword_18003E410; SidToCheck
0x18001a744  call    cs:__imp_CheckTokenMembership
0x18001a74a  test    eax, eax
0x18001a74c  jnz     short loc_18001A7B2
0x18001a74e  call    cs:__imp_GetLastError
0x18001a754  mov     ebx, eax
0x18001a756  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a75d  lea     rax, WPP_GLOBAL_Control
0x18001a764  cmp     rcx, rax
0x18001a767  jz      short loc_18001A787
0x18001a769  cmp     byte ptr [rcx+19h], 2
0x18001a76d  jb      short loc_18001A787
0x18001a76f  mov     rcx, [rcx+10h]
0x18001a773  lea     r8, WPP_ed900848e5123e61f3bb69b3da2f293f_Traceguids
0x18001a77a  mov     edx, 0Ch
0x18001a77f  mov     r9d, ebx
0x18001a782  call    WPP_SF_d
0x18001a787  test    ebx, ebx
0x18001a789  jle     short loc_18001A794
0x18001a78b  movzx   ebx, bx
0x18001a78e  or      ebx, 80070000h
0x18001a794  mov     edx, ebx; int
0x18001a796  lea     rcx, [rsp+108h+pExceptionObject]; this
0x18001a79b  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18001a7a0  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18001a7a7  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18001a7ac  call    _CxxThrowException_0
0x18001a7b2  cmp     [rsp+108h+var_18], 0
0x18001a7ba  setnz   al
0x18001a7bd  mov     rcx, [rsp+108h+var_10]
0x18001a7c5  xor     rcx, rsp; StackCookie
0x18001a7c8  call    __security_check_cookie
0x18001a7cd  add     rsp, 100h
0x18001a7d4  pop     rbx
0x18001a7d5  retn
```
