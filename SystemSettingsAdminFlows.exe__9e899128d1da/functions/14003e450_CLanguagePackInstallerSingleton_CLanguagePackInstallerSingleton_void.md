# CLanguagePackInstallerSingleton::~CLanguagePackInstallerSingleton(void)

- ea: `0x14003e450`
- end: `0x14003e625`
- name: `??1CLanguagePackInstallerSingleton@@UEAA@XZ`
- size: `469`
- prototype: `void __fastcall(CLanguagePackInstallerSingleton *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14003e6c0`

## callees

- `0x14000e624`
- `0x14003e03c`
- `0x14003e450`
- `0x14003e728`
- `0x14003f8cc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14003e569`
- `KERNEL32!DeleteCriticalSection` at `0x14003e5a6`
- `KERNEL32!DeleteCriticalSection` at `0x14003e5b0`
- `KERNEL32!DeleteCriticalSection` at `0x14003e569`
- `KERNEL32!DeleteCriticalSection` at `0x14003e5a6`
- `KERNEL32!DeleteCriticalSection` at `0x14003e5b0`
- `KERNEL32!TlsGetValue` at `0x14003e476`
- `KERNEL32!TlsGetValue` at `0x14003e476`
- `KERNEL32!TlsSetValue` at `0x14003e4a9`
- `KERNEL32!TlsSetValue` at `0x14003e4a9`
- `ole32!CoTaskMemFree` at `0x14003e57b`
- `ole32!CoTaskMemFree` at `0x14003e5e4`
- `ole32!CoTaskMemFree` at `0x14003e57b`
- `ole32!CoTaskMemFree` at `0x14003e5e4`

## pseudocode

