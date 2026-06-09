# CLegacyHandlerShim::GetObjectW(_GUID const &,_GUID const &,void * *)

- ea: `0x18001d200`
- end: `0x18001d3d3`
- name: `?GetObjectW@CLegacyHandlerShim@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `467`
- prototype: `int(CLegacyHandlerShim *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001d200`
- `0x18001ecd4`
- `0x180024ac4`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d378`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d378`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d329`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d329`

## pseudocode

```c
__int64 __fastcall CLegacyHandlerShim::GetObjectW(
        CLegacyHandlerShim *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  CLegacyHandlerShim *v6; // rdi
  HRESULT v7; // ebx
  __int64 (__fastcall **v8)(CLegacyHandlerShim *, const struct _GUID *, void **); // rax
  __int64 v10; // rcx
  void *v11; // rcx
  HICON v12; // r8
  int Instance; // eax
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  *a4 = 0;
  v6 = this;
  v7 = -2147467262;
  if ( *(_OWORD *)a2 == SYNCMGR_OBJECTID_ShowProperties )
  {
    if ( CLegacyHandlerShim::_HasProperties(this) == 1 )
    {
      *((_BYTE *)v6 + 316) = 1;
      this = v6;
      v8 = *(__int64 (__fastcall ***)(CLegacyHandlerShim *, const struct _GUID *, void **))v6;
      return (unsigned int)(*v8)(this, a3, a4);
    }
  }
  else
  {
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&SYNCMGR_OBJECTID_EventLinkClick.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)SYNCMGR_OBJECTID_EventLinkClick.Data4 )
    {
      v8 = *(__int64 (__fastcall ***)(CLegacyHandlerShim *, const struct _GUID *, void **))this;
      *((_BYTE *)this + 316) = 0;
      return (unsigned int)(*v8)(this, a3, a4);
    }
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&SYNCMGR_OBJECTID_ConflictStore.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)SYNCMGR_OBJECTID_ConflictStore.Data4 )
    {
      return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, GUID *))(**((_QWORD **)this + 30) + 48LL))(
                             *((_QWORD *)this + 30),
                             &GUID_NULL);
    }
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&SYNCMGR_OBJECTID_Icon.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)SYNCMGR_OBJECTID_Icon.Data4 )
    {
      v10 = *((_QWORD *)this + 30);
      pv = 0;
      if ( !(*(unsigned int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v10 + 32LL))(v10, &pv) )
      {
        v11 = pv;
        v12 = (HICON)*((_QWORD *)pv + 1);
        if ( v12 )
        {
          Instance = ExtractIconOnHICON_CreateInstance(0, (const unsigned __int16 *)v6 + 22, v12, a3, a4);
          v11 = pv;
          v7 = Instance;
        }
        CoTaskMemFree(v11);
      }
    }
    else if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&SYNCMGR_OBJECTID_ShowSchedule.Data1
           && *(_QWORD *)a2->Data4 == *(_QWORD *)SYNCMGR_OBJECTID_ShowSchedule.Data4 )
    {
      pv = 0;
      v7 = CoCreateInstance(&CLSID_SyncMgrScheduleWizard, 0, 0x15u, &GUID_459a6c84_21d2_4ddc_8a53_f023a46066f2, &pv);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)pv + 32LL))(pv, (__int64)v6 + 44);
        if ( v7 >= 0 )
          v7 = (**(__int64 (__fastcall ***)(LPVOID, const struct _GUID *, void **))pv)(pv, a3, a4);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001d200  push    rbx
