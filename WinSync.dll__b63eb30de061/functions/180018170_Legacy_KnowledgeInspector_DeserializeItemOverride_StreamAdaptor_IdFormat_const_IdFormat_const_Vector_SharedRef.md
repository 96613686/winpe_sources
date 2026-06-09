# Legacy::KnowledgeInspector::DeserializeItemOverride(StreamAdaptor &,IdFormat const &,IdFormat const &,Vector<SharedRefPtr<ClockVector>,1> const &,ClockVectorManager &,SharedRefPtr<RangeSet> &,RefCountedHashTable<Tuple<SyncId,SyncId>,ulong> &)

- ea: `0x180018170`
- end: `0x180018ab3`
- name: `?DeserializeItemOverride@KnowledgeInspector@Legacy@@AEAAJAEAVStreamAdaptor@@AEBUIdFormat@@1AEBV?$Vector@V?$SharedRefPtr@VClockVector@@@@$00@@AEAVClockVectorManager@@AEAV?$SharedRefPtr@VRangeSet@@@@AEAV?$RefCountedHashTable@U?$Tuple@VSyncId@@V1@@@K@@@Z`
- size: `2371`
- prototype: `__int64 __fastcall(void *, __int64, __int64, struct IdFormat *, __int64, __int64, RangeSet **, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x180016a40`

## callees

- `0x180007584`
- `0x180009840`
- `0x18000f810`
- `0x180011f60`
- `0x180015140`
- `0x180017d50`
- `0x180018170`
- `0x180018dd0`
- `0x18001a038`
- `0x18001a1f0`
- `0x18001ae20`
- `0x18001e4a4`
- `0x18008eaa0`
- `0x180093232`
- `0x180094010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001821b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018457`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001821b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018457`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018236`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018304`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018472`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018501`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018236`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018304`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018472`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018501`

## string_xrefs

- `0x1800188f4`: `Legacy::KnowledgeInspector::DeserializeItemOverride`
- `0x180018a92`: `Legacy::KnowledgeInspector::DeserializeItemOverride`

## pseudocode

```c
__int64 __fastcall Legacy::KnowledgeInspector::DeserializeItemOverride(
        void *a1,
        __int64 a2,
        __int64 a3,
        struct IdFormat *a4,
        __int64 a5,
        __int64 a6,
        RangeSet **a7,
        __int64 a8)
{
  unsigned __int16 v10; // r13
  _DWORD *v11; // rsi
  unsigned int *v12; // r14
  unsigned __int16 *v13; // r12
  unsigned int v14; // edi
  __int64 v15; // rax
  unsigned int v16; // edx
  unsigned __int16 *v17; // r14
  unsigned __int16 *v18; // r13
  int v19; // eax
  unsigned int v20; // r14d
  __int64 v21; // rdx
  int v22; // r8d
  __int64 v23; // rdx
  __int64 v24; // rbx
  __int64 *v25; // rdx
  unsigned int v26; // r14d
  unsigned __int16 v27; // ax
  _WORD *v28; // rsi
  unsigned __int16 *v29; // rdx
  __int16 v30; // r8
  _BYTE *v31; // rcx
  bool v32; // zf
  void *v33; // r14
  __int64 v34; // rdx
  __int64 v35; // r14
  unsigned int v36; // ebx
  unsigned int i; // esi
  int v39; // edx
  unsigned __int16 v40; // r8
  unsigned __int16 v41; // ax
  unsigned __int16 v42; // ax
  char *v43; // rcx
  unsigned __int16 *v44; // rax
  unsigned __int16 *v45; // rax
  unsigned __int16 *v46; // rax
  unsigned __int16 *v47; // rax
  unsigned __int16 *v48; // rax
  __int64 v49; // rdx
  int v50; // r8d
  unsigned int v51; // edi
  __int64 v52; // rdx
  __int64 v53; // rdx
  unsigned int v54; // eax
  unsigned int v55; // [rsp+38h] [rbp-59h] BYREF
  LPVOID v56; // [rsp+40h] [rbp-51h] BYREF
  _BYTE v57[4]; // [rsp+48h] [rbp-49h] BYREF
  unsigned int v58; // [rsp+4Ch] [rbp-45h]
  unsigned __int16 *v59; // [rsp+50h] [rbp-41h]
  _BYTE v60[4]; // [rsp+58h] [rbp-39h] BYREF
  unsigned int v61; // [rsp+5Ch] [rbp-35h]
  _WORD *v62; // [rsp+60h] [rbp-31h]
  _BYTE v63[4]; // [rsp+68h] [rbp-29h] BYREF
  int v64; // [rsp+6Ch] [rbp-25h]
  __int64 v65; // [rsp+70h] [rbp-21h]
  unsigned int v66; // [rsp+78h] [rbp-19h]
  __int64 v67; // [rsp+80h] [rbp-11h] BYREF
  int v68; // [rsp+88h] [rbp-9h]
  RangeSet *v69; // [rsp+90h] [rbp-1h]
  LPVOID lpMem; // [rsp+D8h] [rbp+47h] BYREF
  int v71; // [rsp+E8h] [rbp+57h] BYREF
  struct IdFormat *v72; // [rsp+F0h] [rbp+5Fh]

  v72 = a4;
  lpMem = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      WPP_48b71e9a06de38317ed143d1f750f029_Traceguids,
      "Legacy::KnowledgeInspector::DeserializeItemOverride");
  }
  v10 = *(_WORD *)(a3 + 4);
  v11 = (_DWORD *)(a2 + 16);
  v12 = (unsigned int *)(a2 + 20);
  v58 = 0;
  v59 = 0;
  if ( *(_DWORD *)a3 )
  {
    v52 = (unsigned int)*v11;
    if ( v52 + 2 > (unsigned __int64)*v12 || (int)v52 + 2 < (unsigned int)v52 )
      goto LABEL_18;
    v10 = _byteswap_ushort(*(_WORD *)(*(_QWORD *)(a2 + 8) + v52));
    *v11 = v52 + 2;
    if ( *(_DWORD *)a3 )
    {
      if ( v10 > 2u && v10 <= *(_WORD *)(a3 + 4) && (unsigned __int64)v10 - 2 <= *v12 - *(_DWORD *)(a2 + 16) )
      {
        v11 = (_DWORD *)(a2 + 16);
        goto LABEL_6;
      }
LABEL_18:
      v14 = -2147217396;
      ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(&lpMem);
      v13 = (unsigned __int16 *)lpMem;
      goto LABEL_19;
    }
  }
  if ( v10 != *(_WORD *)(a3 + 4) || v10 > *v12 - *v11 )
    goto LABEL_18;
