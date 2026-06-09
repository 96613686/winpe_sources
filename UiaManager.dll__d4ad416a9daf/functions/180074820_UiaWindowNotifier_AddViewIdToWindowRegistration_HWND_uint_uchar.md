# UiaWindowNotifier::AddViewIdToWindowRegistration(HWND__ *,uint,uchar)

- ea: `0x180074820`
- end: `0x180074919`
- name: `?AddViewIdToWindowRegistration@UiaWindowNotifier@@UEAAJPEAUHWND__@@IE@Z`
- size: `249`
- prototype: `__int64 __fastcall(UiaWindowNotifier *__hidden this, HWND, unsigned int, unsigned __int8)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800054f8`
- `0x1800067f8`
- `0x180006edc`
- `0x18000cbe8`
- `0x18000cc98`
- `0x180074820`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180074868`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180074868`

## string_xrefs

- `0x1800748a5`: `onecore\windows\accessibletech\uiamanager\dll\uiawindownotifier.cpp`

## pseudocode

```c
__int64 __fastcall UiaWindowNotifier::AddViewIdToWindowRegistration(
        UiaWindowNotifier *this,
        HWND a2,
        unsigned int a3,
        char a4)
{
  unsigned int v7; // r14d
  HRESULT v8; // eax
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // rdx
  int ppv; // [rsp+20h] [rbp-58h]
  LPVOID v14; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int64 v15; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v16[48]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v14 = 0;
  v7 = (unsigned int)a2;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  v8 = CoCreateInstance(&CLSID_UiaManager, 0, 4u, &GUID_83140d1c_7e82_4cfb_96e4_f997cede7e10, &v14);
  v10 = v8;
  if ( v8 >= 0 )
  {
    LOBYTE(v9) = a4;
    v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64))(*(_QWORD *)v14 + 32LL))(v14, v7, a3, v9);
    v10 = v8;
    if ( v8 >= 0 )
    {
      v15 = ((unsigned __int64)this + 8) & -(__int64)(this != (UiaWindowNotifier *)48);
      wil::com_weak_query<IUiaWindowNotifierCallback * &>(v16, &v15);
      ThreadSafeMap<unsigned int,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>::InsertOrAssign<wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>((std::_Mutex_base *)&UiaWindowNotifierInProcManager::s_inProcViewIdMap);
      wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(v16);
      v10 = 0;
      *((_DWORD *)this + 14) = a3;
      goto LABEL_7;
    }
    v11 = 64;
  }
  else
  {
    v11 = 59;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiawindownotifier.cpp",
    (const char *)(unsigned int)v8,
    ppv);
LABEL_7:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  return v10;
}

```

## disassembly

```asm
0x180074820  push    rbx
0x180074822  push    rbp
0x180074823  push    rsi
0x180074824  push    rdi
0x180074825  push    r14
0x180074827  sub     rsp, 50h
0x18007482b  mov     rsi, rcx
0x18007482e  mov     [rsp+78h+var_40], 0
0x180074837  lea     rcx, [rsp+78h+var_40]
0x18007483c  mov     bpl, r9b
0x18007483f  mov     edi, r8d
0x180074842  mov     r14, rdx
0x180074845  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007484a  xor     edx, edx; pUnkOuter
0x18007484c  lea     rax, [rsp+78h+var_40]
0x180074851  lea     r9, _GUID_83140d1c_7e82_4cfb_96e4_f997cede7e10; riid
0x180074858  mov     qword ptr [rsp+78h+ppv], rax; int
0x18007485d  lea     rcx, CLSID_UiaManager; rclsid
0x180074864  lea     r8d, [rdx+4]; dwClsContext
0x180074868  call    cs:__imp_CoCreateInstance
0x18007486e  mov     ebx, eax
0x180074870  test    eax, eax
0x180074872  jns     short loc_18007487B
0x180074874  mov     edx, 3Bh ; ';'
0x180074879  jmp     short loc_1800748A0
0x18007487b  mov     rcx, [rsp+78h+var_40]
0x180074880  mov     edx, r14d
0x180074883  mov     r9b, bpl
0x180074886  mov     r8d, edi
0x180074889  mov     rax, [rcx]
0x18007488c  mov     rax, [rax+20h]
0x180074890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074895  mov     ebx, eax
0x180074897  test    eax, eax
0x180074899  jns     short loc_1800748B6
0x18007489b  mov     edx, 40h ; '@'; void *
0x1800748a0  mov     rcx, [rsp+78h]; this
0x1800748a5  lea     r8, aOnecoreWindows_25; "onecore\\windows\\accessibletech\\uiama"...
0x1800748ac  mov     r9d, eax; char *
0x1800748af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800748b4  jmp     short loc_180074902
0x1800748b6  lea     rdx, [rsi+8]
0x1800748ba  mov     [rsp+78h+var_48], edi
0x1800748be  lea     rax, [rsi-30h]
0x1800748c2  neg     rax
0x1800748c5  sbb     rcx, rcx
0x1800748c8  and     rcx, rdx
0x1800748cb  lea     rdx, [rsp+78h+var_38]
0x1800748d0  mov     [rsp+78h+var_38], rcx
0x1800748d5  lea     rcx, [rsp+78h+var_30]
0x1800748da  call    ??$com_weak_query@AEAPEAUIUiaWindowNotifierCallback@@@wil@@YA?AV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@0@AEAPEAUIUiaWindowNotifierCallback@@@Z; wil::com_weak_query<IUiaWindowNotifierCallback * &>(IUiaWindowNotifierCallback * &)
0x1800748df  mov     r8, rax
0x1800748e2  lea     rdx, [rsp+78h+var_48]
0x1800748e7  lea     rcx, ?s_inProcViewIdMap@UiaWindowNotifierInProcManager@@0V?$SmartLeak@V?$ThreadSafeMap@IV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@@@@A; this
0x1800748ee  call    ??$InsertOrAssign@V?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@?$ThreadSafeMap@IV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@@QEAAXAEBI$$QEAV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@Z; ThreadSafeMap<uint,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>::InsertOrAssign<wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>(uint const &,wil::com_ptr_t<IWeakReference,wil::err_exception_policy> &&)
0x1800748f3  lea     rcx, [rsp+78h+var_30]
0x1800748f8  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x1800748fd  xor     ebx, ebx
0x1800748ff  mov     [rsi+38h], edi
0x180074902  lea     rcx, [rsp+78h+var_40]
0x180074907  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007490c  mov     eax, ebx
0x18007490e  add     rsp, 50h
0x180074912  pop     r14
0x180074914  pop     rdi
0x180074915  pop     rsi
0x180074916  pop     rbp
0x180074917  pop     rbx
0x180074918  retn
```
