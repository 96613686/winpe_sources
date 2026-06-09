# WriteAlias(ulong,_WINMMDRIVERINFO *,ulong,HKEY__ *,ushort *)

- ea: `0x18001961c`
- end: `0x1800197de`
- name: `?WriteAlias@@YAJKPEAU_WINMMDRIVERINFO@@KPEAUHKEY__@@PEAG@Z`
- size: `450`
- prototype: `int(unsigned int, struct _WINMMDRIVERINFO *, unsigned int, HKEY, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018fc0`

## callees

- `0x180010b70`
- `0x180010da8`
- `0x18001961c`
- `0x18001baa0`
- `0x180033464`
- `0x18003e920`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800196d4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180019738`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180019778`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800196d4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180019738`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180019778`

## string_xrefs

- `0x18001967b`: `avcore\audiocore\server\audioendpointbuilder\dll\winmm.cpp`
- `0x1800196eb`: `avcore\audiocore\server\audioendpointbuilder\dll\winmm.cpp`

## pseudocode

```c
__int64 __fastcall WriteAlias(
        unsigned int a1,
        struct _WINMMDRIVERINFO *a2,
        unsigned int a3,
        HKEY a4,
        unsigned __int16 *lpSubKey)
{
  __int64 v7; // r14
  int AliasString; // ebx
  __int64 v9; // rdx
  __int64 v11; // rbx
  __int64 v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // r10
  unsigned int lpData; // [rsp+20h] [rbp-68h]
  __int64 Data; // [rsp+30h] [rbp-58h] BYREF
  int v19; // [rsp+38h] [rbp-50h]
  __int16 v20; // [rsp+3Ch] [rbp-4Ch]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  Data = 0;
  v19 = 0;
  v20 = 0;
  v7 = a3;
  AliasString = GetAliasString(a1, (unsigned __int16 *)&Data, a3, a3);
  if ( AliasString < 0 )
  {
    v9 = 114;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\winmm.cpp",
      (const char *)(unsigned int)AliasString,
      lpData);
    return (unsigned int)AliasString;
  }
  v11 = -1;
  if ( a4 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)&Data + v12) );
    v13 = RegSetKeyValueW(a4, lpSubKey, L"Alias", 1u, &Data, 2 * v12 + 2);
    if ( v13 )
    {
      v14 = 119;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v14,
               (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\winmm.cpp",
               (const char *)v13,
               lpData);
    }
  }
  v15 = -1;
  do
    ++v15;
  while ( lpSubKey[v15] );
  v13 = RegSetKeyValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Drivers32",
          (LPCWSTR)&Data,
          1u,
          lpSubKey,
          2 * v15 + 2);
  if ( v13 )
  {
    v14 = 123;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v14,
             (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\winmm.cpp",
             (const char *)v13,
             lpData);
  }
  do
    ++v11;
  while ( lpSubKey[v11] );
  v13 = RegSetKeyValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\WOW6432Node\\Microsoft\\Windows NT\\CurrentVersion\\Drivers32",
          (LPCWSTR)&Data,
          1u,
          lpSubKey,
          2 * v11 + 2);
  if ( v13 )
  {
    v14 = 125;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v14,
             (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\winmm.cpp",
             (const char *)v13,
             lpData);
  }
  *((_BYTE *)a2 + 522 * v7) = 1;
  AliasString = StringCchCopyW((unsigned __int16 *)a2 + 261 * v7 + 1, 0x104u, lpSubKey);
  if ( AliasString < 0 )
  {
    v9 = 130;
    goto LABEL_3;
  }
  *((_BYTE *)a2 + v16 + 1) = 1;
  return 0;
}

```

## disassembly

