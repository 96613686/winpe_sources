# appv::utility::safe_array_with_structs<ServerPolicyProperties>::create_safe_array(ATL::CComPtr<IRecordInfo> const &,uint,ServerPolicyProperties * &)

- ea: `0x1400390d0`
- end: `0x140039245`
- name: `?create_safe_array@?$safe_array_with_structs@UServerPolicyProperties@@@utility@appv@@QEAA_KAEBV?$CComPtr@UIRecordInfo@@@ATL@@IAEAPEAUServerPolicyProperties@@@Z`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140037088`

## callees

- `0x1400050e0`
- `0x140018bec`
- `0x1400390d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039137`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003918a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400391fb`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039137`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003918a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400391fb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140039172`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140039172`
- `OLEAUT32!__imp_SafeArrayCreateEx` at `0x14003911e`
- `OLEAUT32!__imp_SafeArrayCreateEx` at `0x14003911e`

## pseudocode

```c
__int64 __fastcall appv::utility::safe_array_with_structs<ServerPolicyProperties>::create_safe_array(
        __int64 a1,
        void **a2,
        unsigned int a3,
        void **a4)
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
  __int64 result; // rax
  char *v21; // rax
  const char *v22; // rax
  unsigned __int64 v23; // [rsp+40h] [rbp+8h] BYREF

  v4 = (void **)(a1 + 16);
  v5 = a3;
  if ( *(_QWORD *)(a1 + 16) || *(_QWORD *)(a1 + 8) )
  {
    v21 = strrchr("admin\\AppMan\\AppV\\shared\\include\\safe_array_with_structs.hpp", 92);
    if ( v21 )
      v22 = v21 + 1;
    else
      v22 = "admin\\AppMan\\AppV\\shared\\include\\safe_array_with_structs.hpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v22);
    v13 = 0x30500010001LL;
    goto LABEL_18;
  }
  v8 = *a2;
  v23 = a3;
  v9 = SafeArrayCreateEx(0x24u, 1u, (SAFEARRAYBOUND *)&v23, v8);
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
    memset_0(*v4, 0, 16 * v5);
    *a4 = *v4;
    result = 0x8000000000LL;
    *(_BYTE *)a1 = 1;
    *(_DWORD *)(a1 + 24) = v5;
    return result;
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
0x1400390d0  mov     rax, rsp
0x1400390d3  mov     [rax+10h], rbx
0x1400390d7  mov     [rax+18h], rbp
0x1400390db  push    rsi
0x1400390dc  push    rdi
0x1400390dd  push    r14
0x1400390df  sub     rsp, 20h
0x1400390e3  lea     rdi, [rcx+10h]
0x1400390e7  mov     esi, r8d
0x1400390ea  cmp     qword ptr [rdi], 0
0x1400390ee  mov     r14, r9
0x1400390f1  mov     rbx, rcx
0x1400390f4  jnz     loc_1400391EF
0x1400390fa  cmp     qword ptr [rcx+8], 0
0x1400390ff  jnz     loc_1400391EF
0x140039105  mov     r9, [rdx]; pvExtra
0x140039108  lea     r8, [rax+8]; rgsabound
0x14003910c  mov     ecx, 24h ; '$'; vt
0x140039111  mov     [rax+8], esi
0x140039114  mov     dword ptr [rax+0Ch], 0
0x14003911b  lea     edx, [rcx-23h]; cDims
0x14003911e  call    cs:__imp_SafeArrayCreateEx
0x140039124  mov     [rbx+8], rax
0x140039128  test    rax, rax
0x14003912b  jnz     short loc_14003916C
0x14003912d  lea     edx, [rax+5Ch]; Ch
0x140039130  lea     rcx, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x140039137  call    cs:__imp_strrchr
0x14003913d  test    rax, rax
0x140039140  jz      short loc_140039147
0x140039142  inc     rax
0x140039145  jmp     short loc_14003914E
0x140039147  lea     rax, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14003914e  mov     rdx, rax; char *
0x140039151  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140039158  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14003915d  mov     rcx, 3050001000Eh
0x140039167  jmp     loc_14003922B
0x14003916c  mov     rdx, rdi; ppvData
0x14003916f  mov     rcx, rax; psa
0x140039172  call    cs:__imp_SafeArrayAccessData
0x140039178  mov     ebp, eax
0x14003917a  test    eax, eax
0x14003917c  jns     short loc_1400391C6
0x14003917e  mov     edx, 5Ch ; '\'; Ch
0x140039183  lea     rcx, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14003918a  call    cs:__imp_strrchr
0x140039190  test    rax, rax
0x140039193  jz      short loc_14003919A
0x140039195  inc     rax
0x140039198  jmp     short loc_1400391A1
0x14003919a  lea     rax, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x1400391a1  mov     rdx, rax; char *
0x1400391a4  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400391ab  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400391b0  shl     rax, 34h
0x1400391b4  mov     rcx, 40500010000h
0x1400391be  movzx   edx, bp
0x1400391c1  or      rax, rdx
0x1400391c4  jmp     short loc_14003922F
0x1400391c6  mov     rcx, [rdi]; void *
0x1400391c9  mov     r8, rsi
0x1400391cc  shl     r8, 4; Size
0x1400391d0  xor     edx, edx; Val
0x1400391d2  call    memset_0
0x1400391d7  mov     rax, [rdi]
0x1400391da  mov     [r14], rax
0x1400391dd  mov     rax, 8000000000h
0x1400391e7  mov     byte ptr [rbx], 1
0x1400391ea  mov     [rbx+18h], esi
0x1400391ed  jmp     short loc_140039232
0x1400391ef  mov     edx, 5Ch ; '\'; Ch
0x1400391f4  lea     rcx, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x1400391fb  call    cs:__imp_strrchr
0x140039201  test    rax, rax
0x140039204  jz      short loc_14003920B
0x140039206  inc     rax
0x140039209  jmp     short loc_140039212
0x14003920b  lea     rax, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x140039212  mov     rdx, rax; char *
0x140039215  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14003921c  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140039221  mov     rcx, 30500010001h
0x14003922b  shl     rax, 34h
0x14003922f  or      rax, rcx
0x140039232  mov     rbx, [rsp+38h+arg_8]
0x140039237  mov     rbp, [rsp+38h+arg_10]
0x14003923c  add     rsp, 20h
0x140039240  pop     r14
0x140039242  pop     rdi
0x140039243  pop     rsi
0x140039244  retn
```
