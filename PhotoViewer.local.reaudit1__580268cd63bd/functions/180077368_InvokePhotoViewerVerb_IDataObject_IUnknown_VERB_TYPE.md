# InvokePhotoViewerVerb(IDataObject *,IUnknown *,VERB_TYPE)

- ea: `0x180077368`
- end: `0x180077563`
- name: `?InvokePhotoViewerVerb@@YAJPEAUIDataObject@@PEAUIUnknown@@W4VERB_TYPE@@@Z`
- size: `507`
- prototype: `int __high(struct IDataObject *, struct IUnknown *, enum VERB_TYPE)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800771c0`
- `0x180077270`
- `0x180077610`
- `0x180077780`
- `0x1800778f0`

## callees

- `0x1800037d8`
- `0x180004908`
- `0x18000cb74`
- `0x18004b3d0`
- `0x1800728e4`
- `0x180077368`
- `0x180080010`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x180077380`
- `USER32!GetSystemMetrics` at `0x180077380`
- `ole32!CoCreateInstance` at `0x18007743d`
- `ole32!CoCreateInstance` at `0x1800774b8`
- `ole32!CoCreateInstance` at `0x18007743d`
- `ole32!CoCreateInstance` at `0x1800774b8`
- `ole32!CoAllowSetForegroundWindow` at `0x180077456`
- `ole32!CoAllowSetForegroundWindow` at `0x180077456`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x180077464`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x180077464`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180077449`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800774a4`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800774c4`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800774e7`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180077530`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180077449`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800774a4`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800774c4`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800774e7`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180077530`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall InvokePhotoViewerVerb(__int64 a1, IUnknown *a2, unsigned int a3)
{
  TRACEHANDLE v7; // r8
  GUID *v8; // r9
  IUnknown *v9; // rdx
  HRESULT Instance; // eax
  int v11; // edx
  int v12; // edx
  __int64 v13; // rcx
  HRESULT v14; // eax
  int v15; // edx
  int v16; // eax
  int v17; // edx
  int v18; // eax
  int v19; // edx
  unsigned int ppv; // [rsp+20h] [rbp-68h]
  LPVOID *ppva; // [rsp+20h] [rbp-68h]
  IUnknown *pUnk; // [rsp+30h] [rbp-58h] BYREF
  __int64 v23; // [rsp+38h] [rbp-50h] BYREF
  HWND v24; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int16 *v25[8]; // [rsp+48h] [rbp-40h] BYREF
  int v26; // [rsp+A8h] [rbp+20h] BYREF

  if ( GetSystemMetrics(67) )
  {
    Base::ResourceString::ResourceString((Base::ResourceString *)v25, 0xBC1u);
    Base::ResourceString::ResourceString((Base::ResourceString *)&v24, 0xBFCu);
    UIBase::MessageBoxRTL(0, v24, v25[0], (const unsigned __int16 *)0x30, ppv);
    Base::String::~String((Base::String *)&v24);
    Base::String::~String((Base::String *)v25);
    return 1;
  }
  else
  {
    if ( a3 < 2 || a3 == 3 )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 7);
      if ( v7 )
        WPP::PrivateTraceEvent((WPP *)PIX_PHOTOVIEWER_PERF_TRACE_GUID, (const struct _GUID *)0x2C, v7, 0);
    }
    pUnk = 0;
    v8 = &GUID_00000122_0000_0000_c000_000000000046;
    v9 = 0;
    ppva = (LPVOID *)&pUnk;
    if ( a3 - 3 <= 3 )
      goto LABEL_15;
    Instance = CoCreateInstance(
                 &CLSID_PhotoViewerLocalServer,
                 0,
                 4u,
                 &GUID_00000122_0000_0000_c000_000000000046,
                 (LPVOID *)&pUnk);
    if ( Instance < 0 )
      Base::Throw((Base *)(unsigned int)Instance, v11);
    CoAllowSetForegroundWindow(pUnk, 0);
    while ( 1 )
    {
      IUnknown_SetSite(pUnk, a2);
      v13 = 0;
      v23 = 0;
      if ( pUnk )
      {
        ((void (__fastcall *)(IUnknown *, GUID *, __int64 *))pUnk->lpVtbl->QueryInterface)(
          pUnk,
          &GUID_b7d14566_0509_4cce_a71f_0a554233bd9b,
          &v23);
        v13 = v23;
      }
      if ( v13 )
        break;
      Base::Throw((Base *)0x80004002LL, v12);
LABEL_15:
      v14 = CoCreateInstance(&CLSID_PhotoViewerDropTarget, v9, 1u, v8, ppva);
      if ( v14 < 0 )
      {
        Base::Throw((Base *)(unsigned int)v14, v15);
        break;
      }
    }
    v16 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, _QWORD))(*(_QWORD *)v13 + 24LL))(v13, &WindowName, a3);
    if ( v16 < 0 )
      Base::Throw((Base *)(unsigned int)v16, v17);
    v26 = 1;
    v25[0] = 0;
    v18 = ((__int64 (__fastcall *)(IUnknown *, __int64, _QWORD, _QWORD, int *))pUnk->lpVtbl[2].QueryInterface)(
            pUnk,
            a1,
            0,
            0,
            &v26);
    if ( v18 < 0 )
      Base::Throw((Base *)(unsigned int)v18, v19);
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v23);
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&pUnk);
    return 0;
  }
}

```

