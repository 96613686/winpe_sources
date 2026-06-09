# UIAPP::~UIAPP(void)

- ea: `0x1801a9364`
- end: `0x1801a96c8`
- name: `??1UIAPP@@QEAA@XZ`
- size: `868`
- prototype: `void __fastcall(UIAPP *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x1801a865c`
- `0x1801a9ce8`

## callees

- `0x1800f1bf0`
- `0x1800fbfb4`
- `0x1800ffc38`
- `0x18011731c`
- `0x180139600`
- `0x18014275c`
- `0x180144ac4`
- `0x1801a84e0`
- `0x1801a9364`
- `0x1801f5244`
- `0x1802223a0`
- `0x18022a858`
- `0x180248f78`
- `0x18025ae08`
- `0x18025cef0`
- `0x180289b60`

## import_xrefs

- `GDI32!DeleteObject` at `0x1801a94b2`
- `GDI32!DeleteObject` at `0x1801a94d1`
- `GDI32!DeleteObject` at `0x1801a94b2`
- `GDI32!DeleteObject` at `0x1801a94d1`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a937c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a939f`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a93b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a93c1`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a93d2`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a93e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a937c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a939f`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a93b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a93c1`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a93d2`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a93e3`

## pseudocode

```c
void __fastcall UIAPP::~UIAPP(UIAPP *this)
{
  POPUPTIP *v1; // [rsp+20h] [rbp-50h]
  NAMELIST *v2; // [rsp+28h] [rbp-48h]
  VALUETIP *v3; // [rsp+30h] [rbp-40h]

  SysFreeString(*((BSTR *)this + 250));
  CALLSTACK_ITEM::DeleteList((UIAPP *)((char *)this + 920));
  SysFreeString(*((BSTR *)this + 118));
  SysFreeString(*((BSTR *)this + 119));
  SysFreeString(*((BSTR *)this + 120));
  SysFreeString(*((BSTR *)this + 58));
  SysFreeString(*((BSTR *)this + 59));
  operator delete(*((void **)this + 100));
  if ( *((_QWORD *)this + 66) )
  {
    SysFreeStringA(*(_QWORD *)(*((_QWORD *)this + 66) + 16LL));
    SysFreeStringA(*(_QWORD *)(*((_QWORD *)this + 66) + 8LL));
    ProfMemFree(*((_QWORD *)this + 66));
  }
  SysFreeStringA(*((_QWORD *)this + 121));
  SysFreeStringA(*((_QWORD *)this + 122));
  SysFreeStringA(*((_QWORD *)this + 123));
  SysFreeStringA(*((_QWORD *)this + 124));
  SysFreeStringA(*((_QWORD *)this + 125));
  if ( *((_QWORD *)this + 127) )
    DeleteObject(*((HGDIOBJ *)this + 127));
  if ( *((_QWORD *)this + 126) )
    DeleteObject(*((HGDIOBJ *)this + 126));
  ProfMemFree(*((_QWORD *)this + 206));
  DestroyEbrefdlg(*((struct EBREFDLG **)this + 103));
  v2 = (NAMELIST *)*((_QWORD *)this + 238);
  if ( v2 )
  {
    NAMELIST::~NAMELIST(v2);
    CZeroInit::operator delete(v2);
  }
  v1 = (POPUPTIP *)*((_QWORD *)this + 239);
  if ( v1 )
  {
    POPUPTIP::~POPUPTIP(v1);
    CZeroInit::operator delete(v1);
  }
  v3 = (VALUETIP *)*((_QWORD *)this + 240);
  if ( v3 )
  {
    VALUETIP::~VALUETIP(v3);
    CZeroInit::operator delete(v3);
  }
  ERRINFO::~ERRINFO((UIAPP *)((char *)this + 1984));
  PROJLIST::Clear((UIAPP *)((char *)this + 1624));
  PROJLIST::Clear((UIAPP *)((char *)this + 1608));
  CACHELN::~CACHELN((UIAPP *)((char *)this + 1504));
  CACHELN::~CACHELN((UIAPP *)((char *)this + 1400));
  CACHELN::~CACHELN((UIAPP *)((char *)this + 1296));
  CACHELN::~CACHELN((UIAPP *)((char *)this + 1192));
  CACHELN::~CACHELN((UIAPP *)((char *)this + 1088));
  BTSRC_ERR::~BTSRC_ERR((UIAPP *)((char *)this + 1032));
  BPMGR::~BPMGR((UIAPP *)((char *)this + 896));
  DWIN::~DWIN((UIAPP *)((char *)this + 352));
}

