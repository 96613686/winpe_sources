# PhotoDocument::GetThumbnail(ISharedBitmap * *,int)

- ea: `0x180029f30`
- end: `0x18002a0ac`
- name: `?GetThumbnail@PhotoDocument@@AEAAXPEAPEAUISharedBitmap@@H@Z`
- size: `380`
- prototype: `void __fastcall(PhotoDocument *__hidden this, struct ISharedBitmap **, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000cf20`

## callees

- `0x18000cb74`
- `0x180021a90`
- `0x180029f30`
- `0x1800320a8`
- `0x1800361ac`
- `0x180080010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180029ff1`
- `KERNEL32!GetTickCount` at `0x180029ff1`
- `ole32!CoCreateInstance` at `0x180029fae`
- `ole32!CoCreateInstance` at `0x180029fae`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180029f4f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180029f82`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180029fba`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180029f4f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180029f82`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180029fba`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall PhotoDocument::GetThumbnail(PhotoDocument *this, struct ISharedBitmap **a2, int a3)
{
  int v5; // eax
  int v6; // edx
  HRESULT v7; // eax
  const unsigned __int16 *v8; // rdx
  const unsigned __int16 *v9; // rcx
  bool v10; // r8
  BOOL BoolRegValue; // esi
  bool v12; // r8
  unsigned int v13; // ebx
  DWORD TickCount; // eax
  struct ISharedBitmap *v15; // rcx
  __int64 v16; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v17[24]; // [rsp+48h] [rbp-18h] BYREF
  struct ISharedBitmap *v18; // [rsp+88h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+38h] BYREF

  if ( !a2 )
  {
    Base::Throw((Base *)0x80004003LL, 0);
    __debugbreak();
  }
  v16 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(**((_QWORD **)this + 42) + 112LL))(
         *((_QWORD *)this + 42),
         &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
         &v16);
  if ( v5 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v5, v6);
    __debugbreak();
  }
  ppv = 0;
  v7 = CoCreateInstance(
         &GUID_50ef4544_ac9f_4a8e_b21b_8a26180db13f,
         0,
         0x17u,
         &GUID_f676c15d_596a_4ce2_8234_33996f445db1,
         &ppv);
  if ( v7 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v7, (_DWORD)v8);
    __debugbreak();
  }
  BoolRegValue = GetBoolRegValue(v9, v8, v10);
  if ( a3 == 1 )
  {
    v13 = 256;
  }
  else if ( a3 == 2 )
  {
    v13 = 1024;
  }
  else
  {
    ATL::CCritSecLock::CCritSecLock(
      (ATL::CCritSecLock *)v17,
      (struct _RTL_CRITICAL_SECTION *)PhotoDocument::s_critSecThumbnailRequestTicks,
      v12);
    TickCount = GetTickCount();
    if ( TickCount > PhotoDocument::s_dwLastThumbnailRequestTicks + 200
      || (v13 = 256, TickCount < PhotoDocument::s_dwLastThumbnailRequestTicks) )
    {
      v13 = 1024;
    }
    PhotoDocument::s_dwLastThumbnailRequestTicks = TickCount;
    ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v17);
  }
  v18 = 0;
  if ( (*(int (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD, struct ISharedBitmap **, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
         ppv,
         v16,
         v13,
         (unsigned int)(BoolRegValue + 1),
         &v18,
         0,
         0) >= 0 )
  {
    v15 = v18;
    *a2 = v18;
    if ( v15 )
      ((void (__fastcall *)(struct ISharedBitmap *))v15->lpVtbl->AddRef)(v15);
  }
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v18);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppv);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v16);
}

