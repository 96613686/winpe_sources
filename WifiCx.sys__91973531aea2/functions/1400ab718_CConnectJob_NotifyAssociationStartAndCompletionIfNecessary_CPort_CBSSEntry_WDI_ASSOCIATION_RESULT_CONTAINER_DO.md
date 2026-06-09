# CConnectJob::NotifyAssociationStartAndCompletionIfNecessary(CPort *,CBSSEntry *,_WDI_ASSOCIATION_RESULT_CONTAINER *,DOT11_CONNECTION_INFO *)

- ea: `0x1400ab718`
- end: `0x1400aba19`
- name: `?NotifyAssociationStartAndCompletionIfNecessary@CConnectJob@@AEAAKPEAVCPort@@PEAVCBSSEntry@@PEAU_WDI_ASSOCIATION_RESULT_CONTAINER@@PEAUDOT11_CONNECTION_INFO@@@Z`
- size: `769`
- prototype: `__int64 __fastcall(CConnectJob *this, struct CPort *, struct CBSSEntry *, struct _WDI_ASSOCIATION_RESULT_CONTAINER *, struct DOT11_CONNECTION_INFO *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400b06f0`
- `0x1400b0a94`

## callees

- `0x14000c778`
- `0x14000c940`
- `0x14000d054`
- `0x14002ed50`
- `0x14003895c`
- `0x14006b8ac`
- `0x1400a5520`
- `0x1400ab718`
- `0x1400abc80`
- `0x1400b6878`

## pseudocode

```c
__int64 __fastcall CConnectJob::NotifyAssociationStartAndCompletionIfNecessary(
        CConnectJob *this,
        struct CPort *a2,
        struct CBSSEntry *a3,
        struct _WDI_ASSOCIATION_RESULT_CONTAINER *a4,
        struct DOT11_CONNECTION_INFO *a5)
{
  const struct _DOT11_SSID *v9; // rdx
  struct DOT11_CONNECTION_INFO *v10; // rsi
  char *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdx
  unsigned int v14; // ebp
  int v15; // r8d
  int v16; // r9d
  struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *v17; // rbx
  int v18; // edx
  int v19; // eax
  void *v20; // r9
  unsigned int v21; // edx
  CAdapter *v22; // rcx
  unsigned int v23; // eax
  int v24; // edx
  int v26; // [rsp+20h] [rbp-98h]
  unsigned __int8 v27; // [rsp+C0h] [rbp+8h] BYREF
  struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *v28; // [rsp+C8h] [rbp+10h] BYREF

  v27 = 0;
  v9 = &WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v9,
      1,
      127,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids);
  }
  if ( *((_QWORD *)a2 + 9) )
    *(_QWORD *)(*((_QWORD *)a2 + 9) + 104LL) = CSystem::get_CurrentTime();
  v10 = a5;
  *((_BYTE *)this + 5561) = *((_BYTE *)a3 + 596);
  v11 = (char *)v10 + 98;
  if ( !v10 )
    v11 = (char *)a4 + 4;
  *((_DWORD *)this + 332) = *(_DWORD *)v11;
  *((_WORD *)this + 666) = *((_WORD *)v11 + 2);
  v12 = *((_QWORD *)this + 123);
  *(_OWORD *)((char *)this + 1336) = *(_OWORD *)v12;
  *(_OWORD *)((char *)this + 1352) = *(_OWORD *)(v12 + 16);
  *((_DWORD *)this + 342) = *(_DWORD *)(v12 + 32);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF__MAC_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v9,
      (_DWORD)a3,
      128,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (__int64)this + 1328);
  }
  LODWORD(a5) = 0;
  v28 = 0;
  v14 = CConnectJob::FillAssociationCompletionParams(this, a3, a4, v10, &v28, (unsigned int *)&a5, &v27);
  if ( !v14 )
  {
    LOBYTE(v13) = *((_BYTE *)this + 1084) != 0;
    CConnectJob::NotifyDataPathOffloadChangeIfNecessary(this, v13, *((unsigned int *)a4 + 15));
  }
  v17 = v28;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( v10 )
    {
      v18 = *((_DWORD *)v10 + 2);
      v19 = *((_DWORD *)v10 + 1);
    }
    else
    {
      v18 = *((_DWORD *)a3 + 223);
      v19 = *((_DWORD *)a3 + 222);
    }
    WPP_RECORDER_SF_Dd_MAC_dddddDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v18,
      v15,
      v16,
      v26,
      0,
      *((_DWORD *)v28 + 24),
      (__int64)this + 1328,
      *((_DWORD *)v28 + 3),
      *((_DWORD *)v28 + 13),
      *((_DWORD *)v28 + 14),
      *((_DWORD *)v28 + 15),
      *((_DWORD *)v28 + 22),
      v19,
      v18);
  }
  v20 = (void *)*((_QWORD *)this + 662);
  v21 = *((_DWORD *)this + 1326);
  v22 = (CAdapter *)*((_QWORD *)this + 67);
  *((_BYTE *)this + 1324) = 0x80;
  *((_BYTE *)this + 1325) = 1;
  *((_WORD *)this + 663) = 56;
  CAdapter::IndicateStatus(v22, v21, 1073938434, v20, (char *)this + 1324, 0x38u);
  v23 = (unsigned int)a5;
  *(_DWORD *)v17 = 7602816;
  CAdapter::IndicateStatus(
    *((CAdapter **)this + 67),
    *((_DWORD *)this + 1326),
    1073938474,
    *((void **)this + 662),
    v17,
    v23);
  if ( v27 )
    operator delete(v17);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v24) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v24,
      1,
      130,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      v14);
  }
  return v14;
}

```

