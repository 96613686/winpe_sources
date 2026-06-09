# DoesDirectoryExist(ushort const *,EObjectPresence *)

- ea: `0x140066898`
- end: `0x140066ac2`
- name: `?DoesDirectoryExist@@YAJPEBGPEAW4EObjectPresence@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, enum EObjectPresence *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140012b88`
- `0x14001381c`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140066898`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140066a92`
- `KERNEL32!CloseHandle` at `0x140066a92`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400668e7`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400668e7`
- `KERNEL32!CreateFileW` at `0x1400669c8`
- `KERNEL32!CreateFileW` at `0x1400669c8`
- `KERNEL32!GetLastError` at `0x1400668fc`
- `KERNEL32!GetLastError` at `0x1400669d1`
- `KERNEL32!GetLastError` at `0x1400668fc`
- `KERNEL32!GetLastError` at `0x1400669d1`
- `KERNEL32!IsDebuggerPresent` at `0x140066950`
- `KERNEL32!IsDebuggerPresent` at `0x140066a2d`
- `KERNEL32!IsDebuggerPresent` at `0x140066950`
- `KERNEL32!IsDebuggerPresent` at `0x140066a2d`

## string_xrefs

- `0x140066929`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x14006696b`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140066a1c`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140066a53`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140066936`: `dwResult != 0 && dwResult <= (sizeof(*RtlpNumberOf(szTemp)))`
- `0x140066958`: `dwResult != 0 && dwResult <= (sizeof(*RtlpNumberOf(szTemp)))`
- `0x14006691f`: `DoesDirectoryExist`
- `0x140066a0f`: `DoesDirectoryExist`

## pseudocode

