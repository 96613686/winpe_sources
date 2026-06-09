# CAdapterPropertyCache::SetPhyProperties(ulong,tagWFC_PHY_INFO *)

- ea: `0x1400680e8`
- end: `0x1400683a6`
- name: `?SetPhyProperties@CAdapterPropertyCache@@QEAAHKPEAUtagWFC_PHY_INFO@@@Z`
- size: `702`
- prototype: `__int64 __fastcall(CAdapterPropertyCache *__hidden this, unsigned int, struct tagWFC_PHY_INFO *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x14005758c`

## callees

- `0x140009420`
- `0x14000c778`
- `0x14000c940`
- `0x14000d054`
- `0x1400119f0`
- `0x140016d00`
- `0x140024a20`
- `0x14002aaec`
- `0x140067a78`
- `0x1400680e8`
- `0x140068404`

## pseudocode

```c
__int64 __fastcall CAdapterPropertyCache::SetPhyProperties(
        CAdapterPropertyCache *this,
        unsigned int a2,
        struct tagWFC_PHY_INFO *a3)
{
  unsigned __int64 v3; // rdi
  unsigned int PropertyListProperty; // eax
  int v6; // edx
  unsigned int v7; // ebx
  int v8; // edx
  unsigned __int8 *v9; // r15
  unsigned int PropertyPropertyCacheList; // eax
  int v11; // edx
  int v12; // r9d
  CPropertyCache *v13; // r14
  __int64 v14; // rsi
  int v15; // r8d
  struct _WFC_PROPERTY_LOAD_INFO *v17; // [rsp+28h] [rbp-50h]
  struct CPropertyCache *v18; // [rsp+90h] [rbp+18h] BYREF

  v3 = a2;
  v18 = 0;
  if ( a3 && a2 )
  {
    PropertyListProperty = CPropertyCache::LoadPropertyListProperty(
                             this,
                             3u,
                             a2,
                             0x234u,
                             (unsigned __int8 *)a3,
                             (const struct _WFC_PROPERTY_LOAD_INFO *)qword_1400FE7F0,
                             7u,
                             8u);
    v7 = PropertyListProperty;
    if ( PropertyListProperty )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v17) = PropertyListProperty;
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          1,
          65,
          (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
          v17);
      }
    }
    else
    {
      v9 = (unsigned __int8 *)operator new(saturated_mul(v3, 4u));
      if ( v9 )
      {
        PropertyPropertyCacheList = CPropertyCache::GetPropertyPropertyCacheList(this, 3u, &v18);
        v7 = PropertyPropertyCacheList;
        if ( PropertyPropertyCacheList )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v12 = 67;
LABEL_29:
            LODWORD(v17) = PropertyPropertyCacheList;
            LOBYTE(v11) = 2;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v11,
              1,
              v12,
              (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
              v17);
          }
        }
        else
        {
          v13 = v18;
          v14 = 0;
          while ( v13 )
          {
            PropertyPropertyCacheList = CPropertyCache::SetPropertyULong(v13, 7u, v14);
            v7 = PropertyPropertyCacheList;
            if ( PropertyPropertyCacheList )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_30;
              v12 = 68;
              goto LABEL_29;
            }
            if ( (unsigned int)v14 >= (unsigned int)v3 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v11) = 2;
                WPP_RECORDER_SF_Ld(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v11,
                  v15,
                  69,
                  (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
                  v14,
                  v3);
              }
              v7 = -1073676267;
              goto LABEL_30;
            }
            PropertyPropertyCacheList = CPropertyCache::GetPropertyULong(v13, 0, (unsigned int *)&v9[4 * v14]);
            v7 = PropertyPropertyCacheList;
            if ( PropertyPropertyCacheList )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_30;
              v12 = 70;
              goto LABEL_29;
            }
            v13 = *(CPropertyCache **)v13;
            v14 = (unsigned int)(v14 + 1);
          }
          PropertyPropertyCacheList = CPropertyCache::SetPropertyList(this, 4, (unsigned int)(4 * v3), v3, v9);
          v7 = PropertyPropertyCacheList;
          if ( PropertyPropertyCacheList && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v12 = 71;
            goto LABEL_29;
          }
        }
LABEL_30:
        operator delete(v9);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v8) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v8,
            1,
            66,
            (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids);
        }
        return (unsigned int)-1073741670;
      }
    }
  }
  else
  {
    v7 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        64,
        (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1400680e8  mov     rax, rsp
0x1400680eb  push    rbx
0x1400680ec  push    rbp
0x1400680ed  push    rsi
0x1400680ee  push    rdi
0x1400680ef  push    r14
0x1400680f1  push    r15
0x1400680f3  sub     rsp, 48h
0x1400680f7  mov     edi, edx
0x1400680f9  mov     rbp, rcx
0x1400680fc  mov     qword ptr [rax+18h], 0
0x140068104  test    r8, r8
0x140068107  jz      loc_14006835E
0x14006810d  test    edx, edx
0x14006810f  jz      loc_14006835E
0x140068115  mov     dword ptr [rax-40h], 8
0x14006811c  mov     esi, 3
0x140068121  mov     dword ptr [rax-48h], 7
0x140068128  mov     r9d, 234h; unsigned int
0x14006812e  lea     rax, qword_1400FE7F0
0x140068135  mov     edx, esi; unsigned int
0x140068137  mov     [rsp+78h+var_50], rax; struct _WFC_PROPERTY_LOAD_INFO *
0x14006813c  mov     [rsp+78h+var_58], r8; unsigned __int8 *
0x140068141  mov     r8d, edi; unsigned int
0x140068144  call    ?LoadPropertyListProperty@CPropertyCache@@IEAAHKIIPEAEPEBU_WFC_PROPERTY_LOAD_INFO@@KI@Z; CPropertyCache::LoadPropertyListProperty(ulong,uint,uint,uchar *,_WFC_PROPERTY_LOAD_INFO const *,ulong,uint)
0x140068149  mov     ebx, eax
0x14006814b  test    eax, eax
0x14006814d  jz      short loc_140068192
0x14006814f  lea     rcx, WPP_RECORDER_INITIALIZED
0x140068156  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14006815d  jz      loc_140068396
0x140068163  mov     rcx, cs:WPP_GLOBAL_Control
0x14006816a  lea     r9d, [rsi+3Eh]
0x14006816e  mov     dword ptr [rsp+78h+var_50], eax
0x140068172  lea     r8d, [rsi-2]
0x140068176  lea     rax, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x14006817d  mov     dl, 2
0x14006817f  mov     [rsp+78h+var_58], rax
0x140068184  mov     rcx, [rcx+40h]
0x140068188  call    WPP_RECORDER_SF_d
0x14006818d  jmp     loc_140068396
0x140068192  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140068199  mov     eax, 4
0x14006819e  mul     rdi
0x1400681a1  cmovb   rax, rcx
0x1400681a5  mov     rcx, rax; unsigned __int64
0x1400681a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400681ad  mov     r15, rax
0x1400681b0  test    rax, rax
0x1400681b3  jnz     short loc_1400681F5
0x1400681b5  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400681bc  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400681c3  jz      short loc_1400681EB
0x1400681c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400681cc  lea     r9d, [rax+42h]
0x1400681d0  lea     rax, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x1400681d7  mov     dl, 2
0x1400681d9  lea     r8d, [r15+1]
0x1400681dd  mov     [rsp+78h+var_58], rax
0x1400681e2  mov     rcx, [rcx+40h]
0x1400681e6  call    WPP_RECORDER_SF_
0x1400681eb  mov     ebx, 0C000009Ah
0x1400681f0  jmp     loc_140068396
0x1400681f5  lea     r8, [rsp+78h+arg_10]; struct CPropertyCache **
0x1400681fd  mov     edx, esi; unsigned int
0x1400681ff  mov     rcx, rbp; this
0x140068202  call    ?GetPropertyPropertyCacheList@CPropertyCache@@QEAAHKPEAPEAV1@@Z; CPropertyCache::GetPropertyPropertyCacheList(ulong,CPropertyCache * *)
0x140068207  mov     ebx, eax
0x140068209  test    eax, eax
0x14006820b  jz      short loc_14006822C
0x14006820d  lea     rcx, WPP_RECORDER_INITIALIZED
0x140068214  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14006821b  jz      loc_140068354
0x140068221  mov     r9d, 43h ; 'C'
0x140068227  jmp     loc_14006832C
0x14006822c  mov     r14, [rsp+78h+arg_10]
0x140068234  xor     esi, esi
0x140068236  test    r14, r14
0x140068239  jz      loc_1400682F2
0x14006823f  mov     r8d, esi; unsigned int
0x140068242  mov     edx, 7; unsigned int
0x140068247  mov     rcx, r14; this
0x14006824a  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x14006824f  mov     ebx, eax
0x140068251  test    eax, eax
0x140068253  jnz     loc_1400682DA
0x140068259  cmp     esi, edi
0x14006825b  jnb     short loc_140068297
0x14006825d  lea     r8, [r15+rsi*4]; unsigned int *
0x140068261  xor     edx, edx; unsigned int
0x140068263  mov     rcx, r14; this
0x140068266  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x14006826b  mov     ebx, eax
0x14006826d  test    eax, eax
0x14006826f  jnz     short loc_140068278
0x140068271  mov     r14, [r14]
0x140068274  inc     esi
0x140068276  jmp     short loc_140068236
0x140068278  lea     rcx, WPP_RECORDER_INITIALIZED
0x14006827f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140068286  jz      loc_140068354
0x14006828c  mov     r9d, 46h ; 'F'
0x140068292  jmp     loc_14006832C
0x140068297  lea     rcx, WPP_RECORDER_INITIALIZED
0x14006829e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400682a5  jz      short loc_1400682D3
0x1400682a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400682ae  lea     rax, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x1400682b5  mov     [rsp+78h+var_48], edi
0x1400682b9  mov     r9d, 45h ; 'E'
0x1400682bf  mov     dword ptr [rsp+78h+var_50], esi
0x1400682c3  mov     dl, 2
0x1400682c5  mov     [rsp+78h+var_58], rax
0x1400682ca  mov     rcx, [rcx+40h]
0x1400682ce  call    WPP_RECORDER_SF_Ld
0x1400682d3  mov     ebx, 0C0010015h
0x1400682d8  jmp     short loc_140068354
0x1400682da  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400682e1  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400682e8  jz      short loc_140068354
0x1400682ea  mov     r9d, 44h ; 'D'
0x1400682f0  jmp     short loc_14006832C
0x1400682f2  movzx   r9d, di; unsigned __int16
0x1400682f6  mov     [rsp+78h+var_58], r15; unsigned __int8 *
0x1400682fb  lea     r8d, ds:0[rdi*4]; unsigned int
0x140068303  mov     edx, 4; unsigned int
0x140068308  mov     rcx, rbp; this
0x14006830b  call    ?SetPropertyList@CPropertyCache@@QEAAHKKGPEAE@Z; CPropertyCache::SetPropertyList(ulong,ulong,ushort,uchar *)
0x140068310  mov     ebx, eax
0x140068312  test    eax, eax
0x140068314  jz      short loc_140068354
0x140068316  lea     rcx, WPP_RECORDER_INITIALIZED
0x14006831d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140068324  jz      short loc_140068354
0x140068326  mov     r9d, 47h ; 'G'
0x14006832c  mov     rcx, cs:WPP_GLOBAL_Control
0x140068333  mov     r8d, 1
0x140068339  mov     dword ptr [rsp+78h+var_50], eax
0x14006833d  mov     dl, 2
0x14006833f  lea     rax, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x140068346  mov     [rsp+78h+var_58], rax
0x14006834b  mov     rcx, [rcx+40h]
0x14006834f  call    WPP_RECORDER_SF_d
0x140068354  mov     rcx, r15; void *
0x140068357  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14006835c  jmp     short loc_140068396
0x14006835e  xor     ebx, ebx
0x140068360  lea     rcx, WPP_RECORDER_INITIALIZED
0x140068367  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14006836e  jz      short loc_140068396
0x140068370  mov     rcx, cs:WPP_GLOBAL_Control
0x140068377  lea     rax, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x14006837e  lea     r9d, [rbx+40h]
0x140068382  mov     [rsp+78h+var_58], rax
0x140068387  lea     r8d, [rbx+1]
0x14006838b  mov     dl, 2
0x14006838d  mov     rcx, [rcx+40h]
0x140068391  call    WPP_RECORDER_SF_
0x140068396  mov     eax, ebx
0x140068398  add     rsp, 48h
0x14006839c  pop     r15
0x14006839e  pop     r14
0x1400683a0  pop     rdi
0x1400683a1  pop     rsi
0x1400683a2  pop     rbp
0x1400683a3  pop     rbx
0x1400683a4  retn
```
