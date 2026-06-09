# ScriptSite::CreateObjectFromProgID(ushort const *,ushort const *,IUnknown * *)

- ea: `0x180220f68`
- end: `0x1802211ce`
- name: `?CreateObjectFromProgID@ScriptSite@@QEAAJPEBG0PEAPEAUIUnknown@@@Z`
- size: `614`
- prototype: `__int64 __fastcall(ScriptSite *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801aff74`
- `0x180221d90`

## callees

- `0x18021760c`
- `0x1802177e4`
- `0x18021d7e8`
- `0x180220f68`
- `0x180223ffc`
- `0x1802241e0`
- `0x180252c18`
- `0x180341dd0`
- `0x18035e010`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoGetClassObject` at `0x18022108e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetClassObject` at `0x18022108e`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromProgID` at `0x180221008`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromProgID` at `0x180221008`
- `ole32!CLSIDFromProgIDEx` at `0x180221000`
- `ole32!CLSIDFromProgIDEx` at `0x180221000`

## pseudocode

```c
__int64 __fastcall ScriptSite::CreateObjectFromProgID(
        ScriptSite *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IUnknown **a4)
{
  __int64 v8; // rdx
  void *v9; // r12
  BOOL IsSafeMode; // r15d
  HRESULT v11; // eax
  DWORD v12; // edx
  bool v13; // sf
  __int64 v14; // rax
  int v15; // eax
  SiteService *v16; // rdi
  int v17; // ebx
  void (*v18)(void); // rax
  LPVOID ppv; // [rsp+30h] [rbp-50h] BYREF
  __int64 v21; // [rsp+38h] [rbp-48h] BYREF
  struct SiteService *v22; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v23[4]; // [rsp+48h] [rbp-38h] BYREF
  GUID clsid; // [rsp+68h] [rbp-18h] BYREF

  v23[0] = 0;
  v8 = *((_QWORD *)this + 1);
  clsid = 0;
  v23[1] = a3;
  v9 = (void *)((unsigned __int64)v23 & -(__int64)(a3 != 0));
  v23[2] = 0;
  v23[3] = 0;
  IsSafeMode = ScriptEngine::IsSafeMode(this, *(_DWORD *)(v8 + 924), 0);
  if ( IsSafeMode )
    v11 = CLSIDFromProgID(a2, &clsid);
  else
    v11 = CLSIDFromProgIDEx(a2, &clsid);
  if ( v11 < 0
    || (unsigned int)IsProhibitedUnsafeExtension(&clsid)
    || !(unsigned int)ScriptEngine::CanCreateObject(*((ScriptEngine **)this + 1), &clsid) )
  {
    return (unsigned int)-2146827859;
  }
  v12 = 5;
  if ( a3 )
  {
    if ( *(int *)(*((_QWORD *)this + 20) + 2336LL) >= 3 || IsSafeMode )
      return (unsigned int)-2146827859;
    v12 = 16;
  }
  ppv = 0;
  v21 = 0;
  if ( CoGetClassObject(&clsid, v12, v9, &IID_IClassFactory, &ppv) < 0 )
    return (unsigned int)-2146827859;
  v13 = (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IClassFactoryEx, &v21) < 0;
  v14 = *(_QWORD *)ppv;
  if ( v13 )
  {
    v17 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, struct IUnknown **))(v14 + 24))(ppv, 0, &IID_IUnknown, a4);
    v18 = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
    if ( v17 < 0 )
    {
      v18();
      return (unsigned int)v17;
    }
    v18();
  }
  else
  {
    (*(void (**)(void))(v14 + 16))();
    v22 = 0;
    v15 = SiteService::Create(&v22, this);
    v16 = v22;
    v17 = v15;
    if ( v15 < 0
      || (v17 = (*(__int64 (__fastcall **)(__int64, struct SiteService *, _QWORD, GUID *, struct IUnknown **))(*(_QWORD *)v21 + 40LL))(
                  v21,
                  v22,
                  0,
                  &IID_IUnknown,
                  a4),
          v17 < 0) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      if ( v16 )
        SiteService::Release(v16);
      return (unsigned int)v17;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    SiteService::Release(v16);
  }
  if ( !(unsigned int)ScriptEngine::CanObjectRun(*((ScriptEngine **)this + 1), &clsid, *a4) )
  {
    ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
    *a4 = 0;
    return (unsigned int)-2146827859;
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180220f68  mov     rax, rsp
0x180220f6b  mov     [rax+20h], r9
0x180220f6f  mov     [rax+18h], r8
0x180220f73  mov     [rax+10h], rdx
0x180220f77  mov     [rax+8], rcx
0x180220f7b  push    rbp
0x180220f7c  push    rbx
0x180220f7d  push    rsi
0x180220f7e  push    rdi
0x180220f7f  push    r12
0x180220f81  push    r14
0x180220f83  push    r15
0x180220f85  mov     rbp, rsp
0x180220f88  sub     rsp, 80h
0x180220f8f  mov     rax, cs:__security_cookie
0x180220f96  xor     rax, rsp
0x180220f99  mov     [rbp+var_8], rax
0x180220f9d  mov     rdi, [rbp+arg_10]
0x180220fa1  xorps   xmm0, xmm0
0x180220fa4  mov     rsi, [rbp+arg_0]
0x180220fa8  mov     rax, rdi
0x180220fab  mov     rbx, [rbp+lpszProgID]
0x180220faf  neg     rax
0x180220fb2  mov     r14, [rbp+arg_18]
0x180220fb6  lea     rax, [rbp+var_38]
0x180220fba  sbb     r12, r12
0x180220fbd  mov     [rbp+var_38], 0
0x180220fc5  mov     rdx, [rsi+8]
0x180220fc9  xor     r8d, r8d; struct _GUID *
0x180220fcc  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x180220fd0  mov     [rbp+var_30], rdi
0x180220fd4  and     r12, rax
0x180220fd7  mov     [rbp+var_28], 0
0x180220fdf  mov     [rbp+var_20], 0
0x180220fe7  mov     edx, [rdx+39Ch]; unsigned int
0x180220fed  call    ?IsSafeMode@ScriptEngine@@QEAAHKPEBU_GUID@@@Z; ScriptEngine::IsSafeMode(ulong,_GUID const *)
0x180220ff2  lea     rdx, [rbp+clsid]; lpclsid
0x180220ff6  mov     r15d, eax
0x180220ff9  mov     rcx, rbx; lpszProgID
0x180220ffc  test    eax, eax
0x180220ffe  jnz     short loc_180221008
0x180221000  call    cs:__imp_CLSIDFromProgIDEx
0x180221006  jmp     short loc_18022100E
0x180221008  call    cs:__imp_CLSIDFromProgID
0x18022100e  test    eax, eax
0x180221010  js      loc_1802211A9
0x180221016  lea     rcx, [rbp+clsid]
0x18022101a  call    IsProhibitedUnsafeExtension
0x18022101f  test    eax, eax
0x180221021  jnz     loc_1802211A9
0x180221027  mov     rcx, [rsi+8]; this
0x18022102b  lea     rdx, [rbp+clsid]; struct _GUID *
0x18022102f  call    ?CanCreateObject@ScriptEngine@@QEAAHAEBU_GUID@@@Z; ScriptEngine::CanCreateObject(_GUID const &)
0x180221034  test    eax, eax
0x180221036  jz      loc_1802211A9
0x18022103c  mov     edx, 5
0x180221041  test    rdi, rdi
0x180221044  jz      short loc_180221067
0x180221046  mov     rax, [rsi+0A0h]
0x18022104d  cmp     dword ptr [rax+920h], 3
0x180221054  jge     loc_1802211A9
0x18022105a  test    r15d, r15d
0x18022105d  jnz     loc_1802211A9
0x180221063  lea     edx, [r15+10h]; dwClsContext
0x180221067  lea     rax, [rbp+var_50]
0x18022106b  mov     [rbp+var_50], 0
0x180221073  lea     r9, IID_IClassFactory; riid
0x18022107a  mov     [rsp+80h+ppv], rax; ppv
0x18022107f  mov     r8, r12; pvReserved
0x180221082  mov     [rbp+var_48], 0
0x18022108a  lea     rcx, [rbp+clsid]; rclsid
0x18022108e  call    cs:__imp_CoGetClassObject
0x180221094  test    eax, eax
0x180221096  js      loc_1802211A9
0x18022109c  mov     rcx, [rbp+var_50]
0x1802210a0  lea     r8, [rbp+var_48]
0x1802210a4  lea     rdx, IID_IClassFactoryEx
0x1802210ab  mov     rax, [rcx]
0x1802210ae  mov     rax, [rax]
0x1802210b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802210b6  mov     rcx, [rbp+var_50]
0x1802210ba  test    eax, eax
0x1802210bc  mov     rax, [rcx]
0x1802210bf  js      loc_18022114D
0x1802210c5  mov     rax, [rax+10h]
0x1802210c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802210ce  mov     rdx, rsi; struct ScriptSite *
0x1802210d1  mov     [rbp+var_40], 0
0x1802210d9  lea     rcx, [rbp+var_40]; struct SiteService **
0x1802210dd  call    ?Create@SiteService@@SAJPEAPEAV1@PEAVScriptSite@@@Z; SiteService::Create(SiteService * *,ScriptSite *)
0x1802210e2  mov     rdi, [rbp+var_40]
0x1802210e6  mov     ebx, eax
0x1802210e8  test    eax, eax
0x1802210ea  js      short loc_18022112E
0x1802210ec  mov     rcx, [rbp+var_48]
0x1802210f0  lea     r9, IID_IUnknown
0x1802210f7  xor     r8d, r8d
0x1802210fa  mov     [rsp+80h+ppv], r14
0x1802210ff  mov     rdx, rdi
0x180221102  mov     rax, [rcx]
0x180221105  mov     rax, [rax+28h]
0x180221109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022110e  mov     ebx, eax
0x180221110  test    eax, eax
0x180221112  js      short loc_18022112E
0x180221114  mov     rcx, [rbp+var_48]
0x180221118  mov     rax, [rcx]
0x18022111b  mov     rax, [rax+10h]
0x18022111f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180221124  mov     rcx, rdi; this
0x180221127  call    ?Release@SiteService@@UEAAKXZ; SiteService::Release(void)
0x18022112c  jmp     short loc_18022117F
0x18022112e  mov     rcx, [rbp+var_48]
0x180221132  mov     rax, [rcx]
0x180221135  mov     rax, [rax+10h]
0x180221139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022113e  test    rdi, rdi
0x180221141  jz      short loc_1802211AE
0x180221143  mov     rcx, rdi; this
0x180221146  call    ?Release@SiteService@@UEAAKXZ; SiteService::Release(void)
0x18022114b  jmp     short loc_1802211AE
0x18022114d  mov     rax, [rax+18h]
0x180221151  lea     r8, IID_IUnknown
0x180221158  mov     r9, r14
0x18022115b  xor     edx, edx
0x18022115d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180221162  mov     rcx, [rbp+var_50]
0x180221166  mov     ebx, eax
0x180221168  test    eax, eax
0x18022116a  mov     rax, [rcx]
0x18022116d  mov     rax, [rax+10h]
0x180221171  jns     short loc_18022117A
0x180221173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180221178  jmp     short loc_1802211AE
0x18022117a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022117f  mov     r8, [r14]; struct IUnknown *
0x180221182  lea     rdx, [rbp+clsid]; struct _GUID *
0x180221186  mov     rcx, [rsi+8]; this
0x18022118a  call    ?CanObjectRun@ScriptEngine@@QEAAHAEBU_GUID@@PEAUIUnknown@@@Z; ScriptEngine::CanObjectRun(_GUID const &,IUnknown *)
0x18022118f  test    eax, eax
0x180221191  jnz     short loc_1802211AE
0x180221193  mov     rcx, [r14]
0x180221196  mov     rax, [rcx]
0x180221199  mov     rax, [rax+10h]
0x18022119d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802211a2  mov     qword ptr [r14], 0
0x1802211a9  mov     ebx, 800A01ADh
0x1802211ae  mov     eax, ebx
0x1802211b0  mov     rcx, [rbp+var_8]
0x1802211b4  xor     rcx, rsp; StackCookie
0x1802211b7  call    __security_check_cookie
0x1802211bc  add     rsp, 80h
0x1802211c3  pop     r15
0x1802211c5  pop     r14
0x1802211c7  pop     r12
0x1802211c9  pop     rdi
0x1802211ca  pop     rsi
0x1802211cb  pop     rbx
0x1802211cc  pop     rbp
0x1802211cd  retn
```
