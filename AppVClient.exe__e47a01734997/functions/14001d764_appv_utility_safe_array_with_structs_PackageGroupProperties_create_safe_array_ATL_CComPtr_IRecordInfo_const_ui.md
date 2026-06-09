# appv::utility::safe_array_with_structs<PackageGroupProperties>::create_safe_array(ATL::CComPtr<IRecordInfo> const &,uint,PackageGroupProperties * &)

- ea: `0x14001d764`
- end: `0x14001d8da`
- name: `?create_safe_array@?$safe_array_with_structs@UPackageGroupProperties@@@utility@appv@@QEAA_KAEBV?$CComPtr@UIRecordInfo@@@ATL@@IAEAPEAUPackageGroupProperties@@@Z`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001aa14`

## callees

- `0x1400050e0`
- `0x140018bec`
- `0x14001d764`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001d7cb`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001d81e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001d890`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001d7cb`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001d81e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001d890`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14001d806`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14001d806`
- `OLEAUT32!__imp_SafeArrayCreateEx` at `0x14001d7b2`
- `OLEAUT32!__imp_SafeArrayCreateEx` at `0x14001d7b2`

## pseudocode

```c
__int64 __fastcall appv::utility::safe_array_with_structs<PackageGroupProperties>::create_safe_array(
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
    memset_0(*v4, 0, 40 * v5);
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
0x14001d764  mov     rax, rsp
0x14001d767  mov     [rax+10h], rbx
0x14001d76b  mov     [rax+18h], rbp
0x14001d76f  push    rsi
0x14001d770  push    rdi
0x14001d771  push    r14
0x14001d773  sub     rsp, 20h
0x14001d777  lea     rdi, [rcx+10h]
0x14001d77b  mov     esi, r8d
0x14001d77e  cmp     qword ptr [rdi], 0
0x14001d782  mov     r14, r9
0x14001d785  mov     rbx, rcx
0x14001d788  jnz     loc_14001D884
0x14001d78e  cmp     qword ptr [rcx+8], 0
0x14001d793  jnz     loc_14001D884
0x14001d799  mov     r9, [rdx]; pvExtra
0x14001d79c  lea     r8, [rax+8]; rgsabound
0x14001d7a0  mov     ecx, 24h ; '$'; vt
0x14001d7a5  mov     [rax+8], esi
0x14001d7a8  mov     dword ptr [rax+0Ch], 0
0x14001d7af  lea     edx, [rcx-23h]; cDims
0x14001d7b2  call    cs:__imp_SafeArrayCreateEx
0x14001d7b8  mov     [rbx+8], rax
0x14001d7bc  test    rax, rax
0x14001d7bf  jnz     short loc_14001D800
0x14001d7c1  lea     edx, [rax+5Ch]; Ch
0x14001d7c4  lea     rcx, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14001d7cb  call    cs:__imp_strrchr
0x14001d7d1  test    rax, rax
0x14001d7d4  jz      short loc_14001D7DB
0x14001d7d6  inc     rax
0x14001d7d9  jmp     short loc_14001D7E2
0x14001d7db  lea     rax, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14001d7e2  mov     rdx, rax; char *
0x14001d7e5  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14001d7ec  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14001d7f1  mov     rcx, 3050001000Eh
0x14001d7fb  jmp     loc_14001D8C0
0x14001d800  mov     rdx, rdi; ppvData
0x14001d803  mov     rcx, rax; psa
0x14001d806  call    cs:__imp_SafeArrayAccessData
0x14001d80c  mov     ebp, eax
0x14001d80e  test    eax, eax
0x14001d810  jns     short loc_14001D85A
0x14001d812  mov     edx, 5Ch ; '\'; Ch
0x14001d817  lea     rcx, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14001d81e  call    cs:__imp_strrchr
0x14001d824  test    rax, rax
0x14001d827  jz      short loc_14001D82E
0x14001d829  inc     rax
0x14001d82c  jmp     short loc_14001D835
0x14001d82e  lea     rax, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14001d835  mov     rdx, rax; char *
0x14001d838  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14001d83f  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14001d844  shl     rax, 34h
0x14001d848  mov     rcx, 40500010000h
0x14001d852  movzx   edx, bp
0x14001d855  or      rax, rdx
0x14001d858  jmp     short loc_14001D8C4
0x14001d85a  mov     rcx, [rdi]; void *
0x14001d85d  lea     r8, [rsi+rsi*4]
0x14001d861  shl     r8, 3; Size
0x14001d865  xor     edx, edx; Val
0x14001d867  call    memset_0
0x14001d86c  mov     rax, [rdi]
0x14001d86f  mov     byte ptr [rbx], 1
0x14001d872  mov     [rbx+18h], esi
0x14001d875  mov     [r14], rax
0x14001d878  mov     rax, 8000000000h
0x14001d882  jmp     short loc_14001D8C7
0x14001d884  mov     edx, 5Ch ; '\'; Ch
0x14001d889  lea     rcx, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14001d890  call    cs:__imp_strrchr
0x14001d896  test    rax, rax
0x14001d899  jz      short loc_14001D8A0
0x14001d89b  inc     rax
0x14001d89e  jmp     short loc_14001D8A7
0x14001d8a0  lea     rax, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14001d8a7  mov     rdx, rax; char *
0x14001d8aa  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14001d8b1  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14001d8b6  mov     rcx, 30500010001h
0x14001d8c0  shl     rax, 34h
0x14001d8c4  or      rax, rcx
0x14001d8c7  mov     rbx, [rsp+38h+arg_8]
0x14001d8cc  mov     rbp, [rsp+38h+arg_10]
0x14001d8d1  add     rsp, 20h
0x14001d8d5  pop     r14
0x14001d8d7  pop     rdi
0x14001d8d8  pop     rsi
0x14001d8d9  retn
```
