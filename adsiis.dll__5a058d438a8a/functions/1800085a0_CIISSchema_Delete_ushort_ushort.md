# CIISSchema::Delete(ushort *,ushort *)

- ea: `0x1800085a0`
- end: `0x18000886b`
- name: `?Delete@CIISSchema@@UEAAJPEAG0@Z`
- size: `715`
- prototype: `int(CIISSchema *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x1800085a0`
- `0x180012ffc`
- `0x18001441c`
- `0x180019590`
- `0x18001984c`
- `0x180019d84`
- `0x180019e14`
- `0x18001a0c8`
- `0x18001b4e4`
- `0x18001b5ac`
- `0x18001bc54`
- `0x18001e010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800085e3`
- `msvcrt!_wcsicmp` at `0x1800086ac`
- `msvcrt!_wcsicmp` at `0x1800085e3`
- `msvcrt!_wcsicmp` at `0x1800086ac`

## pseudocode

```c
__int64 __fastcall CIISSchema::Delete(CIISSchema *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int v6; // esi
  int v7; // ebx
  int v8; // eax
  IIsSchema *v9; // rcx
  _QWORD *v10; // r15
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // r15
  _DWORD *v15; // rax
  unsigned int v16; // ebx
  struct IMSAdminBaseW *v17; // rcx
  unsigned int v19; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v20[24]; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v21; // [rsp+88h] [rbp+38h] BYREF
  unsigned int v22; // [rsp+98h] [rbp+48h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  v6 = 0;
  v21 = 0;
  if ( _wcsicmp(a2, L"Class") )
  {
    if ( _wcsicmp(a2, L"Property") )
    {
      v7 = -2147463160;
      goto LABEL_31;
    }
    v9 = (IIsSchema *)*((_QWORD *)this + 6);
    v22 = 0;
    v19 = 0;
    v7 = IIsSchema::PropNameWToId(v9, a3, &v19);
    if ( v7 < 0 )
      goto LABEL_31;
    v7 = IIsSchema::LookupMetaID(*((IIsSchema **)this + 6), a3, &v22);
    if ( v7 < 0 )
      goto LABEL_31;
    CCredentials::Initialize((CCredentials *)v20, 0, 0, 0);
    v10 = (_QWORD *)((char *)this + 40);
    v7 = OpenAdminBaseKey(
           (struct CCredentials *)v20,
           *((unsigned __int16 **)this + 4),
           L"Schema/Properties",
           2u,
           (struct IMSAdminBaseW **)this + 5,
           &v21);
    if ( v7 < 0 )
      goto LABEL_6;
    v6 = v21;
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, _DWORD))(*(_QWORD *)*v10 + 88LL))(
            *v10,
            v21,
            L"Names",
            v22,
            0);
    v7 = 0;
    if ( v11 != -2146646015 )
      v7 = v11;
    if ( v7 < 0 )
      goto LABEL_18;
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, _DWORD))(*(_QWORD *)*v10 + 88LL))(
            *v10,
            v6,
            L"Types",
            v22,
            0);
    v7 = 0;
    if ( v12 != -2146646015 )
      v7 = v12;
    if ( v7 < 0 )
    {
LABEL_18:
      CCredentials::~CCredentials((CCredentials *)v20);
      goto LABEL_31;
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, _DWORD))(*(_QWORD *)*v10 + 88LL))(
            *v10,
            v6,
            L"Defaults",
            v22,
            0);
    v7 = 0;
    if ( v13 != -2146646015 )
      v7 = v13;
    CCredentials::~CCredentials((CCredentials *)v20);
    if ( v7 < 0 )
      goto LABEL_31;
    v14 = *((_QWORD *)this + 6);
    v21 = 0;
    v15 = StrMap::Find((StrMap *)(v14 + 32), a3, &v21);
    if ( !v15 )
    {
      v7 = -2147463162;
      goto LABEL_31;
    }
    v16 = v15[2];
    StrMap::ClearEntry((StrMap *)(v14 + 32), a3);
    if ( v16 )
      DWORDMap::ClearEntry((DWORDMap *)(v14 + 64), v16);
    goto LABEL_29;
  }
  v7 = IIsSchema::ValidateClassName(*((IIsSchema **)this + 6), a3);
  if ( v7 >= 0 )
  {
    CCredentials::Initialize((CCredentials *)v20, 0, 0, 0);
    v7 = OpenAdminBaseKey(
           (struct CCredentials *)v20,
           *((unsigned __int16 **)this + 4),
           L"Schema/Classes",
           2u,
           (struct IMSAdminBaseW **)this + 5,
           &v21);
    if ( v7 < 0 )
    {
LABEL_6:
      CCredentials::~CCredentials((CCredentials *)v20);
      v6 = v21;
      goto LABEL_31;
    }
    v6 = v21;
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 5) + 32LL))(
           *((_QWORD *)this + 5),
           v21,
           a3);
    v7 = 0;
    if ( v8 != -2146646015 )
      v7 = v8;
    CCredentials::~CCredentials((CCredentials *)v20);
    if ( v7 < 0 )
      goto LABEL_31;
    StrMap::ClearEntry(*((StrMap **)this + 6), a3);
LABEL_29:
    v7 = 0;
  }
LABEL_31:
  v17 = (struct IMSAdminBaseW *)*((_QWORD *)this + 5);
  if ( v17 )
  {
    if ( v6 )
      CloseAdminBaseKey(v17, v6);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800085a0  mov     [rsp-28h+arg_0], rbx
0x1800085a5  mov     [rsp-28h+arg_10], rsi
0x1800085aa  push    rbp
0x1800085ab  push    rdi
0x1800085ac  push    r12
0x1800085ae  push    r14
0x1800085b0  push    r15
0x1800085b2  mov     rbp, rsp
0x1800085b5  sub     rsp, 50h
0x1800085b9  mov     r14, r8
0x1800085bc  mov     rbx, rdx
0x1800085bf  mov     rdi, rcx
0x1800085c2  test    rdx, rdx
0x1800085c5  jz      loc_18000884D
0x1800085cb  test    r8, r8
0x1800085ce  jz      loc_18000884D
0x1800085d4  xor     esi, esi
0x1800085d6  lea     rdx, aClass_0; "Class"
0x1800085dd  mov     rcx, rbx; String1
0x1800085e0  mov     [rbp+arg_8], esi
0x1800085e3  call    cs:__imp__wcsicmp
0x1800085e9  test    eax, eax
0x1800085eb  jnz     loc_1800086A2
0x1800085f1  mov     rcx, [rdi+30h]; this
0x1800085f5  mov     rdx, r14; unsigned __int16 *
0x1800085f8  call    ?ValidateClassName@IIsSchema@@QEAAJPEBG@Z; IIsSchema::ValidateClassName(ushort const *)
0x1800085fd  mov     ebx, eax
0x1800085ff  test    eax, eax
0x180008601  js      loc_180008835
0x180008607  xor     r9d, r9d; unsigned int
0x18000860a  lea     rcx, [rbp+var_18]; this
0x18000860e  xor     r8d, r8d; unsigned __int16 *
0x180008611  xor     edx, edx; unsigned __int16 *
0x180008613  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x180008618  mov     rdx, [rdi+20h]; unsigned __int16 *
0x18000861c  lea     rax, [rbp+arg_8]
0x180008620  mov     [rsp+50h+var_28], rax; unsigned int *
0x180008625  lea     rsi, [rdi+28h]
0x180008629  mov     r9d, 2; unsigned int
0x18000862f  mov     [rsp+50h+var_30], rsi; struct IMSAdminBaseW **
0x180008634  lea     r8, aSchemaClasses; "Schema/Classes"
0x18000863b  lea     rcx, [rbp+var_18]; this
0x18000863f  call    ?OpenAdminBaseKey@@YAJAEAVCCredentials@@PEAG1KPEAPEAUIMSAdminBaseW@@PEAK@Z; OpenAdminBaseKey(CCredentials &,ushort *,ushort *,ulong,IMSAdminBaseW * *,ulong *)
0x180008644  mov     ebx, eax
0x180008646  test    eax, eax
0x180008648  jns     short loc_18000865B
0x18000864a  lea     rcx, [rbp+var_18]; this
0x18000864e  call    ??1CCredentials@@QEAA@XZ; CCredentials::~CCredentials(void)
0x180008653  mov     esi, [rbp+arg_8]
0x180008656  jmp     loc_180008835
0x18000865b  mov     rcx, [rsi]
0x18000865e  mov     r8, r14
0x180008661  mov     esi, [rbp+arg_8]
0x180008664  mov     edx, esi
0x180008666  mov     rax, [rcx]
0x180008669  mov     rax, [rax+20h]
0x18000866d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008672  xor     ebx, ebx
0x180008674  lea     rcx, [rbp+var_18]; this
0x180008678  mov     r12d, 800CC801h
0x18000867e  cmp     eax, r12d
0x180008681  cmovnz  ebx, eax
0x180008684  call    ??1CCredentials@@QEAA@XZ; CCredentials::~CCredentials(void)
0x180008689  test    ebx, ebx
0x18000868b  js      loc_180008835
0x180008691  mov     rcx, [rdi+30h]; this
0x180008695  mov     rdx, r14; unsigned __int16 *
0x180008698  call    ?ClearEntry@StrMap@@QEAAHPEBG@Z; StrMap::ClearEntry(ushort const *)
0x18000869d  jmp     loc_18000882C
0x1800086a2  lea     rdx, aProperty; "Property"
0x1800086a9  mov     rcx, rbx; String1
0x1800086ac  call    cs:__imp__wcsicmp
0x1800086b2  test    eax, eax
0x1800086b4  jnz     loc_180008830
0x1800086ba  mov     rcx, [rdi+30h]; this
0x1800086be  lea     r8, [rbp+var_20]; unsigned int *
0x1800086c2  mov     rdx, r14; unsigned __int16 *
0x1800086c5  mov     [rbp+arg_18], esi
0x1800086c8  mov     [rbp+var_20], esi
0x1800086cb  call    ?PropNameWToId@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::PropNameWToId(ushort const *,ulong *)
0x1800086d0  mov     ebx, eax
0x1800086d2  test    eax, eax
0x1800086d4  js      loc_180008835
0x1800086da  mov     rcx, [rdi+30h]; this
0x1800086de  lea     r8, [rbp+arg_18]; unsigned int *
0x1800086e2  mov     rdx, r14; unsigned __int16 *
0x1800086e5  call    ?LookupMetaID@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::LookupMetaID(ushort const *,ulong *)
0x1800086ea  mov     ebx, eax
0x1800086ec  test    eax, eax
0x1800086ee  js      loc_180008835
0x1800086f4  xor     r9d, r9d; unsigned int
0x1800086f7  lea     rcx, [rbp+var_18]; this
0x1800086fb  xor     r8d, r8d; unsigned __int16 *
0x1800086fe  xor     edx, edx; unsigned __int16 *
0x180008700  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x180008705  mov     rdx, [rdi+20h]; unsigned __int16 *
0x180008709  lea     rax, [rbp+arg_8]
0x18000870d  mov     [rsp+50h+var_28], rax; unsigned int *
0x180008712  lea     r15, [rdi+28h]
0x180008716  mov     r9d, 2; unsigned int
0x18000871c  mov     [rsp+50h+var_30], r15; struct IMSAdminBaseW **
0x180008721  lea     r8, aSchemaProperti; "Schema/Properties"
0x180008728  lea     rcx, [rbp+var_18]; this
0x18000872c  call    ?OpenAdminBaseKey@@YAJAEAVCCredentials@@PEAG1KPEAPEAUIMSAdminBaseW@@PEAK@Z; OpenAdminBaseKey(CCredentials &,ushort *,ushort *,ulong,IMSAdminBaseW * *,ulong *)
0x180008731  mov     ebx, eax
0x180008733  test    eax, eax
0x180008735  js      loc_18000864A
0x18000873b  mov     rcx, [r15]
0x18000873e  lea     r8, aNames; "Names"
0x180008745  mov     r9d, [rbp+arg_18]
0x180008749  mov     dword ptr [rsp+50h+var_30], esi
0x18000874d  mov     esi, [rbp+arg_8]
0x180008750  mov     edx, esi
0x180008752  mov     rax, [rcx]
0x180008755  mov     rax, [rax+58h]
0x180008759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000875e  xor     ebx, ebx
0x180008760  mov     r12d, 800CC801h
0x180008766  cmp     eax, r12d
0x180008769  cmovnz  ebx, eax
0x18000876c  test    ebx, ebx
0x18000876e  jns     short loc_18000877E
0x180008770  lea     rcx, [rbp+var_18]; this
0x180008774  call    ??1CCredentials@@QEAA@XZ; CCredentials::~CCredentials(void)
0x180008779  jmp     loc_180008835
0x18000877e  mov     rcx, [r15]
0x180008781  lea     r8, aTypes; "Types"
0x180008788  mov     r9d, [rbp+arg_18]
0x18000878c  mov     edx, esi
0x18000878e  mov     dword ptr [rsp+50h+var_30], 0
0x180008796  mov     rax, [rcx]
0x180008799  mov     rax, [rax+58h]
0x18000879d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087a2  xor     ebx, ebx
0x1800087a4  cmp     eax, r12d
0x1800087a7  cmovnz  ebx, eax
0x1800087aa  test    ebx, ebx
0x1800087ac  js      short loc_180008770
0x1800087ae  mov     rcx, [r15]
0x1800087b1  lea     r8, aDefaults; "Defaults"
0x1800087b8  mov     r9d, [rbp+arg_18]
0x1800087bc  mov     edx, esi
0x1800087be  mov     dword ptr [rsp+50h+var_30], 0
0x1800087c6  mov     rax, [rcx]
0x1800087c9  mov     rax, [rax+58h]
0x1800087cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087d2  xor     ebx, ebx
0x1800087d4  lea     rcx, [rbp+var_18]; this
0x1800087d8  cmp     eax, r12d
0x1800087db  cmovnz  ebx, eax
0x1800087de  call    ??1CCredentials@@QEAA@XZ; CCredentials::~CCredentials(void)
0x1800087e3  test    ebx, ebx
0x1800087e5  js      short loc_180008835
0x1800087e7  mov     r15, [rdi+30h]
0x1800087eb  lea     r8, [rbp+arg_8]; unsigned int *
0x1800087ef  mov     rdx, r14; unsigned __int16 *
0x1800087f2  mov     [rbp+arg_8], 0
0x1800087f9  lea     rcx, [r15+20h]; this
0x1800087fd  call    ?Find@StrMap@@QEBAPEAXPEBGPEAK@Z; StrMap::Find(ushort const *,ulong *)
0x180008802  test    rax, rax
0x180008805  jnz     short loc_18000880E
0x180008807  mov     ebx, 80005006h
0x18000880c  jmp     short loc_180008835
0x18000880e  mov     ebx, [rax+8]
0x180008811  lea     rcx, [r15+20h]; this
0x180008815  mov     rdx, r14; unsigned __int16 *
0x180008818  call    ?ClearEntry@StrMap@@QEAAHPEBG@Z; StrMap::ClearEntry(ushort const *)
0x18000881d  test    ebx, ebx
0x18000881f  jz      short loc_18000882C
0x180008821  lea     rcx, [r15+40h]; this
0x180008825  mov     edx, ebx; unsigned int
0x180008827  call    ?ClearEntry@DWORDMap@@QEAAHK@Z; DWORDMap::ClearEntry(ulong)
0x18000882c  xor     ebx, ebx
0x18000882e  jmp     short loc_180008835
0x180008830  mov     ebx, 80005008h
0x180008835  mov     rcx, [rdi+28h]; struct IMSAdminBaseW *
0x180008839  test    rcx, rcx
0x18000883c  jz      short loc_180008849
0x18000883e  test    esi, esi
0x180008840  jz      short loc_180008849
0x180008842  mov     edx, esi; unsigned int
0x180008844  call    ?CloseAdminBaseKey@@YAXPEAUIMSAdminBaseW@@K@Z; CloseAdminBaseKey(IMSAdminBaseW *,ulong)
0x180008849  mov     eax, ebx
0x18000884b  jmp     short loc_180008852
0x18000884d  mov     eax, 80004003h
0x180008852  lea     r11, [rsp+50h+var_s0]
0x180008857  mov     rbx, [r11+30h]
0x18000885b  mov     rsi, [r11+40h]
0x18000885f  mov     rsp, r11
0x180008862  pop     r15
0x180008864  pop     r14
0x180008866  pop     r12
0x180008868  pop     rdi
0x180008869  pop     rbp
0x18000886a  retn
```
