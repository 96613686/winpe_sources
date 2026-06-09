# COutboundRoutingGroupsMap::UpdateAllDevicesGroup(void)

- ea: `0x140060fac`
- end: `0x140061418`
- name: `?UpdateAllDevicesGroup@COutboundRoutingGroupsMap@@QEAAHXZ`
- size: `1132`
- prototype: `__int64 __fastcall(COutboundRoutingGroupsMap *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, installer_update`

## callers

- `0x140049f40`
- `0x14004c1a4`

## callees

- `0x140001bac`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x14000effc`
- `0x14005f694`
- `0x14005f7fc`
- `0x14005f984`
- `0x14005fdf8`
- `0x140060634`
- `0x140060750`
- `0x140060fac`
- `0x14006998c`
- `0x140083048`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400613d0`
- `ADVAPI32!RegCloseKey` at `0x1400613d0`
- `KERNEL32!GetLastError` at `0x14006102d`
- `KERNEL32!GetLastError` at `0x140061122`
- `KERNEL32!GetLastError` at `0x1400612c6`
- `KERNEL32!GetLastError` at `0x14006102d`
- `KERNEL32!GetLastError` at `0x140061122`
- `KERNEL32!GetLastError` at `0x1400612c6`
- `KERNEL32!SetLastError` at `0x1400610ce`
- `KERNEL32!SetLastError` at `0x1400611f3`
- `KERNEL32!SetLastError` at `0x1400613f5`
- `KERNEL32!SetLastError` at `0x1400610ce`
- `KERNEL32!SetLastError` at `0x1400611f3`
- `KERNEL32!SetLastError` at `0x1400613f5`
- `KERNEL32!EnterCriticalSection` at `0x14006120e`
- `KERNEL32!EnterCriticalSection` at `0x14006120e`
- `KERNEL32!LeaveCriticalSection` at `0x1400613e3`
- `KERNEL32!LeaveCriticalSection` at `0x1400613e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall COutboundRoutingGroupsMap::UpdateAllDevicesGroup(COutboundRoutingGroupsMap *this)
{
  COutboundRoutingGroupsMap *v1; // rdi
  COutboundRoutingGroup *Group; // rsi
  DWORD LastError; // eax
  __int64 v4; // rcx
  unsigned int v6; // eax
  DWORD v7; // ebx
  _QWORD *v8; // rdi
  _QWORD *v9; // rcx
  _QWORD *v10; // rbx
  DWORD v11; // eax
  _QWORD *v12; // rcx
  _QWORD *v13; // rbx
  _QWORD *v14; // rdi
  _QWORD *v15; // rcx
  _QWORD *v16; // rbx
  unsigned int v17; // eax
  DWORD v18; // ebx
  HKEY v19; // r14
  __int64 v20; // rdi
  _DWORD *v21; // r12
  unsigned int v22; // r15d
  unsigned int v23; // edx
  DWORD_PTR v24; // rax
  unsigned int v25; // ebx
  DWORD_PTR v26; // rax
  DWORD_PTR *v27; // rdi
  HKEY v28; // rax
  CMapDeviceId *v29; // rcx
  __int64 v30; // rdx
  void *Block[2]; // [rsp+30h] [rbp-10h] BYREF
  COutboundRoutingGroupsMap *v32; // [rsp+80h] [rbp+40h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp+48h] BYREF

  v32 = this;
  v1 = g_pGroupsMap;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids);
  }
  lpMem = 0;
  LODWORD(v32) = 0;
  Group = COutboundRoutingGroupsMap::FindGroup(v1, L"<All devices>");
  if ( !Group )
  {
    LastError = GetLastError();
    if ( LastError != 7002 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids, LastError);
      }
      return 0;
    }
    Block[1] = 0;
    Block[0] = (void *)std::_List_alloc<0,std::_List_base_types<unsigned long>>::_Buynode0(v4, 0, 0);
    v6 = COutboundRoutingGroupsMap::AddGroup(v1, L"<All devices>", (struct COutboundRoutingGroup *)Block);
    v7 = v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids, v6);
      }
      SetLastError(v7);
      v8 = Block[0];
      v9 = *(_QWORD **)Block[0];
      *(_QWORD *)Block[0] = Block[0];
      v8[1] = v8;
      if ( v9 != v8 )
      {
        do
        {
          v10 = (_QWORD *)*v9;
          operator delete(v9);
          v9 = v10;
        }
        while ( v10 != v8 );
      }
LABEL_19:
      operator delete(v8);
      return 0;
    }
    Group = COutboundRoutingGroupsMap::FindGroup(v1, L"<All devices>");
    if ( !Group )
    {
      v11 = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids, v11);
      }
      v8 = Block[0];
      v12 = *(_QWORD **)Block[0];
      *(_QWORD *)Block[0] = Block[0];
      v8[1] = v8;
      if ( v12 != v8 )
      {
        do
        {
          v13 = (_QWORD *)*v12;
          operator delete(v12);
          v12 = v13;
        }
        while ( v13 != v8 );
      }
      goto LABEL_19;
    }
    v14 = Block[0];
    v15 = *(_QWORD **)Block[0];
    *(_QWORD *)Block[0] = Block[0];
    v14[1] = v14;
    if ( v15 != v14 )
    {
      do
      {
        v16 = (_QWORD *)*v15;
        operator delete(v15);
        v15 = v16;
      }
      while ( v16 != v14 );
    }
    operator delete(v14);
  }
  v17 = COutboundRoutingGroup::SerializeDevices(Group, (unsigned int **)&lpMem, (unsigned int *)&v32, 1);
  v18 = v17;
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids, v17);
    }
    SetLastError(v18);
    return 0;
  }
  v19 = 0;
  EnterCriticalSection(&g_CsLine);
  v20 = 0;
  v21 = lpMem;
  v22 = (unsigned int)v32;
  if ( (_DWORD)v32 )
  {
    while ( 1 )
    {
      v23 = v21[v20];
      v24 = g_TapiLinesListHead;
      if ( g_TapiLinesListHead )
      {
        while ( (DWORD_PTR *)v24 != &g_TapiLinesListHead )
        {
          if ( *(_DWORD *)(v24 + 24) == v23 )
          {
            if ( v24 )
              goto LABEL_46;
            break;
          }
          v24 = *(_QWORD *)v24;
        }
      }
      v25 = COutboundRoutingGroup::DelDevice(Group, v23);
      if ( v25 )
        break;
LABEL_46:
      v20 = (unsigned int)(v20 + 1);
      if ( (unsigned int)v20 >= v22 )
        goto LABEL_47;
    }
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    v30 = 71;
    goto LABEL_59;
  }
LABEL_47:
  v26 = g_TapiLinesListHead;
  if ( (DWORD_PTR *)g_TapiLinesListHead != &g_TapiLinesListHead )
  {
    while ( 1 )
    {
      v27 = *(DWORD_PTR **)v26;
      v25 = COutboundRoutingGroup::AddDevice(Group, *(_DWORD *)(v26 + 24));
      if ( v25 )
        break;
      v26 = (DWORD_PTR)v27;
      if ( v27 == &g_TapiLinesListHead )
        goto LABEL_50;
    }
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    v30 = 72;
    goto LABEL_59;
  }
LABEL_50:
  v28 = (HKEY)OpenOutboundGroupKey((__int64)L"<All devices>", 1u);
  v19 = v28;
  if ( v28 )
  {
    v25 = COutboundRoutingGroup::Save(Group, v28);
    if ( v25
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        (unsigned int)WPP_b9c408ceb555301912c179a0f26e2108_Traceguids,
        (unsigned int)L"<All devices>",
        v25);
    }
    goto LABEL_69;
  }
  v25 = GetLastError();
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v30 = 73;
LABEL_59:
    WPP_SF_d(*((_QWORD *)v29 + 2), v30, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids, v25);
  }
LABEL_69:
  pMemFree(v21);
  if ( v19 )
    RegCloseKey(v19);
  LeaveCriticalSection(&g_CsLine);
  if ( v25 )
    SetLastError(v25);
  return v25 == 0;
}

```