## disassembly

```asm
0x1400ab718  mov     rax, rsp
0x1400ab71b  mov     [rax+18h], rbx
0x1400ab71f  push    rbp
0x1400ab720  push    rsi
0x1400ab721  push    rdi
0x1400ab722  push    r12
0x1400ab724  push    r13
0x1400ab726  push    r14
0x1400ab728  push    r15
0x1400ab72a  sub     rsp, 80h
0x1400ab731  xor     ebp, ebp
0x1400ab733  mov     r15, r9
0x1400ab736  mov     [rax+8], bpl
0x1400ab73a  mov     r14, r8
0x1400ab73d  mov     rbx, rdx
0x1400ab740  mov     rdi, rcx
0x1400ab743  lea     rax, WPP_RECORDER_INITIALIZED
0x1400ab74a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ab751  lea     rdx, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400ab758  jz      short loc_1400AB787
0x1400ab75a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab761  cmp     byte ptr [rcx+29h], 5
0x1400ab765  jnb     short loc_1400AB76D
0x1400ab767  cmp     [rcx+48h], bp
0x1400ab76b  jz      short loc_1400AB787
0x1400ab76d  mov     rcx, [rcx+40h]
0x1400ab771  mov     r9d, 7Fh
0x1400ab777  mov     [rsp+0B8h+var_98], rdx
0x1400ab77c  mov     dl, 5
0x1400ab77e  lea     r8d, [r9-7Eh]
0x1400ab782  call    WPP_RECORDER_SF_
0x1400ab787  cmp     [rbx+48h], rbp
0x1400ab78b  jz      short loc_1400AB79A
0x1400ab78d  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x1400ab792  mov     rcx, [rbx+48h]
0x1400ab796  mov     [rcx+68h], rax
0x1400ab79a  mov     al, [r14+254h]
0x1400ab7a1  lea     r13, [rdi+52Ch]
0x1400ab7a8  mov     rsi, [rsp+0B8h+arg_20]
0x1400ab7b0  lea     r12, [r13+4]
0x1400ab7b4  mov     [rdi+15B9h], al
0x1400ab7ba  test    rsi, rsi
0x1400ab7bd  lea     rax, [r15+4]
0x1400ab7c1  lea     rcx, [rsi+62h]
0x1400ab7c5  cmovz   rcx, rax
0x1400ab7c9  mov     eax, [rcx]
0x1400ab7cb  mov     [r12], eax
0x1400ab7cf  movzx   eax, word ptr [rcx+4]
0x1400ab7d3  mov     [r12+4], ax
0x1400ab7d9  mov     rax, [rdi+3D8h]
0x1400ab7e0  movups  xmm0, xmmword ptr [rax]
0x1400ab7e3  movups  xmmword ptr [rdi+538h], xmm0
0x1400ab7ea  movups  xmm1, xmmword ptr [rax+10h]
0x1400ab7ee  movups  xmmword ptr [rdi+548h], xmm1
0x1400ab7f5  mov     eax, [rax+20h]
0x1400ab7f8  mov     [rdi+558h], eax
0x1400ab7fe  lea     rax, WPP_RECORDER_INITIALIZED
0x1400ab805  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ab80c  jz      short loc_1400AB843
0x1400ab80e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab815  cmp     byte ptr [rcx+29h], 5
0x1400ab819  jnb     short loc_1400AB821
0x1400ab81b  cmp     [rcx+48h], bp
0x1400ab81f  jz      short loc_1400AB843
0x1400ab821  mov     rcx, [rcx+40h]
0x1400ab825  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400ab82c  mov     r9d, 80h
0x1400ab832  mov     [rsp+0B8h+var_90], r12
0x1400ab837  mov     dl, 5
0x1400ab839  mov     [rsp+0B8h+var_98], rax
0x1400ab83e  call    WPP_RECORDER_SF__MAC_
0x1400ab843  lea     rax, [rsp+0B8h+arg_0]
0x1400ab84b  mov     dword ptr [rsp+0B8h+arg_20], ebp
0x1400ab852  mov     [rsp+0B8h+var_88], rax; unsigned __int8 *
0x1400ab857  mov     r9, rsi; struct DOT11_CONNECTION_INFO *
0x1400ab85a  lea     rax, [rsp+0B8h+arg_20]
0x1400ab862  mov     [rsp+0B8h+arg_8], rbp
0x1400ab86a  mov     [rsp+0B8h+var_90], rax; unsigned int *
0x1400ab86f  mov     r8, r15; struct _WDI_ASSOCIATION_RESULT_CONTAINER *
0x1400ab872  lea     rax, [rsp+0B8h+arg_8]
0x1400ab87a  mov     rdx, r14; struct CBSSEntry *
0x1400ab87d  mov     rcx, rdi; this
0x1400ab880  mov     [rsp+0B8h+var_98], rax; struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS **
0x1400ab885  call    ?FillAssociationCompletionParams@CConnectJob@@AEAAKPEAVCBSSEntry@@PEAU_WDI_ASSOCIATION_RESULT_CONTAINER@@PEAUDOT11_CONNECTION_INFO@@PEAPEAUDOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS@@PEAKPEAE@Z; CConnectJob::FillAssociationCompletionParams(CBSSEntry *,_WDI_ASSOCIATION_RESULT_CONTAINER *,DOT11_CONNECTION_INFO *,DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS * *,ulong *,uchar *)
0x1400ab88a  mov     ebp, eax
0x1400ab88c  xor     eax, eax
0x1400ab88e  test    ebp, ebp
0x1400ab890  jnz     short loc_1400AB8A7
0x1400ab892  cmp     [rdi+43Ch], al
0x1400ab898  mov     rcx, rdi
0x1400ab89b  mov     r8d, [r15+3Ch]
0x1400ab89f  setnz   dl
0x1400ab8a2  call    ?NotifyDataPathOffloadChangeIfNecessary@CConnectJob@@AEAAX_NW4_WDI_DISABLE_DATA_PATH_OFFLOADS_SCENARIO@@@Z; CConnectJob::NotifyDataPathOffloadChangeIfNecessary(bool,_WDI_DISABLE_DATA_PATH_OFFLOADS_SCENARIO)
0x1400ab8a7  mov     rbx, [rsp+0B8h+arg_8]
0x1400ab8af  lea     r15, WPP_RECORDER_INITIALIZED
0x1400ab8b6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400ab8bd  jz      short loc_1400AB92F
0x1400ab8bf  lea     rcx, [r14+37Ch]
0x1400ab8c6  test    rsi, rsi
0x1400ab8c9  jz      short loc_1400AB8D3
0x1400ab8cb  mov     edx, [rsi+8]
0x1400ab8ce  mov     eax, [rsi+4]
0x1400ab8d1  jmp     short loc_1400AB8DC
0x1400ab8d3  mov     edx, [rcx]
0x1400ab8d5  mov     eax, [r14+378h]
0x1400ab8dc  mov     ecx, [rcx]
0x1400ab8de  mov     [rsp+0B8h+var_48], edx
0x1400ab8e2  and     ecx, 400h
0x1400ab8e8  mov     [rsp+0B8h+var_50], eax
0x1400ab8ec  mov     eax, [rbx+58h]
0x1400ab8ef  mov     [rsp+0B8h+var_58], eax
0x1400ab8f3  mov     eax, [rbx+3Ch]
0x1400ab8f6  mov     [rsp+0B8h+var_60], eax
0x1400ab8fa  mov     eax, [rbx+38h]
0x1400ab8fd  mov     [rsp+0B8h+var_68], eax
0x1400ab901  mov     eax, [rbx+34h]
0x1400ab904  mov     [rsp+0B8h+var_70], eax
0x1400ab908  mov     eax, [rbx+0Ch]
0x1400ab90b  mov     [rsp+0B8h+var_78], eax
0x1400ab90f  mov     eax, [rbx+60h]
0x1400ab912  mov     [rsp+0B8h+var_80], r12
0x1400ab917  mov     dword ptr [rsp+0B8h+var_88], eax
0x1400ab91b  mov     dword ptr [rsp+0B8h+var_90], ecx
0x1400ab91f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab926  mov     rcx, [rcx+40h]
0x1400ab92a  call    WPP_RECORDER_SF_Dd_MAC_dddddDD
0x1400ab92f  mov     r9, [rdi+14B0h]; void *
0x1400ab936  mov     eax, 38h ; '8'
0x1400ab93b  mov     edx, [rdi+14B8h]; unsigned int
0x1400ab941  mov     r8d, 40030002h; int
0x1400ab947  mov     rcx, [rdi+218h]; this
0x1400ab94e  mov     dword ptr [rsp+0B8h+var_90], eax; unsigned int
0x1400ab952  mov     [rsp+0B8h+var_98], r13; void *
0x1400ab957  mov     byte ptr [r13+0], 80h
0x1400ab95c  mov     byte ptr [rdi+52Dh], 1
0x1400ab963  mov     [rdi+52Eh], ax
0x1400ab96a  call    ?IndicateStatus@CAdapter@@QEAAXKHPEAX0K@Z; CAdapter::IndicateStatus(ulong,int,void *,void *,ulong)
0x1400ab96f  mov     eax, dword ptr [rsp+0B8h+arg_20]
0x1400ab976  mov     r8d, 4003002Ah; int
0x1400ab97c  mov     dword ptr [rbx], 740280h
0x1400ab982  mov     r9, [rdi+14B0h]; void *
0x1400ab989  mov     edx, [rdi+14B8h]; unsigned int
0x1400ab98f  mov     rcx, [rdi+218h]; this
0x1400ab996  mov     dword ptr [rsp+0B8h+var_90], eax; unsigned int
0x1400ab99a  mov     [rsp+0B8h+var_98], rbx; void *
0x1400ab99f  call    ?IndicateStatus@CAdapter@@QEAAXKHPEAX0K@Z; CAdapter::IndicateStatus(ulong,int,void *,void *,ulong)
0x1400ab9a4  xor     edi, edi
0x1400ab9a6  cmp     [rsp+0B8h+arg_0], dil
0x1400ab9ae  jz      short loc_1400AB9B8
0x1400ab9b0  mov     rcx, rbx; void *
0x1400ab9b3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400ab9b8  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400ab9bf  jz      short loc_1400AB9FB
0x1400ab9c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab9c8  cmp     byte ptr [rcx+29h], 5
0x1400ab9cc  jnb     short loc_1400AB9D4
0x1400ab9ce  cmp     [rcx+48h], di
0x1400ab9d2  jz      short loc_1400AB9FB
0x1400ab9d4  mov     rcx, [rcx+40h]
0x1400ab9d8  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400ab9df  mov     r9d, 82h
0x1400ab9e5  mov     dword ptr [rsp+0B8h+var_90], ebp
0x1400ab9e9  mov     r8d, 1
0x1400ab9ef  mov     [rsp+0B8h+var_98], rax
0x1400ab9f4  mov     dl, 5
0x1400ab9f6  call    WPP_RECORDER_SF_d
0x1400ab9fb  mov     rbx, [rsp+0B8h+arg_10]
0x1400aba03  mov     eax, ebp
0x1400aba05  add     rsp, 80h
0x1400aba0c  pop     r15
0x1400aba0e  pop     r14
0x1400aba10  pop     r13
0x1400aba12  pop     r12
0x1400aba14  pop     rdi
0x1400aba15  pop     rsi
0x1400aba16  pop     rbp
0x1400aba17  retn
```