0x18001d202  push    rbp
0x18001d203  push    rsi
0x18001d204  push    rdi
0x18001d205  sub     rsp, 38h
0x18001d209  mov     qword ptr [r9], 0
0x18001d210  mov     rsi, r9
0x18001d213  mov     rax, [rdx]
0x18001d216  mov     rbp, r8
0x18001d219  cmp     rax, qword ptr cs:SYNCMGR_OBJECTID_ShowProperties
0x18001d220  mov     rdi, rcx
0x18001d223  mov     ebx, 80004002h
0x18001d228  jnz     short loc_18001D252
0x18001d22a  mov     rax, [rdx+8]
0x18001d22e  cmp     rax, qword ptr cs:SYNCMGR_OBJECTID_ShowProperties+8
0x18001d235  jnz     short loc_18001D252
0x18001d237  call    ?_HasProperties@CLegacyHandlerShim@@AEBA_NXZ; CLegacyHandlerShim::_HasProperties(void)
0x18001d23c  cmp     al, 1
0x18001d23e  jnz     loc_18001D3C8
0x18001d244  mov     [rdi+13Ch], al
0x18001d24a  mov     rcx, rdi
0x18001d24d  mov     rax, [rdi]
0x18001d250  jmp     short loc_18001D275
0x18001d252  mov     rax, [rdx]
0x18001d255  cmp     rax, qword ptr cs:SYNCMGR_OBJECTID_EventLinkClick.Data1
0x18001d25c  jnz     short loc_18001D285
0x18001d25e  mov     rax, [rdx+8]
0x18001d262  cmp     rax, qword ptr cs:SYNCMGR_OBJECTID_EventLinkClick.Data4
0x18001d269  jnz     short loc_18001D285
0x18001d26b  mov     rax, [rcx]
0x18001d26e  mov     byte ptr [rcx+13Ch], 0
0x18001d275  mov     rax, [rax]
0x18001d278  mov     rdx, rbp
0x18001d27b  mov     r8, rsi
0x18001d27e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d283  jmp     short loc_18001D2B8
0x18001d285  mov     rax, [rdx]
0x18001d288  cmp     rax, qword ptr cs:SYNCMGR_OBJECTID_ConflictStore.Data1
0x18001d28f  jnz     short loc_18001D2BF
0x18001d291  mov     rax, [rdx+8]
0x18001d295  cmp     rax, qword ptr cs:SYNCMGR_OBJECTID_ConflictStore.Data4
0x18001d29c  jnz     short loc_18001D2BF
0x18001d29e  mov     rcx, [rcx+0F0h]
0x18001d2a5  lea     rdx, GUID_NULL
0x18001d2ac  mov     rax, [rcx]
0x18001d2af  mov     rax, [rax+30h]
0x18001d2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2b8  mov     ebx, eax
0x18001d2ba  jmp     loc_18001D3C8
0x18001d2bf  mov     rax, [rdx]
0x18001d2c2  cmp     rax, qword ptr cs:SYNCMGR_OBJECTID_Icon.Data1
0x18001d2c9  jnz     short loc_18001D334
0x18001d2cb  mov     rax, [rdx+8]
0x18001d2cf  cmp     rax, qword ptr cs:SYNCMGR_OBJECTID_Icon.Data4
0x18001d2d6  jnz     short loc_18001D334
0x18001d2d8  mov     rcx, [rcx+0F0h]
0x18001d2df  lea     rdx, [rsp+58h+pv]
0x18001d2e4  mov     [rsp+58h+pv], 0
0x18001d2ed  mov     rax, [rcx]
0x18001d2f0  mov     rax, [rax+20h]
0x18001d2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2f9  test    eax, eax
0x18001d2fb  jnz     loc_18001D3C8
0x18001d301  mov     rcx, [rsp+58h+pv]
0x18001d306  mov     r8, [rcx+8]; HICON
0x18001d30a  test    r8, r8
0x18001d30d  jz      short loc_18001D329
0x18001d30f  lea     rdx, [rdi+2Ch]; unsigned __int16 *
0x18001d313  mov     [rsp+58h+ppv], rsi; void **
0x18001d318  mov     r9, rbp; struct _GUID *
0x18001d31b  xor     ecx, ecx; bool
0x18001d31d  call    ?ExtractIconOnHICON_CreateInstance@@YAJ_NPEBGPEAUHICON__@@AEBU_GUID@@PEAPEAX@Z; ExtractIconOnHICON_CreateInstance(bool,ushort const *,HICON__ *,_GUID const &,void * *)
0x18001d322  mov     rcx, [rsp+58h+pv]; pv
0x18001d327  mov     ebx, eax
0x18001d329  call    cs:__imp_CoTaskMemFree
0x18001d32f  jmp     loc_18001D3C8
0x18001d334  mov     rax, [rdx]
0x18001d337  cmp     rax, qword ptr cs:SYNCMGR_OBJECTID_ShowSchedule.Data1
0x18001d33e  jnz     loc_18001D3C8
0x18001d344  mov     rax, [rdx+8]
0x18001d348  cmp     rax, qword ptr cs:SYNCMGR_OBJECTID_ShowSchedule.Data4
0x18001d34f  jnz     short loc_18001D3C8
0x18001d351  xor     edx, edx; pUnkOuter
0x18001d353  mov     [rsp+58h+pv], 0
0x18001d35c  lea     rax, [rsp+58h+pv]
0x18001d361  lea     r9, _GUID_459a6c84_21d2_4ddc_8a53_f023a46066f2; riid
0x18001d368  mov     [rsp+58h+ppv], rax; ppv
0x18001d36d  lea     rcx, CLSID_SyncMgrScheduleWizard; rclsid
0x18001d374  lea     r8d, [rdx+15h]; dwClsContext
0x18001d378  call    cs:__imp_CoCreateInstance
0x18001d37e  mov     ebx, eax
0x18001d380  test    eax, eax
0x18001d382  js      short loc_18001D3C8
0x18001d384  mov     rcx, [rsp+58h+pv]
0x18001d389  lea     rdx, [rdi+2Ch]
0x18001d38d  mov     rax, [rcx]
0x18001d390  mov     rax, [rax+20h]
0x18001d394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d399  mov     ebx, eax
0x18001d39b  test    eax, eax
0x18001d39d  js      short loc_18001D3B7
0x18001d39f  mov     rcx, [rsp+58h+pv]
0x18001d3a4  mov     r8, rsi
0x18001d3a7  mov     rdx, rbp
0x18001d3aa  mov     rax, [rcx]
0x18001d3ad  mov     rax, [rax]
0x18001d3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3b5  mov     ebx, eax
0x18001d3b7  mov     rcx, [rsp+58h+pv]
0x18001d3bc  mov     rax, [rcx]
0x18001d3bf  mov     rax, [rax+10h]
0x18001d3c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3c8  mov     eax, ebx
0x18001d3ca  add     rsp, 38h
0x18001d3ce  pop     rdi
0x18001d3cf  pop     rsi
0x18001d3d0  pop     rbp
0x18001d3d1  pop     rbx
0x18001d3d2  retn
```
