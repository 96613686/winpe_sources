# Csl::RegistryKey::GetStringValue(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x18000b3b0`
- end: `0x18000b5aa`
- name: `?GetStringValue@RegistryKey@Csl@@QEBAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `506`
- prototype: `__int64 __fastcall(HKEY *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18001edfc`

## callees

- `0x180002534`
- `0x180003ce4`
- `0x1800045e4`
- `0x180009e10`
- `0x18000b0c0`
- `0x18000b3b0`
- `0x18000b7e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b3fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b49a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b3fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b49a`

## string_xrefs

- `0x18000b426`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x18000b4ef`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x18000b55b`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x18000b598`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::RegistryKey::GetStringValue(HKEY *a1, __int64 a2, __int64 a3)
{
  unsigned int ValueW; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  PVOID v9; // rcx
  unsigned int v10; // ebx
  bool v11; // zf
  const char *v12; // r9
  int pdwType; // [rsp+20h] [rbp-48h]
  PVOID pvData[2]; // [rsp+40h] [rbp-28h] BYREF
  _WORD v15[12]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]
  DWORD pcbData; // [rsp+98h] [rbp+30h] BYREF
  int v18; // [rsp+9Ch] [rbp+34h]

  v18 = HIDWORD(a2);
  pcbData = 0;
  ValueW = RegGetValueW(*a1, 0, L"ContainerId", 2u, 0, 0, &pcbData);
  if ( ValueW == 2 )
    return 2147942402LL;
  if ( ValueW )
    return wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x2DC,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
             (const char *)ValueW,
             (unsigned int)"Failed to query buffer size for string value with name '%ws'",
             (const char *)L"ContainerId");
  pvData[0] = v15;
  pvData[1] = v15;
  v15[0] = 0;
  do
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::resize(
                             pvData,
                             (unsigned __int64)pcbData >> 1) )
    {
      v10 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E8,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
        (const char *)0x8007000ELL,
        pdwType);
      v9 = pvData[0];
      v11 = pvData[0] == v15;
      goto LABEL_18;
    }
    v7 = RegGetValueW(*a1, 0, L"ContainerId", 2u, 0, pvData[0], &pcbData);
  }
  while ( v7 == 234 );
  if ( v7 == 2 )
  {
    if ( pvData[0] != v15 )
      operator delete(pvData[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942402LL;
  }
  if ( v7 )
  {
    v8 = wil::details::in1diag3::Return_Win32Msg(
           retaddr,
           (void *)0x304,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
           (const char *)v7,
           (unsigned int)"Failed to get string value with name '%ws'",
           (const char *)L"ContainerId");
    v9 = pvData[0];
    v10 = v8;
    v11 = pvData[0] == v15;
LABEL_18:
    if ( !v11 )
      operator delete(v9, (const struct std::nothrow_t *)&std::nothrow);
    return v10;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::resize(
                           pvData,
                           (pcbData >> 1) - 1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x312,
      (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
      v12);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    a3,
    (__int64)pvData);
  if ( pvData[0] != v15 )
    operator delete(pvData[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x18000b3b0  mov     r11, rsp
0x18000b3b3  mov     [r11+10h], rdx
0x18000b3b7  push    rbp
0x18000b3b8  push    rbx
0x18000b3b9  push    rdi
0x18000b3ba  push    r15
0x18000b3bc  mov     rbp, rsp
0x18000b3bf  sub     rsp, 68h
0x18000b3c3  lea     rax, [rbp+arg_8]
0x18000b3c7  mov     [rbp+arg_8], 0
0x18000b3ce  mov     [r11-58h], rax
0x18000b3d2  lea     r15, Value; "ContainerId"
0x18000b3d9  mov     rbx, r8
0x18000b3dc  mov     qword ptr [r11-60h], 0
0x18000b3e4  mov     rdi, rcx
0x18000b3e7  mov     qword ptr [r11-68h], 0
0x18000b3ef  mov     rcx, [rcx]; hkey
0x18000b3f2  mov     r9d, 2; dwFlags
0x18000b3f8  mov     r8, r15; lpValue
0x18000b3fb  xor     edx, edx; lpSubKey
0x18000b3fd  call    cs:__imp_RegGetValueW
0x18000b404  nop     dword ptr [rax+rax+00h]
0x18000b409  cmp     eax, 2
0x18000b40c  jz      loc_18000B4CB
0x18000b412  test    eax, eax
0x18000b414  jz      short loc_18000B444
0x18000b416  mov     rcx, [rbp+20h]; this
0x18000b41a  lea     rdx, aFailedToQueryB; "Failed to query buffer size for string "...
0x18000b421  mov     [rsp+68h+pvData], r15; char *
0x18000b426  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000b42d  mov     [rsp+68h+pdwType], rdx; unsigned int
0x18000b432  mov     r9d, eax; char *
0x18000b435  mov     edx, 2DCh; void *
0x18000b43a  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000b43f  jmp     loc_18000B4D0
0x18000b444  lea     rax, [rbp+var_18]
0x18000b448  mov     [rbp+var_28], rax
0x18000b44c  lea     rax, [rbp+var_18]
0x18000b450  mov     [rbp+var_20], rax
0x18000b454  xor     eax, eax
0x18000b456  mov     [rbp+var_18], ax
0x18000b45a  mov     edx, [rbp+arg_8]
0x18000b45d  lea     rcx, [rbp+var_28]
0x18000b461  shr     rdx, 1
0x18000b464  call    ?resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::resize(unsigned __int64,ushort)
0x18000b469  test    al, al
0x18000b46b  jz      loc_18000B557
0x18000b471  mov     rax, [rbp+var_28]
0x18000b475  lea     rcx, [rbp+arg_8]
0x18000b479  mov     [rsp+68h+pcbData], rcx; pcbData
0x18000b47e  mov     r9d, 2; dwFlags
0x18000b484  mov     rcx, [rdi]; hkey
0x18000b487  mov     r8, r15; lpValue
0x18000b48a  mov     [rsp+68h+pvData], rax; pvData
0x18000b48f  xor     edx, edx; lpSubKey
0x18000b491  mov     [rsp+68h+pdwType], 0; pdwType
0x18000b49a  call    cs:__imp_RegGetValueW
0x18000b4a1  nop     dword ptr [rax+rax+00h]
0x18000b4a6  cmp     eax, 0EAh
0x18000b4ab  jz      short loc_18000B45A
0x18000b4ad  cmp     eax, 2
0x18000b4b0  jnz     short loc_18000B4DB
0x18000b4b2  mov     rcx, [rbp+var_28]; void *
0x18000b4b6  lea     rax, [rbp+var_18]
0x18000b4ba  cmp     rcx, rax
0x18000b4bd  jz      short loc_18000B4CB
0x18000b4bf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b4c6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b4cb  mov     eax, 80070002h
0x18000b4d0  add     rsp, 68h
0x18000b4d4  pop     r15
0x18000b4d6  pop     rdi
0x18000b4d7  pop     rbx
0x18000b4d8  pop     rbp
0x18000b4d9  retn
0x18000b4db  test    eax, eax
0x18000b4dd  jz      short loc_18000B517
0x18000b4df  mov     rcx, [rbp+20h]; this
0x18000b4e3  lea     rdx, aFailedToGetStr; "Failed to get string value with name '%"...
0x18000b4ea  mov     [rsp+68h+pvData], r15; char *
0x18000b4ef  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000b4f6  mov     [rsp+68h+pdwType], rdx; unsigned int
0x18000b4fb  mov     r9d, eax; char *
0x18000b4fe  mov     edx, 304h; void *
0x18000b503  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000b508  mov     rcx, [rbp+var_28]
0x18000b50c  mov     ebx, eax
0x18000b50e  lea     rax, [rbp+var_18]
0x18000b512  cmp     rcx, rax
0x18000b515  jmp     short loc_18000B57F
0x18000b517  mov     edx, [rbp+arg_8]
0x18000b51a  lea     rcx, [rbp+var_28]
0x18000b51e  shr     edx, 1
0x18000b520  dec     edx
0x18000b522  call    ?resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::resize(unsigned __int64,ushort)
0x18000b527  test    al, al
0x18000b529  jz      short loc_18000B594
0x18000b52b  lea     rdx, [rbp+var_28]
0x18000b52f  mov     rcx, rbx
0x18000b532  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x18000b537  mov     rcx, [rbp+var_28]; void *
0x18000b53b  lea     rax, [rbp+var_18]
0x18000b53f  cmp     rcx, rax
0x18000b542  jz      short loc_18000B550
0x18000b544  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b54b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b550  xor     eax, eax
0x18000b552  jmp     loc_18000B4D0
0x18000b557  mov     rcx, [rbp+20h]; this
0x18000b55b  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000b562  mov     ebx, 8007000Eh
0x18000b567  mov     edx, 2E8h; void *
0x18000b56c  mov     r9d, ebx; char *
0x18000b56f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b574  mov     rcx, [rbp+var_28]; void *
0x18000b578  lea     rdx, [rbp+var_18]
0x18000b57c  cmp     rcx, rdx
0x18000b57f  jz      short loc_18000B58D
0x18000b581  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b588  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b58d  mov     eax, ebx
0x18000b58f  jmp     loc_18000B4D0
0x18000b594  mov     rcx, [rbp+20h]; this
0x18000b598  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000b59f  mov     edx, 312h; void *
0x18000b5a4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
