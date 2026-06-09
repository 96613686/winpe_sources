# RegistryKey::GetValueBlob(wchar_t const *,ulong *,RegistryKey::MissingValueDisposition)

- ea: `0x180010548`
- end: `0x180010792`
- name: `?GetValueBlob@RegistryKey@@QEBA?AV?$vector@EV?$allocator@E@std@@@std@@PEB_WPEAKW4MissingValueDisposition@1@@Z`
- size: `586`
- prototype: `__int64 __fastcall(HKEY *, __int64, const WCHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800108e4`

## callees

- `0x1800065d4`
- `0x180006608`
- `0x18000895c`
- `0x18000d710`
- `0x18000ec70`
- `0x18000ee40`
- `0x18000fbfc`
- `0x180010548`
- `0x180010df0`
- `0x1800119f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800105c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010608`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800105c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010608`

## pseudocode

```c
__int64 __fastcall RegistryKey::GetValueBlob(HKEY *a1, __int64 a2, const WCHAR *a3, _DWORD *a4)
{
  LSTATUS v8; // esi
  LPBYTE v9; // r14
  LSTATUS v10; // esi
  LPBYTE lpData[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h]
  __int64 v14; // [rsp+50h] [rbp-B0h]
  _BYTE pExceptionObject[208]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+128h] [rbp+28h] BYREF
  DWORD Type[2]; // [rsp+130h] [rbp+30h] BYREF

  v14 = -2;
  *(_QWORD *)Type = a2;
  std::vector<unsigned char>::vector<unsigned char>(lpData);
  cbData = LODWORD(lpData[1]) - LODWORD(lpData[0]);
  Type[0] = 0;
  v8 = RegQueryValueExW(*a1, a3, 0, Type, lpData[0], &cbData);
  if ( v8 == 234 )
  {
    std::vector<unsigned char>::resize(lpData, cbData);
    v9 = lpData[0];
    v10 = RegQueryValueExW(*a1, a3, 0, Type, lpData[0], &cbData);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
          (_DWORD)a3,
          v10);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v10);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  else
  {
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
          (_DWORD)a3,
          v8);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v8);
      throw (Win32Exception *)pExceptionObject;
    }
    std::vector<unsigned char>::resize(lpData, cbData);
    v9 = lpData[0];
  }
  if ( a4 )
  {
    *a4 = Type[0];
  }
  else if ( Type[0] != 3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, Type[0], (_DWORD)a3, Type[0], cbData);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147023267);
    throw (HResultException *)pExceptionObject;
  }
  *(_QWORD *)a2 = v9;
  *(LPBYTE *)(a2 + 8) = lpData[1];
  *(_QWORD *)(a2 + 16) = v13;
  *(_OWORD *)lpData = 0;
  v13 = 0;
  std::vector<unsigned char>::_Tidy((__int64)lpData);
  return a2;
}

