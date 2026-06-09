# GetRepositoryDirectory(ushort * const)

- ea: `0x180007bc4`
- end: `0x180007e57`
- name: `?GetRepositoryDirectory@@YAJQEAG@Z`
- size: `659`
- prototype: `__int64 __fastcall(LPWSTR lpDst)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007a20`
- `0x180013ddc`
- `0x1800148e4`
- `0x1800149e8`

## callees

- `0x180007bc4`
- `0x180012c34`
- `0x18001d3a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007c14`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007c14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007e34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007e34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007cbb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007cbb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007d70`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007d70`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180007c2e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180007cd5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180007d27`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180007d8a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180007de0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180007c2e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180007cd5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180007d27`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180007d8a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180007de0`
- `wbemcomn!GetMemLogObject` at `0x180007c1e`
- `wbemcomn!GetMemLogObject` at `0x180007cc5`
- `wbemcomn!GetMemLogObject` at `0x180007d17`
- `wbemcomn!GetMemLogObject` at `0x180007d7a`
- `wbemcomn!GetMemLogObject` at `0x180007dd0`
- `wbemcomn!GetMemLogObject` at `0x180007c1e`
- `wbemcomn!GetMemLogObject` at `0x180007cc5`
- `wbemcomn!GetMemLogObject` at `0x180007d17`
- `wbemcomn!GetMemLogObject` at `0x180007d7a`
- `wbemcomn!GetMemLogObject` at `0x180007dd0`

## string_xrefs

- `0x180007caf`: `Repository Directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetRepositoryDirectory(LPWSTR lpDst)
{
  CMemoryLog *v2; // rax
  unsigned int v3; // edi
  HKEY v4; // rbx
  CMemoryLog *MemLogObject; // rax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  CMemoryLog *v8; // rax
  CMemoryLog *v9; // rax
  __int64 v10; // rax
  CMemoryLog *v11; // rax
  __int64 v12; // rax
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey[3]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Data[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey[0] = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WBEM\\CIMOM", 0, 0x20019u, hKey) )
  {
    v4 = hKey[0];
    hKey[1] = hKey[0];
    Type = 0;
    cbData = 522;
    if ( RegQueryValueExW(hKey[0], L"Repository Directory", 0, &Type, (LPBYTE)Data, &cbData) )
    {
      MemLogObject = GetMemLogObject();
      v3 = -2147217407;
      CMemoryLog::Write(MemLogObject, -2147217407);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_32;
      }
      v7 = 41;
    }
    else if ( Type == 2 )
    {
      if ( ExpandEnvironmentStringsW(Data, lpDst, 0x105u) )
      {
        v10 = -1;
        do
          ++v10;
        while ( lpDst[v10] );
        if ( (unsigned int)v10 >= 2 )
        {
          v12 = (unsigned int)(v10 - 1);
          if ( lpDst[v12] == 92 )
            lpDst[v12] = 0;
          v3 = 0;
          goto LABEL_32;
        }
        v11 = GetMemLogObject();
        v3 = -2147217407;
        CMemoryLog::Write(v11, -2147217407);
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_32:
          RegCloseKey(v4);
          return v3;
        }
        v7 = 44;
      }
      else
      {
        v9 = GetMemLogObject();
        v3 = -2147217407;
        CMemoryLog::Write(v9, -2147217407);
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_32;
        }
        v7 = 43;
      }
    }
    else
    {
      v8 = GetMemLogObject();
      v3 = -2147217407;
      CMemoryLog::Write(v8, -2147217407);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_32;
      }
      v7 = 42;
    }
    WPP_SF_d(v6[2], v7, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids, 2147749889LL);
    goto LABEL_32;
  }
  v2 = GetMemLogObject();
  v3 = -2147217407;
  CMemoryLog::Write(v2, -2147217407);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids, 2147749889LL);
  }
  return v3;
}

