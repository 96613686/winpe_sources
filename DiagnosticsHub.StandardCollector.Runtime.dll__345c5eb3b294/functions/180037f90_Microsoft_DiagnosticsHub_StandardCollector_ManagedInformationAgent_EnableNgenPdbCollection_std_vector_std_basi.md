# Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::EnableNgenPdbCollection(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>)

- ea: `0x180037f90`
- end: `0x1800380ea`
- name: `?EnableNgenPdbCollection@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@QEAAXV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d2d0`

## callees

- `0x18001662c`
- `0x1800196c0`
- `0x180037f90`
- `0x180039970`
- `0x18003d864`
- `0x180049b50`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800380a1`
- `KERNEL32!LeaveCriticalSection` at `0x1800380a1`
- `KERNEL32!EnterCriticalSection` at `0x180038075`
- `KERNEL32!EnterCriticalSection` at `0x180038075`
- `ADVAPI32!RegCloseKey` at `0x1800380bc`
- `ADVAPI32!RegCloseKey` at `0x1800380bc`
- `ADVAPI32!RegQueryValueExW` at `0x180038016`
- `ADVAPI32!RegQueryValueExW` at `0x180038016`

## string_xrefs

- `0x180038048`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\ManagedInformationAgent.cpp`
- `0x180038041`: `Ngen PDB collection was disabled by the regkey ForceDisableNGENPdbCollection, disabling pdb collection despite this collection session being configured for it.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::EnableNgenPdbCollection(
        __int64 a1,
        HKEY a2)
{
  _QWORD *v2; // rsi
  int v4; // eax
  HKEY v5; // r14
  HKEY hKey[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v8; // [rsp+40h] [rbp-48h]
  HKEY v9; // [rsp+48h] [rbp-40h]
  DWORD cbData; // [rsp+50h] [rbp-38h] BYREF
  DWORD Type; // [rsp+54h] [rbp-34h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-30h] BYREF

  v2 = a2;
  v9 = a2;
  *(_OWORD *)hKey = 0;
  hKey[0] = 0;
  LODWORD(hKey[1]) = 0;
  v8 = 0;
  v4 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, a2, L"Software\\Microsoft\\VisualStudio\\DiagnosticsHub");
  v5 = hKey[0];
  if ( v4
    || (cbData = 4, RegQueryValueExW(hKey[0], L"ForceDisableNGENPdbCollection", 0, &Type, Data, &cbData))
    || Type != 4
    || *(_DWORD *)Data != 1 )
  {
    *(_BYTE *)(a1 + 114) = 1;
    *(_BYTE *)(a1 + 116) = 1;
    if ( *v2 != v2[1] )
    {
      *(_QWORD *)Data = a1 + 24;
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
      try
      {
        std::vector<std::wstring>::_Insert_counted_range<std::wstring *>(
          a1 + 320,
          *(_QWORD *)(a1 + 328),
          *v2,
          (__int64)(v2[1] - *v2) >> 5);
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
      }
      catch ( std::bad_alloc )
      {
        v5 = hKey[0];
        v2 = v9;
      }
    }
  }
  else
  {
    *(_BYTE *)(a1 + 114) = 0;
    *(_BYTE *)(a1 + 116) = 0;
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 112),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\ManagedInformationAgent.cpp",
      L"Ngen PDB collection was disabled by the regkey ForceDisableNGENPdbCollection, disabling pdb collection despite thi"
       "s collection session being configured for it.");
  }
  if ( v5 )
    RegCloseKey(v5);
  return std::vector<std::wstring>::~vector<std::wstring>(v2);
}

```

## disassembly

