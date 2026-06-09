# MODULE_OBJECT_EXTENSION::GetModulesConfigurationForApp(ushort const *,IExtensionContext *,int,INativeConfigurationSystem * *,STRU *,INativeConfigurationElement * *,STRU *,INativeSectionException * *)

- ea: `0x180022394`
- end: `0x1800227d1`
- name: `?GetModulesConfigurationForApp@MODULE_OBJECT_EXTENSION@@AEAAJPEBGPEAVIExtensionContext@@HPEAPEAVINativeConfigurationSystem@@PEAVSTRU@@PEAPEAVINativeConfigurationElement@@3PEAPEAVINativeSectionException@@@Z`
- size: `1085`
- prototype: `int(MODULE_OBJECT_EXTENSION *__hidden this, const unsigned __int16 *, struct IExtensionContext *, int, struct INativeConfigurationSystem **, struct STRU *, struct INativeConfigurationElement **, struct STRU *, struct INativeSectionException **)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800200b0`
- `0x180020674`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180002e90`
- `0x1800049b0`
- `0x180004a70`
- `0x1800220f8`
- `0x180022394`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002254d`
- `msvcrt!_wcsicmp` at `0x18002254d`

## pseudocode

```c
__int64 __fastcall MODULE_OBJECT_EXTENSION::GetModulesConfigurationForApp(
        MODULE_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        struct IExtensionContext *a3,
        __int64 a4,
        struct INativeConfigurationSystem **a5,
        struct STRU *a6,
        struct INativeConfigurationElement **a7,
        struct STRU *a8,
        struct INativeSectionException **a9)
{
  struct INativeConfigurationElement *v11; // r14
  struct INativeSectionException *v12; // rdi
  int ConfigurationForPath; // ebx
  __int64 v14; // rdx
  unsigned __int16 *v15; // r15
  struct INativeConfigurationSystem *v16; // rax
  struct INativeConfigurationSystem *v18; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  struct INativeConfigurationElement *v21; // [rsp+58h] [rbp-A8h] BYREF
  struct INativeSectionException *v22; // [rsp+60h] [rbp-A0h] BYREF
  struct INativeConfigurationElement **v23; // [rsp+68h] [rbp-98h]
  struct INativeConfigurationSystem **v24; // [rsp+70h] [rbp-90h]
  struct INativeSectionException **v25; // [rsp+78h] [rbp-88h]
  __int128 v26; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v27[32]; // [rsp+90h] [rbp-70h] BYREF
  __int16 *v28; // [rsp+B0h] [rbp-50h]
  int v29; // [rsp+B8h] [rbp-48h]
  __int16 v30; // [rsp+BCh] [rbp-44h]
  int v31; // [rsp+C0h] [rbp-40h]
  _BYTE v32[32]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v33; // [rsp+E8h] [rbp-18h]
  int v34; // [rsp+F0h] [rbp-10h]
  __int16 v35; // [rsp+F4h] [rbp-Ch]
  unsigned int v36; // [rsp+F8h] [rbp-8h]
  __int16 v37; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v38[510]; // [rsp+102h] [rbp+2h] BYREF
  __int16 v39; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v40[510]; // [rsp+302h] [rbp+202h] BYREF

  v24 = a5;
  v23 = a7;
  v18 = 0;
  v11 = 0;
  v21 = 0;
  v12 = 0;
  v22 = 0;
  v20 = 0;
  v25 = a9;
  memset_0(v40, 0, sizeof(v40));
  v34 = 512;
  v36 = 0;
  v39 = 0;
  v33 = (unsigned __int16 *)&v39;
  v35 = 256;
  memset_0(v38, 0, sizeof(v38));
  v29 = 512;
  v28 = &v37;
  v30 = 256;
  v31 = 0;
  v37 = 0;
  String1 = 0;
  v26 = 0;
  if ( !a5 || !a3 || !v23 || !a8 || !a9 || !a6 )
  {
    ConfigurationForPath = -2147024809;
LABEL_35:
    if ( v12 )
    {
      *v25 = v12;
      v12 = 0;
    }
    goto LABEL_37;
  }
  if ( !a2 || !*a2 )
  {
    STRU::Copy((STRU *)v32, (const unsigned __int8 *)L"MACHINE/WEBROOT/APPHOST");
    goto LABEL_25;
  }
  ConfigurationForPath = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, __int64 *, int))(*(_QWORD *)a3 + 64LL))(
                           a3,
                           L"APP",
                           a2,
                           &v20,
                           4);
  if ( ConfigurationForPath >= 0 )
  {
    if ( !v20 )
    {
      ConfigurationForPath = -2147467259;
      goto LABEL_43;
    }
    (*(void (__fastcall **)(__int64, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v20 + 80LL))(
      v20,
      L"APP.NAME",
      &String1);
    if ( !String1 )
    {
      ConfigurationForPath = -2147467259;
      goto LABEL_37;
    }
    if ( _wcsicmp(String1, a2) )
    {
      *(_QWORD *)&v26 = L"APP";
      ConfigurationForPath = -2147024846;
      *((_QWORD *)&v26 + 1) = L"SET";
      (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, _DWORD))(*(_QWORD *)a3 + 144LL))(
        a3,
        2147942450LL,
        3221226508LL,
        &v26,
        0);
      goto LABEL_37;
    }
    ConfigurationForPath = STRU::Copy((STRU *)v32, (const unsigned __int8 *)L"MACHINE/WEBROOT/APPHOST");
    if ( ConfigurationForPath < 0 )
      goto LABEL_37;
    ConfigurationForPath = STRU::Append((STRU *)v32, L"/");
    if ( ConfigurationForPath < 0 )
      goto LABEL_37;
    ConfigurationForPath = STRU::Append((STRU *)v32, String1);
    if ( ConfigurationForPath < 0 )
      goto LABEL_37;
    while ( v36 > 1 )
    {
      v14 = v36 - 1;
      if ( v33[v14] != 47 )
        break;
      STRU::SetLen((STRU *)v32, v14);
    }
LABEL_25:
    v15 = v33;
    ConfigurationForPath = (*(__int64 (__fastcall **)(struct IExtensionContext *, unsigned __int16 *, __int16 *, __int64))(*(_QWORD *)a3 + 72LL))(
                             a3,
                             v33,
                             &v37,
                             256);
    if ( ConfigurationForPath < 0 )
      goto LABEL_37;
    STRU::SyncWithBuffer((STRU *)v27);
    ConfigurationForPath = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int16 *, struct INativeConfigurationSystem **))(*(_QWORD *)a3 + 80LL))(
                             a3,
                             v28,
                             &v18);
    if ( ConfigurationForPath < 0 )
      goto LABEL_37;
    ConfigurationForPath = MODULE_OBJECT_EXTENSION::GetConfigurationForPath(
                             (MODULE_OBJECT_EXTENSION *)&v21,
                             v15,
                             L"system.webServer/modules",
                             a3,
                             v18,
                             &v21,
                             &v22);
    if ( ConfigurationForPath < 0 )
      goto LABEL_31;
    ConfigurationForPath = STRU::Copy(a6, (const unsigned __int8 *)v15);
    if ( ConfigurationForPath < 0 )
      goto LABEL_31;
    if ( String1 )
    {
      ConfigurationForPath = STRU::Copy(a8, (const unsigned __int8 *)String1);
      if ( ConfigurationForPath < 0 )
      {
LABEL_31:
        v11 = v21;
        v12 = v22;
        goto LABEL_35;
      }
    }
    else
    {
      **((_WORD **)a8 + 4) = 0;
      *((_DWORD *)a8 + 12) = 0;
    }
    v11 = 0;
    ConfigurationForPath = 0;
    v12 = v22;
    *v23 = v21;
    v16 = v18;
    v18 = 0;
    *v24 = v16;
  }
LABEL_37:
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v12 )
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_43:
  if ( v18 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v27);
  BUFFER::~BUFFER((BUFFER *)v32);
  return (unsigned int)ConfigurationForPath;
}

```

