# WorkerGarbageCollector::Add(PhotoDocumentLoadWorker *)

- ea: `0x18002bca4`
- end: `0x18002bdbc`
- name: `?Add@WorkerGarbageCollector@@QEAAXPEAVPhotoDocumentLoadWorker@@@Z`
- size: `280`
- prototype: `void __fastcall(WorkerGarbageCollector *__hidden this, struct PhotoDocumentLoadWorker *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180062010`

## callees

- `0x180021a90`
- `0x18002bca4`
- `0x18002c4ec`
- `0x18002c6c0`
- `0x1800320a8`
- `0x180048060`
- `0x18006063c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002bcce`
- `KERNEL32!GetCurrentThreadId` at `0x18002bcce`
- `USER32!SetTimer` at `0x18002bd8b`
- `USER32!SetTimer` at `0x18002bd8b`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002bd27`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002bd27`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WorkerGarbageCollector::Add(WorkerGarbageCollector *this, struct PhotoDocumentLoadWorker *a2, bool a3)
{
  bool v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned __int16 v8; // ax
  __int64 v9; // rdx
  Base *v10; // rcx
  __int64 v11; // rax
  __int64 *v12; // rcx
  _BYTE v13[16]; // [rsp+50h] [rbp-48h] BYREF
  _BYTE v14[56]; // [rsp+60h] [rbp-38h] BYREF

  ATL::CCritSecLock::CCritSecLock((ATL::CCritSecLock *)v14, (struct _RTL_CRITICAL_SECTION *)((char *)this + 176), a3);
  if ( !*((_DWORD *)this + 55) )
  {
    *((_DWORD *)this + 54) = GetCurrentThreadId();
    if ( !qword_1800A2950 )
      qword_1800A2950 = 0;
    v8 = ATL::AtlModuleRegisterWndClassInfoT<ATL::AtlModuleRegisterWndClassInfoParamW>(
           v7,
           v6,
           &`ATL::CWindowImpl<WorkerGarbageCollector,ATL::CWindow,ATL::CWinTraits<1442840576,0>>::GetWndClassInfo'::`2'::wc,
           (char *)this + 64);
    if ( !ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(
            (HMENU)this,
            v9,
            0,
            0,
            0x56000000u,
            0,
            0,
            v8) )
    {
      Base::ThrowLastError(v10);
      __debugbreak();
    }
    *((_DWORD *)this + 55) = 1;
  }
  ATL::CCritSecLock::CCritSecLock((ATL::CCritSecLock *)v13, (struct _RTL_CRITICAL_SECTION *)((char *)this + 88), v5);
  v11 = ATL::CAtlList<ATL::CComQIPtr<IListIteratorEventSink,&__s_GUID const _GUID_bd462ee3_4fdc_4c82_8f68_10af70d8f6ba>,ATL::CComQIPtrElementTraits<IListIteratorEventSink,&__s_GUID const _GUID_bd462ee3_4fdc_4c82_8f68_10af70d8f6ba>>::NewNode(
          (char *)this + 128,
          a2,
          *((_QWORD *)this + 17));
  v12 = (__int64 *)*((_QWORD *)this + 17);
  if ( v12 )
    *v12 = v11;
  else
    *((_QWORD *)this + 16) = v11;
  *((_QWORD *)this + 17) = v11;
  if ( *((_DWORD *)this + 55) == 1 )
    SetTimer(*((HWND *)this + 1), 0x91Du, 0x64u, 0);
  else
    WorkerGarbageCollector::Dispose(this, 1);
  ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v13);
  ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v14);
}

