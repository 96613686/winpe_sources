# ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6_

- ea: `0x140007e3c`
- end: `0x14000807e`
- name: `ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6___`
- size: `578`
- prototype: `__int64 __fastcall(HKEY hKey, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140008f54`

## callees

- `0x1400064d0`
- `0x140007b38`
- `0x140007e3c`
- `0x1400080e0`
- `0x140008ce4`
- `0x140009490`
- `0x14000a190`
- `0x14000a370`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140008047`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140008047`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000800f`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000800f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140007f4c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140007f4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007f7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007f7e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140007eb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140007eb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007ff1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007ff1`

## string_xrefs

- `0x140008057`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x14000806c`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`

## pseudocode

```c
__int64 __fastcall ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6_(HKEY hKey, __int64 *a2)
{
  unsigned int v4; // eax
  void *v5; // rdx
  DWORD v6; // eax
  DWORD v7; // r8d
  const char *v8; // r9
  DWORD i; // ebx
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r14
  const struct Command *v13; // rax
  __int64 v14; // r15
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-E0h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-E0h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR lpName[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v26; // [rsp+88h] [rbp-78h]
  void *v27[14]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x40,
      (int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
      (const char *)v4,
      lpcSubKeys);
  v5 = (void *)cbMaxSubKeyLen;
  v6 = cbMaxSubKeyLen + 1;
  v7 = -1;
  if ( cbMaxSubKeyLen + 1 >= cbMaxSubKeyLen )
    v7 = cbMaxSubKeyLen + 1;
  v8 = v6 < cbMaxSubKeyLen ? (const char *)0x80070216LL : 0LL;
  cbMaxSubKeyLen = v7;
  if ( v6 < (unsigned int)v5 )
    wil::details::in1diag3::_Throw_Hr(retaddr, v5, v7, v8, lpcSubKeys);
  *(_OWORD *)lpName = 0;
  v26 = 0;
  if ( v7 )
    std::vector<unsigned short>::_Reallocate((__int64)lpName, v7);
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = cbMaxSubKeyLen;
    v10 = RegEnumKeyExW(hKey, i, lpName[0], &cchName, 0, 0, 0, 0);
    if ( v10 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x4C,
        (int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
        (const char *)v10,
        lpcSubKeysa);
    phkResult = 0;
    if ( !RegOpenKeyExW(hKey, lpName[0], 0, 0x20019u, &phkResult) )
    {
      v12 = *a2;
      v13 = (const struct Command *)RegistryConfig::ParseCommand(v11, v27, phkResult, lpName[0]);
      v14 = *(_QWORD *)(v12 + 8);
      v16 = std::_List_buy<Command>::_Buynode<Command>(v15, v14, *(_QWORD *)(v14 + 8), v13);
      v17 = *(_QWORD *)(v12 + 16);
      if ( v17 == 0x1FFFFFFFFFFFFFELL )
        std::_Xlength_error("list<T> too long");
      *(_QWORD *)(v12 + 16) = v17 + 1;
      *(_QWORD *)(v14 + 8) = v16;
      **(_QWORD **)(v16 + 8) = v16;
      Command::~Command(v27);
    }
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  if ( lpName[0] )
    operator delete(lpName[0]);
  return i;
}

```

## disassembly

