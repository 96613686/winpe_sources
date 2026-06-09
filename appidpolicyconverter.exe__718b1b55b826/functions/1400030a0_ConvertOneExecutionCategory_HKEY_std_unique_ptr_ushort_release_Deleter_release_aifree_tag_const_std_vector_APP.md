# ConvertOneExecutionCategory(HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<APPID_EXECUTION_CATEGORY_,std::allocator<APPID_EXECUTION_CATEGORY_>> &,std::vector<_GUID,std::allocator<_GUID>> &,ulong &)

- ea: `0x1400030a0`
- end: `0x140003328`
- name: `?ConvertOneExecutionCategory@@YAKPEAUHKEY__@@AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@UAPPID_EXECUTION_CATEGORY_@@V?$allocator@UAPPID_EXECUTION_CATEGORY_@@@std@@@3@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@3@AEAK@Z`
- size: `648`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t **, __int64, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400022ac`

## callees

- `0x1400023d0`
- `0x1400030a0`
- `0x140005ebc`
- `0x140006db4`
- `0x140007040`
- `0x140013aab`
- `0x140013b10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140003240`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140003240`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003124`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400031d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003124`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400031d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003181`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003181`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003146`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003195`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400031f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003254`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003263`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400032dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400032eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400032fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003146`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003195`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400031f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003254`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003263`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400032dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400032eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400032fd`

## pseudocode

```c
__int64 __fastcall ConvertOneExecutionCategory(HKEY hKey, wchar_t **a2, __int64 a3, _QWORD *a4, _DWORD *a5)
{
  unsigned int v9; // ebx
  HKEY v11; // rbx
  unsigned int v12; // edi
  HKEY v13; // rdi
  unsigned int v14; // esi
  __int64 v15; // r8
  DWORD v16; // esi
  DWORD cbData; // [rsp+60h] [rbp-41h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-39h] BYREF
  DWORD Type; // [rsp+70h] [rbp-31h] BYREF
  DWORD cSubKeys; // [rsp+74h] [rbp-2Dh] BYREF
  HKEY hKeya; // [rsp+78h] [rbp-29h] BYREF
  HKEY v22; // [rsp+80h] [rbp-21h] BYREF
  struct _GUID Buf1[2]; // [rsp+88h] [rbp-19h] BYREF

  cbData = 0;
  Type = 0;
  hKeya = 0;
  memset(Buf1, 0, 28);
  if ( !(unsigned int)WSZtoGUID(*a2, Buf1) )
    return 1010;
  phkResult = 0;
  v9 = RegOpenKeyExW(hKey, *a2, 0, 0x20019u, &phkResult);
  std::unique_ptr<HKEY__,release::Deleter<void>>::reset(&hKeya, phkResult);
  if ( v9 )
  {
    if ( hKeya )
      RegCloseKey(hKeya);
    return v9;
  }
  cbData = 4;
  v11 = hKeya;
  v12 = RegQueryValueExW(hKeya, L"Flags", 0, &Type, (LPBYTE)&Buf1[1], &cbData);
  if ( v12 )
    goto LABEL_7;
  if ( Type != 4 || cbData != 4 )
  {
    if ( v11 )
      RegCloseKey(v11);
    return 1010;
  }
  phkResult = 0;
  v22 = 0;
  v12 = RegOpenKeyExW(v11, L"Policies", 0, 0x20019u, &v22);
  std::unique_ptr<HKEY__,release::Deleter<void>>::reset(&phkResult, v22);
  if ( v12 )
  {
    if ( phkResult )
      RegCloseKey(phkResult);
LABEL_7:
    if ( v11 )
      RegCloseKey(v11);
    return v12;
  }
  cSubKeys = 0;
  v13 = phkResult;
  v14 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v14 )
    goto LABEL_16;
  v16 = cSubKeys;
  if ( cSubKeys )
  {
    if ( !*a5 && !memcmp_0(Buf1, qword_1400188A0, 0x10u) )
      *a5 = 1;
    *(_DWORD *)Buf1[1].Data4 = v16;
    *(_DWORD *)&Buf1[1].Data2 = (__int64)(a4[1] - *a4) >> 4;
    v14 = ForEachSubKeyCount<unsigned long (HKEY__ *,std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>> const &,std::vector<_GUID> &),std::vector<_GUID> &>(
            v13,
            v16,
            v15,
            (__int64)a4);
    if ( v14 )
    {
LABEL_16:
      if ( v13 )
        RegCloseKey(v13);
      if ( v11 )
        RegCloseKey(v11);
      return v14;
    }
  }
  else
  {
    *(_QWORD *)&Buf1[1].Data2 = 0;
  }
  std::vector<APPID_EXECUTION_CATEGORY_>::push_back(a3, Buf1);
  if ( v13 )
    RegCloseKey(v13);
  if ( v11 )
    RegCloseKey(v11);
  return 0;
}

