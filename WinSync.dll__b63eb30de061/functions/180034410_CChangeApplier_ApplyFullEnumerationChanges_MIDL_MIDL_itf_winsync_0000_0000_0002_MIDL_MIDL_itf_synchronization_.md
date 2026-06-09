# CChangeApplier::ApplyFullEnumerationChanges(__MIDL___MIDL_itf_winsync_0000_0000_0002,__MIDL___MIDL_itf_synchronization_0000_0000_0002,ISyncFullEnumerationChangeBatch *,IUnknown *,IEnumSyncChanges *,ISyncKnowledge *,IForgottenKnowledge *,IAsynchronousNotifyingChangeApplierTarget *,IConflictLogAccess *,ISyncSessionState *,ISyncCallback *)

- ea: `0x180034410`
- end: `0x1800345fc`
- name: `?ApplyFullEnumerationChanges@CChangeApplier@@UEAAJW4__MIDL___MIDL_itf_winsync_0000_0000_0002@@W4__MIDL___MIDL_itf_synchronization_0000_0000_0002@@PEAUISyncFullEnumerationChangeBatch@@PEAUIUnknown@@PEAUIEnumSyncChanges@@PEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAUIAsynchronousNotifyingChangeApplierTarget@@PEAUIConflictLogAccess@@PEAUISyncSessionState@@PEAUISyncCallback@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), struct IUnknown *, __int64, __int64, __int64, struct IAsynchronousNotifyingChangeApplierTarget *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x1800331dc`
- `0x180034410`
- `0x18003fe48`
- `0x180094010`

## pseudocode

