# RegistryKey::GetValueBlob(wchar_t const *,ulong *,RegistryKey::MissingValueDisposition)

- ea: `0x18002729c`
- end: `0x180027559`
- name: `?GetValueBlob@RegistryKey@@QEBA?AV?$vector@EV?$allocator@E@std@@@std@@PEB_WPEAKW4MissingValueDisposition@1@@Z`
- size: `701`
- prototype: `_QWORD *__fastcall(HKEY *, _QWORD *, const WCHAR *, _DWORD *, int)`
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x18001d9c0`
- `0x18001f2e4`
- `0x180027964`
- `0x180027d2c`

## callees

- `0x1800027c0`
- `0x1800032d8`
- `0x1800032e4`
- `0x180007048`
- `0x180008854`
- `0x180008c78`
- `0x18000d974`
- `0x18000ec8c`
- `0x18002498c`
- `0x1800267a8`
- `0x180026928`
- `0x18002729c`
- `0x180028804`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002730f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027392`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002730f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027392`

## pseudocode

```c
_QWORD *__fastcall RegistryKey::GetValueBlob(HKEY *a1, _QWORD *a2, const WCHAR *a3, _DWORD *a4, int a5)
{
  LSTATUS v9; // ebx
  char *v10; // rsi
  BYTE *v11; // rax
  size_t v12; // rbx
  LSTATUS v13; // ebx
  char *v14; // rsi
  BYTE *v15; // rax
  size_t v16; // rbx
  _BYTE pExceptionObject[208]; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+108h] [rbp+8h] BYREF
  LPBYTE lpData; // [rsp+110h] [rbp+10h] BYREF
  void *v21; // [rsp+118h] [rbp+18h]
  __int64 v22; // [rsp+120h] [rbp+20h]
  DWORD Type[2]; // [rsp+128h] [rbp+28h] BYREF

  *(_QWORD *)Type = a2;
  std::vector<unsigned char>::vector<unsigned char>(&lpData, 128);
  cbData = (_DWORD)v21 - (_DWORD)lpData;
  Type[0] = 0;
  v9 = RegQueryValueExW(*a1, a3, 0, Type, lpData, &cbData);
  if ( v9 == 234 )
  {
    v10 = (char *)v21;
    if ( cbData >= (unsigned __int64)((_BYTE *)v21 - lpData) )
    {
      if ( cbData <= (unsigned __int64)((_BYTE *)v21 - lpData) )
        goto LABEL_9;
      if ( cbData > (unsigned __int64)(v22 - (_QWORD)lpData) )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&lpData, cbData);
        goto LABEL_9;
      }
      v12 = cbData - ((_BYTE *)v21 - lpData);
      memset_0(v21, 0, v12);
      v11 = (BYTE *)&v10[v12];
    }
    else
    {
      v11 = &lpData[cbData];
    }
    v21 = v11;
LABEL_9:
    v13 = RegQueryValueExW(*a1, a3, 0, Type, lpData, &cbData);
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          (unsigned int)WPP_419802ccba213757c01acb0d7aa84d96_Traceguids,
          (_DWORD)a3,
          v13);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v13);
      throw (Win32Exception *)pExceptionObject;
    }
    goto LABEL_29;
  }
  if ( v9 == 2 )
  {
    if ( a5 == 1 )
    {
      std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(a2);
      goto LABEL_37;
    }
LABEL_18:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        (unsigned int)WPP_419802ccba213757c01acb0d7aa84d96_Traceguids,
        (_DWORD)a3,
        v9);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v9);
    throw (Win32Exception *)pExceptionObject;
  }
  if ( v9 )
    goto LABEL_18;
  v14 = (char *)v21;
  if ( cbData < (unsigned __int64)((_BYTE *)v21 - lpData) )
  {
    v15 = &lpData[cbData];
LABEL_28:
    v21 = v15;
    goto LABEL_29;
  }
  if ( cbData > (unsigned __int64)((_BYTE *)v21 - lpData) )
  {
    if ( cbData <= (unsigned __int64)(v22 - (_QWORD)lpData) )
    {
      v16 = cbData - ((_BYTE *)v21 - lpData);
      memset_0(v21, 0, v16);
      v15 = (BYTE *)&v14[v16];
      goto LABEL_28;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&lpData, cbData);
  }
LABEL_29:
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
  std::vector<unsigned char>::vector<unsigned char>(a2, &lpData);
LABEL_37:
  std::vector<unsigned char>::_Tidy((__int64)&lpData);
  return a2;
}

