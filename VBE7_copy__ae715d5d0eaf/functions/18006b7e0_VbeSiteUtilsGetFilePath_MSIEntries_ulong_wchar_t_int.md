# VbeSiteUtilsGetFilePath(MSIEntries,ulong,wchar_t *,int)

- ea: `0x18006b7e0`
- end: `0x18006bb15`
- name: `?VbeSiteUtilsGetFilePath@@YAJW4MSIEntries@@KPEA_WH@Z`
- size: `821`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180014c7c`
- `0x180025778`
- `0x180026678`
- `0x180056aa8`
- `0x18005742c`
- `0x180057538`
- `0x18006bc48`

## callees

- `0x18005aa78`
- `0x18005ab18`
- `0x18006b7e0`
- `0x18006c1e4`
- `0x180378ed0`
- `0x180379078`
- `0x180379244`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!strcpy_s` at `0x18006b9d3`
- `MSVCR100!strcpy_s` at `0x18006b9d3`
- `MSVCR100!wcscat_s` at `0x18006bada`
- `MSVCR100!wcscat_s` at `0x18006bada`
- `MSVCR100!_stricmp` at `0x18006b999`
- `MSVCR100!_stricmp` at `0x18006b999`
- `MSVCR100!strcat_s` at `0x18006b910`
- `MSVCR100!strcat_s` at `0x18006b927`
- `MSVCR100!strcat_s` at `0x18006b910`
- `MSVCR100!strcat_s` at `0x18006b927`
- `MSVCR100!_ultoa_s` at `0x18006b8f9`
- `MSVCR100!_ultoa_s` at `0x18006b9ed`
- `MSVCR100!_ultoa_s` at `0x18006b8f9`
- `MSVCR100!_ultoa_s` at `0x18006b9ed`
- `KERNEL32!GetSystemDirectoryW` at `0x18006baae`
- `KERNEL32!GetSystemDirectoryW` at `0x18006baae`

## string_xrefs

- `0x18006ba4c`: `\riched20.dll`
- `0x18006ba80`: `\usp10.dll`

## pseudocode

```c
__int64 __fastcall VbeSiteUtilsGetFilePath(unsigned int a1, unsigned int a2, wchar_t *a3, int a4)
{
  rsize_t v4; // r15
  unsigned int v5; // edi
  __int64 v9; // r14
  __int64 result; // rax
  unsigned __int64 v11; // rsi
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  const char *p_Value; // rdx
  int v16; // eax
  int v17; // eax
  signed int v18; // ebx
  __int64 v19; // rax
  __int64 i; // rcx
  __int64 v21; // r14
  __int64 v22; // rcx
  UINT SystemDirectoryW; // eax
  const wchar_t *v24; // r8
  unsigned int Value; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v26[6]; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v27[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+58h] [rbp-A8h]
  char v29[2048]; // [rsp+60h] [rbp-A0h] BYREF
  char Source[2048]; // [rsp+860h] [rbp+760h] BYREF
  char Buffer[2048]; // [rsp+1060h] [rbp+F60h] BYREF

  v4 = a4;
  v5 = 0;
  Value = a2;
  if ( a4 < 260 && a3 || a1 > 0xE )
    return 2147500037LL;
  v9 = 3LL * (int)a1;
  result = AskHostForFilePath((const wchar_t *)*(&g_msiData + 3 * (int)a1), a2, a3, a4);
  if ( (int)result >= 0 )
    return result;
  if ( a1 != 11 && a1 != 12 )
  {
    result = LoadMSI(1);
    if ( (int)result < 0 )
      return result;
    v11 = -1;
    v29[0] = 0;
    v12 = *((_DWORD *)&g_msiData + 2 * v9 + 4);
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( !v14 )
        {
          strcpyAfromW(Source, (const wchar_t *)*(&g_msiData + v9));
          _ultoa_s(Value, Buffer, 0x800u, 10);
          strcat_s(Buffer, 0x800u, "\\");
          strcat_s(Buffer, 0x800u, Source);
          v17 = TCOQualifiedComponentState((const char *)*(&g_msiData + v9 + 1), Buffer, v29);
          v18 = (unsigned __int16)v17 | 0x80070000;
          if ( v17 <= 0 )
            v18 = v17;
          if ( v18 < 0 )
            return (unsigned int)v18;
          v19 = -1;
          do
            ++v19;
          while ( v29[v19] );
          for ( i = (int)v19; i > 0; LODWORD(v19) = v19 - 1 )
          {
            if ( v29[i - 1] == 92 )
              break;
            --i;
          }
          v21 = (int)v19;
          if ( _stricmp(&v29[(int)v19], Source) )
          {
            v22 = -1;
            do
              ++v22;
            while ( Source[v22] );
            if ( v21 + v22 >= v4 )
              return (unsigned int)-2147467259;
            strcpy_s(&v29[v21], 2048 - v21, Source);
          }
          goto LABEL_31;
        }
        if ( v14 != 1 )
          return (unsigned int)-2147467259;
        p_Value = "vbeext.olb_6.0";
      }
      else
      {
        _ultoa_s(a2, (char *)&Value, 6u, 10);
        p_Value = (const char *)&Value;
      }
      v16 = TCOQualifiedComponentState((const char *)*(&g_msiData + v9 + 1), p_Value, v29);
    }
    else
    {
      v16 = TCOComponentState((const char *)*(&g_msiData + v9 + 1), v29);
    }
    v18 = (unsigned __int16)v16 | 0x80070000;
    if ( v16 <= 0 )
      v18 = v16;
LABEL_31:
    if ( v18 < 0 )
      return (unsigned int)v18;
    do
      ++v11;
    while ( v29[v11] );
    if ( v11 < v4 )
    {
      strcpyWfromA(a3, v29);
      return (unsigned int)v18;
    }
    return (unsigned int)-2147467259;
  }
  v27[0] = *(_QWORD *)L"\\riched20.dll";
  v27[1] = *(_QWORD *)L"hed20.dll";
  v27[2] = *(_QWORD *)L"0.dll";
  v28 = *(_DWORD *)L"l";
  wcscpy((wchar_t *)v26, L"\\usp10.dll");
  SystemDirectoryW = GetSystemDirectoryW(a3, v4);
  if ( !SystemDirectoryW || SystemDirectoryW >= v4 - 4 )
    return (unsigned int)-2147467259;
  v24 = (const wchar_t *)v27;
  if ( a1 != 11 )
    v24 = (const wchar_t *)v26;
  if ( wcscat_s(a3, v4, v24) )
    return (unsigned int)-2147467259;
  return v5;
}

```