## disassembly

```asm
0x140060fac  mov     [rsp-38h+arg_0], rcx
0x140060fb1  push    rbp
0x140060fb2  push    rbx
0x140060fb3  push    rsi
0x140060fb4  push    rdi
0x140060fb5  push    r12
0x140060fb7  push    r14
0x140060fb9  push    r15
0x140060fbb  mov     rbp, rsp
0x140060fbe  sub     rsp, 40h
0x140060fc2  mov     rdi, cs:?g_pGroupsMap@@3PEAVCOutboundRoutingGroupsMap@@EA; COutboundRoutingGroupsMap * g_pGroupsMap
0x140060fc9  lea     r15, WPP_GLOBAL_Control
0x140060fd0  lea     r12, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids
0x140060fd7  mov     r14b, 4
0x140060fda  mov     rcx, cs:WPP_GLOBAL_Control
0x140060fe1  cmp     rcx, r15
0x140060fe4  jz      short loc_140061003
0x140060fe6  test    [rcx+1Ch], r14b
0x140060fea  jz      short loc_140061003
0x140060fec  cmp     byte ptr [rcx+19h], 5
0x140060ff0  jb      short loc_140061003
0x140060ff2  mov     edx, 42h ; 'B'
0x140060ff7  mov     r8, r12
0x140060ffa  mov     rcx, [rcx+10h]
0x140060ffe  call    WPP_SF_
0x140061003  mov     [rbp+lpMem], 0
0x14006100b  mov     dword ptr [rbp+arg_0], 0
0x140061012  lea     rdx, aAllDevices; "<All devices>"
0x140061019  mov     rcx, rdi; this
0x14006101c  call    ?FindGroup@COutboundRoutingGroupsMap@@QEAAPEAVCOutboundRoutingGroup@@PEBG@Z; COutboundRoutingGroupsMap::FindGroup(ushort const *)
0x140061021  mov     rsi, rax
0x140061024  test    rax, rax
0x140061027  jnz     loc_1400611A9
0x14006102d  call    cs:__imp_GetLastError
0x140061034  nop     dword ptr [rax+rax+00h]
0x140061039  cmp     eax, 1B5Ah
0x14006103e  jz      short loc_140061071
0x140061040  mov     rcx, cs:WPP_GLOBAL_Control
0x140061047  cmp     rcx, r15
0x14006104a  jz      short loc_14006106A
0x14006104c  test    [rcx+1Ch], r14b
0x140061050  jz      short loc_14006106A
0x140061052  cmp     byte ptr [rcx+19h], 2
0x140061056  jb      short loc_14006106A
0x140061058  lea     edx, [rsi+43h]
0x14006105b  mov     r9d, eax
0x14006105e  mov     r8, r12
0x140061061  mov     rcx, [rcx+10h]
0x140061065  call    WPP_SF_d
0x14006106a  xor     eax, eax
0x14006106c  jmp     loc_140061408
0x140061071  mov     [rbp+var_8], 0
0x140061079  xor     r8d, r8d
0x14006107c  xor     edx, edx
0x14006107e  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@KV?$allocator@K@std@@@std@@@std@@QEAAPEAU?$_List_node@KPEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<ulong>>::_Buynode0(std::_List_node<ulong,void *> *,std::_List_node<ulong,void *> *)
0x140061083  mov     [rbp+Block], rax
0x140061087  lea     r8, [rbp+Block]; struct COutboundRoutingGroup *
0x14006108b  lea     rdx, aAllDevices; "<All devices>"
0x140061092  mov     rcx, rdi; this
0x140061095  call    ?AddGroup@COutboundRoutingGroupsMap@@QEAAKPEBGPEAVCOutboundRoutingGroup@@@Z; COutboundRoutingGroupsMap::AddGroup(ushort const *,COutboundRoutingGroup *)
0x14006109a  mov     ebx, eax
0x14006109c  test    eax, eax
0x14006109e  jz      short loc_14006110B
0x1400610a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400610a7  cmp     rcx, r15
0x1400610aa  jz      short loc_1400610CC
0x1400610ac  test    [rcx+1Ch], r14b
0x1400610b0  jz      short loc_1400610CC
0x1400610b2  cmp     byte ptr [rcx+19h], 2
0x1400610b6  jb      short loc_1400610CC
0x1400610b8  mov     edx, 44h ; 'D'
0x1400610bd  mov     r9d, eax
0x1400610c0  mov     r8, r12
0x1400610c3  mov     rcx, [rcx+10h]
0x1400610c7  call    WPP_SF_d
0x1400610cc  mov     ecx, ebx; dwErrCode
0x1400610ce  call    cs:__imp_SetLastError
0x1400610d5  nop     dword ptr [rax+rax+00h]
0x1400610da  nop
0x1400610db  mov     rdi, [rbp+Block]
0x1400610df  mov     rcx, [rdi]; Block
0x1400610e2  mov     [rdi], rdi
0x1400610e5  mov     [rdi+8], rdi
0x1400610e9  cmp     rcx, rdi
0x1400610ec  jz      short loc_1400610FE
0x1400610ee  mov     rbx, [rcx]
0x1400610f1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400610f6  mov     rcx, rbx
0x1400610f9  cmp     rbx, rdi
0x1400610fc  jnz     short loc_1400610EE
0x1400610fe  mov     rcx, rdi; Block
0x140061101  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140061106  jmp     loc_14006106A
0x14006110b  lea     rdx, aAllDevices; "<All devices>"
0x140061112  mov     rcx, rdi; this
0x140061115  call    ?FindGroup@COutboundRoutingGroupsMap@@QEAAPEAVCOutboundRoutingGroup@@PEBG@Z; COutboundRoutingGroupsMap::FindGroup(ushort const *)
0x14006111a  mov     rsi, rax
0x14006111d  test    rax, rax
0x140061120  jnz     short loc_14006117E
0x140061122  call    cs:__imp_GetLastError
0x140061129  nop     dword ptr [rax+rax+00h]
0x14006112e  mov     rcx, cs:WPP_GLOBAL_Control
0x140061135  cmp     rcx, r15
0x140061138  jz      short loc_140061159
0x14006113a  test    [rcx+1Ch], r14b
0x14006113e  jz      short loc_140061159
0x140061140  cmp     byte ptr [rcx+19h], 2
0x140061144  jb      short loc_140061159
0x140061146  lea     edx, [rsi+45h]
0x140061149  mov     r9d, eax
0x14006114c  mov     r8, r12
0x14006114f  mov     rcx, [rcx+10h]
0x140061153  call    WPP_SF_d
0x140061158  nop
0x140061159  mov     rdi, [rbp+Block]
0x14006115d  mov     rcx, [rdi]; Block
0x140061160  mov     [rdi], rdi
0x140061163  mov     [rdi+8], rdi
0x140061167  cmp     rcx, rdi
0x14006116a  jz      short loc_1400610FE
0x14006116c  mov     rbx, [rcx]
0x14006116f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140061174  mov     rcx, rbx
0x140061177  cmp     rbx, rdi
0x14006117a  jnz     short loc_14006116C
0x14006117c  jmp     short loc_1400610FE
0x14006117e  mov     rdi, [rbp+Block]
0x140061182  mov     rcx, [rdi]; Block
0x140061185  mov     [rdi], rdi
0x140061188  mov     [rdi+8], rdi
0x14006118c  cmp     rcx, rdi
0x14006118f  jz      short loc_1400611A1
0x140061191  mov     rbx, [rcx]
0x140061194  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140061199  mov     rcx, rbx
0x14006119c  cmp     rbx, rdi
0x14006119f  jnz     short loc_140061191
0x1400611a1  mov     rcx, rdi; Block
0x1400611a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400611a9  mov     r9d, 1; int
0x1400611af  lea     r8, [rbp+arg_0]; unsigned int *
0x1400611b3  lea     rdx, [rbp+lpMem]; unsigned int **
0x1400611b7  mov     rcx, rsi; this
0x1400611ba  call    ?SerializeDevices@COutboundRoutingGroup@@QEBAKPEAPEAKPEAKH@Z; COutboundRoutingGroup::SerializeDevices(ulong * *,ulong *,int)
0x1400611bf  mov     ebx, eax
0x1400611c1  test    eax, eax
0x1400611c3  jz      short loc_140061204
0x1400611c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400611cc  cmp     rcx, r15
0x1400611cf  jz      short loc_1400611F1
0x1400611d1  test    [rcx+1Ch], r14b
0x1400611d5  jz      short loc_1400611F1
0x1400611d7  cmp     byte ptr [rcx+19h], 2
0x1400611db  jb      short loc_1400611F1
0x1400611dd  mov     edx, 46h ; 'F'
0x1400611e2  mov     r9d, eax
0x1400611e5  mov     r8, r12
0x1400611e8  mov     rcx, [rcx+10h]
0x1400611ec  call    WPP_SF_d
0x1400611f1  mov     ecx, ebx; dwErrCode
0x1400611f3  call    cs:__imp_SetLastError
0x1400611fa  nop     dword ptr [rax+rax+00h]
0x1400611ff  jmp     loc_14006106A
0x140061204  xor     r14d, r14d
0x140061207  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14006120e  call    cs:__imp_EnterCriticalSection
0x140061215  nop     dword ptr [rax+rax+00h]
0x14006121a  xor     edi, edi
0x14006121c  lea     rcx, ?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x140061223  mov     r12, [rbp+lpMem]
0x140061227  mov     r15d, dword ptr [rbp+arg_0]
0x14006122b  test    r15d, r15d
0x14006122e  jz      short loc_140061276
0x140061230  mov     edx, [r12+rdi*4]; unsigned int
0x140061234  mov     rax, cs:?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x14006123b  test    rax, rax
0x14006123e  jz      short loc_140061256
0x140061240  jmp     short loc_14006124A
0x140061242  cmp     [rax+18h], edx
0x140061245  jz      short loc_140061251
0x140061247  mov     rax, [rax]
0x14006124a  cmp     rax, rcx
0x14006124d  jnz     short loc_140061242
0x14006124f  jmp     short loc_140061256
0x140061251  test    rax, rax
0x140061254  jnz     short loc_14006126F
0x140061256  mov     rcx, rsi; this
0x140061259  call    ?DelDevice@COutboundRoutingGroup@@QEAAKK@Z; COutboundRoutingGroup::DelDevice(ulong)
0x14006125e  mov     ebx, eax
0x140061260  test    eax, eax
0x140061262  jnz     loc_140061305
0x140061268  lea     rcx, ?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x14006126f  inc     edi
0x140061271  cmp     edi, r15d
0x140061274  jb      short loc_140061230
0x140061276  mov     rax, cs:?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x14006127d  cmp     rax, rcx
0x140061280  jz      short loc_1400612A9
0x140061282  lea     r15, ?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x140061289  mov     rdi, [rax]
0x14006128c  mov     edx, [rax+18h]; unsigned int
0x14006128f  mov     rcx, rsi; this
0x140061292  call    ?AddDevice@COutboundRoutingGroup@@QEAAKK@Z; COutboundRoutingGroup::AddDevice(ulong)
0x140061297  mov     ebx, eax
0x140061299  test    eax, eax
0x14006129b  jnz     loc_14006134A
0x1400612a1  mov     rax, rdi
0x1400612a4  cmp     rdi, r15
0x1400612a7  jnz     short loc_140061289
0x1400612a9  mov     edx, 1
0x1400612ae  lea     rcx, aAllDevices; "<All devices>"
0x1400612b5  call    OpenOutboundGroupKey
0x1400612ba  mov     r14, rax
0x1400612bd  test    rax, rax
0x1400612c0  jnz     loc_140061370
0x1400612c6  call    cs:__imp_GetLastError
0x1400612cd  nop     dword ptr [rax+rax+00h]
0x1400612d2  mov     ebx, eax
0x1400612d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400612db  lea     rax, WPP_GLOBAL_Control
0x1400612e2  cmp     rcx, rax
0x1400612e5  jz      loc_1400613C0
0x1400612eb  test    byte ptr [rcx+1Ch], 4
0x1400612ef  jz      loc_1400613C0
0x1400612f5  cmp     byte ptr [rcx+19h], 2
0x1400612f9  jb      loc_1400613C0
0x1400612ff  lea     edx, [r14+49h]
0x140061303  jmp     short loc_140061335
0x140061305  mov     rcx, cs:WPP_GLOBAL_Control
0x14006130c  lea     rax, WPP_GLOBAL_Control
0x140061313  cmp     rcx, rax
0x140061316  jz      loc_1400613C0
0x14006131c  test    byte ptr [rcx+1Ch], 4
0x140061320  jz      loc_1400613C0
0x140061326  cmp     byte ptr [rcx+19h], 2
0x14006132a  jb      loc_1400613C0
0x140061330  mov     edx, 47h ; 'G'
0x140061335  mov     r9d, ebx
0x140061338  lea     r8, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids
0x14006133f  mov     rcx, [rcx+10h]
0x140061343  call    WPP_SF_d
0x140061348  jmp     short loc_1400613C0
0x14006134a  mov     rcx, cs:WPP_GLOBAL_Control
0x140061351  lea     rax, WPP_GLOBAL_Control
0x140061358  cmp     rcx, rax
0x14006135b  jz      short loc_1400613C0
0x14006135d  test    byte ptr [rcx+1Ch], 4
0x140061361  jz      short loc_1400613C0
0x140061363  cmp     byte ptr [rcx+19h], 2
0x140061367  jb      short loc_1400613C0
0x140061369  mov     edx, 48h ; 'H'
0x14006136e  jmp     short loc_140061335
0x140061370  mov     rdx, rax; HKEY
0x140061373  mov     rcx, rsi; this
0x140061376  call    ?Save@COutboundRoutingGroup@@QEBAKPEAUHKEY__@@@Z; COutboundRoutingGroup::Save(HKEY__ *)
0x14006137b  mov     ebx, eax
0x14006137d  test    eax, eax
0x14006137f  jz      short loc_1400613C0
0x140061381  mov     rcx, cs:WPP_GLOBAL_Control
0x140061388  lea     rax, WPP_GLOBAL_Control
0x14006138f  cmp     rcx, rax
0x140061392  jz      short loc_1400613C0
0x140061394  test    byte ptr [rcx+1Ch], 4
0x140061398  jz      short loc_1400613C0
0x14006139a  cmp     byte ptr [rcx+19h], 2
0x14006139e  jb      short loc_1400613C0
0x1400613a0  mov     edx, 4Ah ; 'J'
0x1400613a5  mov     [rsp+40h+var_20], ebx
0x1400613a9  lea     r9, aAllDevices; "<All devices>"
0x1400613b0  lea     r8, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids
0x1400613b7  mov     rcx, [rcx+10h]
0x1400613bb  call    WPP_SF_Sd
0x1400613c0  mov     rcx, r12; lpMem
0x1400613c3  call    pMemFree
0x1400613c8  test    r14, r14
0x1400613cb  jz      short loc_1400613DC
0x1400613cd  mov     rcx, r14; hKey
0x1400613d0  call    cs:__imp_RegCloseKey
0x1400613d7  nop     dword ptr [rax+rax+00h]
0x1400613dc  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400613e3  call    cs:__imp_LeaveCriticalSection
0x1400613ea  nop     dword ptr [rax+rax+00h]
0x1400613ef  test    ebx, ebx
0x1400613f1  jz      short loc_140061401
0x1400613f3  mov     ecx, ebx; dwErrCode
0x1400613f5  call    cs:__imp_SetLastError
0x1400613fc  nop     dword ptr [rax+rax+00h]
0x140061401  xor     eax, eax
0x140061403  test    ebx, ebx
0x140061405  setz    al
0x140061408  add     rsp, 40h
0x14006140c  pop     r15
0x14006140e  pop     r14
0x140061410  pop     r12
0x140061412  pop     rdi
0x140061413  pop     rsi
0x140061414  pop     rbx
0x140061415  pop     rbp
0x140061416  retn
```
