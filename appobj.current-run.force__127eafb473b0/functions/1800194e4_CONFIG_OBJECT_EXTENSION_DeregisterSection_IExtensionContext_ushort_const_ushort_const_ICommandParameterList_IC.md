# CONFIG_OBJECT_EXTENSION::DeregisterSection(IExtensionContext *,ushort const *,ushort const *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x1800194e4`
- end: `0x18001993f`
- name: `?DeregisterSection@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBG1PEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `1115`
- prototype: `int(CONFIG_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a850`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x18000557c`
- `0x180006b6c`
- `0x18001882c`
- `0x1800194e4`
- `0x18001aff4`
- `0x18002b304`
- `0x18002e9ac`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800195fd`
- `msvcrt!_wcsicmp` at `0x1800195fd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800196f8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800196f8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800198fb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800198fb`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT_EXTENSION::DeregisterSection(
        CONFIG_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct ICommandParameterList *a5,
        struct ICommandObjectList *a6)
{
  OLECHAR *v8; // r12
  const unsigned __int16 **v10; // rdi
  int SectionNameHelper; // ebx
  __int64 v12; // rdx
  __int64 v13; // r8
  APP_OBJECT_UTILS *v14; // rcx
  int v15; // eax
  int v16; // r14d
  BSTR v17; // rax
  struct IAppHostSectionGroup *v18; // rcx
  unsigned __int16 *v19; // r13
  int v20; // eax
  unsigned int v21; // r9d
  int v22; // eax
  int v23; // r14d
  STATUS_OBJECT *v24; // rax
  int v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+28h] [rbp-D8h]
  struct IAppHostSectionGroup *v28; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  va_list Arguments[2]; // [rsp+58h] [rbp-A8h] BYREF
  va_list v34; // [rsp+68h] [rbp-98h]
  struct ICommandObjectList *v35; // [rsp+70h] [rbp-90h]
  _QWORD v36[4]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v37[32]; // [rsp+98h] [rbp-68h] BYREF
  __int16 *v38; // [rsp+B8h] [rbp-48h]
  int v39; // [rsp+C0h] [rbp-40h]
  __int16 v40; // [rsp+C4h] [rbp-3Ch]
  int v41; // [rsp+C8h] [rbp-38h]
  _BYTE v42[32]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v43; // [rsp+F0h] [rbp-10h]
  int v44; // [rsp+F8h] [rbp-8h]
  __int16 v45; // [rsp+FCh] [rbp-4h]
  int v46; // [rsp+100h] [rbp+0h]
  __int16 v47; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v48[510]; // [rsp+112h] [rbp+12h] BYREF
  __int16 v49; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v50[510]; // [rsp+312h] [rbp+212h] BYREF

  v35 = a6;
  v32 = 0;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  *(_OWORD *)Arguments = 0;
  v8 = 0;
  v34 = (va_list)a4;
  memset_0(v48, 0, sizeof(v48));
  v45 = 256;
  v43 = (unsigned __int16 *)&v47;
  v44 = 512;
  v47 = 0;
  v46 = 0;
  memset_0(v50, 0, sizeof(v50));
  v39 = 512;
  v38 = &v49;
  v40 = 256;
  v49 = 0;
  v41 = 0;
  `vector constructor iterator'(
    v36,
    0x20u,
    1u,
    (void *(*)(void *))IIS_CONFIG_SECTION_DEFINITION::IIS_CONFIG_SECTION_DEFINITION);
  v10 = 0;
  if ( !a2 || !a4 || !a5 )
  {
    SectionNameHelper = -2147024809;
    goto LABEL_36;
  }
  if ( _wcsicmp(a3, L"MACHINE/WEBROOT/APPHOST") )
  {
    SectionNameHelper = -2147024809;
    Arguments[0] = (va_list)a3;
    v12 = 2147942487LL;
    Arguments[1] = (va_list)L"MACHINE/WEBROOT/APPHOST";
    v13 = 3221226504LL;
LABEL_6:
    (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, va_list *, _DWORD))(*(_QWORD *)a2 + 144LL))(
      a2,
      v12,
      v13,
      Arguments,
      0);
    goto LABEL_36;
  }
  SectionNameHelper = CONFIG_OBJECT_EXTENSION::ExtractSectionNameHelper(a4, (struct STRU *)v37, (struct STRU *)v42);
  if ( SectionNameHelper >= 0 )
  {
    v36[0] = v38;
    v15 = APP_OBJECT_UTILS::PopEmptyParameter(v14, a2, a5, L"ignoreifnotfound", v26, v27);
    v16 = v15;
    if ( v15 >= 0 || (SectionNameHelper = v15, v15 == -2147023483) )
    {
      SectionNameHelper = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, __int64 *))(*(_QWORD *)a2 + 80LL))(
                            a2,
                            a3,
                            &v32);
      if ( SectionNameHelper >= 0 )
      {
        SectionNameHelper = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v32)(
                              v32,
                              &IID_IAppHostWritableAdminManager,
                              &v31);
        if ( SectionNameHelper >= 0 )
        {
          SectionNameHelper = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 48LL))(v31, &v30);
          if ( SectionNameHelper >= 0 )
          {
            v17 = SysAllocString(a3);
            v8 = v17;
            if ( !v17 )
            {
              SectionNameHelper = -2147024882;
              goto LABEL_36;
            }
            SectionNameHelper = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v30 + 24LL))(
                                  v30,
                                  v17,
                                  &v29);
            if ( SectionNameHelper >= 0 )
            {
              v18 = 0;
              v28 = 0;
              if ( v29 && (v19 = v43) != 0 )
              {
                v20 = (*(__int64 (__fastcall **)(__int64, struct IAppHostSectionGroup **))(*(_QWORD *)v29 + 80LL))(
                        v29,
                        &v28);
                v18 = v28;
                SectionNameHelper = v20;
                if ( v20 >= 0 )
                {
                  v22 = CONFIG_SECTION_DEFINITION_HELPER::RecursivelyDeleteSectionDefinitions(
                          v28,
                          v19,
                          (struct IIS_CONFIG_SECTION_DEFINITION *const)v36,
                          v21);
                  v18 = v28;
                  SectionNameHelper = v22;
                }
              }
              else
              {
                SectionNameHelper = -2147024809;
              }
              if ( v18 )
                ((void (__fastcall *)(struct IAppHostSectionGroup *))v18->lpVtbl->Release)(v18);
              v12 = 2147943813LL;
              if ( SectionNameHelper == -2147023483 )
              {
                if ( v16 < 0 )
                {
                  v13 = 3221226507LL;
                  goto LABEL_6;
                }
                v23 = 1;
              }
              else
              {
                if ( SectionNameHelper < 0 )
                  goto LABEL_36;
                v23 = 0;
                SectionNameHelper = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, _QWORD))(*(_QWORD *)a2 + 208LL))(
                                      a2,
                                      a3,
                                      0);
                if ( SectionNameHelper < 0 )
                  goto LABEL_36;
              }
              v24 = (STATUS_OBJECT *)operator new(0x110u);
              if ( v24 && (v10 = (const unsigned __int16 **)STATUS_OBJECT::STATUS_OBJECT(v24)) != 0 )
              {
                Arguments[0] = v34;
                Arguments[1] = 0;
                SectionNameHelper = STATUS_OBJECT::Create(v10, v23 != 0 ? 1073742901 : 1076, Arguments);
                if ( SectionNameHelper >= 0 )
                  SectionNameHelper = (*(__int64 (__fastcall **)(struct ICommandObjectList *, const unsigned __int16 **))(*(_QWORD *)v35 + 24LL))(
                                        v35,
                                        v10);
              }
              else
              {
                SectionNameHelper = -2147024888;
              }
            }
          }
        }
      }
    }
  }
