# BackgroundInitializeHandler(void *)

- ea: `0x180006240`
- end: `0x180006366`
- name: `?BackgroundInitializeHandler@@YAKPEAX@Z`
- size: `294`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003ca0`
- `0x180006240`
- `0x180006da4`
- `0x180006ef4`
- `0x18000b010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800062b3`
- `KERNEL32!WaitForSingleObject` at `0x1800062b3`
- `KERNEL32!SetEvent` at `0x1800062a6`
- `KERNEL32!SetEvent` at `0x1800062a6`
- `ole32!CoUninitialize` at `0x18000633f`
- `ole32!CoUninitialize` at `0x18000633f`
- `ole32!CoInitializeEx` at `0x180006256`
- `ole32!CoInitializeEx` at `0x180006256`
- `ole32!CoCreateInstance` at `0x180006281`
- `ole32!CoCreateInstance` at `0x180006281`

## pseudocode

```c
__int64 __fastcall BackgroundInitializeHandler(char *Parameter)
{
  _QWORD *v2; // rsi
  HRESULT Instance; // eax
  void *v4; // rcx
  signed __int32 *v5; // rdi
  __int64 v6; // rcx
  int v7; // edx
  bool v8; // zf
  signed __int32 v9; // edx

  if ( CoInitializeEx(0, 0) >= 0 )
  {
    v2 = Parameter + 8;
    Instance = CoCreateInstance(
                 &CLSID_CNetworkListManager,
                 0,
                 4u,
                 &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b,
                 (LPVOID *)Parameter + 1);
    if ( Instance >= 0 )
    {
      Instance = CProfileCache::_UpdateMapping((CProfileCache *)Parameter);
      if ( Instance >= 0 )
        Instance = CProfileCache::_RegisterNotification((CProfileCache *)Parameter);
    }
    v4 = (void *)*((_QWORD *)Parameter + 7);
    *((_DWORD *)Parameter + 19) = Instance;
    SetEvent(v4);
    WaitForSingleObject(*((HANDLE *)Parameter + 8), 0xFFFFFFFF);
    v5 = (signed __int32 *)(Parameter + 48);
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(Parameter + 48));
    v6 = *((_QWORD *)Parameter + 10);
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 48LL))(v6, *((unsigned int *)Parameter + 22));
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 10) + 16LL))(*((_QWORD *)Parameter + 10));
      *((_QWORD *)Parameter + 10) = 0;
    }
    if ( *v2 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
      *v2 = 0;
    }
    v7 = *((_DWORD *)Parameter + 13) - 1;
    v8 = (((Parameter[52] - 1) & 3) != 0 ? v7 : 0) == 0;
    _InterlockedExchange((volatile __int32 *)Parameter + 13, ((Parameter[52] - 1) & 3) != 0 ? v7 : 0);
    if ( v8 )
    {
      _m_prefetchw(v5);
      do
        v9 = *v5;
      while ( v9 != _InterlockedCompareExchange(v5, (v9 - 0x10000) & 0xFFFF0000, v9) );
    }
    CoUninitialize();
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)Parameter + 16LL))(Parameter);
  return 0;
}

```

## disassembly

```asm
0x180006240  mov     [rsp+arg_0], rbx
0x180006245  mov     [rsp+arg_8], rsi
0x18000624a  push    rdi
0x18000624b  sub     rsp, 30h
0x18000624f  mov     rbx, rcx
0x180006252  xor     edx, edx; dwCoInit
0x180006254  xor     ecx, ecx; pvReserved
0x180006256  call    cs:__imp_CoInitializeEx
0x18000625c  test    eax, eax
0x18000625e  js      loc_180006345
0x180006264  xor     edx, edx; pUnkOuter
0x180006266  lea     rsi, [rbx+8]
0x18000626a  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x180006271  mov     [rsp+38h+ppv], rsi; ppv
0x180006276  lea     rcx, CLSID_CNetworkListManager; rclsid
0x18000627d  lea     r8d, [rdx+4]; dwClsContext
0x180006281  call    cs:__imp_CoCreateInstance
0x180006287  test    eax, eax
0x180006289  js      short loc_18000629F
0x18000628b  mov     rcx, rbx; this
0x18000628e  call    ?_UpdateMapping@CProfileCache@@AEAAJXZ; CProfileCache::_UpdateMapping(void)
0x180006293  test    eax, eax
0x180006295  js      short loc_18000629F
0x180006297  mov     rcx, rbx; this
0x18000629a  call    ?_RegisterNotification@CProfileCache@@AEAAJXZ; CProfileCache::_RegisterNotification(void)
0x18000629f  mov     rcx, [rbx+38h]; hEvent
0x1800062a3  mov     [rbx+4Ch], eax
0x1800062a6  call    cs:__imp_SetEvent
0x1800062ac  mov     rcx, [rbx+40h]; hHandle
0x1800062b0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800062b3  call    cs:__imp_WaitForSingleObject
0x1800062b9  lea     rdi, [rbx+30h]
0x1800062bd  mov     rcx, rdi; this
0x1800062c0  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800062c5  mov     rcx, [rbx+50h]
0x1800062c9  test    rcx, rcx
0x1800062cc  jz      short loc_1800062F5
0x1800062ce  mov     rax, [rcx]
0x1800062d1  mov     edx, [rbx+58h]
0x1800062d4  mov     rax, [rax+30h]
0x1800062d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062dd  mov     rcx, [rbx+50h]
0x1800062e1  mov     rax, [rcx]
0x1800062e4  mov     rax, [rax+10h]
0x1800062e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062ed  mov     qword ptr [rbx+50h], 0
0x1800062f5  mov     rcx, [rsi]
0x1800062f8  test    rcx, rcx
0x1800062fb  jz      short loc_180006310
0x1800062fd  mov     rax, [rcx]
0x180006300  mov     rax, [rax+10h]
0x180006304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006309  mov     qword ptr [rsi], 0
0x180006310  mov     edx, [rdi+4]
0x180006313  dec     edx
0x180006315  mov     eax, edx
0x180006317  and     al, 3
0x180006319  neg     al
0x18000631b  sbb     ecx, ecx
0x18000631d  and     ecx, edx
0x18000631f  xchg    ecx, [rdi+4]
0x180006322  jnz     short loc_18000633F
0x180006324  prefetchw byte ptr [rdi]
0x180006327  mov     edx, [rdi]
0x180006329  mov     eax, edx
0x18000632b  lea     ecx, [rdx-10000h]
0x180006331  and     ecx, 0FFFF0000h
0x180006337  lock cmpxchg [rdi], ecx
0x18000633b  cmp     edx, eax
0x18000633d  jnz     short loc_180006327
0x18000633f  call    cs:__imp_CoUninitialize
0x180006345  mov     rax, [rbx]
0x180006348  mov     rcx, rbx
0x18000634b  mov     rax, [rax+10h]
0x18000634f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006354  mov     rbx, [rsp+38h+arg_0]
0x180006359  xor     eax, eax
0x18000635b  mov     rsi, [rsp+38h+arg_8]
0x180006360  add     rsp, 30h
0x180006364  pop     rdi
0x180006365  retn
```
