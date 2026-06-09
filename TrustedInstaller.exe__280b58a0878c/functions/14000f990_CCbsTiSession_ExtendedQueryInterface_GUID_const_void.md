# CCbsTiSession::ExtendedQueryInterface(_GUID const &,void * *)

- ea: `0x14000f990`
- end: `0x14000fb5b`
- name: `?ExtendedQueryInterface@CCbsTiSession@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `459`
- prototype: `__int64 __fastcall(CCbsTiSession *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x140002070`
- `0x140006344`
- `0x14000695c`
- `0x14000f990`
- `0x140010254`
- `0x140017658`
- `0x14001c6c0`
- `0x14002b010`

## string_xrefs

- `0x14000faec`: `Failed to allocate new CbsIdleHander`

## pseudocode

```c
__int64 __fastcall CCbsTiSession::ExtendedQueryInterface(CCbsTiSession *this, const struct _GUID *a2, void **a3)
{
  unsigned int v6; // ebx
  CCbsIdleHandler *v7; // rax
  CCbsIdleHandler *v8; // r8
  __int64 v9; // rax
  CCbsIdleHandler *v10; // rcx
  char *v11; // rax
  char *v12; // rcx
  _BYTE v14[40]; // [rsp+20h] [rbp-28h] BYREF

  if ( a3 )
  {
    if ( *(_QWORD *)&GUID_839d7762_5121_4009_9234_4f0d19394f04.Data1 == *(_QWORD *)&a2->Data1
      && *(_QWORD *)GUID_839d7762_5121_4009_9234_4f0d19394f04.Data4 == *(_QWORD *)a2->Data4 )
    {
      MonitoredCritSecLocker::MonitoredCritSecLocker(
        (MonitoredCritSecLocker *)v14,
        (struct MonitoredCritSec *)&vScavengeHandlerLock,
        1);
      if ( CCbsTiSession::m_pIdleScavengeHandler )
      {
        MonitoredCritSecLocker::Unlock((MonitoredCritSecLocker *)v14);
        v12 = (char *)CCbsTiSession::m_pIdleScavengeHandler
            + *(int *)(*((_QWORD *)CCbsTiSession::m_pIdleScavengeHandler + 1) + 4LL)
            + 8;
        v6 = (**(__int64 (__fastcall ***)(char *, const struct _GUID *, void **))v12)(v12, a2, a3);
      }
      else
      {
        v7 = (CCbsIdleHandler *)operator new(0x40u);
        v8 = v7;
        if ( v7 )
        {
          CCbsTiSession::m_pIdleScavengeHandler = v7;
          *((_QWORD *)v7 + 1) = &CCbsArray<CCbsLock>::`vbtable';
          v6 = 0;
          *(_QWORD *)v7 = &CCbsIUnknownImpl<ITaskHandler,>::`vftable'{for `CCbsIUnknownImpl<ITaskHandler,>'};
          *((_QWORD *)v7 + 7) = &CCbsIUnknownImpl<ITaskHandler,>::`vftable'{for `ITaskHandler'};
          *((_DWORD *)v7 + 13) = 24;
          *(_QWORD *)v7 = &CCbsIdleHandler::`vftable'{for `CCbsIUnknownImpl<ITaskHandler,>'};
          v9 = *((_QWORD *)v7 + 1);
          *((_DWORD *)v8 + 4) = 1;
          *(_QWORD *)((char *)v8 + *(int *)(v9 + 4) + 8) = &CCbsIdleHandler::`vftable'{for `ITaskHandler'};
          v10 = (CCbsIdleHandler *)*(int *)(*((_QWORD *)v8 + 1) + 4LL);
          *(_DWORD *)((char *)v8 + (_QWORD)v10 + 4) = (_DWORD)v10 - 48;
          *((_QWORD *)v8 + 3) = 0;
          *((_QWORD *)v8 + 4) = 0;
          *((_DWORD *)v8 + 10) = 0;
          CCbsIdleHandler::Initialize(v10, (CCbsTiSession *)((char *)this - 8));
          if ( CCbsTiSession::m_pIdleScavengeHandler )
            v11 = (char *)CCbsTiSession::m_pIdleScavengeHandler
                + *(int *)(*((_QWORD *)CCbsTiSession::m_pIdleScavengeHandler + 1) + 4LL)
                + 8;
          else
            v11 = 0;
          *a3 = v11;
        }
        else
        {
          v6 = -2147024882;
          CCbsTiSession::m_pIdleScavengeHandler = 0;
          CBSWdsLogLight(0x4000000u, 0x8007000E, (size_t *)1, "Failed to allocate new CbsIdleHander");
        }
      }
      MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v14);
    }
    else
    {
      return (unsigned int)-2147467262;
    }
  }
  else
  {
    v6 = -2147467261;
    CBSWdsLogLight(0x4000000u, 0x80004003, (size_t *)1, "Invalid argument: ppvObject.");
  }
  return v6;
}

