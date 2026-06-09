# CChangeApplier::ApplyFullEnumerationChanges(__MIDL___MIDL_itf_winsync_0000_0000_0002,__MIDL___MIDL_itf_synchronization_0000_0000_0002,ISyncFullEnumerationChangeBatch *,IUnknown *,IEnumSyncChanges *,ISyncKnowledge *,IForgottenKnowledge *,ISynchronousNotifyingChangeApplierTarget *,IConflictLogAccess *,ISyncSessionState *,ISyncCallback *)

- ea: `0x180034610`
- end: `0x1800347d7`
- name: `?ApplyFullEnumerationChanges@CChangeApplier@@UEAAJW4__MIDL___MIDL_itf_winsync_0000_0000_0002@@W4__MIDL___MIDL_itf_synchronization_0000_0000_0002@@PEAUISyncFullEnumerationChangeBatch@@PEAUIUnknown@@PEAUIEnumSyncChanges@@PEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAUISynchronousNotifyingChangeApplierTarget@@PEAUIConflictLogAccess@@PEAUISyncSessionState@@PEAUISyncCallback@@@Z`
- size: `455`
- prototype: `__int64 __fastcall(CChangeApplier *, unsigned int, unsigned int, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), struct IUnknown *, __int64, __int64, __int64, struct ISynchronousNotifyingChangeApplierTarget *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x1800331dc`
- `0x180034610`
- `0x18004008c`
- `0x180094010`

## pseudocode

