# CRegistry::GetCurrentKeyValue(HKEY__ *,ushort const *,CHString &)

- ea: `0x18000366c`
- end: `0x180003952`
- name: `?GetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHString@@@Z`
- size: `742`
- prototype: `unsigned int(CRegistry *__hidden this, HKEY, const unsigned __int16 *, struct CHString *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002ea4`

## callees

- `0x18000354c`
- `0x180003608`
- `0x18000366c`
- `0x180003b08`
- `0x180003dac`
- `0x180003f28`
- `0x18000c204`
- `0x18000c258`
- `0x1800101cc`
- `0x1800101e4`
- `0x18001ce80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800036c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000372d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800036c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000372d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003767`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003789`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003827`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800038c8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000391a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003767`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003789`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003827`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800038c8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000391a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800036f4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800038e2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800036f4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800038e2`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CRegistry::GetCurrentKeyValue(
        CRegistry *this,
        HKEY a2,
        const unsigned __int16 *a3,
        struct CHString *a4)
{
  unsigned __int64 v7; // rcx
  unsigned __int16 *lpData; // rbx
  DWORD v9; // r14d
  __int64 v10; // rax
  DWORD v12; // edi
  int v13; // r14d
  unsigned __int16 *Buffer; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned __int16 *v17; // r15
  __int64 v18; // rdi
  DWORD i; // r12d
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rdi
  DWORD cbData; // [rsp+30h] [rbp-58h] BYREF
  DWORD Type; // [rsp+34h] [rbp-54h] BYREF
  int pExceptionObject; // [rsp+38h] [rbp-50h] BYREF
  int v25; // [rsp+3Ch] [rbp-4Ch] BYREF
  unsigned __int16 *v26; // [rsp+40h] [rbp-48h]
  unsigned __int16 *v27; // [rsp+48h] [rbp-40h]

  cbData = 0;
  Type = 0;
  CHString::AllocBeforeWrite(a4, 0);
  CHString::Release(a4);
  if ( RegQueryValueExW(a2, a3, 0, &Type, 0, &cbData) )
    return 2147746131LL;
  v7 = cbData;
  if ( !cbData )
    return 2147746131LL;
  if ( Type - 1 <= 1 || Type == 7 )
  {
    v7 = cbData + 2;
    cbData += 2;
  }
  lpData = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(v7);
  v26 = lpData;
  v9 = cbData;
  if ( !lpData )
  {
    pExceptionObject = 0;
    throw (CHeap_Exception *)&pExceptionObject;
  }
  if ( !RegQueryValueExW(a2, a3, 0, &Type, (LPBYTE)lpData, &cbData) )
  {
    switch ( Type )
    {
      case 1u:
      case 2u:
        if ( cbData >= v9 )
          v10 = v9 - 1;
        else
          v10 = cbData;
        *((_BYTE *)lpData + v10) = 0;
        CHString::operator=(a4, lpData);
LABEL_12:
        CWin32DefaultArena::WbemMemFree(lpData);
        return 0;
      case 3u:
        CHString::Empty(a4);
        v12 = cbData & 1;
        v13 = (cbData >> 1) + v12;
        Buffer = CHString::GetBuffer(a4, v13);
        memcpy_0(Buffer, lpData, cbData);
        if ( v12 )
          *(_BYTE *)(cbData + *(_QWORD *)a4) = 0;
        CHString::GetBufferSetLength(a4, v13);
        goto LABEL_12;
      case 4u:
        if ( cbData == 4 )
        {
          v20 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x200u);
          v21 = v20;
          v27 = v20;
          if ( !v20 )
          {
            v25 = 0;
            throw (CHeap_Exception *)&v25;
          }
          try
          {
            StringCchPrintfW(v20, 0x100u, L"%ld", *(unsigned int *)lpData);
            CHString::operator=(a4, v21);
            CWin32DefaultArena::WbemMemFree(v21);
            v27 = 0;
          }
          catch ( CHeap_Exception )
          {
            CWin32DefaultArena::WbemMemFree(v27);
            throw;
          }
          goto LABEL_12;
        }
        break;
      case 7u:
        v15 = v9 - 2;
        if ( cbData >= (unsigned int)v15 )
        {
          *((_BYTE *)lpData + v15) = 0;
          v16 = v9 - 1;
        }
        else
        {
          *((_BYTE *)lpData + cbData) = 0;
          v16 = cbData + 1;
        }
        *((_BYTE *)lpData + v16) = 0;
        v17 = lpData;
        v18 = -1;
        do
          ++v18;
        while ( lpData[v18] );
        for ( i = v18; (_DWORD)v18 && i <= v9; i += v18 )
        {
          CHString::operator+=(a4, v17);
          CHString::operator+=(a4, L"\n");
          v17 += (int)v18 + 1;
          v18 = -1;
          do
            ++v18;
          while ( v17[v18] );
        }
        goto LABEL_12;
    }
  }
  CWin32DefaultArena::WbemMemFree(lpData);
  v26 = 0;
  return 2147746131LL;
}

