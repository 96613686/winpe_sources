# CMapi2RowFilter::OpenMessage(CMapi2Accessor *,int,IMessage * *)

- ea: `0x180020e44`
- end: `0x180021022`
- name: `?OpenMessage@CMapi2RowFilter@@AEAAJPEAVCMapi2Accessor@@HPEAPEAUIMessage@@@Z`
- size: `478`
- prototype: `int(CMapi2RowFilter *__hidden this, struct CMapi2Accessor *, int, struct IMessage **)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001cd24`
- `0x18001f990`

## callees

- `0x180002300`
- `0x18000ad14`
- `0x18000e658`
- `0x18000e8ac`
- `0x18000ebac`
- `0x180011884`
- `0x18001241c`
- `0x180015970`
- `0x180017894`
- `0x180020e44`
- `0x180030754`
- `0x180034910`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180020f79`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180020f93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180020f79`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180020f93`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180020f8d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180020f8d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMapi2RowFilter::OpenMessage(
        const wchar_t **this,
        struct CMapi2Accessor *a2,
        __int64 a3,
        struct IMessage **a4)
{
  int v5; // r14d
  _QWORD *v8; // rax
  int MsgStore; // edi
  __int64 v10; // r8
  CMapiStore *Ptr; // rbx
  int v12; // r9d
  BOOL v13; // eax
  int v14; // ecx
  int v15; // edi
  DWORD v16; // eax
  DWORD v17; // ecx
  _QWORD v19[2]; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v20[96]; // [rsp+40h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+A0h] [rbp+7h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+B0h] [rbp+17h] BYREF

  v5 = a3;
  if ( (Microsoft_Windows_Search_ProtocolHandlersEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)Microsoft_Windows_Search_ProtocolHandlers_Context,
      (const EVENT_DESCRIPTOR *)MSSearchTraceId_OpenMessage_Start,
      a3,
      1u,
      &v22);
  CMapiUrl::CMapiUrl((CMapiUrl *)v20, this[2647]);
  CMapiUrl::Store((__int64)v20, (__int64)v19);
  v22.Ptr = 0;
  v8 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
         &v21,
         v19);
  MsgStore = CMapi2Accessor::GetMsgStore((__int64)a2, v8, &v22);
  if ( !MsgStore )
  {
    Ptr = (CMapiStore *)v22.Ptr;
    if ( v22.Ptr )
    {
      LODWORD(v21.Ptr) = 0;
      MsgStore = CMapiSupport::CheckPolicyOnStore((struct CMapiStore *)v22.Ptr, (int *)&v21, 0);
      if ( MsgStore >= 0 )
      {
        if ( LODWORD(v21.Ptr) )
        {
          v13 = *((_DWORD *)Ptr + 20) && !*((_DWORD *)Ptr + 24);
          *((_DWORD *)this + 5949) = v13;
          *((_DWORD *)this + 5951) = *((_DWORD *)Ptr + 25);
          v14 = *((_DWORD *)Ptr + 26);
          *((_DWORD *)this + 5952) = v14;
          *((_DWORD *)this + 5950) = *((_DWORD *)Ptr + 22);
          if ( v5 && v14 && *((_DWORD *)Ptr + 33) )
          {
            v15 = *((_DWORD *)Ptr + 34);
            if ( v15 )
            {
              v16 = GetTickCount() - v15;
              v17 = *((_DWORD *)Ptr + 33);
              if ( v16 < v17 )
                Sleep(v17 - v16);
            }
            *((_DWORD *)Ptr + 34) = GetTickCount();
          }
          MsgStore = CMapiStore::OpenEntryAndCheckFolder(Ptr, (struct CMapiUrl *)v20, a4, v12);
        }
        else
        {
          MsgStore = -2147216895;
        }
      }
    }
  }
  if ( (Microsoft_Windows_Search_ProtocolHandlersEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)Microsoft_Windows_Search_ProtocolHandlers_Context,
      (const EVENT_DESCRIPTOR *)MSSearchTraceId_OpenMessage_Stop,
      v10,
      1u,
      &v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
  ATL::CStringData::Release((ATL::CStringData *)(v19[0] - 24LL));
  CMapiUrl::~CMapiUrl((CMapiUrl *)v20);
  return (unsigned int)MsgStore;
}

```

