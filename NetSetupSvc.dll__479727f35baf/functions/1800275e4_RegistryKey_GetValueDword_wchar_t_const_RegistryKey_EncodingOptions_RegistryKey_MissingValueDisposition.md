# RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)

- ea: `0x1800275e4`
- end: `0x180027893`
- name: `?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z`
- size: `687`
- prototype: `__int64 __fastcall(HKEY *, const WCHAR *, int, unsigned int)`
- caller_count: `14`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180009cfc`
- `0x18000a4d0`
- `0x18000a570`
- `0x18000c5e0`
- `0x18001d9c0`
- `0x18001eb14`
- `0x18001f2e4`
- `0x18001f984`
- `0x18001fe58`
- `0x1800209dc`
- `0x180021650`
- `0x180023718`
- `0x180027560`
- `0x1800275e4`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180008854`
- `0x180008c78`
- `0x18000d954`
- `0x18000d9b4`
- `0x18000df60`
- `0x18002498c`
- `0x1800275e4`
- `0x180027d2c`
- `0x180028804`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x180027706`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x180027706`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027644`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800277b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027644`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800277b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RegistryKey::GetValueDword(HKEY *a1, const WCHAR *a2, int a3, unsigned int a4)
{
  LSTATUS v7; // edi
  const wchar_t *v9; // rax
  unsigned __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // r10
  LSTATUS v13; // edi
  _BYTE pExceptionObject[208]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+100h] [rbp+0h] BYREF
  DWORD v16; // [rsp+104h] [rbp+4h] BYREF
  BYTE Data[4]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v18[32]; // [rsp+110h] [rbp+10h] BYREF

  if ( !a3 )
  {
    *(_DWORD *)Data = 0;
    Type = 4;
    v16 = 0;
    v13 = RegQueryValueExW(*a1, a2, 0, &v16, Data, &Type);
    if ( v13 == 2 )
    {
      if ( a4 == 1 )
        return 0;
    }
    else if ( !v13 )
    {
      if ( v16 != 4 || Type != 4 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_SDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, Type, (_DWORD)a2, v16, Type);
        HResultException::HResultException((HResultException *)pExceptionObject, -2147023267);
        throw (HResultException *)pExceptionObject;
      }
      return *(unsigned int *)Data;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)WPP_419802ccba213757c01acb0d7aa84d96_Traceguids,
        (_DWORD)a2,
        v13);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v13);
    throw (Win32Exception *)pExceptionObject;
  }
  if ( a3 != 1 )
    return 0;
  Type = 0;
  v7 = RegQueryValueExW(*a1, a2, 0, &Type, 0, 0);
  if ( v7 == 2 )
  {
    if ( a4 != 1 )
    {
LABEL_7:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          (unsigned int)WPP_419802ccba213757c01acb0d7aa84d96_Traceguids,
          (_DWORD)a2,
          v7);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v7);
      throw (Win32Exception *)pExceptionObject;
    }
    return 0;
  }
  if ( v7 )
    goto LABEL_7;
  if ( Type == 4 )
    return RegistryKey::GetValueDword(a1, a2, 0, a4);
  RegistryKey::GetValueString(a1, v18, a2, 0);
  v9 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v10 = _wcstoi64(v9, 0, 10);
  if ( v10 > 0xFFFFFFFF )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      WPP_SF_S(*(_QWORD *)(v12 + 16), 26, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids, v11);
    }
    HResultException::HResultException((HResultException *)pExceptionObject, -2147483637);
    throw (HResultException *)pExceptionObject;
  }
  std::wstring::_Tidy_deallocate((__int64)v18);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800275e4  push    rbp