```

## disassembly

```asm
0x18000366c  push    rbx
0x18000366e  push    rsi
0x18000366f  push    rdi
0x180003670  push    r12
0x180003672  push    r13
0x180003674  push    r14
0x180003676  push    r15
0x180003678  sub     rsp, 50h
0x18000367c  mov     rsi, r9
0x18000367f  mov     rdi, r8
0x180003682  mov     r15, rdx
0x180003685  xor     r13d, r13d
0x180003688  mov     [rsp+88h+cbData], r13d
0x18000368d  mov     [rsp+88h+Type], r13d
0x180003692  xor     edx, edx; int
0x180003694  mov     rcx, r9; this
0x180003697  call    ?AllocBeforeWrite@CHString@@IEAAXH@Z; CHString::AllocBeforeWrite(int)
0x18000369c  mov     rcx, rsi; this
0x18000369f  call    ?Release@CHString@@QEAAXXZ; CHString::Release(void)
0x1800036a4  lea     rax, [rsp+88h+cbData]
0x1800036a9  mov     [rsp+88h+lpcbData], rax; lpcbData
0x1800036ae  mov     [rsp+88h+lpData], r13; lpData
0x1800036b3  lea     r9, [rsp+88h+Type]; lpType
0x1800036b8  xor     r8d, r8d; lpReserved
0x1800036bb  mov     rdx, rdi; lpValueName
0x1800036be  mov     rcx, r15; hKey
0x1800036c1  call    cs:__imp_RegQueryValueExW
0x1800036c7  test    eax, eax
0x1800036c9  jnz     loc_18000377F
0x1800036cf  mov     ecx, [rsp+88h+cbData]
0x1800036d3  test    ecx, ecx
0x1800036d5  jz      loc_18000377F
0x1800036db  mov     edx, [rsp+88h+Type]
0x1800036df  lea     eax, [rdx-1]
0x1800036e2  cmp     eax, 1
0x1800036e5  jbe     loc_18000379B
0x1800036eb  cmp     edx, 7
0x1800036ee  jz      loc_18000379B
0x1800036f4  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800036fa  mov     rbx, rax
0x1800036fd  mov     [rsp+88h+var_48], rax
0x180003702  mov     r14d, [rsp+88h+cbData]
0x180003707  test    rax, rax
0x18000370a  jz      loc_1800037FF
0x180003710  lea     rax, [rsp+88h+cbData]
0x180003715  mov     [rsp+88h+lpcbData], rax; lpcbData
0x18000371a  mov     [rsp+88h+lpData], rbx; lpData
0x18000371f  lea     r9, [rsp+88h+Type]; lpType
0x180003724  xor     r8d, r8d; lpReserved
0x180003727  mov     rdx, rdi; lpValueName
0x18000372a  mov     rcx, r15; hKey
0x18000372d  call    cs:__imp_RegQueryValueExW
0x180003733  test    eax, eax
0x180003735  jnz     short loc_180003786
0x180003737  mov     eax, [rsp+88h+Type]
0x18000373b  sub     eax, 1
0x18000373e  jz      short loc_180003745
0x180003740  sub     eax, 1
0x180003743  jnz     short loc_1800037A7
0x180003745  cmp     [rsp+88h+cbData], r14d
0x18000374a  jnb     loc_1800037F6
0x180003750  mov     eax, [rsp+88h+cbData]
0x180003754  mov     [rax+rbx], r13b
0x180003758  mov     rdx, rbx; unsigned __int16 *
0x18000375b  mov     rcx, rsi; this
0x18000375e  call    ??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x180003763  nop
0x180003764  mov     rcx, rbx
0x180003767  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000376d  xor     eax, eax
0x18000376f  add     rsp, 50h
0x180003773  pop     r15
0x180003775  pop     r14
0x180003777  pop     r13
0x180003779  pop     r12
0x18000377b  pop     rdi
0x18000377c  pop     rsi
0x18000377d  pop     rbx
0x18000377e  retn
0x18000377f  mov     eax, 80040153h
0x180003784  jmp     short loc_18000376F
0x180003786  mov     rcx, rbx
0x180003789  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000378f  mov     [rsp+88h+var_48], r13
0x180003794  mov     eax, 80040153h
0x180003799  jmp     short loc_18000376F
0x18000379b  add     ecx, 2
0x18000379e  mov     [rsp+88h+cbData], ecx
0x1800037a2  jmp     loc_1800036F4
0x1800037a7  sub     eax, 1
0x1800037aa  jnz     short loc_180003816
0x1800037ac  mov     rcx, rsi; this
0x1800037af  call    ?Empty@CHString@@QEAAXXZ; CHString::Empty(void)
0x1800037b4  mov     eax, [rsp+88h+cbData]
0x1800037b8  mov     edi, eax
0x1800037ba  and     edi, 1
0x1800037bd  shr     eax, 1
0x1800037bf  lea     r14d, [rax+rdi]
0x1800037c3  mov     edx, r14d; int
0x1800037c6  mov     rcx, rsi; this
0x1800037c9  call    ?GetBuffer@CHString@@QEAAPEAGH@Z; CHString::GetBuffer(int)
0x1800037ce  mov     r8d, [rsp+88h+cbData]; Size
0x1800037d3  mov     rdx, rbx; Src
0x1800037d6  mov     rcx, rax; void *
0x1800037d9  call    memcpy_0
0x1800037de  test    edi, edi
0x1800037e0  jnz     loc_180003940
0x1800037e6  mov     edx, r14d; int
0x1800037e9  mov     rcx, rsi; this
0x1800037ec  call    ?GetBufferSetLength@CHString@@QEAAPEAGH@Z; CHString::GetBufferSetLength(int)
0x1800037f1  jmp     loc_180003764
0x1800037f6  lea     eax, [r14-1]
0x1800037fa  jmp     loc_180003754
0x1800037ff  mov     [rsp+88h+pExceptionObject], r13d
0x180003804  lea     rdx, _TI1?AVCHeap_Exception@@; pThrowInfo
0x18000380b  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180003810  call    _CxxThrowException_0
0x180003816  sub     eax, 1
0x180003819  jz      loc_1800038BE
0x18000381f  cmp     eax, 3
0x180003822  jz      short loc_18000383C
0x180003824  mov     rcx, rbx
0x180003827  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000382d  mov     [rsp+88h+var_48], r13
0x180003832  mov     eax, 80040153h
0x180003837  jmp     loc_18000376F
0x18000383c  lea     eax, [r14-2]
0x180003840  cmp     [rsp+88h+cbData], eax
0x180003844  jnb     short loc_180003856
0x180003846  mov     eax, [rsp+88h+cbData]
0x18000384a  mov     [rax+rbx], r13b
0x18000384e  mov     eax, [rsp+88h+cbData]
0x180003852  inc     eax
0x180003854  jmp     short loc_18000385E
0x180003856  mov     [rax+rbx], r13b
0x18000385a  lea     eax, [r14-1]
0x18000385e  mov     [rax+rbx], r13b
0x180003862  mov     r15, rbx
0x180003865  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003869  inc     rdi
0x18000386c  cmp     [rbx+rdi*2], r13w
0x180003871  jnz     short loc_180003869
0x180003873  mov     r12d, edi
0x180003876  test    edi, edi
0x180003878  jz      loc_180003764
0x18000387e  cmp     r12d, r14d
0x180003881  ja      loc_180003764
0x180003887  mov     rdx, r15; unsigned __int16 *
0x18000388a  mov     rcx, rsi; this
0x18000388d  call    ??YCHString@@QEAAAEBV0@PEBG@Z; CHString::operator+=(ushort const *)
0x180003892  lea     rdx, asc_1800274B0; "\n"
0x180003899  mov     rcx, rsi; this
0x18000389c  call    ??YCHString@@QEAAAEBV0@PEBG@Z; CHString::operator+=(ushort const *)
0x1800038a1  lea     eax, [rdi+1]
0x1800038a4  movsxd  rcx, eax
0x1800038a7  lea     r15, [r15+rcx*2]
0x1800038ab  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800038af  inc     rdi
0x1800038b2  cmp     [r15+rdi*2], r13w
0x1800038b7  jnz     short loc_1800038AF
0x1800038b9  add     r12d, edi
0x1800038bc  jmp     short loc_180003876
0x1800038be  cmp     [rsp+88h+cbData], 4
0x1800038c3  jz      short loc_1800038DD
0x1800038c5  mov     rcx, rbx
0x1800038c8  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800038ce  mov     [rsp+88h+var_48], r13
0x1800038d3  mov     eax, 80040153h
0x1800038d8  jmp     loc_18000376F
0x1800038dd  mov     ecx, 200h
0x1800038e2  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800038e8  mov     rdi, rax
0x1800038eb  mov     [rsp+88h+var_40], rax
0x1800038f0  test    rax, rax
0x1800038f3  jz      short loc_18000392A
0x1800038f5  mov     r9d, [rbx]
0x1800038f8  lea     r8, aLd; "%ld"
0x1800038ff  mov     edx, 100h; unsigned __int64
0x180003904  mov     rcx, rax; unsigned __int16 *
0x180003907  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000390c  mov     rdx, rdi; unsigned __int16 *
0x18000390f  mov     rcx, rsi; this
0x180003912  call    ??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x180003917  mov     rcx, rdi
0x18000391a  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180003920  mov     [rsp+88h+var_40], r13
0x180003925  jmp     loc_180003764
0x18000392a  mov     [rsp+88h+var_4C], r13d
0x18000392f  lea     rdx, _TI1?AVCHeap_Exception@@; pThrowInfo
0x180003936  lea     rcx, [rsp+88h+var_4C]; pExceptionObject
0x18000393b  call    _CxxThrowException_0
0x180003940  mov     ecx, [rsp+88h+cbData]
0x180003944  mov     rax, [rsi]
0x180003947  mov     [rcx+rax], r13b
0x18000394b  jmp     loc_1800037E6
```
