# CNetworkExplorerFolderViewCB::_StartProgressBar(void)

- ea: `0x18000cc44`
- end: `0x18000ce2b`
- name: `?_StartProgressBar@CNetworkExplorerFolderViewCB@@AEAAJXZ`
- size: `487`
- prototype: `__int64 __fastcall(CNetworkExplorerFolderViewCB *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18000c984`
- `0x18000cb00`

## callees

- `0x180002a90`
- `0x18000693c`
- `0x180006bcc`
- `0x18000c690`
- `0x18000cc44`
- `0x18000ce34`
- `0x18000ced8`
- `0x18000de78`
- `0x18000dee0`
- `0x180010010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000ccb5`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000ccb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNetworkExplorerFolderViewCB::_StartProgressBar(CNetworkExplorerFolderViewCB *this)
{
  unsigned int *v2; // r14
  unsigned int v3; // ecx
  IUnknown *v4; // rcx
  HRESULT started; // edi
  __int64 v6; // rdx
  int v7; // r15d
  _QWORD *v8; // rax
  _QWORD *v9; // rsi
  void *ppvOut; // [rsp+50h] [rbp+30h] BYREF
  void *v12; // [rsp+58h] [rbp+38h] BYREF

  v2 = (unsigned int *)((char *)this + 32);
  v3 = *((_DWORD *)this + 8);
  if ( v3 )
  {
    GIT_CancelInform(v3, &stru_1800141C8);
    GIT_CancelInform(*v2, &stru_1800141B8);
  }
  CNetworkExplorerFolderViewCB::_StopTimer(this);
  CNetworkExplorerFolderViewCB::_StopProgressBar(this);
  v4 = (IUnknown *)*((_QWORD *)this + 7);
  *v2 = 0;
  ppvOut = 0;
  started = IUnknown_QueryService(
              v4,
              &IID_IBrowserProgressAggregator,
              &GUID_18140cbd_aa23_4384_a38d_6a8d3e2be505,
              &ppvOut);
  if ( started >= 0 )
  {
    started = (*(__int64 (__fastcall **)(void *, unsigned int *))(*(_QWORD *)ppvOut + 40LL))(ppvOut, v2);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    if ( started >= 0 )
    {
      LODWORD(ppvOut) = 0;
      started = (*(__int64 (__fastcall **)(_QWORD, void **))(**((_QWORD **)this + 8) + 96LL))(
                  *((_QWORD *)this + 8),
                  &ppvOut);
      if ( started >= 0 && !(_DWORD)ppvOut )
      {
        started = GIT_RegisterProgress(*v2, v6, (char *)this + 36);
        if ( started < 0 )
        {
          *v2 = 0;
        }
        else
        {
          started = CNetworkExplorerFolderViewCB::_StartTimer(this);
          if ( started < 0 )
            CNetworkExplorerFolderViewCB::_StopProgressBar(this);
        }
      }
      LODWORD(v12) = 0;
      if ( CNetworkExplorerFolder::_GetInforBarStatus(
             *((CNetworkExplorerFolder **)this + 3),
             (enum INFOBAR_STATE *)&v12) >= 0 )
      {
        v7 = (int)v12;
        if ( (_DWORD)v12 != 4 )
        {
          v8 = operator new(0x20u);
          v9 = v8;
          v12 = v8;
          if ( v8 )
          {
            *v8 = &CNetworkExplorerInfoBar::`vftable';
            *((_DWORD *)v8 + 2) = 1;
            *((_DWORD *)v8 + 3) = v7;
            v8[2] = this;
            v8[3] = 0;
            (*(void (__fastcall **)(CNetworkExplorerFolderViewCB *))(*(_QWORD *)this + 8LL))(this);
          }
          else
          {
            v9 = 0;
          }
          if ( v9 )
          {
            v12 = 0;
            started = UnMarshalFromGIT(*v2, &GUID_e38fe0f3_3db0_47ee_a314_25cf7f4bf521, &v12);
            if ( started >= 0 )
            {
              started = (*(__int64 (__fastcall **)(void *, _QWORD *))(*(_QWORD *)v12 + 24LL))(v12, v9);
              (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
            }
            (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
          }
        }
      }
    }
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18000cc44  mov     [rsp-28h+arg_10], rbx
0x18000cc49  push    rbp
0x18000cc4a  push    rsi
0x18000cc4b  push    rdi
0x18000cc4c  push    r14
0x18000cc4e  push    r15
0x18000cc50  mov     rbp, rsp
0x18000cc53  sub     rsp, 20h
0x18000cc57  mov     rbx, rcx
0x18000cc5a  lea     r14, [rcx+20h]
0x18000cc5e  mov     ecx, [r14]; unsigned int
0x18000cc61  test    ecx, ecx
0x18000cc63  jz      short loc_18000CC80
0x18000cc65  lea     rdx, stru_1800141C8; struct _GUID *
0x18000cc6c  call    ?GIT_CancelInform@@YAJKAEBU_GUID@@@Z; GIT_CancelInform(ulong,_GUID const &)
0x18000cc71  lea     rdx, stru_1800141B8; struct _GUID *
0x18000cc78  mov     ecx, [r14]; unsigned int
0x18000cc7b  call    ?GIT_CancelInform@@YAJKAEBU_GUID@@@Z; GIT_CancelInform(ulong,_GUID const &)
0x18000cc80  mov     rcx, rbx; this
0x18000cc83  call    ?_StopTimer@CNetworkExplorerFolderViewCB@@AEAAJXZ; CNetworkExplorerFolderViewCB::_StopTimer(void)
0x18000cc88  mov     rcx, rbx; this
0x18000cc8b  call    ?_StopProgressBar@CNetworkExplorerFolderViewCB@@AEAAJXZ; CNetworkExplorerFolderViewCB::_StopProgressBar(void)
0x18000cc90  mov     rcx, [rbx+38h]; punk
0x18000cc94  mov     dword ptr [r14], 0
0x18000cc9b  mov     [rbp+ppvOut], 0
0x18000cca3  lea     r9, [rbp+ppvOut]; ppvOut
0x18000cca7  lea     r8, _GUID_18140cbd_aa23_4384_a38d_6a8d3e2be505; riid
0x18000ccae  lea     rdx, IID_IBrowserProgressAggregator; guidService
0x18000ccb5  call    cs:__imp_IUnknown_QueryService
0x18000ccbb  mov     edi, eax
0x18000ccbd  test    eax, eax
0x18000ccbf  js      loc_18000CE18
0x18000ccc5  mov     rcx, [rbp+ppvOut]
0x18000ccc9  mov     rax, [rcx]
0x18000cccc  mov     rdx, r14
0x18000cccf  mov     rax, [rax+28h]
0x18000ccd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccd8  mov     edi, eax
0x18000ccda  mov     rcx, [rbp+ppvOut]
0x18000ccde  mov     rax, [rcx]
0x18000cce1  mov     rax, [rax+10h]
0x18000cce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccea  test    edi, edi
0x18000ccec  js      loc_18000CE18
0x18000ccf2  mov     dword ptr [rbp+ppvOut], 0
0x18000ccf9  mov     rcx, [rbx+40h]
0x18000ccfd  mov     rax, [rcx]
0x18000cd00  lea     rdx, [rbp+ppvOut]
0x18000cd04  mov     rax, [rax+60h]
0x18000cd08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd0d  mov     edi, eax
0x18000cd0f  test    eax, eax
0x18000cd11  js      short loc_18000CD4A
0x18000cd13  cmp     dword ptr [rbp+ppvOut], 0
0x18000cd17  jnz     short loc_18000CD4A
0x18000cd19  lea     r8, [rbx+24h]
0x18000cd1d  mov     ecx, [r14]
0x18000cd20  call    ?GIT_RegisterProgress@@YAJKAEBU_GUID@@PEAKW4tagBPASCODE@@@Z; GIT_RegisterProgress(ulong,_GUID const &,ulong *,tagBPASCODE)
0x18000cd25  mov     edi, eax
0x18000cd27  test    eax, eax
0x18000cd29  js      short loc_18000CD43
0x18000cd2b  mov     rcx, rbx; this
0x18000cd2e  call    ?_StartTimer@CNetworkExplorerFolderViewCB@@AEAAJXZ; CNetworkExplorerFolderViewCB::_StartTimer(void)
0x18000cd33  mov     edi, eax
0x18000cd35  test    eax, eax
0x18000cd37  jns     short loc_18000CD4A
0x18000cd39  mov     rcx, rbx; this
0x18000cd3c  call    ?_StopProgressBar@CNetworkExplorerFolderViewCB@@AEAAJXZ; CNetworkExplorerFolderViewCB::_StopProgressBar(void)
0x18000cd41  jmp     short loc_18000CD4A
0x18000cd43  mov     dword ptr [r14], 0
0x18000cd4a  mov     dword ptr [rbp+arg_8], 0
0x18000cd51  lea     rdx, [rbp+arg_8]; enum INFOBAR_STATE *
0x18000cd55  mov     rcx, [rbx+18h]; this
0x18000cd59  call    ?_GetInforBarStatus@CNetworkExplorerFolder@@AEAAJPEAW4INFOBAR_STATE@@@Z; CNetworkExplorerFolder::_GetInforBarStatus(INFOBAR_STATE *)
0x18000cd5e  test    eax, eax
0x18000cd60  js      loc_18000CE18
0x18000cd66  mov     r15d, dword ptr [rbp+arg_8]
0x18000cd6a  cmp     r15d, 4
0x18000cd6e  jz      loc_18000CE18
0x18000cd74  mov     ecx, 20h ; ' '; unsigned __int64
0x18000cd79  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cd7e  mov     rsi, rax
0x18000cd81  mov     [rbp+arg_8], rax
0x18000cd85  test    rax, rax
0x18000cd88  jz      short loc_18000CDBC
0x18000cd8a  lea     rax, ??_7CNetworkExplorerInfoBar@@6B@; const CNetworkExplorerInfoBar::`vftable'
0x18000cd91  mov     [rsi], rax
0x18000cd94  mov     dword ptr [rsi+8], 1
0x18000cd9b  mov     [rsi+0Ch], r15d
0x18000cd9f  mov     [rsi+10h], rbx
0x18000cda3  mov     qword ptr [rsi+18h], 0
0x18000cdab  mov     rax, [rbx]
0x18000cdae  mov     rcx, rbx
0x18000cdb1  mov     rax, [rax+8]
0x18000cdb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdba  jmp     short loc_18000CDBE
0x18000cdbc  xor     esi, esi
0x18000cdbe  test    rsi, rsi
0x18000cdc1  jz      short loc_18000CE18
0x18000cdc3  mov     [rbp+arg_8], 0
0x18000cdcb  lea     r8, [rbp+arg_8]; void **
0x18000cdcf  lea     rdx, _GUID_e38fe0f3_3db0_47ee_a314_25cf7f4bf521; struct _GUID *
0x18000cdd6  mov     ecx, [r14]; unsigned int
0x18000cdd9  call    ?UnMarshalFromGIT@@YAJKAEBU_GUID@@PEAPEAX@Z; UnMarshalFromGIT(ulong,_GUID const &,void * *)
0x18000cdde  mov     edi, eax
0x18000cde0  test    eax, eax
0x18000cde2  js      short loc_18000CE09
0x18000cde4  mov     rcx, [rbp+arg_8]
0x18000cde8  mov     rax, [rcx]
0x18000cdeb  mov     rdx, rsi
0x18000cdee  mov     rax, [rax+18h]
0x18000cdf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdf7  mov     edi, eax
0x18000cdf9  mov     rcx, [rbp+arg_8]
0x18000cdfd  mov     rax, [rcx]
0x18000ce00  mov     rax, [rax+10h]
0x18000ce04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce09  mov     rax, [rsi]
0x18000ce0c  mov     rcx, rsi
0x18000ce0f  mov     rax, [rax+10h]
0x18000ce13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce18  mov     eax, edi
0x18000ce1a  mov     rbx, [rsp+20h+arg_10]
0x18000ce1f  add     rsp, 20h
0x18000ce23  pop     r15
0x18000ce25  pop     r14
0x18000ce27  pop     rdi
0x18000ce28  pop     rsi
0x18000ce29  pop     rbp
0x18000ce2a  retn
```