## disassembly

```asm
0x180077368  push    rbx
0x18007736a  push    rsi
0x18007736b  push    rdi
0x18007736c  push    r14
0x18007736e  sub     rsp, 68h
0x180077372  mov     ebx, r8d
0x180077375  mov     rsi, rdx
0x180077378  mov     r14, rcx
0x18007737b  xor     edi, edi
0x18007737d  lea     ecx, [rdi+43h]; nIndex
0x180077380  call    cs:__imp_GetSystemMetrics
0x180077386  test    eax, eax
0x180077388  jz      short loc_1800773DB
0x18007738a  mov     edx, 0BC1h; unsigned int
0x18007738f  lea     rcx, [rsp+88h+var_40]; this
0x180077394  call    ??0ResourceString@Base@@QEAA@I@Z; Base::ResourceString::ResourceString(uint)
0x180077399  nop
0x18007739a  mov     edx, 0BFCh; unsigned int
0x18007739f  lea     rcx, [rsp+88h+var_48]; this
0x1800773a4  call    ??0ResourceString@Base@@QEAA@I@Z; Base::ResourceString::ResourceString(uint)
0x1800773a9  lea     r9d, [rdi+30h]; unsigned __int16 *
0x1800773ad  mov     r8, [rsp+88h+var_40]; unsigned __int16 *
0x1800773b2  mov     rdx, [rsp+88h+var_48]; HWND
0x1800773b7  xor     ecx, ecx; this
0x1800773b9  call    ?MessageBoxRTL@UIBase@@YAHPEAUHWND__@@PEBG1I@Z; UIBase::MessageBoxRTL(HWND__ *,ushort const *,ushort const *,uint)
0x1800773be  lea     rcx, [rsp+88h+var_48]; this
0x1800773c3  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x1800773c8  nop
0x1800773c9  lea     rcx, [rsp+88h+var_40]; this
0x1800773ce  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x1800773d3  lea     eax, [rdi+1]
0x1800773d6  jmp     loc_180077558
0x1800773db  mov     ecx, ebx
0x1800773dd  test    ebx, ebx
0x1800773df  jz      short loc_1800773EB
0x1800773e1  sub     ecx, 1
0x1800773e4  jz      short loc_1800773EB
0x1800773e6  cmp     ecx, 2
0x1800773e9  jnz     short loc_18007740E
0x1800773eb  mov     rax, cs:WPP_GLOBAL_Control
0x1800773f2  mov     r8, [rax+38h]; unsigned int
0x1800773f6  test    r8, r8
0x1800773f9  jz      short loc_18007740E
0x1800773fb  xor     r9d, r9d; unsigned __int64
0x1800773fe  lea     edx, [r9+2Ch]; struct _GUID *
0x180077402  lea     rcx, PIX_PHOTOVIEWER_PERF_TRACE_GUID; this
0x180077409  call    ?PrivateTraceEvent@WPP@@YAXPEBU_GUID@@K_KE@Z; WPP::PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18007740e  mov     [rsp+88h+pUnk], 0
0x180077417  lea     eax, [rbx-3]
0x18007741a  lea     r9, _GUID_00000122_0000_0000_c000_000000000046; riid
0x180077421  xor     edx, edx; pUnkOuter
0x180077423  cmp     eax, 3
0x180077426  lea     rax, [rsp+88h+pUnk]
0x18007742b  mov     [rsp+88h+ppv], rax; ppv
0x180077430  jbe     short loc_1800774AB
0x180077432  lea     r8d, [rdx+4]; dwClsContext
0x180077436  lea     rcx, CLSID_PhotoViewerLocalServer; rclsid
0x18007743d  call    cs:__imp_CoCreateInstance
0x180077443  test    eax, eax
0x180077445  jns     short loc_18007744F
0x180077447  mov     ecx, eax
0x180077449  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18007744f  xor     edx, edx; lpvReserved
0x180077451  mov     rcx, [rsp+88h+pUnk]; pUnk
0x180077456  call    cs:__imp_CoAllowSetForegroundWindow
0x18007745c  mov     rdx, rsi; punkSite
0x18007745f  mov     rcx, [rsp+88h+pUnk]; punk
0x180077464  call    cs:__imp_IUnknown_SetSite
0x18007746a  mov     r9, [rsp+88h+pUnk]
0x18007746f  xor     ecx, ecx
0x180077471  mov     [rsp+88h+var_50], rcx
0x180077476  test    r9, r9
0x180077479  jz      short loc_18007749A
0x18007747b  mov     rax, [r9]
0x18007747e  lea     r8, [rsp+88h+var_50]
0x180077483  lea     rdx, _GUID_b7d14566_0509_4cce_a71f_0a554233bd9b
0x18007748a  mov     rcx, r9
0x18007748d  mov     rax, [rax]
0x180077490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077495  mov     rcx, [rsp+88h+var_50]
0x18007749a  test    rcx, rcx
0x18007749d  jnz     short loc_1800774CB
0x18007749f  mov     ecx, 80004002h
0x1800774a4  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x1800774aa  nop
0x1800774ab  mov     r8d, 1; dwClsContext
0x1800774b1  lea     rcx, CLSID_PhotoViewerDropTarget; rclsid
0x1800774b8  call    cs:__imp_CoCreateInstance
0x1800774be  test    eax, eax
0x1800774c0  jns     short loc_18007745C
0x1800774c2  mov     ecx, eax
0x1800774c4  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x1800774ca  nop
0x1800774cb  mov     rax, [rcx]
0x1800774ce  mov     r8d, ebx
0x1800774d1  lea     rdx, WindowName
0x1800774d8  mov     rax, [rax+18h]
0x1800774dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800774e1  test    eax, eax
0x1800774e3  jns     short loc_1800774ED
0x1800774e5  mov     ecx, eax
0x1800774e7  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x1800774ed  mov     [rsp+88h+arg_18], 1
0x1800774f8  mov     [rsp+88h+var_40], 0
0x180077501  mov     rcx, [rsp+88h+pUnk]
0x180077506  mov     rax, [rcx]
0x180077509  lea     rdx, [rsp+88h+arg_18]
0x180077511  mov     [rsp+88h+ppv], rdx
0x180077516  mov     r9, [rsp+88h+var_40]
0x18007751b  xor     r8d, r8d
0x18007751e  mov     rdx, r14
0x180077521  mov     rax, [rax+30h]
0x180077525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007752a  test    eax, eax
0x18007752c  jns     short loc_180077537
0x18007752e  mov     ecx, eax
0x180077530  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180077536  nop
0x180077537  lea     rcx, [rsp+88h+var_50]
0x18007753c  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180077541  nop
0x180077542  lea     rcx, [rsp+88h+pUnk]
0x180077547  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18007754c  nop
0x18007754d  jmp     short loc_180077556
0x18007754f  mov     edi, [rsp+88h+arg_18]
0x180077556  mov     eax, edi
0x180077558  add     rsp, 68h
0x18007755c  pop     r14
0x18007755e  pop     rdi
0x18007755f  pop     rsi
0x180077560  pop     rbx
0x180077561  retn
```
