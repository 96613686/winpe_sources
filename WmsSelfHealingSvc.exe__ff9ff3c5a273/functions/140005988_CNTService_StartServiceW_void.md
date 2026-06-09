# CNTService::StartServiceW(void)

- ea: `0x140005988`
- end: `0x140005a91`
- name: `?StartServiceW@CNTService@@QEAAHXZ`
- size: `265`
- prototype: `_BOOL8 __fastcall(CNTService *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140003218`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x140005988`

## import_xrefs

- `ADVAPI32!StartServiceCtrlDispatcherW` at `0x1400059b6`
- `ADVAPI32!StartServiceCtrlDispatcherW` at `0x1400059b6`
- `KERNEL32!IsDebuggerPresent` at `0x140005a18`
- `KERNEL32!IsDebuggerPresent` at `0x140005a18`
- `KERNEL32!GetLastError` at `0x1400059c4`
- `KERNEL32!GetLastError` at `0x1400059c4`

## string_xrefs

- `0x1400059fb`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x140005a26`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x140005a59`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x1400059e7`: `CNTService::StartServiceW`

## pseudocode

```c
_BOOL8 __fastcall CNTService::StartServiceW(CNTService *this)
{
  signed int v1; // ebx
  signed int LastError; // eax
  signed int v4; // [rsp+30h] [rbp-58h]
  signed int v5; // [rsp+38h] [rbp-50h]
  SERVICE_TABLE_ENTRYW v6; // [rsp+40h] [rbp-48h] BYREF
  __int64 v7; // [rsp+50h] [rbp-38h]
  __int64 v8; // [rsp+58h] [rbp-30h]

  v1 = 0;
  v6.lpServiceName = (LPWSTR)((char *)this + 8);
  v7 = 0;
  v6.lpServiceProc = (LPSERVICE_MAIN_FUNCTIONW)CNTService::s_ServiceMain;
  v8 = 0;
  if ( !StartServiceCtrlDispatcherW(&v6) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 >= 0 )
      v1 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
      0x2CEu,
      L"CNTService::StartServiceW",
      L"CBRAEx",
      L"fOK",
      v1);
    if ( IsDebuggerPresent() )
    {
      v5 = v1;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
        718,
        L"CNTService::StartServiceW",
        L"CBRAEx",
        L"fOK",
        v5);
    }
    else
    {
      v4 = v1;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
        718,
        L"CNTService::StartServiceW",
        L"CBRAEx",
        L"fOK",
        v4);
    }
  }
  return v1 >= 0;
}

```

## disassembly

```asm
0x140005988  mov     r11, rsp
0x14000598b  push    rbx
0x14000598c  push    rbp
0x14000598d  push    r14
0x14000598f  push    r15
0x140005991  sub     rsp, 68h
0x140005995  lea     rax, [rcx+8]
0x140005999  xor     ebx, ebx
0x14000599b  mov     [r11-48h], rax
0x14000599f  lea     rcx, [r11-48h]; lpServiceStartTable
0x1400059a3  lea     rax, ?s_ServiceMain@CNTService@@SAXKPEAPEAG@Z; CNTService::s_ServiceMain(ulong,ushort * *)
0x1400059aa  mov     [r11-38h], rbx
0x1400059ae  mov     [r11-40h], rax
0x1400059b2  mov     [r11-30h], rbx
0x1400059b6  call    cs:__imp_StartServiceCtrlDispatcherW
0x1400059bc  test    eax, eax
0x1400059be  jnz     loc_140005A7F
0x1400059c4  call    cs:__imp_GetLastError
0x1400059ca  mov     ebx, eax
0x1400059cc  test    eax, eax
0x1400059ce  jle     short loc_1400059D9
0x1400059d0  movzx   ebx, ax
0x1400059d3  or      ebx, 80070000h
0x1400059d9  mov     eax, 80004005h
0x1400059de  lea     r15, aCbraex; "CBRAEx"
0x1400059e5  test    ebx, ebx
0x1400059e7  lea     rbp, aCntserviceStar; "CNTService::StartServiceW"
0x1400059ee  lea     r14, aFok; "fOK"
0x1400059f5  mov     r9, r15; unsigned __int16 *
0x1400059f8  cmovns  ebx, eax
0x1400059fb  lea     rcx, aTermsrvWmsSrcC_5; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x140005a02  mov     [rsp+88h+var_60], ebx; int
0x140005a06  mov     r8, rbp; unsigned __int16 *
0x140005a09  mov     edx, 2CEh; unsigned int
0x140005a0e  mov     [rsp+88h+var_68], r14; unsigned __int16 *
0x140005a13  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140005a18  call    cs:__imp_IsDebuggerPresent
0x140005a1e  test    eax, eax
0x140005a20  jz      short loc_140005A55
0x140005a22  mov     [rsp+88h+var_50], ebx
0x140005a26  lea     r8, aTermsrvWmsSrcC_5; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x140005a2d  mov     [rsp+88h+var_58], r14
0x140005a32  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140005a39  mov     qword ptr [rsp+88h+var_60], r15
0x140005a3e  mov     r9d, 2CEh
0x140005a44  mov     ecx, 2; unsigned __int8
0x140005a49  mov     [rsp+88h+var_68], rbp
0x140005a4e  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140005a53  jmp     short loc_140005A7F
0x140005a55  mov     dword ptr [rsp+88h+var_58], ebx
0x140005a59  lea     rdx, aTermsrvWmsSrcC_5; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x140005a60  mov     qword ptr [rsp+88h+var_60], r14
0x140005a65  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140005a6c  mov     r9, rbp
0x140005a6f  mov     [rsp+88h+var_68], r15
0x140005a74  mov     r8d, 2CEh
0x140005a7a  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140005a7f  not     ebx
0x140005a81  shr     ebx, 1Fh
0x140005a84  mov     eax, ebx
0x140005a86  add     rsp, 68h
0x140005a8a  pop     r15
0x140005a8c  pop     r14
0x140005a8e  pop     rbp
0x140005a8f  pop     rbx
0x140005a90  retn
```
