# RoutePolicyCache::QueryRoutingRulesForInterface(WcmRoutePolicy::RoutingRulesForInterface * const,ulong,ulong *)

- ea: `0x140002618`
- end: `0x140002944`
- name: `?QueryRoutingRulesForInterface@RoutePolicyCache@@YAJQEAURoutingRulesForInterface@WcmRoutePolicy@@KPEAK@Z`
- size: `812`
- prototype: `__int64 __fastcall(RoutePolicyCache *__hidden this, struct WcmRoutePolicy::RoutingRulesForInterface *const, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140008878`

## callees

- `0x1400012f0`
- `0x140002618`
- `0x140007d28`
- `0x140007d7c`
- `0x14000a680`
- `0x14000a780`

## pseudocode

```c
__int64 __fastcall RoutePolicyCache::QueryRoutingRulesForInterface(
        RoutePolicyCache *this,
        struct WcmRoutePolicy::RoutingRulesForInterface *const a2,
        unsigned int *a3,
        unsigned int *a4)
{
  unsigned int v5; // r12d
  unsigned int v6; // edi
  PVOID *v7; // rdx
  __int64 v8; // r8
  char *v10; // r15
  char *v11; // rbx
  unsigned int v12; // r13d
  int v13; // edx
  int v14; // eax
  __int64 *v15; // rcx
  bool v16; // cf
  __int64 *v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rsi
  unsigned int v23; // eax
  unsigned int *v24; // rsi
  unsigned int v25; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v26; // [rsp+34h] [rbp-CCh]
  int v27; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v28; // [rsp+3Ch] [rbp-C4h] BYREF
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  void *v30; // [rsp+48h] [rbp-B8h]
  __int128 v31; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int *v32; // [rsp+60h] [rbp-A0h]
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+68h] [rbp-98h] BYREF
  unsigned int *v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+90h] [rbp-70h]
  struct _EVENT_DATA_DESCRIPTOR v36; // [rsp+A0h] [rbp-60h] BYREF
  int *v37; // [rsp+C0h] [rbp-40h]
  __int64 v38; // [rsp+C8h] [rbp-38h]
  int *v39; // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  __int64 *v41; // [rsp+E0h] [rbp-20h]
  int v42; // [rsp+E8h] [rbp-18h]
  int v43; // [rsp+ECh] [rbp-14h]
  __int64 *v44; // [rsp+F0h] [rbp-10h]
  int v45; // [rsp+F8h] [rbp-8h]
  int v46; // [rsp+FCh] [rbp-4h]
  int *v47; // [rsp+100h] [rbp+0h]
  __int64 v48; // [rsp+108h] [rbp+8h]

  v26 = (unsigned int)a2;
  v32 = a3;
  v5 = 0;
  v6 = 12;
  *a3 = 12;
  AcquireSpinLock(&v31, &g_cacheLock);
  v7 = (PVOID *)g_rulesListHead;
  if ( g_rulesListHead == &g_rulesListHead )
    goto LABEL_6;
  v8 = *(_QWORD *)this;
  while ( v8 && *(_QWORD *)v7[2] != v8 )
  {
    v7 = (PVOID *)*v7;
    if ( v7 == &g_rulesListHead )
      goto LABEL_6;
  }
  v10 = (char *)v7[2];
  if ( v10 && *((_DWORD *)v10 + 2) )
  {
    v30 = (char *)this + 12;
    v11 = v10 + 12;
    v12 = 0;
    do
    {
      if ( (unsigned int)dword_140012050 > 4 )
      {
        v13 = *(_DWORD *)v11;
        if ( (*(_DWORD *)v11 & 0x10000) != 0 )
          v14 = *((_DWORD *)v11 + 116);
        else
          v14 = 0;
        v27 = v14;
        v15 = (__int64 *)(v11 + 260);
        if ( (v13 & 0x1000) == 0 )
          v15 = &qword_14000C9D0;
        v16 = (v13 & 0x800) != 0;
        v17 = (__int64 *)(v11 + 4);
        if ( !v16 )
          v17 = &qword_14000C9D0;
        v48 = 4;
        v28 = v12 + 1;
        v29 = *((_DWORD *)v10 + 2);
        v47 = &v27;
        if ( v15 )
        {
          v18 = -1;
          do
            ++v18;
          while ( *((_WORD *)v15 + v18) );
          v19 = 2 * v18 + 2;
        }
        else
        {
          v15 = &qword_14000C868;
          v19 = 2;
        }
        v44 = v15;
        v45 = v19;
        v46 = 0;
        if ( v17 )
        {
          v20 = -1;
          do
            ++v20;
          while ( *((_WORD *)v17 + v20) );
          v21 = 2 * v20 + 2;
        }
        else
        {
          v17 = &qword_14000C868;
          v21 = 2;
        }
        v42 = v21;
        v41 = v17;
        v39 = (int *)&v28;
        v43 = 0;
        v37 = &v29;
        v40 = 4;
        v38 = 4;
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, (unsigned __int8 *)&unk_14000E0D0, 0, 0, 7u, &v36);
      }
      if ( *((_DWORD *)v11 + 117) && (unsigned int)dword_140012050 > 5 )
      {
        v35 = 4 * (unsigned int)(unsigned __int8)v11[473] + 8;
        v34 = (unsigned int *)(v11 + 472);
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, (unsigned __int8 *)&word_14000E692, 0, 0, 3u, &v33);
      }
      v6 += *((_DWORD *)v11 + 117) + 472;
      v22 = (unsigned int)(*((_DWORD *)v11 + 117) + 472);
      if ( v26 >= v6 )
      {
        memmove(v30, v11, (unsigned int)v22);
        v30 = (char *)v30 + v22;
      }
      v23 = *((_DWORD *)v10 + 2);
      v11 += v22;
      ++v12;
    }
    while ( v12 < v23 );
    v5 = 0;
    v24 = v32;
    if ( v26 < v6 )
    {
      *((_DWORD *)this + 2) = v6;
      if ( (unsigned int)dword_140012050 > 4 )
      {
        v25 = v6;
        v34 = &v25;
        v35 = 4;
        tlgWriteTransfer_EtwWriteTransfer(
          (__int64)&dword_140012050,
          (unsigned __int8 *)&dword_14000E1EC,
          0,
          0,
          3u,
          &v33);
      }
      v5 = -2147483643;
    }
    else
    {
      *((_DWORD *)this + 2) = v23;
      *v24 = v6;
    }
  }
  else
  {
LABEL_6:
    *((_DWORD *)this + 2) = 0;
  }
  if ( (_QWORD)v31 )
    SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v31);
  return v5;
}

```

