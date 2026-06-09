# F12::GetF12RegEntry(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18002fba8`
- end: `0x18002fd9b`
- name: `?GetF12RegEntry@F12@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `499`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004030`
- `0x1800241cc`

## callees

- `0x180003338`
- `0x180003858`
- `0x1800042a4`
- `0x1800045b4`
- `0x18002fba8`
- `0x180030314`
- `0x180035010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002fcf5`
- `ADVAPI32!RegCloseKey` at `0x18002fd63`
- `ADVAPI32!RegCloseKey` at `0x18002fcf5`
- `ADVAPI32!RegCloseKey` at `0x18002fd63`
- `ADVAPI32!RegOpenKeyExW` at `0x18002fc0c`
- `ADVAPI32!RegOpenKeyExW` at `0x18002fc0c`
- `ADVAPI32!RegQueryValueExW` at `0x18002fc45`
- `ADVAPI32!RegQueryValueExW` at `0x18002fc45`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LSTATUS __fastcall F12::GetF12RegEntry(LPCWSTR *a1, _QWORD *a2)
{
  LSTATUS result; // eax
  HKEY v5; // rbx
  unsigned int v6; // esi
  __int64 v7; // rax
  unsigned __int16 *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rax
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v13[3]; // [rsp+38h] [rbp-18h] BYREF
  DWORD Type; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int16 *cbData; // [rsp+98h] [rbp+48h] BYREF

  ATL::CSimpleStringT<unsigned short,0>::SetString(a2, &String, 0);
  memset(v13, 0, sizeof(v13));
  hKey = 0;
  result = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\F12", 0, 0x20019u, &hKey);
  if ( !result )
  {
    v5 = hKey;
    v13[0] = hKey;
    Type = 0;
    LODWORD(cbData) = 0;
    if ( RegQueryValueExW(hKey, *a1, 0, &Type, 0, (LPDWORD)&cbData) || Type - 1 > 1 )
    {
LABEL_23:
      if ( v5 )
        RegCloseKey(v5);
      return 0;
    }
    v6 = (unsigned int)cbData >> 1;
    Type = (unsigned int)cbData >> 1;
    v7 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
    v8 = (unsigned __int16 *)(v7 + 24);
    cbData = (unsigned __int16 *)(v7 + 24);
    if ( (((*(_DWORD *)(v7 + 12) - v6) | (1 - *(_DWORD *)(v7 + 16))) & 0x80000000) != 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&cbData);
      v8 = cbData;
    }
    v9 = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v13, *a1, v8, &Type);
    v10 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
      if ( hKey )
        RegCloseKey(hKey);
      return v10;
    }
    if ( v8 )
    {
      v11 = -1;
      do
        ++v11;
      while ( v8[v11] );
      if ( (int)v11 < 0 )
        goto LABEL_29;
    }
    else
    {
      LODWORD(v11) = 0;
    }
    if ( (int)v11 <= *((_DWORD *)v8 - 3) )
    {
      *((_DWORD *)v8 - 4) = v11;
      v8[(unsigned int)v11] = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        a2,
        &cbData);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
      v5 = hKey;
      goto LABEL_23;
    }
