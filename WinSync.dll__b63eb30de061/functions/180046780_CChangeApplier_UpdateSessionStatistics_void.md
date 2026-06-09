# CChangeApplier::UpdateSessionStatistics(void)

- ea: `0x180046780`
- end: `0x180046a09`
- name: `?UpdateSessionStatistics@CChangeApplier@@AEAAJXZ`
- size: `649`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180040aa4`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x1800227b0`
- `0x180046780`
- `0x180067f28`
- `0x180068b64`
- `0x18006d7a4`
- `0x1800709c0`
- `0x1800721fc`
- `0x180072558`
- `0x180094010`

## string_xrefs

- `0x1800467bc`: `CChangeApplier::UpdateSessionStatistics`
- `0x1800469d4`: `CChangeApplier::UpdateSessionStatistics`

## pseudocode

```c
__int64 __fastcall CChangeApplier::UpdateSessionStatistics(CChangeApplier *this)
{
  CSyncChangeWrapper *v2; // rcx
  int TransferFilters; // ebx
  BOOL v4; // edi
  BOOL v5; // ebp
  CSyncChangeWrapper *v6; // rcx
  int v7; // eax
  CEnumSyncChangeUnitWrappers *v8; // r14
  unsigned int v9; // edx
  unsigned int *v10; // r9
  CSyncChangeUnitWrapper *v11; // r15
  int Error; // eax
  __int64 v13; // r8
  __int64 v14; // rcx
  int v15; // eax
  int v16; // ecx
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v20; // [rsp+60h] [rbp+8h] BYREF
  CSyncChangeUnitWrapper *v21; // [rsp+68h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      306,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::UpdateSessionStatistics");
  }
  v2 = (CSyncChangeWrapper *)*((_QWORD *)this + 68);
  v20 = 0;
  TransferFilters = CSyncChangeWrapper::GetTransferFilters(v2, (enum SYNC_TRANSFER_FILTER *)&v20);
  if ( TransferFilters < 0 )
    goto LABEL_35;
  v4 = (v20 & 0x30) != 0;
  v5 = (v20 & 0x4000) != 0;
  if ( (v20 & 0x30) == 0 )
  {
    if ( (int)CSyncChangeWrapper::GetError(*((CSyncChangeWrapper **)this + 68)) >= 0 )
    {
      TransferFilters = CSyncChangeWrapper::SetFilter(*((_QWORD *)this + 68), 0);
      if ( TransferFilters >= 0 )
      {
        v6 = (CSyncChangeWrapper *)*((_QWORD *)this + 68);
        v21 = 0;
        v7 = CSyncChangeWrapper::GetChangeUnitWrappers(v6, &v21);
        TransferFilters = v7;
        if ( v7 == -2147217393 )
        {
          TransferFilters = 0;
        }
        else if ( v7 >= 0 )
        {
          v8 = v21;
          TransferFilters = (*(__int64 (__fastcall **)(CSyncChangeUnitWrapper *))(*(_QWORD *)v21 + 40LL))(v21);
          if ( TransferFilters >= 0 )
          {
            v21 = 0;
            do
            {
              TransferFilters = CEnumSyncChangeUnitWrappers::Next(v8, v9, &v21, v10);
              if ( TransferFilters )
                break;
              v11 = v21;
              Error = CSyncChangeUnitWrapper::GetError(v21);
              if ( Error >= 0 )
                TransferFilters = Error;
              else
                v4 = 1;
              if ( !v4 )
              {
                TransferFilters = CSyncChangeUnitWrapper::GetTransferFilters(v11, (enum SYNC_TRANSFER_FILTER *)&v20);
                if ( TransferFilters >= 0 )
                  v4 = (v20 & 0x30) != 0;
              }
              (*(void (__fastcall **)(CSyncChangeUnitWrapper *))(*(_QWORD *)v11 + 16LL))(v11);
              if ( TransferFilters < 0 )
                break;
            }
            while ( !v4 );
          }
          (*(void (__fastcall **)(CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v8 + 16LL))(v8);
        }
      }
    }
    else
    {
      TransferFilters = 0;
      v4 = 1;
    }
  }
  if ( v5 )
    goto LABEL_40;
  if ( v4 )
  {
    v13 = *((unsigned int *)this + 115);
    if ( (_DWORD)v13 == -1 )
    {
      v13 = 0xFFFFFFFFLL;
    }
    else if ( *((int *)this + 163) <= 0 || *((_DWORD *)this + 164) )
    {
      v13 = (unsigned int)(v13 + 1);
      *((_DWORD *)this + 115) = v13;
    }
    if ( TransferFilters >= 0 )
    {
      v14 = *((_QWORD *)this + 51);
      if ( v14 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v14 + 72LL))(
                v14,
                *((unsigned int *)this + 114),
                v13);
LABEL_39:
        TransferFilters = v15;
      }
    }
  }
  else
  {
LABEL_35:
    v16 = *((_DWORD *)this + 114);
    if ( v16 != -1 )
    {
      v17 = (unsigned int)(v16 + 1);
      *((_DWORD *)this + 114) = v17;
      if ( TransferFilters >= 0 )
      {
        v18 = *((_QWORD *)this + 51);
        if ( v18 )
        {
          v15 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v18 + 64LL))(
                  v18,
                  v17,
                  *((unsigned int *)this + 115));
          goto LABEL_39;
        }
      }
    }
  }
LABEL_40:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      307,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::UpdateSessionStatistics",
      TransferFilters);
  }
  return (unsigned int)TransferFilters;
}

```

