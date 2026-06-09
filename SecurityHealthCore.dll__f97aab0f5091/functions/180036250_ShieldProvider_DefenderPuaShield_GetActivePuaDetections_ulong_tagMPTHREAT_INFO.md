# ShieldProvider::DefenderPuaShield::GetActivePuaDetections(ulong *,tagMPTHREAT_INFO * * *)

- ea: `0x180036250`
- end: `0x180036446`
- name: `?GetActivePuaDetections@DefenderPuaShield@ShieldProvider@@UEAAJPEAKPEAPEAPEAUtagMPTHREAT_INFO@@@Z`
- size: `502`
- prototype: `__int64 __fastcall(ShieldProvider::DefenderPuaShield *__hidden this, unsigned int *, struct tagMPTHREAT_INFO ***)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d7fc`
- `0x180016d08`
- `0x1800298a0`
- `0x18002a034`
- `0x18002e680`
- `0x180034434`
- `0x180034958`
- `0x18003522c`
- `0x180035b2c`
- `0x180036250`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800363e2`
- `ole32!CoTaskMemFree` at `0x180036405`
- `ole32!CoTaskMemFree` at `0x1800363e2`
- `ole32!CoTaskMemFree` at `0x180036405`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DefenderPuaShield::GetActivePuaDetections(
        ShieldProvider::DefenderPuaShield *this,
        unsigned int *a2,
        struct tagMPTHREAT_INFO ***a3)
{
  unsigned int v3; // esi
  struct tagMPTHREAT_INFO **v4; // r15
  __int64 v5; // r10
  unsigned int CurrentActiveThreats; // eax
  struct tagMPTHREAT_INFO *v7; // rdx
  ShieldProvider **v8; // r12
  unsigned int i; // ebx
  int v10; // r14d
  int v11; // eax
  struct tagMPTHREAT_INFO **v12; // r8
  unsigned int *v13; // rbx
  __int64 v14; // r13
  unsigned int *v15; // rdi
  __int64 j; // rbx
  __int64 k; // rbx
  LPVOID pv; // [rsp+20h] [rbp-30h] BYREF
  struct tagMPTHREAT_INFO **v20; // [rsp+28h] [rbp-28h] BYREF
  _QWORD v21[4]; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v24; // [rsp+A8h] [rbp+58h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  *a2 = 0;
  v3 = 0;
  *a3 = 0;
  v4 = 0;
  v20 = 0;
  v24 = 0;
  std::vector<_incompatibleDriver>::vector<_incompatibleDriver>(v21);
  CurrentActiveThreats = ShieldProvider::GetCurrentActiveThreats(
                           *(ShieldProvider **)(v5 + 56),
                           0,
                           (bool)&v24,
                           (unsigned int *)&pv,
                           0);
  v8 = (ShieldProvider **)pv;
  if ( CurrentActiveThreats )
  {
    if ( CurrentActiveThreats != 1 )
    {
      v7 = (struct tagMPTHREAT_INFO *)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          WPP_80ef7ce797a33dd123a9e70e82e6d042_Traceguids,
          CurrentActiveThreats);
    }
  }
  else if ( pv )
  {
    for ( i = 0; ; CurrentActiveThreats = i )
    {
      LODWORD(pv) = i;
      if ( CurrentActiveThreats >= v24 )
        break;
      if ( ShieldProvider::IsThreatPUA(v8[CurrentActiveThreats], v7) )
      {
        v10 = CommonUtil::HrStdPushBack<CommonUtil::CStdVector<unsigned long,std::allocator<unsigned long>>,unsigned long>(
                v21,
                &pv);
        if ( v10 < 0 )
          goto LABEL_25;
        i = (unsigned int)pv;
        ++v3;
      }
      ++i;
    }
    if ( v3 )
    {
      v11 = CommonUtil::UtilCoTaskMemAllocArray<tagMPTHREAT_INFO *>(&v20, v3);
      v4 = v20;
      v10 = v11;
      if ( v11 >= 0 )
      {
        v13 = (unsigned int *)v21[0];
        v14 = 0;
        v15 = (unsigned int *)v21[1];
        while ( v13 != v15 )
        {
          if ( (unsigned int)v14 >= v3 )
          {
            v10 = -2147418113;
            goto LABEL_25;
          }
          v10 = ShieldProvider::UtilDuplicateThreat(v8[*v13], (const struct tagMPTHREAT_INFO *)&v4[v14], v12);
          if ( v10 < 0 )
            goto LABEL_25;
          v14 = (unsigned int)(v14 + 1);
          ++v13;
        }
        *a2 = v3;
        *a3 = v4;
        v4 = 0;
      }
      goto LABEL_25;
    }
  }
  v10 = 1;
LABEL_25:
  if ( v8 )
  {
    for ( j = 0; (unsigned int)j < v24; j = (unsigned int)(j + 1) )
      ShieldProvider::FreeMpThreatInfo(v8[j], v7);
    CoTaskMemFree(v8);
  }
  if ( v4 )
  {
    for ( k = 0; (unsigned int)k < v3; k = (unsigned int)(k + 1) )
      ShieldProvider::FreeMpThreatInfo(v4[k], v7);
    CoTaskMemFree(v4);
  }
  if ( v21[0] )
    std::_Deallocate<16>(v21[0], (v21[2] - v21[0]) & 0xFFFFFFFFFFFFFFFCuLL);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180036250  mov     [rsp-38h+arg_0], rbx
0x180036255  mov     [rsp-38h+arg_10], r8
0x18003625a  mov     [rsp-38h+arg_8], rdx
0x18003625f  push    rbp
0x180036260  push    rsi
0x180036261  push    rdi
0x180036262  push    r12
0x180036264  push    r13
0x180036266  push    r14
0x180036268  push    r15
0x18003626a  mov     rbp, rsp
0x18003626d  sub     rsp, 50h
0x180036271  mov     rax, r8
0x180036274  mov     r10, rcx
0x180036277  test    rdx, rdx
0x18003627a  jz      loc_180036429
0x180036280  test    rax, rax
0x180036283  jz      loc_180036429
0x180036289  mov     dword ptr [rdx], 0
0x18003628f  lea     rcx, [rbp+var_20]
0x180036293  xor     esi, esi
0x180036295  mov     qword ptr [r8], 0
0x18003629c  xor     r15d, r15d
0x18003629f  mov     [rbp+pv], rsi
0x1800362a3  mov     [rbp+var_28], r15
0x1800362a7  mov     [rbp+arg_18], 0
0x1800362ae  call    ??0?$vector@U_incompatibleDriver@@V?$allocator@U_incompatibleDriver@@@std@@@std@@QEAA@XZ; std::vector<_incompatibleDriver>::vector<_incompatibleDriver>(void)
0x1800362b3  mov     rcx, [r10+38h]; this
0x1800362b7  lea     r9, [rbp+pv]; unsigned int *
0x1800362bb  lea     r8, [rbp+arg_18]; bool
0x1800362bf  xor     edx, edx; struct tagMPCONTEXT *
0x1800362c1  call    ?GetCurrentActiveThreats@ShieldProvider@@YAJPEAUtagMPCONTEXT@@_NPEAKPEAPEAPEAUtagMPTHREAT_INFO@@@Z; ShieldProvider::GetCurrentActiveThreats(tagMPCONTEXT *,bool,ulong *,tagMPTHREAT_INFO * * *)
0x1800362c6  mov     r12, [rbp+pv]
0x1800362ca  test    eax, eax
0x1800362cc  jnz     loc_180036387
0x1800362d2  test    r12, r12
0x1800362d5  jz      loc_1800363BD
0x1800362db  xor     ebx, ebx
0x1800362dd  mov     dword ptr [rbp+pv], ebx
0x1800362e0  cmp     eax, [rbp+arg_18]
0x1800362e3  jnb     short loc_180036317
0x1800362e5  mov     ecx, eax
0x1800362e7  mov     rcx, [r12+rcx*8]; this
0x1800362eb  call    ?IsThreatPUA@ShieldProvider@@YA_NPEAUtagMPTHREAT_INFO@@@Z; ShieldProvider::IsThreatPUA(tagMPTHREAT_INFO *)
0x1800362f0  test    al, al
0x1800362f2  jz      short loc_180036311
0x1800362f4  lea     rdx, [rbp+pv]
0x1800362f8  lea     rcx, [rbp+var_20]
0x1800362fc  call    ??$HrStdPushBack@V?$CStdVector@KV?$allocator@K@std@@@CommonUtil@@K@CommonUtil@@YAJAEAV?$CStdVector@KV?$allocator@K@std@@@0@AEBK@Z; CommonUtil::HrStdPushBack<CommonUtil::CStdVector<ulong,std::allocator<ulong>>,ulong>(CommonUtil::CStdVector<ulong,std::allocator<ulong>> &,ulong const &)
0x180036301  mov     r14d, eax
0x180036304  test    eax, eax
0x180036306  js      loc_1800363C3
0x18003630c  mov     ebx, dword ptr [rbp+pv]
0x18003630f  inc     esi
0x180036311  inc     ebx
0x180036313  mov     eax, ebx
0x180036315  jmp     short loc_1800362DD
0x180036317  test    esi, esi
0x180036319  jz      loc_1800363BD
0x18003631f  mov     edx, esi
0x180036321  lea     rcx, [rbp+var_28]
0x180036325  call    ??$UtilCoTaskMemAllocArray@PEAUtagMPTHREAT_INFO@@@CommonUtil@@YAJPEAPEAPEAUtagMPTHREAT_INFO@@_K_N@Z; CommonUtil::UtilCoTaskMemAllocArray<tagMPTHREAT_INFO *>(tagMPTHREAT_INFO * * *,unsigned __int64,bool)
0x18003632a  mov     r15, [rbp+var_28]
0x18003632e  mov     r14d, eax
0x180036331  test    eax, eax
0x180036333  js      loc_1800363C3
0x180036339  mov     rbx, [rbp+var_20]
0x18003633d  xor     r13d, r13d
0x180036340  mov     rdi, [rbp+var_18]
0x180036344  cmp     rbx, rdi
0x180036347  jz      short loc_180036375
0x180036349  cmp     r13d, esi
0x18003634c  jnb     short loc_18003636D
0x18003634e  mov     ecx, [rbx]
0x180036350  lea     rdx, [r15+r13*8]; struct tagMPTHREAT_INFO *
0x180036354  mov     rcx, [r12+rcx*8]; this
0x180036358  call    ?UtilDuplicateThreat@ShieldProvider@@YAJPEBUtagMPTHREAT_INFO@@PEAPEAU2@@Z; ShieldProvider::UtilDuplicateThreat(tagMPTHREAT_INFO const *,tagMPTHREAT_INFO * *)
0x18003635d  mov     r14d, eax
0x180036360  test    eax, eax
0x180036362  js      short loc_1800363C3
0x180036364  inc     r13d
0x180036367  add     rbx, 4
0x18003636b  jmp     short loc_180036344
0x18003636d  mov     r14d, 8000FFFFh
0x180036373  jmp     short loc_1800363C3
0x180036375  mov     rax, [rbp+arg_8]
0x180036379  mov     [rax], esi
0x18003637b  mov     rax, [rbp+arg_10]
0x18003637f  mov     [rax], r15
0x180036382  xor     r15d, r15d
0x180036385  jmp     short loc_1800363C3
0x180036387  cmp     eax, 1
0x18003638a  jz      short loc_1800363BD
0x18003638c  mov     rcx, cs:WPP_GLOBAL_Control
0x180036393  lea     rdx, WPP_GLOBAL_Control
0x18003639a  cmp     rcx, rdx
0x18003639d  jz      short loc_1800363BD
0x18003639f  test    byte ptr [rcx+1Ch], 1
0x1800363a3  jz      short loc_1800363BD
0x1800363a5  mov     rcx, [rcx+10h]
0x1800363a9  lea     r8, WPP_80ef7ce797a33dd123a9e70e82e6d042_Traceguids
0x1800363b0  mov     edx, 33h ; '3'
0x1800363b5  mov     r9d, eax
0x1800363b8  call    WPP_SF_d
0x1800363bd  mov     r14d, 1
0x1800363c3  test    r12, r12
0x1800363c6  jz      short loc_1800363E8
0x1800363c8  xor     ebx, ebx
0x1800363ca  cmp     [rbp+arg_18], ebx
0x1800363cd  jbe     short loc_1800363DF
0x1800363cf  mov     rcx, [r12+rbx*8]; this
0x1800363d3  call    ?FreeMpThreatInfo@ShieldProvider@@YAXPEAUtagMPTHREAT_INFO@@@Z; ShieldProvider::FreeMpThreatInfo(tagMPTHREAT_INFO *)
0x1800363d8  inc     ebx
0x1800363da  cmp     ebx, [rbp+arg_18]
0x1800363dd  jb      short loc_1800363CF
0x1800363df  mov     rcx, r12; pv
0x1800363e2  call    cs:__imp_CoTaskMemFree
0x1800363e8  test    r15, r15
0x1800363eb  jz      short loc_18003640B
0x1800363ed  xor     ebx, ebx
0x1800363ef  test    esi, esi
0x1800363f1  jz      short loc_180036402
0x1800363f3  mov     rcx, [r15+rbx*8]; this
0x1800363f7  call    ?FreeMpThreatInfo@ShieldProvider@@YAXPEAUtagMPTHREAT_INFO@@@Z; ShieldProvider::FreeMpThreatInfo(tagMPTHREAT_INFO *)
0x1800363fc  inc     ebx
0x1800363fe  cmp     ebx, esi
0x180036400  jb      short loc_1800363F3
0x180036402  mov     rcx, r15; pv
0x180036405  call    cs:__imp_CoTaskMemFree
0x18003640b  mov     rcx, [rbp+var_20]
0x18003640f  test    rcx, rcx
0x180036412  jz      short loc_180036424
0x180036414  mov     rdx, [rbp+var_10]
0x180036418  sub     rdx, rcx
0x18003641b  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18003641f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180036424  mov     eax, r14d
0x180036427  jmp     short loc_18003642E
0x180036429  mov     eax, 80070057h
0x18003642e  mov     rbx, [rsp+50h+arg_0]
0x180036436  add     rsp, 50h
0x18003643a  pop     r15
0x18003643c  pop     r14
0x18003643e  pop     r13
0x180036440  pop     r12
0x180036442  pop     rdi
0x180036443  pop     rsi
0x180036444  pop     rbp
0x180036445  retn
```