```

## disassembly

```asm
0x1801a9364  mov     [rsp-8+arg_0], rcx
0x1801a9369  push    rbp
0x1801a936a  mov     rbp, rsp
0x1801a936d  sub     rsp, 70h
0x1801a9371  mov     rax, [rbp+arg_0]
0x1801a9375  mov     rcx, [rax+7D0h]; bstrString
0x1801a937c  call    cs:__imp_SysFreeString
0x1801a9382  mov     rax, [rbp+arg_0]
0x1801a9386  add     rax, 398h
0x1801a938c  mov     rcx, rax; this
0x1801a938f  call    ?DeleteList@CALLSTACK_ITEM@@QEAAXXZ; CALLSTACK_ITEM::DeleteList(void)
0x1801a9394  mov     rax, [rbp+arg_0]
0x1801a9398  mov     rcx, [rax+3B0h]; bstrString
0x1801a939f  call    cs:__imp_SysFreeString
0x1801a93a5  mov     rax, [rbp+arg_0]
0x1801a93a9  mov     rcx, [rax+3B8h]; bstrString
0x1801a93b0  call    cs:__imp_SysFreeString
0x1801a93b6  mov     rax, [rbp+arg_0]
0x1801a93ba  mov     rcx, [rax+3C0h]; bstrString
0x1801a93c1  call    cs:__imp_SysFreeString
0x1801a93c7  mov     rax, [rbp+arg_0]
0x1801a93cb  mov     rcx, [rax+1D0h]; bstrString
0x1801a93d2  call    cs:__imp_SysFreeString
0x1801a93d8  mov     rax, [rbp+arg_0]
0x1801a93dc  mov     rcx, [rax+1D8h]; bstrString
0x1801a93e3  call    cs:__imp_SysFreeString
0x1801a93e9  mov     rax, [rbp+arg_0]
0x1801a93ed  mov     rax, [rax+320h]
0x1801a93f4  mov     [rsp+70h+var_10], rax
0x1801a93f9  mov     rcx, [rsp+70h+var_10]; void *
0x1801a93fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801a9403  mov     rax, [rbp+arg_0]
0x1801a9407  cmp     qword ptr [rax+210h], 0
0x1801a940f  jz      short loc_1801A9449
0x1801a9411  mov     rax, [rbp+arg_0]
0x1801a9415  mov     rax, [rax+210h]
0x1801a941c  mov     rcx, [rax+10h]
0x1801a9420  call    SysFreeStringA
0x1801a9425  mov     rax, [rbp+arg_0]
0x1801a9429  mov     rax, [rax+210h]
0x1801a9430  mov     rcx, [rax+8]
0x1801a9434  call    SysFreeStringA
0x1801a9439  mov     rax, [rbp+arg_0]
0x1801a943d  mov     rcx, [rax+210h]
0x1801a9444  call    ProfMemFree
0x1801a9449  mov     rax, [rbp+arg_0]
0x1801a944d  mov     rcx, [rax+3C8h]
0x1801a9454  call    SysFreeStringA
0x1801a9459  mov     rax, [rbp+arg_0]
0x1801a945d  mov     rcx, [rax+3D0h]
0x1801a9464  call    SysFreeStringA
0x1801a9469  mov     rax, [rbp+arg_0]
0x1801a946d  mov     rcx, [rax+3D8h]
0x1801a9474  call    SysFreeStringA
0x1801a9479  mov     rax, [rbp+arg_0]
0x1801a947d  mov     rcx, [rax+3E0h]
0x1801a9484  call    SysFreeStringA
0x1801a9489  mov     rax, [rbp+arg_0]
0x1801a948d  mov     rcx, [rax+3E8h]
0x1801a9494  call    SysFreeStringA
0x1801a9499  mov     rax, [rbp+arg_0]
0x1801a949d  cmp     qword ptr [rax+3F8h], 0
0x1801a94a5  jz      short loc_1801A94B8
0x1801a94a7  mov     rax, [rbp+arg_0]
0x1801a94ab  mov     rcx, [rax+3F8h]; ho
0x1801a94b2  call    cs:__imp_DeleteObject
0x1801a94b8  mov     rax, [rbp+arg_0]
0x1801a94bc  cmp     qword ptr [rax+3F0h], 0
0x1801a94c4  jz      short loc_1801A94D7
0x1801a94c6  mov     rax, [rbp+arg_0]
0x1801a94ca  mov     rcx, [rax+3F0h]; ho
0x1801a94d1  call    cs:__imp_DeleteObject
0x1801a94d7  mov     rax, [rbp+arg_0]
0x1801a94db  mov     rcx, [rax+670h]
0x1801a94e2  call    ProfMemFree
0x1801a94e7  mov     rax, [rbp+arg_0]
0x1801a94eb  mov     rcx, [rax+338h]; struct EBREFDLG *
0x1801a94f2  call    ?DestroyEbrefdlg@@YAXPEAUEBREFDLG@@@Z; DestroyEbrefdlg(EBREFDLG *)
0x1801a94f7  mov     rax, [rbp+arg_0]
0x1801a94fb  mov     rax, [rax+770h]
0x1801a9502  mov     [rsp+70h+var_38], rax
0x1801a9507  mov     rax, [rsp+70h+var_38]
0x1801a950c  mov     [rsp+70h+var_48], rax
0x1801a9511  cmp     [rsp+70h+var_48], 0
0x1801a9517  jz      short loc_1801A9545
0x1801a9519  mov     rcx, [rsp+70h+var_48]; this
0x1801a951e  call    ??1NAMELIST@@QEAA@XZ; NAMELIST::~NAMELIST(void)
0x1801a9523  mov     eax, 1
0x1801a9528  and     eax, 1
0x1801a952b  test    eax, eax
0x1801a952d  jz      short loc_1801A9539
0x1801a952f  mov     rcx, [rsp+70h+var_48]; void *
0x1801a9534  call    ??3CZeroInit@@SAXPEAX@Z; CZeroInit::operator delete(void *)
0x1801a9539  mov     rax, [rsp+70h+var_48]
0x1801a953e  mov     [rsp+70h+var_20], rax
0x1801a9543  jmp     short loc_1801A954E
0x1801a9545  mov     [rsp+70h+var_20], 0
0x1801a954e  mov     rax, [rbp+arg_0]
0x1801a9552  mov     rax, [rax+778h]
0x1801a9559  mov     [rsp+70h+var_30], rax
0x1801a955e  mov     rax, [rsp+70h+var_30]
0x1801a9563  mov     [rsp+70h+var_50], rax
0x1801a9568  cmp     [rsp+70h+var_50], 0
0x1801a956e  jz      short loc_1801A959C
0x1801a9570  mov     rcx, [rsp+70h+var_50]; this
0x1801a9575  call    ??1POPUPTIP@@QEAA@XZ; POPUPTIP::~POPUPTIP(void)
0x1801a957a  mov     eax, 1
0x1801a957f  and     eax, 1
0x1801a9582  test    eax, eax
0x1801a9584  jz      short loc_1801A9590
0x1801a9586  mov     rcx, [rsp+70h+var_50]; void *
0x1801a958b  call    ??3CZeroInit@@SAXPEAX@Z; CZeroInit::operator delete(void *)
0x1801a9590  mov     rax, [rsp+70h+var_50]
0x1801a9595  mov     [rsp+70h+var_28], rax
0x1801a959a  jmp     short loc_1801A95A5
0x1801a959c  mov     [rsp+70h+var_28], 0
0x1801a95a5  mov     rax, [rbp+arg_0]
0x1801a95a9  mov     rax, [rax+780h]
0x1801a95b0  mov     [rsp+70h+var_18], rax
0x1801a95b5  mov     rax, [rsp+70h+var_18]
0x1801a95ba  mov     [rsp+70h+var_40], rax
0x1801a95bf  cmp     [rsp+70h+var_40], 0
0x1801a95c5  jz      short loc_1801A95F3
0x1801a95c7  mov     rcx, [rsp+70h+var_40]; this
0x1801a95cc  call    ??1VALUETIP@@QEAA@XZ; VALUETIP::~VALUETIP(void)
0x1801a95d1  mov     eax, 1
0x1801a95d6  and     eax, 1
0x1801a95d9  test    eax, eax
0x1801a95db  jz      short loc_1801A95E7
0x1801a95dd  mov     rcx, [rsp+70h+var_40]; void *
0x1801a95e2  call    ??3CZeroInit@@SAXPEAX@Z; CZeroInit::operator delete(void *)
0x1801a95e7  mov     rax, [rsp+70h+var_40]
0x1801a95ec  mov     [rsp+70h+var_8], rax
0x1801a95f1  jmp     short loc_1801A95FC
0x1801a95f3  mov     [rsp+70h+var_8], 0
0x1801a95fc  mov     rax, [rbp+arg_0]
0x1801a9600  add     rax, 7C0h
0x1801a9606  mov     rcx, rax; this
0x1801a9609  call    ??1ERRINFO@@QEAA@XZ; ERRINFO::~ERRINFO(void)
0x1801a960e  mov     rax, [rbp+arg_0]
0x1801a9612  add     rax, 658h
0x1801a9618  mov     rcx, rax; this
0x1801a961b  call    ?Clear@PROJLIST@@QEAAXXZ; PROJLIST::Clear(void)
0x1801a9620  mov     rax, [rbp+arg_0]
0x1801a9624  add     rax, 648h
0x1801a962a  mov     rcx, rax; this
0x1801a962d  call    ?Clear@PROJLIST@@QEAAXXZ; PROJLIST::Clear(void)
0x1801a9632  mov     rax, [rbp+arg_0]
0x1801a9636  add     rax, 5E0h
0x1801a963c  mov     rcx, rax; this
0x1801a963f  call    ??1CACHELN@@UEAA@XZ; CACHELN::~CACHELN(void)
0x1801a9644  mov     rax, [rbp+arg_0]
0x1801a9648  add     rax, 578h
0x1801a964e  mov     rcx, rax; this
0x1801a9651  call    ??1CACHELN@@UEAA@XZ; CACHELN::~CACHELN(void)
0x1801a9656  mov     rax, [rbp+arg_0]
0x1801a965a  add     rax, 510h
0x1801a9660  mov     rcx, rax; this
0x1801a9663  call    ??1CACHELN@@UEAA@XZ; CACHELN::~CACHELN(void)
0x1801a9668  mov     rax, [rbp+arg_0]
0x1801a966c  add     rax, 4A8h
0x1801a9672  mov     rcx, rax; this
0x1801a9675  call    ??1CACHELN@@UEAA@XZ; CACHELN::~CACHELN(void)
0x1801a967a  mov     rax, [rbp+arg_0]
0x1801a967e  add     rax, 440h
0x1801a9684  mov     rcx, rax; this
0x1801a9687  call    ??1CACHELN@@UEAA@XZ; CACHELN::~CACHELN(void)
0x1801a968c  mov     rax, [rbp+arg_0]
0x1801a9690  add     rax, 408h
0x1801a9696  mov     rcx, rax; this
0x1801a9699  call    ??1BTSRC_ERR@@QEAA@XZ; BTSRC_ERR::~BTSRC_ERR(void)
0x1801a969e  mov     rax, [rbp+arg_0]
0x1801a96a2  add     rax, 380h
0x1801a96a8  mov     rcx, rax; this
0x1801a96ab  call    ??1BPMGR@@QEAA@XZ; BPMGR::~BPMGR(void)
0x1801a96b0  mov     rax, [rbp+arg_0]
0x1801a96b4  add     rax, 160h
0x1801a96ba  mov     rcx, rax; this
0x1801a96bd  call    ??1DWIN@@QEAA@XZ; DWIN::~DWIN(void)
0x1801a96c2  add     rsp, 70h
0x1801a96c6  pop     rbp
0x1801a96c7  retn
```