```c
__int64 __fastcall DoesDirectoryExist(LPCWSTR lpSrc, enum EObjectPresence *a2)
{
  int v4; // r15d
  char *FileW; // rdi
  signed int LastError; // eax
  signed int v7; // ebx
  bool v8; // zf
  const unsigned __int16 *v9; // rax
  __int64 v10; // r9
  __int64 v11; // r8
  signed int v12; // eax
  HANDLE hTemplateFile; // [rsp+30h] [rbp-258h]
  WCHAR Dst[264]; // [rsp+40h] [rbp-248h] BYREF

  v4 = 0;
  memset_0(Dst, 0, 0x208u);
  if ( ExpandEnvironmentStringsW(lpSrc, Dst, 0x104u) - 1 > 0x103 )
  {
    FileW = 0;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
      v7 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0xF32u,
      L"DoesDirectoryExist",
      L"CBRAEx",
      L"dwResult != 0 && dwResult <= (sizeof(*RtlpNumberOf(szTemp)))",
      v7);
    v8 = !IsDebuggerPresent();
    v9 = L"dwResult != 0 && dwResult <= (sizeof(*RtlpNumberOf(szTemp)))";
    if ( !v8 )
    {
      v10 = 3890;
LABEL_8:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v10,
        L"DoesDirectoryExist",
        L"CBRAEx",
        v9,
        v7);
      goto LABEL_18;
    }
    v11 = 3890;
    goto LABEL_17;
  }
  FileW = (char *)CreateFileW(Dst, 0x120088u, 1u, 0, 3u, 0x2000080u, 0);
  v12 = GetLastError();
  v7 = v12;
  if ( (unsigned int)(v12 - 2) > 1 )
  {
    if ( v12 )
    {
      if ( v12 > 0 )
        v7 = (unsigned __int16)v12 | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0xF3Du,
        L"DoesDirectoryExist",
        L"CBRAEx",
        L"dwResult == 0L",
        v7);
      v8 = !IsDebuggerPresent();
      v9 = L"dwResult == 0L";
      if ( !v8 )
      {
        v10 = 3901;
        goto LABEL_8;
      }
      v11 = 3901;
LABEL_17:
      LODWORD(hTemplateFile) = v7;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v11,
        L"DoesDirectoryExist",
        L"CBRAEx",
        v9,
        hTemplateFile);
LABEL_18:
      if ( v7 < 0 )
        goto LABEL_23;
      goto LABEL_22;
    }
    v4 = 1;
  }
  v7 = 0;
LABEL_22:
  *(_DWORD *)a2 = v4;
LABEL_23:
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140066898  mov     [rsp+arg_10], rbx
0x14006689d  push    rbp
0x14006689e  push    rdi
0x14006689f  push    r12
0x1400668a1  push    r14
0x1400668a3  push    r15
0x1400668a5  sub     rsp, 260h
0x1400668ac  mov     rax, cs:__security_cookie
0x1400668b3  xor     rax, rsp
0x1400668b6  mov     [rsp+288h+var_38], rax
0x1400668be  mov     r12, rdx
0x1400668c1  mov     rbx, rcx
0x1400668c4  xor     edx, edx; Val
0x1400668c6  lea     rcx, [rsp+288h+Dst]; void *
0x1400668cb  mov     r8d, 208h; Size
0x1400668d1  xor     r15d, r15d
0x1400668d4  call    memset_0
0x1400668d9  mov     r8d, 104h; nSize
0x1400668df  lea     rdx, [rsp+288h+Dst]; lpDst
0x1400668e4  mov     rcx, rbx; lpSrc
0x1400668e7  call    cs:__imp_ExpandEnvironmentStringsW
0x1400668ed  dec     eax
0x1400668ef  cmp     eax, 103h
0x1400668f4  jbe     loc_1400669A2
0x1400668fa  xor     edi, edi
0x1400668fc  call    cs:__imp_GetLastError
0x140066902  mov     ebx, eax
0x140066904  test    eax, eax
0x140066906  jle     short loc_140066911
0x140066908  movzx   ebx, ax
0x14006690b  or      ebx, 80070000h
0x140066911  mov     eax, 80004005h
0x140066916  lea     r14, aCbraex; "CBRAEx"
0x14006691d  test    ebx, ebx
0x14006691f  lea     rbp, aDoesdirectorye; "DoesDirectoryExist"
0x140066926  mov     r9, r14; unsigned __int16 *
0x140066929  lea     rcx, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140066930  cmovns  ebx, eax
0x140066933  mov     r8, rbp; unsigned __int16 *
0x140066936  lea     rax, aDwresult0Dwres_1; "dwResult != 0 && dwResult <= (sizeof(*R"...
0x14006693d  mov     [rsp+288h+dwFlagsAndAttributes], ebx; int
0x140066941  mov     edx, 0F32h; unsigned int
0x140066946  mov     qword ptr [rsp+288h+dwCreationDisposition], rax; unsigned __int16 *
0x14006694b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140066950  call    cs:__imp_IsDebuggerPresent
0x140066956  test    eax, eax
0x140066958  lea     rax, aDwresult0Dwres_1; "dwResult != 0 && dwResult <= (sizeof(*R"...
0x14006695f  jz      short loc_140066997
0x140066961  mov     r9d, 0F32h
0x140066967  mov     [rsp+288h+var_250], ebx
0x14006696b  lea     r8, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140066972  mov     [rsp+288h+hTemplateFile], rax
0x140066977  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14006697e  mov     qword ptr [rsp+288h+dwFlagsAndAttributes], r14
0x140066983  mov     ecx, 2; unsigned __int8
0x140066988  mov     qword ptr [rsp+288h+dwCreationDisposition], rbp
0x14006698d  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140066992  jmp     loc_140066A73
0x140066997  mov     r8d, 0F32h
0x14006699d  jmp     loc_140066A4F
0x1400669a2  xor     r9d, r9d; lpSecurityAttributes
0x1400669a5  mov     [rsp+288h+hTemplateFile], r15; hTemplateFile
0x1400669aa  mov     [rsp+288h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x1400669b2  lea     rcx, [rsp+288h+Dst]; lpFileName
0x1400669b7  mov     edx, 120088h; dwDesiredAccess
0x1400669bc  mov     [rsp+288h+dwCreationDisposition], 3; dwCreationDisposition
0x1400669c4  lea     r8d, [r9+1]; dwShareMode
0x1400669c8  call    cs:__imp_CreateFileW
0x1400669ce  mov     rdi, rax
0x1400669d1  call    cs:__imp_GetLastError
0x1400669d7  mov     ebx, eax
0x1400669d9  lea     ecx, [rax-2]
0x1400669dc  cmp     ecx, 1
0x1400669df  jbe     loc_140066A7F
0x1400669e5  test    eax, eax
0x1400669e7  jz      loc_140066A79
0x1400669ed  jle     short loc_1400669F8
0x1400669ef  movzx   ebx, ax
0x1400669f2  or      ebx, 80070000h
0x1400669f8  lea     rax, aDwresult0l; "dwResult == 0L"
0x1400669ff  mov     [rsp+288h+dwFlagsAndAttributes], ebx; int
0x140066a03  lea     r14, aCbraex; "CBRAEx"
0x140066a0a  mov     qword ptr [rsp+288h+dwCreationDisposition], rax; unsigned __int16 *
0x140066a0f  lea     rbp, aDoesdirectorye; "DoesDirectoryExist"
0x140066a16  mov     r9, r14; unsigned __int16 *
0x140066a19  mov     r8, rbp; unsigned __int16 *
0x140066a1c  lea     rcx, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140066a23  mov     edx, 0F3Dh; unsigned int
0x140066a28  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140066a2d  call    cs:__imp_IsDebuggerPresent
0x140066a33  test    eax, eax
0x140066a35  lea     rax, aDwresult0l; "dwResult == 0L"
0x140066a3c  jz      short loc_140066A49
0x140066a3e  mov     r9d, 0F3Dh
0x140066a44  jmp     loc_140066967
0x140066a49  mov     r8d, 0F3Dh
0x140066a4f  mov     dword ptr [rsp+288h+hTemplateFile], ebx
0x140066a53  lea     rdx, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140066a5a  mov     qword ptr [rsp+288h+dwFlagsAndAttributes], rax
0x140066a5f  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140066a66  mov     r9, rbp
0x140066a69  mov     qword ptr [rsp+288h+dwCreationDisposition], r14
0x140066a6e  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140066a73  test    ebx, ebx
0x140066a75  js      short loc_140066A85
0x140066a77  jmp     short loc_140066A81
0x140066a79  mov     r15d, 1
0x140066a7f  xor     ebx, ebx
0x140066a81  mov     [r12], r15d
0x140066a85  lea     rcx, [rdi-1]
0x140066a89  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140066a8d  ja      short loc_140066A98
0x140066a8f  mov     rcx, rdi; hObject
0x140066a92  call    cs:__imp_CloseHandle
0x140066a98  mov     eax, ebx
0x140066a9a  mov     rcx, [rsp+288h+var_38]
0x140066aa2  xor     rcx, rsp; StackCookie
0x140066aa5  call    __security_check_cookie
0x140066aaa  mov     rbx, [rsp+288h+arg_10]
0x140066ab2  add     rsp, 260h
0x140066ab9  pop     r15
0x140066abb  pop     r14
0x140066abd  pop     r12
0x140066abf  pop     rdi
0x140066ac0  pop     rbp
0x140066ac1  retn
```