LABEL_6:
  ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(&lpMem);
  v13 = (unsigned __int16 *)HeapAlloc(hHeap, 0, v10 + 7LL);
  if ( lpMem )
    HeapFree(hHeap, 0, lpMem);
  if ( !v13 )
  {
    v14 = -2147024882;
LABEL_19:
    SyncId::~SyncId((SyncId *)v57);
    v20 = 0;
    v18 = 0;
    v58 = 0;
    v59 = 0;
    v71 = 0;
    goto LABEL_20;
  }
  v15 = (unsigned int)*v11;
  v16 = *v12;
  if ( !*(_DWORD *)a3 )
  {
    if ( (unsigned int)v15 + v10 >= (unsigned int)v15 && (unsigned int)v15 + v10 <= v16 )
    {
      v17 = v13 + 2;
      memcpy_0(v13 + 2, (const void *)(*(_QWORD *)(a2 + 8) + (unsigned int)v15), v10);
      *v11 += v10;
      v14 = 0;
      goto LABEL_14;
    }
    goto LABEL_82;
  }
  v51 = v10 - 2;
  if ( v51 + (unsigned int)v15 < (unsigned int)v15 || v51 + (unsigned int)v15 > v16 )
  {
LABEL_82:
    v14 = -2147217396;
    v17 = v13 + 2;
    goto LABEL_14;
  }
  memcpy_0(v13 + 3, (const void *)(*(_QWORD *)(a2 + 8) + v15), v51);
  *v11 += v51;
  v17 = v13 + 2;
  v14 = 0;
LABEL_14:
  if ( v14 )
    goto LABEL_19;
  *(_DWORD *)v13 = 1;
  if ( *(_DWORD *)a3 )
    *v17 = v10;
  v18 = v13;
  v19 = *(_DWORD *)a3 & 1;
  v59 = v13;
  v13 = 0;
  v58 = v19 << 16;
  LOWORD(v58) = *(_WORD *)(a3 + 4);
  v20 = v58;
  v71 = (unsigned __int16)v58;