```

## disassembly

```asm
0x14000f990  mov     [rsp+arg_0], rbx
0x14000f995  mov     [rsp+arg_8], rsi
0x14000f99a  push    rdi
0x14000f99b  sub     rsp, 40h
0x14000f99f  mov     rdi, r8
0x14000f9a2  mov     rbx, rdx
0x14000f9a5  mov     rsi, rcx
0x14000f9a8  test    r8, r8
0x14000f9ab  jnz     short loc_14000F9CE
0x14000f9ad  mov     ebx, 80004003h
0x14000f9b2  lea     r9, aInvalidArgumen_19; "Invalid argument: ppvObject."
0x14000f9b9  mov     edx, ebx
0x14000f9bb  lea     r8d, [rdi+1]
0x14000f9bf  mov     ecx, 4000000h
0x14000f9c4  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000f9c9  jmp     loc_14000FB49
0x14000f9ce  mov     rax, qword ptr cs:_GUID_839d7762_5121_4009_9234_4f0d19394f04.Data1
0x14000f9d5  cmp     rax, [rdx]
0x14000f9d8  jnz     loc_14000FB44
0x14000f9de  mov     rax, qword ptr cs:_GUID_839d7762_5121_4009_9234_4f0d19394f04.Data4
0x14000f9e5  cmp     rax, [rdx+8]
0x14000f9e9  jnz     loc_14000FB44
0x14000f9ef  mov     r8b, 1; bool
0x14000f9f2  lea     rdx, ?vScavengeHandlerLock@@3UMonitoredCritSec@@A; struct MonitoredCritSec *
0x14000f9f9  lea     rcx, [rsp+48h+var_28]; this
0x14000f9fe  call    ??0MonitoredCritSecLocker@@QEAA@AEAUMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(MonitoredCritSec &,bool)
0x14000fa03  cmp     cs:?m_pIdleScavengeHandler@CCbsTiSession@@2PEAVCCbsIdleHandler@@EA, 0; CCbsIdleHandler * CCbsTiSession::m_pIdleScavengeHandler
0x14000fa0b  jnz     loc_14000FB0F
0x14000fa11  mov     ecx, 40h ; '@'; Size
0x14000fa16  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000fa1b  mov     r8, rax
0x14000fa1e  test    rax, rax
0x14000fa21  jz      loc_14000FADA
0x14000fa27  lea     rax, ??_8?$CCbsArray@UCCbsLock@@@@7B@; const CCbsArray<CCbsLock>::`vbtable'
0x14000fa2e  mov     cs:?m_pIdleScavengeHandler@CCbsTiSession@@2PEAVCCbsIdleHandler@@EA, r8; CCbsIdleHandler * CCbsTiSession::m_pIdleScavengeHandler
0x14000fa35  mov     [r8+8], rax
0x14000fa39  xor     ebx, ebx
0x14000fa3b  lea     rax, ??_7?$CCbsIUnknownImpl@UITaskHandler@@$$V@@6B0@@; const CCbsIUnknownImpl<ITaskHandler,>::`vftable'{for `CCbsIUnknownImpl<ITaskHandler,>'}
0x14000fa42  mov     [r8], rax
0x14000fa45  lea     rax, ??_7?$CCbsIUnknownImpl@UITaskHandler@@$$V@@6BITaskHandler@@@; const CCbsIUnknownImpl<ITaskHandler,>::`vftable'{for `ITaskHandler'}
0x14000fa4c  mov     [r8+38h], rax
0x14000fa50  movsxd  rax, cs:dword_140033A18
0x14000fa57  lea     ecx, [rax-18h]
0x14000fa5a  mov     [rax+r8+4], ecx
0x14000fa5f  lea     rax, ??_7CCbsIdleHandler@@6B?$CCbsIUnknownImpl@UITaskHandler@@$$V@@@; const CCbsIdleHandler::`vftable'{for `CCbsIUnknownImpl<ITaskHandler,>'}
0x14000fa66  mov     [r8], rax
0x14000fa69  mov     rax, [r8+8]
0x14000fa6d  mov     dword ptr [r8+10h], 1
0x14000fa75  movsxd  rcx, dword ptr [rax+4]
0x14000fa79  lea     rax, ??_7CCbsIdleHandler@@6BITaskHandler@@@; const CCbsIdleHandler::`vftable'{for `ITaskHandler'}
0x14000fa80  mov     [rcx+r8+8], rax
0x14000fa85  mov     rax, [r8+8]
0x14000fa89  movsxd  rcx, dword ptr [rax+4]; this
0x14000fa8d  lea     edx, [rcx-30h]
0x14000fa90  mov     [rcx+r8+4], edx
0x14000fa95  lea     rdx, [rsi-8]; struct CCbsTiSession *
0x14000fa99  mov     qword ptr [r8+18h], 0
0x14000faa1  mov     qword ptr [r8+20h], 0
0x14000faa9  mov     dword ptr [r8+28h], 0
0x14000fab1  call    ?Initialize@CCbsIdleHandler@@QEAAJPEAVCCbsTiSession@@@Z; CCbsIdleHandler::Initialize(CCbsTiSession *)
0x14000fab6  mov     rdx, cs:?m_pIdleScavengeHandler@CCbsTiSession@@2PEAVCCbsIdleHandler@@EA; CCbsIdleHandler * CCbsTiSession::m_pIdleScavengeHandler
0x14000fabd  test    rdx, rdx
0x14000fac0  jnz     short loc_14000FAC6
0x14000fac2  xor     eax, eax
0x14000fac4  jmp     short loc_14000FAD5
0x14000fac6  mov     rax, [rdx+8]
0x14000faca  movsxd  rax, dword ptr [rax+4]
0x14000face  add     rax, 8
0x14000fad2  add     rax, rdx
0x14000fad5  mov     [rdi], rax
0x14000fad8  jmp     short loc_14000FB03
0x14000fada  mov     ebx, 8007000Eh
0x14000fadf  mov     cs:?m_pIdleScavengeHandler@CCbsTiSession@@2PEAVCCbsIdleHandler@@EA, 0; CCbsIdleHandler * CCbsTiSession::m_pIdleScavengeHandler
0x14000faea  mov     edx, ebx
0x14000faec  lea     r9, aFailedToAlloca_10; "Failed to allocate new CbsIdleHander"
0x14000faf3  mov     r8d, 1
0x14000faf9  mov     ecx, 4000000h
0x14000fafe  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000fb03  lea     rcx, [rsp+48h+var_28]; this
0x14000fb08  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x14000fb0d  jmp     short loc_14000FB49
0x14000fb0f  lea     rcx, [rsp+48h+var_28]; this
0x14000fb14  call    ?Unlock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Unlock(void)
0x14000fb19  mov     rdx, cs:?m_pIdleScavengeHandler@CCbsTiSession@@2PEAVCCbsIdleHandler@@EA; CCbsIdleHandler * CCbsTiSession::m_pIdleScavengeHandler
0x14000fb20  mov     r8, rdi
0x14000fb23  mov     rax, [rdx+8]
0x14000fb27  add     rdx, 8
0x14000fb2b  movsxd  rcx, dword ptr [rax+4]
0x14000fb2f  add     rcx, rdx
0x14000fb32  mov     rdx, rbx
0x14000fb35  mov     rax, [rcx]
0x14000fb38  mov     rax, [rax]
0x14000fb3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fb40  mov     ebx, eax
0x14000fb42  jmp     short loc_14000FB03
0x14000fb44  mov     ebx, 80004002h
0x14000fb49  mov     rsi, [rsp+48h+arg_8]
0x14000fb4e  mov     eax, ebx
0x14000fb50  mov     rbx, [rsp+48h+arg_0]
0x14000fb55  add     rsp, 40h
0x14000fb59  pop     rdi
0x14000fb5a  retn
```
