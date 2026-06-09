# StartInstallJob::_ApplySinglePropertyHeuristic(_DEVPROPKEY const &)

- ea: `0x1800345c8`
- end: `0x1800346c4`
- name: `?_ApplySinglePropertyHeuristic@StartInstallJob@@AEAAJAEBU_DEVPROPKEY@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(StartInstallJob *__hidden this, const struct _DEVPROPKEY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800350a8`

## callees

- `0x180006770`
- `0x1800112a4`
- `0x180018678`
- `0x18001a8ec`
- `0x1800345c8`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034601`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034601`

## string_xrefs

- `0x180034655`: `onecoreuap\base\devices\setup\dsm\service\job.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StartInstallJob::_ApplySinglePropertyHeuristic(StartInstallJob *this, const struct _DEVPROPKEY *a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  _QWORD *v6; // rdx
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v10; // [rsp+48h] [rbp+10h] BYREF

  v10 = 0;
  v3 = CoCreateInstance(
         &GUID_5acb106d_1a06_4fcd_862d_02a74de81835,
         0,
         1u,
         &GUID_5163f90c_0c58_4057_bca6_95aa25acf06e,
         &v10);
  v4 = v3;
  if ( v3 >= 0 )
  {
    if ( !*((_WORD *)this + 40) )
      Job::_PopulateDefaultLanguages(this);
    v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v10 + 24LL))(
           v10,
           *((_QWORD *)this + 16),
           *((_QWORD *)this + 12),
           *((unsigned int *)this + 22));
    v4 = v3;
    if ( v3 >= 0 )
    {
      v6 = (_QWORD *)((char *)this + 40);
      if ( *((_QWORD *)this + 8) > 7u )
        v6 = (_QWORD *)*v6;
      v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *, const DEVPROPKEY *))(*(_QWORD *)v10 + 48LL))(
             v10,
             v6,
             &DEVPKEY_DeviceContainer_DiscoveryMethod);
      v4 = v3;
      if ( v3 >= 0 )
      {
        CDsmPropertyCache::CommitCachedContainerProperties((RTL_SRWLOCK *)(*((_QWORD *)this + 16) + 104LL));
        v4 = 0;
        goto LABEL_13;
      }
      v5 = 1516;
    }
    else
    {
      v5 = 1512;
    }
  }
  else
  {
    v5 = 1501;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\job.cpp",
    (const char *)(unsigned int)v3,
    v8);
LABEL_13:
  Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&v10);
  return v4;
}

```

## disassembly

```asm
0x1800345c8  mov     r11, rsp
0x1800345cb  mov     [r11+8], rbx
0x1800345cf  mov     [r11+18h], rsi
0x1800345d3  mov     [r11+10h], rdx
0x1800345d7  push    rdi
0x1800345d8  sub     rsp, 30h
0x1800345dc  mov     rdi, rcx
0x1800345df  xor     esi, esi
0x1800345e1  mov     [r11+10h], rsi
0x1800345e5  lea     rax, [r11+10h]
0x1800345e9  mov     [r11-18h], rax
0x1800345ed  lea     r9, _GUID_5163f90c_0c58_4057_bca6_95aa25acf06e; riid
0x1800345f4  xor     edx, edx; pUnkOuter
0x1800345f6  lea     r8d, [rsi+1]; dwClsContext
0x1800345fa  lea     rcx, _GUID_5acb106d_1a06_4fcd_862d_02a74de81835; rclsid
0x180034601  call    cs:__imp_CoCreateInstance
0x180034607  mov     ebx, eax
0x180034609  test    eax, eax
0x18003460b  jns     short loc_180034614
0x18003460d  mov     edx, 5DDh
0x180034612  jmp     short loc_18003464D
0x180034614  cmp     [rdi+50h], si
0x180034618  jnz     short loc_180034622
0x18003461a  mov     rcx, rdi; this
0x18003461d  call    ?_PopulateDefaultLanguages@Job@@IEAAXXZ; Job::_PopulateDefaultLanguages(void)
0x180034622  mov     rcx, [rsp+38h+arg_8]
0x180034627  mov     rax, [rcx]
0x18003462a  mov     r9d, [rdi+58h]
0x18003462e  mov     r8, [rdi+60h]
0x180034632  mov     rdx, [rdi+80h]
0x180034639  mov     rax, [rax+18h]
0x18003463d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034642  mov     ebx, eax
0x180034644  test    eax, eax
0x180034646  jns     short loc_180034663
0x180034648  mov     edx, 5E8h; void *
0x18003464d  mov     rcx, [rsp+38h]; this
0x180034652  mov     r9d, eax; char *
0x180034655  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18003465c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034661  jmp     short loc_1800346A8
0x180034663  mov     rcx, [rsp+38h+arg_8]
0x180034668  mov     rax, [rcx]
0x18003466b  lea     rdx, [rdi+28h]
0x18003466f  cmp     qword ptr [rdx+18h], 7
0x180034674  jbe     short loc_180034679
0x180034676  mov     rdx, [rdx]
0x180034679  lea     r8, DEVPKEY_DeviceContainer_DiscoveryMethod
0x180034680  mov     rax, [rax+30h]
0x180034684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034689  mov     ebx, eax
0x18003468b  test    eax, eax
0x18003468d  jns     short loc_180034696
0x18003468f  mov     edx, 5ECh
0x180034694  jmp     short loc_18003464D
0x180034696  mov     rcx, [rdi+80h]
0x18003469d  add     rcx, 68h ; 'h'; this
0x1800346a1  call    ?CommitCachedContainerProperties@CDsmPropertyCache@@QEAAXXZ; CDsmPropertyCache::CommitCachedContainerProperties(void)
0x1800346a6  mov     ebx, esi
0x1800346a8  lea     rcx, [rsp+38h+arg_8]
0x1800346ad  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x1800346b2  mov     eax, ebx
0x1800346b4  mov     rbx, [rsp+38h+arg_0]
0x1800346b9  mov     rsi, [rsp+38h+arg_10]
0x1800346be  add     rsp, 30h
0x1800346c2  pop     rdi
0x1800346c3  retn
```