```

## disassembly

```asm
0x18002729c  push    rbp
0x18002729e  push    rbx
0x18002729f  push    rsi
0x1800272a0  push    rdi
0x1800272a1  push    r12
0x1800272a3  push    r14
0x1800272a5  push    r15
0x1800272a7  lea     rbp, [rsp-40h]
0x1800272ac  sub     rsp, 140h
0x1800272b3  mov     rax, cs:__security_cookie
0x1800272ba  xor     rax, rsp
0x1800272bd  mov     [rbp+70h+var_40], rax
0x1800272c1  mov     r15, r9
0x1800272c4  mov     r14, r8
0x1800272c7  mov     rdi, rdx
0x1800272ca  mov     r12, rcx
0x1800272cd  mov     qword ptr [rbp+70h+Type], rdx
0x1800272d1  mov     edx, 80h
0x1800272d6  lea     rcx, [rbp+70h+var_60]
0x1800272da  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800272df  nop
0x1800272e0  mov     rcx, [rbp+70h+var_60]
0x1800272e4  mov     eax, dword ptr [rbp+70h+var_58]
0x1800272e7  sub     eax, ecx
0x1800272e9  mov     [rbp+70h+cbData], eax
0x1800272ec  mov     [rbp+70h+Type], 0
0x1800272f3  lea     rax, [rbp+70h+cbData]
0x1800272f7  mov     [rsp+170h+lpcbData], rax; lpcbData
0x1800272fc  mov     [rsp+170h+lpData], rcx; lpData
0x180027301  lea     r9, [rbp+70h+Type]; lpType
0x180027305  xor     r8d, r8d; lpReserved
0x180027308  mov     rdx, r14; lpValueName
0x18002730b  mov     rcx, [r12]; hKey
0x18002730f  call    cs:__imp_RegQueryValueExW
0x180027315  mov     ebx, eax
0x180027317  cmp     eax, 0EAh
0x18002731c  jnz     loc_1800273F5
0x180027322  mov     ebx, [rbp+70h+cbData]
0x180027325  mov     rdx, [rbp+70h+var_60]
0x180027329  mov     rsi, [rbp+70h+var_58]
0x18002732d  mov     rcx, rsi
0x180027330  sub     rcx, rdx
0x180027333  cmp     rbx, rcx
0x180027336  jnb     short loc_18002733E
0x180027338  lea     rax, [rbx+rdx]
0x18002733c  jmp     short loc_18002736E
0x18002733e  jbe     short loc_180027372
0x180027340  mov     rax, [rbp+70h+var_50]
0x180027344  sub     rax, rdx
0x180027347  cmp     rbx, rax
0x18002734a  jbe     short loc_18002735A
0x18002734c  mov     rdx, rbx
0x18002734f  lea     rcx, [rbp+70h+var_60]
0x180027353  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180027358  jmp     short loc_180027372
0x18002735a  sub     rbx, rcx
0x18002735d  mov     r8, rbx; Size
0x180027360  xor     edx, edx; Val
0x180027362  mov     rcx, rsi; void *
0x180027365  call    memset_0
0x18002736a  lea     rax, [rbx+rsi]
0x18002736e  mov     [rbp+70h+var_58], rax
0x180027372  mov     rax, [rbp+70h+var_60]
0x180027376  lea     rcx, [rbp+70h+cbData]
0x18002737a  mov     [rsp+170h+lpcbData], rcx; lpcbData
0x18002737f  mov     [rsp+170h+lpData], rax; lpData
0x180027384  lea     r9, [rbp+70h+Type]; lpType
0x180027388  xor     r8d, r8d; lpReserved
0x18002738b  mov     rdx, r14; lpValueName
0x18002738e  mov     rcx, [r12]; hKey
0x180027392  call    cs:__imp_RegQueryValueExW
0x180027398  mov     ebx, eax
0x18002739a  test    eax, eax
0x18002739c  jz      loc_1800274B7
0x1800273a2  lea     rax, WPP_GLOBAL_Control
0x1800273a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800273b0  cmp     rcx, rax
0x1800273b3  jz      short loc_1800273D7
0x1800273b5  cmp     byte ptr [rcx+19h], 2
0x1800273b9  jb      short loc_1800273D7
0x1800273bb  mov     edx, 24h ; '$'
0x1800273c0  mov     dword ptr [rsp+170h+lpData], ebx
0x1800273c4  mov     r9, r14
0x1800273c7  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x1800273ce  mov     rcx, [rcx+10h]
0x1800273d2  call    WPP_SF_Sd
0x1800273d7  mov     edx, ebx; int
0x1800273d9  lea     rcx, [rsp+170h+pExceptionObject]; this
0x1800273de  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x1800273e3  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x1800273ea  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x1800273ef  call    _CxxThrowException_0
0x1800273f5  cmp     ebx, 2
0x1800273f8  jnz     short loc_180027410
0x1800273fa  cmp     [rbp+70h+arg_20], 1
0x180027401  jnz     short loc_180027414
0x180027403  mov     rcx, rdi
0x180027406  call    ??0?$vector@PEAUNETSETUP_RPC_CONTEXT@@V?$allocator@PEAUNETSETUP_RPC_CONTEXT@@@std@@@std@@QEAA@XZ; std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(void)
0x18002740b  jmp     loc_18002752F
0x180027410  test    ebx, ebx
0x180027412  jz      short loc_180027467
0x180027414  lea     rax, WPP_GLOBAL_Control
0x18002741b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027422  cmp     rcx, rax
0x180027425  jz      short loc_180027449
0x180027427  cmp     byte ptr [rcx+19h], 2
0x18002742b  jb      short loc_180027449
0x18002742d  mov     edx, 25h ; '%'
0x180027432  mov     dword ptr [rsp+170h+lpData], ebx
0x180027436  mov     r9, r14
0x180027439  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x180027440  mov     rcx, [rcx+10h]
0x180027444  call    WPP_SF_Sd
0x180027449  mov     edx, ebx; int
0x18002744b  lea     rcx, [rsp+170h+pExceptionObject]; this
0x180027450  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180027455  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18002745c  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x180027461  call    _CxxThrowException_0
0x180027467  mov     ebx, [rbp+70h+cbData]
0x18002746a  mov     rdx, [rbp+70h+var_60]
0x18002746e  mov     rsi, [rbp+70h+var_58]
0x180027472  mov     rcx, rsi
0x180027475  sub     rcx, rdx
0x180027478  cmp     rbx, rcx
0x18002747b  jnb     short loc_180027483
0x18002747d  lea     rax, [rbx+rdx]
0x180027481  jmp     short loc_1800274B3
0x180027483  jbe     short loc_1800274B7
0x180027485  mov     rax, [rbp+70h+var_50]
0x180027489  sub     rax, rdx
0x18002748c  cmp     rbx, rax
0x18002748f  jbe     short loc_18002749F
0x180027491  mov     rdx, rbx
0x180027494  lea     rcx, [rbp+70h+var_60]
0x180027498  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002749d  jmp     short loc_1800274B7
0x18002749f  sub     rbx, rcx
0x1800274a2  mov     r8, rbx; Size
0x1800274a5  xor     edx, edx; Val
0x1800274a7  mov     rcx, rsi; void *
0x1800274aa  call    memset_0
0x1800274af  lea     rax, [rbx+rsi]
0x1800274b3  mov     [rbp+70h+var_58], rax
0x1800274b7  test    r15, r15
0x1800274ba  jnz     short loc_18002751C
0x1800274bc  mov     r8d, [rbp+70h+Type]
0x1800274c0  cmp     r8d, 3
0x1800274c4  jz      short loc_180027522
0x1800274c6  lea     rax, WPP_GLOBAL_Control
0x1800274cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800274d4  cmp     rcx, rax
0x1800274d7  jz      short loc_1800274FB
0x1800274d9  cmp     byte ptr [rcx+19h], 2
0x1800274dd  jb      short loc_1800274FB
0x1800274df  lea     edx, [r15+26h]
0x1800274e3  mov     eax, [rbp+70h+cbData]
0x1800274e6  mov     dword ptr [rsp+170h+lpcbData], eax
0x1800274ea  mov     dword ptr [rsp+170h+lpData], r8d
0x1800274ef  mov     r9, r14
0x1800274f2  mov     rcx, [rcx+10h]
0x1800274f6  call    WPP_SF_SDD
0x1800274fb  mov     edx, 8007065Dh; int
0x180027500  lea     rcx, [rsp+170h+pExceptionObject]; this
0x180027505  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18002750a  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180027511  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x180027516  call    _CxxThrowException_0
0x18002751c  mov     eax, [rbp+70h+Type]
0x18002751f  mov     [r15], eax
0x180027522  lea     rdx, [rbp+70h+var_60]
0x180027526  mov     rcx, rdi
0x180027529  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> &&)
0x18002752e  nop
0x18002752f  lea     rcx, [rbp+70h+var_60]
0x180027533  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180027538  mov     rax, rdi
0x18002753b  mov     rcx, [rbp+70h+var_40]
0x18002753f  xor     rcx, rsp; StackCookie
0x180027542  call    __security_check_cookie
0x180027547  add     rsp, 140h
0x18002754e  pop     r15
0x180027550  pop     r14
0x180027552  pop     r12
0x180027554  pop     rdi
0x180027555  pop     rsi
0x180027556  pop     rbx
0x180027557  pop     rbp
0x180027558  retn
```