```

## disassembly

```asm
0x180010548  push    rbp
0x18001054a  push    rbx
0x18001054b  push    rsi
0x18001054c  push    rdi
0x18001054d  push    r12
0x18001054f  push    r14
0x180010551  push    r15
0x180010553  lea     rbp, [rsp-40h]
0x180010558  sub     rsp, 140h
0x18001055f  mov     [rsp+170h+var_120], 0FFFFFFFFFFFFFFFEh
0x180010568  mov     rax, cs:__security_cookie
0x18001056f  xor     rax, rsp
0x180010572  mov     [rbp+70h+var_38], rax
0x180010576  mov     r15, r9
0x180010579  mov     rdi, r8
0x18001057c  mov     rbx, rdx
0x18001057f  mov     r12, rcx
0x180010582  mov     qword ptr [rbp+70h+Type], rdx
0x180010586  mov     edx, 80h
0x18001058b  lea     rcx, [rsp+170h+var_140]
0x180010590  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_K@Z; std::vector<uchar>::vector<uchar>(unsigned __int64)
0x180010595  nop
0x180010596  mov     eax, dword ptr [rsp+170h+var_140+8]
0x18001059a  mov     rcx, [rsp+170h+var_140]
0x18001059f  sub     eax, ecx
0x1800105a1  mov     [rbp+70h+cbData], eax
0x1800105a4  mov     [rbp+70h+Type], 0
0x1800105ab  lea     rax, [rbp+70h+cbData]
0x1800105af  mov     [rsp+170h+lpcbData], rax; lpcbData
0x1800105b4  mov     [rsp+170h+lpData], rcx; lpData
0x1800105b9  lea     r9, [rbp+70h+Type]; lpType
0x1800105bd  xor     r8d, r8d; lpReserved
0x1800105c0  mov     rdx, rdi; lpValueName
0x1800105c3  mov     rcx, [r12]; hKey
0x1800105c7  call    cs:__imp_RegQueryValueExW
0x1800105cd  mov     esi, eax
0x1800105cf  cmp     eax, 0EAh
0x1800105d4  jnz     loc_18001066B
0x1800105da  mov     edx, [rbp+70h+cbData]
0x1800105dd  lea     rcx, [rsp+170h+var_140]
0x1800105e2  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800105e7  lea     rax, [rbp+70h+cbData]
0x1800105eb  mov     [rsp+170h+lpcbData], rax; lpcbData
0x1800105f0  mov     r14, [rsp+170h+var_140]
0x1800105f5  mov     [rsp+170h+lpData], r14; lpData
0x1800105fa  lea     r9, [rbp+70h+Type]; lpType
0x1800105fe  xor     r8d, r8d; lpReserved
0x180010601  mov     rdx, rdi; lpValueName
0x180010604  mov     rcx, [r12]; hKey
0x180010608  call    cs:__imp_RegQueryValueExW
0x18001060e  mov     esi, eax
0x180010610  test    eax, eax
0x180010612  jz      loc_1800106D5
0x180010618  lea     rax, WPP_GLOBAL_Control
0x18001061f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010626  cmp     rcx, rax
0x180010629  jz      short loc_18001064D
0x18001062b  cmp     byte ptr [rcx+19h], 2
0x18001062f  jb      short loc_18001064D
0x180010631  mov     edx, 24h ; '$'
0x180010636  mov     dword ptr [rsp+170h+lpData], esi
0x18001063a  mov     r9, rdi
0x18001063d  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x180010644  mov     rcx, [rcx+10h]
0x180010648  call    WPP_SF_SD
0x18001064d  mov     edx, esi; int
0x18001064f  lea     rcx, [rsp+170h+pExceptionObject]; this
0x180010654  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180010659  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180010660  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x180010665  call    _CxxThrowException_0
0x18001066b  cmp     esi, 1
0x18001066e  jb      short loc_1800106C3
0x180010670  lea     rax, WPP_GLOBAL_Control
0x180010677  mov     rcx, cs:WPP_GLOBAL_Control
0x18001067e  cmp     rcx, rax
0x180010681  jz      short loc_1800106A5
0x180010683  cmp     byte ptr [rcx+19h], 2
0x180010687  jb      short loc_1800106A5
0x180010689  mov     edx, 25h ; '%'
0x18001068e  mov     dword ptr [rsp+170h+lpData], esi
0x180010692  mov     r9, rdi
0x180010695  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x18001069c  mov     rcx, [rcx+10h]
0x1800106a0  call    WPP_SF_SD
0x1800106a5  mov     edx, esi; int
0x1800106a7  lea     rcx, [rsp+170h+pExceptionObject]; this
0x1800106ac  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x1800106b1  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x1800106b8  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x1800106bd  call    _CxxThrowException_0
0x1800106c3  mov     edx, [rbp+70h+cbData]
0x1800106c6  lea     rcx, [rsp+170h+var_140]
0x1800106cb  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800106d0  mov     r14, [rsp+170h+var_140]
0x1800106d5  test    r15, r15
0x1800106d8  jnz     short loc_18001073A
0x1800106da  mov     r8d, [rbp+70h+Type]
0x1800106de  cmp     r8d, 3
0x1800106e2  jz      short loc_180010740
0x1800106e4  lea     rax, WPP_GLOBAL_Control
0x1800106eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106f2  cmp     rcx, rax
0x1800106f5  jz      short loc_180010719
0x1800106f7  cmp     byte ptr [rcx+19h], 2
0x1800106fb  jb      short loc_180010719
0x1800106fd  lea     edx, [r15+26h]
0x180010701  mov     eax, [rbp+70h+cbData]
0x180010704  mov     dword ptr [rsp+170h+lpcbData], eax
0x180010708  mov     dword ptr [rsp+170h+lpData], r8d
0x18001070d  mov     r9, rdi
0x180010710  mov     rcx, [rcx+10h]
0x180010714  call    WPP_SF_SDD
0x180010719  mov     edx, 8007065Dh; int
0x18001071e  lea     rcx, [rsp+170h+pExceptionObject]; this
0x180010723  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180010728  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18001072f  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x180010734  call    _CxxThrowException_0
0x18001073a  mov     eax, [rbp+70h+Type]
0x18001073d  mov     [r15], eax
0x180010740  mov     [rbx], r14
0x180010743  mov     rcx, [rsp+170h+var_140+8]
0x180010748  mov     [rbx+8], rcx
0x18001074c  mov     rcx, [rsp+170h+var_130]
0x180010751  mov     [rbx+10h], rcx
0x180010755  xorps   xmm0, xmm0
0x180010758  movdqu  xmmword ptr [rsp+170h+var_140], xmm0
0x18001075e  mov     [rsp+170h+var_130], 0
0x180010767  lea     rcx, [rsp+170h+var_140]
0x18001076c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180010771  mov     rax, rbx
0x180010774  mov     rcx, [rbp+70h+var_38]
0x180010778  xor     rcx, rsp; StackCookie
0x18001077b  call    __security_check_cookie
0x180010780  add     rsp, 140h
0x180010787  pop     r15
0x180010789  pop     r14
0x18001078b  pop     r12
0x18001078d  pop     rdi
0x18001078e  pop     rsi
0x18001078f  pop     rbx
0x180010790  pop     rbp
0x180010791  retn
```
