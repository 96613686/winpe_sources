# AppxAllUserStore::EnumKeyAndDoActionForAllSubkeys__lambda_2d578b1cd5e47a877bf62ef1cd046595____0

- ea: `0x180030964`
- end: `0x180030b4f`
- name: `AppxAllUserStore::EnumKeyAndDoActionForAllSubkeys__lambda_2d578b1cd5e47a877bf62ef1cd046595____0`
- size: `491`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800158cc`

## callees

- `0x18000ed34`
- `0x180017198`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x180030964`
- `0x18004c98a`
- `0x18004c9d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800309ea`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180030ae5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800309ea`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180030ae5`

## string_xrefs

- `0x180030a7f`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x180030b0f`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x180030a22`: `AdjustPathForSubTree %ls failed, 0x%0x.`

## pseudocode

```c
LSTATUS __fastcall AppxAllUserStore::EnumKeyAndDoActionForAllSubkeys__lambda_2d578b1cd5e47a877bf62ef1cd046595____0(
        HKEY *a1,
        __int64 a2,
        __int64 a3)
{
  LSTATUS result; // eax
  char **v6; // r15
  DWORD v7; // edi
  AppxAllUserStore::Internal *v8; // rsi
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  HKEY v12; // rcx
  int lpReserved; // [rsp+20h] [rbp-E0h]
  int lpReserveda; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcchClass; // [rsp+30h] [rbp-D0h]
  DWORD cchName[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[526]; // [rsp+52h] [rbp-AEh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  cchName[0] = 261;
  Name = 0;
  memset_0(v18, 0, 0x208u);
  result = RegEnumKeyExW(*a1, 0, &Name, cchName, 0, 0, 0, 0);
  if ( result )
  {
LABEL_10:
    if ( result == 259 )
    {
      return 0;
    }
    else if ( result > 0 )
    {
      return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    v6 = *(char ***)(a3 + 8);
    v7 = 0;
    v8 = *(AppxAllUserStore::Internal **)a3;
    while ( 1 )
    {
      v9 = AppxAllUserStore::Internal::AdjustPathForSubTree(v8, &Name, *v6, (unsigned __int64)a1);
      v10 = v9;
      if ( v9 >= 0 )
      {
        v10 = 0;
      }
      else
      {
        v11 = AppxAllUserStore::BasicLogFile::WriteMsg(
                v8,
                L"AdjustPathForSubTree %ls failed, 0x%0x.",
                &Name,
                (unsigned int)v9);
        if ( v11 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x6A6,
            (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)(unsigned int)v11);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6A6,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)v10,
          lpReserved);
      }
      LODWORD(lpcchClass) = v10;
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x14C,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
        (const char *)v10,
        (__int64)"Failed performing action on key %ws: %X",
        (const char *)&Name,
        lpcchClass);
      if ( (v10 & 0x80000000) != 0 )
        break;
      v12 = *a1;
      ++v7;
      cchName[0] = 261;
      result = RegEnumKeyExW(v12, v7, &Name, cchName, 0, 0, 0, 0);
      if ( result )
        goto LABEL_10;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14E,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
      (const char *)v10,
      lpReserveda);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x180030964  mov     [rsp-8+arg_8], rbx
0x180030969  push    rbp
0x18003096a  push    rsi
0x18003096b  push    rdi
0x18003096c  push    r14
0x18003096e  push    r15
0x180030970  lea     rbp, [rsp-170h]
0x180030978  sub     rsp, 270h
0x18003097f  mov     rax, cs:__security_cookie
0x180030986  xor     rax, rsp
0x180030989  mov     [rbp+190h+var_30], rax
0x180030990  mov     rbx, r8
0x180030993  mov     [rsp+290h+cchName], 105h
0x18003099b  mov     r14, rcx
0x18003099e  xor     eax, eax
0x1800309a0  mov     r8d, 208h; Size
0x1800309a6  mov     [rsp+290h+Name], ax
0x1800309ab  lea     rcx, [rsp+290h+var_23E]; void *
0x1800309b0  xor     edx, edx; Val
0x1800309b2  call    memset_0
0x1800309b7  mov     rcx, [r14]; hKey
0x1800309ba  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800309bf  mov     [rsp+290h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800309c8  lea     r8, [rsp+290h+Name]; lpName
0x1800309cd  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x1800309d6  xor     edx, edx; dwIndex
0x1800309d8  mov     [rsp+290h+lpClass], 0; lpClass
0x1800309e1  mov     [rsp+290h+lpReserved], 0; int
0x1800309ea  call    cs:__imp_RegEnumKeyExW
0x1800309f0  test    eax, eax
0x1800309f2  jnz     loc_180030AF3
0x1800309f8  mov     r15, [rbx+8]
0x1800309fc  xor     edi, edi
0x1800309fe  mov     rsi, [rbx]
0x180030a01  mov     r8, [r15]; unsigned __int16 *
0x180030a04  lea     rdx, [rsp+290h+Name]; struct AppxAllUserStore::BasicLogFile *
0x180030a09  mov     r9, r14; unsigned __int16 *
0x180030a0c  mov     rcx, rsi; this
0x180030a0f  call    ?AdjustPathForSubTree@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG1PEAVRegistryKey@Common@@@Z; AppxAllUserStore::Internal::AdjustPathForSubTree(AppxAllUserStore::BasicLogFile &,ushort const *,ushort const *,Common::RegistryKey *)
0x180030a14  mov     ebx, eax
0x180030a16  test    eax, eax
0x180030a18  jns     short loc_180030A6D
0x180030a1a  mov     r9d, eax
0x180030a1d  lea     r8, [rsp+290h+Name]
0x180030a22  lea     rdx, aAdjustpathfors_0; "AdjustPathForSubTree %ls failed, 0x%0x."
0x180030a29  mov     rcx, rsi; this
0x180030a2c  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180030a31  test    eax, eax
0x180030a33  jns     short loc_180030A50
0x180030a35  mov     rcx, [rbp+198h]; this
0x180030a3c  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180030a43  mov     r9d, eax; char *
0x180030a46  mov     edx, 6A6h; void *
0x180030a4b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030a50  mov     rcx, [rbp+198h]; this
0x180030a57  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180030a5e  mov     r9d, ebx; char *
0x180030a61  mov     edx, 6A6h; void *
0x180030a66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030a6b  jmp     short loc_180030A6F
0x180030a6d  xor     ebx, ebx
0x180030a6f  mov     rcx, [rbp+198h]; this
0x180030a76  lea     rax, [rsp+290h+Name]
0x180030a7b  mov     dword ptr [rsp+290h+lpcchClass], ebx
0x180030a7f  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180030a86  mov     [rsp+290h+lpClass], rax; char *
0x180030a8b  mov     r9d, ebx; char *
0x180030a8e  lea     rax, aFailedPerformi; "Failed performing action on key %ws: %X"
0x180030a95  mov     edx, 14Ch; void *
0x180030a9a  mov     [rsp+290h+lpReserved], rax; int
0x180030a9f  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180030aa4  test    ebx, ebx
0x180030aa6  js      short loc_180030B08
0x180030aa8  mov     rcx, [r14]; hKey
0x180030aab  lea     r9, [rsp+290h+cchName]; lpcchName
0x180030ab0  mov     [rsp+290h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180030ab9  lea     r8, [rsp+290h+Name]; lpName
0x180030abe  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180030ac7  inc     edi
0x180030ac9  mov     [rsp+290h+lpClass], 0; lpClass
0x180030ad2  mov     edx, edi; dwIndex
0x180030ad4  mov     [rsp+290h+lpReserved], 0; lpReserved
0x180030add  mov     [rsp+290h+cchName], 105h
0x180030ae5  call    cs:__imp_RegEnumKeyExW
0x180030aeb  test    eax, eax
0x180030aed  jz      loc_180030A01
0x180030af3  cmp     eax, 103h
0x180030af8  jz      short loc_180030B27
0x180030afa  test    eax, eax
0x180030afc  jle     short loc_180030B29
0x180030afe  movzx   eax, ax
0x180030b01  or      eax, 80070000h
0x180030b06  jmp     short loc_180030B29
0x180030b08  mov     rcx, [rbp+198h]; this
0x180030b0f  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180030b16  mov     r9d, ebx; char *
0x180030b19  mov     edx, 14Eh; void *
0x180030b1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030b23  mov     eax, ebx
0x180030b25  jmp     short loc_180030B29
0x180030b27  xor     eax, eax
0x180030b29  mov     rcx, [rbp+190h+var_30]
0x180030b30  xor     rcx, rsp; StackCookie
0x180030b33  call    __security_check_cookie
0x180030b38  mov     rbx, [rsp+290h+arg_8]
0x180030b40  add     rsp, 270h
0x180030b47  pop     r15
0x180030b49  pop     r14
0x180030b4b  pop     rdi
0x180030b4c  pop     rsi
0x180030b4d  pop     rbp
0x180030b4e  retn
```