LABEL_20:
  if ( v13 )
    HeapFree(hHeap, 0, v13);
  v55 = 0;
  if ( v14 )
  {
    v67 = 0;
    goto LABEL_70;
  }
  v21 = (unsigned int)*v11;
  if ( v21 + 4 > (unsigned __int64)*(unsigned int *)(a2 + 20) || (v22 = v21 + 4, (int)v21 + 4 < (unsigned int)v21) )
  {
    v14 = -2147217396;
    v23 = 0;
  }
  else
  {
    v23 = *(unsigned __int8 *)(v21 + *(_QWORD *)(a2 + 8) + 3)
        | ((*(unsigned __int8 *)(v21 + *(_QWORD *)(a2 + 8) + 2)
          | (((*(unsigned __int8 *)(v21 + *(_QWORD *)(a2 + 8)) << 8)
            | (unsigned int)*(unsigned __int8 *)(v21 + *(_QWORD *)(a2 + 8) + 1)) << 8)) << 8);
    *(_DWORD *)(a2 + 16) = v22;
    v55 = v23;
  }
  if ( (_DWORD)v23 == -1 )
    goto LABEL_65;
  if ( !v14 && (unsigned int)v23 >= *(_DWORD *)a5 )
  {
LABEL_133:
    v14 = -2147217396;
    goto LABEL_70;
  }
  v24 = 0;
  v67 = 0;
  if ( !v14 )
  {
    v25 = (__int64 *)(*(_QWORD *)(a5 + 16) + 8 * v23);
    if ( &v67 != v25 )
    {
      v24 = *v25;
      v67 = v24;
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
    }
    v14 = ClockVectorManager::FindByKeyOrAdd(a6, &v67, &v55);
    if ( v14 )
      goto LABEL_63;
    v69 = *a7;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        WPP_ff88f7f000e13ecf98ed337d60498caa_Traceguids,
        "RangeSet::InjectRangeOfOne");
    }
    v26 = v20 & 0xFFFDFFFF;
    v62 = 0;
    v66 = v26;
    v68 = v26 & 0x10000;
    v61 = v26;
    if ( (v26 & 0x10000) != 0 )
    {
      v39 = HIWORD(v58) & 1;
      if ( v39 )
      {
        v46 = v18;
        if ( (v58 & 0x20000) == 0 )
          v46 = v18 + 2;
        v41 = *v46;
        v40 = v71;
      }
      else
      {
        v40 = v71;
        v41 = v71;
      }
      if ( v41 >= (unsigned __int16)v26 )
      {
        if ( v39 )
        {
          v48 = v18;
          if ( (v58 & 0x20000) == 0 )
            v48 = v18 + 2;
          v42 = *v48;
        }
        else
        {
          v42 = v40;
        }
        LOWORD(lpMem) = v42;
        if ( v42 <= 2u )
        {
LABEL_100:
          v14 = -2147024809;
          ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(&v56);
          v28 = v56;
          goto LABEL_86;
        }
        while ( 1 )
        {
          v43 = (char *)v18;
          if ( (v58 & 0x20000) == 0 )
            v43 = (char *)(v18 + 2);
          if ( v43[v42 - 1] != -1 )
            break;
          v42 = (_WORD)lpMem - 1;
          LOWORD(lpMem) = v42;
          if ( v42 <= 2u )
            goto LABEL_100;
        }
LABEL_40:
        ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(&v56);
        v28 = HeapAlloc(hHeap, 0, (unsigned __int16)lpMem + 7LL);
        if ( v56 )
          HeapFree(hHeap, 0, v56);
        v14 = 0;
        if ( v28 )
        {
          v29 = v18;
          LODWORD(v56) = (v58 >> 17) & 1;
          if ( !(_DWORD)v56 )
            v29 = v18 + 2;
          memcpy_0(v28 + 2, v29, (unsigned __int16)lpMem);
          if ( (v26 & 0x10000) != 0 )
          {
            if ( (v58 & 0x10000) != 0 )
            {
              v45 = v18;
              if ( !(_DWORD)v56 )
                v45 = v18 + 2;
              v71 = *v45;
            }
            v30 = (__int16)lpMem;
            if ( (unsigned __int16)v71 >= (unsigned __int16)v26 )
              ++*((_BYTE *)v28 + (unsigned __int16)lpMem + 3);
            else
              *((_BYTE *)v28 + (unsigned __int16)lpMem + 3) = 0;
          }
          else
          {
            v30 = (__int16)lpMem;
            v31 = (char *)v28 + (unsigned __int16)lpMem + 3;
            if ( v31 >= (_BYTE *)v28 + 4 )
            {
              while ( 1 )
              {
                v32 = (*v31)++ == 0xFF;
                if ( !v32 )
                  break;
                if ( --v31 < (_BYTE *)v28 + 4 )
                {
                  v14 = -2147024809;
                  goto LABEL_86;
                }
              }
            }
          }
          v32 = v68 == 0;
          *(_DWORD *)v28 = 1;
          if ( !v32 )
            v28[2] = v30;
          v33 = v28;
          v62 = v28;
          v28 = 0;
          goto LABEL_52;
        }
        v14 = -2147024882;
LABEL_86:
        SyncId::~SyncId((SyncId *)v60);
        v33 = 0;
        v66 = 0;
        v62 = 0;
        v61 = 0;
LABEL_52:
        if ( v28 )
          HeapFree(hHeap, 0, v28);
        if ( !v14 )
          v14 = RangeSet::InjectRange(v69, (const struct SyncId *)v57, (const struct SyncId *)v60, v55);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            (unsigned int)WPP_ff88f7f000e13ecf98ed337d60498caa_Traceguids,
            (unsigned int)"RangeSet::InjectRangeOfOne",
            v14);
        }
        if ( (v66 & 0x20000) == 0 && v33 && _InterlockedExchangeAdd((volatile signed __int32 *)v33, 0xFFFFFFFF) == 1 )
          SeFree(v33);
        if ( (int)(v14 + 0x80000000) >= 0 && v14 != -2147024882 )
          v14 = -2147217396;
