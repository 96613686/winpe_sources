# COCInstallHelper::GetUpdateDisplayName(ushort const *,ushort *,ulong)

- ea: `0x18003036c`
- end: `0x180030457`
- name: `?GetUpdateDisplayName@COCInstallHelper@@QEAAJPEBGPEAGK@Z`
- size: `235`
- prototype: `int(COCInstallHelper *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800260e4`

## callees

- `0x18000791c`
- `0x180008cf8`
- `0x1800227c8`
- `0x180022e20`
- `0x18003036c`
- `0x180030678`
- `0x180059010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800303f1`
- `msvcrt!_wcsicmp` at `0x1800303f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003042c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003042c`

## pseudocode

```c
__int64 __fastcall COCInstallHelper::GetUpdateDisplayName(COCInstallHelper *this, wchar_t *a2, unsigned __int16 *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  wchar_t *v8; // r8
  wchar_t *String1; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+28h] [rbp-20h] BYREF
  LPVOID ppv[3]; // [rsp+30h] [rbp-18h] BYREF

  ppv[0] = 0;
  v11 = 0;
  String1 = 0;
  v5 = COCInstallHelper::OpenFoundationPackage(this, ppv);
  v6 = v5;
  if ( v5 < 0 )
    goto LABEL_8;
  v5 = (*(__int64 (__fastcall **)(LPVOID, wchar_t *, __int64 *))(*(_QWORD *)ppv[0] + 48LL))(ppv[0], a2, &v11);
  v6 = v5;
  if ( v5 < 0 )
    goto LABEL_8;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64, wchar_t **))(*(_QWORD *)v11 + 24LL))(v11, 2, &String1);
  v6 = v5;
  if ( v5 < 0 )
    goto LABEL_8;
  if ( !String1 || (v7 = _wcsicmp(String1, &WindowName), v8 = String1, !v7) )
    v8 = a2;
  v5 = StringCchCopyW(a3, 0x104u, v8);
  v6 = v5;
  if ( v5 < 0 )
LABEL_8:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v5);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( String1 )
  {
    CoTaskMemFree(String1);
    String1 = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(ppv);
  return v6;
}

```

## disassembly

```asm
0x18003036c  push    rbp
0x18003036e  push    rbx
0x18003036f  push    rsi
0x180030370  push    rdi
0x180030371  mov     rbp, rsp
0x180030374  sub     rsp, 48h
0x180030378  mov     rsi, rdx
0x18003037b  mov     [rbp+ppv], 0
0x180030383  lea     rdx, [rbp+ppv]; ppv
0x180030387  mov     [rbp+var_20], 0
0x18003038f  mov     rdi, r8
0x180030392  mov     [rbp+String1], 0
0x18003039a  call    ?OpenFoundationPackage@COCInstallHelper@@QEAAJPEAPEAUICbsPackage@@@Z; COCInstallHelper::OpenFoundationPackage(ICbsPackage * *)
0x18003039f  mov     ebx, eax
0x1800303a1  test    eax, eax
0x1800303a3  js      short loc_180030415
0x1800303a5  mov     rcx, [rbp+ppv]
0x1800303a9  lea     r8, [rbp+var_20]
0x1800303ad  mov     rdx, rsi
0x1800303b0  mov     rax, [rcx]
0x1800303b3  mov     rax, [rax+30h]
0x1800303b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303bc  mov     ebx, eax
0x1800303be  test    eax, eax
0x1800303c0  js      short loc_180030415
0x1800303c2  mov     rcx, [rbp+var_20]
0x1800303c6  lea     r8, [rbp+String1]
0x1800303ca  mov     edx, 2
0x1800303cf  mov     rax, [rcx]
0x1800303d2  mov     rax, [rax+18h]
0x1800303d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303db  mov     ebx, eax
0x1800303dd  test    eax, eax
0x1800303df  js      short loc_180030415
0x1800303e1  mov     rcx, [rbp+String1]; String1
0x1800303e5  test    rcx, rcx
0x1800303e8  jz      short loc_1800303FF
0x1800303ea  lea     rdx, WindowName; String2
0x1800303f1  call    cs:__imp__wcsicmp
0x1800303f7  mov     r8, [rbp+String1]
0x1800303fb  test    eax, eax
0x1800303fd  jnz     short loc_180030402
0x1800303ff  mov     r8, rsi; unsigned __int16 *
0x180030402  mov     edx, 104h; unsigned __int64
0x180030407  mov     rcx, rdi; unsigned __int16 *
0x18003040a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003040f  mov     ebx, eax
0x180030411  test    eax, eax
0x180030413  jns     short loc_18003041C
0x180030415  mov     ecx, eax
0x180030417  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003041c  mov     ecx, ebx
0x18003041e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180030423  mov     rcx, [rbp+String1]; pv
0x180030427  test    rcx, rcx
0x18003042a  jz      short loc_18003043A
0x18003042c  call    cs:__imp_CoTaskMemFree
0x180030432  mov     [rbp+String1], 0
0x18003043a  lea     rcx, [rbp+var_20]
0x18003043e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180030443  lea     rcx, [rbp+ppv]
0x180030447  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003044c  mov     eax, ebx
0x18003044e  add     rsp, 48h
0x180030452  pop     rdi
0x180030453  pop     rsi
0x180030454  pop     rbx
0x180030455  pop     rbp
0x180030456  retn
```
