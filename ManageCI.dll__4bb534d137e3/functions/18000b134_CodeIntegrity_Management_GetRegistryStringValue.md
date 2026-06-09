# CodeIntegrity::Management::GetRegistryStringValue

- ea: `0x18000b134`
- end: `0x18000b36d`
- name: `CodeIntegrity::Management::GetRegistryStringValue`
- size: `569`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b878`

## callees

- `0x180002a90`
- `0x180003870`
- `0x180004c7c`
- `0x180007654`
- `0x180007678`
- `0x18000a614`
- `0x18000b134`
- `0x18000c860`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b1ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b25b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b28f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b2e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b2f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b341`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b1ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b25b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b28f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b2e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b2f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b341`
- `ntdll!NtQueryValueKey` at `0x18000b1a4`
- `ntdll!NtQueryValueKey` at `0x18000b2ba`
- `ntdll!NtQueryValueKey` at `0x18000b1a4`
- `ntdll!NtQueryValueKey` at `0x18000b2ba`

## string_xrefs

- `0x18000b1bd`: `onecore\base\ci\management\dll\policymgmt.cpp`
- `0x18000b212`: `onecore\base\ci\management\dll\policymgmt.cpp`
- `0x18000b26e`: `onecore\base\ci\management\dll\policymgmt.cpp`
- `0x18000b2cd`: `onecore\base\ci\management\dll\policymgmt.cpp`

## pseudocode

```c
int __fastcall CodeIntegrity::Management::GetRegistryStringValue(HANDLE KeyHandle, __int64 a2, _OWORD *a3)
{
  NTSTATUS v5; // eax
  void **unique_hlocal; // rax
  HLOCAL v8; // rcx
  char *v9; // rbx
  void **v10; // rax
  HLOCAL v11; // rcx
  HLOCAL v12; // rdi
  NTSTATUS v13; // eax
  __int64 v14; // rdx
  int v15; // esi
  ULONG Length; // [rsp+20h] [rbp-60h]
  ULONG Lengtha; // [rsp+20h] [rbp-60h]
  ULONG ResultLength; // [rsp+30h] [rbp-50h] BYREF
  HLOCAL v19; // [rsp+38h] [rbp-48h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-40h] BYREF
  HLOCAL v21; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 v22[8]; // [rsp+50h] [rbp-30h] BYREF
  __int128 KeyValueInformation; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  ResultLength = 0;
  v19 = 0;
  v21 = 0;
  *(_OWORD *)v22 = 0;
  KeyValueInformation = 0;
  v5 = NtQueryValueKey(
         KeyHandle,
         (PUNICODE_STRING)&ValueName,
         KeyValuePartialInformation,
         &KeyValueInformation,
         0x10u,
         &ResultLength);
  if ( v5 != -2147483643 )
  {
    if ( v5 < 0 )
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x84,
               (unsigned int)"onecore\\base\\ci\\management\\dll\\policymgmt.cpp",
               (const char *)(unsigned int)v5,
               Length);
    return 0;
  }
  unique_hlocal = (void **)wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, ResultLength);
  wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
    &v19,
    unique_hlocal);
  v8 = hMem;
  hMem = 0;
  if ( v8 )
    LocalFree(v8);
  v9 = (char *)v19;
  if ( !v19 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecore\\base\\ci\\management\\dll\\policymgmt.cpp",
      (const char *)0x8007000ELL,
      Length);
    return -2147024882;
  }
  v10 = (void **)wil::make_unique_hlocal_nothrow<unsigned char [0]>(&v19, DWORD2(KeyValueInformation));
  wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
    &v21,
    v10);
  v11 = v19;
  v19 = 0;
  if ( v11 )
    LocalFree(v11);
  v12 = v21;
  if ( !v21 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecore\\base\\ci\\management\\dll\\policymgmt.cpp",
      (const char *)0x8007000ELL,
      Length);
    if ( v9 )
      LocalFree(v9);
    return -2147024882;
  }
  v13 = NtQueryValueKey(
          KeyHandle,
          (PUNICODE_STRING)&ValueName,
          KeyValuePartialInformation,
          v9,
          ResultLength,
          &ResultLength);
  if ( v13 >= 0 )
  {
    memcpy_0(v12, v9 + 12, DWORD2(KeyValueInformation));
    v13 = RtlULongToUShort(DWORD2(KeyValueInformation), v22);
    if ( v13 >= 0 )
    {
      v22[1] = v22[0];
      *(_QWORD *)&v22[4] = v12;
      *a3 = *(_OWORD *)v22;
      if ( v9 )
        LocalFree(v9);
      return 0;
    }
    v14 = 154;
  }
  else
  {
    v14 = 147;
  }
  v15 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\base\\ci\\management\\dll\\policymgmt.cpp",
          (const char *)(unsigned int)v13,
          Lengtha);
  if ( v12 )
    LocalFree(v12);
  if ( v9 )
    LocalFree(v9);
  return v15;
}

