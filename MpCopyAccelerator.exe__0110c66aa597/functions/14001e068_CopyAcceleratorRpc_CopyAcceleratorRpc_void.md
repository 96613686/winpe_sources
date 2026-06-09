# CopyAcceleratorRpc::CopyAcceleratorRpc(void)

- ea: `0x14001e068`
- end: `0x14001e235`
- name: `??0CopyAcceleratorRpc@@QEAA@XZ`
- size: `461`
- prototype: `CopyAcceleratorRpc *__fastcall(CopyAcceleratorRpc *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001dba4`

## callees

- `0x140002e74`
- `0x140003254`
- `0x140003ed8`
- `0x14000493c`
- `0x140005c20`
- `0x140005c40`
- `0x14001da4c`
- `0x14001e068`
- `0x14001fbd0`
- `0x140020748`
- `0x140020aac`

## import_xrefs

- `MpClient!MpConfigUnregisterNotifications` at `0x14001e0b3`
- `MpClient!MpConfigUnregisterNotifications` at `0x14001e0b3`
- `MpClient!MpConfigRegisterForNotifications` at `0x14001e0d9`
- `MpClient!MpConfigRegisterForNotifications` at `0x14001e0d9`
- `KERNEL32!GetLastError` at `0x14001e1e2`
- `KERNEL32!GetLastError` at `0x14001e1e2`
- `KERNEL32!CreateEventW` at `0x14001e0fb`
- `KERNEL32!CreateEventW` at `0x14001e0fb`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14001e18b`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14001e18b`

## string_xrefs

- `0x14001e150`: `IMpCpyAcltr`

## pseudocode

```c
CopyAcceleratorRpc *__fastcall CopyAcceleratorRpc::CopyAcceleratorRpc(CopyAcceleratorRpc *this)
{
  _QWORD *v2; // rbx
  int v3; // eax
  int v4; // edx
  struct CCopyControl *Instance; // rbx
  HANDLE EventW; // rax
  int v7; // edx
  int v8; // edx
  unsigned __int64 v9; // rdx
  int v10; // eax
  int v11; // edx
  int LastFailure; // eax
  int v13; // edx
  _QWORD *v15; // rcx
  DWORD LastError; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  _BYTE v19[8]; // [rsp+38h] [rbp-20h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+40h] [rbp-18h] BYREF

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 4) = 0;
  v2 = (_QWORD *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 5) = 0;
  if ( *((_QWORD *)this + 3) )
  {
    MpConfigUnregisterNotifications();
    *v2 = 0;
  }
  v3 = MpConfigRegisterForNotifications(L".", this, guard_check_icall_nop, 0, v2);
  if ( v3 < 0 )
    CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v3, v4);
  Instance = CCopyControl::GetInstance();
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)Instance = EventW;
  if ( !EventW )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, LastError);
        v15 = WPP_GLOBAL_Control;
      }
      if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
        WPP_SF_(v15[2], 14, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids);
    }
    CommonUtil::CommonThrowHr((CommonUtil *)0x80004005LL, v7);
  }
  qword_14003DBA8 = *(_QWORD *)std::chrono::steady_clock::now(v19) - 86400000000000LL;
  CommonUtil::StoreRpcGetClientPidFunction(0, v8);
  if ( *(_QWORD *)this )
  {
    operator delete(*(void **)this, v9);
    *(_QWORD *)this = 0;
  }
  v10 = CommonUtil::NewSprintfW(this, (wchar_t **)L"%ls%ls", L"IMpCpyAcltr", L"1d8d3448-2a8d-409f-841d-2db9e0220897");
  if ( v10 < 0 )
    CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v10, v11);
  SecurityDescriptorSize = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GA;;;AU)(A;;GA;;;AC)(A;;GA;;;S-1-15-3-1024-3153509613-960666767-3724611135-2725662640-12138253-543910227"
           "-1950414635-4190290187)",
          1u,
          (PSECURITY_DESCRIPTOR *)this + 1,
          &SecurityDescriptorSize) )
  {
    LastFailure = HrGetLastFailure();
    if ( LastFailure < 0 )
      CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)LastFailure, v13);
  }
  return this;
}

```

## disassembly