```c
__int64 __fastcall CChangeApplier::ApplyFullEnumerationChanges(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 (__fastcall ***a4)(_QWORD, GUID *, __int64 *),
        struct IUnknown *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        struct IAsynchronousNotifyingChangeApplierTarget *a9,
        __int64 a10,
        __int64 a11,
        __int64 a12)
{
  PVOID *v16; // rcx
  int v17; // ebx
  CChangeApplier *v18; // rsi
  __int64 v19; // rcx
  _QWORD *v20; // rdi
  __int64 v21; // rcx
  __int64 (__fastcall **v22)(_QWORD, GUID *, __int64 *); // rax
  __int64 v24; // [rsp+98h] [rbp+20h] BYREF

  _InterlockedIncrement(&g_cRefThisDll);
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::ApplyFullEnumerationChanges");
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  v17 = -2147467261;
  if ( a4 )
  {
    v18 = (CChangeApplier *)(a1 - 8);
    v19 = *(_QWORD *)(a1 - 8 + 632);
    if ( v19 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v20 = (_QWORD *)(a1 + 624);
      *v20 = 0;
    }
    else
    {
      v20 = (_QWORD *)(a1 + 624);
    }
    v21 = a10;
    if ( a10 )
    {
      *v20 = a10;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
    }
    v17 = CChangeApplier::Init(v18, a9, a5);
    if ( v17 >= 0 )
    {
      v22 = *a4;
      v24 = 0;
      v17 = (*v22)(a4, &GUID_52f6e694_6a71_4494_a184_a8311bf5d227, &v24);
      if ( v17 >= 0 )
      {
        v17 = CChangeApplier::ApplyChangesHelper(v18, a2, a3, v24, a6, a7, a8, a11, a12, 1);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
    }
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 8) != 0 && *((_BYTE *)v16 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v16[2],
      37,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::ApplyFullEnumerationChanges",
      v17);
  if ( v17 < 0 )
    _InterlockedDecrement(&g_cRefThisDll);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180034410  mov     [rsp+arg_0], rbx
0x180034415  mov     [rsp+arg_8], rbp
0x18003441a  push    rsi
0x18003441b  push    rdi
0x18003441c  push    r12
0x18003441e  push    r14
0x180034420  push    r15
0x180034422  sub     rsp, 50h
0x180034426  mov     r14, r9
0x180034429  mov     ebp, r8d
0x18003442c  mov     r15d, edx
0x18003442f  mov     rdi, rcx
0x180034432  lock inc cs:?g_cRefThisDll@@3JC; long volatile g_cRefThisDll
0x180034439  mov     rcx, cs:WPP_GLOBAL_Control
0x180034440  lea     r12, WPP_GLOBAL_Control
0x180034447  cmp     rcx, r12
0x18003444a  jz      short loc_18003447B
0x18003444c  test    byte ptr [rcx+1Ch], 8
0x180034450  jz      short loc_18003447B
0x180034452  cmp     byte ptr [rcx+19h], 5
0x180034456  jb      short loc_18003447B
0x180034458  mov     rcx, [rcx+10h]
0x18003445c  lea     r9, aCchangeapplier_33; "CChangeApplier::ApplyFullEnumerationCha"...
0x180034463  mov     edx, 24h ; '$'
0x180034468  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003446f  call    WPP_SF_s
0x180034474  mov     rcx, cs:WPP_GLOBAL_Control
0x18003447b  mov     ebx, 80004003h
0x180034480  test    r14, r14
0x180034483  jz      loc_1800345A5
0x180034489  lea     rsi, [rdi-8]
0x18003448d  mov     rcx, [rsi+278h]
0x180034494  test    rcx, rcx
0x180034497  jz      short loc_1800344B5
0x180034499  mov     rax, [rcx]
0x18003449c  mov     rax, [rax+10h]
0x1800344a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344a5  add     rdi, 270h
0x1800344ac  mov     qword ptr [rdi], 0
0x1800344b3  jmp     short loc_1800344BC
0x1800344b5  add     rdi, 270h
0x1800344bc  mov     rcx, [rsp+78h+arg_48]
0x1800344c4  test    rcx, rcx
0x1800344c7  jz      short loc_1800344D8
0x1800344c9  mov     [rdi], rcx
0x1800344cc  mov     rax, [rcx]
0x1800344cf  mov     rax, [rax+8]
0x1800344d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344d8  mov     r8, [rsp+78h+arg_20]; struct IUnknown *
0x1800344e0  mov     rcx, rsi; this
0x1800344e3  mov     rdx, [rsp+78h+arg_40]; struct IAsynchronousNotifyingChangeApplierTarget *
0x1800344eb  call    ?Init@CChangeApplier@@QEAAJPEAUIAsynchronousNotifyingChangeApplierTarget@@PEAUIUnknown@@@Z; CChangeApplier::Init(IAsynchronousNotifyingChangeApplierTarget *,IUnknown *)
0x1800344f0  mov     ebx, eax
0x1800344f2  test    eax, eax
0x1800344f4  js      loc_18003459E
0x1800344fa  mov     rax, [r14]
0x1800344fd  lea     r8, [rsp+78h+arg_18]
0x180034505  lea     rdx, _GUID_52f6e694_6a71_4494_a184_a8311bf5d227
0x18003450c  mov     [rsp+78h+arg_18], 0
0x180034518  mov     rcx, r14
0x18003451b  mov     rax, [rax]
0x18003451e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034523  mov     ebx, eax
0x180034525  test    eax, eax
0x180034527  js      short loc_18003459E
0x180034529  mov     rax, [rsp+78h+arg_58]
0x180034531  mov     r8d, ebp
0x180034534  mov     r9, [rsp+78h+arg_18]
0x18003453c  mov     edx, r15d
0x18003453f  mov     [rsp+78h+var_30], 1
0x180034547  mov     rcx, rsi
0x18003454a  mov     [rsp+78h+var_38], rax
0x18003454f  mov     rax, [rsp+78h+arg_50]
0x180034557  mov     [rsp+78h+var_40], rax
0x18003455c  mov     rax, [rsp+78h+arg_38]
0x180034564  mov     [rsp+78h+var_48], rax
0x180034569  mov     rax, [rsp+78h+arg_30]
0x180034571  mov     [rsp+78h+var_50], rax
0x180034576  mov     rax, [rsp+78h+arg_28]
0x18003457e  mov     [rsp+78h+var_58], rax
0x180034583  call    ?ApplyChangesHelper@CChangeApplier@@AEAAJW4__MIDL___MIDL_itf_winsync_0000_0000_0002@@W4__MIDL___MIDL_itf_synchronization_0000_0000_0002@@PEAUISyncChangeBatchBase@@PEAUIEnumSyncChanges@@PEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAUISyncSessionState@@PEAUISyncCallback@@H@Z; CChangeApplier::ApplyChangesHelper(__MIDL___MIDL_itf_winsync_0000_0000_0002,__MIDL___MIDL_itf_synchronization_0000_0000_0002,ISyncChangeBatchBase *,IEnumSyncChanges *,ISyncKnowledge *,IForgottenKnowledge *,ISyncSessionState *,ISyncCallback *,int)
0x180034588  mov     rcx, [rsp+78h+arg_18]
0x180034590  mov     ebx, eax
0x180034592  mov     rax, [rcx]
0x180034595  mov     rax, [rax+10h]
0x180034599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003459e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800345a5  cmp     rcx, r12
0x1800345a8  jz      short loc_1800345D6
0x1800345aa  test    byte ptr [rcx+1Ch], 8
0x1800345ae  jz      short loc_1800345D6
0x1800345b0  cmp     byte ptr [rcx+19h], 5
0x1800345b4  jb      short loc_1800345D6
0x1800345b6  mov     rcx, [rcx+10h]
0x1800345ba  lea     r9, aCchangeapplier_33; "CChangeApplier::ApplyFullEnumerationCha"...
0x1800345c1  mov     edx, 25h ; '%'
0x1800345c6  mov     dword ptr [rsp+78h+var_58], ebx
0x1800345ca  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800345d1  call    WPP_SF_sD
0x1800345d6  test    ebx, ebx
0x1800345d8  jns     short loc_1800345E1
0x1800345da  lock dec cs:?g_cRefThisDll@@3JC; long volatile g_cRefThisDll
0x1800345e1  lea     r11, [rsp+78h+var_28]
0x1800345e6  mov     eax, ebx
0x1800345e8  mov     rbx, [r11+30h]
0x1800345ec  mov     rbp, [r11+38h]
0x1800345f0  mov     rsp, r11
0x1800345f3  pop     r15
0x1800345f5  pop     r14
0x1800345f7  pop     r12
0x1800345f9  pop     rdi
0x1800345fa  pop     rsi
0x1800345fb  retn
```