## disassembly

```asm
0x180022394  mov     [rsp-8+arg_0], rbx
0x180022399  push    rbp
0x18002239a  push    rsi
0x18002239b  push    rdi
0x18002239c  push    r12
0x18002239e  push    r13
0x1800223a0  push    r14
0x1800223a2  push    r15
0x1800223a4  lea     rbp, [rsp-410h]
0x1800223ac  sub     rsp, 510h
0x1800223b3  mov     rax, cs:__security_cookie
0x1800223ba  xor     rax, rsp
0x1800223bd  mov     [rbp+440h+var_40], rax
0x1800223c4  mov     rax, [rbp+440h+arg_20]
0x1800223cb  lea     rcx, [rbp+440h+var_23E]; void *
0x1800223d2  mov     rbx, [rbp+440h+arg_40]
0x1800223d9  mov     rsi, r8
0x1800223dc  mov     r12, [rbp+440h+arg_28]
0x1800223e3  mov     r15, rdx
0x1800223e6  mov     r13, [rbp+440h+arg_38]
0x1800223ed  xor     edx, edx; Val
0x1800223ef  mov     [rsp+540h+var_4D0], rax
0x1800223f4  mov     r8d, 1FEh; Size
0x1800223fa  mov     rax, [rbp+440h+arg_30]
0x180022401  mov     [rsp+540h+var_4D8], rax
0x180022406  xor     eax, eax
0x180022408  mov     [rsp+540h+var_500], rax
0x18002240d  mov     r14d, eax
0x180022410  mov     [rsp+540h+var_4E8], rax
0x180022415  mov     edi, eax
0x180022417  mov     [rsp+540h+var_4E0], rax
0x18002241c  mov     [rsp+540h+var_4F0], rax
0x180022421  mov     [rsp+540h+var_4C8], rbx
0x180022426  call    memset_0
0x18002242b  xor     ecx, ecx
0x18002242d  mov     [rbp+440h+var_450], 200h
0x180022434  mov     [rbp+440h+var_448], ecx
0x180022437  lea     rax, [rbp+440h+var_240]
0x18002243e  mov     [rbp+440h+var_240], cx
0x180022445  xor     edx, edx; Val
0x180022447  lea     rcx, [rbp+440h+var_43E]; void *
0x18002244b  mov     [rbp+440h+var_458], rax
0x18002244f  mov     r8d, 1FEh; Size
0x180022455  mov     [rbp+440h+var_44C], 100h
0x18002245b  call    memset_0
0x180022460  xor     r8d, r8d
0x180022463  mov     [rbp+440h+var_488], 200h
0x18002246a  lea     rax, [rbp+440h+var_440]
0x18002246e  xorps   xmm0, xmm0
0x180022471  mov     [rbp+440h+var_490], rax
0x180022475  mov     [rbp+440h+var_484], 100h
0x18002247b  mov     [rbp+440h+var_480], r8d
0x18002247f  mov     [rbp+440h+var_440], r8w
0x180022484  mov     [rsp+540h+String1], r8
0x180022489  movups  [rbp+440h+var_4C0], xmm0
0x18002248d  cmp     [rsp+540h+var_4D0], r8
0x180022492  jz      loc_18002271B
0x180022498  test    rsi, rsi
0x18002249b  jz      loc_18002271B
0x1800224a1  cmp     [rsp+540h+var_4D8], r8
0x1800224a6  jz      loc_18002271B
0x1800224ac  test    r13, r13
0x1800224af  jz      loc_18002271B
0x1800224b5  test    rbx, rbx
0x1800224b8  jz      loc_18002271B
0x1800224be  test    r12, r12
0x1800224c1  jz      loc_18002271B
0x1800224c7  test    r15, r15
0x1800224ca  jz      loc_18002260A
0x1800224d0  cmp     [r15], r8w
0x1800224d4  jz      loc_18002260A
0x1800224da  mov     rax, [rsi]
0x1800224dd  lea     r9, [rsp+540h+var_4F0]
0x1800224e2  mov     r8, r15
0x1800224e5  mov     dword ptr [rsp+540h+var_520], 4
0x1800224ed  lea     rdx, aApp_0; "APP"
0x1800224f4  mov     rcx, rsi
0x1800224f7  mov     rax, [rax+40h]
0x1800224fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022500  mov     ebx, eax
0x180022502  test    eax, eax
0x180022504  js      loc_180022730
0x18002250a  mov     rcx, [rsp+540h+var_4F0]
0x18002250f  test    rcx, rcx
0x180022512  jnz     short loc_18002251E
0x180022514  mov     ebx, 80004005h
0x180022519  jmp     loc_180022776
0x18002251e  mov     rax, [rcx]
0x180022521  lea     r8, [rsp+540h+String1]
0x180022526  lea     rdx, aAppName_0; "APP.NAME"
0x18002252d  mov     rax, [rax+50h]
0x180022531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022536  mov     rcx, [rsp+540h+String1]; String1
0x18002253b  test    rcx, rcx
0x18002253e  jnz     short loc_18002254A
0x180022540  mov     ebx, 80004005h
0x180022545  jmp     loc_180022730
0x18002254a  mov     rdx, r15; String2
0x18002254d  call    cs:__imp__wcsicmp
0x180022553  xor     ecx, ecx
0x180022555  test    eax, eax
0x180022557  jz      short loc_18002259B
0x180022559  lea     rax, aApp_0; "APP"
0x180022560  mov     dword ptr [rsp+540h+var_520], ecx
0x180022564  mov     qword ptr [rbp+440h+var_4C0], rax
0x180022568  lea     r9, [rbp+440h+var_4C0]
0x18002256c  lea     rax, aSet_0; "SET"
0x180022573  mov     ebx, 80070032h
0x180022578  mov     qword ptr [rbp+440h+var_4C0+8], rax
0x18002257c  mov     r8d, 0C000040Ch
0x180022582  mov     rax, [rsi]
0x180022585  mov     edx, ebx
0x180022587  mov     rcx, rsi
0x18002258a  mov     rax, [rax+90h]
0x180022591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022596  jmp     loc_180022730
0x18002259b  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800225a2  lea     rcx, [rbp+440h+var_478]; this
0x1800225a6  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800225ab  mov     ebx, eax
0x1800225ad  test    eax, eax
0x1800225af  js      loc_180022730
0x1800225b5  lea     rdx, SubStr; "/"
0x1800225bc  lea     rcx, [rbp+440h+var_478]; this
0x1800225c0  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800225c5  mov     ebx, eax
0x1800225c7  test    eax, eax
0x1800225c9  js      loc_180022730
0x1800225cf  mov     rdx, [rsp+540h+String1]; unsigned __int16 *
0x1800225d4  lea     rcx, [rbp+440h+var_478]; this
0x1800225d8  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800225dd  mov     ebx, eax
0x1800225df  test    eax, eax
0x1800225e1  js      loc_180022730
0x1800225e7  jmp     short loc_180022600
0x1800225e9  lea     edx, [rax-1]; unsigned int
0x1800225ec  mov     rax, [rbp+440h+var_458]
0x1800225f0  cmp     word ptr [rax+rdx*2], 2Fh ; '/'
0x1800225f5  jnz     short loc_18002261A
0x1800225f7  lea     rcx, [rbp+440h+var_478]; this
0x1800225fb  call    ?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180022600  mov     eax, [rbp+440h+var_448]
0x180022603  cmp     eax, 1
0x180022606  ja      short loc_1800225E9
0x180022608  jmp     short loc_18002261A
0x18002260a  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180022611  lea     rcx, [rbp+440h+var_478]; this
0x180022615  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002261a  mov     rax, [rsi]
0x18002261d  lea     r8, [rbp+440h+var_440]
0x180022621  mov     r15, [rbp+440h+var_458]
0x180022625  mov     r9d, 100h
0x18002262b  mov     rdx, r15
0x18002262e  mov     rcx, rsi
0x180022631  mov     rax, [rax+48h]
0x180022635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002263a  mov     ebx, eax
0x18002263c  test    eax, eax
0x18002263e  js      loc_180022730
0x180022644  lea     rcx, [rbp+440h+var_4B0]; this
0x180022648  call    ?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18002264d  mov     rax, [rsi]
0x180022650  lea     r8, [rsp+540h+var_500]
0x180022655  mov     rdx, [rbp+440h+var_490]
0x180022659  mov     rcx, rsi
0x18002265c  mov     rax, [rax+50h]
0x180022660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022665  mov     ebx, eax
0x180022667  test    eax, eax
0x180022669  js      loc_180022730
0x18002266f  mov     rax, [rsp+540h+var_500]
0x180022674  lea     rcx, [rsp+540h+var_4E0]
0x180022679  mov     [rsp+540h+var_510], rcx; struct INativeSectionException **
0x18002267e  lea     r8, aSystemWebserve_9; "system.webServer/modules"
0x180022685  lea     rcx, [rsp+540h+var_4E8]; this
0x18002268a  mov     r9, rsi; struct IExtensionContext *
0x18002268d  mov     [rsp+540h+var_518], rcx; struct INativeConfigurationElement **
0x180022692  mov     rdx, r15; unsigned __int16 *
0x180022695  mov     [rsp+540h+var_520], rax; struct INativeConfigurationSystem *
0x18002269a  call    ?GetConfigurationForPath@MODULE_OBJECT_EXTENSION@@AEAAJPEBG0PEAVIExtensionContext@@PEAVINativeConfigurationSystem@@PEAPEAVINativeConfigurationElement@@PEAPEAVINativeSectionException@@@Z; MODULE_OBJECT_EXTENSION::GetConfigurationForPath(ushort const *,ushort const *,IExtensionContext *,INativeConfigurationSystem *,INativeConfigurationElement * *,INativeSectionException * *)
0x18002269f  xor     r8d, r8d
0x1800226a2  mov     ebx, eax
0x1800226a4  test    eax, eax
0x1800226a6  js      short loc_1800226D7
0x1800226a8  mov     rdx, r15; unsigned __int16 *
0x1800226ab  mov     rcx, r12; this
0x1800226ae  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800226b3  xor     r8d, r8d
0x1800226b6  mov     ebx, eax
0x1800226b8  test    eax, eax
0x1800226ba  js      short loc_1800226D7
0x1800226bc  mov     rdx, [rsp+540h+String1]; unsigned __int16 *
0x1800226c1  test    rdx, rdx
0x1800226c4  jz      short loc_1800226E3
0x1800226c6  mov     rcx, r13; this
0x1800226c9  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800226ce  xor     r8d, r8d
0x1800226d1  mov     ebx, eax
0x1800226d3  test    eax, eax
0x1800226d5  jns     short loc_1800226EF
0x1800226d7  mov     r14, [rsp+540h+var_4E8]
0x1800226dc  mov     rdi, [rsp+540h+var_4E0]
0x1800226e1  jmp     short loc_180022720
0x1800226e3  mov     rcx, [r13+20h]
0x1800226e7  mov     [rcx], r8w
0x1800226eb  mov     [r13+30h], r8d
0x1800226ef  mov     rcx, [rsp+540h+var_4D8]
0x1800226f4  mov     r14, r8
0x1800226f7  mov     rax, [rsp+540h+var_4E8]
0x1800226fc  mov     ebx, r8d
0x1800226ff  mov     rdi, [rsp+540h+var_4E0]
0x180022704  mov     [rcx], rax
0x180022707  mov     rax, [rsp+540h+var_500]
0x18002270c  mov     rcx, [rsp+540h+var_4D0]
0x180022711  mov     [rsp+540h+var_500], r8
0x180022716  mov     [rcx], rax
0x180022719  jmp     short loc_180022730
0x18002271b  mov     ebx, 80070057h
0x180022720  test    rdi, rdi
0x180022723  jz      short loc_180022730
0x180022725  mov     rax, [rsp+540h+var_4C8]
0x18002272a  mov     [rax], rdi
0x18002272d  mov     rdi, r8
0x180022730  mov     rcx, [rsp+540h+var_4F0]
0x180022735  test    rcx, rcx
0x180022738  jz      short loc_18002274E
0x18002273a  mov     rax, [rcx]
0x18002273d  mov     rax, [rax+10h]
0x180022741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022746  xor     r8d, r8d
0x180022749  mov     [rsp+540h+var_4F0], r8
0x18002274e  test    r14, r14
0x180022751  jz      short loc_180022762
0x180022753  mov     rax, [r14]
0x180022756  mov     rcx, r14
0x180022759  mov     rax, [rax+10h]
0x18002275d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022762  test    rdi, rdi
0x180022765  jz      short loc_180022776
0x180022767  mov     rax, [rdi]
0x18002276a  mov     rcx, rdi
0x18002276d  mov     rax, [rax+10h]
0x180022771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022776  mov     rcx, [rsp+540h+var_500]
0x18002277b  test    rcx, rcx
0x18002277e  jz      short loc_180022793
0x180022780  mov     rax, [rcx]
0x180022783  mov     rax, [rax+10h]
0x180022787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002278c  xor     ecx, ecx
0x18002278e  mov     [rsp+540h+var_500], rcx
0x180022793  lea     rcx, [rbp+440h+var_4B0]; this
0x180022797  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002279c  lea     rcx, [rbp+440h+var_478]; this
0x1800227a0  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800227a5  mov     eax, ebx
0x1800227a7  mov     rcx, [rbp+440h+var_40]
0x1800227ae  xor     rcx, rsp; StackCookie
0x1800227b1  call    __security_check_cookie
0x1800227b6  mov     rbx, [rsp+540h+arg_0]
0x1800227be  add     rsp, 510h
0x1800227c5  pop     r15
0x1800227c7  pop     r14
0x1800227c9  pop     r13
0x1800227cb  pop     r12
0x1800227cd  pop     rdi
0x1800227ce  pop     rsi
0x1800227cf  pop     rbp
0x1800227d0  retn
```
