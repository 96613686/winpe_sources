# DEBUGMSGBOX(ushort const *,...)

- ea: `0x14005bc68`
- end: `0x14005bfe6`
- name: `?DEBUGMSGBOX@@YAHPEBGZZ`
- size: `894`
- prototype: `__int64(const unsigned __int16 *, ...)`
- caller_count: `632`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140002268`
- `0x140002454`
- `0x140002a0c`
- `0x14000308c`
- `0x140003480`
- `0x140003658`
- `0x140003b44`
- `0x140003f48`
- `0x1400045f8`
- `0x140004730`
- `0x140004804`
- `0x14000490c`
- `0x140004a04`
- `0x140004b78`
- `0x140004d1c`
- `0x140004fa8`
- `0x1400050c4`
- `0x1400051e0`
- `0x140005324`
- `0x14000558c`
- `0x1400057b8`
- `0x140005ac0`
- `0x140005d60`
- `0x140005ec4`
- `0x140006098`
- `0x140006304`
- `0x1400064a4`
- `0x140006890`
- `0x140006a10`
- `0x140006c40`
- `0x140006f20`
- `0x140007350`
- `0x140007798`
- `0x140007a44`
- `0x140007bf4`
- `0x140007d10`
- `0x1400080f0`
- `0x140008510`
- `0x1400087b0`
- `0x140008a30`
- `0x140008b40`
- `0x140008da0`
- `0x1400090dc`
- `0x1400091f8`
- `0x14000944c`
- `0x140009650`
- `0x140009778`
- `0x140009af0`
- `0x140009f08`
- `0x14000a1d0`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14005c5c0`
- `0x14005c7a8`
- `0x14007cb9e`
- `0x14007cbd0`
- `0x14007cc60`

## import_xrefs

- `KERNEL32!WriteFile` at `0x14005beca`
- `KERNEL32!WriteFile` at `0x14005bf0f`
- `KERNEL32!WriteFile` at `0x14005beca`
- `KERNEL32!WriteFile` at `0x14005bf0f`
- `KERNEL32!GetLastError` at `0x14005bed4`
- `KERNEL32!GetLastError` at `0x14005bf1d`
- `KERNEL32!GetLastError` at `0x14005bed4`
- `KERNEL32!GetLastError` at `0x14005bf1d`
- `KERNEL32!IsDebuggerPresent` at `0x14005bd72`
- `KERNEL32!IsDebuggerPresent` at `0x14005be38`
- `KERNEL32!IsDebuggerPresent` at `0x14005bf6a`
- `KERNEL32!IsDebuggerPresent` at `0x14005bd72`
- `KERNEL32!IsDebuggerPresent` at `0x14005be38`
- `KERNEL32!IsDebuggerPresent` at `0x14005bf6a`
- `msi!__imp_MsiCloseHandle` at `0x14005be92`
- `msi!__imp_MsiCloseHandle` at `0x14005be92`
- `msi!__imp_MsiCreateRecord` at `0x14005bd2b`
- `msi!__imp_MsiCreateRecord` at `0x14005bd2b`
- `msi!__imp_MsiProcessMessage` at `0x14005be85`
- `msi!__imp_MsiProcessMessage` at `0x14005be85`
- `msi!__imp_MsiRecordSetStringW` at `0x14005bdf7`
- `msi!__imp_MsiRecordSetStringW` at `0x14005bdf7`

## string_xrefs

- `0x14005bd5b`: `__EHM_MsiWrite`
- `0x14005be21`: `__EHM_MsiWrite`
- `0x14005bd19`: `termsrv\wms\src\common\ehmlib\ehmlib.cpp`
- `0x14005bf4d`: `__EHM_FlatFileWrite`

## pseudocode