```

## disassembly

```asm
0x1400030a0  push    rbp
0x1400030a2  push    rbx
0x1400030a3  push    rsi
0x1400030a4  push    rdi
0x1400030a5  push    r12
0x1400030a7  push    r13
0x1400030a9  push    r14
0x1400030ab  push    r15
0x1400030ad  lea     rbp, [rsp-17h]
0x1400030b2  sub     rsp, 0B8h
0x1400030b9  mov     rax, cs:__security_cookie
0x1400030c0  xor     rax, rsp
0x1400030c3  mov     [rbp+4Fh+var_48], rax
0x1400030c7  mov     r15, r9
0x1400030ca  mov     r12, r8
0x1400030cd  mov     rbx, rdx
0x1400030d0  mov     rdi, rcx
0x1400030d3  mov     r14, [rbp+4Fh+arg_20]
0x1400030d7  xor     r13d, r13d
0x1400030da  mov     [rbp+4Fh+cbData], r13d
0x1400030de  mov     [rbp+4Fh+Type], r13d
0x1400030e2  mov     [rbp+4Fh+hKey], r13
0x1400030e6  xorps   xmm0, xmm0
0x1400030e9  movups  [rbp+4Fh+Buf1], xmm0
0x1400030ed  movups  [rbp+4Fh+Buf1+0Ch], xmm0
0x1400030f1  lea     rdx, [rbp+4Fh+Buf1]; struct _GUID *
0x1400030f5  mov     rcx, [rbx]; Buffer
0x1400030f8  call    ?WSZtoGUID@@YAHPEBGPEAU_GUID@@@Z; WSZtoGUID(ushort const *,_GUID *)
0x1400030fd  test    eax, eax
0x1400030ff  jnz     short loc_140003106
0x140003101  jmp     loc_140003303
0x140003106  mov     [rbp+4Fh+var_88], r13
0x14000310a  lea     rax, [rbp+4Fh+var_88]
0x14000310e  mov     [rsp+0F0h+phkResult], rax; phkResult
0x140003113  mov     esi, 20019h
0x140003118  mov     r9d, esi; samDesired
0x14000311b  xor     r8d, r8d; ulOptions
0x14000311e  mov     rdx, [rbx]; lpSubKey
0x140003121  mov     rcx, rdi; hKey
0x140003124  call    cs:__imp_RegOpenKeyExW
0x14000312a  mov     ebx, eax
0x14000312c  mov     rdx, [rbp+4Fh+var_88]
0x140003130  lea     rcx, [rbp+4Fh+hKey]
0x140003134  call    ?reset@?$unique_ptr@UHKEY__@@U?$Deleter@X@release@@@std@@QEAAXPEAUHKEY__@@@Z; std::unique_ptr<HKEY__,release::Deleter<void>>::reset(HKEY__ *)
0x140003139  test    ebx, ebx
0x14000313b  jz      short loc_140003153
0x14000313d  mov     rcx, [rbp+4Fh+hKey]; hKey
0x140003141  test    rcx, rcx
0x140003144  jz      short loc_14000314C
0x140003146  call    cs:__imp_RegCloseKey
0x14000314c  mov     eax, ebx
0x14000314e  jmp     loc_140003308
0x140003153  mov     [rbp+4Fh+cbData], 4
0x14000315a  lea     rax, [rbp+4Fh+cbData]
0x14000315e  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x140003163  lea     rax, [rbp+4Fh+Data]
0x140003167  mov     [rsp+0F0h+phkResult], rax; lpData
0x14000316c  lea     r9, [rbp+4Fh+Type]; lpType
0x140003170  xor     r8d, r8d; lpReserved
0x140003173  lea     rdx, ValueName; "Flags"
0x14000317a  mov     rbx, [rbp+4Fh+hKey]
0x14000317e  mov     rcx, rbx; hKey
0x140003181  call    cs:__imp_RegQueryValueExW
0x140003187  mov     edi, eax
0x140003189  test    eax, eax
0x14000318b  jz      short loc_1400031A2
0x14000318d  test    rbx, rbx
0x140003190  jz      short loc_14000319B
0x140003192  mov     rcx, rbx; hKey
0x140003195  call    cs:__imp_RegCloseKey
0x14000319b  mov     eax, edi
0x14000319d  jmp     loc_140003308
0x1400031a2  cmp     [rbp+4Fh+Type], 4
0x1400031a6  jnz     loc_1400032F5
0x1400031ac  cmp     [rbp+4Fh+cbData], 4
0x1400031b0  jnz     loc_1400032F5
0x1400031b6  mov     [rbp+4Fh+var_88], r13
0x1400031ba  mov     [rbp+4Fh+var_70], r13
0x1400031be  lea     rax, [rbp+4Fh+var_70]
0x1400031c2  mov     [rsp+0F0h+phkResult], rax; phkResult
0x1400031c7  mov     r9d, esi; samDesired
0x1400031ca  xor     r8d, r8d; ulOptions
0x1400031cd  lea     rdx, SubKey; "Policies"
0x1400031d4  mov     rcx, rbx; hKey
0x1400031d7  call    cs:__imp_RegOpenKeyExW
0x1400031dd  mov     edi, eax
0x1400031df  mov     rdx, [rbp+4Fh+var_70]
0x1400031e3  lea     rcx, [rbp+4Fh+var_88]
0x1400031e7  call    ?reset@?$unique_ptr@UHKEY__@@U?$Deleter@X@release@@@std@@QEAAXPEAUHKEY__@@@Z; std::unique_ptr<HKEY__,release::Deleter<void>>::reset(HKEY__ *)
0x1400031ec  test    edi, edi
0x1400031ee  jz      short loc_140003201
0x1400031f0  mov     rcx, [rbp+4Fh+var_88]; hKey
0x1400031f4  test    rcx, rcx
0x1400031f7  jz      short loc_14000318D
0x1400031f9  call    cs:__imp_RegCloseKey
0x1400031ff  jmp     short loc_14000318D
0x140003201  mov     [rbp+4Fh+cSubKeys], r13d
0x140003205  mov     [rsp+0F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x14000320a  mov     [rsp+0F0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x14000320f  mov     [rsp+0F0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x140003214  mov     [rsp+0F0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x140003219  mov     [rsp+0F0h+lpcValues], r13; lpcValues
0x14000321e  mov     [rsp+0F0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x140003223  mov     [rsp+0F0h+lpcbData], r13; lpcbMaxSubKeyLen
0x140003228  lea     rax, [rbp+4Fh+cSubKeys]
0x14000322c  mov     [rsp+0F0h+phkResult], rax; lpcSubKeys
0x140003231  xor     r9d, r9d; lpReserved
0x140003234  xor     r8d, r8d; lpcchClass
0x140003237  xor     edx, edx; lpClass
0x140003239  mov     rdi, [rbp+4Fh+var_88]
0x14000323d  mov     rcx, rdi; hKey
0x140003240  call    cs:__imp_RegQueryInfoKeyW
0x140003246  mov     esi, eax
0x140003248  test    eax, eax
0x14000324a  jz      short loc_140003270
0x14000324c  test    rdi, rdi
0x14000324f  jz      short loc_14000325B
0x140003251  mov     rcx, rdi; hKey
0x140003254  call    cs:__imp_RegCloseKey
0x14000325a  nop
0x14000325b  test    rbx, rbx
0x14000325e  jz      short loc_140003269
0x140003260  mov     rcx, rbx; hKey
0x140003263  call    cs:__imp_RegCloseKey
0x140003269  mov     eax, esi
0x14000326b  jmp     loc_140003308
0x140003270  mov     esi, [rbp+4Fh+cSubKeys]
0x140003273  test    esi, esi
0x140003275  jz      short loc_1400032C3
0x140003277  cmp     [r14], r13d
0x14000327a  jnz     short loc_14000329D
0x14000327c  mov     r8d, 10h; Size
0x140003282  lea     rdx, qword_1400188A0; Buf2
0x140003289  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x14000328d  call    memcmp_0
0x140003292  test    eax, eax
0x140003294  jnz     short loc_14000329D
0x140003296  mov     dword ptr [r14], 1
0x14000329d  mov     dword ptr [rbp+4Fh+var_54+4], esi
0x1400032a0  mov     rax, [r15+8]
0x1400032a4  sub     rax, [r15]
0x1400032a7  sar     rax, 4
0x1400032ab  mov     dword ptr [rbp+4Fh+var_54], eax
0x1400032ae  mov     r9, r15
0x1400032b1  mov     edx, esi
0x1400032b3  mov     rcx, rdi; hKey
0x1400032b6  call    ??$ForEachSubKeyCount@$$A6AKPEAUHKEY__@@AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@3@@ZAEAV43@@@YAKPEAUHKEY__@@KA6AK0AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@2@@Z2@Z; ForEachSubKeyCount<ulong (HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<_GUID> &),std::vector<_GUID> &>(HKEY__ *,ulong,ulong (&)(HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<_GUID> &),std::vector<_GUID> &)
0x1400032bb  mov     esi, eax
0x1400032bd  test    eax, eax
0x1400032bf  jz      short loc_1400032C7
0x1400032c1  jmp     short loc_14000324C
0x1400032c3  mov     [rbp+4Fh+var_54], r13
0x1400032c7  lea     rdx, [rbp+4Fh+Buf1]
0x1400032cb  mov     rcx, r12
0x1400032ce  call    ?push_back@?$vector@UAPPID_EXECUTION_CATEGORY_@@V?$allocator@UAPPID_EXECUTION_CATEGORY_@@@std@@@std@@QEAAXAEBUAPPID_EXECUTION_CATEGORY_@@@Z; std::vector<APPID_EXECUTION_CATEGORY_>::push_back(APPID_EXECUTION_CATEGORY_ const &)
0x1400032d3  nop
0x1400032d4  test    rdi, rdi
0x1400032d7  jz      short loc_1400032E3
0x1400032d9  mov     rcx, rdi; hKey
0x1400032dc  call    cs:__imp_RegCloseKey
0x1400032e2  nop
0x1400032e3  test    rbx, rbx
0x1400032e6  jz      short loc_1400032F1
0x1400032e8  mov     rcx, rbx; hKey
0x1400032eb  call    cs:__imp_RegCloseKey
0x1400032f1  xor     eax, eax
0x1400032f3  jmp     short loc_140003308
0x1400032f5  test    rbx, rbx
0x1400032f8  jz      short loc_140003303
0x1400032fa  mov     rcx, rbx; hKey
0x1400032fd  call    cs:__imp_RegCloseKey
0x140003303  mov     eax, 3F2h
0x140003308  mov     rcx, [rbp+4Fh+var_48]
0x14000330c  xor     rcx, rsp; StackCookie
0x14000330f  call    __security_check_cookie
0x140003314  add     rsp, 0B8h
0x14000331b  pop     r15
0x14000331d  pop     r14
0x14000331f  pop     r13
0x140003321  pop     r12
0x140003323  pop     rdi
0x140003324  pop     rsi
0x140003325  pop     rbx
0x140003326  pop     rbp
0x140003327  retn
```
