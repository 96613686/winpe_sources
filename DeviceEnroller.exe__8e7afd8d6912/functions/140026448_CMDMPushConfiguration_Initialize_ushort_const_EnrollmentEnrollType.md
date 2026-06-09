# CMDMPushConfiguration::Initialize(ushort const *,EnrollmentEnrollType)

- ea: `0x140026448`
- end: `0x14002664d`
- name: `?Initialize@CMDMPushConfiguration@@QEAAJPEBGW4EnrollmentEnrollType@@@Z`
- size: `517`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014040`
- `0x1400142a4`
- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x1400095b4`
- `0x1400133c4`
- `0x14001e988`
- `0x14001eb6c`
- `0x140024378`
- `0x140026448`
- `0x140028e7c`
- `0x140029124`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400265ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400265ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400265c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400265c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400265b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400265b9`
- `OLEAUT32!__imp_SysAllocString` at `0x140026536`
- `OLEAUT32!__imp_SysAllocString` at `0x140026536`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002658e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002658e`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140026514`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140026514`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::Initialize(__int64 a1, const OLECHAR *a2, int a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  HRESULT v8; // eax
  BSTR v9; // rax
  const WCHAR *v10; // rdx
  __int64 v11; // r14
  void **v12; // rdi
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v15; // rcx
  int dwAuthnLevel; // [rsp+20h] [rbp-E0h]
  PSRWLOCK SRWLock[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v19[34]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v20; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v19,
    "InitializeActivity");
  v19[0] = &MDMPushProvider::InitializeActivity::`vftable';
  MDMPushProvider::InitializeActivity::StartActivity((MDMPushProvider::InitializeActivity *)v19);
  if ( *(_DWORD *)a1 )
  {
    v6 = -2147483634;
    v7 = 127;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
      (const char *)(unsigned int)v6,
      dwAuthnLevel);
    goto LABEL_20;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = 128;
    goto LABEL_5;
  }
  v8 = CoInitializeSecurity(0, -1, 0, 0, 1u, 3u, 0, 0, 0);
  if ( v8 < 0 )
  {
    v6 = 0;
    if ( v8 != -2147417831 )
      v6 = v8;
    if ( v6 < 0 )
    {
      v7 = 140;
      goto LABEL_5;
    }
  }
  v9 = SysAllocString(a2);
  *(_QWORD *)(a1 + 8) = v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    v7 = 144;
    goto LABEL_5;
  }
  v10 = c_szTestHookLocation;
  *(_DWORD *)(a1 + 16) = a3;
  if ( !RegGetValueW(HKEY_LOCAL_MACHINE, v10, L"MDMPushTestHook", 0x18u, 0, 0, 0) )
  {
    wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      v19,
      SRWLock);
    v11 = v20;
    v12 = (void **)(v20 + 56);
    if ( *(_BYTE *)(v20 + 64) )
    {
      v13 = *v12;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
      *(_BYTE *)(v11 + 64) = 0;
    }
    v15 = SRWLock[0];
    *v12 = 0;
    *v12 = L"TestHook";
    if ( v15 )
      ReleaseSRWLockExclusive(v15);
    *(_DWORD *)(a1 + 20) = 1;
  }
  *(_DWORD *)a1 = 1;
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v19);
  v6 = 0;
LABEL_20:
  v19[0] = &MDMPushProvider::InitializeActivity::`vftable';
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v19);
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v19);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140026448  mov     [rsp-8+arg_10], rbx
0x14002644d  push    rbp
0x14002644e  push    rsi
0x14002644f  push    rdi
0x140026450  push    r13
0x140026452  push    r14
0x140026454  lea     rbp, [rsp-0C0h]
0x14002645c  sub     rsp, 1C0h
0x140026463  mov     rax, cs:__security_cookie
0x14002646a  xor     rax, rsp
0x14002646d  mov     [rbp+0E0h+var_30], rax
0x140026474  mov     rdi, rdx
0x140026477  mov     rsi, rcx
0x14002647a  lea     rdx, aInitializeacti; "InitializeActivity"
0x140026481  mov     r14d, r8d
0x140026484  lea     rcx, [rsp+1E0h+var_180]
0x140026489  call    ??0?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14002648e  lea     r13, ??_7InitializeActivity@MDMPushProvider@@6B@; const MDMPushProvider::InitializeActivity::`vftable'
0x140026495  lea     rcx, [rsp+1E0h+var_180]; this
0x14002649a  mov     [rsp+1E0h+var_180], r13
0x14002649f  call    ?StartActivity@InitializeActivity@MDMPushProvider@@QEAAXXZ; MDMPushProvider::InitializeActivity::StartActivity(void)
0x1400264a4  cmp     dword ptr [rsi], 0
0x1400264a7  jz      short loc_1400264B5
0x1400264a9  mov     ebx, 8000000Eh
0x1400264ae  mov     edx, 7Fh
0x1400264b3  jmp     short loc_1400264C4
0x1400264b5  test    rdi, rdi
0x1400264b8  jnz     short loc_1400264DF
0x1400264ba  mov     ebx, 80070057h
0x1400264bf  mov     edx, 80h; void *
0x1400264c4  mov     rcx, [rbp+0E8h]; this
0x1400264cb  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x1400264d2  mov     r9d, ebx; char *
0x1400264d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400264da  jmp     loc_14002660C
0x1400264df  mov     [rsp+1E0h+pReserved3], 0; pReserved3
0x1400264e8  xor     r9d, r9d; pReserved1
0x1400264eb  mov     [rsp+1E0h+dwCapabilities], 0; dwCapabilities
0x1400264f3  xor     r8d, r8d; asAuthSvc
0x1400264f6  mov     [rsp+1E0h+pAuthList], 0; pAuthList
0x1400264ff  or      edx, 0FFFFFFFFh; cAuthSvc
0x140026502  mov     [rsp+1E0h+dwImpLevel], 3; dwImpLevel
0x14002650a  xor     ecx, ecx; pSecDesc
0x14002650c  mov     [rsp+1E0h+dwAuthnLevel], 1; dwAuthnLevel
0x140026514  call    cs:__imp_CoInitializeSecurity
0x14002651a  test    eax, eax
0x14002651c  jns     short loc_140026533
0x14002651e  xor     ebx, ebx
0x140026520  cmp     eax, 80010119h
0x140026525  cmovnz  ebx, eax
0x140026528  test    ebx, ebx
0x14002652a  jns     short loc_140026533
0x14002652c  mov     edx, 8Ch
0x140026531  jmp     short loc_1400264C4
0x140026533  mov     rcx, rdi; psz
0x140026536  call    cs:__imp_SysAllocString
0x14002653c  mov     [rsi+8], rax
0x140026540  test    rax, rax
0x140026543  jnz     short loc_140026554
0x140026545  mov     ebx, 8007000Eh
0x14002654a  mov     edx, 90h
0x14002654f  jmp     loc_1400264C4
0x140026554  mov     rdx, cs:?c_szTestHookLocation@@3PEBGEB; lpSubKey
0x14002655b  lea     r8, aMdmpushtesthoo; "MDMPushTestHook"
0x140026562  mov     [rsp+1E0h+pAuthList], 0; pcbData
0x14002656b  mov     r9d, 18h; dwFlags
0x140026571  mov     qword ptr [rsp+1E0h+dwImpLevel], 0; pvData
0x14002657a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140026581  mov     qword ptr [rsp+1E0h+dwAuthnLevel], 0; pdwType
0x14002658a  mov     [rsi+10h], r14d
0x14002658e  call    cs:__imp_RegGetValueW
0x140026594  test    eax, eax
0x140026596  jnz     short loc_1400265FA
0x140026598  lea     rdx, [rsp+1E0h+SRWLock]
0x14002659d  lea     rcx, [rsp+1E0h+var_180]
0x1400265a2  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400265a7  mov     r14, [rbp+0E0h+var_70]
0x1400265ab  cmp     byte ptr [r14+40h], 0
0x1400265b0  lea     rdi, [r14+38h]
0x1400265b4  jz      short loc_1400265D2
0x1400265b6  mov     rbx, [rdi]
0x1400265b9  call    cs:__imp_GetProcessHeap
0x1400265bf  mov     r8, rbx; lpMem
0x1400265c2  xor     edx, edx; dwFlags
0x1400265c4  mov     rcx, rax; hHeap
0x1400265c7  call    cs:__imp_HeapFree
0x1400265cd  mov     byte ptr [r14+40h], 0
0x1400265d2  mov     rcx, [rsp+1E0h+SRWLock]; SRWLock
0x1400265d7  lea     rax, aTesthook; "TestHook"
0x1400265de  mov     qword ptr [rdi], 0
0x1400265e5  mov     [rdi], rax
0x1400265e8  test    rcx, rcx
0x1400265eb  jz      short loc_1400265F3
0x1400265ed  call    cs:__imp_ReleaseSRWLockExclusive
0x1400265f3  mov     dword ptr [rsi+14h], 1
0x1400265fa  lea     rcx, [rsp+1E0h+var_180]
0x1400265ff  mov     dword ptr [rsi], 1
0x140026605  call    ?Stop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14002660a  xor     ebx, ebx
0x14002660c  lea     rcx, [rsp+1E0h+var_180]
0x140026611  mov     [rsp+1E0h+var_180], r13
0x140026616  call    ?Destroy@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14002661b  lea     rcx, [rsp+1E0h+var_180]
0x140026620  call    ??1?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140026625  mov     eax, ebx
0x140026627  mov     rcx, [rbp+0E0h+var_30]
0x14002662e  xor     rcx, rsp; StackCookie
0x140026631  call    __security_check_cookie
0x140026636  mov     rbx, [rsp+1E0h+arg_10]
0x14002663e  add     rsp, 1C0h
0x140026645  pop     r14
0x140026647  pop     r13
0x140026649  pop     rdi
0x14002664a  pop     rsi
0x14002664b  pop     rbp
0x14002664c  retn
```