```

## disassembly

```asm
0x18002bca4  push    rbx
0x18002bca6  push    rbp
0x18002bca7  push    rsi
0x18002bca8  push    rdi
0x18002bca9  sub     rsp, 78h
0x18002bcad  mov     rbp, rdx
0x18002bcb0  mov     rsi, rcx
0x18002bcb3  lea     rdx, [rcx+0B0h]; struct _RTL_CRITICAL_SECTION *
0x18002bcba  lea     rcx, [rsp+98h+var_38]; this
0x18002bcbf  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x18002bcc4  nop
0x18002bcc5  cmp     dword ptr [rsi+0DCh], 0
0x18002bccc  jnz     short loc_18002BD38
0x18002bcce  call    cs:__imp_GetCurrentThreadId
0x18002bcd4  mov     [rsi+0D8h], eax
0x18002bcda  xor     ebx, ebx
0x18002bcdc  xor     edi, edi
0x18002bcde  cmp     cs:qword_1800A2950, rbx
0x18002bce5  jnz     short loc_18002BCEE
0x18002bce7  mov     cs:qword_1800A2950, rbx
0x18002bcee  lea     r9, [rsi+40h]
0x18002bcf2  lea     r8, ?wc@?1??GetWndClassInfo@?$CWindowImpl@VWorkerGarbageCollector@@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@3@@ATL@@SAAEAU_ATL_WNDCLASSINFOW@3@XZ@4U43@A; ATL::_ATL_WNDCLASSINFOW `ATL::CWindowImpl<WorkerGarbageCollector,ATL::CWindow,ATL::CWinTraits<1442840576,0>>::GetWndClassInfo(void)'::`2'::wc
0x18002bcf9  call    ??$AtlModuleRegisterWndClassInfoT@VAtlModuleRegisterWndClassInfoParamW@ATL@@@ATL@@YAGPEAU_ATL_BASE_MODULE70@0@PEAU_ATL_WIN_MODULE70@0@PEAU_ATL_WNDCLASSINFOW@0@PEAP6A_JPEAUHWND__@@I_K_J@ZVAtlModuleRegisterWndClassInfoParamW@0@@Z; ATL::AtlModuleRegisterWndClassInfoT<ATL::AtlModuleRegisterWndClassInfoParamW>(ATL::_ATL_BASE_MODULE70 *,ATL::_ATL_WIN_MODULE70 *,ATL::_ATL_WNDCLASSINFOW *,__int64 (**)(HWND__ *,uint,unsigned __int64,__int64),ATL::AtlModuleRegisterWndClassInfoParamW)
0x18002bcfe  mov     [rsp+98h+var_60], ax
0x18002bd03  mov     [rsp+98h+var_68], rbx
0x18002bd08  mov     [rsp+98h+var_70], ebx
0x18002bd0c  mov     [rsp+98h+var_78], 56000000h
0x18002bd14  xor     r9d, r9d
0x18002bd17  mov     r8, rdi
0x18002bd1a  mov     rcx, rsi
0x18002bd1d  call    ?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@GPEAX@Z; ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,ushort,void *)
0x18002bd22  test    rax, rax
0x18002bd25  jnz     short loc_18002BD2E
0x18002bd27  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x18002bd2d  int     3; Trap to Debugger
0x18002bd2e  mov     dword ptr [rsi+0DCh], 1
0x18002bd38  lea     rdx, [rsi+58h]; struct _RTL_CRITICAL_SECTION *
0x18002bd3c  lea     rcx, [rsp+98h+var_48]; this
0x18002bd41  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x18002bd46  nop
0x18002bd47  lea     rbx, [rsi+80h]
0x18002bd4e  mov     r8, [rbx+8]
0x18002bd52  mov     rdx, rbp
0x18002bd55  mov     rcx, rbx
0x18002bd58  call    ?NewNode@?$CAtlList@V?$CComQIPtr@VIListIteratorEventSink@@$1?_GUID_bd462ee3_4fdc_4c82_8f68_10af70d8f6ba@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@VIListIteratorEventSink@@$1?_GUID_bd462ee3_4fdc_4c82_8f68_10af70d8f6ba@@3U__s_GUID@@B@2@@ATL@@AEAAPEAVCNode@12@PEAVIListIteratorEventSink@@PEAV312@1@Z; ATL::CAtlList<ATL::CComQIPtr<IListIteratorEventSink,&__s_GUID const _GUID_bd462ee3_4fdc_4c82_8f68_10af70d8f6ba>,ATL::CComQIPtrElementTraits<IListIteratorEventSink,&__s_GUID const _GUID_bd462ee3_4fdc_4c82_8f68_10af70d8f6ba>>::NewNode(IListIteratorEventSink *,ATL::CAtlList<ATL::CComQIPtr<IListIteratorEventSink,&__s_GUID const _GUID_bd462ee3_4fdc_4c82_8f68_10af70d8f6ba>,ATL::CComQIPtrElementTraits<IListIteratorEventSink,&__s_GUID const _GUID_bd462ee3_4fdc_4c82_8f68_10af70d8f6ba>>::CNode *,ATL::CAtlList<ATL::CComQIPtr<IListIteratorEventSink,&__s_GUID const _GUID_bd462ee3_4fdc_4c82_8f68_10af70d8f6ba>,ATL::CComQIPtrElementTraits<IListIteratorEventSink,&__s_GUID const _GUID_bd462ee3_4fdc_4c82_8f68_10af70d8f6ba>>::CNode *)
0x18002bd5d  mov     rcx, [rbx+8]
0x18002bd61  test    rcx, rcx
0x18002bd64  jz      short loc_18002BD6B
0x18002bd66  mov     [rcx], rax
0x18002bd69  jmp     short loc_18002BD6E
0x18002bd6b  mov     [rbx], rax
0x18002bd6e  mov     [rbx+8], rax
0x18002bd72  cmp     dword ptr [rsi+0DCh], 1
0x18002bd79  jnz     short loc_18002BD93
0x18002bd7b  xor     r9d, r9d; lpTimerFunc
0x18002bd7e  mov     edx, 91Dh; nIDEvent
0x18002bd83  lea     r8d, [r9+64h]; uElapse
0x18002bd87  mov     rcx, [rsi+8]; hWnd
0x18002bd8b  call    cs:__imp_SetTimer
0x18002bd91  jmp     short loc_18002BD9E
0x18002bd93  mov     dl, 1; bool
0x18002bd95  mov     rcx, rsi; this
0x18002bd98  call    ?Dispose@WorkerGarbageCollector@@AEAAX_N@Z; WorkerGarbageCollector::Dispose(bool)
0x18002bd9d  nop
0x18002bd9e  lea     rcx, [rsp+98h+var_48]; this
0x18002bda3  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x18002bda8  nop
0x18002bda9  lea     rcx, [rsp+98h+var_38]; this
0x18002bdae  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x18002bdb3  add     rsp, 78h
0x18002bdb7  pop     rdi
0x18002bdb8  pop     rsi
0x18002bdb9  pop     rbp
0x18002bdba  pop     rbx
0x18002bdbb  retn
```
