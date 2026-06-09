# CItemInfo::AddEvent(SYNCMGR_EVENTINFO * *)

- ea: `0x18001b9e0`
- end: `0x18001bae7`
- name: `?AddEvent@CItemInfo@@QEAAJPEAPEAUSYNCMGR_EVENTINFO@@@Z`
- size: `263`
- prototype: `__int64 __fastcall(CItemInfo *__hidden this, struct SYNCMGR_EVENTINFO **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800167c0`

## callees

- `0x180008a90`
- `0x180009940`
- `0x180010310`
- `0x18001b9e0`
- `0x18001bc14`
- `0x18001c4dc`
- `0x180039a70`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x18001babd`
- `SHELL32!SHChangeNotify` at `0x18001babd`
- `SHELL32!__imp_ILFree` at `0x18001bac8`
- `SHELL32!__imp_ILFree` at `0x18001bac8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ba8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ba8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b9f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b9f3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001ba62`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001ba62`

## pseudocode

```c
__int64 __fastcall CItemInfo::AddEvent(CItemInfo *this, struct SYNCMGR_EVENTINFO **a2)
{
  const struct _GUID *v4; // rdx
  int appended; // esi
  LONG v6; // eax
  void *v7; // rcx
  LPCVOID dwItem1; // [rsp+50h] [rbp+8h] BYREF

  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 3));
  if ( !*((_QWORD *)this + 244) )
    CDPA_Base<SYNCMGR_EVENTINFO,CTContainer_PolicyUnOwned<SYNCMGR_EVENTINFO>>::Create((char *)this + 1952, 4);
  v4 = (const struct _GUID *)((char *)*a2 + 256);
  dwItem1 = 0;
  appended = -2147024816;
  if ( (unsigned int)CItemInfo::FindEvent(this, v4, (struct SYNCMGR_EVENTINFO **)&dwItem1) == -2147024894 )
  {
    appended = CDPA_Base<CHandlerCollectionInfo,CTContainer_PolicyUnOwned<CHandlerCollectionInfo>>::AppendPtr(
                 (char *)this + 1952,
                 *a2);
    if ( appended >= 0 )
    {
      v6 = CompareFileTime((const FILETIME *)((char *)this + 852), (const FILETIME *)((char *)*a2 + 2868));
      if ( *((_DWORD *)*a2 + 68) == 4 && v6 < 0 )
        CItemInfo::SetErrorCount(this, *((_DWORD *)this + 215) + 1);
    }
  }
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 3));
  v7 = *a2;
  if ( appended < 0 )
  {
    CZeroInitNew::operator delete(v7);
  }
  else
  {
    dwItem1 = 0;
    if ( (int)GetPidlForEvent((const struct SYNCMGR_EVENTINFO *)v7, (struct _ITEMIDLIST_ABSOLUTE **)&dwItem1) >= 0 )
    {
      SHChangeNotify(2, 0, dwItem1, 0);
      ILFree((LPITEMIDLIST)dwItem1);
    }
  }
  *a2 = 0;
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18001b9e0  push    rbx
0x18001b9e2  push    rbp
0x18001b9e3  push    rsi
0x18001b9e4  push    rdi
0x18001b9e5  sub     rsp, 28h
0x18001b9e9  mov     rbx, rcx
0x18001b9ec  mov     rdi, rdx
0x18001b9ef  mov     rcx, [rcx+18h]; lpCriticalSection
0x18001b9f3  call    cs:__imp_EnterCriticalSection
0x18001b9f9  lea     rbp, [rbx+7A0h]
0x18001ba00  cmp     qword ptr [rbp+0], 0
0x18001ba05  jnz     short loc_18001BA14
0x18001ba07  mov     edx, 4
0x18001ba0c  mov     rcx, rbp
0x18001ba0f  call    ?Create@?$CDPA_Base@USYNCMGR_EVENTINFO@@V?$CTContainer_PolicyUnOwned@USYNCMGR_EVENTINFO@@@@@@QEAAHH@Z; CDPA_Base<SYNCMGR_EVENTINFO,CTContainer_PolicyUnOwned<SYNCMGR_EVENTINFO>>::Create(int)
0x18001ba14  mov     rdx, [rdi]
0x18001ba17  lea     r8, [rsp+48h+dwItem1]; struct SYNCMGR_EVENTINFO **
0x18001ba1c  add     rdx, 100h; struct _GUID *
0x18001ba23  mov     [rsp+48h+dwItem1], 0
0x18001ba2c  mov     rcx, rbx; this
0x18001ba2f  mov     esi, 80070050h
0x18001ba34  call    ?FindEvent@CItemInfo@@QEBAJAEBU_GUID@@PEAPEAUSYNCMGR_EVENTINFO@@@Z; CItemInfo::FindEvent(_GUID const &,SYNCMGR_EVENTINFO * *)
0x18001ba39  cmp     eax, 80070002h
0x18001ba3e  jnz     short loc_18001BA88
0x18001ba40  mov     rdx, [rdi]
0x18001ba43  mov     rcx, rbp
0x18001ba46  call    ?AppendPtr@?$CDPA_Base@VCHandlerCollectionInfo@@V?$CTContainer_PolicyUnOwned@VCHandlerCollectionInfo@@@@@@QEAAJPEAVCHandlerCollectionInfo@@PEAH@Z; CDPA_Base<CHandlerCollectionInfo,CTContainer_PolicyUnOwned<CHandlerCollectionInfo>>::AppendPtr(CHandlerCollectionInfo *,int *)
0x18001ba4b  mov     esi, eax
0x18001ba4d  test    eax, eax
0x18001ba4f  js      short loc_18001BA88
0x18001ba51  mov     rdx, [rdi]
0x18001ba54  lea     rcx, [rbx+354h]; lpFileTime1
0x18001ba5b  add     rdx, 0B34h; lpFileTime2
0x18001ba62  call    cs:__imp_CompareFileTime
0x18001ba68  mov     rcx, [rdi]
0x18001ba6b  cmp     dword ptr [rcx+110h], 4
0x18001ba72  jnz     short loc_18001BA88
0x18001ba74  test    eax, eax
0x18001ba76  jns     short loc_18001BA88
0x18001ba78  mov     edx, [rbx+35Ch]
0x18001ba7e  mov     rcx, rbx; this
0x18001ba81  inc     edx; unsigned int
0x18001ba83  call    ?SetErrorCount@CItemInfo@@QEAAXK@Z; CItemInfo::SetErrorCount(ulong)
0x18001ba88  mov     rcx, [rbx+18h]; lpCriticalSection
0x18001ba8c  call    cs:__imp_LeaveCriticalSection
0x18001ba92  mov     rcx, [rdi]; lpMem
0x18001ba95  test    esi, esi
0x18001ba97  js      short loc_18001BAD0
0x18001ba99  lea     rdx, [rsp+48h+dwItem1]; struct _ITEMIDLIST_ABSOLUTE **
0x18001ba9e  mov     [rsp+48h+dwItem1], 0
0x18001baa7  call    ?GetPidlForEvent@@YAJPEBUSYNCMGR_EVENTINFO@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; GetPidlForEvent(SYNCMGR_EVENTINFO const *,_ITEMIDLIST_ABSOLUTE * *)
0x18001baac  test    eax, eax
0x18001baae  js      short loc_18001BAD5
0x18001bab0  mov     r8, [rsp+48h+dwItem1]; dwItem1
0x18001bab5  xor     edx, edx; uFlags
0x18001bab7  xor     r9d, r9d; dwItem2
0x18001baba  lea     ecx, [rdx+2]; wEventId
0x18001babd  call    cs:__imp_SHChangeNotify
0x18001bac3  mov     rcx, [rsp+48h+dwItem1]; pidl
0x18001bac8  call    cs:__imp_ILFree
0x18001bace  jmp     short loc_18001BAD5
0x18001bad0  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x18001bad5  mov     qword ptr [rdi], 0
0x18001badc  mov     eax, esi
0x18001bade  add     rsp, 28h
0x18001bae2  pop     rdi
0x18001bae3  pop     rsi
0x18001bae4  pop     rbp
0x18001bae5  pop     rbx
0x18001bae6  retn
```
