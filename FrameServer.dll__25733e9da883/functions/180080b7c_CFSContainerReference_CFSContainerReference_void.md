# CFSContainerReference::~CFSContainerReference(void)

- ea: `0x180080b7c`
- end: `0x180080c0b`
- name: `??1CFSContainerReference@@MEAA@XZ`
- size: `143`
- prototype: `void __fastcall(CFSContainerReference *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180080c20`

## callees

- `0x1800095c8`
- `0x180080b44`
- `0x180080b60`
- `0x180080b7c`
- `0x180081668`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180080bf3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180080bf3`
- `MFPlat!MFUnlockWorkQueue` at `0x180080ba5`
- `MFPlat!MFUnlockWorkQueue` at `0x180080ba5`

## pseudocode

```c
void __fastcall CFSContainerReference::~CFSContainerReference(CFSContainerReference *this)
{
  DWORD v2; // ecx

  *(_QWORD *)this = &CFSContainerReference::`vftable';
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseActivity_CFSContainerReference__CAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 96,
    0);
  v2 = *((_DWORD *)this + 27);
  if ( v2 )
  {
    MFUnlockWorkQueue(v2);
    *((_DWORD *)this + 27) = 0;
  }
  if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 18, WPP_cb07d43c516b3c9f6415f7501f7e13b4_Traceguids, this);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseActivity_CFSContainerReference__CAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 96);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseContainer_CFSContainerReference__CAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 88);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  _InterlockedDecrement(&g_lRefModule);
}

```

## disassembly

```asm
0x180080b7c  mov     [rsp+arg_0], rbx
0x180080b81  push    rdi
0x180080b82  sub     rsp, 20h
0x180080b86  lea     rax, ??_7CFSContainerReference@@6B@; const CFSContainerReference::`vftable'
0x180080b8d  mov     rbx, rcx
0x180080b90  mov     [rcx], rax
0x180080b93  xor     edx, edx
0x180080b95  add     rcx, 60h ; '`'
0x180080b99  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseActivity@CFSContainerReference@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180080b9e  mov     ecx, [rbx+6Ch]; dwWorkQueue
0x180080ba1  test    ecx, ecx
0x180080ba3  jz      short loc_180080BB2
0x180080ba5  call    cs:__imp_MFUnlockWorkQueue
0x180080bab  mov     dword ptr [rbx+6Ch], 0
0x180080bb2  cmp     cs:byte_18010EC4D, 10h
0x180080bb9  jb      short loc_180080BDD
0x180080bbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180080bc2  lea     r8, WPP_cb07d43c516b3c9f6415f7501f7e13b4_Traceguids
0x180080bc9  mov     edx, 12h
0x180080bce  mov     r9, rbx
0x180080bd1  mov     rcx, [rcx+0D8h]
0x180080bd8  call    WPP_SF_q
0x180080bdd  lea     rcx, [rbx+60h]
0x180080be1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseActivity@CFSContainerReference@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180080be6  lea     rcx, [rbx+58h]
0x180080bea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseContainer@CFSContainerReference@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180080bef  lea     rcx, [rbx+18h]; lpCriticalSection
0x180080bf3  call    cs:__imp_DeleteCriticalSection
0x180080bf9  lock dec cs:?g_lRefModule@@3JA; long g_lRefModule
0x180080c00  mov     rbx, [rsp+28h+arg_0]
0x180080c05  add     rsp, 20h
0x180080c09  pop     rdi
0x180080c0a  retn
```
