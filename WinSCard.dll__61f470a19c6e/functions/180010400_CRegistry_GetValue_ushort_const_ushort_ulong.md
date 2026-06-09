# CRegistry::GetValue(ushort const *,ushort * *,ulong *)

- ea: `0x180010400`
- end: `0x1800107a0`
- name: `?GetValue@CRegistry@@QEAAXPEBGPEAPEAGPEAK@Z`
- size: `928`
- prototype: `void __fastcall(CRegistry *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `6`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180009480`
- `0x18000ff40`
- `0x18002a8ec`
- `0x18002aaf8`
- `0x18002ad8c`
- `0x18002b2d8`

## callees

- `0x180003ee0`
- `0x18000d320`
- `0x180010400`
- `0x18001b9b8`
- `0x18001ba04`
- `0x18002ef20`
- `0x18002ef38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001046b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010511`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001046b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010705`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800106ae`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800106f8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800106ae`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800106f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRegistry::GetValue(HKEY *this, const unsigned __int16 *a2, unsigned __int16 **a3, unsigned int *a4)
{
  const WCHAR *v5; // r12
  LSTATUS v6; // eax
  DWORD v7; // ebx
  DWORD *v8; // r14
  void *v9; // rdi
  void **v10; // r15
  HKEY v11; // rcx
  int v12; // edi
  const WCHAR *v13; // r13
  BYTE *lpData; // rax
  LSTATUS v15; // eax
  DWORD v16; // ebx
  void *v17; // rdi
  void *v18; // rcx
  WCHAR *v19; // r12
  void *v20; // rax
  DWORD v21; // ebx
  void *v22; // r12
  const WCHAR *v23; // rcx
  int v24; // r14d
  DWORD v25; // eax
  DWORD v26; // edi
  WCHAR *v27; // rax
  const WCHAR *v28; // rcx
  DWORD Type; // [rsp+30h] [rbp-38h] BYREF
  DWORD lpcbData; // [rsp+34h] [rbp-34h] BYREF
  DWORD LastError; // [rsp+38h] [rbp-30h] BYREF
  WCHAR *pExceptionObject; // [rsp+40h] [rbp-28h] BYREF
  const int *v33; // [rsp+48h] [rbp-20h] BYREF
  LPCWSTR lpSrc; // [rsp+50h] [rbp-18h]
  __int64 v35; // [rsp+58h] [rbp-10h]
  DWORD cbData; // [rsp+B0h] [rbp+48h] BYREF
  LPCWSTR lpValueName; // [rsp+B8h] [rbp+50h]
  unsigned __int16 **v38; // [rsp+C0h] [rbp+58h]
  unsigned int *Dst; // [rsp+C8h] [rbp+60h] BYREF

  Dst = a4;
  v38 = a3;
  lpValueName = a2;
  Type = 0;
  LOWORD(Dst) = 0;
  v33 = &CBuffer::`vftable';
  pExceptionObject = 0;
  lpSrc = 0;
  v35 = 0;
  cbData = 0;
  v5 = a2;
  v6 = RegQueryValueExW(*this, a2, 0, &Type, 0, &cbData);
  if ( v6 )
  {
    LastError = v6;
    throw &LastError;
  }
  if ( Type == 1 )
    goto LABEL_3;
  if ( Type != 2 )
  {
    if ( Type != 3 && Type != 7 )
    {
      LastError = 11;
      throw &LastError;
    }
LABEL_3:
    v7 = cbData;
    v8 = (DWORD *)this + 9;
    if ( *((_DWORD *)this + 9) >= cbData )
    {
      v10 = (void **)(this + 3);
    }
    else
    {
      v9 = operator new[](cbData);
      if ( !v9 )
      {
        LastError = 14;
        throw &LastError;
      }
      v10 = (void **)(this + 3);
      v11 = this[3];
      if ( v11 )
        operator delete(v11);
      *v10 = v9;
      *v8 = v7;
    }
    *((_DWORD *)this + 8) = 0;
    LastError = 0;
    if ( *((_DWORD *)this + 10) )
    {
      LODWORD(pExceptionObject) = *((_DWORD *)this + 10);
      throw (ulong *)&pExceptionObject;
    }
    v12 = 0;
    v13 = &WideCharStr;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v12 )
        {
          Type = LastError;
          v19 = pExceptionObject;
          goto LABEL_22;
        }
        lpcbData = *v8;
        lpData = lpcbData ? (BYTE *)this[3] : (BYTE *)&WideCharStr;
        v15 = RegQueryValueExW(*this, v5, 0, &LastError, lpData, &lpcbData);
        if ( !v15 )
          break;
        if ( v15 != 234 )
        {
          LODWORD(pExceptionObject) = v15;
          throw (ulong *)&pExceptionObject;
        }
        v21 = lpcbData;
        if ( *v8 < lpcbData )
        {
          v22 = operator new[](lpcbData);
          if ( !v22 )
          {
            LODWORD(pExceptionObject) = 14;
            throw (ulong *)&pExceptionObject;
          }
          if ( *v10 )
            operator delete(*v10);
          *v10 = v22;
          *v8 = v21;
          v5 = lpValueName;
        }
        *((_DWORD *)this + 8) = 0;
      }
      v16 = lpcbData;
      if ( !*((_DWORD *)this + 8) )
        break;
      if ( *v8 < lpcbData )
      {
        v20 = operator new[](lpcbData);
        v17 = v20;
        if ( !v20 )
        {
          LODWORD(pExceptionObject) = 14;
          throw (ulong *)&pExceptionObject;
        }
        memcpy_0(v20, *v10, *((unsigned int *)this + 8));
        v18 = *v10;
        goto LABEL_18;
      }
