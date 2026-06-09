# CreateSyncService(_GUID const &,void * *)

- ea: `0x18002070c`
- end: `0x180020858`
- name: `?CreateSyncService@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `332`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180020700`
- `0x180029810`
- `0x180037cb0`
- `0x18004e2e4`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18002070c`
- `0x180094010`

## string_xrefs

- `0x180020806`: `CreateSyncService`
- `0x18002083a`: `CreateSyncService`

## pseudocode

```c
__int64 __fastcall CreateSyncService(const struct _GUID *a1, void **a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  _QWORD *v6; // rax
  _QWORD *v7; // rdi

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      62,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CreateSyncService");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = -2147467261;
  if ( a2 )
  {
    v5 = -2147024882;
    v6 = SeAlloc(0x40u);
    v7 = v6;
    if ( v6 )
    {
      v6[7] = 0;
      *v6 = &CSyncServices::`vftable'{for `IApplicationSyncServices'};
      v6[1] = &CSyncServices::`vftable'{for `IProviderFilteredSyncServices2'};
      v6[2] = &CSyncServices::`vftable'{for `IProviderSyncServices2'};
      v6[3] = &CSyncServices::`vftable'{for `IProviderCustomFilteredSyncServices'};
      v6[4] = &CSyncServices::`vftable'{for `IClockVectorServices'};
      v6[5] = &CSyncServices::`vftable'{for `ISupportErrorInfo'};
      *((_DWORD *)v6 + 12) = 1;
      _InterlockedIncrement(&g_cRefThisDll);
      v5 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v6)(v6, a1, a2);
      (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      63,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CreateSyncService",
      v5);
  return v5;
}

```

## disassembly

```asm
0x18002070c  push    rbx
0x18002070e  push    rbp
0x18002070f  push    rsi
0x180020710  push    rdi
0x180020711  push    r14
0x180020713  sub     rsp, 30h
0x180020717  mov     rsi, rdx
0x18002071a  mov     rbp, rcx
0x18002071d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020724  lea     r14, WPP_GLOBAL_Control
0x18002072b  cmp     rcx, r14
0x18002072e  jnz     loc_1800207EE
0x180020734  mov     ebx, 80004003h
0x180020739  test    rsi, rsi
0x18002073c  jz      loc_1800207DC
0x180020742  mov     ecx, 40h ; '@'; unsigned __int64
0x180020747  mov     ebx, 8007000Eh
0x18002074c  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180020751  mov     rdi, rax
0x180020754  test    rax, rax
0x180020757  jz      short loc_1800207D5
0x180020759  lea     rax, ??_7CSyncServices@@6BIApplicationSyncServices@@@; const CSyncServices::`vftable'{for `IApplicationSyncServices'}
0x180020760  mov     qword ptr [rdi+38h], 0
0x180020768  mov     [rdi], rax
0x18002076b  lea     rax, ??_7CSyncServices@@6BIProviderFilteredSyncServices2@@@; const CSyncServices::`vftable'{for `IProviderFilteredSyncServices2'}
0x180020772  mov     [rdi+8], rax
0x180020776  lea     rax, ??_7CSyncServices@@6BIProviderSyncServices2@@@; const CSyncServices::`vftable'{for `IProviderSyncServices2'}
0x18002077d  mov     [rdi+10h], rax
0x180020781  lea     rax, ??_7CSyncServices@@6BIProviderCustomFilteredSyncServices@@@; const CSyncServices::`vftable'{for `IProviderCustomFilteredSyncServices'}
0x180020788  mov     [rdi+18h], rax
0x18002078c  lea     rax, ??_7CSyncServices@@6BIClockVectorServices@@@; const CSyncServices::`vftable'{for `IClockVectorServices'}
0x180020793  mov     [rdi+20h], rax
0x180020797  lea     rax, ??_7CSyncServices@@6BISupportErrorInfo@@@; const CSyncServices::`vftable'{for `ISupportErrorInfo'}
0x18002079e  mov     [rdi+28h], rax
0x1800207a2  mov     dword ptr [rdi+30h], 1
0x1800207a9  lock inc cs:?g_cRefThisDll@@3JC; long volatile g_cRefThisDll
0x1800207b0  mov     rax, [rdi]
0x1800207b3  mov     r8, rsi
0x1800207b6  mov     rdx, rbp
0x1800207b9  mov     rcx, rdi
0x1800207bc  mov     rax, [rax]
0x1800207bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207c4  mov     rcx, [rdi]
0x1800207c7  mov     ebx, eax
0x1800207c9  mov     rax, [rcx+10h]
0x1800207cd  mov     rcx, rdi
0x1800207d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800207dc  cmp     rcx, r14
0x1800207df  jnz     short loc_18002082A
0x1800207e1  mov     eax, ebx
0x1800207e3  add     rsp, 30h
0x1800207e7  pop     r14
0x1800207e9  pop     rdi
0x1800207ea  pop     rsi
0x1800207eb  pop     rbp
0x1800207ec  pop     rbx
0x1800207ed  retn
0x1800207ee  test    byte ptr [rcx+1Ch], 2
0x1800207f2  jz      loc_180020734
0x1800207f8  cmp     byte ptr [rcx+19h], 5
0x1800207fc  jb      loc_180020734
0x180020802  mov     rcx, [rcx+10h]
0x180020806  lea     r9, aCreatesyncserv; "CreateSyncService"
0x18002080d  mov     edx, 3Eh ; '>'
0x180020812  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x180020819  call    WPP_SF_s
0x18002081e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020825  jmp     loc_180020734
0x18002082a  test    byte ptr [rcx+1Ch], 2
0x18002082e  jz      short loc_1800207E1
0x180020830  cmp     byte ptr [rcx+19h], 5
0x180020834  jb      short loc_1800207E1
0x180020836  mov     rcx, [rcx+10h]
0x18002083a  lea     r9, aCreatesyncserv; "CreateSyncService"
0x180020841  mov     edx, 3Fh ; '?'
0x180020846  mov     [rsp+58h+var_38], ebx
0x18002084a  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x180020851  call    WPP_SF_sD
0x180020856  jmp     short loc_1800207E1
```
