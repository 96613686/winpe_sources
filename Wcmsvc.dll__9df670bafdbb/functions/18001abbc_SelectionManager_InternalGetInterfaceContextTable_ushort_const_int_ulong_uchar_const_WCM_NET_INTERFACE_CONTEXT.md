# SelectionManager::InternalGetInterfaceContextTable(ushort const *,int,ulong,uchar const *,_WCM_NET_INTERFACE_CONTEXT_TABLE * *,void * *)

- ea: `0x18001abbc`
- end: `0x18001b2a7`
- name: `?InternalGetInterfaceContextTable@SelectionManager@@IEAAJPEBGHKPEBEPEAPEAU_WCM_NET_INTERFACE_CONTEXT_TABLE@@PEAPEAX@Z`
- size: `1771`
- prototype: `__int64 __fastcall(SelectionManager *__hidden this, const unsigned __int16 *, int, unsigned int, const unsigned __int8 *, struct _WCM_NET_INTERFACE_CONTEXT_TABLE **, void **)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18001aa10`

## callees

- `0x18000e970`
- `0x180011bb0`
- `0x180011c20`
- `0x1800137a0`
- `0x180019434`
- `0x1800199f8`
- `0x18001abbc`
- `0x18001b2b0`
- `0x18001c11c`
- `0x18001c254`
- `0x18001c288`
- `0x180027660`
- `0x18002b300`
- `0x180036c30`
- `0x18004bdb4`
- `0x18006c2c0`
- `0x18007015c`
- `0x18007084c`
- `0x180084f34`
- `0x180084f50`
- `0x180085bc4`
- `0x180087ab8`
- `0x180089ee0`
- `0x1800ccfc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ae68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ae68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aec1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aec1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001ae34`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001ae34`

## string_xrefs

- `0x18001b1cf`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001ac9d`: `onecoreuap\net\wcm\service\base\selection\lib\selectionmanager.cpp`
- `0x18001b044`: `onecoreuap\net\wcm\service\base\selection\lib\selectionmanager.cpp`
- `0x18001b108`: `onecoreuap\net\wcm\service\base\selection\lib\selectionmanager.cpp`
- `0x18001b120`: `onecoreuap\net\wcm\service\base\selection\lib\selectionmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SelectionManager::InternalGetInterfaceContextTable(
        SelectionManager *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5,
        struct _WCM_NET_INTERFACE_CONTEXT_TABLE **a6,
        void **a7)
{
  unsigned __int16 *v9; // rbx
  SelectionManager *v10; // r15
  int SelectableConnectionList; // eax
  struct _WCM_NET_INTERFACE_CONTEXT_TABLE *v12; // rax
  const char *v13; // r9
  struct _WCM_SELECTABLE_CONNECTION_LIST *v14; // rcx
  char v16; // si
  __int64 v17; // rcx
  __int64 v18; // rbx
  void *v19; // rax
  const char *v20; // r9
  __int64 v21; // r8
  unsigned int v22; // edi
  struct _WCM_SELECTABLE_CONNECTION_LIST *v23; // rbx
  DWORD v24; // eax
  const char *v25; // r9
  signed int v26; // ebx
  char *v27; // r11
  __int64 v28; // rbx
  char *v29; // r14
  wil::details::in1diag3 *v30; // r10
  __int64 v31; // r11
  __int64 v32; // rax
  int v33; // r11d
  __int64 v34; // r8
  const char *v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rcx
  int v38; // [rsp+20h] [rbp-81h]
  _QWORD v39[2]; // [rsp+40h] [rbp-61h] BYREF
  char v40; // [rsp+50h] [rbp-51h]
  char *v41; // [rsp+58h] [rbp-49h]
  struct _WCM_SELECTABLE_CONNECTION_LIST **v42; // [rsp+60h] [rbp-41h]
  char v43; // [rsp+68h] [rbp-39h]
  struct _WCM_SELECTABLE_CONNECTION_LIST *v44; // [rsp+70h] [rbp-31h] BYREF
  void *Block; // [rsp+78h] [rbp-29h] BYREF
  HANDLE hHandle; // [rsp+80h] [rbp-21h] BYREF
  __int64 v47; // [rsp+88h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+47h]

  v9 = a2;
  v10 = this;
  v39[0] = this;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      29,
      WPP_1e598accbd0633246e27c279a8537074_Traceguids,
      "SelectionManager::InternalGetInterfaceContextTable");
  }
  *a6 = 0;
  *a7 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v35 = "a selection filter";
    if ( !a5 )
      v35 = "no selection filter";
    LOBYTE(a2) = a3 != 0;
    WPP_SF_SsDc(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      (_DWORD)a2,
      (unsigned int)"no selection filter",
      (_DWORD)v9,
      (__int64)v35,
      a4,
      a3 != 0);
  }
  v44 = 0;
  SelectableConnectionList = SelectionManager::InternalGetSelectableConnectionList(v10, v9, a5, a4, 0, a3, &v44);
  if ( SelectableConnectionList < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x34C,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\selection\\lib\\selectionmanager.cpp",
      (const char *)(unsigned int)SelectableConnectionList,
      v38);
  v42 = &v44;
  v43 = 1;
  if ( SelectableConnectionList == 1 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 31, WPP_1e598accbd0633246e27c279a8537074_Traceguids);
    }
    v12 = (struct _WCM_NET_INTERFACE_CONTEXT_TABLE *)MIDL_user_allocate(0x208u);
    if ( !v12 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x360,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\selection\\lib\\selectionmanager.cpp",
        v13);
    *(_QWORD *)v12 = 0;
    *((_WORD *)v12 + 4) = 0;
    *a6 = v12;
    *a7 = 0;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_sL(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        32,
        (unsigned int)WPP_1e598accbd0633246e27c279a8537074_Traceguids,
        (unsigned int)"SelectionManager::InternalGetInterfaceContextTable",
        0);
    }
    goto LABEL_12;
  }
  v16 = 1;
  if ( SelectableConnectionList == 2 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 33, WPP_1e598accbd0633246e27c279a8537074_Traceguids);
      v17 = WPP_GLOBAL_Control;
    }
    v16 = 0;
  }
  else
  {
    v17 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v17 != &WPP_GLOBAL_Control && *(_BYTE *)(v17 + 25) >= 4u && (*(_BYTE *)(v17 + 28) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(v17 + 16), 34, WPP_1e598accbd0633246e27c279a8537074_Traceguids, *(unsigned int *)v44);
  v18 = 516LL * (unsigned int)(*(_DWORD *)v44 - 1);
  v19 = MIDL_user_allocate(v18 + 520);
  Block = v19;
  if ( !v19 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x37D,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\selection\\lib\\selectionmanager.cpp",
      v20);
  v39[1] = &Block;
  v40 = 1;
  memset_0(v19, 0, v18 + 520);
  *(_DWORD *)Block = *(_DWORD *)v44;
  v22 = 0;
  v23 = v44;
  if ( *(_DWORD *)v44 )
  {
    do
    {
      v27 = (char *)v23 + 1108 * v22;
      v28 = 516LL * v22;
      v29 = (char *)Block;
      *(_DWORD *)((char *)Block + v28 + 4) = *((_DWORD *)v27 + 5);
      if ( (int)StringCchCopyW((unsigned __int16 *)&v29[v28 + 8], 0x100u, (const unsigned __int16 *)v27 + 300) < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          v30,
          (void *)0x392,
          (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\selection\\lib\\selectionmanager.cpp",
          (const char *)0x8000FFFFLL,
          v38);
      v21 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v32 = EnumToString(*(unsigned int *)(v31 + 24));
        WPP_SF__guid_sDS(
          *(_QWORD *)(v34 + 16),
          *(_DWORD *)&v29[v28 + 4],
          v34,
          v33 + 4,
          v32,
          *(_DWORD *)&v29[v28 + 4],
          (__int64)&v29[v28 + 8]);
      }
      ++v22;
      v23 = v44;
    }
    while ( v22 < *(_DWORD *)v44 );
    v10 = (SelectionManager *)v39[0];
  }
  if ( !v16 )
  {
    *a6 = (struct _WCM_NET_INTERFACE_CONTEXT_TABLE *)Block;
    *a7 = 0;
    v36 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 36, WPP_1e598accbd0633246e27c279a8537074_Traceguids);
        v23 = v44;
        v36 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v36 != &WPP_GLOBAL_Control && *(_BYTE *)(v36 + 25) >= 5u && (*(_BYTE *)(v36 + 28) & 1) != 0 )
      {
        WPP_SF_sL(
          *(_QWORD *)(v36 + 16),
          37,
          (unsigned int)WPP_1e598accbd0633246e27c279a8537074_Traceguids,
          (unsigned int)"SelectionManager::InternalGetInterfaceContextTable",
          0);
        v23 = v44;
      }
    }
    if ( !v23 )
      return 0;
    v14 = v23;
    goto LABEL_44;
  }
  LODWORD(v39[0]) = *((_DWORD *)v23 + 7);
  hHandle = 0;
  v47 = 0;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (wil::details **)&hHandle,
    0,
    v21);
  SelectionManager::InternalAcquireSelectableConnectionAsync(
    v10,
    v39[0],
    &hHandle,
    SelectionManager::InternalGetInterfaceContextTable_::_2_::_lambda_3_::_lambda_invoker_cdecl_);
  v24 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
  if ( v24 != 258 && v24 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB0F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v25);
  v26 = v47;
  if ( !(_DWORD)v47 )
  {
    *((_DWORD *)Block + 1) = HIDWORD(v47);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v10 + 168));
    v41 = (char *)v10 + 168;
    std::vector<InterfaceLifetimeTracking>::emplace_back<unsigned long &>((char *)v10 + 208, v39);
    v40 = 0;
    *a6 = (struct _WCM_NET_INTERFACE_CONTEXT_TABLE *)Block;
    *a7 = InterfaceLifetimeTracking::GetEvent((InterfaceLifetimeTracking *)(*((_QWORD *)v10 + 27) - 24LL));
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_sL(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        40,
        (unsigned int)WPP_1e598accbd0633246e27c279a8537074_Traceguids,
        (unsigned int)"SelectionManager::InternalGetInterfaceContextTable",
        0);
    }
    if ( v10 != (SelectionManager *)-168LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v10 + 168));
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
LABEL_12:
    v14 = v44;
    if ( !v44 )
      return 0;
LABEL_44:
    operator delete(v14);
    return 0;
  }
  v37 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_S_guid_D(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        38,
        (unsigned int)WPP_1e598accbd0633246e27c279a8537074_Traceguids,
        (_DWORD)v44 + 600,
        (__int64)v44 + 4,
        v47);
      v26 = v47;
      v37 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v37 != &WPP_GLOBAL_Control && *(_BYTE *)(v37 + 25) >= 5u && (*(_BYTE *)(v37 + 28) & 1) != 0 )
    {
      WPP_SF_sL(
        *(_QWORD *)(v37 + 16),
        39,
        (unsigned int)WPP_1e598accbd0633246e27c279a8537074_Traceguids,
        (unsigned int)"SelectionManager::InternalGetInterfaceContextTable",
        v26);
      v26 = v47;
    }
  }
  if ( v26 > 0 )
    v26 = (unsigned __int16)v26 | 0x80070000;
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
  operator delete(Block);
  if ( v44 )
    operator delete(v44);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x18001abbc  push    rbp
0x18001abbe  push    rbx
0x18001abbf  push    rsi
0x18001abc0  push    rdi
0x18001abc1  push    r12
0x18001abc3  push    r13
0x18001abc5  push    r14
0x18001abc7  push    r15
0x18001abc9  lea     rbp, [rsp-7]
0x18001abce  sub     rsp, 0A8h
0x18001abd5  mov     rax, cs:__security_cookie
0x18001abdc  xor     rax, rsp
0x18001abdf  mov     [rbp+3Fh+var_50], rax
0x18001abe3  mov     esi, r9d
0x18001abe6  mov     edi, r8d
0x18001abe9  mov     rbx, rdx
0x18001abec  mov     r15, rcx
0x18001abef  mov     [rbp+3Fh+var_A0], rcx
0x18001abf3  mov     r14, [rbp+3Fh+arg_20]
0x18001abf7  mov     r12, [rbp+3Fh+arg_28]
0x18001abfb  mov     r13, [rbp+3Fh+arg_30]
0x18001abff  lea     rax, WPP_GLOBAL_Control
0x18001ac06  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac0d  cmp     rcx, rax
0x18001ac10  jz      short loc_18001AC41
0x18001ac12  cmp     byte ptr [rcx+19h], 5
0x18001ac16  jb      short loc_18001AC41
0x18001ac18  test    byte ptr [rcx+1Ch], 1
0x18001ac1c  jz      short loc_18001AC41
0x18001ac1e  mov     edx, 1Dh
0x18001ac23  lea     r9, aSelectionmanag; "SelectionManager::InternalGetInterfaceC"...
0x18001ac2a  lea     r8, WPP_1e598accbd0633246e27c279a8537074_Traceguids
0x18001ac31  mov     rcx, [rcx+10h]
0x18001ac35  call    WPP_SF_s
0x18001ac3a  lea     rax, WPP_GLOBAL_Control
0x18001ac41  mov     qword ptr [r12], 0
0x18001ac49  mov     qword ptr [r13+0], 0
0x18001ac51  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac58  cmp     rcx, rax
0x18001ac5b  jnz     loc_18001AFF8
0x18001ac61  mov     [rbp+3Fh+var_70], 0
0x18001ac69  lea     rax, [rbp+3Fh+var_70]
0x18001ac6d  mov     [rsp+0E0h+var_B0], rax; struct _WCM_SELECTABLE_CONNECTION_LIST **
0x18001ac72  mov     [rsp+0E0h+var_B8], edi; int
0x18001ac76  mov     [rsp+0E0h+var_C0], 0; int
0x18001ac7e  mov     r9d, esi; unsigned int
0x18001ac81  mov     r8, r14; unsigned __int8 *
0x18001ac84  mov     rdx, rbx; unsigned __int16 *
0x18001ac87  mov     rcx, r15; this
0x18001ac8a  call    ?InternalGetSelectableConnectionList@SelectionManager@@IEAAJPEBGPEBEKHHPEAPEAU_WCM_SELECTABLE_CONNECTION_LIST@@@Z; SelectionManager::InternalGetSelectableConnectionList(ushort const *,uchar const *,ulong,int,int,_WCM_SELECTABLE_CONNECTION_LIST * *)
0x18001ac8f  mov     rcx, [rbp+47h]; this
0x18001ac93  xor     r14d, r14d
0x18001ac96  test    eax, eax
0x18001ac98  jns     short loc_18001ACAF
0x18001ac9a  mov     r9d, eax; char *
0x18001ac9d  lea     r8, aOnecoreuapNetW_26; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18001aca4  mov     edx, 34Ch; void *
0x18001aca9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001acaf  lea     rcx, [rbp+3Fh+var_70]
0x18001acb3  mov     [rbp+3Fh+var_80], rcx
0x18001acb7  mov     edi, 1
0x18001acbc  mov     [rbp+3Fh+var_78], dil
0x18001acc0  cmp     eax, edi
0x18001acc2  jnz     loc_18001AD67
0x18001acc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001accf  lea     rbx, WPP_GLOBAL_Control
0x18001acd6  cmp     rcx, rbx
0x18001acd9  jnz     short loc_18001AD41
0x18001acdb  mov     ecx, 208h; size
0x18001ace0  call    MIDL_user_allocate
0x18001ace5  mov     rcx, [rbp+47h]; this
0x18001ace9  test    rax, rax
0x18001acec  jz      loc_18001B044
0x18001acf2  mov     [rax], r14
0x18001acf5  mov     [rax+8], r14w
0x18001acfa  mov     [r12], rax
0x18001acfe  mov     [r13+0], r14
0x18001ad02  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad09  cmp     rcx, rbx
0x18001ad0c  jnz     loc_18001B056
0x18001ad12  mov     rcx, [rbp+3Fh+var_70]
0x18001ad16  test    rcx, rcx
0x18001ad19  jnz     loc_18001AFEE
0x18001ad1f  xor     eax, eax
0x18001ad21  mov     rcx, [rbp+3Fh+var_50]
0x18001ad25  xor     rcx, rsp; StackCookie
0x18001ad28  call    __security_check_cookie
0x18001ad2d  add     rsp, 0A8h
0x18001ad34  pop     r15
0x18001ad36  pop     r14
0x18001ad38  pop     r13
0x18001ad3a  pop     r12
0x18001ad3c  pop     rdi
0x18001ad3d  pop     rsi
0x18001ad3e  pop     rbx
0x18001ad3f  pop     rbp
0x18001ad40  retn
0x18001ad41  cmp     byte ptr [rcx+19h], 4
0x18001ad45  jb      short loc_18001ACDB
0x18001ad47  test    [rcx+1Ch], dil
0x18001ad4b  jz      short loc_18001ACDB
0x18001ad4d  mov     edx, 1Fh
0x18001ad52  lea     r8, WPP_1e598accbd0633246e27c279a8537074_Traceguids
0x18001ad59  mov     rcx, [rcx+10h]
0x18001ad5d  call    WPP_SF_
0x18001ad62  jmp     loc_18001ACDB
0x18001ad67  mov     sil, dil
0x18001ad6a  cmp     eax, 2
0x18001ad6d  jz      loc_18001B090
0x18001ad73  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad7a  lea     rbx, WPP_GLOBAL_Control
0x18001ad81  cmp     rcx, rbx
0x18001ad84  jnz     loc_18001B0D3
0x18001ad8a  mov     rax, [rbp+3Fh+var_70]
0x18001ad8e  mov     eax, [rax]
0x18001ad90  sub     eax, edi
0x18001ad92  imul    rbx, rax, 204h
0x18001ad99  lea     rcx, [rbx+208h]; size
0x18001ada0  call    MIDL_user_allocate
0x18001ada5  mov     [rbp+3Fh+Block], rax
0x18001ada9  mov     rcx, [rbp+47h]; this
0x18001adad  test    rax, rax
0x18001adb0  jz      loc_18001B108
0x18001adb6  lea     rcx, [rbp+3Fh+Block]
0x18001adba  mov     [rbp+3Fh+var_98], rcx
0x18001adbe  mov     [rbp+3Fh+var_90], dil
0x18001adc2  lea     r8, [rbx+208h]; Size
0x18001adc9  xor     edx, edx; Val
0x18001adcb  mov     rcx, rax; void *
0x18001adce  call    memset_0
0x18001add3  mov     rax, [rbp+3Fh+var_70]
0x18001add7  mov     ecx, [rax]
0x18001add9  mov     rax, [rbp+3Fh+Block]
0x18001addd  mov     [rax], ecx
0x18001addf  mov     edi, r14d
0x18001ade2  mov     rbx, [rbp+3Fh+var_70]
0x18001ade6  cmp     [rbx], r14d
0x18001ade9  ja      loc_18001AF34
0x18001adef  test    sil, sil
0x18001adf2  jz      loc_18001B135
0x18001adf8  mov     ebx, [rbx+1Ch]
0x18001adfb  mov     dword ptr [rbp+3Fh+var_A0], ebx
0x18001adfe  mov     [rbp+3Fh+hHandle], r14
0x18001ae02  mov     [rbp+3Fh+var_58], 0
0x18001ae0a  xor     edx, edx
0x18001ae0c  lea     rcx, [rbp+3Fh+hHandle]
0x18001ae10  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001ae15  lea     r9, _SelectionManager__InternalGetInterfaceContextTable____2____lambda_3____lambda_invoker_cdecl_; void (*)(void *, unsigned int, unsigned int)
0x18001ae1c  lea     r8, [rbp+3Fh+hHandle]; void *
0x18001ae20  mov     edx, ebx; unsigned int
0x18001ae22  mov     rcx, r15; this
0x18001ae25  call    ?InternalAcquireSelectableConnectionAsync@SelectionManager@@IEAAXKPEAXP6AX0KK@Z@Z; SelectionManager::InternalAcquireSelectableConnectionAsync(ulong,void *,void (*)(void *,ulong,ulong))
0x18001ae2a  xor     r8d, r8d; bAlertable
0x18001ae2d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001ae30  mov     rcx, [rbp+3Fh+hHandle]; hHandle
0x18001ae34  call    cs:__imp_WaitForSingleObjectEx
0x18001ae3a  cmp     eax, 102h
0x18001ae3f  jz      short loc_18001AE49
0x18001ae41  test    eax, eax
0x18001ae43  jnz     loc_18001B1CB
0x18001ae49  mov     ebx, dword ptr [rbp+3Fh+var_58]
0x18001ae4c  test    ebx, ebx
0x18001ae4e  jnz     loc_18001B1E1
0x18001ae54  mov     rcx, [rbp+3Fh+Block]
0x18001ae58  mov     eax, dword ptr [rbp+3Fh+var_58+4]
0x18001ae5b  mov     [rcx+4], eax
0x18001ae5e  lea     rbx, [r15+0A8h]
0x18001ae65  mov     rcx, rbx; lpCriticalSection
0x18001ae68  call    cs:__imp_EnterCriticalSection
0x18001ae6e  mov     [rbp+3Fh+var_88], rbx
0x18001ae72  lea     rcx, [r15+0D0h]
0x18001ae79  lea     rdx, [rbp+3Fh+var_A0]
0x18001ae7d  call    ??$emplace_back@AEAK@?$vector@VInterfaceLifetimeTracking@@V?$allocator@VInterfaceLifetimeTracking@@@std@@@std@@QEAAAEAVInterfaceLifetimeTracking@@AEAK@Z; std::vector<InterfaceLifetimeTracking>::emplace_back<ulong &>(ulong &)
0x18001ae82  mov     [rbp+3Fh+var_90], r14b
0x18001ae86  mov     rax, [rbp+3Fh+Block]
0x18001ae8a  mov     [r12], rax
0x18001ae8e  mov     rcx, [r15+0D8h]
0x18001ae95  sub     rcx, 18h; this
0x18001ae99  call    ?GetEvent@InterfaceLifetimeTracking@@QEBAPEAXXZ; InterfaceLifetimeTracking::GetEvent(void)
0x18001ae9e  mov     [r13+0], rax
0x18001aea2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aea9  lea     rax, WPP_GLOBAL_Control
0x18001aeb0  cmp     rcx, rax
0x18001aeb3  jnz     loc_18001B26C
0x18001aeb9  test    rbx, rbx
0x18001aebc  jz      short loc_18001AEC8
0x18001aebe  mov     rcx, rbx; lpCriticalSection
0x18001aec1  call    cs:__imp_LeaveCriticalSection
0x18001aec7  nop
0x18001aec8  lea     rcx, [rbp+3Fh+hHandle]
0x18001aecc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001aed1  nop
0x18001aed2  jmp     loc_18001AD12
0x18001aed7  test    ebx, ebx
0x18001aed9  jle     short loc_18001AEE0
0x18001aedb  movzx   ebx, bx
0x18001aede  or      ebx, esi
0x18001aee0  mov     edx, 27h ; '''
0x18001aee5  mov     [rsp+0E0h+var_C0], ebx
0x18001aee9  lea     r9, aSelectionmanag; "SelectionManager::InternalGetInterfaceC"...
0x18001aef0  lea     r8, WPP_1e598accbd0633246e27c279a8537074_Traceguids
0x18001aef7  mov     rcx, [rcx+10h]
0x18001aefb  call    WPP_SF_sL
0x18001af00  mov     ebx, dword ptr [rbp+3Fh+var_58]
0x18001af03  test    ebx, ebx
0x18001af05  jle     short loc_18001AF0C
0x18001af07  movzx   ebx, bx
0x18001af0a  or      ebx, esi
0x18001af0c  lea     rcx, [rbp+3Fh+hHandle]
0x18001af10  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001af15  nop
0x18001af16  mov     rcx, [rbp+3Fh+Block]; Block
0x18001af1a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001af1f  nop
0x18001af20  mov     rcx, [rbp+3Fh+var_70]; Block
0x18001af24  test    rcx, rcx
0x18001af27  jnz     loc_18001B262
0x18001af2d  mov     eax, ebx
0x18001af2f  jmp     loc_18001AD21
0x18001af34  mov     ecx, edi
0x18001af36  imul    r11, rcx, 454h
0x18001af3d  add     r11, rbx
0x18001af40  imul    rbx, rcx, 204h
0x18001af47  mov     r14, [rbp+3Fh+Block]
0x18001af4b  mov     eax, [r11+14h]
0x18001af4f  mov     [rbx+r14+4], eax
0x18001af54  lea     r15, [r14+8]
0x18001af58  add     r15, rbx
0x18001af5b  mov     r10, [rbp+47h]
0x18001af5f  lea     r8, [r11+258h]; unsigned __int16 *
0x18001af66  mov     edx, 100h; unsigned __int64
0x18001af6b  mov     rcx, r15; unsigned __int16 *
0x18001af6e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001af73  shr     eax, 1Fh
0x18001af76  xor     al, 1
0x18001af78  jz      loc_18001B11A
0x18001af7e  mov     r8, cs:WPP_GLOBAL_Control
0x18001af85  lea     rax, WPP_GLOBAL_Control
0x18001af8c  cmp     r8, rax
0x18001af8f  jz      short loc_18001AFC8
0x18001af91  cmp     byte ptr [r8+19h], 4
0x18001af96  jb      short loc_18001AFC8
0x18001af98  test    byte ptr [r8+1Ch], 1
0x18001af9d  jz      short loc_18001AFC8
0x18001af9f  mov     ecx, [r11+18h]
0x18001afa3  call    ?EnumToString@@YAPEBDW4_WCM_MEDIA_TYPE@@@Z; EnumToString(_WCM_MEDIA_TYPE)
0x18001afa8  mov     [rsp+0E0h+var_B0], r15
0x18001afad  mov     edx, [rbx+r14+4]
0x18001afb2  mov     [rsp+0E0h+var_B8], edx
0x18001afb6  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001afbb  lea     r9, [r11+4]
0x18001afbf  mov     rcx, [r8+10h]
0x18001afc3  call    WPP_SF__guid_sDS
0x18001afc8  inc     edi
0x18001afca  mov     rbx, [rbp+3Fh+var_70]
0x18001afce  cmp     edi, [rbx]
0x18001afd0  jb      loc_18001AF34
0x18001afd6  mov     r15, [rbp+3Fh+var_A0]
0x18001afda  xor     r14d, r14d
0x18001afdd  jmp     loc_18001ADEF
0x18001afe2  test    rbx, rbx
0x18001afe5  jz      loc_18001AD1F
0x18001afeb  mov     rcx, rbx; Block
0x18001afee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001aff3  jmp     loc_18001AD1F
0x18001aff8  cmp     byte ptr [rcx+19h], 4
0x18001affc  jb      loc_18001AC61
0x18001b002  test    byte ptr [rcx+1Ch], 1
0x18001b006  jz      loc_18001AC61
0x18001b00c  test    edi, edi
0x18001b00e  setnz   dl
0x18001b011  lea     r8, aNoSelectionFil; "no selection filter"
0x18001b018  lea     rax, aASelectionFilt; "a selection filter"
0x18001b01f  test    r14, r14
0x18001b022  cmovz   rax, r8
0x18001b026  mov     byte ptr [rsp+0E0h+var_B0], dl
0x18001b02a  mov     [rsp+0E0h+var_B8], esi
0x18001b02e  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001b033  mov     r9, rbx
0x18001b036  mov     rcx, [rcx+10h]
0x18001b03a  call    WPP_SF_SsDc
0x18001b03f  jmp     loc_18001AC61
0x18001b044  lea     r8, aOnecoreuapNetW_26; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18001b04b  mov     edx, 360h; void *
0x18001b050  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18001b056  cmp     byte ptr [rcx+19h], 5
0x18001b05a  jb      loc_18001AD12
0x18001b060  test    [rcx+1Ch], dil
0x18001b064  jz      loc_18001AD12
0x18001b06a  mov     edx, 20h ; ' '
0x18001b06f  mov     [rsp+0E0h+var_C0], r14d
0x18001b074  lea     r9, aSelectionmanag; "SelectionManager::InternalGetInterfaceC"...
0x18001b07b  lea     r8, WPP_1e598accbd0633246e27c279a8537074_Traceguids
0x18001b082  mov     rcx, [rcx+10h]
0x18001b086  call    WPP_SF_sL
0x18001b08b  jmp     loc_18001AD12
0x18001b090  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b097  lea     rbx, WPP_GLOBAL_Control
0x18001b09e  cmp     rcx, rbx
0x18001b0a1  jz      short loc_18001B0CB
  ... truncated ...
```
