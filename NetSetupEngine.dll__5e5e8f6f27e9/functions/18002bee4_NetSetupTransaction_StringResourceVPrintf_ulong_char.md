# NetSetupTransaction::StringResourceVPrintf(ulong,char * *)

- ea: `0x18002bee4`
- end: `0x18002c0a9`
- name: `?StringResourceVPrintf@NetSetupTransaction@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KPEAPEAD@Z`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x18002be88`

## callees

- `0x1800058a0`
- `0x18002bee4`
- `0x18002c0b0`
- `0x18005097c`
- `0x18005b034`
- `0x180065035`
- `0x1800810d0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadStringW` at `0x18002bf52`
- `api-ms-win-core-libraryloader-l1-1-0!LoadStringW` at `0x18002bf52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c00d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c00d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c032`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002bfea`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002bfea`

## string_xrefs

- `0x18002bf21`: `NetSetupSvc.dll`

## pseudocode

```c
__int64 __fastcall NetSetupTransaction::StringResourceVPrintf(__int64 a1, __int64 a2, UINT a3, va_list *a4)
{
  HINSTANCE *v4; // rdi
  __int64 v8; // rax
  signed int LastError; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  signed int v12; // eax
  _BYTE pExceptionObject[208]; // [rsp+50h] [rbp-508h] BYREF
  WCHAR Buffer[256]; // [rsp+120h] [rbp-438h] BYREF
  WCHAR lpBuffer[256]; // [rsp+320h] [rbp-238h] BYREF

  v4 = (HINSTANCE *)(a1 + 912);
  if ( !*(_QWORD *)(a1 + 912) )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(**(_QWORD **)(a1 + 72) + 8LL))(
           *(_QWORD *)(a1 + 72),
           L"NetSetupSvc.dll");
    ModuleHandle::operator=(v4, v8);
  }
  if ( !LoadStringW(*v4, a3, Buffer, 256) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_d9f5ad3171d43f677d32b63a5602fd0a_Traceguids, a3);
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, LastError);
    throw (HResultException *)pExceptionObject;
  }
  v10 = FormatMessageW(0x400u, Buffer, 0, 0, lpBuffer, 0x100u, a4);
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_d9f5ad3171d43f677d32b63a5602fd0a_Traceguids, v11);
    }
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, v12);
    throw (HResultException *)pExceptionObject;
  }
  *(_QWORD *)(a2 + 24) = 7;
  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)a2 = 0;
  std::wstring::assign(a2, lpBuffer, v10);
  return a2;
}

