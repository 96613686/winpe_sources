# appv::utility::safe_array_with_structs<AssetIntelligenceProperties>::create_safe_array(ATL::CComPtr<IRecordInfo> const &,uint,AssetIntelligenceProperties * &)

- ea: `0x140038f54`
- end: `0x1400390ca`
- name: `?create_safe_array@?$safe_array_with_structs@UAssetIntelligenceProperties@@@utility@appv@@QEAA_KAEBV?$CComPtr@UIRecordInfo@@@ATL@@IAEAPEAUAssetIntelligenceProperties@@@Z`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140023108`

## callees

- `0x1400050e0`
- `0x140018bec`
- `0x140038f54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140038fbb`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003900e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039080`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140038fbb`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003900e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039080`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140038ff6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140038ff6`
- `OLEAUT32!__imp_SafeArrayCreateEx` at `0x140038fa2`
- `OLEAUT32!__imp_SafeArrayCreateEx` at `0x140038fa2`

## pseudocode

```c
__int64 __fastcall appv::utility::safe_array_with_structs<AssetIntelligenceProperties>::create_safe_array(
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
    memset_0(*v4, 0, 144 * v5);
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
0x140038f54  mov     rax, rsp
0x140038f57  mov     [rax+10h], rbx
0x140038f5b  mov     [rax+18h], rbp
0x140038f5f  push    rsi
0x140038f60  push    rdi
0x140038f61  push    r14
0x140038f63  sub     rsp, 20h
0x140038f67  lea     rdi, [rcx+10h]
0x140038f6b  mov     esi, r8d
0x140038f6e  cmp     qword ptr [rdi], 0
0x140038f72  mov     r14, r9
0x140038f75  mov     rbx, rcx
0x140038f78  jnz     loc_140039074
0x140038f7e  cmp     qword ptr [rcx+8], 0
0x140038f83  jnz     loc_140039074
0x140038f89  mov     r9, [rdx]; pvExtra
0x140038f8c  lea     r8, [rax+8]; rgsabound
0x140038f90  mov     ecx, 24h ; '$'; vt
0x140038f95  mov     [rax+8], esi
0x140038f98  mov     dword ptr [rax+0Ch], 0
0x140038f9f  lea     edx, [rcx-23h]; cDims
0x140038fa2  call    cs:__imp_SafeArrayCreateEx
0x140038fa8  mov     [rbx+8], rax
0x140038fac  test    rax, rax
0x140038faf  jnz     short loc_140038FF0
0x140038fb1  lea     edx, [rax+5Ch]; Ch
0x140038fb4  lea     rcx, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x140038fbb  call    cs:__imp_strrchr
0x140038fc1  test    rax, rax
0x140038fc4  jz      short loc_140038FCB
0x140038fc6  inc     rax
0x140038fc9  jmp     short loc_140038FD2
0x140038fcb  lea     rax, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x140038fd2  mov     rdx, rax; char *
0x140038fd5  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140038fdc  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140038fe1  mov     rcx, 3050001000Eh
0x140038feb  jmp     loc_1400390B0
0x140038ff0  mov     rdx, rdi; ppvData
0x140038ff3  mov     rcx, rax; psa
0x140038ff6  call    cs:__imp_SafeArrayAccessData
0x140038ffc  mov     ebp, eax
0x140038ffe  test    eax, eax
0x140039000  jns     short loc_14003904A
0x140039002  mov     edx, 5Ch ; '\'; Ch
0x140039007  lea     rcx, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14003900e  call    cs:__imp_strrchr
0x140039014  test    rax, rax
0x140039017  jz      short loc_14003901E
0x140039019  inc     rax
0x14003901c  jmp     short loc_140039025
0x14003901e  lea     rax, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x140039025  mov     rdx, rax; char *
0x140039028  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14003902f  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140039034  shl     rax, 34h
0x140039038  mov     rcx, 40500010000h
0x140039042  movzx   edx, bp
0x140039045  or      rax, rdx
0x140039048  jmp     short loc_1400390B4
0x14003904a  mov     rcx, [rdi]; void *
0x14003904d  lea     r8, [rsi+rsi*8]
0x140039051  shl     r8, 4; Size
0x140039055  xor     edx, edx; Val
0x140039057  call    memset_0
0x14003905c  mov     rax, [rdi]
0x14003905f  mov     byte ptr [rbx], 1
0x140039062  mov     [rbx+18h], esi
0x140039065  mov     [r14], rax
0x140039068  mov     rax, 8000000000h
0x140039072  jmp     short loc_1400390B7
0x140039074  mov     edx, 5Ch ; '\'; Ch
0x140039079  lea     rcx, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x140039080  call    cs:__imp_strrchr
0x140039086  test    rax, rax
0x140039089  jz      short loc_140039090
0x14003908b  inc     rax
0x14003908e  jmp     short loc_140039097
0x140039090  lea     rax, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x140039097  mov     rdx, rax; char *
0x14003909a  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400390a1  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400390a6  mov     rcx, 30500010001h
0x1400390b0  shl     rax, 34h
0x1400390b4  or      rax, rcx
0x1400390b7  mov     rbx, [rsp+38h+arg_8]
0x1400390bc  mov     rbp, [rsp+38h+arg_10]
0x1400390c1  add     rsp, 20h
0x1400390c5  pop     r14
0x1400390c7  pop     rdi
0x1400390c8  pop     rsi
0x1400390c9  retn
```
