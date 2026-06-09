# DiagHubCommon::DhTryDebugBreak::DhTryDebugBreak(ushort const *)

- ea: `0x140001230`
- end: `0x140001388`
- name: `??0DhTryDebugBreak@DiagHubCommon@@QEAA@PEBG@Z`
- size: `344`
- prototype: `DiagHubCommon::DhTryDebugBreak *__fastcall(DiagHubCommon::DhTryDebugBreak *this, unsigned __int16 *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001388`

## callees

- `0x140001230`
- `0x140001f2c`
- `0x140003220`
- `0x1400137e0`
- `0x14001473e`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1400012fd`
- `KERNEL32!GetCurrentProcessId` at `0x1400012fd`
- `KERNEL32!IsDebuggerPresent` at `0x140001343`
- `KERNEL32!IsDebuggerPresent` at `0x140001343`
- `KERNEL32!OutputDebugStringW` at `0x140001332`
- `KERNEL32!OutputDebugStringW` at `0x140001332`
- `KERNEL32!Sleep` at `0x14000133d`
- `KERNEL32!Sleep` at `0x14000133d`
- `KERNEL32!DebugBreak` at `0x14000134d`
- `KERNEL32!DebugBreak` at `0x14000134d`
- `ADVAPI32!RegQueryValueExW` at `0x1400012d4`
- `ADVAPI32!RegQueryValueExW` at `0x1400012d4`
- `ADVAPI32!RegCloseKey` at `0x14000135b`
- `ADVAPI32!RegCloseKey` at `0x14000135b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DiagHubCommon::DhTryDebugBreak *__fastcall DiagHubCommon::DhTryDebugBreak::DhTryDebugBreak(
        DiagHubCommon::DhTryDebugBreak *this,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned int a4)
{
  HKEY v5; // rcx
  HKEY v6; // rbx
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  HKEY hKey[3]; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD Type[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR OutputString[1024]; // [rsp+60h] [rbp-A0h] BYREF

  memset(hKey, 0, sizeof(hKey));
  if ( ATL::CRegKey::Open(
         (ATL::CRegKey *)hKey,
         (HKEY)a2,
         L"Software\\Microsoft\\VisualStudio\\DiagnosticsHub\\Debug",
         a4) )
  {
    v5 = hKey[0];
    if ( hKey[0] )
      goto LABEL_14;
  }
  else
  {
    v6 = hKey[0];
    cbData = 4;
    if ( !RegQueryValueExW(hKey[0], L"Merge", 0, Type, Data, &cbData) && Type[0] == 4 )
    {
      if ( *(_DWORD *)Data )
      {
        memset_0(OutputString, 0, sizeof(OutputString));
        LODWORD(lpData) = GetCurrentProcessId();
        _snwprintf_s<1024>(
          OutputString,
          0x3FFu,
          (wchar_t *)L"DiagnosticsHub - DebugBreak - %s - Attach to %d",
          L"Merge",
          lpData);
        if ( *(_DWORD *)Data == 2 )
        {
          while ( !IsDebuggerPresent() )
          {
            OutputDebugStringW(OutputString);
            Sleep(0x3E8u);
          }
          DebugBreak();
        }
      }
    }
    if ( v6 )
    {
      v5 = v6;
LABEL_14:
      RegCloseKey(v5);
    }
  }
  return this;
}

```

## disassembly

```asm
0x140001230  mov     [rsp-8+arg_0], rbx
0x140001235  mov     [rsp-8+arg_8], rdi
0x14000123a  push    rbp
0x14000123b  lea     rbp, [rsp-770h]
0x140001243  sub     rsp, 870h
0x14000124a  mov     rax, cs:__security_cookie
0x140001251  xor     rax, rsp
0x140001254  mov     [rbp+770h+var_10], rax
0x14000125b  mov     rdi, rcx
0x14000125e  mov     [rsp+870h+var_838], 0
0x140001267  lea     rcx, [rsp+870h+hKey]; this
0x14000126c  mov     [rsp+870h+hKey], 0
0x140001275  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\VisualStudio\\Diag"...
0x14000127c  mov     [rsp+870h+var_830], 0
0x140001285  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14000128a  test    eax, eax
0x14000128c  jz      short loc_1400012A1
0x14000128e  mov     rcx, [rsp+870h+hKey]
0x140001293  test    rcx, rcx
0x140001296  jz      loc_140001361
0x14000129c  jmp     loc_14000135B
0x1400012a1  mov     rbx, [rsp+870h+hKey]
0x1400012a6  lea     rax, [rsp+870h+cbData]
0x1400012ab  mov     [rsp+870h+lpcbData], rax; lpcbData
0x1400012b0  lea     r9, [rsp+870h+Type]; lpType
0x1400012b5  lea     rax, [rsp+870h+Data]
0x1400012ba  mov     [rsp+870h+cbData], 4
0x1400012c2  xor     r8d, r8d; lpReserved
0x1400012c5  mov     [rsp+870h+lpData], rax; lpData
0x1400012ca  lea     rdx, ValueName; "Merge"
0x1400012d1  mov     rcx, rbx; hKey
0x1400012d4  call    cs:__imp_RegQueryValueExW
0x1400012da  test    eax, eax
0x1400012dc  jnz     short loc_140001353
0x1400012de  cmp     [rsp+870h+Type], 4
0x1400012e3  jnz     short loc_140001353
0x1400012e5  cmp     dword ptr [rsp+870h+Data], eax
0x1400012e9  jz      short loc_140001353
0x1400012eb  xor     edx, edx; Val
0x1400012ed  lea     rcx, [rsp+870h+OutputString]; void *
0x1400012f2  mov     r8d, 800h; Size
0x1400012f8  call    memset_0
0x1400012fd  call    cs:__imp_GetCurrentProcessId
0x140001303  lea     r9, ValueName; "Merge"
0x14000130a  mov     edx, 3FFh; MaxCount
0x14000130f  lea     r8, aDiagnosticshub; "DiagnosticsHub - DebugBreak - %s - Atta"...
0x140001316  mov     dword ptr [rsp+870h+lpData], eax
0x14000131a  lea     rcx, [rsp+870h+OutputString]; Buffer
0x14000131f  call    ??$_snwprintf_s@$0EAA@@@YAHAEAY0EAA@G_KPEBGZZ; _snwprintf_s<1024>(ushort (&)[1024],unsigned __int64,ushort const *,...)
0x140001324  cmp     dword ptr [rsp+870h+Data], 2
0x140001329  jnz     short loc_140001353
0x14000132b  jmp     short loc_140001343
0x14000132d  lea     rcx, [rsp+870h+OutputString]; lpOutputString
0x140001332  call    cs:__imp_OutputDebugStringW
0x140001338  mov     ecx, 3E8h; dwMilliseconds
0x14000133d  call    cs:__imp_Sleep
0x140001343  call    cs:__imp_IsDebuggerPresent
0x140001349  test    eax, eax
0x14000134b  jz      short loc_14000132D
0x14000134d  call    cs:__imp_DebugBreak
0x140001353  test    rbx, rbx
0x140001356  jz      short loc_140001361
0x140001358  mov     rcx, rbx; hKey
0x14000135b  call    cs:__imp_RegCloseKey
0x140001361  mov     rax, rdi
0x140001364  mov     rcx, [rbp+770h+var_10]
0x14000136b  xor     rcx, rsp; StackCookie
0x14000136e  call    __security_check_cookie
0x140001373  lea     r11, [rsp+870h+var_s0]
0x14000137b  mov     rbx, [r11+10h]
0x14000137f  mov     rdi, [r11+18h]
0x140001383  mov     rsp, r11
0x140001386  pop     rbp
0x140001387  retn
```
