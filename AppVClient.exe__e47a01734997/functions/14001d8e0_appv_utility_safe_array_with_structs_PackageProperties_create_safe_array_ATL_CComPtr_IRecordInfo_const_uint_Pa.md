# appv::utility::safe_array_with_structs<PackageProperties>::create_safe_array(ATL::CComPtr<IRecordInfo> const &,uint,PackageProperties * &)

- ea: `0x14001d8e0`
- end: `0x14001da56`
- name: `?create_safe_array@?$safe_array_with_structs@UPackageProperties@@@utility@appv@@QEAA_KAEBV?$CComPtr@UIRecordInfo@@@ATL@@IAEAPEAUPackageProperties@@@Z`
- size: `374`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001ab08`
- `0x140037360`

## callees

- `0x1400050e0`
- `0x140018bec`
- `0x14001d8e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001d947`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001d99a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001da0c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001d947`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001d99a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001da0c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14001d982`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14001d982`
- `OLEAUT32!__imp_SafeArrayCreateEx` at `0x14001d92e`
- `OLEAUT32!__imp_SafeArrayCreateEx` at `0x14001d92e`

## pseudocode

```c
__int64 __fastcall appv::utility::safe_array_with_structs<PackageProperties>::create_safe_array(
        __int64 a1,
        void **a2,
        unsigned int a3,
        _QWORD *a4)
{
  void **v4; // rdi
  __int64 v5; // rsi
  void *v8; // r9
  SAFEARRAY *v9; // rax
  char *v10; // rax
  const char *v11; // rax
  unsigned __int64 FileId; // rax
  __int64 v13; // rcx
  HRESULT v14; // eax
  unsigned __int16 v15; // bp
  char *v16; // rax
  const char *v17; // rax
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rax
  void *v20; // rax
  char *v22; // rax
  const char *v23; // rax
  unsigned __int64 v24; // [rsp+40h] [rbp+8h] BYREF

  v4 = (void **)(a1 + 16);
  v5 = a3;
  if ( *(_QWORD *)(a1 + 16) || *(_QWORD *)(a1 + 8) )
  {
    v22 = strrchr("admin\\AppMan\\AppV\\shared\\include\\safe_array_with_structs.hpp", 92);
    if ( v22 )
      v23 = v22 + 1;
    else
      v23 = "admin\\AppMan\\AppV\\shared\\include\\safe_array_with_structs.hpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v23);
    v13 = 0x30500010001LL;
    goto LABEL_18;
  }
  v8 = *a2;
  v24 = a3;
  v9 = SafeArrayCreateEx(0x24u, 1u, (SAFEARRAYBOUND *)&v24, v8);
  *(_QWORD *)(a1 + 8) = v9;
  if ( !v9 )
  {
    v10 = strrchr("admin\\AppMan\\AppV\\shared\\include\\safe_array_with_structs.hpp", 92);
    if ( v10 )
      v11 = v10 + 1;
    else
      v11 = "admin\\AppMan\\AppV\\shared\\include\\safe_array_with_structs.hpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v11);
    v13 = 0x3050001000ELL;
LABEL_18:
    v19 = FileId << 52;
    return v13 | v19;
  }
  v14 = SafeArrayAccessData(v9, v4);
  v15 = v14;
  if ( v14 >= 0 )
  {
    memset_0(*v4, 0, 48 * v5);
    v20 = *v4;
    *(_BYTE *)a1 = 1;
    *(_DWORD *)(a1 + 24) = v5;
    *a4 = v20;
    return 0x8000000000LL;
  }
  v16 = strrchr("admin\\AppMan\\AppV\\shared\\include\\safe_array_with_structs.hpp", 92);
  if ( v16 )
    v17 = v16 + 1;
  else
    v17 = "admin\\AppMan\\AppV\\shared\\include\\safe_array_with_structs.hpp";
  v18 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v17);
  v13 = 0x40500010000LL;
  v19 = v15 | (v18 << 52);
  return v13 | v19;
}

```

## disassembly