```asm
0x14001e068  mov     [rsp+arg_8], rbx
0x14001e06d  push    rdi
0x14001e06e  sub     rsp, 50h
0x14001e072  mov     rax, cs:__security_cookie
0x14001e079  xor     rax, rsp
0x14001e07c  mov     [rsp+58h+var_10], rax
0x14001e081  mov     rdi, rcx
0x14001e084  mov     [rsp+58h+var_28], rcx
0x14001e089  mov     qword ptr [rcx], 0
0x14001e090  mov     dword ptr [rcx+10h], 0
0x14001e097  lea     rbx, [rcx+18h]
0x14001e09b  mov     qword ptr [rbx], 0
0x14001e0a2  xor     eax, eax
0x14001e0a4  mov     [rcx+20h], eax
0x14001e0a7  mov     [rcx+28h], rax
0x14001e0ab  mov     rcx, [rbx]
0x14001e0ae  test    rcx, rcx
0x14001e0b1  jz      short loc_14001E0C0
0x14001e0b3  call    cs:__imp_MpConfigUnregisterNotifications
0x14001e0b9  mov     qword ptr [rbx], 0
0x14001e0c0  mov     [rsp+58h+var_38], rbx
0x14001e0c5  xor     r9d, r9d
0x14001e0c8  lea     r8, _guard_check_icall_nop
0x14001e0cf  mov     rdx, rdi
0x14001e0d2  lea     rcx, asc_1400340D8; "."
0x14001e0d9  call    cs:__imp_MpConfigRegisterForNotifications
0x14001e0df  test    eax, eax
0x14001e0e1  js      loc_14001E1C1
0x14001e0e7  call    ?GetInstance@CCopyControl@@SAAEAV1@XZ; CCopyControl::GetInstance(void)
0x14001e0ec  mov     rbx, rax
0x14001e0ef  xor     r9d, r9d; lpName
0x14001e0f2  xor     r8d, r8d; bInitialState
0x14001e0f5  lea     edx, [r9+1]; bManualReset
0x14001e0f9  xor     ecx, ecx; lpEventAttributes
0x14001e0fb  call    cs:__imp_CreateEventW
0x14001e101  mov     [rbx], rax
0x14001e104  test    rax, rax
0x14001e107  jz      loc_14001E1C9
0x14001e10d  lea     rcx, [rsp+58h+var_20]
0x14001e112  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x14001e117  mov     rcx, [rax]
0x14001e11a  mov     rax, 4E94914F0000h
0x14001e124  sub     rcx, rax
0x14001e127  mov     cs:qword_14003DBA8, rcx
0x14001e12e  xor     ecx, ecx; this
0x14001e130  call    ?StoreRpcGetClientPidFunction@CommonUtil@@YAJH@Z; CommonUtil::StoreRpcGetClientPidFunction(int)
0x14001e135  mov     rcx, [rdi]; void *
0x14001e138  test    rcx, rcx
0x14001e13b  jz      short loc_14001E149
0x14001e13d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001e142  mov     qword ptr [rdi], 0
0x14001e149  lea     r9, a1d8d34482a8d40; "1d8d3448-2a8d-409f-841d-2db9e0220897"
0x14001e150  lea     r8, aImpcpyacltr; "IMpCpyAcltr"
0x14001e157  lea     rdx, aLsLs_0; "%ls%ls"
0x14001e15e  mov     rcx, rdi; this
0x14001e161  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x14001e166  test    eax, eax
0x14001e168  js      loc_14001E22D
0x14001e16e  mov     [rsp+58h+SecurityDescriptorSize], 0
0x14001e176  lea     r8, [rdi+8]; SecurityDescriptor
0x14001e17a  lea     r9, [rsp+58h+SecurityDescriptorSize]; SecurityDescriptorSize
0x14001e17f  mov     edx, 1; StringSDRevision
0x14001e184  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;AU)(A;;GA;;;AC)(A;;GA;;;S-1-"...
0x14001e18b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14001e191  test    eax, eax
0x14001e193  jnz     short loc_14001E19E
0x14001e195  call    HrGetLastFailure
0x14001e19a  test    eax, eax
0x14001e19c  js      short loc_14001E1B9
0x14001e19e  mov     rax, rdi
0x14001e1a1  mov     rcx, [rsp+58h+var_10]
0x14001e1a6  xor     rcx, rsp; StackCookie
0x14001e1a9  call    __security_check_cookie
0x14001e1ae  mov     rbx, [rsp+58h+arg_8]
0x14001e1b3  add     rsp, 50h
0x14001e1b7  pop     rdi
0x14001e1b8  retn
0x14001e1b9  mov     ecx, eax; this
0x14001e1bb  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x14001e1c1  mov     ecx, eax; this
0x14001e1c3  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x14001e1c9  lea     rbx, WPP_GLOBAL_Control
0x14001e1d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e1d7  cmp     rcx, rbx
0x14001e1da  jz      short loc_14001E222
0x14001e1dc  test    byte ptr [rcx+1Ch], 4
0x14001e1e0  jz      short loc_14001E202
0x14001e1e2  call    cs:__imp_GetLastError
0x14001e1e8  mov     r9d, eax
0x14001e1eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e1f2  mov     rcx, [rcx+10h]
0x14001e1f6  call    WPP_SF_l
0x14001e1fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e202  cmp     rcx, rbx
0x14001e205  jz      short loc_14001E222
0x14001e207  test    byte ptr [rcx+1Ch], 1
0x14001e20b  jz      short loc_14001E222
0x14001e20d  mov     edx, 0Eh
0x14001e212  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001e219  mov     rcx, [rcx+10h]
0x14001e21d  call    WPP_SF_
0x14001e222  mov     ecx, 80004005h; this
0x14001e227  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x14001e22d  mov     ecx, eax; this
0x14001e22f  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
```