LABEL_63:
        if ( v24 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
LABEL_65:
        if ( !v14 )
        {
          v34 = *(unsigned int *)(a2 + 16);
          if ( v34 + 4 <= (unsigned __int64)*(unsigned int *)(a2 + 20) && (int)v34 + 4 >= (unsigned int)v34 )
          {
            v35 = a5;
            v36 = *(unsigned __int8 *)(v34 + *(_QWORD *)(a2 + 8) + 3)
                | ((*(unsigned __int8 *)(v34 + *(_QWORD *)(a2 + 8) + 2)
                  | (((*(unsigned __int8 *)(v34 + *(_QWORD *)(a2 + 8)) << 8)
                    | *(unsigned __int8 *)(v34 + *(_QWORD *)(a2 + 8) + 1)) << 8)) << 8);
            *(_DWORD *)(a2 + 16) = v34 + 4;
            for ( i = 0; ; ++i )
            {
              if ( i >= v36 )
                goto LABEL_70;
              v61 = 0;
              v62 = 0;
              v64 = 0;
              v65 = 0;
              SyncId::operator=(v60, v57);
              v14 = SyncId::InitializeByDeserializing((SyncId *)v63, v72, (struct StreamAdaptor *)a2);
              if ( v14 )
                goto LABEL_119;
              v49 = *(unsigned int *)(a2 + 16);
              if ( v49 + 4 > (unsigned __int64)*(unsigned int *)(a2 + 20) )
                break;
              v50 = v49 + 4;
              if ( (int)v49 + 4 < (unsigned int)v49 )
                break;
              v53 = *(unsigned __int8 *)(v49 + *(_QWORD *)(a2 + 8) + 3)
                  | ((*(unsigned __int8 *)(v49 + *(_QWORD *)(a2 + 8) + 2)
                    | (((*(unsigned __int8 *)(v49 + *(_QWORD *)(a2 + 8)) << 8)
                      | (unsigned int)*(unsigned __int8 *)(v49 + *(_QWORD *)(a2 + 8) + 1)) << 8)) << 8);
              *(_DWORD *)(a2 + 16) = v50;
              LODWORD(lpMem) = v53;
              if ( (unsigned int)v53 >= *(_DWORD *)v35 )
                break;
              SharedRefPtr<IForgottenKnowledge>::SharedRefPtr<IForgottenKnowledge>(
                &v71,
                *(_QWORD *)(v35 + 16) + 8 * v53);
              v14 = ClockVectorManager::FindByKeyOrAdd(a6, &v71, &lpMem);
              if ( v14 )
                goto LABEL_146;
              v54 = HashTable<Tuple<SyncId,SyncId>,unsigned long,SimpleHashTableContext>::AddItem(a8, v60, &lpMem);
              v14 = v54;
              if ( v54 == -2147024809 )
              {
                v14 = -2147217396;
LABEL_146:
                SharedRefPtr<ClockVector>::~SharedRefPtr<ClockVector>(&v71);
LABEL_119:
                SyncId::~SyncId((SyncId *)v63);
                SyncId::~SyncId((SyncId *)v60);
                goto LABEL_70;
              }
              if ( v54 )
                goto LABEL_146;
              SharedRefPtr<ClockVector>::~SharedRefPtr<ClockVector>(&v71);
              SyncId::~SyncId((SyncId *)v63);
              SyncId::~SyncId((SyncId *)v60);
            }
            v14 = -2147217396;
            goto LABEL_119;
          }
          goto LABEL_133;
        }
        goto LABEL_70;
      }
      if ( v39 )
      {
        v47 = v18;
        if ( (v58 & 0x20000) == 0 )
          v47 = v18 + 2;
        v27 = *v47 + 1;
      }
      else
      {
        v27 = v40 + 1;
      }
    }
    else if ( (v58 & 0x10000) != 0 )
    {
      v44 = v18;
      if ( (v58 & 0x20000) == 0 )
        v44 = v18 + 2;
      v27 = *v44;
    }
    else
    {
      v27 = v71;
    }
    LOWORD(lpMem) = v27;
    goto LABEL_40;
  }
