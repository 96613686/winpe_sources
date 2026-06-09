# CFSContainerReference::OnStartContainerActivity(IMFAsyncResult *)

- ea: `0x1800811fc`
- end: `0x1800813a5`
- name: `?OnStartContainerActivity@CFSContainerReference@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `425`
- prototype: `void __fastcall(CFSContainerReference *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180081170`

## callees

- `0x180009608`
- `0x1800096f4`
- `0x180080b44`
- `0x1800811fc`
- `0x180081668`
- `0x1800816bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081329`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081360`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081329`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081360`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800812e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180081335`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800812e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180081335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800812a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800812a1`
- `api-ms-win-containers-cmclient-l1-2-0!CmsCreateActivity` at `0x180081237`
- `api-ms-win-containers-cmclient-l1-2-0!CmsCreateActivity` at `0x180081237`
- `api-ms-win-containers-cmclient-l1-2-0!CmsStartActivityAsync` at `0x180081273`
- `api-ms-win-containers-cmclient-l1-2-0!CmsStartActivityAsync` at `0x180081273`

## pseudocode

```c
void __fastcall CFSContainerReference::OnStartContainerActivity(CFSContainerReference *this, struct IMFAsyncResult *a2)
{
  int Activity; // eax
  signed int v4; // ebx
  __int64 v5; // rdx
  signed int LastError; // eax
  signed __int32 v7; // eax
  _QWORD v8[7]; // [rsp+30h] [rbp-38h] BYREF
  int v9; // [rsp+78h] [rbp+10h] BYREF
  int v10; // [rsp+7Ch] [rbp+14h]

  v10 = HIDWORD(a2);
  v9 = 0;
  v8[0] = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseActivity_CFSContainerReference__CAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    v8,
    0);
  Activity = CmsCreateActivity(*((_QWORD *)this + 11), 23000, v8);
  v4 = Activity;
  if ( Activity < 0 )
  {
    if ( !g_wppLevels )
    {
LABEL_14:
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
      v7 = _InterlockedDecrement((volatile signed __int32 *)this + 26);
      if ( byte_18010EC4D )
        WPP_SF_qDD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          38,
          &WPP_cb07d43c516b3c9f6415f7501f7e13b4_Traceguids,
          this,
          v4,
          v7);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
      goto LABEL_21;
    }
    v5 = 35;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_cb07d43c516b3c9f6415f7501f7e13b4_Traceguids, this, Activity);
    goto LABEL_14;
  }
  Activity = CmsStartActivityAsync(v8[0], CFSContainerReference::ActivityNotificationCallback, &v9);
  v4 = Activity;
  if ( Activity < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_14;
    v5 = 36;
    goto LABEL_4;
  }
  if ( !(unsigned __int8)wil::slim_event_t<1>::wait(&v9) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_cb07d43c516b3c9f6415f7501f7e13b4_Traceguids, this, v4);
      goto LABEL_14;
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( (_QWORD *)((char *)this + 96) != v8 )
  {
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseActivity_CFSContainerReference__CAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 96,
      v8[0]);
    v8[0] = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 39, &WPP_cb07d43c516b3c9f6415f7501f7e13b4_Traceguids, this, v4);
LABEL_21:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseActivity_CFSContainerReference__CAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v8);
}

```

## disassembly

```asm
0x1800811fc  mov     rax, rsp
0x1800811ff  mov     [rax+10h], rdx
0x180081203  push    rbx
0x180081204  push    rsi
0x180081205  push    rdi
0x180081206  push    r14
0x180081208  sub     rsp, 48h
0x18008120c  mov     rdi, rcx
0x18008120f  mov     dword ptr [rax+10h], 0
0x180081216  lea     rcx, [rax-38h]
0x18008121a  mov     qword ptr [rax-38h], 0
0x180081222  xor     edx, edx
0x180081224  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseActivity@CFSContainerReference@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180081229  mov     rcx, [rdi+58h]
0x18008122d  lea     r8, [rsp+68h+var_38]
0x180081232  mov     edx, 59D8h
0x180081237  call    cs:__imp_CmsCreateActivity
0x18008123d  lea     r14, WPP_cb07d43c516b3c9f6415f7501f7e13b4_Traceguids
0x180081244  mov     ebx, eax
0x180081246  test    eax, eax
0x180081248  jns     short loc_180081262
0x18008124a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180081251  jb      loc_1800812E2
0x180081257  mov     edx, 23h ; '#'
0x18008125c  mov     [rsp+68h+var_48], eax
0x180081260  jmp     short loc_1800812CC
0x180081262  mov     rcx, [rsp+68h+var_38]
0x180081267  lea     r8, [rsp+68h+arg_8]
0x18008126c  lea     rdx, ?ActivityNotificationCallback@CFSContainerReference@@KAXPEAU_CMS_ACTIVITY_NOTIFICATION@@PEAX@Z; CFSContainerReference::ActivityNotificationCallback(_CMS_ACTIVITY_NOTIFICATION *,void *)
0x180081273  call    cs:__imp_CmsStartActivityAsync
0x180081279  mov     ebx, eax
0x18008127b  test    eax, eax
0x18008127d  jns     short loc_18008128F
0x18008127f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180081286  jb      short loc_1800812E2
0x180081288  mov     edx, 24h ; '$'
0x18008128d  jmp     short loc_18008125C
0x18008128f  lea     rcx, [rsp+68h+arg_8]
0x180081294  call    ?wait@?$slim_event_t@$00@wil@@QEAA_NK@Z; wil::slim_event_t<1>::wait(ulong)
0x180081299  test    al, al
0x18008129b  jnz     loc_180081331
0x1800812a1  call    cs:__imp_GetLastError
0x1800812a7  mov     ebx, eax
0x1800812a9  test    eax, eax
0x1800812ab  jle     short loc_1800812B6
0x1800812ad  movzx   ebx, ax
0x1800812b0  or      ebx, 80070000h
0x1800812b6  test    ebx, ebx
0x1800812b8  jns     short loc_180081331
0x1800812ba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800812c1  jb      short loc_1800812E2
0x1800812c3  mov     edx, 25h ; '%'
0x1800812c8  mov     [rsp+68h+var_48], ebx
0x1800812cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800812d3  mov     r9, rdi
0x1800812d6  mov     r8, r14
0x1800812d9  mov     rcx, [rcx+10h]
0x1800812dd  call    WPP_SF_qD
0x1800812e2  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800812e6  call    cs:__imp_EnterCriticalSection
0x1800812ec  or      eax, 0FFFFFFFFh
0x1800812ef  lock xadd [rdi+68h], eax
0x1800812f4  dec     eax
0x1800812f6  cmp     cs:byte_18010EC4D, 1
0x1800812fd  jb      short loc_180081325
0x1800812ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180081306  mov     edx, 26h ; '&'
0x18008130b  mov     [rsp+68h+var_40], eax
0x18008130f  mov     r9, rdi
0x180081312  mov     r8, r14
0x180081315  mov     [rsp+68h+var_48], ebx
0x180081319  mov     rcx, [rcx+0D8h]
0x180081320  call    WPP_SF_qDD
0x180081325  lea     rcx, [rdi+18h]; lpCriticalSection
0x180081329  call    cs:__imp_LeaveCriticalSection
0x18008132f  jmp     short loc_180081391
0x180081331  lea     rcx, [rdi+18h]; lpCriticalSection
0x180081335  call    cs:__imp_EnterCriticalSection
0x18008133b  lea     rcx, [rdi+60h]
0x18008133f  lea     rax, [rsp+68h+var_38]
0x180081344  cmp     rcx, rax
0x180081347  jz      short loc_18008135C
0x180081349  mov     rdx, [rsp+68h+var_38]
0x18008134e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseActivity@CFSContainerReference@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180081353  mov     [rsp+68h+var_38], 0
0x18008135c  lea     rcx, [rdi+18h]; lpCriticalSection
0x180081360  call    cs:__imp_LeaveCriticalSection
0x180081366  cmp     cs:byte_18010EC4D, 10h
0x18008136d  jb      short loc_180081391
0x18008136f  mov     rcx, cs:WPP_GLOBAL_Control
0x180081376  mov     edx, 27h ; '''
0x18008137b  mov     r9, rdi
0x18008137e  mov     [rsp+68h+var_48], ebx
0x180081382  mov     r8, r14
0x180081385  mov     rcx, [rcx+0D8h]
0x18008138c  call    WPP_SF_qD
0x180081391  lea     rcx, [rsp+68h+var_38]
0x180081396  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseActivity@CFSContainerReference@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008139b  add     rsp, 48h
0x18008139f  pop     r14
0x1800813a1  pop     rdi
0x1800813a2  pop     rsi
0x1800813a3  pop     rbx
0x1800813a4  retn
```