```asm
0x18001961c  push    rbx
0x18001961e  push    rbp
0x18001961f  push    rsi
0x180019620  push    rdi
0x180019621  push    r14
0x180019623  push    r15
0x180019625  sub     rsp, 58h
0x180019629  mov     rax, cs:__security_cookie
0x180019630  xor     rax, rsp
0x180019633  mov     [rsp+88h+var_48], rax
0x180019638  mov     rdi, [rsp+88h+lpSubKey]
0x180019640  xor     eax, eax
0x180019642  mov     rbp, r9
0x180019645  mov     [rsp+88h+Data], rax
0x18001964a  mov     rsi, rdx
0x18001964d  mov     [rsp+88h+var_50], eax
0x180019651  mov     r9d, r8d; unsigned int
0x180019654  mov     [rsp+88h+var_4C], ax
0x180019659  lea     rdx, [rsp+88h+Data]; unsigned __int16 *
0x18001965e  mov     r14d, r8d
0x180019661  call    ?GetAliasString@@YAJKPEAGKK@Z; GetAliasString(ulong,ushort *,ulong,ulong)
0x180019666  xor     r15d, r15d
0x180019669  mov     ebx, eax
0x18001966b  test    eax, eax
0x18001966d  jns     short loc_180019691
0x18001966f  lea     edx, [r15+72h]; void *
0x180019673  mov     rcx, [rsp+88h]; this
0x18001967b  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\server\\audioendpoin"...
0x180019682  mov     r9d, ebx; char *
0x180019685  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001968a  mov     eax, ebx
0x18001968c  jmp     loc_1800197C4
0x180019691  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180019695  cmp     rbp, rbx
0x180019698  jz      short loc_1800196FF
0x18001969a  lea     rcx, [rsp+88h+Data]
0x18001969f  mov     rax, rbx
0x1800196a2  inc     rax
0x1800196a5  cmp     [rcx+rax*2], r15w
0x1800196aa  jnz     short loc_1800196A2
0x1800196ac  lea     eax, ds:2[rax*2]
0x1800196b3  mov     r9d, 1; dwType
0x1800196b9  mov     [rsp+88h+cbData], eax; cbData
0x1800196bd  lea     r8, aAlias; "Alias"
0x1800196c4  lea     rax, [rsp+88h+Data]
0x1800196c9  mov     rdx, rdi; lpSubKey
0x1800196cc  mov     rcx, rbp; hKey
0x1800196cf  mov     [rsp+88h+lpData], rax; unsigned int
0x1800196d4  call    cs:__imp_RegSetKeyValueW
0x1800196da  test    eax, eax
0x1800196dc  jz      short loc_1800196FF
0x1800196de  mov     edx, 77h ; 'w'; void *
0x1800196e3  mov     rcx, [rsp+88h]; this
0x1800196eb  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\server\\audioendpoin"...
0x1800196f2  mov     r9d, eax; char *
0x1800196f5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800196fa  jmp     loc_1800197C4
0x1800196ff  mov     rax, rbx
0x180019702  inc     rax
0x180019705  cmp     [rdi+rax*2], r15w
0x18001970a  jnz     short loc_180019702
0x18001970c  lea     eax, ds:2[rax*2]
0x180019713  mov     rbp, 0FFFFFFFF80000002h
0x18001971a  mov     [rsp+88h+cbData], eax; cbData
0x18001971e  lea     r8, [rsp+88h+Data]; lpValueName
0x180019723  mov     rcx, rbp; hKey
0x180019726  mov     [rsp+88h+lpData], rdi; lpData
0x18001972b  mov     r9d, 1; dwType
0x180019731  lea     rdx, ?driver32Path@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180019738  call    cs:__imp_RegSetKeyValueW
0x18001973e  test    eax, eax
0x180019740  jz      short loc_180019749
0x180019742  mov     edx, 7Bh ; '{'
0x180019747  jmp     short loc_1800196E3
0x180019749  inc     rbx
0x18001974c  cmp     [rdi+rbx*2], r15w
0x180019751  jnz     short loc_180019749
0x180019753  lea     eax, ds:2[rbx*2]
0x18001975a  mov     r9d, 1; dwType
0x180019760  mov     [rsp+88h+cbData], eax; cbData
0x180019764  lea     r8, [rsp+88h+Data]; lpValueName
0x180019769  lea     rdx, ?driver32WowPath@@3QBGB; "SOFTWARE\\WOW6432Node\\Microsoft\\Windo"...
0x180019770  mov     [rsp+88h+lpData], rdi; lpData
0x180019775  mov     rcx, rbp; hKey
0x180019778  call    cs:__imp_RegSetKeyValueW
0x18001977e  test    eax, eax
0x180019780  jz      short loc_18001978C
0x180019782  mov     edx, 7Dh ; '}'
0x180019787  jmp     loc_1800196E3
0x18001978c  imul    r10, r14, 20Ah
0x180019793  lea     rcx, [rsi+2]
0x180019797  mov     r8, rdi; unsigned __int16 *
0x18001979a  add     rcx, r10; unsigned __int16 *
0x18001979d  mov     edx, 104h; unsigned __int64
0x1800197a2  mov     byte ptr [r10+rsi], 1
0x1800197a7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800197ac  mov     ebx, eax
0x1800197ae  test    eax, eax
0x1800197b0  jns     short loc_1800197BC
0x1800197b2  mov     edx, 82h
0x1800197b7  jmp     loc_180019673
0x1800197bc  mov     byte ptr [r10+rsi+1], 1
0x1800197c2  xor     eax, eax
0x1800197c4  mov     rcx, [rsp+88h+var_48]
0x1800197c9  xor     rcx, rsp; StackCookie
0x1800197cc  call    __security_check_cookie
0x1800197d1  add     rsp, 58h
0x1800197d5  pop     r15
0x1800197d7  pop     r14
0x1800197d9  pop     rdi
0x1800197da  pop     rsi
0x1800197db  pop     rbp
0x1800197dc  pop     rbx
0x1800197dd  retn
```
