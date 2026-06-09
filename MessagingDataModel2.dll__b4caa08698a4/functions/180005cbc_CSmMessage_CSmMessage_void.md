# CSmMessage::~CSmMessage(void)

- ea: `0x180005cbc`
- end: `0x180005dbc`
- name: `??1CSmMessage@@UEAA@XZ`
- size: `256`
- prototype: `void __fastcall(CSmMessage *__hidden this)`
- caller_count: `6`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000594c`
- `0x180005ae8`
- `0x1800060e0`
- `0x180018bdc`
- `0x180018dd4`
- `0x180018e0c`

## callees

- `0x1800057ac`
- `0x180005c50`
- `0x180005c74`
- `0x180005cbc`
- `0x180008870`
- `0x180017854`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005d7c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005d7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180005ccc`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d29`
- `OLEAUT32!__imp_SysFreeString` at `0x180005ccc`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005cd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005cfb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005cd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005cfb`
- `CEMAPI!MAPIFreeBuffer` at `0x180005d4e`
- `CEMAPI!MAPIFreeBuffer` at `0x180005d4e`

## pseudocode

```c
void __fastcall CSmMessage::~CSmMessage(CSmMessage *this)
{
  MessageDelayLoadedInfo *v2; // rcx

  SysFreeString(*((BSTR *)this + 55));
  LocalFree(*((HLOCAL *)this + 54));
  *((_QWORD *)this + 54) = 0;
  *((_DWORD *)this + 106) = 0;
  LocalFree(*((HLOCAL *)this + 51));
  *((_QWORD *)this + 51) = 0;
  *((_DWORD *)this + 100) = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((char *)this + 360);
  SysFreeString(*((BSTR *)this + 43));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 312);
  CSmStoreTransaction::~CSmStoreTransaction((CSmMessage *)((char *)this + 280));
  MAPIFreeBuffer(*((LPVOID *)this + 32));
  *((_QWORD *)this + 32) = 0;
  *((_DWORD *)this + 62) = 0;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 232);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  v2 = (MessageDelayLoadedInfo *)*((_QWORD *)this + 20);
  if ( v2 )
    tlx::_delete<MessageDelayLoadedInfo>(v2);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 104);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 72);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 64);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CSmMessage *)((char *)this + 16));
}

```

## disassembly

```asm
0x180005cbc  push    rbx
0x180005cbe  sub     rsp, 20h
0x180005cc2  mov     rbx, rcx
0x180005cc5  mov     rcx, [rcx+1B8h]; bstrString
0x180005ccc  call    cs:__imp_SysFreeString
0x180005cd2  mov     rcx, [rbx+1B0h]; hMem
0x180005cd9  call    cs:__imp_LocalFree
0x180005cdf  mov     qword ptr [rbx+1B0h], 0
0x180005cea  mov     dword ptr [rbx+1A8h], 0
0x180005cf4  mov     rcx, [rbx+198h]; hMem
0x180005cfb  call    cs:__imp_LocalFree
0x180005d01  lea     rcx, [rbx+168h]
0x180005d08  mov     qword ptr [rbx+198h], 0
0x180005d13  mov     dword ptr [rbx+190h], 0
0x180005d1d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180005d22  mov     rcx, [rbx+158h]; bstrString
0x180005d29  call    cs:__imp_SysFreeString
0x180005d2f  lea     rcx, [rbx+138h]
0x180005d36  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005d3b  lea     rcx, [rbx+118h]; this
0x180005d42  call    ??1CSmStoreTransaction@@UEAA@XZ; CSmStoreTransaction::~CSmStoreTransaction(void)
0x180005d47  mov     rcx, [rbx+100h]; pv
0x180005d4e  call    cs:__imp_MAPIFreeBuffer
0x180005d54  lea     rcx, [rbx+0E8h]
0x180005d5b  mov     qword ptr [rbx+100h], 0
0x180005d66  mov     dword ptr [rbx+0F8h], 0
0x180005d70  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005d75  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180005d7c  call    cs:__imp_DeleteCriticalSection
0x180005d82  mov     rcx, [rbx+0A0h]
0x180005d89  test    rcx, rcx
0x180005d8c  jz      short loc_180005D93
0x180005d8e  call    ??$_delete@UMessageDelayLoadedInfo@@@tlx@@YAXPEAUMessageDelayLoadedInfo@@@Z; tlx::_delete<MessageDelayLoadedInfo>(MessageDelayLoadedInfo *)
0x180005d93  lea     rcx, [rbx+68h]
0x180005d97  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005d9c  lea     rcx, [rbx+48h]
0x180005da0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005da5  lea     rcx, [rbx+40h]
0x180005da9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005dae  lea     rcx, [rbx+10h]; this
0x180005db2  add     rsp, 20h
0x180005db6  pop     rbx
0x180005db7  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
