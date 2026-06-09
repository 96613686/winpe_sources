# CreateConnectionDispenser(ulong,_VersionInfo *,IConnectionDispenser * *)

- ea: `0x1800ad534`
- end: `0x1800ad73e`
- name: `?CreateConnectionDispenser@@YAJKPEAU_VersionInfo@@PEAPEAUIConnectionDispenser@@@Z`
- size: `522`
- prototype: `__int64 __fastcall(unsigned int, struct _VersionInfo *, struct IConnectionDispenser **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008afb0`
- `0x180097f20`

## callees

- `0x1800240b0`
- `0x1800ad518`
- `0x1800ad534`
- `0x1800bd010`

## import_xrefs

- `MSDTCPRX!CreateLocalTmInstance` at `0x1800ad56d`
- `MSDTCPRX!CreateLocalTmInstance` at `0x1800ad56d`
- `MSDTCPRX!__imp_DllGetDTCConnectionManager` at `0x1800ad5cc`
- `MSDTCPRX!__imp_DllGetDTCConnectionManager` at `0x1800ad5cc`
- `MSDTCPRX!__imp_?ContactToNameObject@@YAPEAUINameObject@@PEAUIProperties@@@Z` at `0x1800ad5a2`
- `MSDTCPRX!__imp_?ContactToNameObject@@YAPEAUINameObject@@PEAUIProperties@@@Z` at `0x1800ad5a2`

## pseudocode

```c
__int64 __fastcall CreateConnectionDispenser(__int64 a1, struct _VersionInfo *a2, struct IConnectionDispenser **a3)
{
  CAcceptNoConnections *v3; // rdi
  struct INameObject *v4; // rsi
  int DTCConnectionManager; // ebx
  struct IProperties *v7; // rax
  CAcceptNoConnections *v8; // rax
  __int64 v10; // [rsp+30h] [rbp-20h] BYREF
  struct IProperties *v11[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v12; // [rsp+78h] [rbp+28h] BYREF
  __int64 v13; // [rsp+88h] [rbp+38h] BYREF

  v3 = 0;
  v12 = 0;
  v4 = 0;
  v13 = 0;
  v11[0] = 0;
  v10 = 0;
  DTCConnectionManager = CreateLocalTmInstance(&v10);
  if ( DTCConnectionManager >= 0 )
  {
    DTCConnectionManager = (*(__int64 (__fastcall **)(__int64, struct IProperties **))(*(_QWORD *)v10 + 176LL))(
                             v10,
                             v11);
    if ( DTCConnectionManager >= 0 )
    {
      v4 = ContactToNameObject(v11[0]);
      if ( v4 )
      {
        DTCConnectionManager = DllGetDTCConnectionManager(&CLSID_DTCCM, &IID_IConnectionManager, &v12);
        if ( !DTCConnectionManager )
        {
          DTCConnectionManager = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v12)(
                                   v12,
                                   &IID_IConnectionManagerConfig2,
                                   &v13);
          if ( !DTCConnectionManager )
          {
            DTCConnectionManager = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 120LL))(v13, 32);
            if ( !DTCConnectionManager )
            {
              v7 = (struct IProperties *)operator new(0x10u);
              v11[1] = v7;
              if ( v7 && (v8 = CAcceptNoConnections::CAcceptNoConnections(v7), (v3 = v8) != 0) )
              {
                DTCConnectionManager = (*(__int64 (__fastcall **)(__int64, struct INameObject *, CAcceptNoConnections *, _QWORD))(*(_QWORD *)v12 + 24LL))(
                                         v12,
                                         v4,
                                         v8,
                                         0);
                if ( !DTCConnectionManager )
                {
                  DTCConnectionManager = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 32LL))(v12);
                  if ( !DTCConnectionManager )
                  {
                    DTCConnectionManager = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
                    if ( !DTCConnectionManager )
                      DTCConnectionManager = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IConnectionDispenser **))v12)(
                                               v12,
                                               &IID_IConnectionDispenser,
                                               a3);
                  }
                }
              }
              else
              {
                DTCConnectionManager = -2147024882;
              }
            }
          }
        }
      }
      else
      {
        DTCConnectionManager = -2147467259;
      }
    }
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v3 )
    (*(void (__fastcall **)(CAcceptNoConnections *))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v11[0] )
    (*(void (__fastcall **)(struct IProperties *))(*(_QWORD *)v11[0] + 16LL))(v11[0]);
  if ( v4 )
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)DTCConnectionManager;
}

```