LABEL_70:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      (unsigned int)WPP_48b71e9a06de38317ed143d1f750f029_Traceguids,
      (unsigned int)"Legacy::KnowledgeInspector::DeserializeItemOverride",
      v14);
  }
  if ( (v58 & 0x20000) == 0 && v18 && _InterlockedExchangeAdd((volatile signed __int32 *)v18, 0xFFFFFFFF) == 1 )
    SeFree(v18);
  return v14;
}

```

## disassembly

```asm
0x180018170  mov     rax, rsp
0x180018173  mov     [rax+20h], r9
0x180018177  mov     [rax+8], rcx
0x18001817b  push    rbp
0x18001817c  push    rdi
0x18001817d  push    r12
0x18001817f  push    r13
0x180018181  lea     rbp, [rax-3Fh]
0x180018185  sub     rsp, 0A8h
0x18001818c  mov     [rax+10h], rbx
0x180018190  mov     rbx, r8
0x180018193  mov     [rax-38h], r15
0x180018197  mov     r15, rdx
0x18001819a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181a1  lea     rax, WPP_GLOBAL_Control
0x1800181a8  cmp     rcx, rax
0x1800181ab  jz      short loc_1800181B7
0x1800181ad  test    byte ptr [rcx+1Ch], 40h
0x1800181b1  jnz     loc_1800188E6
0x1800181b7  movzx   r13d, word ptr [rbx+4]
0x1800181bc  xor     edi, edi
0x1800181be  mov     [rsp+0A0h], rsi
0x1800181c6  lea     rsi, [r15+10h]
0x1800181ca  mov     [rsp+0C0h+var_28], r14
0x1800181d2  lea     r14, [r15+14h]
0x1800181d6  mov     [rbp+37h+var_7C], edi
0x1800181d9  mov     [rbp+37h+var_78], rdi
0x1800181dd  cmp     [rbx], edi
0x1800181df  jnz     loc_180018871
0x1800181e5  cmp     r13w, [rbx+4]
0x1800181ea  jnz     loc_1800182C6
0x1800181f0  mov     ecx, [r14]
0x1800181f3  sub     ecx, [rsi]
0x1800181f5  movzx   eax, r13w
0x1800181f9  cmp     eax, ecx
0x1800181fb  ja      loc_1800182C6
0x180018201  lea     rcx, [rbp+37h+lpMem]
0x180018205  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18001820a  mov     rcx, cs:hHeap; hHeap
0x180018211  xor     edx, edx; dwFlags
0x180018213  movzx   r8d, r13w
0x180018217  add     r8, 7; dwBytes
0x18001821b  call    cs:__imp_HeapAlloc
0x180018221  mov     r8, [rbp+37h+lpMem]; lpMem
0x180018225  mov     r12, rax
0x180018228  test    r8, r8
0x18001822b  jz      short loc_18001823C
0x18001822d  mov     rcx, cs:hHeap; hHeap
0x180018234  xor     edx, edx; dwFlags
0x180018236  call    cs:__imp_HeapFree
0x18001823c  test    r12, r12
0x18001823f  mov     eax, 8007000Eh
0x180018244  cmovz   edi, eax
0x180018247  jz      loc_1800182D8
0x18001824d  cmp     dword ptr [rbx], 0
0x180018250  mov     eax, [rsi]
0x180018252  mov     edx, [r14]
0x180018255  movzx   edi, r13w
0x180018259  jnz     loc_180018839
0x18001825f  lea     ecx, [rax+rdi]
0x180018262  cmp     ecx, eax
0x180018264  jb      loc_180018684
0x18001826a  cmp     ecx, edx
0x18001826c  ja      loc_180018684
0x180018272  mov     edx, eax
0x180018274  lea     r14, [r12+4]
0x180018279  add     rdx, [r15+8]; Src
0x18001827d  mov     rcx, r14; void *
0x180018280  mov     r8d, edi; Size
0x180018283  call    memcpy_0
0x180018288  add     [rsi], edi
0x18001828a  xor     edi, edi
0x18001828c  test    edi, edi
0x18001828e  jnz     short loc_1800182D8
0x180018290  mov     dword ptr [r12], 1
0x180018298  cmp     [rbx], edi
0x18001829a  jnz     loc_180018911
0x1800182a0  mov     eax, [rbx]
0x1800182a2  mov     r13, r12
0x1800182a5  and     eax, 1
0x1800182a8  mov     [rbp+37h+var_78], r12
0x1800182ac  xor     r12d, r12d
0x1800182af  shl     eax, 10h
0x1800182b2  mov     [rbp+37h+var_7C], eax
0x1800182b5  movzx   eax, word ptr [rbx+4]
0x1800182b9  mov     word ptr [rbp+37h+var_7C], ax
0x1800182bd  mov     r14d, [rbp+37h+var_7C]
0x1800182c1  mov     [rbp+37h+arg_10], eax
0x1800182c4  jmp     short loc_1800182F3
0x1800182c6  lea     rcx, [rbp+37h+lpMem]
0x1800182ca  mov     edi, 8004100Ch
0x1800182cf  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x1800182d4  mov     r12, [rbp+37h+lpMem]
0x1800182d8  lea     rcx, [rbp+37h+var_80]; this
0x1800182dc  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x1800182e1  xor     r14d, r14d
0x1800182e4  xor     r13d, r13d
0x1800182e7  mov     [rbp+37h+var_7C], r14d
0x1800182eb  mov     [rbp+37h+var_78], r13
0x1800182ef  mov     [rbp+37h+arg_10], r14d
0x1800182f3  test    r12, r12
0x1800182f6  jz      short loc_18001830A
0x1800182f8  mov     rcx, cs:hHeap; hHeap
0x1800182ff  mov     r8, r12; lpMem
0x180018302  xor     edx, edx; dwFlags
0x180018304  call    cs:__imp_HeapFree
0x18001830a  mov     [rbp+37h+var_90], 0
0x180018311  mov     r12d, 0FFFFFFFFh
0x180018317  test    edi, edi
0x180018319  jnz     loc_1800186E5
0x18001831f  mov     edx, [rsi]
0x180018321  mov     ecx, [r15+14h]
0x180018325  lea     rax, [rdx+4]
0x180018329  cmp     rax, rcx
0x18001832c  ja      loc_18001891A
0x180018332  lea     r8d, [rdx+4]
0x180018336  cmp     r8d, edx
0x180018339  jb      loc_18001891A
0x18001833f  mov     rcx, [r15+8]
0x180018343  add     rcx, rdx
0x180018346  movzx   eax, byte ptr [rcx]
0x180018349  movzx   edx, byte ptr [rcx+1]
0x18001834d  shl     eax, 8
0x180018350  or      edx, eax
0x180018352  movzx   eax, byte ptr [rcx+2]
0x180018356  shl     edx, 8
0x180018359  or      edx, eax
0x18001835b  movzx   eax, byte ptr [rcx+3]
0x18001835f  shl     edx, 8
0x180018362  or      edx, eax
0x180018364  mov     [r15+10h], r8d
0x180018368  mov     [rbp+37h+var_90], edx
0x18001836b  cmp     edx, 0FFFFFFFFh
0x18001836e  jz      loc_180018582
0x180018374  mov     rax, [rbp+37h+arg_20]
0x180018378  test    edi, edi
0x18001837a  jnz     short loc_180018384
0x18001837c  cmp     edx, [rax]
0x18001837e  jnb     loc_180018926
0x180018384  xor     ebx, ebx
0x180018386  mov     [rbp+37h+var_48], rbx
0x18001838a  test    edi, edi
0x18001838c  jnz     loc_1800185DF
0x180018392  mov     rax, [rax+10h]
0x180018396  lea     rdx, [rax+rdx*8]
0x18001839a  lea     rax, [rbp+37h+var_48]
0x18001839e  cmp     rax, rdx
0x1800183a1  jz      short loc_1800183BE
0x1800183a3  mov     rbx, [rdx]
0x1800183a6  mov     [rbp+37h+var_48], rbx
0x1800183aa  test    rbx, rbx
0x1800183ad  jz      short loc_1800183BE
0x1800183af  mov     rax, [rbx]
0x1800183b2  mov     rcx, rbx
0x1800183b5  mov     rax, [rax+8]
0x1800183b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183be  mov     rcx, [rbp+37h+arg_28]
0x1800183c2  lea     r8, [rbp+37h+var_90]
0x1800183c6  lea     rdx, [rbp+37h+var_48]
0x1800183ca  call    ?FindByKeyOrAdd@ClockVectorManager@@QEAAJAEBV?$SharedRefPtr@VClockVector@@@@AEAK@Z; ClockVectorManager::FindByKeyOrAdd(SharedRefPtr<ClockVector> const &,ulong &)
0x1800183cf  mov     edi, eax
0x1800183d1  test    eax, eax
0x1800183d3  jnz     loc_18001856E
0x1800183d9  mov     rax, [rbp+37h+arg_30]
0x1800183dd  mov     rax, [rax]
0x1800183e0  mov     [rbp+37h+var_38], rax
0x1800183e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183eb  lea     rax, WPP_GLOBAL_Control
0x1800183f2  cmp     rcx, rax
0x1800183f5  jz      short loc_180018401
0x1800183f7  test    byte ptr [rcx+1Ch], 40h
0x1800183fb  jnz     loc_180018930
0x180018401  mov     edi, [rbp+37h+var_7C]
0x180018404  btr     r14d, 11h
0x180018409  mov     eax, r14d
0x18001840c  mov     [rbp+37h+var_68], 0
0x180018414  and     eax, 10000h
0x180018419  mov     [rbp+37h+var_50], r14d
0x18001841d  mov     [rbp+37h+var_40], eax
0x180018420  mov     [rbp+37h+var_6C], r14d
0x180018424  jnz     loc_1800186FC
0x18001842a  bt      edi, 10h
0x18001842e  jb      loc_180018786
0x180018434  movzx   eax, word ptr [rbp+37h+arg_10]
0x180018438  mov     word ptr [rbp+37h+lpMem], ax
0x18001843c  lea     rcx, [rbp+37h+var_88]
0x180018440  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180018445  movzx   r8d, word ptr [rbp+37h+lpMem]
0x18001844a  xor     edx, edx; dwFlags
0x18001844c  mov     rcx, cs:hHeap; hHeap
0x180018453  add     r8, 7; dwBytes
0x180018457  call    cs:__imp_HeapAlloc
0x18001845d  mov     r8, [rbp+37h+var_88]; lpMem
0x180018461  mov     rsi, rax
0x180018464  test    r8, r8
0x180018467  jz      short loc_180018478
0x180018469  mov     rcx, cs:hHeap; hHeap
0x180018470  xor     edx, edx; dwFlags
0x180018472  call    cs:__imp_HeapFree
0x180018478  xor     edi, edi
0x18001847a  mov     eax, 8007000Eh
0x18001847f  test    rsi, rsi
0x180018482  cmovz   edi, eax
0x180018485  jz      loc_1800186AE
0x18001848b  mov     eax, [rbp+37h+var_7C]
0x18001848e  mov     rdx, r13
0x180018491  shr     eax, 11h
0x180018494  and     eax, 1
0x180018497  mov     dword ptr [rbp+37h+var_88], eax
0x18001849a  jnz     short loc_1800184A0
0x18001849c  lea     rdx, [r13+4]; Src
0x1800184a0  movzx   r8d, word ptr [rbp+37h+lpMem]; Size
0x1800184a5  lea     rcx, [rsi+4]; void *
0x1800184a9  call    memcpy_0
0x1800184ae  bt      r14d, 10h
0x1800184b3  jb      loc_180018660
0x1800184b9  movzx   r8d, word ptr [rbp+37h+lpMem]
0x1800184be  lea     rdx, [rsi+4]
0x1800184c2  lea     rcx, [r8+3]
0x1800184c6  add     rcx, rsi
0x1800184c9  cmp     rcx, rdx
0x1800184cc  jb      short loc_1800184D7
0x1800184ce  add     byte ptr [rcx], 1
0x1800184d1  jz      loc_18001869D
0x1800184d7  cmp     [rbp+37h+var_40], 0
0x1800184db  mov     dword ptr [rsi], 1
0x1800184e1  jnz     loc_1800186F2
0x1800184e7  mov     r14, rsi
0x1800184ea  mov     [rbp+37h+var_68], rsi
0x1800184ee  xor     esi, esi
0x1800184f0  test    rsi, rsi
0x1800184f3  jz      short loc_180018507
0x1800184f5  mov     rcx, cs:hHeap; hHeap
0x1800184fc  mov     r8, rsi; lpMem
0x1800184ff  xor     edx, edx; dwFlags
0x180018501  call    cs:__imp_HeapFree
0x180018507  test    edi, edi
0x180018509  jnz     short loc_180018522
0x18001850b  mov     r9d, [rbp+37h+var_90]; unsigned int
0x18001850f  lea     r8, [rbp+37h+var_70]; struct SyncId *
0x180018513  mov     rcx, [rbp+37h+var_38]; this
0x180018517  lea     rdx, [rbp+37h+var_80]; struct SyncId *
0x18001851b  call    ?InjectRange@RangeSet@@QEAAJAEBVSyncId@@0K@Z; RangeSet::InjectRange(SyncId const &,SyncId const &,ulong)
0x180018520  mov     edi, eax
0x180018522  mov     rcx, cs:WPP_GLOBAL_Control
0x180018529  lea     rax, WPP_GLOBAL_Control
0x180018530  cmp     rcx, rax
0x180018533  jz      short loc_18001853F
0x180018535  test    byte ptr [rcx+1Ch], 40h
0x180018539  jnz     loc_18001895B
0x18001853f  test    [rbp+37h+var_50], 20000h
0x180018546  jnz     short loc_18001855E
0x180018548  test    r14, r14
0x18001854b  jz      short loc_18001855E
0x18001854d  mov     eax, r12d
0x180018550  lock xadd [r14], eax
0x180018555  cmp     eax, 1
0x180018558  jz      loc_1800186D8
0x18001855e  mov     ecx, 80000000h
0x180018563  lea     eax, [rdi+rcx]
0x180018566  test    ecx, eax
0x180018568  jz      loc_18001864A
0x18001856e  test    rbx, rbx
0x180018571  jz      short loc_180018582
0x180018573  mov     rax, [rbx]
0x180018576  mov     rcx, rbx
0x180018579  mov     rax, [rax+10h]
0x18001857d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018582  test    edi, edi
0x180018584  jnz     short loc_1800185DF
0x180018586  mov     edx, [r15+10h]
0x18001858a  mov     ecx, [r15+14h]
0x18001858e  lea     rax, [rdx+4]
0x180018592  cmp     rax, rcx
0x180018595  ja      loc_180018926
0x18001859b  lea     r8d, [rdx+4]
0x18001859f  cmp     r8d, edx
0x1800185a2  jb      loc_180018926
0x1800185a8  mov     rcx, [r15+8]
0x1800185ac  mov     r14, [rbp+37h+arg_20]
0x1800185b0  add     rcx, rdx
0x1800185b3  movzx   eax, byte ptr [rcx]
0x1800185b6  movzx   ebx, byte ptr [rcx+1]
0x1800185ba  shl     eax, 8
0x1800185bd  or      ebx, eax
0x1800185bf  movzx   eax, byte ptr [rcx+2]
0x1800185c3  shl     ebx, 8
0x1800185c6  or      ebx, eax
0x1800185c8  movzx   eax, byte ptr [rcx+3]
0x1800185cc  shl     ebx, 8
0x1800185cf  or      ebx, eax
0x1800185d1  mov     [r15+10h], r8d
0x1800185d5  xor     esi, esi
0x1800185d7  cmp     esi, ebx
0x1800185d9  jb      loc_18001898A
0x1800185df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185e6  lea     rax, WPP_GLOBAL_Control
0x1800185ed  mov     r15, [rsp+0C0h+var_30]
0x1800185f5  mov     r14, [rsp+0C0h+var_28]
0x1800185fd  mov     rsi, [rsp+0A0h]
  ... truncated ...
```
