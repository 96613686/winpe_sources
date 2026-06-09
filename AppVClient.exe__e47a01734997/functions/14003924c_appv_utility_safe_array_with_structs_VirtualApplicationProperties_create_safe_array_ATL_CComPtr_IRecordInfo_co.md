# appv::utility::safe_array_with_structs<VirtualApplicationProperties>::create_safe_array(ATL::CComPtr<IRecordInfo> const &,uint,VirtualApplicationProperties * &)

- ea: `0x14003924c`
- end: `0x1400393be`
- name: `?create_safe_array@?$safe_array_with_structs@UVirtualApplicationProperties@@@utility@appv@@QEAA_KAEBV?$CComPtr@UIRecordInfo@@@ATL@@IAEAPEAUVirtualApplicationProperties@@@Z`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140022c90`

## callees

- `0x1400050e0`
- `0x140018bec`
- `0x14003924c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400392b3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039306`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039374`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400392b3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039306`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140039374`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1400392ee`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1400392ee`
- `OLEAUT32!__imp_SafeArrayCreateEx` at `0x14003929a`
- `OLEAUT32!__imp_SafeArrayCreateEx` at `0x14003929a`

## pseudocode

```c
__int64 __fastcall appv::utility::safe_array_with_structs<VirtualApplicationProperties>::create_safe_array(
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
    memset_0(*v4, 0, 56 * v5);
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
0x14003924c  mov     rax, rsp
0x14003924f  mov     [rax+10h], rbx
0x140039253  mov     [rax+18h], rbp
0x140039257  push    rsi
0x140039258  push    rdi
0x140039259  push    r14
0x14003925b  sub     rsp, 20h
0x14003925f  lea     rdi, [rcx+10h]
0x140039263  mov     esi, r8d
0x140039266  cmp     qword ptr [rdi], 0
0x14003926a  mov     r14, r9
0x14003926d  mov     rbx, rcx
0x140039270  jnz     loc_140039368
0x140039276  cmp     qword ptr [rcx+8], 0
0x14003927b  jnz     loc_140039368
0x140039281  mov     r9, [rdx]; pvExtra
0x140039284  lea     r8, [rax+8]; rgsabound
0x140039288  mov     ecx, 24h ; '$'; vt
0x14003928d  mov     [rax+8], esi
0x140039290  mov     dword ptr [rax+0Ch], 0
0x140039297  lea     edx, [rcx-23h]; cDims
0x14003929a  call    cs:__imp_SafeArrayCreateEx
0x1400392a0  mov     [rbx+8], rax
0x1400392a4  test    rax, rax
0x1400392a7  jnz     short loc_1400392E8
0x1400392a9  lea     edx, [rax+5Ch]; Ch
0x1400392ac  lea     rcx, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x1400392b3  call    cs:__imp_strrchr
0x1400392b9  test    rax, rax
0x1400392bc  jz      short loc_1400392C3
0x1400392be  inc     rax
0x1400392c1  jmp     short loc_1400392CA
0x1400392c3  lea     rax, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x1400392ca  mov     rdx, rax; char *
0x1400392cd  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400392d4  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400392d9  mov     rcx, 3050001000Eh
0x1400392e3  jmp     loc_1400393A4
0x1400392e8  mov     rdx, rdi; ppvData
0x1400392eb  mov     rcx, rax; psa
0x1400392ee  call    cs:__imp_SafeArrayAccessData
0x1400392f4  mov     ebp, eax
0x1400392f6  test    eax, eax
0x1400392f8  jns     short loc_140039342
0x1400392fa  mov     edx, 5Ch ; '\'; Ch
0x1400392ff  lea     rcx, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x140039306  call    cs:__imp_strrchr
0x14003930c  test    rax, rax
0x14003930f  jz      short loc_140039316
0x140039311  inc     rax
0x140039314  jmp     short loc_14003931D
0x140039316  lea     rax, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14003931d  mov     rdx, rax; char *
0x140039320  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140039327  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14003932c  shl     rax, 34h
0x140039330  mov     rcx, 40500010000h
0x14003933a  movzx   edx, bp
0x14003933d  or      rax, rdx
0x140039340  jmp     short loc_1400393A8
0x140039342  mov     rcx, [rdi]; void *
0x140039345  xor     edx, edx; Val
0x140039347  imul    r8, rsi, 38h ; '8'; Size
0x14003934b  call    memset_0
0x140039350  mov     rax, [rdi]
0x140039353  mov     byte ptr [rbx], 1
0x140039356  mov     [rbx+18h], esi
0x140039359  mov     [r14], rax
0x14003935c  mov     rax, 8000000000h
0x140039366  jmp     short loc_1400393AB
0x140039368  mov     edx, 5Ch ; '\'; Ch
0x14003936d  lea     rcx, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x140039374  call    cs:__imp_strrchr
0x14003937a  test    rax, rax
0x14003937d  jz      short loc_140039384
0x14003937f  inc     rax
0x140039382  jmp     short loc_14003938B
0x140039384  lea     rax, aAdminAppmanApp_2; "admin\\AppMan\\AppV\\shared\\include\\s"...
0x14003938b  mov     rdx, rax; char *
0x14003938e  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140039395  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14003939a  mov     rcx, 30500010001h
0x1400393a4  shl     rax, 34h
0x1400393a8  or      rax, rcx
0x1400393ab  mov     rbx, [rsp+38h+arg_8]
0x1400393b0  mov     rbp, [rsp+38h+arg_10]
0x1400393b5  add     rsp, 20h
0x1400393b9  pop     r14
0x1400393bb  pop     rdi
0x1400393bc  pop     rsi
0x1400393bd  retn
```