## disassembly

```asm
0x1800ad534  mov     [rsp-18h+arg_0], rbx
0x1800ad539  mov     [rsp-18h+arg_10], rsi
0x1800ad53e  mov     [rsp-18h+arg_8], rdx
0x1800ad543  push    rbp
0x1800ad544  push    rdi
0x1800ad545  push    r14
0x1800ad547  mov     rbp, rsp
0x1800ad54a  sub     rsp, 50h
0x1800ad54e  xor     edi, edi
0x1800ad550  mov     [rbp+arg_8], 0
0x1800ad558  xor     esi, esi
0x1800ad55a  mov     [rbp+arg_18], rdi
0x1800ad55e  lea     rcx, [rbp+var_20]
0x1800ad562  mov     [rbp+var_18], rdi
0x1800ad566  mov     [rbp+var_20], rsi
0x1800ad56a  mov     r14, r8
0x1800ad56d  call    cs:__imp_CreateLocalTmInstance
0x1800ad573  mov     ebx, eax
0x1800ad575  test    eax, eax
0x1800ad577  js      loc_1800AD6AB
0x1800ad57d  mov     rcx, [rbp+var_20]
0x1800ad581  lea     rdx, [rbp+var_18]
0x1800ad585  mov     rax, [rcx]
0x1800ad588  mov     rax, [rax+0B0h]
0x1800ad58f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad594  mov     ebx, eax
0x1800ad596  test    eax, eax
0x1800ad598  js      loc_1800AD6AB
0x1800ad59e  mov     rcx, [rbp+var_18]
0x1800ad5a2  call    cs:__imp_?ContactToNameObject@@YAPEAUINameObject@@PEAUIProperties@@@Z; ContactToNameObject(IProperties *)
0x1800ad5a8  mov     rsi, rax
0x1800ad5ab  test    rax, rax
0x1800ad5ae  jnz     short loc_1800AD5BA
0x1800ad5b0  mov     ebx, 80004005h
0x1800ad5b5  jmp     loc_1800AD6AB
0x1800ad5ba  lea     r8, [rbp+arg_8]
0x1800ad5be  lea     rdx, IID_IConnectionManager
0x1800ad5c5  lea     rcx, CLSID_DTCCM
0x1800ad5cc  call    cs:__imp_DllGetDTCConnectionManager
0x1800ad5d2  mov     ebx, eax
0x1800ad5d4  test    eax, eax
0x1800ad5d6  jnz     loc_1800AD6AB
0x1800ad5dc  mov     rcx, [rbp+arg_8]
0x1800ad5e0  lea     r8, [rbp+arg_18]
0x1800ad5e4  lea     rdx, IID_IConnectionManagerConfig2
0x1800ad5eb  mov     rax, [rcx]
0x1800ad5ee  mov     rax, [rax]
0x1800ad5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad5f6  mov     ebx, eax
0x1800ad5f8  test    eax, eax
0x1800ad5fa  jnz     loc_1800AD6AB
0x1800ad600  mov     rcx, [rbp+arg_18]
0x1800ad604  lea     edx, [rbx+20h]
0x1800ad607  mov     rax, [rcx]
0x1800ad60a  mov     rax, [rax+78h]
0x1800ad60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad613  mov     ebx, eax
0x1800ad615  test    eax, eax
0x1800ad617  jnz     loc_1800AD6AB
0x1800ad61d  lea     ecx, [rax+10h]; Size
0x1800ad620  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ad625  mov     [rbp+var_10], rax
0x1800ad629  test    rax, rax
0x1800ad62c  jz      short loc_1800AD6A6
0x1800ad62e  mov     rcx, rax; this
0x1800ad631  call    ??0CAcceptNoConnections@@QEAA@XZ; CAcceptNoConnections::CAcceptNoConnections(void)
0x1800ad636  mov     rdi, rax
0x1800ad639  test    rax, rax
0x1800ad63c  jz      short loc_1800AD6A6
0x1800ad63e  mov     rcx, [rbp+arg_8]
0x1800ad642  xor     r9d, r9d
0x1800ad645  mov     r8, rdi
0x1800ad648  mov     rdx, rsi
0x1800ad64b  mov     rax, [rcx]
0x1800ad64e  mov     rax, [rax+18h]
0x1800ad652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad657  mov     ebx, eax
0x1800ad659  test    eax, eax
0x1800ad65b  jnz     short loc_1800AD6AB
0x1800ad65d  mov     rcx, [rbp+arg_8]
0x1800ad661  mov     rax, [rcx]
0x1800ad664  mov     rax, [rax+20h]
0x1800ad668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad66d  mov     ebx, eax
0x1800ad66f  test    eax, eax
0x1800ad671  jnz     short loc_1800AD6AB
0x1800ad673  mov     rcx, [rbp+arg_18]
0x1800ad677  mov     rax, [rcx]
0x1800ad67a  mov     rax, [rax+18h]
0x1800ad67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad683  mov     ebx, eax
0x1800ad685  test    eax, eax
0x1800ad687  jnz     short loc_1800AD6AB
0x1800ad689  mov     rcx, [rbp+arg_8]
0x1800ad68d  lea     rdx, IID_IConnectionDispenser
0x1800ad694  mov     r8, r14
0x1800ad697  mov     rax, [rcx]
0x1800ad69a  mov     rax, [rax]
0x1800ad69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad6a2  mov     ebx, eax
0x1800ad6a4  jmp     short loc_1800AD6AB
0x1800ad6a6  mov     ebx, 8007000Eh
0x1800ad6ab  mov     rcx, [rbp+var_20]
0x1800ad6af  test    rcx, rcx
0x1800ad6b2  jz      short loc_1800AD6C0
0x1800ad6b4  mov     rax, [rcx]
0x1800ad6b7  mov     rax, [rax+10h]
0x1800ad6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad6c0  mov     rcx, [rbp+arg_8]
0x1800ad6c4  test    rcx, rcx
0x1800ad6c7  jz      short loc_1800AD6D5
0x1800ad6c9  mov     rax, [rcx]
0x1800ad6cc  mov     rax, [rax+10h]
0x1800ad6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad6d5  test    rdi, rdi
0x1800ad6d8  jz      short loc_1800AD6E9
0x1800ad6da  mov     rax, [rdi]
0x1800ad6dd  mov     rcx, rdi
0x1800ad6e0  mov     rax, [rax+10h]
0x1800ad6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad6e9  mov     rcx, [rbp+arg_18]
0x1800ad6ed  test    rcx, rcx
0x1800ad6f0  jz      short loc_1800AD6FE
0x1800ad6f2  mov     rax, [rcx]
0x1800ad6f5  mov     rax, [rax+10h]
0x1800ad6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad6fe  mov     rcx, [rbp+var_18]
0x1800ad702  test    rcx, rcx
0x1800ad705  jz      short loc_1800AD713
0x1800ad707  mov     rax, [rcx]
0x1800ad70a  mov     rax, [rax+10h]
0x1800ad70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad713  test    rsi, rsi
0x1800ad716  jz      short loc_1800AD727
0x1800ad718  mov     rax, [rsi]
0x1800ad71b  mov     rcx, rsi
0x1800ad71e  mov     rax, [rax+10h]
0x1800ad722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad727  lea     r11, [rsp+50h+var_s0]
0x1800ad72c  mov     eax, ebx
0x1800ad72e  mov     rbx, [r11+20h]
0x1800ad732  mov     rsi, [r11+30h]
0x1800ad736  mov     rsp, r11
0x1800ad739  pop     r14
0x1800ad73b  pop     rdi
0x1800ad73c  pop     rbp
0x1800ad73d  retn
```
