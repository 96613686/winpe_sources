# WebAppUtil::CreateWebLink(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800184e4`
- end: `0x1800187ee`
- name: `?CreateWebLink@WebAppUtil@@SAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `778`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800182b4`

## callees

- `0x1800062ac`
- `0x1800065f8`
- `0x180009d64`
- `0x180009e20`
- `0x18000a2c0`
- `0x18000a3c0`
- `0x1800184e4`
- `0x18001f420`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180018741`
- `KERNEL32!CloseHandle` at `0x180018741`
- `KERNEL32!GetLastError` at `0x180018591`
- `KERNEL32!GetLastError` at `0x18001866d`
- `KERNEL32!GetLastError` at `0x1800186e9`
- `KERNEL32!GetLastError` at `0x180018591`
- `KERNEL32!GetLastError` at `0x18001866d`
- `KERNEL32!GetLastError` at `0x1800186e9`
- `KERNEL32!DeleteFileW` at `0x18001875c`
- `KERNEL32!DeleteFileW` at `0x18001875c`
- `KERNEL32!CreateFileW` at `0x18001857c`
- `KERNEL32!CreateFileW` at `0x18001857c`
- `KERNEL32!WriteFile` at `0x18001865d`
- `KERNEL32!WriteFile` at `0x1800186d5`
- `KERNEL32!WriteFile` at `0x18001865d`
- `KERNEL32!WriteFile` at `0x1800186d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WebAppUtil::CreateWebLink(const WCHAR *lpFileName, __int64 a2)
{
  const WCHAR *v3; // rdi
  unsigned int v4; // ebx
  HANDLE FileW; // rsi
  signed int LastError; // eax
  __int64 v7; // rdx
  const WCHAR *v8; // r9
  signed int v9; // eax
  LPCWSTR v10; // rcx
  __int64 v11; // rdx
  LPCVOID *v12; // rdx
  signed int v13; // eax
  const WCHAR *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int16 Buffer[2]; // [rsp+40h] [rbp-40h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-3Ch] BYREF
  const WCHAR *v20; // [rsp+48h] [rbp-38h]
  __int64 v21; // [rsp+50h] [rbp-30h]
  LPCVOID lpBuffer[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v23; // [rsp+68h] [rbp-18h]
  unsigned __int64 v24; // [rsp+70h] [rbp-10h]

  v3 = lpFileName;
  v20 = lpFileName;
  v21 = a2;
  NumberOfBytesWritten = 0;
  v24 = 7;
  v23 = 0;
  LOWORD(lpBuffer[0]) = 0;
  if ( !*((_QWORD *)lpFileName + 2) || !*(_QWORD *)(a2 + 16) )
  {
    v4 = -2147024809;
LABEL_33:
    if ( *((_QWORD *)v3 + 3) < 8u )
      v14 = v3;
    else
      v14 = *(const WCHAR **)v3;
    DeleteFileW(v14);
    goto LABEL_40;
  }
  if ( *((_QWORD *)lpFileName + 3) >= 8u )
    lpFileName = *(const WCHAR **)lpFileName;
  FileW = CreateFileW(lpFileName, 0x40000000u, 1u, 0, 2u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      if ( *((_QWORD *)v3 + 3) < 8u )
        LODWORD(v8) = (_DWORD)v3;
      else
        v8 = *(const WCHAR **)v3;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids,
        (_DWORD)v8,
        v4);
    }
    goto LABEL_30;
  }
  std::wstring::assign(lpBuffer, L"[InternetShortcut]\r\n");
  std::wstring::append(lpBuffer, L"URL=");
  std::wstring::append(lpBuffer, a2, 0, -1);
  std::wstring::append(lpBuffer, L"\r\n");
  Buffer[0] = -257;
  if ( !WriteFile(FileW, Buffer, 2u, &NumberOfBytesWritten, 0) )
  {
    v9 = GetLastError();
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_30;
    v11 = 16;
    goto LABEL_29;
  }
  v12 = lpBuffer;
  if ( v24 >= 8 )
    v12 = (LPCVOID *)lpBuffer[0];
  if ( !WriteFile(FileW, v12, 2 * v23, &NumberOfBytesWritten, 0) )
  {
    v13 = GetLastError();
    v4 = v13;
    if ( v13 > 0 )
      v4 = (unsigned __int16)v13 | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_30;
    v11 = 17;
LABEL_29:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids, v4);
LABEL_30:
    if ( (v4 & 0x80000000) == 0 )
      goto LABEL_40;
    if ( FileW )
      CloseHandle(FileW);
    goto LABEL_33;
  }
  v4 = 0;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids,
      NumberOfBytesWritten);