LABEL_29:
    ATL::AtlThrowImpl(-2147024809);
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002fba8  mov     [rsp-28h+arg_0], rbx
0x18002fbad  mov     [rsp-28h+arg_8], rsi
0x18002fbb2  push    rbp
0x18002fbb3  push    rdi
0x18002fbb4  push    r12
0x18002fbb6  push    r14
0x18002fbb8  push    r15
0x18002fbba  mov     rbp, rsp
0x18002fbbd  sub     rsp, 50h
0x18002fbc1  mov     r15, rdx
0x18002fbc4  mov     r14, rcx
0x18002fbc7  xor     r8d, r8d
0x18002fbca  lea     rdx, String
0x18002fbd1  mov     rcx, r15
0x18002fbd4  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002fbd9  xor     r12d, r12d
0x18002fbdc  mov     [rbp+var_18], r12
0x18002fbe0  mov     [rbp+var_10], r12
0x18002fbe4  mov     [rbp+var_8], r12
0x18002fbe8  mov     [rbp+hKey], r12
0x18002fbec  lea     rax, [rbp+hKey]
0x18002fbf0  mov     [rsp+50h+phkResult], rax; phkResult
0x18002fbf5  mov     r9d, 20019h; samDesired
0x18002fbfb  xor     r8d, r8d; ulOptions
0x18002fbfe  lea     rdx, SubKey; "Software\\Microsoft\\F12"
0x18002fc05  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002fc0c  call    cs:__imp_RegOpenKeyExW
0x18002fc12  test    eax, eax
0x18002fc14  jnz     loc_18002FD6D
0x18002fc1a  mov     rbx, [rbp+hKey]
0x18002fc1e  mov     [rbp+var_18], rbx
0x18002fc22  mov     [rbp+Type], r12d
0x18002fc26  mov     dword ptr [rbp+cbData], r12d
0x18002fc2a  lea     rax, [rbp+cbData]
0x18002fc2e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18002fc33  mov     [rsp+50h+phkResult], r12; lpData
0x18002fc38  lea     r9, [rbp+Type]; lpType
0x18002fc3c  xor     r8d, r8d; lpReserved
0x18002fc3f  mov     rdx, [r14]; lpValueName
0x18002fc42  mov     rcx, rbx; hKey
0x18002fc45  call    cs:__imp_RegQueryValueExW
0x18002fc4b  test    eax, eax
0x18002fc4d  jnz     loc_18002FD5B
0x18002fc53  mov     eax, [rbp+Type]
0x18002fc56  dec     eax
0x18002fc58  lea     edi, [r12+1]
0x18002fc5d  cmp     eax, edi
0x18002fc5f  ja      loc_18002FD5B
0x18002fc65  mov     esi, dword ptr [rbp+cbData]
0x18002fc68  shr     esi, 1
0x18002fc6a  mov     [rbp+Type], esi
0x18002fc6d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002fc74  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002fc7b  mov     rax, [rax+18h]
0x18002fc7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc84  lea     rbx, [rax+18h]
0x18002fc88  mov     [rbp+cbData], rbx
0x18002fc8c  sub     edi, [rbx-8]
0x18002fc8f  mov     eax, [rbx-0Ch]
0x18002fc92  sub     eax, esi
0x18002fc94  or      edi, eax
0x18002fc96  jge     short loc_18002FCA7
0x18002fc98  mov     edx, esi
0x18002fc9a  lea     rcx, [rbp+cbData]
0x18002fc9e  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002fca3  mov     rbx, [rbp+cbData]
0x18002fca7  lea     r9, [rbp+Type]; unsigned int *
0x18002fcab  mov     r8, rbx; unsigned __int16 *
0x18002fcae  mov     rdx, [r14]; unsigned __int16 *
0x18002fcb1  lea     rcx, [rbp+var_18]; this
0x18002fcb5  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18002fcba  mov     edi, eax
0x18002fcbc  test    eax, eax
0x18002fcbe  jz      short loc_18002FCFF
0x18002fcc0  jle     short loc_18002FCCB
0x18002fcc2  movzx   edi, ax
0x18002fcc5  or      edi, 80070000h
0x18002fccb  lea     rdx, [rbx-18h]
0x18002fccf  or      eax, 0FFFFFFFFh
0x18002fcd2  lock xadd [rdx+10h], eax
0x18002fcd7  sub     eax, 1
0x18002fcda  jg      short loc_18002FCEC
0x18002fcdc  mov     rcx, [rdx]
0x18002fcdf  mov     rax, [rcx]
0x18002fce2  mov     rax, [rax+8]
0x18002fce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fceb  nop
0x18002fcec  mov     rcx, [rbp+hKey]; hKey
0x18002fcf0  test    rcx, rcx
0x18002fcf3  jz      short loc_18002FCFB
0x18002fcf5  call    cs:__imp_RegCloseKey
0x18002fcfb  mov     eax, edi
0x18002fcfd  jmp     short loc_18002FD77
0x18002fcff  test    rbx, rbx
0x18002fd02  jnz     short loc_18002FD09
0x18002fd04  mov     eax, r12d
0x18002fd07  jmp     short loc_18002FD1B
0x18002fd09  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002fd0d  inc     rax
0x18002fd10  cmp     [rbx+rax*2], r12w
0x18002fd15  jnz     short loc_18002FD0D
0x18002fd17  test    eax, eax
0x18002fd19  js      short loc_18002FD90
0x18002fd1b  cmp     eax, [rbx-0Ch]
0x18002fd1e  jg      short loc_18002FD90
0x18002fd20  mov     [rbx-10h], eax
0x18002fd23  mov     ecx, eax
0x18002fd25  mov     [rbx+rcx*2], r12w
0x18002fd2a  lea     rdx, [rbp+cbData]
0x18002fd2e  mov     rcx, r15
0x18002fd31  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002fd36  nop
0x18002fd37  lea     rdx, [rbx-18h]
0x18002fd3b  or      eax, 0FFFFFFFFh
0x18002fd3e  lock xadd [rdx+10h], eax
0x18002fd43  sub     eax, 1
0x18002fd46  jg      short loc_18002FD57
0x18002fd48  mov     rcx, [rdx]
0x18002fd4b  mov     rax, [rcx]
0x18002fd4e  mov     rax, [rax+8]
0x18002fd52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd57  mov     rbx, [rbp+hKey]
0x18002fd5b  test    rbx, rbx
0x18002fd5e  jz      short loc_18002FD69
0x18002fd60  mov     rcx, rbx; hKey
0x18002fd63  call    cs:__imp_RegCloseKey
0x18002fd69  xor     eax, eax
0x18002fd6b  jmp     short loc_18002FD77
0x18002fd6d  jle     short loc_18002FD77
0x18002fd6f  movzx   eax, ax
0x18002fd72  or      eax, 80070000h
0x18002fd77  lea     r11, [rsp+50h+var_s0]
0x18002fd7c  mov     rbx, [r11+30h]
0x18002fd80  mov     rsi, [r11+38h]
0x18002fd84  mov     rsp, r11
0x18002fd87  pop     r15
0x18002fd89  pop     r14
0x18002fd8b  pop     r12
0x18002fd8d  pop     rdi
0x18002fd8e  pop     rbp
0x18002fd8f  retn
0x18002fd90  mov     ecx, 80070057h; int
0x18002fd95  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