LABEL_20:
      v12 = 1;
      *((_DWORD *)this + 8) = v16;
    }
    if ( *v8 >= lpcbData )
      goto LABEL_20;
    v17 = operator new[](lpcbData);
    if ( !v17 )
    {
      LODWORD(pExceptionObject) = 14;
      throw (ulong *)&pExceptionObject;
    }
    v18 = *v10;
    if ( *v10 )
LABEL_18:
      operator delete(v18);
    *v8 = v16;
    *v10 = v17;
    goto LABEL_20;
  }
  CBuffer::Presize((CBuffer *)&v33, cbData, 0);
  CRegistry::GetValue((CRegistry *)this, v5, (struct CBuffer *)&v33, &Type);
  v13 = &WideCharStr;
  v23 = &WideCharStr;
  v19 = (WCHAR *)lpSrc;
  v24 = HIDWORD(v35);
  if ( HIDWORD(v35) )
    v23 = lpSrc;
  v25 = ExpandEnvironmentStringsW(v23, (LPWSTR)&Dst, 0);
  v26 = v25;
  cbData = v25;
  if ( !v25 )
  {
    LastError = GetLastError();
    throw &LastError;
  }
  v27 = (WCHAR *)CBuffer::Presize((CBuffer *)(this + 2), v25, 0);
  *((_DWORD *)this + 8) = v26;
  v28 = &WideCharStr;
  if ( v24 )
    v28 = v19;
  cbData = ExpandEnvironmentStringsW(v28, v27, v26);
  if ( !cbData )
  {
    LastError = GetLastError();
    throw &LastError;
  }
  v8 = (DWORD *)this + 9;
  v10 = (void **)(this + 3);
LABEL_22:
  if ( *v8 )
    v13 = (const WCHAR *)*v10;
  *v38 = (unsigned __int16 *)v13;
  if ( v19 )
    operator delete(v19);
}

