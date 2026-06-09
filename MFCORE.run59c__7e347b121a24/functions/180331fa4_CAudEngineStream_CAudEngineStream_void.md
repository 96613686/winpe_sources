# CAudEngineStream::~CAudEngineStream(void)

- ea: `0x180331fa4`
- end: `0x180332124`
- name: `??1CAudEngineStream@@UEAA@XZ`
- size: `384`
- prototype: `void __fastcall(CAudEngineStream *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180318c40`

## callees

- `0x18000f278`
- `0x18002fee0`
- `0x18003ecb0`
- `0x180063f00`
- `0x180331fa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180332031`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180332044`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18033206f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180332082`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180332095`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1803320f3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180332031`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180332044`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18033206f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180332082`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180332095`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1803320f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180332014`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180332014`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803320b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803320b4`

## pseudocode

```c
void __fastcall CAudEngineStream::~CAudEngineStream(CAudEngineStream *this)
{
  char *v2; // rcx
  char v3; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &CAudEngineStream::`vftable'{for `CBaseUnknown'};
  *((_QWORD *)this + 2) = &CAudEngineStream::`vftable'{for `CMfAudioStreamIF'};
  *((_QWORD *)this + 3) = &CAudEngineStream::`vftable'{for `IMFAudioPolicy'};
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v3, "CAudEngineStream::~CAudEngineStream", 317);
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0p_EventWriteTransfer(
      &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
      &AudEngineStream_DelAudEngineStream,
      this);
  v2 = (char *)*((_QWORD *)this + 49);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 456));
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 384);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 376);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 328));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 6);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 136);
  CoTaskMemFree(*((LPVOID *)this + 16));
  *((_QWORD *)this + 16) = 0;
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 120);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 112);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 104);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 96);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 32);
  *((_QWORD *)this + 2) = &CMfAudioStreamIF::`vftable';
  *(_QWORD *)this = &CBaseUnknown::`vftable';
}

```

## disassembly

```asm
0x180331fa4  push    rbx
0x180331fa6  sub     rsp, 20h
0x180331faa  lea     rax, ??_7CAudEngineStream@@6BCBaseUnknown@@@; const CAudEngineStream::`vftable'{for `CBaseUnknown'}
0x180331fb1  mov     rbx, rcx
0x180331fb4  mov     [rcx], rax
0x180331fb7  lea     rdx, aCaudenginestre_12; "CAudEngineStream::~CAudEngineStream"
0x180331fbe  lea     rax, ??_7CAudEngineStream@@6BCMfAudioStreamIF@@@; const CAudEngineStream::`vftable'{for `CMfAudioStreamIF'}
0x180331fc5  mov     r8d, 13Dh; int
0x180331fcb  mov     [rcx+10h], rax
0x180331fcf  lea     rax, ??_7CAudEngineStream@@6BIMFAudioPolicy@@@; const CAudEngineStream::`vftable'{for `IMFAudioPolicy'}
0x180331fd6  mov     [rcx+18h], rax
0x180331fda  lea     rcx, [rsp+28h+arg_0]; this
0x180331fdf  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180331fe4  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, 1
0x180331feb  jz      short loc_180332003
0x180331fed  mov     r8, rbx
0x180331ff0  lea     rdx, AudEngineStream_DelAudEngineStream
0x180331ff7  lea     rcx, Microsoft_Windows_MediaFoundation_Performance_Core_Context
0x180331ffe  call    McTemplateU0p_EventWriteTransfer
0x180332003  mov     rcx, [rbx+188h]; hObject
0x18033200a  lea     rax, [rcx-1]
0x18033200e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180332012  ja      short loc_180332020
0x180332014  call    cs:__imp_CloseHandle
0x18033201b  nop     dword ptr [rax+rax+00h]
0x180332020  lea     rcx, [rsp+28h+arg_0]; this
0x180332025  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18033202a  lea     rcx, [rbx+238h]; lpCriticalSection
0x180332031  call    cs:__imp_DeleteCriticalSection
0x180332038  nop     dword ptr [rax+rax+00h]
0x18033203d  lea     rcx, [rbx+1C8h]; lpCriticalSection
0x180332044  call    cs:__imp_DeleteCriticalSection
0x18033204b  nop     dword ptr [rax+rax+00h]
0x180332050  lea     rcx, [rbx+180h]
0x180332057  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18033205c  lea     rcx, [rbx+178h]
0x180332063  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180332068  lea     rcx, [rbx+148h]; lpCriticalSection
0x18033206f  call    cs:__imp_DeleteCriticalSection
0x180332076  nop     dword ptr [rax+rax+00h]
0x18033207b  lea     rcx, [rbx+120h]; lpCriticalSection
0x180332082  call    cs:__imp_DeleteCriticalSection
0x180332089  nop     dword ptr [rax+rax+00h]
0x18033208e  lea     rcx, [rbx+0F0h]; lpCriticalSection
0x180332095  call    cs:__imp_DeleteCriticalSection
0x18033209c  nop     dword ptr [rax+rax+00h]
0x1803320a1  lea     rcx, [rbx+88h]
0x1803320a8  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1803320ad  mov     rcx, [rbx+80h]; pv
0x1803320b4  call    cs:__imp_CoTaskMemFree
0x1803320bb  nop     dword ptr [rax+rax+00h]
0x1803320c0  lea     rcx, [rbx+78h]
0x1803320c4  mov     qword ptr [rbx+80h], 0
0x1803320cf  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1803320d4  lea     rcx, [rbx+70h]
0x1803320d8  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1803320dd  lea     rcx, [rbx+68h]
0x1803320e1  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1803320e6  lea     rcx, [rbx+60h]
0x1803320ea  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1803320ef  lea     rcx, [rbx+30h]; lpCriticalSection
0x1803320f3  call    cs:__imp_DeleteCriticalSection
0x1803320fa  nop     dword ptr [rax+rax+00h]
0x1803320ff  lea     rcx, [rbx+20h]
0x180332103  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180332108  lea     rax, ??_7CMfAudioStreamIF@@6B@; const CMfAudioStreamIF::`vftable'
0x18033210f  mov     [rbx+10h], rax
0x180332113  lea     rax, ??_7CBaseUnknown@@6B@; const CBaseUnknown::`vftable'
0x18033211a  mov     [rbx], rax
0x18033211d  add     rsp, 20h
0x180332121  pop     rbx
0x180332122  retn
```