## disassembly

```asm
0x180020e44  mov     [rsp-8+arg_10], rbx
0x180020e49  push    rbp
0x180020e4a  push    rsi
0x180020e4b  push    rdi
0x180020e4c  push    r14
0x180020e4e  push    r15
0x180020e50  lea     rbp, [rsp-37h]
0x180020e55  sub     rsp, 0D0h
0x180020e5c  mov     rax, cs:__security_cookie
0x180020e63  xor     rax, rsp
0x180020e66  mov     [rbp+57h+var_30], rax
0x180020e6a  mov     r15, r9
0x180020e6d  mov     r14d, r8d
0x180020e70  mov     rbx, rdx
0x180020e73  mov     rsi, rcx
0x180020e76  test    cs:Microsoft_Windows_Search_ProtocolHandlersEnableBits, 4
0x180020e7d  jz      short loc_180020EA1
0x180020e7f  lea     rax, [rbp+57h+var_40]
0x180020e83  mov     [rsp+0F0h+var_D0], rax
0x180020e88  mov     r9d, 1
0x180020e8e  lea     rdx, MSSearchTraceId_OpenMessage_Start
0x180020e95  lea     rcx, Microsoft_Windows_Search_ProtocolHandlers_Context
0x180020e9c  call    McGenEventWrite_EventWriteTransfer
0x180020ea1  mov     rdx, [rsi+52B8h]; wchar_t *
0x180020ea8  lea     rcx, [rbp+57h+var_B0]; this
0x180020eac  call    ??0CMapiUrl@@QEAA@PEB_W@Z; CMapiUrl::CMapiUrl(wchar_t const *)
0x180020eb1  nop
0x180020eb2  lea     rdx, [rbp+57h+var_C0]
0x180020eb6  lea     rcx, [rbp+57h+var_B0]
0x180020eba  call    ?Store@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::Store(void)
0x180020ebf  nop
0x180020ec0  mov     qword ptr [rbp+57h+var_40], 0
0x180020ec8  lea     rdx, [rbp+57h+var_C0]
0x180020ecc  lea     rcx, [rbp+57h+var_50]
0x180020ed0  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180020ed5  lea     r8, [rbp+57h+var_40]
0x180020ed9  mov     rdx, rax
0x180020edc  mov     rcx, rbx
0x180020edf  call    ?GetMsgStore@CMapi2Accessor@@QEAAJV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAPEAVCMapiStore@@@Z; CMapi2Accessor::GetMsgStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiStore * *)
0x180020ee4  mov     edi, eax
0x180020ee6  test    eax, eax
0x180020ee8  jnz     loc_180020FB0
0x180020eee  mov     rbx, qword ptr [rbp+57h+var_40]
0x180020ef2  test    rbx, rbx
0x180020ef5  jz      loc_180020FB0
0x180020efb  mov     dword ptr [rbp+57h+var_50], eax
0x180020efe  xor     r8d, r8d; enum POLICY_RESULT_ID *
0x180020f01  lea     rdx, [rbp+57h+var_50]; int *
0x180020f05  mov     rcx, rbx; struct CMapiStore *
0x180020f08  call    ?CheckPolicyOnStore@CMapiSupport@@SAJPEAVCMapiStore@@PEAHPEAW4POLICY_RESULT_ID@@@Z; CMapiSupport::CheckPolicyOnStore(CMapiStore *,int *,POLICY_RESULT_ID *)
0x180020f0d  mov     edi, eax
0x180020f0f  test    eax, eax
0x180020f11  js      loc_180020FB0
0x180020f17  cmp     dword ptr [rbp+57h+var_50], 0
0x180020f1b  jnz     short loc_180020F27
0x180020f1d  mov     edi, 80041201h
0x180020f22  jmp     loc_180020FB0
0x180020f27  cmp     dword ptr [rbx+50h], 0
0x180020f2b  jz      short loc_180020F3A
0x180020f2d  cmp     dword ptr [rbx+60h], 0
0x180020f31  jnz     short loc_180020F3A
0x180020f33  mov     eax, 1
0x180020f38  jmp     short loc_180020F3C
0x180020f3a  xor     eax, eax
0x180020f3c  mov     [rsi+5CF4h], eax
0x180020f42  mov     eax, [rbx+64h]
0x180020f45  mov     [rsi+5CFCh], eax
0x180020f4b  mov     ecx, [rbx+68h]
0x180020f4e  mov     [rsi+5D00h], ecx
0x180020f54  mov     eax, [rbx+58h]
0x180020f57  mov     [rsi+5CF8h], eax
0x180020f5d  test    r14d, r14d
0x180020f60  jz      short loc_180020F9F
0x180020f62  test    ecx, ecx
0x180020f64  jz      short loc_180020F9F
0x180020f66  cmp     dword ptr [rbx+84h], 0
0x180020f6d  jz      short loc_180020F9F
0x180020f6f  mov     edi, [rbx+88h]
0x180020f75  test    edi, edi
0x180020f77  jz      short loc_180020F93
0x180020f79  call    cs:__imp_GetTickCount
0x180020f7f  sub     eax, edi
0x180020f81  mov     ecx, [rbx+84h]
0x180020f87  cmp     eax, ecx
0x180020f89  jnb     short loc_180020F93
0x180020f8b  sub     ecx, eax; dwMilliseconds
0x180020f8d  call    cs:__imp_Sleep
0x180020f93  call    cs:__imp_GetTickCount
0x180020f99  mov     [rbx+88h], eax
0x180020f9f  mov     r8, r15; struct IMessage **
0x180020fa2  lea     rdx, [rbp+57h+var_B0]; struct CMapiUrl *
0x180020fa6  mov     rcx, rbx; this
0x180020fa9  call    ?OpenEntryAndCheckFolder@CMapiStore@@QEAAJAEAVCMapiUrl@@PEAPEAUIMessage@@H@Z; CMapiStore::OpenEntryAndCheckFolder(CMapiUrl &,IMessage * *,int)
0x180020fae  mov     edi, eax
0x180020fb0  test    cs:Microsoft_Windows_Search_ProtocolHandlersEnableBits, 4
0x180020fb7  jz      short loc_180020FDC
0x180020fb9  lea     rax, [rbp+57h+var_50]
0x180020fbd  mov     [rsp+0F0h+var_D0], rax
0x180020fc2  mov     r9d, 1
0x180020fc8  lea     rdx, MSSearchTraceId_OpenMessage_Stop
0x180020fcf  lea     rcx, Microsoft_Windows_Search_ProtocolHandlers_Context
0x180020fd6  call    McGenEventWrite_EventWriteTransfer
0x180020fdb  nop
0x180020fdc  lea     rcx, [rbp+57h+var_40]
0x180020fe0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020fe5  nop
0x180020fe6  mov     rcx, [rbp+57h+var_C0]
0x180020fea  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180020fee  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180020ff3  nop
0x180020ff4  lea     rcx, [rbp+57h+var_B0]; this
0x180020ff8  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x180020ffd  mov     eax, edi
0x180020fff  mov     rcx, [rbp+57h+var_30]
0x180021003  xor     rcx, rsp; StackCookie
0x180021006  call    __security_check_cookie
0x18002100b  mov     rbx, [rsp+0F0h+arg_10]
0x180021013  add     rsp, 0D0h
0x18002101a  pop     r15
0x18002101c  pop     r14
0x18002101e  pop     rdi
0x18002101f  pop     rsi
0x180021020  pop     rbp
0x180021021  retn
```