## disassembly

```asm
0x18006b7e0  push    rbp
0x18006b7e2  push    rbx
0x18006b7e3  push    rsi
0x18006b7e4  push    rdi
0x18006b7e5  push    r12
0x18006b7e7  push    r13
0x18006b7e9  push    r14
0x18006b7eb  push    r15
0x18006b7ed  lea     rbp, [rsp-1778h]
0x18006b7f5  mov     eax, 1878h
0x18006b7fa  call    _alloca_probe
0x18006b7ff  sub     rsp, rax
0x18006b802  mov     rax, cs:__security_cookie
0x18006b809  xor     rax, rsp
0x18006b80c  mov     [rbp+17B0h+var_50], rax
0x18006b813  movsxd  r15, r9d
0x18006b816  xor     edi, edi
0x18006b818  mov     r12, r8
0x18006b81b  mov     r13d, edx
0x18006b81e  mov     [rsp+18B0h+Value], edx
0x18006b822  movsxd  rbx, ecx
0x18006b825  cmp     r15d, 104h
0x18006b82c  jge     short loc_18006B837
0x18006b82e  test    r8, r8
0x18006b831  jnz     loc_18006BAED
0x18006b837  cmp     ebx, 0Eh
0x18006b83a  ja      loc_18006BAED
0x18006b840  lea     r14, [rbx+rbx*2]
0x18006b844  lea     rcx, ?g_msiData@@3PAUMSIData@@A; MSIData near * g_msiData
0x18006b84b  mov     r9d, r15d; int
0x18006b84e  mov     rcx, [rcx+r14*8]; wchar_t *
0x18006b852  call    ?AskHostForFilePath@@YAJPEB_WKPEA_WH@Z; AskHostForFilePath(wchar_t const *,ulong,wchar_t *,int)
0x18006b857  test    eax, eax
0x18006b859  jns     loc_18006BAF2
0x18006b85f  cmp     ebx, 0Bh
0x18006b862  jz      loc_18006BA4C
0x18006b868  cmp     ebx, 0Ch
0x18006b86b  jz      loc_18006BA4C
0x18006b871  mov     ecx, 1; int
0x18006b876  call    ?LoadMSI@@YAJH@Z; LoadMSI(int)
0x18006b87b  test    eax, eax
0x18006b87d  js      loc_18006BAF2
0x18006b883  lea     rbx, ?g_msiData@@3PAUMSIData@@A; MSIData near * g_msiData
0x18006b88a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006b88e  mov     [rsp+18B0h+var_1850], dil
0x18006b893  mov     ecx, [rbx+r14*8+10h]
0x18006b898  test    ecx, ecx
0x18006b89a  jz      loc_18006B9FD
0x18006b8a0  dec     ecx
0x18006b8a2  jz      loc_18006B9DB
0x18006b8a8  dec     ecx
0x18006b8aa  jz      short loc_18006B8CF
0x18006b8ac  dec     ecx
0x18006b8ae  jnz     loc_18006BA31
0x18006b8b4  lea     rdx, aVbeextOlb60; "vbeext.olb_6.0"
0x18006b8bb  mov     rcx, [rbx+r14*8+8]; char *
0x18006b8c0  lea     r8, [rsp+18B0h+var_1850]; char *
0x18006b8c5  call    ?TCOQualifiedComponentState@@YAIPEBD0PEAD@Z; TCOQualifiedComponentState(char const *,char const *,char *)
0x18006b8ca  jmp     loc_18006BA0C
0x18006b8cf  mov     rdx, [rbx+r14*8]; wchar_t *
0x18006b8d3  lea     rcx, [rbp+17B0h+Source]; char *
0x18006b8da  call    ?strcpyAfromW@@YAPEADPEADPEB_W@Z; strcpyAfromW(char *,wchar_t const *)
0x18006b8df  mov     ecx, [rsp+18B0h+Value]; Value
0x18006b8e3  mov     r13d, 800h
0x18006b8e9  lea     rdx, [rbp+17B0h+Buffer]; Buffer
0x18006b8f0  mov     r8d, r13d; BufferCount
0x18006b8f3  mov     r9d, 0Ah; Radix
0x18006b8f9  call    cs:__imp__ultoa_s
0x18006b8ff  lea     r8, asc_1803A109C; "\\"
0x18006b906  lea     rcx, [rbp+17B0h+Buffer]; Destination
0x18006b90d  mov     edx, r13d; SizeInBytes
0x18006b910  call    cs:__imp_strcat_s
0x18006b916  lea     r8, [rbp+17B0h+Source]; Source
0x18006b91d  lea     rcx, [rbp+17B0h+Buffer]; Destination
0x18006b924  mov     edx, r13d; SizeInBytes
0x18006b927  call    cs:__imp_strcat_s
0x18006b92d  mov     rcx, [rbx+r14*8+8]; char *
0x18006b932  lea     r8, [rsp+18B0h+var_1850]; char *
0x18006b937  lea     rdx, [rbp+17B0h+Buffer]; char *
0x18006b93e  call    ?TCOQualifiedComponentState@@YAIPEBD0PEAD@Z; TCOQualifiedComponentState(char const *,char const *,char *)
0x18006b943  movzx   ebx, ax
0x18006b946  or      ebx, 80070000h
0x18006b94c  test    eax, eax
0x18006b94e  cmovle  ebx, eax
0x18006b951  test    ebx, ebx
0x18006b953  js      loc_18006BA45
0x18006b959  lea     rcx, [rsp+18B0h+var_1850]
0x18006b95e  mov     rax, rsi
0x18006b961  inc     rax
0x18006b964  cmp     [rcx+rax], dil
0x18006b968  jnz     short loc_18006B961
0x18006b96a  movsxd  rcx, eax
0x18006b96d  test    eax, eax
0x18006b96f  jle     short loc_18006B987
0x18006b971  lea     rdx, [rsp+18B0h+var_1850]
0x18006b976  cmp     byte ptr [rdx+rcx-1], 5Ch ; '\'
0x18006b97b  jz      short loc_18006B987
0x18006b97d  dec     rcx
0x18006b980  dec     eax
0x18006b982  test    rcx, rcx
0x18006b985  jg      short loc_18006B976
0x18006b987  movsxd  r14, eax
0x18006b98a  lea     rcx, [rsp+18B0h+var_1850]
0x18006b98f  lea     rdx, [rbp+17B0h+Source]; String2
0x18006b996  add     rcx, r14; String1
0x18006b999  call    cs:__imp__stricmp
0x18006b99f  test    eax, eax
0x18006b9a1  jz      short loc_18006BA1A
0x18006b9a3  lea     rax, [rbp+17B0h+Source]
0x18006b9aa  mov     rcx, rsi
0x18006b9ad  inc     rcx
0x18006b9b0  cmp     [rax+rcx], dil
0x18006b9b4  jnz     short loc_18006B9AD
0x18006b9b6  add     rcx, r14
0x18006b9b9  cmp     rcx, r15
0x18006b9bc  jnb     short loc_18006BA31
0x18006b9be  sub     r13, r14
0x18006b9c1  lea     rcx, [rsp+18B0h+var_1850]
0x18006b9c6  lea     r8, [rbp+17B0h+Source]; Source
0x18006b9cd  add     rcx, r14; Destination
0x18006b9d0  mov     rdx, r13; SizeInBytes
0x18006b9d3  call    cs:__imp_strcpy_s
0x18006b9d9  jmp     short loc_18006BA1A
0x18006b9db  mov     r9d, 0Ah; Radix
0x18006b9e1  lea     rdx, [rsp+18B0h+Value]; Buffer
0x18006b9e6  mov     ecx, r13d; Value
0x18006b9e9  lea     r8d, [r9-4]; BufferCount
0x18006b9ed  call    cs:__imp__ultoa_s
0x18006b9f3  lea     rdx, [rsp+18B0h+Value]
0x18006b9f8  jmp     loc_18006B8BB
0x18006b9fd  mov     rcx, [rbx+r14*8+8]; char *
0x18006ba02  lea     rdx, [rsp+18B0h+var_1850]; char *
0x18006ba07  call    ?TCOComponentState@@YAIPEBDPEAD@Z; TCOComponentState(char const *,char *)
0x18006ba0c  movzx   ebx, ax
0x18006ba0f  or      ebx, 80070000h
0x18006ba15  test    eax, eax
0x18006ba17  cmovle  ebx, eax
0x18006ba1a  test    ebx, ebx
0x18006ba1c  js      short loc_18006BA45
0x18006ba1e  lea     rax, [rsp+18B0h+var_1850]
0x18006ba23  inc     rsi
0x18006ba26  cmp     [rax+rsi], dil
0x18006ba2a  jnz     short loc_18006BA23
0x18006ba2c  cmp     rsi, r15
0x18006ba2f  jb      short loc_18006BA38
0x18006ba31  mov     ebx, 80004005h
0x18006ba36  jmp     short loc_18006BA45
0x18006ba38  lea     rdx, [rsp+18B0h+var_1850]; char *
0x18006ba3d  mov     rcx, r12; wchar_t *
0x18006ba40  call    ?strcpyWfromA@@YAPEA_WPEA_WPEBD@Z; strcpyWfromA(wchar_t *,char const *)
0x18006ba45  mov     eax, ebx
0x18006ba47  jmp     loc_18006BAF2
0x18006ba4c  mov     rax, qword ptr cs:aRiched20Dll; "\\riched20.dll"
0x18006ba53  mov     edx, r15d; uSize
0x18006ba56  mov     rcx, r12; lpBuffer
0x18006ba59  mov     [rsp+18B0h+var_1870], rax
0x18006ba5e  mov     rax, qword ptr cs:aRiched20Dll+8; "hed20.dll"
0x18006ba65  mov     [rsp+18B0h+var_1868], rax
0x18006ba6a  mov     rax, qword ptr cs:aRiched20Dll+10h; "0.dll"
0x18006ba71  mov     [rsp+18B0h+var_1860], rax
0x18006ba76  mov     eax, dword ptr cs:aRiched20Dll+18h; "l"
0x18006ba7c  mov     [rsp+18B0h+var_1858], eax
0x18006ba80  mov     rax, qword ptr cs:aUsp10Dll_0; "\\usp10.dll"
0x18006ba87  mov     qword ptr [rsp+18B0h+var_1888], rax
0x18006ba8c  mov     rax, qword ptr cs:aUsp10Dll_0+8; "10.dll"
0x18006ba93  mov     qword ptr [rsp+18B0h+var_1888+8], rax
0x18006ba98  mov     eax, dword ptr cs:aUsp10Dll_0+10h; "ll"
0x18006ba9e  mov     [rsp+18B0h+var_1878], eax
0x18006baa2  movzx   eax, word ptr cs:aUsp10Dll_0+14h; ""
0x18006baa9  mov     [rsp+18B0h+var_1874], ax
0x18006baae  call    cs:__imp_GetSystemDirectoryW
0x18006bab4  test    eax, eax
0x18006bab6  jz      short loc_18006BAE4
0x18006bab8  lea     rcx, [r15-4]
0x18006babc  mov     eax, eax
0x18006babe  mov     rdx, r15; SizeInWords
0x18006bac1  cmp     rax, rcx
0x18006bac4  jnb     short loc_18006BAE4
0x18006bac6  lea     rax, [rsp+18B0h+var_1888]
0x18006bacb  lea     r8, [rsp+18B0h+var_1870]
0x18006bad0  cmp     ebx, 0Bh
0x18006bad3  cmovnz  r8, rax; Source
0x18006bad7  mov     rcx, r12; Destination
0x18006bada  call    cs:__imp_wcscat_s
0x18006bae0  test    eax, eax
0x18006bae2  jz      short loc_18006BAE9
0x18006bae4  mov     edi, 80004005h
0x18006bae9  mov     eax, edi
0x18006baeb  jmp     short loc_18006BAF2
0x18006baed  mov     eax, 80004005h
0x18006baf2  mov     rcx, [rbp+17B0h+var_50]
0x18006baf9  xor     rcx, rsp; StackCookie
0x18006bafc  call    __security_check_cookie
0x18006bb01  add     rsp, 1878h
0x18006bb08  pop     r15
0x18006bb0a  pop     r14
0x18006bb0c  pop     r13
0x18006bb0e  pop     r12
0x18006bb10  pop     rdi
0x18006bb11  pop     rsi
0x18006bb12  pop     rbx
0x18006bb13  pop     rbp
0x18006bb14  retn
```
