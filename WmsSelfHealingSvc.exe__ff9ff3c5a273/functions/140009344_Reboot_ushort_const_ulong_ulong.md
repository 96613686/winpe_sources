# Reboot(ushort const *,ulong,ulong)

- ea: `0x140009344`
- end: `0x14000946a`
- name: `?Reboot@@YAJPEBGKK@Z`
- size: `294`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400029e8`
- `0x140002c94`

## callees

- `0x1400036a0`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x1400066f4`
- `0x140009344`

## import_xrefs

- `ADVAPI32!InitiateSystemShutdownExW` at `0x1400093a4`
- `ADVAPI32!InitiateSystemShutdownExW` at `0x1400093a4`
- `KERNEL32!IsDebuggerPresent` at `0x1400093fb`
- `KERNEL32!IsDebuggerPresent` at `0x1400093fb`
- `KERNEL32!GetLastError` at `0x14000937a`
- `KERNEL32!GetLastError` at `0x14000937a`
- `KERNEL32!Sleep` at `0x140009388`
- `KERNEL32!Sleep` at `0x140009388`

## string_xrefs

- `0x1400093ef`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140009409`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140009439`: `termsrv\wms\src\common\srcutils\srcutils.cpp`

## pseudocode

```c
__int64 __fastcall Reboot(const unsigned __int16 *a1)
{
  int v1; // ebx
  signed int LastError; // eax
  int v4; // [rsp+30h] [rbp-38h]
  int v5; // [rsp+38h] [rbp-30h]

  DEBUGMSG(L"Reboot - pszMessage = %s, timeout = %i, shutdown reason = 0x%08X\n", 0, 0, 0);
  v1 = AdjustPrivilege();
  if ( v1 >= 0 )
  {
    while ( !InitiateSystemShutdownExW(0, 0, 0, 1, 1, 0) )
    {
      LastError = GetLastError();
      if ( LastError != 21 )
      {
        if ( LastError > 0 )
          v1 = (unsigned __int16)LastError | 0x80070000;
        else
          v1 = LastError;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          2466,
          L"Reboot",
          L"CBRAEx",
          L"dwError == 21L",
          v1);
        if ( IsDebuggerPresent() )
        {
          v5 = v1;
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
            2466,
            L"Reboot",
            L"CBRAEx",
            L"dwError == 21L",
            v5);
        }
        else
        {
          v4 = v1;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
            2466,
            L"Reboot",
            L"CBRAEx",
            L"dwError == 21L",
            v4);
        }
        return (unsigned int)v1;
      }
      Sleep(0x64u);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140009344  push    rbx
0x140009346  push    rbp
0x140009347  push    rdi
0x140009348  push    r14
0x14000934a  push    r15
0x14000934c  sub     rsp, 40h
0x140009350  xor     r9d, r9d
0x140009353  lea     rcx, aRebootPszmessa; "Reboot - pszMessage = %s, timeout = %i,"...
0x14000935a  xor     r8d, r8d
0x14000935d  xor     edx, edx
0x14000935f  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140009364  call    ?AdjustPrivilege@@YAJPEBGW4EPrivilegeStatus@@@Z; AdjustPrivilege(ushort const *,EPrivilegeStatus)
0x140009369  mov     ebx, eax
0x14000936b  test    eax, eax
0x14000936d  js      loc_14000945C
0x140009373  mov     edi, 1
0x140009378  jmp     short loc_14000938E
0x14000937a  call    cs:__imp_GetLastError
0x140009380  cmp     eax, 15h
0x140009383  jnz     short loc_1400093B3
0x140009385  lea     ecx, [rax+4Fh]; dwMilliseconds
0x140009388  call    cs:__imp_Sleep
0x14000938e  mov     [rsp+68h+dwReason], 0; dwReason
0x140009396  mov     r9d, edi; bForceAppsClosed
0x140009399  xor     r8d, r8d; dwTimeout
0x14000939c  mov     [rsp+68h+bRebootAfterShutdown], edi; bRebootAfterShutdown
0x1400093a0  xor     edx, edx; lpMessage
0x1400093a2  xor     ecx, ecx; lpMachineName
0x1400093a4  call    cs:__imp_InitiateSystemShutdownExW
0x1400093aa  test    eax, eax
0x1400093ac  jz      short loc_14000937A
0x1400093ae  jmp     loc_14000945C
0x1400093b3  test    eax, eax
0x1400093b5  jg      short loc_1400093BB
0x1400093b7  mov     ebx, eax
0x1400093b9  jmp     short loc_1400093C4
0x1400093bb  movzx   ebx, ax
0x1400093be  or      ebx, 80070000h
0x1400093c4  lea     r15, aCbraex; "CBRAEx"
0x1400093cb  mov     [rsp+68h+dwReason], ebx; int
0x1400093cf  lea     rbp, aReboot; "Reboot"
0x1400093d6  mov     edi, 9A2h
0x1400093db  lea     r14, aDwerror21l; "dwError == 21L"
0x1400093e2  mov     r9, r15; unsigned __int16 *
0x1400093e5  mov     r8, rbp; unsigned __int16 *
0x1400093e8  mov     qword ptr [rsp+68h+bRebootAfterShutdown], r14; unsigned __int16 *
0x1400093ed  mov     edx, edi; unsigned int
0x1400093ef  lea     rcx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400093f6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400093fb  call    cs:__imp_IsDebuggerPresent
0x140009401  test    eax, eax
0x140009403  jz      short loc_140009435
0x140009405  mov     [rsp+68h+var_30], ebx
0x140009409  lea     r8, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140009410  mov     [rsp+68h+var_38], r14
0x140009415  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000941c  mov     qword ptr [rsp+68h+dwReason], r15
0x140009421  mov     r9d, edi
0x140009424  mov     ecx, 2; unsigned __int8
0x140009429  mov     qword ptr [rsp+68h+bRebootAfterShutdown], rbp
0x14000942e  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140009433  jmp     short loc_14000945C
0x140009435  mov     dword ptr [rsp+68h+var_38], ebx
0x140009439  lea     rdx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140009440  mov     qword ptr [rsp+68h+dwReason], r14
0x140009445  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000944c  mov     r9, rbp
0x14000944f  mov     qword ptr [rsp+68h+bRebootAfterShutdown], r15
0x140009454  mov     r8d, edi
0x140009457  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000945c  mov     eax, ebx
0x14000945e  add     rsp, 40h
0x140009462  pop     r15
0x140009464  pop     r14
0x140009466  pop     rdi
0x140009467  pop     rbp
0x140009468  pop     rbx
0x140009469  retn
```