```

## disassembly

```asm
0x180010400  mov     [rsp-40h+Dst], r9
0x180010405  mov     [rsp-40h+arg_10], r8
0x18001040a  mov     [rsp-40h+lpValueName], rdx
0x18001040f  push    rbp
0x180010410  push    rbx
0x180010411  push    rsi
0x180010412  push    rdi
0x180010413  push    r12
0x180010415  push    r13
0x180010417  push    r14
0x180010419  push    r15
0x18001041b  mov     rbp, rsp
0x18001041e  sub     rsp, 68h
0x180010422  mov     rsi, rcx
0x180010425  xor     r13d, r13d
0x180010428  mov     [rbp+Type], r13d
0x18001042c  mov     word ptr [rbp+Dst], r13w
0x180010431  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180010438  mov     [rbp+var_20], rax
0x18001043c  mov     [rbp+pExceptionObject], r13
0x180010440  mov     [rbp+lpSrc], r13
0x180010444  mov     [rbp+var_10], r13
0x180010448  mov     [rbp+cbData], r13d
0x18001044c  lea     rax, [rbp+cbData]
0x180010450  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180010455  mov     [rsp+68h+lpData], r13; lpData
0x18001045a  lea     r9, [rbp+Type]; lpType
0x18001045e  xor     r8d, r8d; lpReserved
0x180010461  mov     r12, [rbp+lpValueName]
0x180010465  mov     rdx, r12; lpValueName
0x180010468  mov     rcx, [rcx]; hKey
0x18001046b  call    cs:__imp_RegQueryValueExW
0x180010471  test    eax, eax
0x180010473  jnz     loc_180010629
0x180010479  mov     eax, [rbp+Type]
0x18001047c  cmp     eax, 1
0x18001047f  jnz     loc_18001063D
0x180010485  mov     ebx, [rbp+cbData]
0x180010488  lea     r14, [rsi+24h]
0x18001048c  cmp     [r14], ebx
0x18001048f  jnb     loc_18001060C
0x180010495  mov     ecx, ebx; unsigned __int64
0x180010497  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001049c  mov     rdi, rax
0x18001049f  test    rax, rax
0x1800104a2  jz      loc_18001072C
0x1800104a8  lea     r15, [rsi+18h]
0x1800104ac  mov     rcx, [r15]; void *
0x1800104af  test    rcx, rcx
0x1800104b2  jz      short loc_1800104B9
0x1800104b4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800104b9  mov     [r15], rdi
0x1800104bc  mov     [r14], ebx
0x1800104bf  mov     [rsi+20h], r13d
0x1800104c3  mov     [rbp+var_30], r13d
0x1800104c7  mov     eax, [rsi+28h]
0x1800104ca  test    eax, eax
0x1800104cc  jnz     loc_180010744
0x1800104d2  mov     edi, r13d
0x1800104d5  lea     r13, WideCharStr
0x1800104dc  nop     dword ptr [rax+00h]
0x1800104e0  test    edi, edi
0x1800104e2  jnz     short loc_18001055C
0x1800104e4  mov     eax, [r14]
0x1800104e7  mov     [rbp+var_34], eax
0x1800104ea  test    eax, eax
0x1800104ec  jz      loc_180010604
0x1800104f2  mov     rax, [rsi+18h]
0x1800104f6  lea     rcx, [rbp+var_34]
0x1800104fa  mov     [rsp+68h+lpcbData], rcx; lpcbData
0x1800104ff  mov     [rsp+68h+lpData], rax; lpData
0x180010504  lea     r9, [rbp+var_30]; lpType
0x180010508  xor     r8d, r8d; lpReserved
0x18001050b  mov     rdx, r12; lpValueName
0x18001050e  mov     rcx, [rsi]; hKey
0x180010511  call    cs:__imp_RegQueryValueExW
0x180010517  test    eax, eax
0x180010519  jnz     loc_1800105C1
0x18001051f  mov     ebx, [rbp+var_34]
0x180010522  cmp     [rsi+20h], eax
0x180010525  ja      short loc_180010594
0x180010527  cmp     [r14], ebx
0x18001052a  jnb     short loc_180010552
0x18001052c  mov     ecx, ebx; unsigned __int64
0x18001052e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010533  mov     rdi, rax
0x180010536  test    rax, rax
0x180010539  jz      loc_180010788
0x18001053f  mov     rcx, [r15]; void *
0x180010542  test    rcx, rcx
0x180010545  jz      short loc_18001054C
0x180010547  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001054c  mov     [r14], ebx
0x18001054f  mov     [r15], rdi
0x180010552  mov     edi, 1
0x180010557  mov     [rsi+20h], ebx
0x18001055a  jmp     short loc_1800104E0
0x18001055c  mov     eax, [rbp+var_30]
0x18001055f  mov     [rbp+Type], eax
0x180010562  mov     r12, [rbp+pExceptionObject]
0x180010566  cmp     dword ptr [r14], 0
0x18001056a  jbe     short loc_18001056F
0x18001056c  mov     r13, [r15]
0x18001056f  mov     rax, [rbp+arg_10]
0x180010573  mov     [rax], r13
0x180010576  test    r12, r12
0x180010579  jz      short loc_180010583
0x18001057b  mov     rcx, r12; void *
0x18001057e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010583  add     rsp, 68h
0x180010587  pop     r15
0x180010589  pop     r14
0x18001058b  pop     r13
0x18001058d  pop     r12
0x18001058f  pop     rdi
0x180010590  pop     rsi
0x180010591  pop     rbx
0x180010592  pop     rbp
0x180010593  retn
0x180010594  cmp     [r14], ebx
0x180010597  jnb     short loc_180010552
0x180010599  mov     rcx, rbx; unsigned __int64
0x18001059c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800105a1  mov     rdi, rax
0x1800105a4  test    rax, rax
0x1800105a7  jz      loc_180010770
0x1800105ad  mov     r8d, [rsi+20h]; Size
0x1800105b1  mov     rdx, [r15]; Src
0x1800105b4  mov     rcx, rax; void *
0x1800105b7  call    memcpy_0
0x1800105bc  mov     rcx, [r15]
0x1800105bf  jmp     short loc_180010547
0x1800105c1  cmp     eax, 0EAh
0x1800105c6  jnz     short loc_180010615
0x1800105c8  mov     ebx, [rbp+var_34]
0x1800105cb  cmp     [r14], ebx
0x1800105ce  jnb     short loc_1800105FA
0x1800105d0  mov     ecx, ebx; unsigned __int64
0x1800105d2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800105d7  mov     r12, rax
0x1800105da  test    rax, rax
0x1800105dd  jz      loc_180010758
0x1800105e3  mov     rcx, [r15]; void *
0x1800105e6  test    rcx, rcx
0x1800105e9  jz      short loc_1800105F0
0x1800105eb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800105f0  mov     [r15], r12
0x1800105f3  mov     [r14], ebx
0x1800105f6  mov     r12, [rbp+lpValueName]
0x1800105fa  xor     ebx, ebx
0x1800105fc  mov     [rsi+20h], ebx
0x1800105ff  jmp     loc_1800104E0
0x180010604  mov     rax, r13
0x180010607  jmp     loc_1800104F6
0x18001060c  lea     r15, [rsi+18h]
0x180010610  jmp     loc_1800104BF
0x180010615  mov     dword ptr [rbp+pExceptionObject], eax
0x180010618  lea     rdx, _TI1K; pThrowInfo
0x18001061f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010623  call    _CxxThrowException_0
0x180010629  mov     [rbp+var_30], eax
0x18001062c  lea     rdx, _TI1K; pThrowInfo
0x180010633  lea     rcx, [rbp+var_30]; pExceptionObject
0x180010637  call    _CxxThrowException_0
0x18001063d  sub     eax, 2
0x180010640  jz      short loc_18001066C
0x180010642  sub     eax, 1
0x180010645  jz      loc_180010485
0x18001064b  cmp     eax, 4
0x18001064e  jz      loc_180010485
0x180010654  mov     [rbp+var_30], 0Bh
0x18001065b  lea     rdx, _TI1K; pThrowInfo
0x180010662  lea     rcx, [rbp+var_30]; pExceptionObject
0x180010666  call    _CxxThrowException_0
0x18001066c  xor     r8d, r8d; int
0x18001066f  mov     edx, [rbp+cbData]; unsigned int
0x180010672  lea     rcx, [rbp+var_20]; this
0x180010676  call    ?Presize@CBuffer@@QEAAPEAEKH@Z; CBuffer::Presize(ulong,int)
0x18001067b  lea     r9, [rbp+Type]; unsigned int *
0x18001067f  lea     r8, [rbp+var_20]; struct CBuffer *
0x180010683  mov     rdx, r12; unsigned __int16 *
0x180010686  mov     rcx, rsi; this
0x180010689  call    ?GetValue@CRegistry@@QEAAXPEBGAEAVCBuffer@@PEAK@Z; CRegistry::GetValue(ushort const *,CBuffer &,ulong *)
0x18001068e  lea     r13, WideCharStr
0x180010695  mov     rcx, r13
0x180010698  mov     r12, [rbp+lpSrc]
0x18001069c  mov     r14d, dword ptr [rbp+var_10+4]
0x1800106a0  test    r14d, r14d
0x1800106a3  cmovnz  rcx, r12; lpSrc
0x1800106a7  xor     r8d, r8d; nSize
0x1800106aa  lea     rdx, [rbp+Dst]; lpDst
0x1800106ae  call    cs:__imp_ExpandEnvironmentStringsW
0x1800106b4  mov     edi, eax
0x1800106b6  mov     [rbp+cbData], eax
0x1800106b9  test    eax, eax
0x1800106bb  jnz     short loc_1800106D7
0x1800106bd  call    cs:__imp_GetLastError
0x1800106c3  mov     [rbp+var_30], eax
0x1800106c6  lea     rdx, _TI1K; pThrowInfo
0x1800106cd  lea     rcx, [rbp+var_30]; pExceptionObject
0x1800106d1  call    _CxxThrowException_0
0x1800106d7  xor     r8d, r8d; int
0x1800106da  mov     edx, edi; unsigned int
0x1800106dc  lea     rcx, [rsi+10h]; this
0x1800106e0  call    ?Presize@CBuffer@@QEAAPEAEKH@Z; CBuffer::Presize(ulong,int)
0x1800106e5  mov     [rsi+20h], edi
0x1800106e8  mov     rcx, r13
0x1800106eb  test    r14d, r14d
0x1800106ee  cmovnz  rcx, r12; lpSrc
0x1800106f2  mov     r8d, edi; nSize
0x1800106f5  mov     rdx, rax; lpDst
0x1800106f8  call    cs:__imp_ExpandEnvironmentStringsW
0x1800106fe  mov     [rbp+cbData], eax
0x180010701  test    eax, eax
0x180010703  jnz     short loc_18001071F
0x180010705  call    cs:__imp_GetLastError
0x18001070b  mov     [rbp+var_30], eax
0x18001070e  lea     rdx, _TI1K; pThrowInfo
0x180010715  lea     rcx, [rbp+var_30]; pExceptionObject
0x180010719  call    _CxxThrowException_0
0x18001071f  lea     r14, [rsi+24h]
0x180010723  lea     r15, [rsi+18h]
0x180010727  jmp     loc_180010566
0x18001072c  mov     [rbp+var_30], 0Eh
0x180010733  lea     rdx, _TI1K; pThrowInfo
0x18001073a  lea     rcx, [rbp+var_30]; pExceptionObject
0x18001073e  call    _CxxThrowException_0
0x180010744  mov     dword ptr [rbp+pExceptionObject], eax
0x180010747  lea     rdx, _TI1K; pThrowInfo
0x18001074e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010752  call    _CxxThrowException_0
0x180010758  mov     dword ptr [rbp+pExceptionObject], 0Eh
0x18001075f  lea     rdx, _TI1K; pThrowInfo
0x180010766  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001076a  call    _CxxThrowException_0
0x180010770  mov     dword ptr [rbp+pExceptionObject], 0Eh
0x180010777  lea     rdx, _TI1K; pThrowInfo
0x18001077e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010782  call    _CxxThrowException_0
0x180010788  mov     dword ptr [rbp+pExceptionObject], 0Eh
0x18001078f  lea     rdx, _TI1K; pThrowInfo
0x180010796  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001079a  call    _CxxThrowException_0
```