0x1800275e6  push    rbx
0x1800275e7  push    rsi
0x1800275e8  push    rdi
0x1800275e9  push    r14
0x1800275eb  lea     rbp, [rsp-40h]
0x1800275f0  sub     rsp, 140h
0x1800275f7  mov     rax, cs:__security_cookie
0x1800275fe  xor     rax, rsp
0x180027601  mov     [rbp+60h+var_30], rax
0x180027605  mov     esi, r9d
0x180027608  mov     rbx, rdx
0x18002760b  mov     r14, rcx
0x18002760e  test    r8d, r8d
0x180027611  jz      loc_180027782
0x180027617  cmp     r8d, 1
0x18002761b  jnz     loc_1800277C5
0x180027621  mov     [rbp+60h+Type], 0
0x180027628  mov     [rsp+160h+lpcbData], 0; lpcbData
0x180027631  mov     [rsp+160h+lpData], 0; lpData
0x18002763a  lea     r9, [rbp+60h+Type]; lpType
0x18002763e  xor     r8d, r8d; lpReserved
0x180027641  mov     rcx, [rcx]; hKey
0x180027644  call    cs:__imp_RegQueryValueExW
0x18002764a  mov     edi, eax
0x18002764c  cmp     eax, 2
0x18002764f  jnz     short loc_18002765C
0x180027651  cmp     esi, 1
0x180027654  jz      loc_1800277C5
0x18002765a  jmp     short loc_180027660
0x18002765c  test    edi, edi
0x18002765e  jz      short loc_1800276B3
0x180027660  lea     rax, WPP_GLOBAL_Control
0x180027667  mov     rcx, cs:WPP_GLOBAL_Control
0x18002766e  cmp     rcx, rax
0x180027671  jz      short loc_180027695
0x180027673  cmp     byte ptr [rcx+19h], 2
0x180027677  jb      short loc_180027695
0x180027679  mov     edx, 19h
0x18002767e  mov     dword ptr [rsp+160h+lpData], edi
0x180027682  mov     r9, rbx
0x180027685  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x18002768c  mov     rcx, [rcx+10h]
0x180027690  call    WPP_SF_Sd
0x180027695  mov     edx, edi; int
0x180027697  lea     rcx, [rsp+160h+pExceptionObject]; this
0x18002769c  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x1800276a1  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x1800276a8  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x1800276ad  call    _CxxThrowException_0
0x1800276b3  mov     rcx, r14
0x1800276b6  cmp     [rbp+60h+Type], 4
0x1800276ba  jnz     short loc_1800276E4
0x1800276bc  mov     r9d, esi
0x1800276bf  xor     r8d, r8d
0x1800276c2  mov     rdx, rbx
0x1800276c5  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x1800276ca  mov     rcx, [rbp+60h+var_30]
0x1800276ce  xor     rcx, rsp; StackCookie
0x1800276d1  call    __security_check_cookie
0x1800276d6  add     rsp, 140h
0x1800276dd  pop     r14
0x1800276df  pop     rdi
0x1800276e0  pop     rsi
0x1800276e1  pop     rbx
0x1800276e2  pop     rbp
0x1800276e3  retn
0x1800276e4  xor     r9d, r9d
0x1800276e7  mov     r8, rbx
0x1800276ea  lea     rdx, [rbp+60h+var_50]
0x1800276ee  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x1800276f3  nop
0x1800276f4  lea     rcx, [rbp+60h+var_50]
0x1800276f8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800276fd  mov     rcx, rax; String
0x180027700  xor     edx, edx; EndPtr
0x180027702  lea     r8d, [rdx+0Ah]; Radix
0x180027706  call    cs:__imp__wcstoi64
0x18002770c  mov     rbx, rax
0x18002770f  mov     eax, 0FFFFFFFFh
0x180027714  cmp     rbx, rax
0x180027717  ja      short loc_180027726
0x180027719  lea     rcx, [rbp+60h+var_50]
0x18002771d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027722  mov     eax, ebx
0x180027724  jmp     short loc_1800276CA
0x180027726  lea     rax, WPP_GLOBAL_Control
0x18002772d  mov     r10, cs:WPP_GLOBAL_Control
0x180027734  cmp     r10, rax
0x180027737  jz      short loc_180027761
0x180027739  cmp     byte ptr [r10+19h], 2
0x18002773e  jb      short loc_180027761
0x180027740  lea     rcx, [rbp+60h+var_50]
0x180027744  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180027749  mov     r9, rax
0x18002774c  mov     edx, 1Ah
0x180027751  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x180027758  mov     rcx, [r10+10h]
0x18002775c  call    WPP_SF_S
0x180027761  mov     edx, 8000000Bh; int
0x180027766  lea     rcx, [rsp+160h+pExceptionObject]; this
0x18002776b  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180027770  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180027777  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18002777c  call    _CxxThrowException_0
0x180027782  mov     dword ptr [rbp+60h+Data], 0
0x180027789  mov     [rbp+60h+Type], 4
0x180027790  mov     [rbp+60h+var_5C], 0
0x180027797  lea     rax, [rbp+60h+Type]
0x18002779b  mov     [rsp+160h+lpcbData], rax; lpcbData
0x1800277a0  lea     rax, [rbp+60h+Data]
0x1800277a4  mov     [rsp+160h+lpData], rax; lpData
0x1800277a9  lea     r9, [rbp+60h+var_5C]; lpType
0x1800277ad  xor     r8d, r8d; lpReserved
0x1800277b0  mov     rcx, [rcx]; hKey
0x1800277b3  call    cs:__imp_RegQueryValueExW
0x1800277b9  mov     edi, eax
0x1800277bb  cmp     eax, 2
0x1800277be  jnz     short loc_1800277CC
0x1800277c0  cmp     esi, 1
0x1800277c3  jnz     short loc_1800277D0
0x1800277c5  xor     eax, eax
0x1800277c7  jmp     loc_1800276CA
0x1800277cc  test    edi, edi
0x1800277ce  jz      short loc_180027823
0x1800277d0  lea     rax, WPP_GLOBAL_Control
0x1800277d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800277de  cmp     rcx, rax
0x1800277e1  jz      short loc_180027805
0x1800277e3  cmp     byte ptr [rcx+19h], 2
0x1800277e7  jb      short loc_180027805
0x1800277e9  mov     edx, 17h
0x1800277ee  mov     dword ptr [rsp+160h+lpData], edi
0x1800277f2  mov     r9, rbx
0x1800277f5  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x1800277fc  mov     rcx, [rcx+10h]
0x180027800  call    WPP_SF_Sd
0x180027805  mov     edx, edi; int
0x180027807  lea     rcx, [rsp+160h+pExceptionObject]; this
0x18002780c  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180027811  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180027818  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18002781d  call    _CxxThrowException_0
0x180027823  mov     r8d, [rbp+60h+Type]
0x180027827  mov     r9d, [rbp+60h+var_5C]
0x18002782b  cmp     r9d, 4
0x18002782f  jnz     short loc_18002783E
0x180027831  cmp     r8d, r9d
0x180027834  jnz     short loc_18002783E
0x180027836  mov     eax, dword ptr [rbp+60h+Data]
0x180027839  jmp     loc_1800276CA
0x18002783e  lea     rax, WPP_GLOBAL_Control
0x180027845  mov     rcx, cs:WPP_GLOBAL_Control
0x18002784c  cmp     rcx, rax
0x18002784f  jz      short loc_180027872
0x180027851  cmp     byte ptr [rcx+19h], 2
0x180027855  jb      short loc_180027872
0x180027857  mov     edx, 18h
0x18002785c  mov     dword ptr [rsp+160h+lpcbData], r8d
0x180027861  mov     dword ptr [rsp+160h+lpData], r9d
0x180027866  mov     r9, rbx
0x180027869  mov     rcx, [rcx+10h]
0x18002786d  call    WPP_SF_SDD
0x180027872  mov     edx, 8007065Dh; int
0x180027877  lea     rcx, [rsp+160h+pExceptionObject]; this
0x18002787c  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180027881  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180027888  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18002788d  call    _CxxThrowException_0
```