```

## disassembly

```asm
0x180029f30  mov     [rsp-18h+arg_0], rbx
0x180029f35  push    rbp
0x180029f36  push    rsi
0x180029f37  push    rdi
0x180029f38  mov     rbp, rsp
0x180029f3b  sub     rsp, 60h
0x180029f3f  mov     ebx, r8d
0x180029f42  mov     rdi, rdx
0x180029f45  test    rdx, rdx
0x180029f48  jnz     short loc_180029F56
0x180029f4a  mov     ecx, 80004003h
0x180029f4f  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180029f55  int     3; Trap to Debugger
0x180029f56  mov     [rbp+var_20], 0
0x180029f5e  mov     rcx, [rcx+150h]
0x180029f65  mov     rax, [rcx]
0x180029f68  lea     r8, [rbp+var_20]
0x180029f6c  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180029f73  mov     rax, [rax+70h]
0x180029f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f7c  test    eax, eax
0x180029f7e  jns     short loc_180029F89
0x180029f80  mov     ecx, eax
0x180029f82  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180029f88  int     3; Trap to Debugger
0x180029f89  mov     [rbp+arg_18], 0
0x180029f91  lea     rax, [rbp+arg_18]
0x180029f95  mov     [rsp+60h+ppv], rax; ppv
0x180029f9a  lea     r9, _GUID_f676c15d_596a_4ce2_8234_33996f445db1; riid
0x180029fa1  xor     edx, edx; pUnkOuter
0x180029fa3  lea     r8d, [rdx+17h]; dwClsContext
0x180029fa7  lea     rcx, _GUID_50ef4544_ac9f_4a8e_b21b_8a26180db13f; rclsid
0x180029fae  call    cs:__imp_CoCreateInstance
0x180029fb4  test    eax, eax
0x180029fb6  jns     short loc_180029FC1
0x180029fb8  mov     ecx, eax
0x180029fba  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180029fc0  int     3; Trap to Debugger
0x180029fc1  call    ?GetBoolRegValue@@YA_NPEBG0_N@Z; GetBoolRegValue(ushort const *,ushort const *,bool)
0x180029fc6  movzx   esi, al
0x180029fc9  cmp     ebx, 1
0x180029fcc  jnz     short loc_180029FD5
0x180029fce  mov     ebx, 100h
0x180029fd3  jmp     short loc_18002A024
0x180029fd5  cmp     ebx, 2
0x180029fd8  jnz     short loc_180029FE1
0x180029fda  mov     ebx, 400h
0x180029fdf  jmp     short loc_18002A024
0x180029fe1  lea     rdx, ?s_critSecThumbnailRequestTicks@PhotoDocument@@0VCCriticalSection@ATL@@A; struct _RTL_CRITICAL_SECTION *
0x180029fe8  lea     rcx, [rbp+var_18]; this
0x180029fec  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x180029ff1  call    cs:__imp_GetTickCount
0x180029ff7  mov     edx, cs:?s_dwLastThumbnailRequestTicks@PhotoDocument@@0KA; ulong PhotoDocument::s_dwLastThumbnailRequestTicks
0x180029ffd  lea     ecx, [rdx+0C8h]
0x18002a003  cmp     eax, ecx
0x18002a005  ja      short loc_18002A010
0x18002a007  cmp     eax, edx
0x18002a009  mov     ebx, 100h
0x18002a00e  jnb     short loc_18002A015
0x18002a010  mov     ebx, 400h
0x18002a015  mov     cs:?s_dwLastThumbnailRequestTicks@PhotoDocument@@0KA, eax; ulong PhotoDocument::s_dwLastThumbnailRequestTicks
0x18002a01b  lea     rcx, [rbp+var_18]; this
0x18002a01f  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x18002a024  mov     [rbp+arg_8], 0
0x18002a02c  mov     rcx, [rbp+arg_18]
0x18002a030  mov     rax, [rcx]
0x18002a033  mov     [rsp+60h+var_30], 0
0x18002a03c  mov     [rsp+60h+var_38], 0
0x18002a045  lea     rdx, [rbp+arg_8]
0x18002a049  mov     [rsp+60h+ppv], rdx
0x18002a04e  lea     r9d, [rsi+1]
0x18002a052  mov     r8d, ebx
0x18002a055  mov     rdx, [rbp+var_20]
0x18002a059  mov     rax, [rax+18h]
0x18002a05d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a062  test    eax, eax
0x18002a064  js      short loc_18002A07F
0x18002a066  mov     rcx, [rbp+arg_8]
0x18002a06a  mov     [rdi], rcx
0x18002a06d  test    rcx, rcx
0x18002a070  jz      short loc_18002A07F
0x18002a072  mov     rax, [rcx]
0x18002a075  mov     rax, [rax+8]
0x18002a079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a07e  nop
0x18002a07f  lea     rcx, [rbp+arg_8]
0x18002a083  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18002a088  nop
0x18002a089  lea     rcx, [rbp+arg_18]
0x18002a08d  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18002a092  nop
0x18002a093  lea     rcx, [rbp+var_20]
0x18002a097  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18002a09c  mov     rbx, [rsp+60h+arg_0]
0x18002a0a4  add     rsp, 60h
0x18002a0a8  pop     rdi
0x18002a0a9  pop     rsi
0x18002a0aa  pop     rbp
0x18002a0ab  retn
```
