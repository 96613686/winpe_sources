# OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::GetMsiExecPath(void)

- ea: `0x140009310`
- end: `0x140009442`
- name: `?GetMsiExecPath@CustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@KAPEBGXZ`
- size: `306`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140008ec8`

## callees

- `0x140007d78`
- `0x14000859c`
- `0x140008610`
- `0x140009310`
- `0x14000e4d0`
- `0x14000e780`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140009355`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140009390`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140009355`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140009390`

## string_xrefs

- `0x1400093e9`: `msiexec.exe`
- `0x14000936c`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x1400093aa`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x1400093d7`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009404`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`

## pseudocode

```c
const unsigned __int16 *OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::GetMsiExecPath(void)
{
  UINT SystemDirectoryW; // eax
  UINT v1; // ebx
  UINT v2; // eax
  int appended; // eax
  int v4; // eax
  LPWSTR lpBuffer[2]; // [rsp+20h] [rbp-30h] BYREF
  int v7; // [rsp+30h] [rbp-20h]
  _QWORD v8[3]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  if ( !OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::s_msiExecPath )
  {
    *(_OWORD *)lpBuffer = 0;
    v7 = 0;
    v8[1] = lpBuffer;
    v8[0] = &Common::StringBufferBuilder::`vftable';
    v8[2] = lpBuffer;
    SystemDirectoryW = GetSystemDirectoryW(0, 0);
    v1 = SystemDirectoryW;
    if ( SystemDirectoryW <= 1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)0x8000FFFFLL,
        (int)lpBuffer[0]);
    Common::StringBuffer::SetLength((Common::StringBuffer *)lpBuffer, SystemDirectoryW - 1);
    v2 = GetSystemDirectoryW(lpBuffer[1], v1);
    if ( LODWORD(lpBuffer[0]) != v2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)0x8000FFFFLL,
        (int)lpBuffer[0]);
    appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v8, L"\\");
    if ( appended < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)appended,
        (int)lpBuffer[0]);
    v4 = Common::StringBuilder::AppendString((Common::StringBuilder *)v8, L"msiexec.exe");
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v4,
        (int)lpBuffer[0]);
    Common::StringBuffer::operator=(
      &OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::s_msiExecPath,
      lpBuffer);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpBuffer);
  }
  return (const unsigned __int16 *)qword_1400169C0;
}

```

## disassembly

```asm
0x140009310  mov     [rsp-8+arg_0], rbx
0x140009315  push    rbp
0x140009316  mov     rbp, rsp
0x140009319  sub     rsp, 50h
0x14000931d  cmp     cs:?s_msiExecPath@CustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@1VStringBuffer@Common@@A, 0; Common::StringBuffer OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::s_msiExecPath
0x140009324  jnz     loc_140009430
0x14000932a  xor     eax, eax
0x14000932c  xorps   xmm0, xmm0
0x14000932f  movups  xmmword ptr [rbp+lpBuffer], xmm0
0x140009333  mov     [rbp+var_20], eax
0x140009336  lea     rax, [rbp+lpBuffer]
0x14000933a  mov     [rbp+var_10], rax
0x14000933e  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x140009345  mov     [rbp+var_18], rax
0x140009349  lea     rax, [rbp+lpBuffer]
0x14000934d  mov     [rbp+var_8], rax
0x140009351  xor     edx, edx; uSize
0x140009353  xor     ecx, ecx; lpBuffer
0x140009355  call    cs:__imp_GetSystemDirectoryW
0x14000935b  mov     ebx, eax
0x14000935d  mov     rcx, [rbp+8]; this
0x140009361  cmp     eax, 1
0x140009364  ja      short loc_14000937E
0x140009366  mov     r9d, 8000FFFFh; char *
0x14000936c  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009373  mov     edx, 85h; void *
0x140009378  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000937e  lea     edx, [rax-1]; unsigned int
0x140009381  lea     rcx, [rbp+lpBuffer]; this
0x140009385  call    ?SetLength@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetLength(ulong)
0x14000938a  mov     edx, ebx; uSize
0x14000938c  mov     rcx, [rbp+lpBuffer+8]; lpBuffer
0x140009390  call    cs:__imp_GetSystemDirectoryW
0x140009396  cmp     dword ptr [rbp+lpBuffer], eax
0x140009399  setnz   al
0x14000939c  mov     rcx, [rbp+8]; this
0x1400093a0  test    al, al
0x1400093a2  jz      short loc_1400093BC
0x1400093a4  mov     r9d, 8000FFFFh; char *
0x1400093aa  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1400093b1  mov     edx, 89h; void *
0x1400093b6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400093bc  lea     rdx, asc_140010DA0; "\\"
0x1400093c3  lea     rcx, [rbp+var_18]; this
0x1400093c7  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1400093cc  mov     rcx, [rbp+8]; this
0x1400093d0  test    eax, eax
0x1400093d2  jns     short loc_1400093E9
0x1400093d4  mov     r9d, eax; char *
0x1400093d7  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1400093de  mov     edx, 8Bh; void *
0x1400093e3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400093e9  lea     rdx, aMsiexecExe; "msiexec.exe"
0x1400093f0  lea     rcx, [rbp+var_18]; this
0x1400093f4  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1400093f9  mov     rcx, [rbp+8]; this
0x1400093fd  test    eax, eax
0x1400093ff  jns     short loc_140009416
0x140009401  mov     r9d, eax; char *
0x140009404  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000940b  mov     edx, 8Ch; void *
0x140009410  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009416  lea     rdx, [rbp+lpBuffer]
0x14000941a  lea     rcx, ?s_msiExecPath@CustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@1VStringBuffer@Common@@A; Common::StringBuffer OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::s_msiExecPath
0x140009421  call    ??4StringBuffer@Common@@QEAAAEAV01@$$QEAV01@@Z; Common::StringBuffer::operator=(Common::StringBuffer &&)
0x140009426  nop
0x140009427  lea     rcx, [rbp+lpBuffer]; this
0x14000942b  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x140009430  mov     rax, cs:qword_1400169C0
0x140009437  mov     rbx, [rsp+50h+arg_0]
0x14000943c  add     rsp, 50h
0x140009440  pop     rbp
0x140009441  retn
```
