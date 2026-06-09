# CWMIBinMof::CopyWDMKeyToDredgeKey(void)

- ea: `0x14000f91c`
- end: `0x14000fc24`
- name: `?CopyWDMKeyToDredgeKey@CWMIBinMof@@QEAAHXZ`
- size: `776`
- prototype: `__int64 __fastcall(CWMIBinMof *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007c10`

## callees

- `0x14000f7c4`
- `0x14000f80c`
- `0x14000f870`
- `0x14000f898`
- `0x14000f91c`
- `0x14000fe30`
- `0x14000ff40`
- `0x140011be0`
- `0x140011cc0`
- `0x1400120e0`
- `0x140012270`
- `0x1400122b0`
- `0x1400131d0`
- `0x140013a20`
- `0x140014ad0`

## pseudocode

```c
__int64 __fastcall CWMIBinMof::CopyWDMKeyToDredgeKey(CWMIBinMof *this)
{
  unsigned int v1; // edi
  unsigned int i; // eax
  __int64 v3; // rdx
  const unsigned __int16 *v4; // rdx
  unsigned int v6; // [rsp+48h] [rbp-580h] BYREF
  unsigned __int8 *v7; // [rsp+50h] [rbp-578h] BYREF
  unsigned __int16 *v8; // [rsp+58h] [rbp-570h] BYREF
  _BYTE v9[8]; // [rsp+60h] [rbp-568h] BYREF
  unsigned __int16 *v10; // [rsp+68h] [rbp-560h] BYREF
  _BYTE v11[8]; // [rsp+70h] [rbp-558h] BYREF
  _BYTE *v12; // [rsp+78h] [rbp-550h]
  void (__fastcall *v13)(CRegistry *__hidden); // [rsp+80h] [rbp-548h]
  _BYTE v14[8]; // [rsp+88h] [rbp-540h] BYREF
  _BYTE *v15; // [rsp+90h] [rbp-538h]
  void (__fastcall *v16)(CRegistry *__hidden); // [rsp+98h] [rbp-530h]
  _BYTE v17[24]; // [rsp+A0h] [rbp-528h] BYREF
  _BYTE v18[24]; // [rsp+B8h] [rbp-510h] BYREF
  _BYTE v19[608]; // [rsp+D0h] [rbp-4F8h] BYREF
  _BYTE v20[576]; // [rsp+330h] [rbp-298h] BYREF
  unsigned int v21; // [rsp+570h] [rbp-58h]

  v1 = 0;
  CRegistry::CRegistry((CRegistry *)v20);
  CRegistry::CRegistry((CRegistry *)v19);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( !CRegistry::Open((CRegistry *)v20, HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\WDM", 0x20019u) )
    {
      v14[0] = 0;
      v15 = v20;
      v16 = CRegistry::Close;
      if ( !CRegistry::Open((CRegistry *)v19, HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\WDM", 0x20019u) )
      {
        MakeObjGuard<CRegistry,void (CRegistry::*)(void)>((__int64)v17, (__int64)v19);
        CHString::CHString((CHString *)&v7, L"DREDGE");
        ((void (__stdcall *)(CRegistry *, struct CHString *))CRegistry::DeleteKey)(
          (CRegistry *)v19,
          (struct CHString *)&v7);
        CHString::~CHString((const unsigned __int16 **)&v7);
        ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>((__int64)v17);
      }
      if ( !((int (__stdcall *)(CRegistry *, HKEY, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *))CRegistry::CreateOpen)(
              (CRegistry *)v19,
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\WBEM\\WDM\\DREDGE",
              0,
              0,
              2u,
              0,
              0) )
      {
        v11[0] = 0;
        v12 = v19;
        v13 = CRegistry::Close;
        v7 = 0;
        v8 = 0;
        v1 = 1;
        v6 = 0;
        for ( i = 0; i < v21; i = ++v6 )
        {
          if ( (unsigned int)CRegistry::EnumerateAndGetValues((CRegistry *)v20, &v6, &v8, &v7) )
          {
            v1 = 0;
          }
          else
          {
            MakeGuard<void (*)(unsigned char *),unsigned char *>(v18, v8, v8);
            MakeGuard<void (*)(unsigned char *),unsigned char *>(v17, v3, v7);
            CHString::CHString((CHString *)&v10, v4);
            CHString::CHString((CHString *)v9, (const unsigned __int16 *)v7);
            if ( CRegistry::SetCurrentKeyValue((CRegistry *)v19, v10, (struct CHString *)v9) )
              v1 = 0;
            CHString::~CHString((const unsigned __int16 **)v9);
            CHString::~CHString((const unsigned __int16 **)&v10);
            ScopeGuardImpl1<void (*)(unsigned short *),unsigned short *>::~ScopeGuardImpl1<void (*)(unsigned short *),unsigned short *>((__int64)v17);
            ScopeGuardImpl1<void (*)(unsigned short *),unsigned short *>::~ScopeGuardImpl1<void (*)(unsigned short *),unsigned short *>((__int64)v18);
          }
          if ( !v1 )
            break;
        }
        ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>((__int64)v11);
      }
      ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>((__int64)v14);
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &CHeap_Exception `RTTI Type Descriptor', 0) )
    {
      v1 = 0;
      __eh34_try_continuation(0, &CHeap_Exception `RTTI Type Descriptor', &loc_14000FBE5);
    }
  }
  CRegistry::~CRegistry((CRegistry *)v19);
  CRegistry::~CRegistry((CRegistry *)v20);
  return v1;
}

```

## disassembly

```asm
0x14000f91c  push    rbx
0x14000f91e  push    rdi
0x14000f91f  push    r12
0x14000f921  push    r15
0x14000f923  sub     rsp, 5A8h
0x14000f92a  mov     rax, cs:__security_cookie
0x14000f931  xor     rax, rsp
0x14000f934  mov     [rsp+5C8h+var_38], rax
0x14000f93c  mov     [rsp+5C8h+var_588], 0
0x14000f944  xor     edi, edi
0x14000f946  lea     rcx, [rsp+5C8h+var_298]; this
0x14000f94e  call    ??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x14000f953  nop
0x14000f954  lea     rcx, [rsp+5C8h+var_4F8]; this
0x14000f95c  call    ??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x14000f961  nop
0x14000f962  mov     r9d, 20019h; unsigned int
0x14000f968  lea     r8, aSoftwareMicros; "Software\\Microsoft\\WBEM\\WDM"
0x14000f96f  mov     r15, 0FFFFFFFF80000002h
0x14000f976  mov     rdx, r15; HKEY
0x14000f979  lea     rcx, [rsp+5C8h+var_298]; this
0x14000f981  call    ?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x14000f986  test    eax, eax
0x14000f988  jnz     loc_14000FBE3
0x14000f98e  mov     [rsp+5C8h+var_540], al
0x14000f995  lea     rax, [rsp+5C8h+var_298]
0x14000f99d  mov     [rsp+5C8h+var_538], rax
0x14000f9a5  lea     r12, ?Close@CRegistry@@QEAAXXZ; CRegistry::Close(void)
0x14000f9ac  mov     [rsp+5C8h+var_530], r12
0x14000f9b4  mov     [rsp+5C8h+var_588], 2
0x14000f9bc  lea     ebx, [rdi+2]
0x14000f9bf  and     ebx, 0FFFFFFFDh
0x14000f9c2  mov     [rsp+5C8h+var_588], ebx
0x14000f9c6  or      ebx, 1
0x14000f9c9  mov     [rsp+5C8h+var_588], ebx
0x14000f9cd  mov     r9d, 20019h; unsigned int
0x14000f9d3  lea     r8, aSoftwareMicros; "Software\\Microsoft\\WBEM\\WDM"
0x14000f9da  mov     rdx, r15; HKEY
0x14000f9dd  lea     rcx, [rsp+5C8h+var_4F8]; this
0x14000f9e5  call    ?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x14000f9ea  test    eax, eax
0x14000f9ec  jnz     short loc_14000FA41
0x14000f9ee  lea     rdx, [rsp+5C8h+var_4F8]
0x14000f9f6  lea     rcx, [rsp+5C8h+var_528]
0x14000f9fe  call    ??$MakeObjGuard@VCRegistry@@P81@EAAXXZ@@YA?AV?$ObjScopeGuardImpl0@VCRegistry@@P81@EAAXXZ@@AEAVCRegistry@@P81@EAAXXZ@Z; MakeObjGuard<CRegistry,void (CRegistry::*)(void)>(CRegistry &,void (CRegistry::*)(void))
0x14000fa03  nop
0x14000fa04  lea     rdx, aDredge; "DREDGE"
0x14000fa0b  lea     rcx, [rsp+5C8h+var_578]; this
0x14000fa10  call    ??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x14000fa15  nop
0x14000fa16  lea     rdx, [rsp+5C8h+var_578]; struct CHString *
0x14000fa1b  lea     rcx, [rsp+5C8h+var_4F8]; this
0x14000fa23  call    ?DeleteKey@CRegistry@@QEAAJPEAVCHString@@@Z; CRegistry::DeleteKey(CHString *)
0x14000fa28  nop
0x14000fa29  lea     rcx, [rsp+5C8h+var_578]; this
0x14000fa2e  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x14000fa33  nop
0x14000fa34  lea     rcx, [rsp+5C8h+var_528]
0x14000fa3c  call    ??1?$ObjScopeGuardImpl0@VCRegistry@@P81@EAAXXZ@@QEAA@XZ; ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(void)
0x14000fa41  mov     [rsp+5C8h+var_590], 0; unsigned int *
0x14000fa4a  mov     [rsp+5C8h+var_598], 0; struct _SECURITY_ATTRIBUTES *
0x14000fa53  mov     [rsp+5C8h+var_5A0], 2; unsigned int
0x14000fa5b  mov     [rsp+5C8h+var_5A8], 0; unsigned int
0x14000fa63  xor     r9d, r9d; unsigned __int16 *
0x14000fa66  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\WBEM\\WDM\\DREDGE"
0x14000fa6d  mov     rdx, r15; HKEY
0x14000fa70  lea     rcx, [rsp+5C8h+var_4F8]; this
0x14000fa78  call    ?CreateOpen@CRegistry@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; CRegistry::CreateOpen(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x14000fa7d  test    eax, eax
0x14000fa7f  jnz     loc_14000FBCE
0x14000fa85  mov     [rsp+5C8h+var_558], al
0x14000fa89  lea     rax, [rsp+5C8h+var_4F8]
0x14000fa91  mov     [rsp+5C8h+var_550], rax
0x14000fa96  mov     [rsp+5C8h+var_548], r12
0x14000fa9e  mov     ebx, 21h ; '!'
0x14000faa3  mov     [rsp+5C8h+var_588], ebx
0x14000faa7  and     ebx, 0FFFFFFDFh
0x14000faaa  mov     [rsp+5C8h+var_588], ebx
0x14000faae  or      ebx, 10h
0x14000fab1  mov     [rsp+5C8h+var_588], ebx
0x14000fab5  mov     [rsp+5C8h+var_578], 0
0x14000fabe  mov     [rsp+5C8h+var_570], 0
0x14000fac7  mov     edi, 1
0x14000facc  mov     [rsp+5C8h+var_584], edi
0x14000fad0  mov     [rsp+5C8h+var_580], 0
0x14000fad8  xor     eax, eax
0x14000fada  cmp     eax, [rsp+5C8h+var_58]
0x14000fae1  jnb     loc_14000FBBD
0x14000fae7  lea     r9, [rsp+5C8h+var_578]; unsigned __int8 **
0x14000faec  lea     r8, [rsp+5C8h+var_570]; unsigned __int16 **
0x14000faf1  lea     rdx, [rsp+5C8h+var_580]; unsigned int *
0x14000faf6  lea     rcx, [rsp+5C8h+var_298]; this
0x14000fafe  call    ?EnumerateAndGetValues@CRegistry@@QEAAJAEAKAEAPEAGAEAPEAE@Z; CRegistry::EnumerateAndGetValues(ulong &,ushort * &,uchar * &)
0x14000fb03  test    eax, eax
0x14000fb05  jnz     loc_14000FBA4
0x14000fb0b  mov     rdx, [rsp+5C8h+var_570]
0x14000fb10  mov     r8, rdx
0x14000fb13  lea     rcx, [rsp+5C8h+var_510]
0x14000fb1b  call    ??$MakeGuard@P6AXPEAE@ZPEAE@@YA?AV?$ScopeGuardImpl1@P6AXPEAE@ZPEAE@@P6AXPEAE@Z0@Z; MakeGuard<void (*)(uchar *),uchar *>(void (*)(uchar *),uchar *)
0x14000fb20  nop
0x14000fb21  mov     r8, [rsp+5C8h+var_578]
0x14000fb26  lea     rcx, [rsp+5C8h+var_528]
0x14000fb2e  call    ??$MakeGuard@P6AXPEAE@ZPEAE@@YA?AV?$ScopeGuardImpl1@P6AXPEAE@ZPEAE@@P6AXPEAE@Z0@Z; MakeGuard<void (*)(uchar *),uchar *>(void (*)(uchar *),uchar *)
0x14000fb33  nop
0x14000fb34  lea     rcx, [rsp+5C8h+var_560]; this
0x14000fb39  call    ??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x14000fb3e  nop
0x14000fb3f  mov     rdx, [rsp+5C8h+var_578]; unsigned __int16 *
0x14000fb44  lea     rcx, [rsp+5C8h+var_568]; this
0x14000fb49  call    ??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x14000fb4e  nop
0x14000fb4f  lea     r8, [rsp+5C8h+var_568]; struct CHString *
0x14000fb54  mov     rdx, [rsp+5C8h+var_560]; unsigned __int16 *
0x14000fb59  lea     rcx, [rsp+5C8h+var_4F8]; this
0x14000fb61  call    ?SetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::SetCurrentKeyValue(ushort const *,CHString &)
0x14000fb66  xor     ecx, ecx
0x14000fb68  test    eax, eax
0x14000fb6a  cmovnz  edi, ecx
0x14000fb6d  mov     [rsp+5C8h+var_584], edi
0x14000fb71  lea     rcx, [rsp+5C8h+var_568]; this
0x14000fb76  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x14000fb7b  nop
0x14000fb7c  lea     rcx, [rsp+5C8h+var_560]; this
0x14000fb81  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x14000fb86  nop
0x14000fb87  lea     rcx, [rsp+5C8h+var_528]
0x14000fb8f  call    ??1?$ScopeGuardImpl1@P6AXPEAG@ZPEAG@@QEAA@XZ; ScopeGuardImpl1<void (*)(ushort *),ushort *>::~ScopeGuardImpl1<void (*)(ushort *),ushort *>(void)
0x14000fb94  nop
0x14000fb95  lea     rcx, [rsp+5C8h+var_510]
0x14000fb9d  call    ??1?$ScopeGuardImpl1@P6AXPEAG@ZPEAG@@QEAA@XZ; ScopeGuardImpl1<void (*)(ushort *),ushort *>::~ScopeGuardImpl1<void (*)(ushort *),ushort *>(void)
0x14000fba2  jmp     short loc_14000FBAA
0x14000fba4  xor     edi, edi
0x14000fba6  mov     [rsp+5C8h+var_584], edi
0x14000fbaa  test    edi, edi
0x14000fbac  jz      short loc_14000FBBD
0x14000fbae  mov     eax, [rsp+5C8h+var_580]
0x14000fbb2  inc     eax
0x14000fbb4  mov     [rsp+5C8h+var_580], eax
0x14000fbb8  jmp     loc_14000FADA
0x14000fbbd  and     ebx, 0FFFFFFEFh
0x14000fbc0  mov     [rsp+5C8h+var_588], ebx
0x14000fbc4  lea     rcx, [rsp+5C8h+var_558]
0x14000fbc9  call    ??1?$ObjScopeGuardImpl0@VCRegistry@@P81@EAAXXZ@@QEAA@XZ; ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(void)
0x14000fbce  and     ebx, 0FFFFFFFEh
0x14000fbd1  mov     [rsp+5C8h+var_588], ebx
0x14000fbd5  lea     rcx, [rsp+5C8h+var_540]
0x14000fbdd  call    ??1?$ObjScopeGuardImpl0@VCRegistry@@P81@EAAXXZ@@QEAA@XZ; ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>::~ObjScopeGuardImpl0<CRegistry,void (CRegistry::*)(void)>(void)
0x14000fbe2  nop
0x14000fbe3  jmp     short loc_14000FBE9
0x14000fbe5  mov     edi, [rsp+5C8h+var_584]
0x14000fbe9  lea     rcx, [rsp+5C8h+var_4F8]; this
0x14000fbf1  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x14000fbf6  nop
0x14000fbf7  lea     rcx, [rsp+5C8h+var_298]; this
0x14000fbff  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x14000fc04  mov     eax, edi
0x14000fc06  mov     rcx, [rsp+5C8h+var_38]
0x14000fc0e  xor     rcx, rsp; StackCookie
0x14000fc11  call    __security_check_cookie
0x14000fc16  add     rsp, 5A8h
0x14000fc1d  pop     r15
0x14000fc1f  pop     r12
0x14000fc21  pop     rdi
0x14000fc22  pop     rbx
0x14000fc23  retn
```