LABEL_36:
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v10 )
    (*((void (__fastcall **)(const unsigned __int16 **))*v10 + 2))(v10);
  if ( v8 )
    SysFreeString(v8);
  BUFFER::~BUFFER((BUFFER *)v37);
  BUFFER::~BUFFER((BUFFER *)v42);
  return (unsigned int)SectionNameHelper;
}

```

## disassembly

```asm
0x1800194e4  mov     [rsp-8+arg_0], rbx
0x1800194e9  push    rbp
0x1800194ea  push    rsi
0x1800194eb  push    rdi
0x1800194ec  push    r12
0x1800194ee  push    r13
0x1800194f0  push    r14
0x1800194f2  push    r15
0x1800194f4  lea     rbp, [rsp-420h]
0x1800194fc  sub     rsp, 520h
0x180019503  mov     rax, cs:__security_cookie
0x18001950a  xor     rax, rsp
0x18001950d  mov     [rbp+450h+var_40], rax
0x180019514  mov     rax, [rbp+450h+arg_28]
0x18001951b  lea     rcx, [rbp+450h+var_43E]; void *
0x18001951f  mov     r14, [rbp+450h+arg_20]
0x180019526  xor     ebx, ebx
0x180019528  mov     r15, r8
0x18001952b  mov     [rsp+550h+var_4E0], rax
0x180019530  mov     rsi, rdx
0x180019533  mov     [rsp+550h+var_500], rbx
0x180019538  xorps   xmm0, xmm0
0x18001953b  mov     [rsp+550h+var_508], rbx
0x180019540  xor     edx, edx; Val
0x180019542  mov     [rsp+550h+var_510], rbx
0x180019547  mov     r8d, 1FEh; Size
0x18001954d  mov     [rsp+550h+var_518], rbx
0x180019552  movups  xmmword ptr [rsp+550h+Arguments], xmm0
0x180019557  mov     r12d, ebx
0x18001955a  mov     [rsp+550h+var_4E8], r9
0x18001955f  mov     r13, r9
0x180019562  call    memset_0
0x180019567  lea     rax, [rbp+450h+var_440]
0x18001956b  mov     [rbp+450h+var_454], 100h
0x180019571  mov     edi, 200h
0x180019576  mov     [rbp+450h+var_460], rax
0x18001957a  xor     eax, eax
0x18001957c  mov     [rbp+450h+var_458], edi
0x18001957f  xor     edx, edx; Val
0x180019581  mov     [rbp+450h+var_440], ax
0x180019585  lea     rcx, [rbp+450h+var_23E]; void *
0x18001958c  mov     [rbp+450h+var_450], r12d
0x180019590  lea     r8d, [rdi-2]; Size
0x180019594  lea     ebx, [r12+1]
0x180019599  call    memset_0
0x18001959e  lea     rax, [rbp+450h+var_240]
0x1800195a5  mov     [rbp+450h+var_490], edi
0x1800195a8  mov     [rbp+450h+var_498], rax
0x1800195ac  lea     r9, ??0IIS_CONFIG_SECTION_DEFINITION@@QEAA@XZ; void *(*)(void *)
0x1800195b3  xor     eax, eax
0x1800195b5  mov     [rbp+450h+var_48C], 100h
0x1800195bb  mov     r8d, ebx; unsigned __int64
0x1800195be  mov     [rbp+450h+var_240], ax
0x1800195c5  lea     edx, [rbx+1Fh]; unsigned __int64
0x1800195c8  mov     [rbp+450h+var_488], r12d
0x1800195cc  lea     rcx, [rsp+550h+var_4D8]; void *
0x1800195d1  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800195d6  xor     edi, edi
0x1800195d8  test    rsi, rsi
0x1800195db  jz      loc_18001985E
0x1800195e1  test    r13, r13
0x1800195e4  jz      loc_18001985E
0x1800195ea  test    r14, r14
0x1800195ed  jz      loc_18001985E
0x1800195f3  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800195fa  mov     rcx, r15; String1
0x1800195fd  call    cs:__imp__wcsicmp
0x180019603  test    eax, eax
0x180019605  jz      short loc_180019645
0x180019607  mov     ebx, 80070057h
0x18001960c  mov     [rsp+550h+Arguments], r15
0x180019611  lea     rax, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180019618  mov     edx, ebx
0x18001961a  mov     [rsp+550h+Arguments+8], rax
0x18001961f  mov     r8d, 0C0000408h
0x180019625  mov     rax, [rsi]
0x180019628  lea     r9, [rsp+550h+Arguments]
0x18001962d  mov     rcx, rsi
0x180019630  mov     [rsp+550h+var_530], edi
0x180019634  mov     rax, [rax+90h]
0x18001963b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019640  jmp     loc_180019863
0x180019645  lea     r8, [rbp+450h+var_480]; struct STRU *
0x180019649  mov     rcx, r13; unsigned __int16 *
0x18001964c  lea     rdx, [rbp+450h+var_4B8]; this
0x180019650  call    ?ExtractSectionNameHelper@CONFIG_OBJECT_EXTENSION@@CAJPEBGPEAVSTRU@@1@Z; CONFIG_OBJECT_EXTENSION::ExtractSectionNameHelper(ushort const *,STRU *,STRU *)
0x180019655  mov     ebx, eax
0x180019657  test    eax, eax
0x180019659  js      loc_180019863
0x18001965f  mov     rax, [rbp+450h+var_498]
0x180019663  lea     r9, aIgnoreifnotfou; "ignoreifnotfound"
0x18001966a  mov     r8, r14; struct ICommandParameterList *
0x18001966d  mov     [rsp+550h+var_4D8], rax
0x180019672  mov     rdx, rsi; struct IExtensionContext *
0x180019675  call    ?PopEmptyParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGHH@Z; APP_OBJECT_UTILS::PopEmptyParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int,int)
0x18001967a  mov     r14d, eax
0x18001967d  test    eax, eax
0x18001967f  jns     short loc_18001968E
0x180019681  mov     ebx, eax
0x180019683  cmp     eax, 80070585h
0x180019688  jnz     loc_180019863
0x18001968e  mov     rax, [rsi]
0x180019691  lea     r8, [rsp+550h+var_500]
0x180019696  mov     rdx, r15
0x180019699  mov     rcx, rsi
0x18001969c  mov     rax, [rax+50h]
0x1800196a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196a5  mov     ebx, eax
0x1800196a7  test    eax, eax
0x1800196a9  js      loc_180019863
0x1800196af  mov     rcx, [rsp+550h+var_500]
0x1800196b4  lea     r8, [rsp+550h+var_508]
0x1800196b9  lea     rdx, IID_IAppHostWritableAdminManager
0x1800196c0  mov     rax, [rcx]
0x1800196c3  mov     rax, [rax]
0x1800196c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196cb  mov     ebx, eax
0x1800196cd  test    eax, eax
0x1800196cf  js      loc_180019863
0x1800196d5  mov     rcx, [rsp+550h+var_508]
0x1800196da  lea     rdx, [rsp+550h+var_510]
0x1800196df  mov     rax, [rcx]
0x1800196e2  mov     rax, [rax+30h]
0x1800196e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196eb  mov     ebx, eax
0x1800196ed  test    eax, eax
0x1800196ef  js      loc_180019863
0x1800196f5  mov     rcx, r15; psz
0x1800196f8  call    cs:__imp_SysAllocString
0x1800196fe  mov     r12, rax
0x180019701  test    rax, rax
0x180019704  jnz     short loc_180019710
0x180019706  mov     ebx, 8007000Eh
0x18001970b  jmp     loc_180019863
0x180019710  mov     rcx, [rsp+550h+var_510]
0x180019715  lea     r8, [rsp+550h+var_518]
0x18001971a  mov     rdx, r12
0x18001971d  mov     rax, [rcx]
0x180019720  mov     rax, [rax+18h]
0x180019724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019729  mov     ebx, eax
0x18001972b  test    eax, eax
0x18001972d  js      loc_180019863
0x180019733  mov     r8, [rsp+550h+var_518]
0x180019738  xor     ecx, ecx
0x18001973a  mov     [rsp+550h+var_520], rcx
0x18001973f  test    r8, r8
0x180019742  jz      short loc_180019782
0x180019744  mov     r13, [rbp+450h+var_460]
0x180019748  test    r13, r13
0x18001974b  jz      short loc_180019782
0x18001974d  mov     rax, [r8]
0x180019750  lea     rdx, [rsp+550h+var_520]
0x180019755  mov     rcx, r8
0x180019758  mov     rax, [rax+50h]
0x18001975c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019761  mov     rcx, [rsp+550h+var_520]; struct IAppHostSectionGroup *
0x180019766  mov     ebx, eax
0x180019768  test    eax, eax
0x18001976a  js      short loc_180019787
0x18001976c  lea     r8, [rsp+550h+var_4D8]; struct IIS_CONFIG_SECTION_DEFINITION *
0x180019771  mov     rdx, r13; unsigned __int16 *
0x180019774  call    ?RecursivelyDeleteSectionDefinitions@CONFIG_SECTION_DEFINITION_HELPER@@CAJPEAUIAppHostSectionGroup@@PEBGQEAUIIS_CONFIG_SECTION_DEFINITION@@K@Z; CONFIG_SECTION_DEFINITION_HELPER::RecursivelyDeleteSectionDefinitions(IAppHostSectionGroup *,ushort const *,IIS_CONFIG_SECTION_DEFINITION * const,ulong)
0x180019779  mov     rcx, [rsp+550h+var_520]
0x18001977e  mov     ebx, eax
0x180019780  jmp     short loc_180019787
0x180019782  mov     ebx, 80070057h
0x180019787  test    rcx, rcx
0x18001978a  jz      short loc_180019798
0x18001978c  mov     rax, [rcx]
0x18001978f  mov     rax, [rax+10h]
0x180019793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019798  mov     edx, 80070585h
0x18001979d  cmp     ebx, edx
0x18001979f  jnz     short loc_1800197B4
0x1800197a1  not     r14d
0x1800197a4  test    r14d, r14d
0x1800197a7  js      short loc_1800197E3
0x1800197a9  mov     r8d, 0C000040Bh
0x1800197af  jmp     loc_180019625
0x1800197b4  test    ebx, ebx
0x1800197b6  js      loc_180019863
0x1800197bc  mov     rax, [rsi]
0x1800197bf  xor     r8d, r8d
0x1800197c2  mov     rdx, r15
0x1800197c5  mov     rcx, rsi
0x1800197c8  xor     r14d, r14d
0x1800197cb  mov     rax, [rax+0D0h]
0x1800197d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197d7  mov     ebx, eax
0x1800197d9  test    eax, eax
0x1800197db  js      loc_180019863
0x1800197e1  jmp     short loc_1800197E9
0x1800197e3  mov     r14d, 1
0x1800197e9  mov     ecx, 110h; Size
0x1800197ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800197f3  test    rax, rax
0x1800197f6  jz      short loc_180019857
0x1800197f8  mov     rcx, rax; this
0x1800197fb  call    ??0STATUS_OBJECT@@QEAA@XZ; STATUS_OBJECT::STATUS_OBJECT(void)
0x180019800  mov     rdi, rax
0x180019803  test    rax, rax
0x180019806  jz      short loc_180019857
0x180019808  mov     rax, [rsp+550h+var_4E8]
0x18001980d  lea     r8, [rsp+550h+Arguments]; Arguments
0x180019812  neg     r14d
0x180019815  mov     [rsp+550h+Arguments], rax
0x18001981a  mov     rcx, rdi; this
0x18001981d  mov     [rsp+550h+Arguments+8], 0
0x180019826  sbb     edx, edx
0x180019828  and     edx, 40000001h
0x18001982e  add     edx, 434h; dwMessageId
0x180019834  call    ?Create@STATUS_OBJECT@@QEAAJKQEAPEBG@Z; STATUS_OBJECT::Create(ulong,ushort const * * const)
0x180019839  mov     ebx, eax
0x18001983b  test    eax, eax
0x18001983d  js      short loc_180019863
0x18001983f  mov     rcx, [rsp+550h+var_4E0]
0x180019844  mov     rdx, rdi
0x180019847  mov     rax, [rcx]
0x18001984a  mov     rax, [rax+18h]
0x18001984e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019853  mov     ebx, eax
0x180019855  jmp     short loc_180019863
0x180019857  mov     ebx, 80070008h
0x18001985c  jmp     short loc_180019863
0x18001985e  mov     ebx, 80070057h
0x180019863  mov     rcx, [rsp+550h+var_518]
0x180019868  test    rcx, rcx
0x18001986b  jz      short loc_180019882
0x18001986d  mov     rax, [rcx]
0x180019870  mov     rax, [rax+10h]
0x180019874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019879  mov     [rsp+550h+var_518], 0
0x180019882  mov     rcx, [rsp+550h+var_510]
0x180019887  test    rcx, rcx
0x18001988a  jz      short loc_1800198A1
0x18001988c  mov     rax, [rcx]
0x18001988f  mov     rax, [rax+10h]
0x180019893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019898  mov     [rsp+550h+var_510], 0
0x1800198a1  mov     rcx, [rsp+550h+var_508]
0x1800198a6  test    rcx, rcx
0x1800198a9  jz      short loc_1800198C0
0x1800198ab  mov     rax, [rcx]
0x1800198ae  mov     rax, [rax+10h]
0x1800198b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198b7  mov     [rsp+550h+var_508], 0
0x1800198c0  mov     rcx, [rsp+550h+var_500]
0x1800198c5  test    rcx, rcx
0x1800198c8  jz      short loc_1800198DF
0x1800198ca  mov     rax, [rcx]
0x1800198cd  mov     rax, [rax+10h]
0x1800198d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198d6  mov     [rsp+550h+var_500], 0
0x1800198df  test    rdi, rdi
0x1800198e2  jz      short loc_1800198F3
0x1800198e4  mov     rax, [rdi]
0x1800198e7  mov     rcx, rdi
0x1800198ea  mov     rax, [rax+10h]
0x1800198ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198f3  test    r12, r12
0x1800198f6  jz      short loc_180019901
0x1800198f8  mov     rcx, r12; bstrString
0x1800198fb  call    cs:__imp_SysFreeString
0x180019901  lea     rcx, [rbp+450h+var_4B8]; this
0x180019905  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001990a  lea     rcx, [rbp+450h+var_480]; this
0x18001990e  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180019913  mov     eax, ebx
0x180019915  mov     rcx, [rbp+450h+var_40]
0x18001991c  xor     rcx, rsp; StackCookie
0x18001991f  call    __security_check_cookie
0x180019924  mov     rbx, [rsp+550h+arg_0]
0x18001992c  add     rsp, 520h
0x180019933  pop     r15
0x180019935  pop     r14
0x180019937  pop     r13
0x180019939  pop     r12
0x18001993b  pop     rdi
0x18001993c  pop     rsi
0x18001993d  pop     rbp
0x18001993e  retn
```
