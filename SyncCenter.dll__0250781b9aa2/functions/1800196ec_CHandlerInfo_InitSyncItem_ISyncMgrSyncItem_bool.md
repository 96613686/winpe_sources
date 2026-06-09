# CHandlerInfo::_InitSyncItem(ISyncMgrSyncItem *,bool)

- ea: `0x1800196ec`
- end: `0x18001997e`
- name: `?_InitSyncItem@CHandlerInfo@@AEAAJPEAUISyncMgrSyncItem@@_N@Z`
- size: `658`
- prototype: `__int64 __fastcall(CHandlerInfo *this, struct ISyncMgrSyncItem *, char)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180009e3c`
- `0x180017440`

## callees

- `0x180005660`
- `0x180005f90`
- `0x180009a9c`
- `0x18000a5e4`
- `0x18000b5f0`
- `0x180016690`
- `0x180019268`
- `0x1800196ec`
- `0x18001a4b4`
- `0x180021e20`
- `0x180021ef0`
- `0x180021f5c`
- `0x18005292a`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019880`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001993b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019880`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001993b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019790`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800198b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019923`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019790`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800198b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019923`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001994f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001994f`

## pseudocode

```c
__int64 __fastcall CHandlerInfo::_InitSyncItem(CHandlerInfo *this, struct ISyncMgrSyncItem *a2, char a3)
{
  struct ISyncMgrSyncItemVtbl *lpVtbl; // rax
  CHandlerInfo *v6; // rcx
  int ItemInfo; // ebx
  char v8; // di
  _BYTE *v9; // rdi
  int v10; // r12d
  char v11; // r15
  char v12; // r14
  bool v13; // bl
  char v14; // al
  char v15; // al
  LPVOID pv; // [rsp+48h] [rbp-81h] BYREF
  void *p[2]; // [rsp+50h] [rbp-79h] BYREF
  unsigned __int16 v20[64]; // [rsp+60h] [rbp-69h] BYREF

  p[0] = 0;
  memset_0(v20, 0, sizeof(v20));
  lpVtbl = a2->lpVtbl;
  pv = 0;
  ItemInfo = ((__int64 (__fastcall *)(struct ISyncMgrSyncItem *, LPVOID *))lpVtbl->GetItemID)(a2, &pv);
  if ( ItemInfo >= 0 )
  {
    ItemInfo = CHandlerInfo::_ValidateItemID(v6, (const unsigned __int16 *)pv);
    if ( ItemInfo >= 0 )
    {
      v8 = 0;
      StringCchCopyW(v20, 0x40u, (const unsigned __int16 *)pv);
      EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 1));
      ItemInfo = CHandlerInfo::_FindItemInfo(this, (const WCHAR *)pv, (struct CSyncItemInfo **)p);
      if ( ItemInfo >= 0 )
      {
        v9 = p[0];
        if ( *((_DWORD *)p[0] + 2) != 5 )
        {
          v12 = 0;
          v11 = 0;
          goto LABEL_15;
        }
        v8 = 1;
      }
      v10 = 0;
      v11 = 1;
      if ( ItemInfo >= 0 )
        v10 = ItemInfo;
      v12 = 0;
      if ( ItemInfo >= 0 )
        v12 = v8;
      v9 = operator new(0x7B0u);
      if ( v9 )
      {
        v13 = *((_DWORD *)this + 502) == 1;
        *(_OWORD *)p = *(_OWORD *)((char *)this + 100);
        CItemInfo::CItemInfo(v9, p, (char *)this + 116, pv);
        v9[1962] = v13;
        *(_QWORD *)v9 = &CSyncItemInfo::`vftable';
        ItemInfo = v10;
        v9[1961] = a3;
        *((_QWORD *)v9 + 5) = ((unsigned __int64)this + 2000) & -(__int64)((CHandlerInfo *)((char *)this + 40) != 0);
      }
      else
      {
        v9 = 0;
        ItemInfo = -2147024882;
      }
      p[0] = v9;
LABEL_15:
      LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 1));
      if ( ItemInfo < 0 || v12 )
        goto LABEL_25;
      ItemInfo = CSyncItemInfo::LoadSyncItemData((CSyncItemInfo *)v9, a2);
      if ( ItemInfo < 0 )
      {
        if ( !v11 )
        {
          EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 1));
          CItemState::MarkChangeState(v9 + 8, 5);
LABEL_24:
          LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 1));
        }
      }
      else if ( v11 == 1 )
      {
        EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 1));
        v14 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 5) + 8LL))((char *)this + 40);
        CSyncItemInfo::ShouldAppearEnabled((CSyncItemInfo *)v9, v14);
        v15 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 5) + 16LL))((char *)this + 40);
        CSyncItemInfo::ShouldAppearConnected((CSyncItemInfo *)v9, v15);
        if ( DPA_InsertPtr(*((HDPA *)this + 254), 0x7FFFFFFF, v9) == -1 )
        {
          ItemInfo = -2147024882;
        }
        else
        {
          ItemInfo = 0;
          p[0] = 0;
        }
        goto LABEL_24;
      }
LABEL_25:
      SafeRelease<CSyncItemInfo>(p);
    }
  }
  CoTaskMemFree(pv);
  return (unsigned int)ItemInfo;
}

```

## disassembly

```asm
0x1800196ec  mov     [rsp-8+arg_10], rbx
0x1800196f1  push    rbp
0x1800196f2  push    rsi
0x1800196f3  push    rdi
0x1800196f4  push    r12
0x1800196f6  push    r13
0x1800196f8  push    r14
0x1800196fa  push    r15
0x1800196fc  lea     rbp, [rsp-27h]
0x180019701  sub     rsp, 0F0h
0x180019708  mov     rax, cs:__security_cookie
0x18001970f  xor     rax, rsp
0x180019712  mov     [rbp+57h+var_40], rax
0x180019716  mov     [rsp+120h+var_E0], r8b
0x18001971b  mov     r13, rdx
0x18001971e  mov     rsi, rcx
0x180019721  mov     [rbp+57h+p], 0
0x180019729  xor     edx, edx; Val
0x18001972b  lea     rcx, [rbp+57h+var_C0]; void *
0x18001972f  mov     r8d, 80h; Size
0x180019735  call    memset_0
0x18001973a  mov     rax, [r13+0]
0x18001973e  lea     rdx, [rsp+120h+pv]
0x180019743  mov     rcx, r13
0x180019746  mov     [rsp+120h+pv], 0
0x18001974f  mov     rax, [rax+18h]
0x180019753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019758  mov     ebx, eax
0x18001975a  test    eax, eax
0x18001975c  js      loc_18001994A
0x180019762  mov     rdx, [rsp+120h+pv]; unsigned __int16 *
0x180019767  call    ?_ValidateItemID@CHandlerInfo@@AEBAJPEBG@Z; CHandlerInfo::_ValidateItemID(ushort const *)
0x18001976c  mov     ebx, eax
0x18001976e  test    eax, eax
0x180019770  js      loc_18001994A
0x180019776  mov     r8, [rsp+120h+pv]; unsigned __int16 *
0x18001977b  lea     rcx, [rbp+57h+var_C0]; unsigned __int16 *
0x18001977f  mov     edx, 40h ; '@'; unsigned __int64
0x180019784  xor     dil, dil
0x180019787  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001978c  mov     rcx, [rsi+8]; lpCriticalSection
0x180019790  call    cs:__imp_EnterCriticalSection
0x180019796  mov     rdx, [rsp+120h+pv]; unsigned __int16 *
0x18001979b  lea     r8, [rbp+57h+p]; struct CSyncItemInfo **
0x18001979f  mov     rcx, rsi; this
0x1800197a2  call    ?_FindItemInfo@CHandlerInfo@@AEBAJQEBGPEAPEAVCSyncItemInfo@@@Z; CHandlerInfo::_FindItemInfo(ushort const * const,CSyncItemInfo * *)
0x1800197a7  mov     ebx, eax
0x1800197a9  test    eax, eax
0x1800197ab  js      short loc_1800197BE
0x1800197ad  mov     rdi, [rbp+57h+p]
0x1800197b1  cmp     dword ptr [rdi+8], 5
0x1800197b5  jnz     loc_180019869
0x1800197bb  mov     dil, 1
0x1800197be  xor     r12d, r12d
0x1800197c1  movzx   eax, dil
0x1800197c5  test    ebx, ebx
0x1800197c7  mov     ecx, 7B0h; unsigned __int64
0x1800197cc  mov     r15b, 1
0x1800197cf  cmovns  r12d, ebx
0x1800197d3  xor     r14d, r14d
0x1800197d6  test    ebx, ebx
0x1800197d8  cmovns  r14d, eax
0x1800197dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800197e1  mov     rdi, rax
0x1800197e4  test    rax, rax
0x1800197e7  jz      loc_180019871
0x1800197ed  movups  xmm0, xmmword ptr [rsi+64h]
0x1800197f1  cmp     dword ptr [rsi+7D8h], 1
0x1800197f8  lea     rax, [rsi+838h]
0x1800197ff  mov     r9, [rsp+120h+pv]
0x180019804  lea     r8, [rsi+74h]
0x180019808  mov     [rsp+120h+var_E8], rax
0x18001980d  lea     rdx, [rbp+57h+p]
0x180019811  mov     rax, [rsi+8]
0x180019815  mov     rcx, rdi
0x180019818  mov     [rsp+120h+var_F0], rax
0x18001981d  setz    bl
0x180019820  mov     [rsp+120h+var_F8], 4
0x180019828  movdqu  xmmword ptr [rbp+57h+p], xmm0
0x18001982d  call    ??0CItemInfo@@IEAA@AEBU_GUID@@PEBG1KW4SYNCMGR_HANDLER_STATUS@@PEAU_RTL_CRITICAL_SECTION@@PEAVCMarkChangeStateStrategy@@@Z; CItemInfo::CItemInfo(_GUID const &,ushort const *,ushort const *,ulong,SYNCMGR_HANDLER_STATUS,_RTL_CRITICAL_SECTION *,CMarkChangeStateStrategy *)
0x180019832  lea     rax, ??_7CSyncItemInfo@@6B@; const CSyncItemInfo::`vftable'
0x180019839  mov     [rdi+7AAh], bl
0x18001983f  mov     [rdi], rax
0x180019842  lea     rdx, [rsi+7D0h]
0x180019849  mov     al, [rsp+120h+var_E0]
0x18001984d  mov     ebx, r12d
0x180019850  mov     [rdi+7A9h], al
0x180019856  lea     rax, [rsi+28h]
0x18001985a  neg     rax
0x18001985d  sbb     rcx, rcx
0x180019860  and     rcx, rdx
0x180019863  mov     [rdi+28h], rcx
0x180019867  jmp     short loc_180019878
0x180019869  xor     r14b, r14b
0x18001986c  xor     r15b, r15b
0x18001986f  jmp     short loc_18001987C
0x180019871  xor     edi, edi
0x180019873  mov     ebx, 8007000Eh
0x180019878  mov     [rbp+57h+p], rdi
0x18001987c  mov     rcx, [rsi+8]; lpCriticalSection
0x180019880  call    cs:__imp_LeaveCriticalSection
0x180019886  test    ebx, ebx
0x180019888  js      loc_180019941
0x18001988e  test    r14b, r14b
0x180019891  jnz     loc_180019941
0x180019897  mov     rdx, r13; struct ISyncMgrSyncItem *
0x18001989a  mov     rcx, rdi; this
0x18001989d  call    ?LoadSyncItemData@CSyncItemInfo@@QEAAJPEAUISyncMgrSyncItem@@@Z; CSyncItemInfo::LoadSyncItemData(ISyncMgrSyncItem *)
0x1800198a2  mov     ebx, eax
0x1800198a4  test    eax, eax
0x1800198a6  js      short loc_18001991A
0x1800198a8  cmp     r15b, 1
0x1800198ac  jnz     loc_180019941
0x1800198b2  mov     rcx, [rsi+8]; lpCriticalSection
0x1800198b6  call    cs:__imp_EnterCriticalSection
0x1800198bc  lea     rbx, [rsi+28h]
0x1800198c0  mov     rax, [rbx]
0x1800198c3  mov     rcx, rbx
0x1800198c6  mov     rax, [rax+8]
0x1800198ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198cf  mov     dl, al; bool
0x1800198d1  mov     rcx, rdi; this
0x1800198d4  call    ?ShouldAppearEnabled@CSyncItemInfo@@QEAAX_N@Z; CSyncItemInfo::ShouldAppearEnabled(bool)
0x1800198d9  mov     rax, [rbx]
0x1800198dc  mov     rcx, rbx
0x1800198df  mov     rax, [rax+10h]
0x1800198e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198e8  mov     dl, al; bool
0x1800198ea  mov     rcx, rdi; this
0x1800198ed  call    ?ShouldAppearConnected@CSyncItemInfo@@QEAAX_N@Z; CSyncItemInfo::ShouldAppearConnected(bool)
0x1800198f2  mov     rcx, [rsi+7F0h]; hdpa
0x1800198f9  mov     r8, rdi; p
0x1800198fc  mov     edx, 7FFFFFFFh; i
0x180019901  call    DPA_InsertPtr
0x180019906  cmp     eax, 0FFFFFFFFh
0x180019909  jz      short loc_180019913
0x18001990b  xor     ebx, ebx
0x18001990d  mov     [rbp+57h+p], rbx
0x180019911  jmp     short loc_180019937
0x180019913  mov     ebx, 8007000Eh
0x180019918  jmp     short loc_180019937
0x18001991a  test    r15b, r15b
0x18001991d  jnz     short loc_180019941
0x18001991f  mov     rcx, [rsi+8]; lpCriticalSection
0x180019923  call    cs:__imp_EnterCriticalSection
0x180019929  lea     rcx, [rdi+8]
0x18001992d  mov     edx, 5
0x180019932  call    ?MarkChangeState@CItemState@@QEAAJW4SYNCMGR_INVALIDATE_REASON@@@Z; CItemState::MarkChangeState(SYNCMGR_INVALIDATE_REASON)
0x180019937  mov     rcx, [rsi+8]; lpCriticalSection
0x18001993b  call    cs:__imp_LeaveCriticalSection
0x180019941  lea     rcx, [rbp+57h+p]
0x180019945  call    ??$SafeRelease@VCSyncItemInfo@@@@YAXPEAPEAVCSyncItemInfo@@@Z; SafeRelease<CSyncItemInfo>(CSyncItemInfo * *)
0x18001994a  mov     rcx, [rsp+120h+pv]; pv
0x18001994f  call    cs:__imp_CoTaskMemFree
0x180019955  mov     eax, ebx
0x180019957  mov     rcx, [rbp+57h+var_40]
0x18001995b  xor     rcx, rsp; StackCookie
0x18001995e  call    __security_check_cookie
0x180019963  mov     rbx, [rsp+120h+arg_10]
0x18001996b  add     rsp, 0F0h
0x180019972  pop     r15
0x180019974  pop     r14
0x180019976  pop     r13
0x180019978  pop     r12
0x18001997a  pop     rdi
0x18001997b  pop     rsi
0x18001997c  pop     rbp
0x18001997d  retn
```