```

## disassembly

```asm
0x180007bc4  push    rbp
0x180007bc6  push    rbx
0x180007bc7  push    rsi
0x180007bc8  push    rdi
0x180007bc9  lea     rbp, [rsp-178h]
0x180007bd1  sub     rsp, 278h
0x180007bd8  mov     rax, cs:__security_cookie
0x180007bdf  xor     rax, rsp
0x180007be2  mov     [rbp+190h+var_30], rax
0x180007be9  mov     rdi, rcx
0x180007bec  xor     esi, esi
0x180007bee  mov     [rsp+290h+hKey], rsi
0x180007bf3  lea     rax, [rsp+290h+hKey]
0x180007bf8  mov     [rsp+290h+phkResult], rax; phkResult
0x180007bfd  mov     r9d, 20019h; samDesired
0x180007c03  xor     r8d, r8d; ulOptions
0x180007c06  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WBEM\\CIMOM"
0x180007c0d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007c14  call    cs:__imp_RegOpenKeyExW
0x180007c1a  test    eax, eax
0x180007c1c  jz      short loc_180007C7D
0x180007c1e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180007c24  mov     edi, 80041001h
0x180007c29  mov     edx, edi
0x180007c2b  mov     rcx, rax
0x180007c2e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180007c34  lea     rax, WPP_GLOBAL_Control
0x180007c3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c42  cmp     rcx, rax
0x180007c45  jz      loc_180007E3A
0x180007c4b  test    byte ptr [rcx+1Ch], 1
0x180007c4f  jz      loc_180007E3A
0x180007c55  cmp     byte ptr [rcx+19h], 2
0x180007c59  jb      loc_180007E3A
0x180007c5f  lea     edx, [rsi+28h]
0x180007c62  mov     r9d, 80041001h
0x180007c68  lea     r8, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids
0x180007c6f  mov     rcx, [rcx+10h]
0x180007c73  call    WPP_SF_d
0x180007c78  jmp     loc_180007E3A
0x180007c7d  mov     rbx, [rsp+290h+hKey]
0x180007c82  mov     [rsp+290h+var_250], rbx
0x180007c87  mov     [rsp+290h+Type], esi
0x180007c8b  mov     [rsp+290h+cbData], 20Ah
0x180007c93  lea     rax, [rsp+290h+cbData]
0x180007c98  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180007c9d  lea     rax, [rsp+290h+Data]
0x180007ca2  mov     [rsp+290h+phkResult], rax; lpData
0x180007ca7  lea     r9, [rsp+290h+Type]; lpType
0x180007cac  xor     r8d, r8d; lpReserved
0x180007caf  lea     rdx, aRepositoryDire; "Repository Directory"
0x180007cb6  mov     rcx, [rsp+290h+hKey]; hKey
0x180007cbb  call    cs:__imp_RegQueryValueExW
0x180007cc1  test    eax, eax
0x180007cc3  jz      short loc_180007D10
0x180007cc5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180007ccb  mov     edi, 80041001h
0x180007cd0  mov     edx, edi
0x180007cd2  mov     rcx, rax
0x180007cd5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180007cdb  lea     rax, WPP_GLOBAL_Control
0x180007ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ce9  cmp     rcx, rax
0x180007cec  jz      loc_180007E31
0x180007cf2  test    byte ptr [rcx+1Ch], 1
0x180007cf6  jz      loc_180007E31
0x180007cfc  cmp     byte ptr [rcx+19h], 2
0x180007d00  jb      loc_180007E31
0x180007d06  mov     edx, 29h ; ')'
0x180007d0b  jmp     loc_180007E0A
0x180007d10  cmp     [rsp+290h+Type], 2
0x180007d15  jz      short loc_180007D62
0x180007d17  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180007d1d  mov     edi, 80041001h
0x180007d22  mov     edx, edi
0x180007d24  mov     rcx, rax
0x180007d27  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180007d2d  lea     rax, WPP_GLOBAL_Control
0x180007d34  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d3b  cmp     rcx, rax
0x180007d3e  jz      loc_180007E31
0x180007d44  test    byte ptr [rcx+1Ch], 1
0x180007d48  jz      loc_180007E31
0x180007d4e  cmp     byte ptr [rcx+19h], 2
0x180007d52  jb      loc_180007E31
0x180007d58  mov     edx, 2Ah ; '*'
0x180007d5d  jmp     loc_180007E0A
0x180007d62  mov     r8d, 105h; nSize
0x180007d68  mov     rdx, rdi; lpDst
0x180007d6b  lea     rcx, [rsp+290h+Data]; lpSrc
0x180007d70  call    cs:__imp_ExpandEnvironmentStringsW
0x180007d76  test    eax, eax
0x180007d78  jnz     short loc_180007DBE
0x180007d7a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180007d80  mov     edi, 80041001h
0x180007d85  mov     edx, edi
0x180007d87  mov     rcx, rax
0x180007d8a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180007d90  lea     rax, WPP_GLOBAL_Control
0x180007d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d9e  cmp     rcx, rax
0x180007da1  jz      loc_180007E31
0x180007da7  test    byte ptr [rcx+1Ch], 1
0x180007dab  jz      loc_180007E31
0x180007db1  cmp     byte ptr [rcx+19h], 2
0x180007db5  jb      short loc_180007E31
0x180007db7  mov     edx, 2Bh ; '+'
0x180007dbc  jmp     short loc_180007E0A
0x180007dbe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007dc2  inc     rax
0x180007dc5  cmp     [rdi+rax*2], si
0x180007dc9  jnz     short loc_180007DC2
0x180007dcb  cmp     eax, 2
0x180007dce  jnb     short loc_180007E22
0x180007dd0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180007dd6  mov     edi, 80041001h
0x180007ddb  mov     edx, edi
0x180007ddd  mov     rcx, rax
0x180007de0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180007de6  lea     rax, WPP_GLOBAL_Control
0x180007ded  mov     rcx, cs:WPP_GLOBAL_Control
0x180007df4  cmp     rcx, rax
0x180007df7  jz      short loc_180007E31
0x180007df9  test    byte ptr [rcx+1Ch], 1
0x180007dfd  jz      short loc_180007E31
0x180007dff  cmp     byte ptr [rcx+19h], 2
0x180007e03  jb      short loc_180007E31
0x180007e05  mov     edx, 2Ch ; ','
0x180007e0a  mov     r9d, 80041001h
0x180007e10  lea     r8, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids
0x180007e17  mov     rcx, [rcx+10h]
0x180007e1b  call    WPP_SF_d
0x180007e20  jmp     short loc_180007E31
0x180007e22  dec     eax
0x180007e24  cmp     word ptr [rdi+rax*2], 5Ch ; '\'
0x180007e29  jnz     short loc_180007E2F
0x180007e2b  mov     [rdi+rax*2], si
0x180007e2f  mov     edi, esi
0x180007e31  mov     rcx, rbx; hKey
0x180007e34  call    cs:__imp_RegCloseKey
0x180007e3a  mov     eax, edi
0x180007e3c  mov     rcx, [rbp+190h+var_30]
0x180007e43  xor     rcx, rsp; StackCookie
0x180007e46  call    __security_check_cookie
0x180007e4b  add     rsp, 278h
0x180007e52  pop     rdi
0x180007e53  pop     rsi
0x180007e54  pop     rbx
0x180007e55  pop     rbp
0x180007e56  retn
```