```asm
0x140007e3c  mov     [rsp-8+arg_10], rbx
0x140007e41  mov     [rsp-8+arg_18], rsi
0x140007e46  push    rbp
0x140007e47  push    r12
0x140007e49  push    r13
0x140007e4b  push    r14
0x140007e4d  push    r15
0x140007e4f  lea     rbp, [rsp-10h]
0x140007e54  sub     rsp, 110h
0x140007e5b  mov     rax, cs:__security_cookie
0x140007e62  xor     rax, rsp
0x140007e65  mov     [rbp+30h+var_30], rax
0x140007e69  mov     r12, rdx
0x140007e6c  mov     rsi, rcx
0x140007e6f  xor     r13d, r13d
0x140007e72  mov     [rsp+130h+cSubKeys], r13d
0x140007e77  mov     [rsp+130h+cbMaxSubKeyLen], r13d
0x140007e7c  mov     [rsp+130h+lpftLastWriteTime], r13; lpftLastWriteTime
0x140007e81  mov     [rsp+130h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x140007e86  mov     [rsp+130h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x140007e8b  mov     [rsp+130h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x140007e90  mov     [rsp+130h+lpcValues], r13; lpcValues
0x140007e95  mov     [rsp+130h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x140007e9a  lea     rax, [rsp+130h+cbMaxSubKeyLen]
0x140007e9f  mov     [rsp+130h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x140007ea4  lea     rax, [rsp+130h+cSubKeys]
0x140007ea9  mov     [rsp+130h+lpcSubKeys], rax; unsigned int
0x140007eae  xor     r9d, r9d; lpReserved
0x140007eb1  xor     r8d, r8d; lpcchClass
0x140007eb4  xor     edx, edx; lpClass
0x140007eb6  call    cs:__imp_RegQueryInfoKeyW
0x140007ebc  mov     rcx, [rbp+38h]; this
0x140007ec0  test    eax, eax
0x140007ec2  jnz     loc_140008069
0x140007ec8  mov     edx, [rsp+130h+cbMaxSubKeyLen]; void *
0x140007ecc  lea     eax, [rdx+1]
0x140007ecf  or      r8d, 0FFFFFFFFh
0x140007ed3  cmp     eax, edx
0x140007ed5  cmovnb  r8d, eax; unsigned int
0x140007ed9  sbb     r9d, r9d
0x140007edc  and     r9d, 80070216h; char *
0x140007ee3  mov     [rsp+130h+cbMaxSubKeyLen], r8d
0x140007ee8  mov     rcx, [rbp+38h]; this
0x140007eec  cmp     eax, edx
0x140007eee  jb      loc_14000804E
0x140007ef4  xorps   xmm0, xmm0
0x140007ef7  movdqu  xmmword ptr [rsp+130h+lpName], xmm0
0x140007efd  mov     [rbp+30h+var_A8], r13
0x140007f01  mov     edx, r8d
0x140007f04  test    r8d, r8d
0x140007f07  jz      short loc_140007F13
0x140007f09  lea     rcx, [rsp+130h+lpName]
0x140007f0e  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x140007f13  mov     ebx, r13d
0x140007f16  cmp     [rsp+130h+cSubKeys], r13d
0x140007f1b  jbe     loc_140008003
0x140007f21  mov     eax, [rsp+130h+cbMaxSubKeyLen]
0x140007f25  mov     [rsp+130h+cchName], eax
0x140007f29  mov     [rsp+130h+lpcValues], r13; lpftLastWriteTime
0x140007f2e  mov     [rsp+130h+lpcbMaxClassLen], r13; lpcchClass
0x140007f33  mov     [rsp+130h+lpcbMaxSubKeyLen], r13; lpClass
0x140007f38  mov     [rsp+130h+lpcSubKeys], r13; unsigned int
0x140007f3d  lea     r9, [rsp+130h+cchName]; lpcchName
0x140007f42  mov     r8, [rsp+130h+lpName]; lpName
0x140007f47  mov     edx, ebx; dwIndex
0x140007f49  mov     rcx, rsi; hKey
0x140007f4c  call    cs:__imp_RegEnumKeyExW
0x140007f52  mov     rcx, [rbp+38h]; this
0x140007f56  test    eax, eax
0x140007f58  jnz     loc_140008054
0x140007f5e  mov     [rsp+130h+phkResult], r13
0x140007f63  lea     rax, [rsp+130h+phkResult]
0x140007f68  mov     [rsp+130h+lpcSubKeys], rax; phkResult
0x140007f6d  mov     r9d, 20019h; samDesired
0x140007f73  xor     r8d, r8d; ulOptions
0x140007f76  mov     rdx, [rsp+130h+lpName]; lpSubKey
0x140007f7b  mov     rcx, rsi; hKey
0x140007f7e  call    cs:__imp_RegOpenKeyExW
0x140007f84  test    eax, eax
0x140007f86  jnz     short loc_140007FE7
0x140007f88  mov     r14, [r12]
0x140007f8c  mov     r9, [rsp+130h+lpName]
0x140007f91  mov     r8, [rsp+130h+phkResult]
0x140007f96  lea     rdx, [rbp+30h+var_A0]
0x140007f9a  call    ?ParseCommand@RegistryConfig@@AEAA?AUCommand@@PEAUHKEY__@@PEBG@Z; RegistryConfig::ParseCommand(HKEY__ *,ushort const *)
0x140007f9f  nop
0x140007fa0  mov     r15, [r14+8]
0x140007fa4  mov     r9, rax
0x140007fa7  mov     r8, [r15+8]
0x140007fab  mov     rdx, r15
0x140007fae  call    ??$_Buynode@UCommand@@@?$_List_buy@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@1@PEAU21@0$$QEAUCommand@@@Z; std::_List_buy<Command>::_Buynode<Command>(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *,Command &&)
0x140007fb3  mov     rdx, [r14+10h]
0x140007fb7  mov     rcx, 1FFFFFFFFFFFFFEh
0x140007fc1  sub     rcx, rdx
0x140007fc4  cmp     rcx, 1
0x140007fc8  jb      short loc_140008040
0x140007fca  lea     rcx, [rdx+1]
0x140007fce  mov     [r14+10h], rcx
0x140007fd2  mov     [r15+8], rax
0x140007fd6  mov     rcx, [rax+8]
0x140007fda  mov     [rcx], rax
0x140007fdd  lea     rcx, [rbp+30h+var_A0]; this
0x140007fe1  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x140007fe6  nop
0x140007fe7  mov     rcx, [rsp+130h+phkResult]; hKey
0x140007fec  test    rcx, rcx
0x140007fef  jz      short loc_140007FF7
0x140007ff1  call    cs:__imp_RegCloseKey
0x140007ff7  inc     ebx
0x140007ff9  cmp     ebx, [rsp+130h+cSubKeys]
0x140007ffd  jb      loc_140007F21
0x140008003  cmp     [rsp+130h+lpName], r13
0x140008008  jz      short loc_140008015
0x14000800a  mov     rcx, [rsp+130h+lpName]
0x14000800f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140008015  mov     eax, ebx
0x140008017  mov     rcx, [rbp+30h+var_30]
0x14000801b  xor     rcx, rsp; StackCookie
0x14000801e  call    __security_check_cookie
0x140008023  lea     r11, [rsp+130h+var_20]
0x14000802b  mov     rbx, [r11+40h]
0x14000802f  mov     rsi, [r11+48h]
0x140008033  mov     rsp, r11
0x140008036  pop     r15
0x140008038  pop     r14
0x14000803a  pop     r13
0x14000803c  pop     r12
0x14000803e  pop     rbp
0x14000803f  retn
0x140008040  lea     rcx, aListTTooLong; "list<T> too long"
0x140008047  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x14000804e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140008054  mov     r9d, eax; char *
0x140008057  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x14000805e  mov     edx, 4Ch ; 'L'; void *
0x140008063  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140008069  mov     r9d, eax; char *
0x14000806c  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x140008073  mov     edx, 40h ; '@'; void *
0x140008078  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