```

## disassembly

```asm
0x18000b134  mov     [rsp-18h+arg_8], rbx
0x18000b139  mov     [rsp-18h+arg_18], rsi
0x18000b13e  push    rbp
0x18000b13f  push    rdi
0x18000b140  push    r14
0x18000b142  mov     rbp, rsp
0x18000b145  sub     rsp, 80h
0x18000b14c  mov     rax, cs:__security_cookie
0x18000b153  xor     rax, rsp
0x18000b156  mov     [rbp+var_10], rax
0x18000b15a  xorps   xmm0, xmm0
0x18000b15d  mov     [rbp+var_50], 0
0x18000b164  lea     rax, [rbp+var_50]
0x18000b168  mov     [rbp+var_48], 0
0x18000b170  mov     rsi, r8
0x18000b173  mov     [rsp+80h+ResultLength], rax; ResultLength
0x18000b178  lea     r9, [rbp+KeyValueInformation]; KeyValueInformation
0x18000b17c  mov     [rsp+80h+Length], 10h; int
0x18000b184  mov     r8d, 2; KeyValueInformationClass
0x18000b18a  mov     [rbp+var_38], 0
0x18000b192  lea     rdx, ValueName; ValueName
0x18000b199  mov     r14, rcx
0x18000b19c  movups  xmmword ptr [rbp+var_30], xmm0
0x18000b1a0  movups  [rbp+KeyValueInformation], xmm0
0x18000b1a4  call    cs:__imp_NtQueryValueKey
0x18000b1aa  cmp     eax, 80000005h
0x18000b1af  jz      short loc_18000B1D6
0x18000b1b1  test    eax, eax
0x18000b1b3  jns     loc_18000B347
0x18000b1b9  mov     rcx, [rbp+18h]; this
0x18000b1bd  lea     r8, aOnecoreBaseCiM_3; "onecore\\base\\ci\\management\\dll\\pol"...
0x18000b1c4  mov     r9d, eax; char *
0x18000b1c7  mov     edx, 84h; void *
0x18000b1cc  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000b1d1  jmp     loc_18000B349
0x18000b1d6  mov     edx, [rbp+var_50]
0x18000b1d9  lea     rcx, [rbp+hMem]
0x18000b1dd  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18000b1e2  mov     rdx, rax
0x18000b1e5  lea     rcx, [rbp+var_48]
0x18000b1e9  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &&)
0x18000b1ee  mov     rcx, [rbp+hMem]; hMem
0x18000b1f2  mov     [rbp+hMem], 0
0x18000b1fa  test    rcx, rcx
0x18000b1fd  jz      short loc_18000B205
0x18000b1ff  call    cs:__imp_LocalFree
0x18000b205  mov     rbx, [rbp+var_48]
0x18000b209  test    rbx, rbx
0x18000b20c  jnz     short loc_18000B232
0x18000b20e  mov     rcx, [rbp+18h]; this
0x18000b212  lea     r8, aOnecoreBaseCiM_3; "onecore\\base\\ci\\management\\dll\\pol"...
0x18000b219  mov     edi, 8007000Eh
0x18000b21e  mov     edx, 88h; void *
0x18000b223  mov     r9d, edi; char *
0x18000b226  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b22b  mov     eax, edi
0x18000b22d  jmp     loc_18000B349
0x18000b232  mov     edx, dword ptr [rbp+KeyValueInformation+8]
0x18000b235  lea     rcx, [rbp+var_48]
0x18000b239  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18000b23e  mov     rdx, rax
0x18000b241  lea     rcx, [rbp+var_38]
0x18000b245  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &&)
0x18000b24a  mov     rcx, [rbp+var_48]; hMem
0x18000b24e  mov     [rbp+var_48], 0
0x18000b256  test    rcx, rcx
0x18000b259  jz      short loc_18000B261
0x18000b25b  call    cs:__imp_LocalFree
0x18000b261  mov     rdi, [rbp+var_38]
0x18000b265  test    rdi, rdi
0x18000b268  jnz     short loc_18000B297
0x18000b26a  mov     rcx, [rbp+18h]; this
0x18000b26e  lea     r8, aOnecoreBaseCiM_3; "onecore\\base\\ci\\management\\dll\\pol"...
0x18000b275  mov     edi, 8007000Eh
0x18000b27a  mov     edx, 8Bh; void *
0x18000b27f  mov     r9d, edi; char *
0x18000b282  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b287  test    rbx, rbx
0x18000b28a  jz      short loc_18000B22B
0x18000b28c  mov     rcx, rbx; hMem
0x18000b28f  call    cs:__imp_LocalFree
0x18000b295  jmp     short loc_18000B22B
0x18000b297  mov     eax, [rbp+var_50]
0x18000b29a  lea     rcx, [rbp+var_50]
0x18000b29e  mov     [rsp+80h+ResultLength], rcx; ResultLength
0x18000b2a3  lea     rdx, ValueName; ValueName
0x18000b2aa  mov     rcx, r14; KeyHandle
0x18000b2ad  mov     [rsp+80h+Length], eax; int
0x18000b2b1  mov     r9, rbx; KeyValueInformation
0x18000b2b4  mov     r8d, 2; KeyValueInformationClass
0x18000b2ba  call    cs:__imp_NtQueryValueKey
0x18000b2c0  test    eax, eax
0x18000b2c2  jns     short loc_18000B2FE
0x18000b2c4  mov     edx, 93h; void *
0x18000b2c9  mov     rcx, [rbp+18h]; this
0x18000b2cd  lea     r8, aOnecoreBaseCiM_3; "onecore\\base\\ci\\management\\dll\\pol"...
0x18000b2d4  mov     r9d, eax; char *
0x18000b2d7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000b2dc  mov     esi, eax
0x18000b2de  test    rdi, rdi
0x18000b2e1  jz      short loc_18000B2EC
0x18000b2e3  mov     rcx, rdi; hMem
0x18000b2e6  call    cs:__imp_LocalFree
0x18000b2ec  test    rbx, rbx
0x18000b2ef  jz      short loc_18000B2FA
0x18000b2f1  mov     rcx, rbx; hMem
0x18000b2f4  call    cs:__imp_LocalFree
0x18000b2fa  mov     eax, esi
0x18000b2fc  jmp     short loc_18000B349
0x18000b2fe  mov     r8d, dword ptr [rbp+KeyValueInformation+8]; Size
0x18000b302  lea     rdx, [rbx+0Ch]; Src
0x18000b306  mov     rcx, rdi; void *
0x18000b309  call    memcpy_0
0x18000b30e  mov     ecx, dword ptr [rbp+KeyValueInformation+8]; unsigned int
0x18000b311  lea     rdx, [rbp+var_30]; unsigned __int16 *
0x18000b315  call    ?RtlULongToUShort@@YAJKPEAG@Z; RtlULongToUShort(ulong,ushort *)
0x18000b31a  test    eax, eax
0x18000b31c  jns     short loc_18000B325
0x18000b31e  mov     edx, 9Ah
0x18000b323  jmp     short loc_18000B2C9
0x18000b325  movzx   eax, [rbp+var_30]
0x18000b329  mov     [rbp+var_30+2], ax
0x18000b32d  mov     qword ptr [rbp+var_30+8], rdi
0x18000b331  movups  xmm0, xmmword ptr [rbp+var_30]
0x18000b335  movdqu  xmmword ptr [rsi], xmm0
0x18000b339  test    rbx, rbx
0x18000b33c  jz      short loc_18000B347
0x18000b33e  mov     rcx, rbx; hMem
0x18000b341  call    cs:__imp_LocalFree
0x18000b347  xor     eax, eax
0x18000b349  mov     rcx, [rbp+var_10]
0x18000b34d  xor     rcx, rsp; StackCookie
0x18000b350  call    __security_check_cookie
0x18000b355  lea     r11, [rsp+80h+var_s0]
0x18000b35d  mov     rbx, [r11+28h]
0x18000b361  mov     rsi, [r11+38h]
0x18000b365  mov     rsp, r11
0x18000b368  pop     r14
0x18000b36a  pop     rdi
0x18000b36b  pop     rbp
0x18000b36c  retn
```