LABEL_40:
  LOBYTE(v7) = 1;
  std::wstring::_Tidy(lpBuffer, v7, 0);
  LOBYTE(v15) = 1;
  std::wstring::_Tidy(v3, v15, 0);
  LOBYTE(v16) = 1;
  std::wstring::_Tidy(a2, v16, 0);
  return v4;
}

```

## disassembly

```asm
0x1800184e4  mov     [rsp-18h+arg_10], rbx
0x1800184e9  mov     [rsp-18h+arg_18], rsi
0x1800184ee  push    rbp
0x1800184ef  push    rdi
0x1800184f0  push    r14
0x1800184f2  mov     rbp, rsp
0x1800184f5  sub     rsp, 80h
0x1800184fc  mov     rax, cs:__security_cookie
0x180018503  xor     rax, rsp
0x180018506  mov     [rbp+var_8], rax
0x18001850a  mov     r14, rdx
0x18001850d  mov     rdi, rcx
0x180018510  mov     [rbp+var_38], rcx
0x180018514  mov     [rbp+var_30], rdx
0x180018518  mov     [rbp+NumberOfBytesWritten], 0
0x18001851f  mov     [rbp+var_10], 7
0x180018527  mov     [rbp+var_18], 0
0x18001852f  xor     eax, eax
0x180018531  mov     word ptr [rbp+lpBuffer], ax
0x180018535  cmp     [rcx+10h], rax
0x180018539  jnz     short loc_180018545
0x18001853b  mov     ebx, 80070057h
0x180018540  jmp     loc_18001874D
0x180018545  cmp     qword ptr [rdx+10h], 0
0x18001854a  jz      short loc_18001853B
0x18001854c  cmp     qword ptr [rcx+18h], 8
0x180018551  jb      short loc_180018556
0x180018553  mov     rcx, [rcx]; lpFileName
0x180018556  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18001855f  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180018567  mov     ebx, 2
0x18001856c  mov     [rsp+80h+dwCreationDisposition], ebx; dwCreationDisposition
0x180018570  xor     r9d, r9d; lpSecurityAttributes
0x180018573  mov     edx, 40000000h; dwDesiredAccess
0x180018578  lea     r8d, [rbx-1]; dwShareMode
0x18001857c  call    cs:__imp_CreateFileW
0x180018583  nop     dword ptr [rax+rax+00h]
0x180018588  mov     rsi, rax
0x18001858b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001858f  jnz     short loc_1800185FA
0x180018591  call    cs:__imp_GetLastError
0x180018598  nop     dword ptr [rax+rax+00h]
0x18001859d  mov     ebx, eax
0x18001859f  test    eax, eax
0x1800185a1  jle     short loc_1800185AC
0x1800185a3  movzx   ebx, ax
0x1800185a6  or      ebx, 80070000h
0x1800185ac  lea     rax, WPP_GLOBAL_Control
0x1800185b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185ba  cmp     rcx, rax
0x1800185bd  jz      loc_180018735
0x1800185c3  test    byte ptr [rcx+1Ch], 4
0x1800185c7  jz      loc_180018735
0x1800185cd  cmp     qword ptr [rdi+18h], 8
0x1800185d2  jb      short loc_1800185D9
0x1800185d4  mov     r9, [rdi]
0x1800185d7  jmp     short loc_1800185DC
0x1800185d9  mov     r9, rdi
0x1800185dc  mov     edx, 0Fh
0x1800185e1  mov     [rsp+80h+dwCreationDisposition], ebx
0x1800185e5  lea     r8, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids
0x1800185ec  mov     rcx, [rcx+10h]
0x1800185f0  call    WPP_SF_Sd
0x1800185f5  jmp     loc_180018735
0x1800185fa  lea     rdx, aInternetshortc; "[InternetShortcut]\r\n"
0x180018601  lea     rcx, [rbp+lpBuffer]
0x180018605  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001860a  lea     rdx, aUrl; "URL="
0x180018611  lea     rcx, [rbp+lpBuffer]
0x180018615  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18001861a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001861e  xor     r8d, r8d
0x180018621  mov     rdx, r14
0x180018624  lea     rcx, [rbp+lpBuffer]
0x180018628  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001862d  lea     rdx, asc_18002406C; "\r\n"
0x180018634  lea     rcx, [rbp+lpBuffer]
0x180018638  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18001863d  mov     eax, 0FEFFh
0x180018642  mov     [rbp+Buffer], ax
0x180018646  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; lpOverlapped
0x18001864f  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180018653  mov     r8d, ebx; nNumberOfBytesToWrite
0x180018656  lea     rdx, [rbp+Buffer]; lpBuffer
0x18001865a  mov     rcx, rsi; hFile
0x18001865d  call    cs:__imp_WriteFile
0x180018664  nop     dword ptr [rax+rax+00h]
0x180018669  test    eax, eax
0x18001866b  jnz     short loc_1800186B0
0x18001866d  call    cs:__imp_GetLastError
0x180018674  nop     dword ptr [rax+rax+00h]
0x180018679  mov     ebx, eax
0x18001867b  test    eax, eax
0x18001867d  jle     short loc_180018688
0x18001867f  movzx   ebx, ax
0x180018682  or      ebx, 80070000h
0x180018688  lea     rax, WPP_GLOBAL_Control
0x18001868f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018696  cmp     rcx, rax
0x180018699  jz      loc_180018735
0x18001869f  test    byte ptr [rcx+1Ch], 4
0x1800186a3  jz      loc_180018735
0x1800186a9  mov     edx, 10h
0x1800186ae  jmp     short loc_180018722
0x1800186b0  mov     r8d, dword ptr [rbp+var_18]
0x1800186b4  lea     rdx, [rbp+lpBuffer]
0x1800186b8  cmp     [rbp+var_10], 8
0x1800186bd  cmovnb  rdx, [rbp+lpBuffer]; lpBuffer
0x1800186c2  add     r8d, r8d; nNumberOfBytesToWrite
0x1800186c5  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; lpOverlapped
0x1800186ce  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800186d2  mov     rcx, rsi; hFile
0x1800186d5  call    cs:__imp_WriteFile
0x1800186dc  nop     dword ptr [rax+rax+00h]
0x1800186e1  test    eax, eax
0x1800186e3  jnz     loc_18001876A
0x1800186e9  call    cs:__imp_GetLastError
0x1800186f0  nop     dword ptr [rax+rax+00h]
0x1800186f5  mov     ebx, eax
0x1800186f7  test    eax, eax
0x1800186f9  jle     short loc_180018704
0x1800186fb  movzx   ebx, ax
0x1800186fe  or      ebx, 80070000h
0x180018704  lea     rax, WPP_GLOBAL_Control
0x18001870b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018712  cmp     rcx, rax
0x180018715  jz      short loc_180018735
0x180018717  test    byte ptr [rcx+1Ch], 4
0x18001871b  jz      short loc_180018735
0x18001871d  mov     edx, 11h
0x180018722  mov     r9d, ebx
0x180018725  lea     r8, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids
0x18001872c  mov     rcx, [rcx+10h]
0x180018730  call    WPP_SF_d
0x180018735  test    ebx, ebx
0x180018737  jns     short loc_18001879D
0x180018739  test    rsi, rsi
0x18001873c  jz      short loc_18001874D
0x18001873e  mov     rcx, rsi; hObject
0x180018741  call    cs:__imp_CloseHandle
0x180018748  nop     dword ptr [rax+rax+00h]
0x18001874d  cmp     qword ptr [rdi+18h], 8
0x180018752  jb      short loc_180018759
0x180018754  mov     rcx, [rdi]
0x180018757  jmp     short loc_18001875C
0x180018759  mov     rcx, rdi; lpFileName
0x18001875c  call    cs:__imp_DeleteFileW
0x180018763  nop     dword ptr [rax+rax+00h]
0x180018768  jmp     short loc_18001879D
0x18001876a  xor     ebx, ebx
0x18001876c  lea     rax, WPP_GLOBAL_Control
0x180018773  mov     rcx, cs:WPP_GLOBAL_Control
0x18001877a  cmp     rcx, rax
0x18001877d  jz      short loc_18001879D
0x18001877f  test    byte ptr [rcx+1Ch], 1
0x180018783  jz      short loc_18001879D
0x180018785  lea     edx, [rbx+12h]
0x180018788  mov     r9d, [rbp+NumberOfBytesWritten]
0x18001878c  lea     r8, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids
0x180018793  mov     rcx, [rcx+10h]
0x180018797  call    WPP_SF_d
0x18001879c  nop
0x18001879d  xor     r8d, r8d
0x1800187a0  mov     dl, 1
0x1800187a2  lea     rcx, [rbp+lpBuffer]
0x1800187a6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800187ab  nop
0x1800187ac  xor     r8d, r8d
0x1800187af  mov     dl, 1
0x1800187b1  mov     rcx, rdi
0x1800187b4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800187b9  nop
0x1800187ba  xor     r8d, r8d
0x1800187bd  mov     dl, 1
0x1800187bf  mov     rcx, r14
0x1800187c2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800187c7  mov     eax, ebx
0x1800187c9  mov     rcx, [rbp+var_8]
0x1800187cd  xor     rcx, rsp; StackCookie
0x1800187d0  call    __security_check_cookie
0x1800187d5  lea     r11, [rsp+80h+var_s0]
0x1800187dd  mov     rbx, [r11+30h]
0x1800187e1  mov     rsi, [r11+38h]
0x1800187e5  mov     rsp, r11
0x1800187e8  pop     r14
0x1800187ea  pop     rdi
0x1800187eb  pop     rbp
0x1800187ec  retn
```