```c
__int64 DEBUGMSGBOX(const unsigned __int16 *a1, ...)
{
  __int64 v2; // rdx
  const struct _EVENT_DESCRIPTOR *v3; // rdx
  __int64 v4; // rcx
  DWORD v5; // r14d
  MSIHANDLE v6; // esi
  MSIHANDLE v7; // ebx
  DWORD Record; // eax
  signed int v9; // eax
  unsigned int v10; // edi
  HANDLE v11; // rbx
  signed int v12; // eax
  signed int v13; // ebx
  unsigned int v14; // r14d
  signed int LastError; // eax
  __int64 v17; // [rsp+38h] [rbp-D0h]
  __int64 v18; // [rsp+40h] [rbp-C8h]
  DWORD NumberOfBytesWritten[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B8h]
  WCHAR szValue[4096]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+20B0h] [rbp+1FA8h] BYREF
  va_list va; // [rsp+20B0h] [rbp+1FA8h]
  va_list va1; // [rsp+20B8h] [rbp+1FB0h] BYREF

  va_start(va1, a1);
  va_start(va, a1);
  v22 = va_arg(va1, _QWORD);
  memset_0(szValue, 0, sizeof(szValue));
  *(_QWORD *)NumberOfBytesWritten = 0;
  v20 = 0;
  if ( (int)__EHM_AddPrefixToDebugMsg(szValue, v2, (unsigned __int64 *)NumberOfBytesWritten, a1, va) >= 0 )
  {
    v5 = NumberOfBytesWritten[0];
    __EHM_EtwWrite(v4, v3, szValue, NumberOfBytesWritten[0] + 1);
    v6 = g_hMsi;
    v7 = 0;
    if ( g_hMsi )
    {
      Record = MsiCreateRecord(1u);
      v7 = Record;
      NumberOfBytesWritten[0] = Record;
      if ( Record )
      {
        v9 = MsiRecordSetStringW(Record, 0, szValue);
        v10 = v9;
        if ( v9 )
        {
          if ( v9 > 0 )
            v10 = (unsigned __int16)v9 | 0x80070000;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
            0xFAu,
            L"__EHM_MsiWrite",
            L"CBRAEx",
            L"rc == 0L",
            v10);
          if ( IsDebuggerPresent() )
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
              250,
              L"__EHM_MsiWrite",
              L"CBRAEx",
              L"rc == 0L",
              v10,
              *(_QWORD *)NumberOfBytesWritten);
          else
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
              250,
              L"__EHM_MsiWrite",
              L"CBRAEx",
              L"rc == 0L",
              v10);
        }
        else
        {
          MsiProcessMessage(v6, INSTALLMESSAGE_INFO, v7);
        }
      }
      else
      {
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
          0xF7u,
          L"__EHM_MsiWrite",
          L"CPR",
          L"hRecord",
          -2147024882);
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
            247,
            L"__EHM_MsiWrite",
            L"CPR",
            L"hRecord",
            -2147024882,
            *(_QWORD *)NumberOfBytesWritten);
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
            247,
            L"__EHM_MsiWrite",
            L"CPR",
            L"hRecord",
            -2147024882);
      }
    }
    if ( v7 )
      MsiCloseHandle(v7);
    v11 = hFile;
    NumberOfBytesWritten[0] = 0;
    if ( hFile )
    {
      if ( WriteFile(hFile, szValue, 2 * v5, NumberOfBytesWritten, 0) )
      {
        if ( WriteFile(v11, L"\r\n", 6u, NumberOfBytesWritten, 0) )
          return 0;
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
        v14 = 286;
      }
      else
      {
        v12 = GetLastError();
        v13 = v12;
        if ( v12 > 0 )
          v13 = (unsigned __int16)v12 | 0x80070000;
        v14 = 283;
      }
      if ( v13 >= 0 )
        v13 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
        v14,
        L"__EHM_FlatFileWrite",
        L"CBRAEx",
        L"fSuccess",
        v13);
      if ( IsDebuggerPresent() )
      {
        LODWORD(v18) = v13;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
          v14,
          L"__EHM_FlatFileWrite",
          L"CBRAEx",
          L"fSuccess",
          v18,
          *(_QWORD *)NumberOfBytesWritten);
      }
      else
      {
        LODWORD(v17) = v13;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
          v14,
          L"__EHM_FlatFileWrite",
          L"CBRAEx",
          L"fSuccess",
          v17);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14005bc68  mov     rax, rsp
0x14005bc6b  mov     [rax+8], rcx
0x14005bc6f  mov     [rax+10h], rdx
0x14005bc73  mov     [rax+18h], r8
0x14005bc77  mov     [rax+20h], r9
0x14005bc7b  push    rbp
0x14005bc7c  push    rbx
0x14005bc7d  push    rsi
0x14005bc7e  push    rdi
0x14005bc7f  push    r12
0x14005bc81  push    r13
0x14005bc83  push    r14
0x14005bc85  lea     rbp, [rax-1F98h]
0x14005bc8c  mov     eax, 2060h
0x14005bc91  call    _alloca_probe
0x14005bc96  sub     rsp, rax
0x14005bc99  mov     rax, cs:__security_cookie
0x14005bca0  xor     rax, rsp
0x14005bca3  mov     [rbp+1F90h+var_40], rax
0x14005bcaa  mov     rbx, rcx
0x14005bcad  xor     edx, edx; Val
0x14005bcaf  mov     r8d, 2000h; Size
0x14005bcb5  lea     rcx, [rsp+2090h+szValue]; void *
0x14005bcba  call    memset_0
0x14005bcbf  mov     qword ptr [rsp+2090h+NumberOfBytesWritten], 0
0x14005bcc8  mov     [rsp+2090h+var_2048], 0
0x14005bcd1  lea     rax, [rbp+1F90h+arg_8]
0x14005bcd8  mov     [rsp+2090h+lpOverlapped], rax; char *
0x14005bcdd  mov     r9, rbx; unsigned __int16 *
0x14005bce0  lea     r8, [rsp+2090h+NumberOfBytesWritten]; unsigned __int64 *
0x14005bce5  lea     rcx, [rsp+2090h+szValue]; unsigned __int16 *
0x14005bcea  call    ?__EHM_AddPrefixToDebugMsg@@YAJPEAG_KPEA_KPEBGPEAD@Z; __EHM_AddPrefixToDebugMsg(ushort *,unsigned __int64,unsigned __int64 *,ushort const *,char *)
0x14005bcef  test    eax, eax
0x14005bcf1  js      loc_14005BFC3
0x14005bcf7  mov     r14, qword ptr [rsp+2090h+NumberOfBytesWritten]
0x14005bcfc  lea     r9, [r14+1]; unsigned __int64
0x14005bd00  lea     r8, [rsp+2090h+szValue]; unsigned __int16 *
0x14005bd05  call    ?__EHM_EtwWrite@@YAX_KPEBU_EVENT_DESCRIPTOR@@PEBG0@Z; __EHM_EtwWrite(unsigned __int64,_EVENT_DESCRIPTOR const *,ushort const *,unsigned __int64)
0x14005bd0a  mov     esi, cs:?g_hMsi@@3KA; ulong g_hMsi
0x14005bd10  xor     ebx, ebx
0x14005bd12  lea     r13, aCbraex; "CBRAEx"
0x14005bd19  lea     r12, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\ehmlib\\ehml"...
0x14005bd20  test    esi, esi
0x14005bd22  jz      loc_14005BE8C
0x14005bd28  lea     ecx, [rbx+1]; cParams
0x14005bd2b  call    cs:__imp_MsiCreateRecord
0x14005bd31  mov     ebx, eax
0x14005bd33  mov     [rsp+2090h+NumberOfBytesWritten], eax
0x14005bd37  test    eax, eax
0x14005bd39  jnz     loc_14005BDEE
0x14005bd3f  mov     edi, 8007000Eh
0x14005bd44  mov     [rsp+2090h+var_2068], edi; int
0x14005bd48  lea     rax, aHrecord; "hRecord"
0x14005bd4f  mov     [rsp+2090h+lpOverlapped], rax; unsigned __int16 *
0x14005bd54  lea     r9, aCpr; "CPR"
0x14005bd5b  lea     rsi, aEhmMsiwrite; "__EHM_MsiWrite"
0x14005bd62  mov     r8, rsi; unsigned __int16 *
0x14005bd65  mov     edx, 0F7h; unsigned int
0x14005bd6a  mov     rcx, r12; unsigned __int16 *
0x14005bd6d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005bd72  call    cs:__imp_IsDebuggerPresent
0x14005bd78  test    eax, eax
0x14005bd7a  lea     rax, aHrecord; "hRecord"
0x14005bd81  jz      short loc_14005BDBC
0x14005bd83  mov     dword ptr [rsp+2090h+var_2058], edi
0x14005bd87  mov     [rsp+2090h+var_2060], rax
0x14005bd8c  lea     rax, aCpr; "CPR"
0x14005bd93  mov     qword ptr [rsp+2090h+var_2068], rax
0x14005bd98  mov     r9d, 0F7h
0x14005bd9e  mov     [rsp+2090h+lpOverlapped], rsi
0x14005bda3  mov     r8, r12
0x14005bda6  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005bdad  mov     ecx, 2; unsigned __int8
0x14005bdb2  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005bdb7  jmp     loc_14005BE8C
0x14005bdbc  mov     dword ptr [rsp+2090h+var_2060], edi
0x14005bdc0  mov     qword ptr [rsp+2090h+var_2068], rax
0x14005bdc5  lea     rax, aCpr; "CPR"
0x14005bdcc  mov     [rsp+2090h+lpOverlapped], rax
0x14005bdd1  mov     r8d, 0F7h
0x14005bdd7  mov     r9, rsi
0x14005bdda  mov     rdx, r12
0x14005bddd  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14005bde4  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14005bde9  jmp     loc_14005BE8C
0x14005bdee  lea     r8, [rsp+2090h+szValue]; szValue
0x14005bdf3  xor     edx, edx; iField
0x14005bdf5  mov     ecx, ebx; hRecord
0x14005bdf7  call    cs:__imp_MsiRecordSetStringW
0x14005bdfd  mov     edi, eax
0x14005bdff  test    eax, eax
0x14005be01  jz      short loc_14005BE7B
0x14005be03  jle     short loc_14005BE0E
0x14005be05  movzx   edi, ax
0x14005be08  or      edi, 80070000h
0x14005be0e  mov     [rsp+2090h+var_2068], edi; int
0x14005be12  lea     rax, aRc0l; "rc == 0L"
0x14005be19  mov     [rsp+2090h+lpOverlapped], rax; unsigned __int16 *
0x14005be1e  mov     r9, r13; unsigned __int16 *
0x14005be21  lea     rsi, aEhmMsiwrite; "__EHM_MsiWrite"
0x14005be28  mov     r8, rsi; unsigned __int16 *
0x14005be2b  mov     edx, 0FAh; unsigned int
0x14005be30  mov     rcx, r12; unsigned __int16 *
0x14005be33  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005be38  call    cs:__imp_IsDebuggerPresent
0x14005be3e  test    eax, eax
0x14005be40  lea     rax, aRc0l; "rc == 0L"
0x14005be47  jz      short loc_14005BE62
0x14005be49  mov     dword ptr [rsp+2090h+var_2058], edi
0x14005be4d  mov     [rsp+2090h+var_2060], rax
0x14005be52  mov     qword ptr [rsp+2090h+var_2068], r13
0x14005be57  mov     r9d, 0FAh
0x14005be5d  jmp     loc_14005BD9E
0x14005be62  mov     dword ptr [rsp+2090h+var_2060], edi
0x14005be66  mov     qword ptr [rsp+2090h+var_2068], rax
0x14005be6b  mov     [rsp+2090h+lpOverlapped], r13
0x14005be70  mov     r8d, 0FAh
0x14005be76  jmp     loc_14005BDD7
0x14005be7b  mov     r8d, ebx; hRecord
0x14005be7e  mov     edx, 4000000h; eMessageType
0x14005be83  mov     ecx, esi; hInstall
0x14005be85  call    cs:__imp_MsiProcessMessage
0x14005be8b  nop
0x14005be8c  test    ebx, ebx
0x14005be8e  jz      short loc_14005BE98
0x14005be90  mov     ecx, ebx; hAny
0x14005be92  call    cs:__imp_MsiCloseHandle
0x14005be98  mov     rbx, cs:hFile
0x14005be9f  mov     [rsp+2090h+NumberOfBytesWritten], 0
0x14005bea7  test    rbx, rbx
0x14005beaa  jz      loc_14005BFC3
0x14005beb0  lea     r8d, [r14+r14]; nNumberOfBytesToWrite
0x14005beb4  mov     [rsp+2090h+lpOverlapped], 0; lpOverlapped
0x14005bebd  lea     r9, [rsp+2090h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14005bec2  lea     rdx, [rsp+2090h+szValue]; lpBuffer
0x14005bec7  mov     rcx, rbx; hFile
0x14005beca  call    cs:__imp_WriteFile
0x14005bed0  test    eax, eax
0x14005bed2  jnz     short loc_14005BEF1
0x14005bed4  call    cs:__imp_GetLastError
0x14005beda  mov     ebx, eax
0x14005bedc  test    eax, eax
0x14005bede  jle     short loc_14005BEE9
0x14005bee0  movzx   ebx, ax
0x14005bee3  or      ebx, 80070000h
0x14005bee9  mov     r14d, 11Bh
0x14005beef  jmp     short loc_14005BF38
0x14005bef1  mov     [rsp+2090h+lpOverlapped], 0; lpOverlapped
0x14005befa  lea     r9, [rsp+2090h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14005beff  mov     r8d, 6; nNumberOfBytesToWrite
0x14005bf05  lea     rdx, asc_1400D7808; "\r\n"
0x14005bf0c  mov     rcx, rbx; hFile
0x14005bf0f  call    cs:__imp_WriteFile
0x14005bf15  test    eax, eax
0x14005bf17  jnz     loc_14005BFC3
0x14005bf1d  call    cs:__imp_GetLastError
0x14005bf23  mov     ebx, eax
0x14005bf25  test    eax, eax
0x14005bf27  jle     short loc_14005BF32
0x14005bf29  movzx   ebx, ax
0x14005bf2c  or      ebx, 80070000h
0x14005bf32  mov     r14d, 11Eh
0x14005bf38  test    ebx, ebx
0x14005bf3a  mov     eax, 80004005h
0x14005bf3f  cmovns  ebx, eax
0x14005bf42  mov     [rsp+2090h+var_2068], ebx; int
0x14005bf46  lea     rsi, aFsuccess; "fSuccess"
0x14005bf4d  lea     rdi, aEhmFlatfilewri; "__EHM_FlatFileWrite"
0x14005bf54  mov     [rsp+2090h+lpOverlapped], rsi; unsigned __int16 *
0x14005bf59  mov     r9, r13; unsigned __int16 *
0x14005bf5c  mov     r8, rdi; unsigned __int16 *
0x14005bf5f  mov     edx, r14d; unsigned int
0x14005bf62  mov     rcx, r12; unsigned __int16 *
0x14005bf65  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005bf6a  call    cs:__imp_IsDebuggerPresent
0x14005bf70  test    eax, eax
0x14005bf72  jz      short loc_14005BFA0
0x14005bf74  mov     dword ptr [rsp+2090h+var_2058], ebx
0x14005bf78  mov     [rsp+2090h+var_2060], rsi
0x14005bf7d  mov     qword ptr [rsp+2090h+var_2068], r13
0x14005bf82  mov     [rsp+2090h+lpOverlapped], rdi
0x14005bf87  mov     r9d, r14d
0x14005bf8a  mov     r8, r12
0x14005bf8d  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005bf94  mov     ecx, 2; unsigned __int8
0x14005bf99  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005bf9e  jmp     short loc_14005BFC3
0x14005bfa0  mov     dword ptr [rsp+2090h+var_2060], ebx
0x14005bfa4  mov     qword ptr [rsp+2090h+var_2068], rsi
0x14005bfa9  mov     [rsp+2090h+lpOverlapped], r13
0x14005bfae  mov     r9, rdi
0x14005bfb1  mov     r8d, r14d
0x14005bfb4  mov     rdx, r12
0x14005bfb7  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14005bfbe  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14005bfc3  xor     eax, eax
0x14005bfc5  mov     rcx, [rbp+1F90h+var_40]
0x14005bfcc  xor     rcx, rsp; StackCookie
0x14005bfcf  call    __security_check_cookie
0x14005bfd4  add     rsp, 2060h
0x14005bfdb  pop     r14
0x14005bfdd  pop     r13
0x14005bfdf  pop     r12
0x14005bfe1  pop     rdi
0x14005bfe2  pop     rsi
0x14005bfe3  pop     rbx
0x14005bfe4  pop     rbp
0x14005bfe5  retn
```
