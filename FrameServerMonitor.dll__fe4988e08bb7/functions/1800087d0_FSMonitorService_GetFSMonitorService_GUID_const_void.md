# FSMonitorService::GetFSMonitorService(_GUID const &,void * *)

- ea: `0x1800087d0`
- end: `0x1800088f1`
- name: `?GetFSMonitorService@FSMonitorService@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `289`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `25`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800067b0`
- `0x18001c7d0`
- `0x18001c8d0`
- `0x18001ca90`
- `0x18001cb70`
- `0x18001ccc0`
- `0x18001ce10`
- `0x18001cf40`
- `0x18001d080`
- `0x18001d210`
- `0x18001d430`
- `0x18001d570`
- `0x18001d6b0`
- `0x18001d7e0`
- `0x18001d8c0`
- `0x18001da20`
- `0x18001dae0`
- `0x18001dcc0`
- `0x18001dde0`
- `0x18001df00`
- `0x18001e020`
- `0x18001e1c0`
- `0x18001e330`
- `0x18001e490`
- `0x18001e5b0`

## callees

- `0x18000261c`
- `0x1800060f8`
- `0x180006a98`
- `0x180006d7c`
- `0x1800087d0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008826`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008826`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088e3`

## pseudocode

```c
__int64 __fastcall FSMonitorService::GetFSMonitorService(const struct _GUID *a1, void **a2)
{
  int v3; // ebx
  FSMonitorService *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx

  if ( a2 )
  {
    *a2 = 0;
    EnterCriticalSection(&stru_18005DCA8);
    v4 = (FSMonitorService *)qword_18005DCA0;
    if ( qword_18005DCA0 )
      goto LABEL_12;
    v4 = (FSMonitorService *)operator new(0x160u);
    if ( v4 )
      v4 = FSMonitorService::FSMonitorService(v4);
    v5 = qword_18005DCA0;
    qword_18005DCA0 = (__int64)v4;
    if ( v5 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      v4 = (FSMonitorService *)qword_18005DCA0;
    }
    if ( v4 )
    {
LABEL_12:
      v3 = (**(__int64 (__fastcall ***)(FSMonitorService *, GUID *, void **))v4)(
             v4,
             &GUID_9db93878_01eb_47f4_bc7b_5fb5bea77068,
             a2);
      if ( v3 >= 0 || !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_16;
      v6 = 12;
    }
    else
    {
      v3 = -2147024882;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
LABEL_16:
        LeaveCriticalSection(&stru_18005DCA8);
        return (unsigned int)v3;
      }
      v6 = 11;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, 0, v3);
    goto LABEL_16;
  }
  v3 = -2147467261;
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, 0, -2147467261);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800087d0  push    rbx
0x1800087d2  sub     rsp, 30h
0x1800087d6  mov     rbx, rdx
0x1800087d9  test    rdx, rdx
0x1800087dc  jnz     short loc_180008818
0x1800087de  mov     ebx, 80004003h
0x1800087e3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800087e8  cmp     al, 1
0x1800087ea  jb      loc_1800088E9
0x1800087f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087f7  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x1800087fe  mov     edx, 0Ah
0x180008803  mov     [rsp+38h+var_18], ebx
0x180008807  xor     r9d, r9d
0x18000880a  mov     rcx, [rcx+10h]
0x18000880e  call    WPP_SF_qD
0x180008813  jmp     loc_1800088E9
0x180008818  lea     rcx, stru_18005DCA8; lpCriticalSection
0x18000881f  mov     qword ptr [rdx], 0
0x180008826  call    cs:__imp_EnterCriticalSection
0x18000882c  mov     rax, cs:qword_18005DCA0
0x180008833  test    rax, rax
0x180008836  jnz     short loc_18000888F
0x180008838  mov     ecx, 160h; Size
0x18000883d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008842  test    rax, rax
0x180008845  jz      short loc_18000884F
0x180008847  mov     rcx, rax; this
0x18000884a  call    ??0FSMonitorService@@IEAA@XZ; FSMonitorService::FSMonitorService(void)
0x18000884f  mov     rcx, cs:qword_18005DCA0
0x180008856  mov     cs:qword_18005DCA0, rax
0x18000885d  test    rcx, rcx
0x180008860  jz      short loc_180008875
0x180008862  mov     rax, [rcx]
0x180008865  mov     rax, [rax+10h]
0x180008869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000886e  mov     rax, cs:qword_18005DCA0
0x180008875  test    rax, rax
0x180008878  jnz     short loc_18000888F
0x18000887a  mov     ebx, 8007000Eh
0x18000887f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180008884  cmp     al, 1
0x180008886  jb      short loc_1800088DC
0x180008888  mov     edx, 0Bh
0x18000888d  jmp     short loc_1800088BE
0x18000888f  mov     rcx, [rax]
0x180008892  lea     rdx, _GUID_9db93878_01eb_47f4_bc7b_5fb5bea77068
0x180008899  mov     r8, rbx
0x18000889c  mov     r9, [rcx]
0x18000889f  mov     rcx, rax
0x1800088a2  mov     rax, r9
0x1800088a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088aa  mov     ebx, eax
0x1800088ac  test    eax, eax
0x1800088ae  jns     short loc_1800088DC
0x1800088b0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800088b5  cmp     al, 1
0x1800088b7  jb      short loc_1800088DC
0x1800088b9  mov     edx, 0Ch
0x1800088be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088c5  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x1800088cc  xor     r9d, r9d
0x1800088cf  mov     [rsp+38h+var_18], ebx
0x1800088d3  mov     rcx, [rcx+10h]
0x1800088d7  call    WPP_SF_qD
0x1800088dc  lea     rcx, stru_18005DCA8; lpCriticalSection
0x1800088e3  call    cs:__imp_LeaveCriticalSection
0x1800088e9  mov     eax, ebx
0x1800088eb  add     rsp, 30h
0x1800088ef  pop     rbx
0x1800088f0  retn
```