```asm
0x180037f90  mov     r11, rsp
0x180037f93  mov     [r11+18h], rbx
0x180037f97  push    rsi
0x180037f98  push    r14
0x180037f9a  push    r15
0x180037f9c  sub     rsp, 70h
0x180037fa0  mov     rax, cs:__security_cookie
0x180037fa7  xor     rax, rsp
0x180037faa  mov     [rsp+88h+var_28], rax
0x180037faf  mov     rsi, rdx
0x180037fb2  mov     r15, rcx
0x180037fb5  mov     [r11-40h], rdx
0x180037fb9  xorps   xmm0, xmm0
0x180037fbc  xor     eax, eax
0x180037fbe  movups  xmmword ptr [rsp+88h+hKey], xmm0
0x180037fc3  mov     [r11-58h], rax
0x180037fc7  mov     dword ptr [rsp+88h+hKey+8], eax
0x180037fcb  mov     [r11-48h], rax
0x180037fcf  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\VisualStudio\\Diag"...
0x180037fd6  lea     rcx, [r11-58h]; this
0x180037fda  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180037fdf  mov     r14, [rsp+88h+hKey]
0x180037fe4  test    eax, eax
0x180037fe6  jnz     short loc_180038056
0x180037fe8  mov     [rsp+88h+cbData], 4
0x180037ff0  lea     rax, [rsp+88h+cbData]
0x180037ff5  mov     [rsp+88h+lpcbData], rax; lpcbData
0x180037ffa  lea     rax, [rsp+88h+Data]
0x180037fff  mov     [rsp+88h+lpData], rax; lpData
0x180038004  lea     r9, [rsp+88h+Type]; lpType
0x180038009  xor     r8d, r8d; lpReserved
0x18003800c  lea     rdx, aForcedisableng; "ForceDisableNGENPdbCollection"
0x180038013  mov     rcx, r14; hKey
0x180038016  call    cs:__imp_RegQueryValueExW
0x18003801c  test    eax, eax
0x18003801e  jnz     short loc_180038056
0x180038020  cmp     [rsp+88h+Type], 4
0x180038025  jnz     short loc_180038056
0x180038027  cmp     dword ptr [rsp+88h+Data], 1
0x18003802c  jnz     short loc_180038056
0x18003802e  mov     [r15+72h], al
0x180038032  mov     [r15+74h], al
0x180038036  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003803d  add     rcx, 70h ; 'p'; this
0x180038041  lea     r8, aNgenPdbCollect; "Ngen PDB collection was disabled by the"...
0x180038048  lea     rdx, aDAWork1SSource_1; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003804f  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180038054  jmp     short loc_1800380B4
0x180038056  mov     byte ptr [r15+72h], 1
0x18003805b  mov     byte ptr [r15+74h], 1
0x180038060  mov     rax, [rsi+8]
0x180038064  cmp     [rsi], rax
0x180038067  jz      short loc_1800380B4
0x180038069  lea     rbx, [r15+18h]
0x18003806d  mov     qword ptr [rsp+88h+Data], rbx
0x180038072  mov     rcx, rbx; lpCriticalSection
0x180038075  call    cs:__imp_EnterCriticalSection
0x18003807b  nop
0x18003807c  mov     r9, [rsi+8]
0x180038080  sub     r9, [rsi]
0x180038083  sar     r9, 5
0x180038087  mov     rdx, [r15+148h]
0x18003808e  lea     rcx, [r15+140h]
0x180038095  mov     r8, [rsi]
0x180038098  call    ??$_Insert_counted_range@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::vector<std::wstring>::_Insert_counted_range<std::wstring *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring *,unsigned __int64)
0x18003809d  nop
0x18003809e  mov     rcx, rbx; lpCriticalSection
0x1800380a1  call    cs:__imp_LeaveCriticalSection
0x1800380a7  nop
0x1800380a8  jmp     short loc_1800380B4
0x1800380aa  mov     r14, [rsp+88h+hKey]
0x1800380af  mov     rsi, [rsp+88h+var_40]
0x1800380b4  test    r14, r14
0x1800380b7  jz      short loc_1800380C3
0x1800380b9  mov     rcx, r14; hKey
0x1800380bc  call    cs:__imp_RegCloseKey
0x1800380c2  nop
0x1800380c3  mov     rcx, rsi
0x1800380c6  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x1800380cb  mov     rcx, [rsp+88h+var_28]
0x1800380d0  xor     rcx, rsp; StackCookie
0x1800380d3  call    __security_check_cookie
0x1800380d8  mov     rbx, [rsp+88h+arg_10]
0x1800380e0  add     rsp, 70h
0x1800380e4  pop     r15
0x1800380e6  pop     r14
0x1800380e8  pop     rsi
0x1800380e9  retn
```
