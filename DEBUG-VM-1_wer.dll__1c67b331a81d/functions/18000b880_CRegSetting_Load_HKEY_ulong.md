# CRegSetting::Load(HKEY__ *,ulong)

- ea: `0x18000b880`
- end: `0x18000bbb6`
- name: `?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z`
- size: `822`
- prototype: `int(CRegSetting *__hidden this, HKEY, unsigned int)`
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000b1f4`
- `0x18000b820`
- `0x18001f7b0`
- `0x18003f1d0`
- `0x18005fb10`
- `0x18007a980`
- `0x18007f868`

## callees

- `0x18000b880`
- `0x18000bc10`
- `0x18002b46c`
- `0x180042918`
- `0x180045128`
- `0x18004975c`
- `0x1800517cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b9ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b9de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b9ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b9de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b973`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000baee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b973`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000baee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b8e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b9bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b9ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b8e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b9bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b9ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b942`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b942`

## pseudocode

```c
__int64 __fastcall CRegSetting::Load(CRegSetting *this, HKEY a2, int a3)
{
  const WCHAR *v7; // rdx
  int v8; // edi
  __int64 v9; // r8
  unsigned int i; // ecx
  __int64 v11; // rax
  int v12; // eax
  int v13; // ecx
  __int64 v14; // rax
  unsigned __int64 v15; // rsi
  __int64 v16; // r15
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  LPVOID lpMem[2]; // [rsp+38h] [rbp-28h] BYREF
  _BYTE v19[24]; // [rsp+48h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
  if ( a2 )
  {
    if ( *((_QWORD *)this + 8) == *((_QWORD *)this + 9) )
    {
      if ( lpMem[0] != v19 )
        HeapFree(g_hWerheap, 0, lpMem[0]);
      return 2149285891LL;
    }
    if ( !*((_BYTE *)this + 1) || *(_BYTE *)this )
      goto LABEL_24;
    v7 = (const WCHAR *)*((_QWORD *)this + 4);
    if ( v7 != *((const WCHAR **)this + 5) )
    {
      if ( RegOpenKeyExW(a2, v7, 0, a3 | 0x20019, &hKey) )
      {
        v8 = -2147467259;
LABEL_14:
        if ( lpMem[0] != v19 )
          HeapFree(g_hWerheap, 0, lpMem[0]);
        if ( hKey )
          RegCloseKey(hKey);
        return (unsigned int)v8;
      }
      a2 = hKey;
    }
    if ( RegQueryValueExW(a2, *((LPCWSTR *)this + 8), 0, &Type, 0, &cbData) )
    {
      v8 = -2147467259;
      goto LABEL_14;
    }
    v9 = cbData;
    if ( Type - 1 <= 1 )
    {
      v9 = cbData + 1;
    }
    else
    {
      if ( Type != 7 )
        goto LABEL_27;
      v9 = cbData + 2;
    }
    cbData = v9;
LABEL_27:
    for ( i = 0; i < 0xB; ++i )
    {
      v11 = 8LL * i;
      if ( *(_DWORD *)((char *)&CRegSetting::s_typeMapping + v11 + 4) == Type )
      {
        v12 = *(_DWORD *)((char *)&CRegSetting::s_typeMapping + v11);
        goto LABEL_31;
      }
    }
    v12 = 9;
LABEL_31:
    v13 = *((_DWORD *)this + 1);
    if ( v13 != v12 && v13 != 9 )
    {
      if ( v13 == 5 )
      {
        if ( v12 != 1 )
        {
LABEL_53:
          v8 = -2147467259;
          goto LABEL_14;
        }
      }
      else if ( v13 == 1 )
      {
        if ( v12 != 5 )
          goto LABEL_53;
      }
      else if ( v13 || v12 != 1 )
      {
        goto LABEL_53;
      }
    }
    *((_DWORD *)this + 1) = v12;
    v14 = *((_QWORD *)this + 1);
    v15 = *((_QWORD *)this + 2) - v14;
    v16 = (unsigned int)v9;
    if ( (unsigned int)v9 > v15 )
    {
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                               (char *)this + 8,
                               (unsigned int)v9,
                               v9,
                               &CRegSetting::s_typeMapping) )
      {
        v8 = -2147024882;
        goto LABEL_14;
      }
      memset_0(*((void **)this + 2), 0, v16 - v15);
      v14 = *((_QWORD *)this + 1);
    }
    *((_QWORD *)this + 2) = v16 + v14;
    if ( RegQueryValueExW(a2, *((LPCWSTR *)this + 8), 0, &Type, *((LPBYTE *)this + 1), &cbData) )
    {
      v8 = -2147467259;
      *((_QWORD *)this + 2) = *((_QWORD *)this + 1);
      goto LABEL_14;
    }
    utl::vector<unsigned char,utl::allocator<unsigned char>>::_Resize<,0>((char *)this + 8, cbData);
    if ( *((_DWORD *)this + 1) == 5 )
    {
      v8 = UtilExpandEnvironmentStrings(*((LPCWSTR *)this + 1));
      if ( v8 < 0 )
        goto LABEL_14;
      cbData = 2 * (((char *)lpMem[1] - (char *)lpMem[0]) >> 1) + 2;
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::assign<unsigned char *,void>(
                               (char *)this + 8,
                               lpMem[0],
                               (char *)lpMem[0] + cbData) )
      {
        v8 = -2147024882;
        goto LABEL_14;
      }
    }
    *(_BYTE *)this = 1;
LABEL_24:
    v8 = 0;
    goto LABEL_14;
  }
  if ( lpMem[0] != v19 )
    HeapFree(g_hWerheap, 0, lpMem[0]);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000b880  push    rbp
0x18000b882  push    rbx
0x18000b883  push    rsi
0x18000b884  push    rdi
0x18000b885  push    r12
0x18000b887  mov     rbp, rsp
0x18000b88a  sub     rsp, 60h
0x18000b88e  xor     r12d, r12d
0x18000b891  mov     rbx, rcx
0x18000b894  lea     rcx, [rbp+lpMem]; void *
0x18000b898  mov     [rbp+hKey], r12
0x18000b89c  mov     [rbp+Type], r12d
0x18000b8a0  mov     esi, r8d
0x18000b8a3  mov     [rbp+cbData], r12d
0x18000b8a7  mov     rdi, rdx
0x18000b8aa  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18000b8af  test    rdi, rdi
0x18000b8b2  jz      loc_18000B9C8
0x18000b8b8  mov     rax, [rbx+48h]
0x18000b8bc  cmp     [rbx+40h], rax
0x18000b8c0  jnz     short loc_18000B8FD
0x18000b8c2  mov     r8, [rbp+lpMem]; lpMem
0x18000b8c6  lea     rax, [rbp+var_18]
0x18000b8ca  cmp     r8, rax
0x18000b8cd  jz      short loc_18000B8DE
0x18000b8cf  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18000b8d6  xor     edx, edx; dwFlags
0x18000b8d8  call    cs:__imp_HeapFree
0x18000b8de  mov     rcx, [rbp+hKey]; hKey
0x18000b8e2  test    rcx, rcx
0x18000b8e5  jz      short loc_18000B8ED
0x18000b8e7  call    cs:__imp_RegCloseKey
0x18000b8ed  mov     eax, 801B8003h
0x18000b8f2  add     rsp, 60h
0x18000b8f6  pop     r12
0x18000b8f8  pop     rdi
0x18000b8f9  pop     rsi
0x18000b8fa  pop     rbx
0x18000b8fb  pop     rbp
0x18000b8fc  retn
0x18000b8fd  mov     [rsp+60h+arg_0], r14
0x18000b905  mov     [rsp+60h+arg_10], r15
0x18000b90d  cmp     [rbx+1], r12b
0x18000b911  jz      loc_18000BA35
0x18000b917  cmp     [rbx], r12b
0x18000b91a  jnz     loc_18000BA35
0x18000b920  mov     rdx, [rbx+20h]; lpSubKey
0x18000b924  cmp     rdx, [rbx+28h]
0x18000b928  jz      short loc_18000B957
0x18000b92a  lea     rax, [rbp+hKey]
0x18000b92e  or      esi, 20019h
0x18000b934  mov     r9d, esi; samDesired
0x18000b937  mov     [rsp+60h+phkResult], rax; phkResult
0x18000b93c  xor     r8d, r8d; ulOptions
0x18000b93f  mov     rcx, rdi; hKey
0x18000b942  call    cs:__imp_RegOpenKeyExW
0x18000b948  test    eax, eax
0x18000b94a  jz      short loc_18000B953
0x18000b94c  mov     edi, 80004005h
0x18000b951  jmp     short loc_18000B986
0x18000b953  mov     rdi, [rbp+hKey]
0x18000b957  mov     rdx, [rbx+40h]; lpValueName
0x18000b95b  lea     rax, [rbp+cbData]
0x18000b95f  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18000b964  lea     r9, [rbp+Type]; lpType
0x18000b968  xor     r8d, r8d; lpReserved
0x18000b96b  mov     [rsp+60h+phkResult], r12; lpData
0x18000b970  mov     rcx, rdi; hKey
0x18000b973  call    cs:__imp_RegQueryValueExW
0x18000b979  test    eax, eax
0x18000b97b  jz      loc_18000BA3D
0x18000b981  mov     edi, 80004005h
0x18000b986  mov     r8, [rbp+lpMem]; lpMem
0x18000b98a  lea     rax, [rbp+var_18]
0x18000b98e  mov     r15, [rsp+60h+arg_10]
0x18000b996  mov     r14, [rsp+60h+arg_0]
0x18000b99e  cmp     r8, rax
0x18000b9a1  jz      short loc_18000B9B2
0x18000b9a3  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18000b9aa  xor     edx, edx; dwFlags
0x18000b9ac  call    cs:__imp_HeapFree
0x18000b9b2  mov     rcx, [rbp+hKey]; hKey
0x18000b9b6  test    rcx, rcx
0x18000b9b9  jz      short loc_18000B9C1
0x18000b9bb  call    cs:__imp_RegCloseKey
0x18000b9c1  mov     eax, edi
0x18000b9c3  jmp     loc_18000B8F2
0x18000b9c8  mov     r8, [rbp+lpMem]; lpMem
0x18000b9cc  lea     rax, [rbp+var_18]
0x18000b9d0  cmp     r8, rax
0x18000b9d3  jz      short loc_18000B9E4
0x18000b9d5  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18000b9dc  xor     edx, edx; dwFlags
0x18000b9de  call    cs:__imp_HeapFree
0x18000b9e4  mov     rcx, [rbp+hKey]; hKey
0x18000b9e8  test    rcx, rcx
0x18000b9eb  jz      short loc_18000B9F3
0x18000b9ed  call    cs:__imp_RegCloseKey
0x18000b9f3  mov     eax, 80070057h
0x18000b9f8  add     rsp, 60h
0x18000b9fc  pop     r12
0x18000b9fe  pop     rdi
0x18000b9ff  pop     rsi
0x18000ba00  pop     rbx
0x18000ba01  pop     rbp
0x18000ba02  retn
0x18000ba03  mov     rdx, [rbp+lpMem]
0x18000ba07  lea     rcx, [rbx+8]
0x18000ba0b  mov     rax, [rbp+var_20]
0x18000ba0f  sub     rax, rdx
0x18000ba12  sar     rax, 1
0x18000ba15  lea     eax, ds:2[rax*2]
0x18000ba1c  mov     r8d, eax
0x18000ba1f  add     r8, rdx
0x18000ba22  mov     [rbp+cbData], eax
0x18000ba25  call    ??$assign@PEAEX@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_NPEAE0@Z; utl::vector<uchar,utl::allocator<uchar>>::assign<uchar *,void>(uchar *,uchar *)
0x18000ba2a  test    al, al
0x18000ba2c  jz      loc_18000BBAC
0x18000ba32  mov     byte ptr [rbx], 1
0x18000ba35  mov     edi, r12d
0x18000ba38  jmp     loc_18000B986
0x18000ba3d  mov     edx, [rbp+Type]
0x18000ba40  mov     r8d, [rbp+cbData]
0x18000ba44  lea     eax, [rdx-1]
0x18000ba47  cmp     eax, 1
0x18000ba4a  jbe     loc_18000BB34
0x18000ba50  cmp     edx, 7
0x18000ba53  jz      loc_18000BB2E
0x18000ba59  mov     ecx, r12d
0x18000ba5c  lea     r9, ?s_typeMapping@CRegSetting@@0QBUDATATYPE_REG_MAPPING@1@B; CRegSetting::DATATYPE_REG_MAPPING const near * const CRegSetting::s_typeMapping
0x18000ba63  cmp     ecx, 0Bh
0x18000ba66  jnb     short loc_18000BAC0
0x18000ba68  mov     eax, ecx
0x18000ba6a  lea     rax, ds:0[rax*8]
0x18000ba72  cmp     [rax+r9+4], edx
0x18000ba77  jnz     short loc_18000BABC
0x18000ba79  mov     eax, [rax+r9]
0x18000ba7d  mov     ecx, [rbx+4]
0x18000ba80  cmp     ecx, eax
0x18000ba82  jnz     loc_18000BB40
0x18000ba88  mov     [rbx+4], eax
0x18000ba8b  mov     rax, [rbx+8]
0x18000ba8f  mov     rsi, [rbx+10h]
0x18000ba93  sub     rsi, rax
0x18000ba96  mov     r15d, r8d
0x18000ba99  cmp     r15, rsi
0x18000ba9c  jbe     short loc_18000BAC7
0x18000ba9e  mov     edx, r15d
0x18000baa1  lea     rcx, [rbx+8]
0x18000baa5  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x18000baaa  test    al, al
0x18000baac  jnz     loc_18000BB80
0x18000bab2  mov     edi, 8007000Eh
0x18000bab7  jmp     loc_18000B986
0x18000babc  inc     ecx
0x18000babe  jmp     short loc_18000BA63
0x18000bac0  mov     eax, 9
0x18000bac5  jmp     short loc_18000BA7D
0x18000bac7  add     rax, r15
0x18000baca  lea     r9, [rbp+Type]; lpType
0x18000bace  mov     [rbx+10h], rax
0x18000bad2  xor     r8d, r8d; lpReserved
0x18000bad5  mov     rdx, [rbx+40h]; lpValueName
0x18000bad9  lea     rax, [rbp+cbData]
0x18000badd  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18000bae2  mov     rcx, rdi; hKey
0x18000bae5  mov     rax, [rbx+8]
0x18000bae9  mov     [rsp+60h+phkResult], rax; lpData
0x18000baee  call    cs:__imp_RegQueryValueExW
0x18000baf4  test    eax, eax
0x18000baf6  jnz     loc_18000BB9A
0x18000bafc  mov     edx, [rbp+cbData]
0x18000baff  lea     rcx, [rbx+8]
0x18000bb03  call    ??$_Resize@$$V$0A@@?$vector@EV?$allocator@E@utl@@@utl@@AEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::_Resize<,0>(unsigned __int64)
0x18000bb08  cmp     dword ptr [rbx+4], 5
0x18000bb0c  jnz     loc_18000BA32
0x18000bb12  mov     rcx, [rbx+8]; lpSrc
0x18000bb16  lea     rdx, [rbp+lpMem]
0x18000bb1a  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18000bb1f  mov     edi, eax
0x18000bb21  test    eax, eax
0x18000bb23  js      loc_18000B986
0x18000bb29  jmp     loc_18000BA03
0x18000bb2e  add     r8d, 2
0x18000bb32  jmp     short loc_18000BB37
0x18000bb34  inc     r8d
0x18000bb37  mov     [rbp+cbData], r8d
0x18000bb3b  jmp     loc_18000BA59
0x18000bb40  cmp     ecx, 9
0x18000bb43  jz      loc_18000BA88
0x18000bb49  cmp     ecx, 5
0x18000bb4c  jnz     short loc_18000BB59
0x18000bb4e  cmp     eax, 1
0x18000bb51  jz      loc_18000BA88
0x18000bb57  jmp     short loc_18000BB76
0x18000bb59  cmp     ecx, 1
0x18000bb5c  jnz     short loc_18000BB69
0x18000bb5e  cmp     eax, 5
0x18000bb61  jz      loc_18000BA88
0x18000bb67  jmp     short loc_18000BB76
0x18000bb69  test    ecx, ecx
0x18000bb6b  jnz     short loc_18000BB76
0x18000bb6d  cmp     eax, 1
0x18000bb70  jz      loc_18000BA88
0x18000bb76  mov     edi, 80004005h
0x18000bb7b  jmp     loc_18000B986
0x18000bb80  mov     rcx, [rbx+10h]; void *
0x18000bb84  mov     r8, r15
0x18000bb87  sub     r8, rsi; Size
0x18000bb8a  xor     edx, edx; Val
0x18000bb8c  call    memset_0
0x18000bb91  mov     rax, [rbx+8]
0x18000bb95  jmp     loc_18000BAC7
0x18000bb9a  mov     rax, [rbx+8]
0x18000bb9e  mov     edi, 80004005h
0x18000bba3  mov     [rbx+10h], rax
0x18000bba7  jmp     loc_18000B986
0x18000bbac  mov     edi, 8007000Eh
0x18000bbb1  jmp     loc_18000B986
```