```c
void __fastcall CLanguagePackInstallerSingleton::~CLanguagePackInstallerSingleton(
        CLanguagePackInstallerSingleton *this)
{
  _DWORD *Value; // rax
  _DWORD *v3; // rdi
  int v4; // eax
  PVOID *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // edx
  __int64 v8; // rsi
  void *v9; // rcx
  unsigned int v10; // edx
  unsigned __int64 *v11; // rdi
  unsigned __int64 i; // rsi
  _QWORD TlsValue[5]; // [rsp+30h] [rbp-28h] BYREF
  DWORD v14; // [rsp+60h] [rbp+8h] BYREF

  *(_QWORD *)this = &CLanguagePackInstallerSingleton::`vftable';
  Value = TlsGetValue(__g_tracingTlsSlot);
  v14 = -1;
  v3 = Value;
  TlsValue[0] = 0;
  if ( !Value )
  {
    v14 = __g_tracingTlsSlot;
    v3 = TlsValue;
    TlsSetValue(__g_tracingTlsSlot, TlsValue);
  }
  v4 = ++*v3;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      if ( (unsigned int)(5 * v4) > 0x1E1 )
        v6 = 0;
      else
        v6 = 479LL - (unsigned int)(5 * v4);
      WPP_SF_sq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)&WPP_f36bffa08b0b30fbbd1fad32a50cf4e7_Traceguids,
        (unsigned int)&asc_140089BC0[v6],
        (char)this);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && *((char *)v5 + 28) < 0 )
    {
      v7 = 5 * *v3;
      if ( v7 > 0x1E1 )
        v8 = 0;
      else
        v8 = 479LL - v7;
      WPP_SF_sq(
        (unsigned int)v5[2],
        11,
        (unsigned int)&WPP_f36bffa08b0b30fbbd1fad32a50cf4e7_Traceguids,
        (unsigned int)&asc_140089BC0[v8],
        (char)this);
    }
  }
  --*v3;
  TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(&v14);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  v9 = (void *)*((_QWORD *)this + 18);
  if ( v9 )
  {
    CoTaskMemFree(v9);
    *((_QWORD *)this + 18) = 0;
  }
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 21) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v11 = (unsigned __int64 *)((char *)this + 40);
  if ( *((_QWORD *)this + 4) )
  {
    for ( i = 0; i < *v11; ++i )
      PROGRESS_CALLBACK_INFO::`scalar deleting destructor'(
        (PROGRESS_CALLBACK_INFO *)(*((_QWORD *)this + 4) + 16 * i),
        v10);
    CoTaskMemFree(*((LPVOID *)this + 4));
    *((_QWORD *)this + 4) = 0;
  }
  *v11 = 0;
  *((_QWORD *)this + 7) = 0;
  CTSmartObj<CLPInstallHandler *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release((char *)this + 24);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x14003e450  mov     [rsp+arg_8], rbx
0x14003e455  mov     [rsp+arg_10], rsi
0x14003e45a  push    rdi
0x14003e45b  push    r13
0x14003e45d  push    r14
0x14003e45f  sub     rsp, 40h
0x14003e463  lea     rax, ??_7CLanguagePackInstallerSingleton@@6B@; const CLanguagePackInstallerSingleton::`vftable'
0x14003e46a  mov     rbx, rcx
0x14003e46d  mov     [rcx], rax
0x14003e470  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x14003e476  call    cs:__imp_TlsGetValue
0x14003e47c  mov     [rsp+58h+arg_0], 0FFFFFFFFh
0x14003e484  mov     rdi, rax
0x14003e487  mov     [rsp+58h+TlsValue], 0
0x14003e490  test    rax, rax
0x14003e493  jnz     short loc_14003E4AF
0x14003e495  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x14003e49b  lea     rdx, [rsp+58h+TlsValue]; lpTlsValue
0x14003e4a0  mov     [rsp+58h+arg_0], ecx
0x14003e4a4  lea     rdi, [rsp+58h+TlsValue]
0x14003e4a9  call    cs:__imp_TlsSetValue
0x14003e4af  inc     dword ptr [rdi]
0x14003e4b1  mov     eax, [rdi]
0x14003e4b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e4ba  lea     r14, WPP_GLOBAL_Control
0x14003e4c1  cmp     rcx, r14
0x14003e4c4  jz      loc_14003E556
0x14003e4ca  test    byte ptr [rcx+1Ch], 80h
0x14003e4ce  lea     r13, asc_140089BC0; "                                       "...
0x14003e4d5  mov     esi, 1DFh
0x14003e4da  jz      short loc_14003E517
0x14003e4dc  lea     edx, [rax+rax*4]
0x14003e4df  cmp     edx, 1E1h
0x14003e4e5  ja      short loc_14003E4F0
0x14003e4e7  mov     eax, edx
0x14003e4e9  mov     edx, esi
0x14003e4eb  sub     rdx, rax
0x14003e4ee  jmp     short loc_14003E4F2
0x14003e4f0  xor     edx, edx
0x14003e4f2  mov     rcx, [rcx+10h]
0x14003e4f6  lea     r9, [rdx+r13]
0x14003e4fa  mov     edx, 0Ah
0x14003e4ff  mov     [rsp+58h+var_38], rbx
0x14003e504  lea     r8, WPP_f36bffa08b0b30fbbd1fad32a50cf4e7_Traceguids
0x14003e50b  call    WPP_SF_sq
0x14003e510  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e517  cmp     rcx, r14
0x14003e51a  jz      short loc_14003E556
0x14003e51c  test    byte ptr [rcx+1Ch], 80h
0x14003e520  jz      short loc_14003E556
0x14003e522  mov     eax, [rdi]
0x14003e524  lea     edx, [rax+rax*4]
0x14003e527  cmp     edx, 1E1h
0x14003e52d  ja      short loc_14003E536
0x14003e52f  mov     eax, edx
0x14003e531  sub     rsi, rax
0x14003e534  jmp     short loc_14003E538
0x14003e536  xor     esi, esi
0x14003e538  mov     rcx, [rcx+10h]
0x14003e53c  lea     r9, [rsi+r13]
0x14003e540  mov     edx, 0Bh
0x14003e545  mov     [rsp+58h+var_38], rbx
0x14003e54a  lea     r8, WPP_f36bffa08b0b30fbbd1fad32a50cf4e7_Traceguids
0x14003e551  call    WPP_SF_sq
0x14003e556  dec     dword ptr [rdi]
0x14003e558  lea     rcx, [rsp+58h+arg_0]
0x14003e55d  call    ??1?$AutoTlsPtr@UTracingContext@TracingInternal@@@TracingInternal@@QEAA@XZ; TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(void)
0x14003e562  lea     rcx, [rbx+0B0h]; lpCriticalSection
0x14003e569  call    cs:__imp_DeleteCriticalSection
0x14003e56f  mov     rcx, [rbx+90h]; pv
0x14003e576  test    rcx, rcx
0x14003e579  jz      short loc_14003E58C
0x14003e57b  call    cs:__imp_CoTaskMemFree
0x14003e581  mov     qword ptr [rbx+90h], 0
0x14003e58c  lea     rcx, [rbx+68h]; lpCriticalSection
0x14003e590  mov     qword ptr [rbx+98h], 0
0x14003e59b  mov     qword ptr [rbx+0A8h], 0
0x14003e5a6  call    cs:__imp_DeleteCriticalSection
0x14003e5ac  lea     rcx, [rbx+40h]; lpCriticalSection
0x14003e5b0  call    cs:__imp_DeleteCriticalSection
0x14003e5b6  cmp     qword ptr [rbx+20h], 0
0x14003e5bb  lea     rdi, [rbx+28h]
0x14003e5bf  jz      short loc_14003E5F2
0x14003e5c1  xor     esi, esi
0x14003e5c3  cmp     [rdi], rsi
0x14003e5c6  jbe     short loc_14003E5E0
0x14003e5c8  mov     rcx, rsi
0x14003e5cb  shl     rcx, 4
0x14003e5cf  add     rcx, [rbx+20h]; this
0x14003e5d3  call    ??_GPROGRESS_CALLBACK_INFO@@QEAAPEAXI@Z; PROGRESS_CALLBACK_INFO::`scalar deleting destructor'(uint)
0x14003e5d8  inc     rsi
0x14003e5db  cmp     rsi, [rdi]
0x14003e5de  jb      short loc_14003E5C8
0x14003e5e0  mov     rcx, [rbx+20h]; pv
0x14003e5e4  call    cs:__imp_CoTaskMemFree
0x14003e5ea  mov     qword ptr [rbx+20h], 0
0x14003e5f2  lea     rcx, [rbx+18h]
0x14003e5f6  mov     qword ptr [rdi], 0
0x14003e5fd  mov     qword ptr [rbx+38h], 0
0x14003e605  call    ?Release@?$CTSmartObj@PEAVCLPInstallHandler@@V?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyNewMem@@@@@@QEAAXXZ; CTSmartObj<CLPInstallHandler *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release(void)
0x14003e60a  mov     rsi, [rsp+58h+arg_10]
0x14003e60f  mov     dword ptr [rbx+0Ch], 0C0000001h
0x14003e616  mov     rbx, [rsp+58h+arg_8]
0x14003e61b  add     rsp, 40h
0x14003e61f  pop     r14
0x14003e621  pop     r13
0x14003e623  pop     rdi
0x14003e624  retn
```