```

## disassembly

```asm
0x18002bee4  push    rbx
0x18002bee6  push    rbp
0x18002bee7  push    rsi
0x18002bee8  push    rdi
0x18002bee9  sub     rsp, 538h
0x18002bef0  mov     rax, cs:__security_cookie
0x18002bef7  xor     rax, rsp
0x18002befa  mov     [rsp+558h+var_38], rax
0x18002bf02  lea     rdi, [rcx+390h]
0x18002bf09  mov     [rsp+558h+var_510], rdx
0x18002bf0e  cmp     qword ptr [rdi], 0
0x18002bf12  mov     rbp, r9
0x18002bf15  mov     esi, r8d
0x18002bf18  mov     rbx, rdx
0x18002bf1b  jnz     short loc_18002BF3F
0x18002bf1d  mov     rcx, [rcx+48h]
0x18002bf21  lea     rdx, aNetsetupsvcDll; "NetSetupSvc.dll"
0x18002bf28  mov     rax, [rcx]
0x18002bf2b  mov     rax, [rax+8]
0x18002bf2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf34  mov     rdx, rax
0x18002bf37  mov     rcx, rdi
0x18002bf3a  call    ??4ModuleHandle@@QEAAAEAV0@PEAUHINSTANCE__@@@Z; ModuleHandle::operator=(HINSTANCE__ *)
0x18002bf3f  mov     rcx, [rdi]; hInstance
0x18002bf42  lea     r8, [rsp+558h+Buffer]; lpBuffer
0x18002bf4a  mov     r9d, 100h; cchBufferMax
0x18002bf50  mov     edx, esi; uID
0x18002bf52  call    cs:__imp_LoadStringW
0x18002bf58  test    eax, eax
0x18002bf5a  jnz     short loc_18002BFBD
0x18002bf5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf63  lea     rax, WPP_GLOBAL_Control
0x18002bf6a  cmp     rcx, rax
0x18002bf6d  jz      short loc_18002BF8D
0x18002bf6f  cmp     byte ptr [rcx+19h], 2
0x18002bf73  jb      short loc_18002BF8D
0x18002bf75  mov     rcx, [rcx+10h]
0x18002bf79  lea     r8, WPP_d9f5ad3171d43f677d32b63a5602fd0a_Traceguids
0x18002bf80  mov     edx, 14h
0x18002bf85  mov     r9d, esi
0x18002bf88  call    WPP_SF_d
0x18002bf8d  call    cs:__imp_GetLastError
0x18002bf93  test    eax, eax
0x18002bf95  jle     short loc_18002BF9F
0x18002bf97  movzx   eax, ax
0x18002bf9a  or      eax, 80070000h
0x18002bf9f  mov     edx, eax; int
0x18002bfa1  lea     rcx, [rsp+558h+pExceptionObject]; this
0x18002bfa6  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18002bfab  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18002bfb2  lea     rcx, [rsp+558h+pExceptionObject]; pExceptionObject
0x18002bfb7  call    _CxxThrowException_0
0x18002bfbd  mov     [rsp+558h+Arguments], rbp; Arguments
0x18002bfc2  lea     rax, [rsp+558h+var_238]
0x18002bfca  mov     [rsp+558h+nSize], 100h; nSize
0x18002bfd2  lea     rdx, [rsp+558h+Buffer]; lpSource
0x18002bfda  xor     r9d, r9d; dwLanguageId
0x18002bfdd  mov     [rsp+558h+lpBuffer], rax; lpBuffer
0x18002bfe2  xor     r8d, r8d; dwMessageId
0x18002bfe5  mov     ecx, 400h; dwFlags
0x18002bfea  call    cs:__imp_FormatMessageW
0x18002bff0  test    eax, eax
0x18002bff2  jnz     short loc_18002C062
0x18002bff4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bffb  lea     rax, WPP_GLOBAL_Control
0x18002c002  cmp     rcx, rax
0x18002c005  jz      short loc_18002C032
0x18002c007  cmp     byte ptr [rcx+19h], 2
0x18002c00b  jb      short loc_18002C032
0x18002c00d  call    cs:__imp_GetLastError
0x18002c013  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c01a  lea     r8, WPP_d9f5ad3171d43f677d32b63a5602fd0a_Traceguids
0x18002c021  mov     edx, 15h
0x18002c026  mov     r9d, eax
0x18002c029  mov     rcx, [rcx+10h]
0x18002c02d  call    WPP_SF_d
0x18002c032  call    cs:__imp_GetLastError
0x18002c038  test    eax, eax
0x18002c03a  jle     short loc_18002C044
0x18002c03c  movzx   eax, ax
0x18002c03f  or      eax, 80070000h
0x18002c044  mov     edx, eax; int
0x18002c046  lea     rcx, [rsp+558h+pExceptionObject]; this
0x18002c04b  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18002c050  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18002c057  lea     rcx, [rsp+558h+pExceptionObject]; pExceptionObject
0x18002c05c  call    _CxxThrowException_0
0x18002c062  xor     ecx, ecx
0x18002c064  mov     qword ptr [rbx+18h], 7
0x18002c06c  mov     qword ptr [rbx+10h], 0
0x18002c074  lea     rdx, [rsp+558h+var_238]
0x18002c07c  mov     [rbx], cx
0x18002c07f  mov     rcx, rbx
0x18002c082  mov     r8d, eax
0x18002c085  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@PEB_W_K@Z; std::wstring::assign(wchar_t const *,unsigned __int64)
0x18002c08a  mov     rax, rbx
0x18002c08d  mov     rcx, [rsp+558h+var_38]
0x18002c095  xor     rcx, rsp; StackCookie
0x18002c098  call    __security_check_cookie
0x18002c09d  add     rsp, 538h
0x18002c0a4  pop     rdi
0x18002c0a5  pop     rsi
0x18002c0a6  pop     rbp
0x18002c0a7  pop     rbx
0x18002c0a8  retn
```
