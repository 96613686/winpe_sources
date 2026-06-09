# CRTThreadManager::~CRTThreadManager(void)

- ea: `0x14007ce78`
- end: `0x14007cf57`
- name: `??1CRTThreadManager@@UEAA@XZ`
- size: `223`
- prototype: `void(CRTThreadManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14007cfb0`

## callees

- `0x140008124`
- `0x14000f3f8`
- `0x140046dc0`
- `0x14007ce78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14007cf31`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14007cf31`
- `RTWorkQ!RtwqShutdown` at `0x14007cec4`
- `RTWorkQ!RtwqShutdown` at `0x14007cec4`
- `RTWorkQ!RtwqUnlockWorkQueue` at `0x14007ce9b`
- `RTWorkQ!RtwqUnlockWorkQueue` at `0x14007ce9b`

## string_xrefs

- `0x14007ceaa`: `avcore\audiocore\server\audiodg\exe\rtthreadmanager.cpp`
- `0x14007ced3`: `avcore\audiocore\server\audiodg\exe\rtthreadmanager.cpp`

## pseudocode

```c
void __fastcall CRTThreadManager::~CRTThreadManager(CRTThreadManager *this)
{
  DWORD v2; // ecx
  HRESULT v3; // eax
  HRESULT v4; // eax
  _QWORD **v5; // rcx
  _QWORD *v6; // rsi
  _QWORD *v7; // rbx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &CRTThreadManager::`vftable';
  v2 = *((_DWORD *)this + 6);
  if ( v2 )
  {
    v3 = RtwqUnlockWorkQueue(v2);
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\rtthreadmanager.cpp",
        (const char *)(unsigned int)v3,
        v8);
  }
  if ( *((_BYTE *)this + 104) )
  {
    v4 = RtwqShutdown();
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\rtthreadmanager.cpp",
        (const char *)(unsigned int)v4,
        v8);
  }
  v5 = (_QWORD **)*((_QWORD *)this + 11);
  *v5[1] = 0;
  v6 = *v5;
  if ( *v5 )
  {
    do
    {
      v7 = (_QWORD *)*v6;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v6 + 2);
      std::_Deallocate<16>(v6, 24);
      v6 = v7;
    }
    while ( v7 );
  }
  std::_Deallocate<16>(*((_QWORD *)this + 11), 24);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 40);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x14007ce78  mov     [rsp+arg_0], rbx
0x14007ce7d  mov     [rsp+arg_8], rsi
0x14007ce82  push    rdi; int
0x14007ce83  sub     rsp, 20h
0x14007ce87  lea     rax, ??_7CRTThreadManager@@6B@; const CRTThreadManager::`vftable'
0x14007ce8e  mov     rdi, rcx
0x14007ce91  mov     [rcx], rax
0x14007ce94  mov     ecx, [rcx+18h]; workQueueId
0x14007ce97  test    ecx, ecx
0x14007ce99  jz      short loc_14007CEBE
0x14007ce9b  call    cs:__imp_RtwqUnlockWorkQueue
0x14007cea1  test    eax, eax
0x14007cea3  jns     short loc_14007CEBE
0x14007cea5  mov     rcx, [rsp+28h]; this
0x14007ceaa  lea     r8, aAvcoreAudiocor_38; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14007ceb1  mov     r9d, eax; char *
0x14007ceb4  mov     edx, 83h; void *
0x14007ceb9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14007cebe  cmp     byte ptr [rdi+68h], 0
0x14007cec2  jz      short loc_14007CEE7
0x14007cec4  call    cs:__imp_RtwqShutdown
0x14007ceca  test    eax, eax
0x14007cecc  jns     short loc_14007CEE7
0x14007cece  mov     rcx, [rsp+28h]; this
0x14007ced3  lea     r8, aAvcoreAudiocor_38; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14007ceda  mov     r9d, eax; char *
0x14007cedd  mov     edx, 88h; void *
0x14007cee2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14007cee7  mov     rcx, [rdi+58h]
0x14007ceeb  mov     rax, [rcx+8]
0x14007ceef  mov     qword ptr [rax], 0
0x14007cef6  mov     rsi, [rcx]
0x14007cef9  test    rsi, rsi
0x14007cefc  jz      short loc_14007CF1F
0x14007cefe  mov     rbx, [rsi]
0x14007cf01  lea     rcx, [rsi+10h]
0x14007cf05  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007cf0a  mov     edx, 18h
0x14007cf0f  mov     rcx, rsi
0x14007cf12  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14007cf17  mov     rsi, rbx
0x14007cf1a  test    rbx, rbx
0x14007cf1d  jnz     short loc_14007CEFE
0x14007cf1f  mov     rcx, [rdi+58h]
0x14007cf23  mov     edx, 18h
0x14007cf28  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14007cf2d  lea     rcx, [rdi+30h]; lpCriticalSection
0x14007cf31  call    cs:__imp_DeleteCriticalSection
0x14007cf37  lea     rcx, [rdi+28h]
0x14007cf3b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007cf40  mov     rbx, [rsp+28h+arg_0]
0x14007cf45  mov     rsi, [rsp+28h+arg_8]
0x14007cf4a  mov     dword ptr [rdi+0Ch], 0C0000001h
0x14007cf51  add     rsp, 20h
0x14007cf55  pop     rdi
0x14007cf56  retn
```