```c
__int64 __fastcall CChangeApplier::ApplyFullEnumerationChanges(
        CChangeApplier *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 (__fastcall ***a4)(_QWORD, GUID *, __int64 *),
        struct IUnknown *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        struct ISynchronousNotifyingChangeApplierTarget *a9,
        __int64 a10,
        __int64 a11,
        __int64 a12)
{
  PVOID *v16; // rcx
  int v17; // ebx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 (__fastcall **v20)(_QWORD, GUID *, __int64 *); // rax
  __int64 v22; // [rsp+A8h] [rbp+20h] BYREF

  _InterlockedIncrement(&g_cRefThisDll);
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::ApplyFullEnumerationChanges");
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  v17 = -2147467261;
  if ( a4 )
  {
    v18 = *((_QWORD *)a1 + 79);
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      *((_QWORD *)a1 + 79) = 0;
    }
    v19 = a10;
    if ( a10 )
    {
      *((_QWORD *)a1 + 79) = a10;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
    }
    v17 = CChangeApplier::Init(a1, a9, a5);
    if ( v17 >= 0 )
    {
      v20 = *a4;
      v22 = 0;
      v17 = (*v20)(a4, &GUID_52f6e694_6a71_4494_a184_a8311bf5d227, &v22);
      if ( v17 >= 0 )
      {
        v17 = CChangeApplier::ApplyChangesHelper(a1, a2, a3, v22, a6, a7, a8, a11, a12, 1);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
    }
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 8) != 0 && *((_BYTE *)v16 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v16[2],
      33,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::ApplyFullEnumerationChanges",
      v17);
  _InterlockedDecrement(&g_cRefThisDll);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180034610  push    rbx
0x180034612  push    rbp
0x180034613  push    rsi
0x180034614  push    rdi
0x180034615  push    r14
0x180034617  push    r15
0x180034619  sub     rsp, 58h
0x18003461d  mov     rsi, r9
0x180034620  mov     ebp, r8d
0x180034623  mov     r14d, edx
0x180034626  mov     rdi, rcx
0x180034629  lock inc cs:?g_cRefThisDll@@3JC; long volatile g_cRefThisDll
0x180034630  mov     rcx, cs:WPP_GLOBAL_Control
0x180034637  lea     r15, WPP_GLOBAL_Control
0x18003463e  cmp     rcx, r15
0x180034641  jz      short loc_180034672
0x180034643  test    byte ptr [rcx+1Ch], 8
0x180034647  jz      short loc_180034672
0x180034649  cmp     byte ptr [rcx+19h], 5
0x18003464d  jb      short loc_180034672
0x18003464f  mov     rcx, [rcx+10h]
0x180034653  lea     r9, aCchangeapplier_33; "CChangeApplier::ApplyFullEnumerationCha"...
0x18003465a  mov     edx, 20h ; ' '
0x18003465f  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180034666  call    WPP_SF_s
0x18003466b  mov     rcx, cs:WPP_GLOBAL_Control
0x180034672  mov     ebx, 80004003h
0x180034677  test    rsi, rsi
0x18003467a  jz      loc_180034790
0x180034680  mov     rcx, [rdi+278h]
0x180034687  test    rcx, rcx
0x18003468a  jz      short loc_1800346A3
0x18003468c  mov     rax, [rcx]
0x18003468f  mov     rax, [rax+10h]
0x180034693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034698  mov     qword ptr [rdi+278h], 0
0x1800346a3  mov     rcx, [rsp+88h+arg_48]
0x1800346ab  test    rcx, rcx
0x1800346ae  jz      short loc_1800346C3
0x1800346b0  mov     [rdi+278h], rcx
0x1800346b7  mov     rax, [rcx]
0x1800346ba  mov     rax, [rax+8]
0x1800346be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800346c3  mov     r8, [rsp+88h+arg_20]; struct IUnknown *
0x1800346cb  mov     rcx, rdi; this
0x1800346ce  mov     rdx, [rsp+88h+arg_40]; struct ISynchronousNotifyingChangeApplierTarget *
0x1800346d6  call    ?Init@CChangeApplier@@QEAAJPEAUISynchronousNotifyingChangeApplierTarget@@PEAUIUnknown@@@Z; CChangeApplier::Init(ISynchronousNotifyingChangeApplierTarget *,IUnknown *)
0x1800346db  mov     ebx, eax
0x1800346dd  test    eax, eax
0x1800346df  js      loc_180034789
0x1800346e5  mov     rax, [rsi]
0x1800346e8  lea     r8, [rsp+88h+arg_18]
0x1800346f0  lea     rdx, _GUID_52f6e694_6a71_4494_a184_a8311bf5d227
0x1800346f7  mov     [rsp+88h+arg_18], 0
0x180034703  mov     rcx, rsi
0x180034706  mov     rax, [rax]
0x180034709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003470e  mov     ebx, eax
0x180034710  test    eax, eax
0x180034712  js      short loc_180034789
0x180034714  mov     rax, [rsp+88h+arg_58]
0x18003471c  mov     r8d, ebp
0x18003471f  mov     r9, [rsp+88h+arg_18]
0x180034727  mov     edx, r14d
0x18003472a  mov     [rsp+88h+var_40], 1
0x180034732  mov     rcx, rdi
0x180034735  mov     [rsp+88h+var_48], rax
0x18003473a  mov     rax, [rsp+88h+arg_50]
0x180034742  mov     [rsp+88h+var_50], rax
0x180034747  mov     rax, [rsp+88h+arg_38]
0x18003474f  mov     [rsp+88h+var_58], rax
0x180034754  mov     rax, [rsp+88h+arg_30]
0x18003475c  mov     [rsp+88h+var_60], rax
0x180034761  mov     rax, [rsp+88h+arg_28]
0x180034769  mov     [rsp+88h+var_68], rax
0x18003476e  call    ?ApplyChangesHelper@CChangeApplier@@AEAAJW4__MIDL___MIDL_itf_winsync_0000_0000_0002@@W4__MIDL___MIDL_itf_synchronization_0000_0000_0002@@PEAUISyncChangeBatchBase@@PEAUIEnumSyncChanges@@PEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAUISyncSessionState@@PEAUISyncCallback@@H@Z; CChangeApplier::ApplyChangesHelper(__MIDL___MIDL_itf_winsync_0000_0000_0002,__MIDL___MIDL_itf_synchronization_0000_0000_0002,ISyncChangeBatchBase *,IEnumSyncChanges *,ISyncKnowledge *,IForgottenKnowledge *,ISyncSessionState *,ISyncCallback *,int)
0x180034773  mov     rcx, [rsp+88h+arg_18]
0x18003477b  mov     ebx, eax
0x18003477d  mov     rax, [rcx]
0x180034780  mov     rax, [rax+10h]
0x180034784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034789  mov     rcx, cs:WPP_GLOBAL_Control
0x180034790  cmp     rcx, r15
0x180034793  jz      short loc_1800347C1
0x180034795  test    byte ptr [rcx+1Ch], 8
0x180034799  jz      short loc_1800347C1
0x18003479b  cmp     byte ptr [rcx+19h], 5
0x18003479f  jb      short loc_1800347C1
0x1800347a1  mov     rcx, [rcx+10h]
0x1800347a5  lea     r9, aCchangeapplier_33; "CChangeApplier::ApplyFullEnumerationCha"...
0x1800347ac  mov     edx, 21h ; '!'
0x1800347b1  mov     dword ptr [rsp+88h+var_68], ebx
0x1800347b5  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800347bc  call    WPP_SF_sD
0x1800347c1  lock dec cs:?g_cRefThisDll@@3JC; long volatile g_cRefThisDll
0x1800347c8  mov     eax, ebx
0x1800347ca  add     rsp, 58h
0x1800347ce  pop     r15
0x1800347d0  pop     r14
0x1800347d2  pop     rdi
0x1800347d3  pop     rsi
0x1800347d4  pop     rbp
0x1800347d5  pop     rbx
0x1800347d6  retn
```