## disassembly

```asm
0x140002618  mov     [rsp-8+arg_8], rbx
0x14000261d  push    rbp
0x14000261e  push    rsi
0x14000261f  push    rdi
0x140002620  push    r12
0x140002622  push    r13
0x140002624  push    r14
0x140002626  push    r15
0x140002628  lea     rbp, [rsp-20h]
0x14000262d  sub     rsp, 120h
0x140002634  mov     rax, cs:__security_cookie
0x14000263b  xor     rax, rsp
0x14000263e  mov     [rbp+50h+var_40], rax
0x140002642  xor     eax, eax
0x140002644  mov     [rsp+150h+var_11C], edx
0x140002648  mov     r14, rcx
0x14000264b  mov     [rsp+150h+var_F0], r8
0x140002650  lea     rdx, ?g_cacheLock@@3_KA; unsigned __int64 g_cacheLock
0x140002657  mov     rsi, r8
0x14000265a  lea     rcx, [rsp+150h+var_100]
0x14000265f  mov     r12d, eax
0x140002662  lea     edi, [rax+0Ch]
0x140002665  mov     [r8], edi
0x140002668  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x14000266d  mov     rdx, cs:?g_rulesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_rulesListHead
0x140002674  lea     r10, ?g_rulesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_rulesListHead
0x14000267b  xor     r9d, r9d
0x14000267e  cmp     rdx, r10
0x140002681  jz      short loc_14000269C
0x140002683  mov     r8, [r14]
0x140002686  test    r8, r8
0x140002689  jz      short loc_1400026E9
0x14000268b  mov     rax, [rdx+10h]
0x14000268f  cmp     [rax], r8
0x140002692  jz      short loc_1400026E9
0x140002694  mov     rdx, [rdx]
0x140002697  cmp     rdx, r10
0x14000269a  jnz     short loc_140002686
0x14000269c  mov     [r14+8], r9d
0x1400026a0  xor     eax, eax
0x1400026a2  cmp     qword ptr [rsp+150h+var_100], rax
0x1400026a7  jz      short loc_1400026BE
0x1400026a9  movaps  xmm0, [rsp+150h+var_100]
0x1400026ae  lea     rcx, [rsp+150h+var_100]; struct SpinLockAndSavedIrql *
0x1400026b3  movdqa  [rsp+150h+var_100], xmm0
0x1400026b9  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x1400026be  mov     eax, r12d
0x1400026c1  mov     rcx, [rbp+50h+var_40]
0x1400026c5  xor     rcx, rsp; StackCookie
0x1400026c8  call    __security_check_cookie
0x1400026cd  mov     rbx, [rsp+150h+arg_8]
0x1400026d5  add     rsp, 120h
0x1400026dc  pop     r15
0x1400026de  pop     r14
0x1400026e0  pop     r13
0x1400026e2  pop     r12
0x1400026e4  pop     rdi
0x1400026e5  pop     rsi
0x1400026e6  pop     rbp
0x1400026e7  retn
0x1400026e9  mov     r15, [rdx+10h]
0x1400026ed  test    r15, r15
0x1400026f0  jz      short loc_14000269C
0x1400026f2  mov     eax, [r15+8]
0x1400026f6  test    eax, eax
0x1400026f8  jz      short loc_14000269C
0x1400026fa  mov     r12d, [rsp+150h+var_11C]
0x1400026ff  lea     rcx, [r14+0Ch]
0x140002703  mov     [rsp+150h+var_108], rcx
0x140002708  lea     rbx, [r15+0Ch]
0x14000270c  mov     r13d, r9d
0x14000270f  mov     eax, cs:dword_140012050
0x140002715  cmp     eax, 4
0x140002718  jbe     loc_140002830
0x14000271e  mov     edx, [rbx]
0x140002720  bt      edx, 10h
0x140002724  jnb     short loc_14000272E
0x140002726  mov     eax, [rbx+1D0h]
0x14000272c  jmp     short loc_140002731
0x14000272e  mov     eax, r9d
0x140002731  mov     [rsp+150h+var_118], eax
0x140002735  lea     rcx, [rbx+104h]
0x14000273c  bt      edx, 0Ch
0x140002740  jb      short loc_140002749
0x140002742  lea     rcx, qword_14000C9D0
0x140002749  bt      edx, 0Bh
0x14000274d  lea     rdx, [rbx+4]
0x140002751  jb      short loc_14000275A
0x140002753  lea     rdx, qword_14000C9D0
0x14000275a  mov     [rbp+50h+var_48], 4
0x140002762  lea     eax, [r13+1]
0x140002766  mov     [rsp+150h+var_114], eax
0x14000276a  mov     eax, [r15+8]
0x14000276e  mov     [rsp+150h+var_110], eax
0x140002772  lea     rax, [rsp+150h+var_118]
0x140002777  mov     [rbp+50h+var_50], rax
0x14000277b  test    rcx, rcx
0x14000277e  jz      short loc_140002797
0x140002780  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002784  inc     rax
0x140002787  cmp     [rcx+rax*2], r9w
0x14000278c  jnz     short loc_140002784
0x14000278e  lea     eax, ds:2[rax*2]
0x140002795  jmp     short loc_1400027A3
0x140002797  lea     rcx, qword_14000C868
0x14000279e  mov     eax, 2
0x1400027a3  mov     [rbp+50h+var_60], rcx
0x1400027a7  mov     [rbp+50h+var_58], eax
0x1400027aa  mov     [rbp+50h+var_54], r9d
0x1400027ae  test    rdx, rdx
0x1400027b1  jz      short loc_1400027CA
0x1400027b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400027b7  inc     rax
0x1400027ba  cmp     [rdx+rax*2], r9w
0x1400027bf  jnz     short loc_1400027B7
0x1400027c1  lea     eax, ds:2[rax*2]
0x1400027c8  jmp     short loc_1400027D6
0x1400027ca  lea     rdx, qword_14000C868
0x1400027d1  mov     eax, 2
0x1400027d6  mov     [rbp+50h+var_68], eax
0x1400027d9  lea     rcx, dword_140012050; int
0x1400027e0  lea     rax, [rsp+150h+var_114]
0x1400027e5  mov     [rbp+50h+var_70], rdx
0x1400027e9  mov     [rbp+50h+var_80], rax
0x1400027ed  lea     rdx, unk_14000E0D0; int
0x1400027f4  lea     rax, [rsp+150h+var_110]
0x1400027f9  mov     [rbp+50h+var_64], r9d
0x1400027fd  mov     [rbp+50h+var_90], rax
0x140002801  xor     r9d, r9d; int
0x140002804  lea     rax, [rbp+50h+var_B0]
0x140002808  mov     [rbp+50h+var_78], 4
0x140002810  mov     [rsp+150h+var_128], rax; PEVENT_DATA_DESCRIPTOR
0x140002815  xor     r8d, r8d; int
0x140002818  mov     [rsp+150h+var_130], 7; ULONG
0x140002820  mov     [rbp+50h+var_88], 4
0x140002828  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000282d  xor     r9d, r9d
0x140002830  cmp     [rbx+1D4h], r9d
0x140002837  jbe     short loc_14000288F
0x140002839  mov     eax, cs:dword_140012050
0x14000283f  cmp     eax, 5
0x140002842  jbe     short loc_14000288F
0x140002844  movzx   eax, byte ptr [rbx+1D9h]
0x14000284b  lea     rdx, word_14000E692; int
0x140002852  mov     dword ptr [rbp+50h+var_C0+4], r9d
0x140002856  xor     r8d, r8d; int
0x140002859  xor     r9d, r9d; int
0x14000285c  lea     ecx, ds:8[rax*4]
0x140002863  lea     rax, [rbx+1D8h]
0x14000286a  mov     dword ptr [rbp+50h+var_C0], ecx
0x14000286d  mov     [rbp+50h+var_C8], rax
0x140002871  lea     rcx, dword_140012050; int
0x140002878  lea     rax, [rsp+150h+var_E8]
0x14000287d  mov     [rsp+150h+var_128], rax; PEVENT_DATA_DESCRIPTOR
0x140002882  mov     [rsp+150h+var_130], 3; ULONG
0x14000288a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000288f  mov     eax, [rbx+1D4h]
0x140002895  add     eax, 1D8h
0x14000289a  add     edi, eax
0x14000289c  mov     esi, eax
0x14000289e  cmp     r12d, edi
0x1400028a1  jb      short loc_1400028B8
0x1400028a3  mov     rcx, [rsp+150h+var_108]; void *
0x1400028a8  mov     r8d, esi; Size
0x1400028ab  mov     rdx, rbx; Src
0x1400028ae  call    memmove
0x1400028b3  add     [rsp+150h+var_108], rsi
0x1400028b8  mov     eax, [r15+8]
0x1400028bc  add     rbx, rsi
0x1400028bf  inc     r13d
0x1400028c2  mov     r9d, 0
0x1400028c8  cmp     r13d, eax
0x1400028cb  jb      loc_14000270F
0x1400028d1  mov     r12d, r9d
0x1400028d4  mov     rsi, [rsp+150h+var_F0]
0x1400028d9  cmp     [rsp+150h+var_11C], edi
0x1400028dd  jb      short loc_1400028EA
0x1400028df  mov     [r14+8], eax
0x1400028e3  mov     [rsi], edi
0x1400028e5  jmp     loc_1400026A0
0x1400028ea  mov     [r14+8], edi
0x1400028ee  mov     eax, cs:dword_140012050
0x1400028f4  cmp     eax, 4
0x1400028f7  jbe     short loc_140002939
0x1400028f9  lea     rax, [rsp+150h+var_120]
0x1400028fe  mov     [rsp+150h+var_120], edi
0x140002902  mov     [rbp+50h+var_C8], rax
0x140002906  lea     rdx, dword_14000E1EC; int
0x14000290d  lea     rax, [rsp+150h+var_E8]
0x140002912  mov     [rbp+50h+var_C0], 4
0x14000291a  mov     [rsp+150h+var_128], rax; PEVENT_DATA_DESCRIPTOR
0x14000291f  lea     rcx, dword_140012050; int
0x140002926  xor     r9d, r9d; int
0x140002929  mov     [rsp+150h+var_130], 3; ULONG
0x140002931  xor     r8d, r8d; int
0x140002934  call    _tlgWriteTransfer_EtwWriteTransfer
0x140002939  mov     r12d, 80000005h
0x14000293f  jmp     loc_1400026A0
```
