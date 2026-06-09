# AppCompatUtility::RegOperations::GetStringValues(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x180046c94`
- end: `0x180046f70`
- name: `?GetStringValues@RegOperations@AppCompatUtility@@YAJPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@5@@Z`
- size: `732`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004937c`

## callees

- `0x180001cf0`
- `0x1800020c0`
- `0x180002bb8`
- `0x18000b5fc`
- `0x18000b720`
- `0x180046048`
- `0x180046c94`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180046d84`
- `ADVAPI32!RegCloseKey` at `0x180046f38`
- `ADVAPI32!RegCloseKey` at `0x180046d84`
- `ADVAPI32!RegCloseKey` at `0x180046f38`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180046d74`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180046d74`
- `ADVAPI32!RegEnumValueW` at `0x180046e18`
- `ADVAPI32!RegEnumValueW` at `0x180046e18`
- `ADVAPI32!RegGetValueW` at `0x180046e72`
- `ADVAPI32!RegGetValueW` at `0x180046e72`
- `ADVAPI32!RegOpenKeyW` at `0x180046ce6`
- `ADVAPI32!RegOpenKeyW` at `0x180046ce6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LSTATUS __fastcall AppCompatUtility::RegOperations::GetStringValues(__int64 a1, const WCHAR *a2, __int64 *a3)
{
  LSTATUS result; // eax
  __int64 v5; // rbx
  __int64 v6; // rsi
  LSTATUS v7; // ebx
  DWORD v8; // r12d
  WCHAR *v9; // rsi
  DWORD i; // r14d
  DWORD v11; // ebx
  void *v12; // r15
  __int64 v13; // rbx
  __int64 v14; // r8
  DWORD cbData; // [rsp+68h] [rbp-49h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp-45h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-41h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+78h] [rbp-39h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-35h] BYREF
  DWORD cchValueName; // [rsp+80h] [rbp-31h] BYREF
  _QWORD v21[4]; // [rsp+88h] [rbp-29h] BYREF
  __int128 v22; // [rsp+A8h] [rbp-9h] BYREF
  __int128 v23; // [rsp+B8h] [rbp+7h]

  v21[1] = -2;
  phkResult = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  result = RegOpenKeyW(HKEY_LOCAL_MACHINE, a2, &phkResult);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v5 = *a3;
    v6 = a3[1];
    if ( *a3 != v6 )
    {
      do
      {
        std::wstring::~wstring((void *)(v5 + 32));
        std::wstring::~wstring((void *)v5);
        v5 += 64;
      }
      while ( v5 != v6 );
      a3[1] = *a3;
    }
    cValues = 0;
    cbMaxValueNameLen = 0;
    v7 = RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
    if ( v7 )
    {
      RegCloseKey(phkResult);
      if ( v7 > 0 )
        return (unsigned __int16)v7 | 0x80070000;
      return v7;
    }
    else
    {
      v8 = 4096;
      if ( cbMaxValueNameLen + 1 < 0x1000 )
        v8 = cbMaxValueNameLen + 1;
      v9 = (WCHAR *)operator new[](saturated_mul(v8, 2u));
      v21[2] = v9;
      for ( i = 0; i < cValues; ++i )
      {
        cchValueName = v8;
        Type = 0;
        cbData = 0;
        if ( !RegEnumValueW(phkResult, i, v9, &cchValueName, 0, &Type, 0, &cbData) && Type == 1 )
        {
          v11 = cbData >> 1;
          v12 = operator new[](saturated_mul(cbData >> 1, 2u));
          v21[3] = v12;
          if ( !RegGetValueW(phkResult, 0, v9, 2u, 0, v12, &cbData) )
          {
            v22 = 0;
            v23 = 0u;
            std::wstring::_Construct<1,unsigned short const *>(&v22, v12, v11 - 1);
            v21[0] = v9;
            v13 = a3[1];
            if ( v13 == a3[2] )
            {
              std::vector<std::pair<std::wstring,std::wstring>>::_Emplace_reallocate<unsigned short *,std::wstring>(
                a3,
                a3[1],
                v21,
                &v22);
            }
            else
            {
              *(_OWORD *)v13 = 0;
              *(_QWORD *)(v13 + 16) = 0;
              *(_QWORD *)(v13 + 24) = 0;
              v14 = -1;
              do
                ++v14;
              while ( v9[v14] );
              std::wstring::_Construct<1,unsigned short const *>(v13, v9, v14);
              *(_OWORD *)(v13 + 32) = v22;
              *(_OWORD *)(v13 + 48) = v23;
              *(_QWORD *)&v23 = 0;
              *((_QWORD *)&v23 + 1) = 7;
              LOWORD(v22) = 0;
              a3[1] += 64;
            }
            std::wstring::~wstring(&v22);
          }
          operator delete(v12);
        }
      }
      RegCloseKey(phkResult);
      operator delete(v9);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180046c94  mov     rax, rsp
0x180046c97  push    rbp
0x180046c98  push    rsi
0x180046c99  push    rdi
0x180046c9a  push    r12
0x180046c9c  push    r13
0x180046c9e  push    r14
0x180046ca0  push    r15
0x180046ca2  lea     rbp, [rax-5Fh]
0x180046ca6  sub     rsp, 0D0h
0x180046cad  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFEh
0x180046cb5  mov     [rax+8], rbx
0x180046cb9  mov     rax, cs:__security_cookie
0x180046cc0  xor     rax, rsp
0x180046cc3  mov     [rbp+57h+var_40], rax
0x180046cc7  mov     rdi, r8
0x180046cca  xor     r13d, r13d
0x180046ccd  mov     [rbp+57h+phkResult], r13
0x180046cd1  cmp     qword ptr [rdx+18h], 7
0x180046cd6  jbe     short loc_180046CDB
0x180046cd8  mov     rdx, [rdx]; lpSubKey
0x180046cdb  lea     r8, [rbp+57h+phkResult]; phkResult
0x180046cdf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180046ce6  call    cs:__imp_RegOpenKeyW
0x180046cec  test    eax, eax
0x180046cee  jz      short loc_180046D03
0x180046cf0  jle     loc_180046F49
0x180046cf6  movzx   eax, ax
0x180046cf9  or      eax, 80070000h
0x180046cfe  jmp     loc_180046F49
0x180046d03  mov     rbx, [rdi]
0x180046d06  mov     rsi, [rdi+8]
0x180046d0a  cmp     rbx, rsi
0x180046d0d  jz      short loc_180046D30
0x180046d0f  lea     rcx, [rbx+20h]; void *
0x180046d13  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180046d18  mov     rcx, rbx; void *
0x180046d1b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180046d20  add     rbx, 40h ; '@'
0x180046d24  cmp     rbx, rsi
0x180046d27  jnz     short loc_180046D0F
0x180046d29  mov     rax, [rdi]
0x180046d2c  mov     [rdi+8], rax
0x180046d30  mov     [rbp+57h+cValues], r13d
0x180046d34  mov     [rbp+57h+cbMaxValueNameLen], r13d
0x180046d38  mov     [rsp+58h], r13; lpftLastWriteTime
0x180046d3d  mov     [rsp+100h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180046d42  mov     [rsp+100h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180046d47  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x180046d4b  mov     [rsp+100h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180046d50  lea     rax, [rbp+57h+cValues]
0x180046d54  mov     [rsp+100h+lpcValues], rax; lpcValues
0x180046d59  mov     [rsp+100h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180046d5e  mov     [rsp+100h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180046d63  mov     [rsp+100h+lpcSubKeys], r13; lpcSubKeys
0x180046d68  xor     r9d, r9d; lpReserved
0x180046d6b  xor     r8d, r8d; lpcchClass
0x180046d6e  xor     edx, edx; lpClass
0x180046d70  mov     rcx, [rbp+57h+phkResult]; hKey
0x180046d74  call    cs:__imp_RegQueryInfoKeyW
0x180046d7a  mov     ebx, eax
0x180046d7c  test    eax, eax
0x180046d7e  jz      short loc_180046D9E
0x180046d80  mov     rcx, [rbp+57h+phkResult]; hKey
0x180046d84  call    cs:__imp_RegCloseKey
0x180046d8a  test    ebx, ebx
0x180046d8c  jle     short loc_180046D97
0x180046d8e  movzx   ebx, bx
0x180046d91  or      ebx, 80070000h
0x180046d97  mov     eax, ebx
0x180046d99  jmp     loc_180046F49
0x180046d9e  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x180046da1  inc     eax
0x180046da3  mov     r12d, 1000h
0x180046da9  cmp     eax, r12d
0x180046dac  cmovb   r12d, eax
0x180046db0  mov     ecx, r12d
0x180046db3  mov     eax, 2
0x180046db8  mul     rcx
0x180046dbb  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180046dc2  cmovb   rax, r15
0x180046dc6  mov     rcx, rax; unsigned __int64
0x180046dc9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180046dce  mov     rsi, rax
0x180046dd1  mov     [rbp+57h+var_70], rax
0x180046dd5  mov     r14d, r13d
0x180046dd8  cmp     [rbp+57h+cValues], r13d
0x180046ddc  jbe     loc_180046F34
0x180046de2  mov     [rbp+57h+cchValueName], r12d
0x180046de6  mov     [rbp+57h+Type], r13d
0x180046dea  mov     [rbp+57h+cbData], r13d
0x180046dee  lea     rax, [rbp+57h+cbData]
0x180046df2  mov     [rsp+100h+lpcValues], rax; lpcbData
0x180046df7  mov     [rsp+100h+lpcbMaxClassLen], r13; lpData
0x180046dfc  lea     rax, [rbp+57h+Type]
0x180046e00  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpType
0x180046e05  mov     [rsp+100h+lpcSubKeys], r13; lpReserved
0x180046e0a  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180046e0e  mov     r8, rsi; lpValueName
0x180046e11  mov     edx, r14d; dwIndex
0x180046e14  mov     rcx, [rbp+57h+phkResult]; hKey
0x180046e18  call    cs:__imp_RegEnumValueW
0x180046e1e  test    eax, eax
0x180046e20  jnz     loc_180046F27
0x180046e26  cmp     [rbp+57h+Type], 1
0x180046e2a  jnz     loc_180046F27
0x180046e30  mov     ebx, [rbp+57h+cbData]
0x180046e33  shr     ebx, 1
0x180046e35  mov     eax, 2
0x180046e3a  mul     rbx
0x180046e3d  cmovb   rax, r15
0x180046e41  mov     rcx, rax; unsigned __int64
0x180046e44  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180046e49  mov     r15, rax
0x180046e4c  mov     [rbp+57h+var_68], rax
0x180046e50  lea     rax, [rbp+57h+cbData]
0x180046e54  mov     [rsp+100h+lpcbMaxClassLen], rax; pcbData
0x180046e59  mov     [rsp+100h+lpcbMaxSubKeyLen], r15; pvData
0x180046e5e  mov     [rsp+100h+lpcSubKeys], r13; pdwType
0x180046e63  mov     r9d, 2; dwFlags
0x180046e69  mov     r8, rsi; lpValue
0x180046e6c  xor     edx, edx; lpSubKey
0x180046e6e  mov     rcx, [rbp+57h+phkResult]; hkey
0x180046e72  call    cs:__imp_RegGetValueW
0x180046e78  test    eax, eax
0x180046e7a  jnz     loc_180046F1B
0x180046e80  xorps   xmm0, xmm0
0x180046e83  movups  [rbp+57h+var_60], xmm0
0x180046e87  mov     qword ptr [rbp+57h+var_50], r13
0x180046e8b  mov     qword ptr [rbp+57h+var_50+8], r13
0x180046e8f  lea     r8d, [rbx-1]
0x180046e93  mov     rdx, r15
0x180046e96  lea     rcx, [rbp+57h+var_60]
0x180046e9a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180046e9f  nop
0x180046ea0  mov     [rbp+57h+var_80], rsi
0x180046ea4  mov     rbx, [rdi+8]
0x180046ea8  cmp     rbx, [rdi+10h]
0x180046eac  jz      short loc_180046EFD
0x180046eae  xorps   xmm0, xmm0
0x180046eb1  movups  xmmword ptr [rbx], xmm0
0x180046eb4  mov     [rbx+10h], r13
0x180046eb8  mov     [rbx+18h], r13
0x180046ebc  or      r8, 0FFFFFFFFFFFFFFFFh
0x180046ec0  inc     r8
0x180046ec3  cmp     [rsi+r8*2], r13w
0x180046ec8  jnz     short loc_180046EC0
0x180046eca  mov     rdx, rsi
0x180046ecd  mov     rcx, rbx
0x180046ed0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180046ed5  movups  xmm0, [rbp+57h+var_60]
0x180046ed9  movups  xmmword ptr [rbx+20h], xmm0
0x180046edd  movups  xmm1, [rbp+57h+var_50]
0x180046ee1  movups  xmmword ptr [rbx+30h], xmm1
0x180046ee5  mov     qword ptr [rbp+57h+var_50], r13
0x180046ee9  mov     qword ptr [rbp+57h+var_50+8], 7
0x180046ef1  mov     word ptr [rbp+57h+var_60], r13w
0x180046ef6  add     qword ptr [rdi+8], 40h ; '@'
0x180046efb  jmp     short loc_180046F11
0x180046efd  lea     r9, [rbp+57h+var_60]
0x180046f01  lea     r8, [rbp+57h+var_80]
0x180046f05  mov     rdx, rbx
0x180046f08  mov     rcx, rdi
0x180046f0b  call    ??$_Emplace_reallocate@PEAGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@QEAU21@$$QEAPEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::vector<std::pair<std::wstring,std::wstring>>::_Emplace_reallocate<ushort *,std::wstring>(std::pair<std::wstring,std::wstring> * const,ushort * &&,std::wstring &&)
0x180046f10  nop
0x180046f11  lea     rcx, [rbp+57h+var_60]; void *
0x180046f15  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180046f1a  nop
0x180046f1b  mov     rcx, r15; Block
0x180046f1e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180046f23  or      r15, 0FFFFFFFFFFFFFFFFh
0x180046f27  inc     r14d
0x180046f2a  cmp     r14d, [rbp+57h+cValues]
0x180046f2e  jb      loc_180046DE2
0x180046f34  mov     rcx, [rbp+57h+phkResult]; hKey
0x180046f38  call    cs:__imp_RegCloseKey
0x180046f3e  nop
0x180046f3f  mov     rcx, rsi; Block
0x180046f42  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180046f47  xor     eax, eax
0x180046f49  mov     rcx, [rbp+57h+var_40]
0x180046f4d  xor     rcx, rsp; StackCookie
0x180046f50  call    __security_check_cookie
0x180046f55  mov     rbx, [rsp+100h+arg_0]
0x180046f5d  add     rsp, 0D0h
0x180046f64  pop     r15
0x180046f66  pop     r14
0x180046f68  pop     r13
0x180046f6a  pop     r12
0x180046f6c  pop     rdi
0x180046f6d  pop     rsi
0x180046f6e  pop     rbp
0x180046f6f  retn
```