```asm
0x14001d8e0  mov     rax, rsp
0x14001d8e3  mov     [rax+10h], rbx
0x14001d8e7  mov     [rax+18h], rbp
0x14001d8eb  push    rsi
0x14001d8ec  push    rdi
0x14001d8ed  push    r14
0x14001d8ef  sub     rsp, 20h
0x14001d8f3  lea     rdi, [rcx+10h]
0x14001d8f7  mov     esi, r8d
0x14001d8fa  cmp     qword ptr [rdi], 0
0x14001d8fe  mov     r14, r9
0x14001d901  mov     rbx, rcx
0x14001d904  jnz     loc_14001DA00
0x14001d90a  cmp     qword ptr [rcx+8], 0
0x14001d90f  jnz     loc_14001DA00
0x14001d915  mov     r9, [rdx]; pvExtra
0x14001d918  lea     r8, [rax+8]; rgsabound
0x14001d91c  mov     ecx, 24h ; '$'; vt
0x14001d921  mov     [rax+8], esi
0x14001d924  mov     dword ptr [rax+0Ch], 0
0x14001d92b  lea     edx, [rcx-23h]; cDims
0x14001d92e  call    cs:__imp_SafeArrayCreateEx
0x14001d934  mov     [rbx+8], rax
0x14001d938  test    rax, rax
0x14001d93b  jnz     short loc_14001D97C
0x14001d93d  lea     edx, [rax+5Ch]; Ch
0x14001d940  lea     rcx, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14001d947  call    cs:__imp_strrchr
0x14001d94d  test    rax, rax
0x14001d950  jz      short loc_14001D957
0x14001d952  inc     rax
0x14001d955  jmp     short loc_14001D95E
0x14001d957  lea     rax, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14001d95e  mov     rdx, rax; char *
0x14001d961  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14001d968  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14001d96d  mov     rcx, 3050001000Eh
0x14001d977  jmp     loc_14001DA3C
0x14001d97c  mov     rdx, rdi; ppvData
0x14001d97f  mov     rcx, rax; psa
0x14001d982  call    cs:__imp_SafeArrayAccessData
0x14001d988  mov     ebp, eax
0x14001d98a  test    eax, eax
0x14001d98c  jns     short loc_14001D9D6
0x14001d98e  mov     edx, 5Ch ; '\'; Ch
0x14001d993  lea     rcx, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14001d99a  call    cs:__imp_strrchr
0x14001d9a0  test    rax, rax
0x14001d9a3  jz      short loc_14001D9AA
0x14001d9a5  inc     rax
0x14001d9a8  jmp     short loc_14001D9B1
0x14001d9aa  lea     rax, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14001d9b1  mov     rdx, rax; char *
0x14001d9b4  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14001d9bb  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14001d9c0  shl     rax, 34h
0x14001d9c4  mov     rcx, 40500010000h
0x14001d9ce  movzx   edx, bp
0x14001d9d1  or      rax, rdx
0x14001d9d4  jmp     short loc_14001DA40
0x14001d9d6  mov     rcx, [rdi]; void *
0x14001d9d9  lea     r8, [rsi+rsi*2]
0x14001d9dd  shl     r8, 4; Size
0x14001d9e1  xor     edx, edx; Val
0x14001d9e3  call    memset_0
0x14001d9e8  mov     rax, [rdi]
0x14001d9eb  mov     byte ptr [rbx], 1
0x14001d9ee  mov     [rbx+18h], esi
0x14001d9f1  mov     [r14], rax
0x14001d9f4  mov     rax, 8000000000h
0x14001d9fe  jmp     short loc_14001DA43
0x14001da00  mov     edx, 5Ch ; '\'; Ch
0x14001da05  lea     rcx, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14001da0c  call    cs:__imp_strrchr
0x14001da12  test    rax, rax
0x14001da15  jz      short loc_14001DA1C
0x14001da17  inc     rax
0x14001da1a  jmp     short loc_14001DA23
0x14001da1c  lea     rax, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14001da23  mov     rdx, rax; char *
0x14001da26  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14001da2d  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14001da32  mov     rcx, 30500010001h
0x14001da3c  shl     rax, 34h
0x14001da40  or      rax, rcx
0x14001da43  mov     rbx, [rsp+38h+arg_8]
0x14001da48  mov     rbp, [rsp+38h+arg_10]
0x14001da4d  add     rsp, 20h
0x14001da51  pop     r14
0x14001da53  pop     rdi
0x14001da54  pop     rsi
0x14001da55  retn
```