## disassembly

```asm
0x180046780  mov     [rsp+arg_10], rbx
0x180046785  mov     [rsp+arg_18], rbp
0x18004678a  push    rsi
0x18004678b  push    rdi
0x18004678c  push    r13
0x18004678e  push    r14
0x180046790  push    r15
0x180046792  sub     rsp, 30h
0x180046796  mov     rsi, rcx
0x180046799  mov     rcx, cs:WPP_GLOBAL_Control
0x1800467a0  lea     r14, WPP_GLOBAL_Control
0x1800467a7  cmp     rcx, r14
0x1800467aa  jz      short loc_1800467D4
0x1800467ac  test    byte ptr [rcx+1Ch], 8
0x1800467b0  jz      short loc_1800467D4
0x1800467b2  cmp     byte ptr [rcx+19h], 5
0x1800467b6  jb      short loc_1800467D4
0x1800467b8  mov     rcx, [rcx+10h]
0x1800467bc  lea     r9, aCchangeapplier_59; "CChangeApplier::UpdateSessionStatistics"
0x1800467c3  mov     edx, 132h
0x1800467c8  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800467cf  call    WPP_SF_s
0x1800467d4  mov     rcx, [rsi+220h]; this
0x1800467db  lea     rdx, [rsp+58h+arg_0]; enum SYNC_TRANSFER_FILTER *
0x1800467e0  mov     [rsp+58h+arg_0], 0
0x1800467e8  call    ?GetTransferFilters@CSyncChangeWrapper@@QEAAJPEAW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeWrapper::GetTransferFilters(SYNC_TRANSFER_FILTER *)
0x1800467ed  mov     ebx, eax
0x1800467ef  test    eax, eax
0x1800467f1  js      loc_18004697D
0x1800467f7  test    byte ptr [rsp+58h+arg_0], 30h
0x1800467fc  mov     edi, 0
0x180046801  mov     r13d, 1
0x180046807  setnz   dil
0x18004680b  test    [rsp+58h+arg_0], 4000h
0x180046813  jz      short loc_18004681A
0x180046815  mov     ebp, r13d
0x180046818  jmp     short loc_18004681C
0x18004681a  xor     ebp, ebp
0x18004681c  test    edi, edi
0x18004681e  jnz     loc_180046924
0x180046824  mov     rcx, [rsi+220h]; this
0x18004682b  call    ?GetError@CSyncChangeWrapper@@QEAAJXZ; CSyncChangeWrapper::GetError(void)
0x180046830  test    eax, eax
0x180046832  jns     short loc_18004683E
0x180046834  xor     ebx, ebx
0x180046836  mov     edi, r13d
0x180046839  jmp     loc_180046924
0x18004683e  mov     rcx, [rsi+220h]
0x180046845  xor     edx, edx
0x180046847  call    ?SetFilter@CSyncChangeWrapper@@QEAAJW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeWrapper::SetFilter(SYNC_TRANSFER_FILTER)
0x18004684c  mov     ebx, eax
0x18004684e  test    eax, eax
0x180046850  js      loc_180046924
0x180046856  mov     rcx, [rsi+220h]; this
0x18004685d  lea     rdx, [rsp+58h+arg_8]; struct CEnumSyncChangeUnitWrappers **
0x180046862  mov     [rsp+58h+arg_8], 0
0x18004686b  call    ?GetChangeUnitWrappers@CSyncChangeWrapper@@QEAAJPEAPEAVCEnumSyncChangeUnitWrappers@@@Z; CSyncChangeWrapper::GetChangeUnitWrappers(CEnumSyncChangeUnitWrappers * *)
0x180046870  mov     ebx, eax
0x180046872  cmp     eax, 8004100Fh
0x180046877  jnz     short loc_180046880
0x180046879  xor     ebx, ebx
0x18004687b  jmp     loc_180046924
0x180046880  test    eax, eax
0x180046882  js      loc_180046924
0x180046888  mov     r14, [rsp+58h+arg_8]
0x18004688d  mov     rcx, r14
0x180046890  mov     rax, [r14]
0x180046893  mov     rax, [rax+28h]
0x180046897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004689c  mov     ebx, eax
0x18004689e  test    eax, eax
0x1800468a0  js      short loc_18004690E
0x1800468a2  mov     [rsp+58h+arg_8], 0
0x1800468ab  lea     r8, [rsp+58h+arg_8]; struct CSyncChangeUnitWrapper **
0x1800468b0  mov     rcx, r14; this
0x1800468b3  call    ?Next@CEnumSyncChangeUnitWrappers@@QEAAJKPEAPEAVCSyncChangeUnitWrapper@@PEAK@Z; CEnumSyncChangeUnitWrappers::Next(ulong,CSyncChangeUnitWrapper * *,ulong *)
0x1800468b8  mov     ebx, eax
0x1800468ba  test    eax, eax
0x1800468bc  jnz     short loc_18004690E
0x1800468be  mov     r15, [rsp+58h+arg_8]
0x1800468c3  mov     rcx, r15; this
0x1800468c6  call    ?GetError@CSyncChangeUnitWrapper@@QEAAJXZ; CSyncChangeUnitWrapper::GetError(void)
0x1800468cb  test    eax, eax
0x1800468cd  cmovs   edi, r13d
0x1800468d1  test    eax, eax
0x1800468d3  cmovns  ebx, eax
0x1800468d6  test    edi, edi
0x1800468d8  jnz     short loc_1800468F7
0x1800468da  lea     rdx, [rsp+58h+arg_0]; enum SYNC_TRANSFER_FILTER *
0x1800468df  mov     rcx, r15; this
0x1800468e2  call    ?GetTransferFilters@CSyncChangeUnitWrapper@@QEAAJPEAW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeUnitWrapper::GetTransferFilters(SYNC_TRANSFER_FILTER *)
0x1800468e7  mov     ebx, eax
0x1800468e9  test    eax, eax
0x1800468eb  js      short loc_1800468F7
0x1800468ed  test    byte ptr [rsp+58h+arg_0], 30h
0x1800468f2  jz      short loc_1800468F7
0x1800468f4  mov     edi, r13d
0x1800468f7  mov     rax, [r15]
0x1800468fa  mov     rcx, r15
0x1800468fd  mov     rax, [rax+10h]
0x180046901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046906  test    ebx, ebx
0x180046908  js      short loc_18004690E
0x18004690a  test    edi, edi
0x18004690c  jz      short loc_1800468AB
0x18004690e  mov     rax, [r14]
0x180046911  mov     rcx, r14
0x180046914  mov     rax, [rax+10h]
0x180046918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004691d  lea     r14, WPP_GLOBAL_Control
0x180046924  test    ebp, ebp
0x180046926  jnz     loc_1800469B8
0x18004692c  test    edi, edi
0x18004692e  jz      short loc_18004697D
0x180046930  mov     r8d, [rsi+1CCh]
0x180046937  or      eax, 0FFFFFFFFh
0x18004693a  cmp     r8d, eax
0x18004693d  jz      short loc_18004695B
0x18004693f  cmp     [rsi+28Ch], ebp
0x180046945  jle     short loc_18004694F
0x180046947  cmp     [rsi+290h], ebp
0x18004694d  jz      short loc_18004695E
0x18004694f  inc     r8d
0x180046952  mov     [rsi+1CCh], r8d
0x180046959  jmp     short loc_18004695E
0x18004695b  mov     r8d, eax
0x18004695e  test    ebx, ebx
0x180046960  js      short loc_1800469B8
0x180046962  mov     rcx, [rsi+198h]
0x180046969  test    rcx, rcx
0x18004696c  jz      short loc_1800469B8
0x18004696e  mov     rax, [rcx]
0x180046971  mov     edx, [rsi+1C8h]
0x180046977  mov     rax, [rax+48h]
0x18004697b  jmp     short loc_1800469B1
0x18004697d  mov     ecx, [rsi+1C8h]
0x180046983  or      eax, 0FFFFFFFFh
0x180046986  cmp     ecx, eax
0x180046988  jz      short loc_1800469B8
0x18004698a  lea     edx, [rcx+1]
0x18004698d  mov     [rsi+1C8h], edx
0x180046993  test    ebx, ebx
0x180046995  js      short loc_1800469B8
0x180046997  mov     rcx, [rsi+198h]
0x18004699e  test    rcx, rcx
0x1800469a1  jz      short loc_1800469B8
0x1800469a3  mov     rax, [rcx]
0x1800469a6  mov     r8d, [rsi+1CCh]
0x1800469ad  mov     rax, [rax+40h]
0x1800469b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469b6  mov     ebx, eax
0x1800469b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800469bf  cmp     rcx, r14
0x1800469c2  jz      short loc_1800469F0
0x1800469c4  test    byte ptr [rcx+1Ch], 8
0x1800469c8  jz      short loc_1800469F0
0x1800469ca  cmp     byte ptr [rcx+19h], 5
0x1800469ce  jb      short loc_1800469F0
0x1800469d0  mov     rcx, [rcx+10h]
0x1800469d4  lea     r9, aCchangeapplier_59; "CChangeApplier::UpdateSessionStatistics"
0x1800469db  mov     edx, 133h
0x1800469e0  mov     [rsp+58h+var_38], ebx
0x1800469e4  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800469eb  call    WPP_SF_sD
0x1800469f0  mov     rbp, [rsp+58h+arg_18]
0x1800469f5  mov     eax, ebx
0x1800469f7  mov     rbx, [rsp+58h+arg_10]
0x1800469fc  add     rsp, 30h
0x180046a00  pop     r15
0x180046a02  pop     r14
0x180046a04  pop     r13
0x180046a06  pop     rdi
0x180046a07  pop     rsi
0x180046a08  retn
```
