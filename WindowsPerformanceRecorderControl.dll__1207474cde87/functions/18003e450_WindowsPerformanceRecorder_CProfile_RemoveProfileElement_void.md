# WindowsPerformanceRecorder::CProfile::RemoveProfileElement(void)

- ea: `0x18003e450`
- end: `0x18003e5f3`
- name: `?RemoveProfileElement@CProfile@WindowsPerformanceRecorder@@UEAAJXZ`
- size: `419`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CProfile *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180001124`
- `0x180001214`
- `0x180019298`
- `0x1800192e8`
- `0x18001e6e0`
- `0x18003e450`
- `0x18004958c`
- `0x18004b128`
- `0x18008c010`

## string_xrefs

- `0x18003e4da`: `RemoveProfileElement`
- `0x18003e512`: `RemoveProfileElement`
- `0x18003e51b`: `RemoveProfileElement`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WindowsPerformanceRecorder::CProfile::RemoveProfileElement(
        WindowsPerformanceRecorder::CProfile *this)
{
  int v2; // edi
  struct WindowsPerformanceRecorder::CBaseProfileElement **v3; // rbx
  __int64 v4; // rcx
  const char *v5; // rax
  __int64 InstanceNameScopedData; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  const char *v11; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v12[2]; // [rsp+48h] [rbp-30h] BYREF
  ATL::CAtlException *v13; // [rsp+58h] [rbp-20h] BYREF
  int v14; // [rsp+88h] [rbp+10h] BYREF
  struct _RTL_CRITICAL_SECTION *v15; // [rsp+90h] [rbp+18h] BYREF
  WCHAR *v16; // [rsp+98h] [rbp+20h] BYREF

  v12[1] = -2;
  v15 = 0;
  v2 = WindowsPerformanceRecorder::CAPIAutoLock::Acquire<WindowsPerformanceRecorder::CTraceMergeProperties>(
         &v15,
         (__int64)this);
  if ( v2 >= 0 )
  {
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 64LL))((char *)this + 16);
    v2 = 1;
    try
    {
      v3 = (struct WindowsPerformanceRecorder::CBaseProfileElement **)((char *)this + 216);
      v16 = (WCHAR *)((char *)this + 216);
      v4 = *((_QWORD *)this + 27);
      if ( v4 )
      {
        v5 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)1,
          "RemoveProfileElement",
          (const char *)0x2F6,
          1u,
          "Removing %ws",
          v5);
        InstanceNameScopedData = WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::GetInstanceNameScopedData((char *)this + 128);
        v2 = WindowsPerformanceRecorder::CProfilesCache::RemoveProfileElementsCollectionFromCacheByString(
               (WindowsPerformanceRecorder::CProfilesCache *)(InstanceNameScopedData + 40),
               *v3);
        if ( !v2 )
          *v3 = 0;
      }
    }
    catch ( ATL::CAtlException *v13 )
    {
      v14 = *(_DWORD *)v13;
      v2 = v14;
      v3 = (struct WindowsPerformanceRecorder::CBaseProfileElement **)v16;
    }
    if ( v2
      && *v3
      && (unsigned int)dword_1800BDC60 > 1
      && (unsigned __int8)tlgKeywordOn(&dword_1800BDC60, 0x200000001000LL) )
    {
      v16 = (WCHAR *)(*(__int64 (__fastcall **)(struct WindowsPerformanceRecorder::CBaseProfileElement *))(*(_QWORD *)*v3 + 16LL))(*v3);
      v14 = v2;
      v11 = "RemoveProfileElement";
      v12[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v7,
        (__int64)byte_1800A52F1,
        v8,
        v9,
        (__int64)v12,
        &v11,
        (__int64)&v14,
        (const WCHAR **)&v16);
    }
  }
  WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v15);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003e450  mov     rax, rsp
0x18003e453  push    rsi
0x18003e454  push    rdi
0x18003e455  push    r14
0x18003e457  sub     rsp, 60h
0x18003e45b  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18003e463  mov     [rax+8], rbx
0x18003e467  mov     rsi, rcx
0x18003e46a  mov     qword ptr [rax+18h], 0
0x18003e472  mov     rdx, rcx
0x18003e475  lea     rcx, [rax+18h]
0x18003e479  call    ??$Acquire@VCTraceMergeProperties@WindowsPerformanceRecorder@@@CAPIAutoLock@WindowsPerformanceRecorder@@QEAAJPEAVCTraceMergeProperties@1@@Z; WindowsPerformanceRecorder::CAPIAutoLock::Acquire<WindowsPerformanceRecorder::CTraceMergeProperties>(WindowsPerformanceRecorder::CTraceMergeProperties *)
0x18003e47e  mov     edi, eax
0x18003e480  test    eax, eax
0x18003e482  js      loc_18003E5D3
0x18003e488  lea     rcx, [rsi+10h]
0x18003e48c  mov     rax, [rcx]
0x18003e48f  mov     rax, [rax+40h]
0x18003e493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e498  mov     edi, 1
0x18003e49d  lea     rbx, [rsi+0D8h]
0x18003e4a4  mov     [rsp+78h+arg_18], rbx
0x18003e4ac  mov     rcx, [rbx]
0x18003e4af  test    rcx, rcx
0x18003e4b2  jz      short loc_18003E512
0x18003e4b4  mov     rax, [rcx]
0x18003e4b7  mov     rax, [rax+10h]
0x18003e4bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e4c0  mov     [rsp+78h+var_50], rax; char *
0x18003e4c5  lea     rax, aRemovingWs; "Removing %ws"
0x18003e4cc  mov     [rsp+78h+Format], rax; Format
0x18003e4d1  mov     r9d, edi; unsigned int
0x18003e4d4  mov     r8d, 2F6h; char *
0x18003e4da  lea     r14, aRemoveprofilee; "RemoveProfileElement"
0x18003e4e1  mov     rdx, r14; unsigned __int8
0x18003e4e4  mov     ecx, edi; this
0x18003e4e6  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18003e4eb  lea     rcx, [rsi+80h]
0x18003e4f2  call    ?GetInstanceNameScopedData@?$CInstanceNameScopedObjectImpl@VCProfile@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAPEAUCInstanceNameScopedData@2@XZ; WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::GetInstanceNameScopedData(void)
0x18003e4f7  lea     rcx, [rax+28h]; this
0x18003e4fb  mov     rdx, [rbx]; struct WindowsPerformanceRecorder::CBaseProfileElement *
0x18003e4fe  call    ?RemoveProfileElementsCollectionFromCacheByString@CProfilesCache@WindowsPerformanceRecorder@@QEAAJPEAVCBaseProfileElement@2@@Z; WindowsPerformanceRecorder::CProfilesCache::RemoveProfileElementsCollectionFromCacheByString(WindowsPerformanceRecorder::CBaseProfileElement *)
0x18003e503  mov     edi, eax
0x18003e505  test    eax, eax
0x18003e507  jnz     short loc_18003E519
0x18003e509  mov     qword ptr [rbx], 0
0x18003e510  jmp     short loc_18003E519
0x18003e512  lea     r14, aRemoveprofilee; "RemoveProfileElement"
0x18003e519  jmp     short loc_18003E531
0x18003e51b  lea     r14, aRemoveprofilee; "RemoveProfileElement"
0x18003e522  mov     edi, [rsp+78h+arg_8]
0x18003e529  mov     rbx, [rsp+78h+arg_18]
0x18003e531  test    edi, edi
0x18003e533  jz      loc_18003E5D3
0x18003e539  cmp     qword ptr [rbx], 0
0x18003e53d  jz      loc_18003E5D3
0x18003e543  mov     eax, cs:dword_1800BDC60
0x18003e549  cmp     eax, 1
0x18003e54c  jbe     loc_18003E5D3
0x18003e552  mov     rdx, 200000001000h
0x18003e55c  lea     rcx, dword_1800BDC60
0x18003e563  call    _tlgKeywordOn
0x18003e568  test    al, al
0x18003e56a  jz      short loc_18003E5D3
0x18003e56c  mov     rcx, [rbx]
0x18003e56f  mov     rax, [rcx]
0x18003e572  mov     rax, [rax+10h]
0x18003e576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e57b  mov     [rsp+78h+arg_18], rax
0x18003e583  mov     [rsp+78h+arg_8], edi
0x18003e58a  mov     [rsp+78h+var_38], r14
0x18003e58f  mov     [rsp+78h+var_30], 1000000h
0x18003e598  lea     rax, [rsp+78h+arg_18]
0x18003e5a0  mov     [rsp+78h+var_40], rax
0x18003e5a5  lea     rax, [rsp+78h+arg_8]
0x18003e5ad  mov     [rsp+78h+var_48], rax
0x18003e5b2  lea     rax, [rsp+78h+var_38]
0x18003e5b7  mov     [rsp+78h+var_50], rax
0x18003e5bc  lea     rax, [rsp+78h+var_30]
0x18003e5c1  mov     [rsp+78h+Format], rax
0x18003e5c6  lea     rdx, byte_1800A52F1
0x18003e5cd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18003e5d2  nop
0x18003e5d3  lea     rcx, [rsp+78h+arg_10]; this
0x18003e5db  call    ??1CAPIAutoLock@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock(void)
0x18003e5e0  mov     eax, edi
0x18003e5e2  mov     rbx, [rsp+78h+arg_0]
0x18003e5ea  add     rsp, 60h
0x18003e5ee  pop     r14
0x18003e5f0  pop     rdi
0x18003e5f1  pop     rsi
0x18003e5f2  retn
```
