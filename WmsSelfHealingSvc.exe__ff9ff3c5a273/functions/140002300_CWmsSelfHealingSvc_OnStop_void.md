# CWmsSelfHealingSvc::OnStop(void)

- ea: `0x140002300`
- end: `0x140002486`
- name: `?OnStop@CWmsSelfHealingSvc@@UEAAXXZ`
- size: `390`
- prototype: `void __fastcall(CWmsSelfHealingSvc *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140002300`
- `0x1400036a0`
- `0x1400036d8`
- `0x140003918`
- `0x140003ab4`
- `0x140003c2c`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140002474`
- `KERNEL32!WaitForSingleObject` at `0x140002474`
- `KERNEL32!SetEvent` at `0x1400023b3`
- `KERNEL32!SetEvent` at `0x1400023b3`
- `KERNEL32!IsDebuggerPresent` at `0x14000234f`
- `KERNEL32!IsDebuggerPresent` at `0x14000240a`
- `KERNEL32!IsDebuggerPresent` at `0x14000234f`
- `KERNEL32!IsDebuggerPresent` at `0x14000240a`
- `KERNEL32!GetLastError` at `0x1400023c1`
- `KERNEL32!GetLastError` at `0x1400023c1`

## string_xrefs

- `0x140002333`: `m_hThreadProcKillEvent != NULL`

## pseudocode

```c
void __fastcall CWmsSelfHealingSvc::OnStop(CWmsSelfHealingSvc *this)
{
  const unsigned __int16 *v2; // r9
  signed int LastError; // eax
  signed int v4; // ebx
  const unsigned __int16 *v5; // [rsp+30h] [rbp-38h]

  DEBUGMSG(L"CWmsSelfHealingSvc::OnStop\n");
  if ( !*((_QWORD *)this + 111) )
  {
    LOGASSERT(
      L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
      128,
      L"CWmsSelfHealingSvc::OnStop",
      v2,
      L"m_hThreadProcKillEvent != NULL");
    if ( IsDebuggerPresent() )
    {
      v5 = L"m_hThreadProcKillEvent != NULL";
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp");
    }
    else
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
        128,
        L"CWmsSelfHealingSvc::OnStop",
        L"ASSERT",
        L"m_hThreadProcKillEvent != NULL");
    }
  }
  if ( SetEvent(*((HANDLE *)this + 111)) )
  {
    WaitForSingleObject(*((HANDLE *)this + 110), 0xFFFFFFFF);
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
      v4 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
      130,
      L"CWmsSelfHealingSvc::OnStop",
      L"CBRAEx",
      L"fSuccess",
      v4);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp");
    }
    else
    {
      LODWORD(v5) = v4;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
        130,
        L"CWmsSelfHealingSvc::OnStop",
        L"CBRAEx",
        L"fSuccess",
        v5);
    }
  }
}

```

## disassembly

```asm
0x140002300  push    rbx
0x140002302  push    rsi
0x140002303  push    rdi
0x140002304  push    r14
0x140002306  push    r15
0x140002308  sub     rsp, 40h
0x14000230c  mov     rbx, rcx
0x14000230f  lea     rcx, aCwmsselfhealin_7; "CWmsSelfHealingSvc::OnStop\n"
0x140002316  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000231b  cmp     qword ptr [rbx+378h], 0
0x140002323  lea     rsi, aCwmsselfhealin_26; "CWmsSelfHealingSvc::OnStop"
0x14000232a  lea     rdi, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140002331  jnz     short loc_1400023AC
0x140002333  lea     r14, aMHthreadprocki; "m_hThreadProcKillEvent != NULL"
0x14000233a  mov     r8, rsi; unsigned __int16 *
0x14000233d  mov     edx, 80h; unsigned int
0x140002342  mov     [rsp+68h+var_48], r14; unsigned __int16 *
0x140002347  mov     rcx, rdi; unsigned __int16 *
0x14000234a  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x14000234f  call    cs:__imp_IsDebuggerPresent
0x140002355  test    eax, eax
0x140002357  lea     rax, aAssert; "ASSERT"
0x14000235e  jz      short loc_14000238A
0x140002360  mov     r9d, 80h
0x140002366  mov     [rsp+68h+var_38], r14
0x14000236b  mov     qword ptr [rsp+68h+var_40], rax
0x140002370  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140002377  mov     r8, rdi
0x14000237a  mov     [rsp+68h+var_48], rsi
0x14000237f  lea     ecx, [r9-7Eh]; unsigned __int8
0x140002383  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140002388  jmp     short loc_1400023AC
0x14000238a  mov     qword ptr [rsp+68h+var_40], r14
0x14000238f  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140002396  mov     r9, rsi
0x140002399  mov     [rsp+68h+var_48], rax
0x14000239e  mov     r8d, 80h
0x1400023a4  mov     rdx, rdi
0x1400023a7  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400023ac  mov     rcx, [rbx+378h]; hEvent
0x1400023b3  call    cs:__imp_SetEvent
0x1400023b9  test    eax, eax
0x1400023bb  jnz     loc_14000246A
0x1400023c1  call    cs:__imp_GetLastError
0x1400023c7  mov     ebx, eax
0x1400023c9  test    eax, eax
0x1400023cb  jle     short loc_1400023D6
0x1400023cd  movzx   ebx, ax
0x1400023d0  or      ebx, 80070000h
0x1400023d6  mov     eax, 80004005h
0x1400023db  lea     r15, aCbraex; "CBRAEx"
0x1400023e2  test    ebx, ebx
0x1400023e4  lea     r14, aFsuccess; "fSuccess"
0x1400023eb  mov     r9, r15; unsigned __int16 *
0x1400023ee  mov     r8, rsi; unsigned __int16 *
0x1400023f1  cmovns  ebx, eax
0x1400023f4  mov     edx, 82h; unsigned int
0x1400023f9  mov     [rsp+68h+var_40], ebx; int
0x1400023fd  mov     rcx, rdi; unsigned __int16 *
0x140002400  mov     [rsp+68h+var_48], r14; unsigned __int16 *
0x140002405  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000240a  call    cs:__imp_IsDebuggerPresent
0x140002410  test    eax, eax
0x140002412  jz      short loc_140002442
0x140002414  mov     [rsp+68h+var_30], ebx
0x140002418  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000241f  mov     r9d, 82h
0x140002425  mov     [rsp+68h+var_38], r14
0x14000242a  mov     qword ptr [rsp+68h+var_40], r15
0x14000242f  mov     r8, rdi
0x140002432  mov     [rsp+68h+var_48], rsi
0x140002437  lea     ecx, [r9-80h]; unsigned __int8
0x14000243b  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140002440  jmp     short loc_14000247A
0x140002442  mov     dword ptr [rsp+68h+var_38], ebx
0x140002446  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000244d  mov     qword ptr [rsp+68h+var_40], r14
0x140002452  mov     r9, rsi
0x140002455  mov     r8d, 82h
0x14000245b  mov     [rsp+68h+var_48], r15
0x140002460  mov     rdx, rdi
0x140002463  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140002468  jmp     short loc_14000247A
0x14000246a  mov     rcx, [rbx+370h]; hHandle
0x140002471  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140002474  call    cs:__imp_WaitForSingleObject
0x14000247a  add     rsp, 40h
0x14000247e  pop     r15
0x140002480  pop     r14
0x140002482  pop     rdi
0x140002483  pop     rsi
0x140002484  pop     rbx
0x140002485  retn
```
