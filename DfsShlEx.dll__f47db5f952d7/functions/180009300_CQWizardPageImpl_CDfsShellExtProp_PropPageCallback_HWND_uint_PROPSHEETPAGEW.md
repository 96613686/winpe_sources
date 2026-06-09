# CQWizardPageImpl<CDfsShellExtProp>::PropPageCallback(HWND__ *,uint,_PROPSHEETPAGEW *)

- ea: `0x180009300`
- end: `0x180009382`
- name: `?PropPageCallback@?$CQWizardPageImpl@VCDfsShellExtProp@@@@SAIPEAUHWND__@@IPEAU_PROPSHEETPAGEW@@@Z`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800068ac`
- `0x180009300`
- `0x18000c010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180009320`
- `KERNEL32!GetCurrentThreadId` at `0x180009320`
- `KERNEL32!EnterCriticalSection` at `0x180009330`
- `KERNEL32!EnterCriticalSection` at `0x180009330`
- `KERNEL32!LeaveCriticalSection` at `0x18000934f`
- `KERNEL32!LeaveCriticalSection` at `0x18000934f`

## pseudocode

```c
__int64 __fastcall CQWizardPageImpl<CDfsShellExtProp>::PropPageCallback(__int64 a1, int a2, __int64 a3)
{
  __int64 v3; // rax
  _QWORD *v4; // rbx

  if ( a2 == 2 )
  {
    v3 = *(_QWORD *)(a3 + 48);
    v4 = (_QWORD *)(v3 + 16);
    if ( v3 == -16 || !v3 )
    {
      ATL::_AtlRaiseException(0xC0000005, 2u);
      JUMPOUT(0x180009381LL);
    }
    *v4 = v3;
    *(_DWORD *)(v3 + 24) = GetCurrentThreadId();
    EnterCriticalSection(&stru_180013368);
    v4[2] = qword_180013390;
    qword_180013390 = (__int64)v4;
    LeaveCriticalSection(&stru_180013368);
  }
  else if ( a2 == 1 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 48) + 40LL))(*(_QWORD *)(a3 + 48));
  }
  return 1;
}

```

## disassembly

```asm
0x180009300  push    rbx
0x180009302  sub     rsp, 20h
0x180009306  cmp     edx, 2
0x180009309  jnz     short loc_180009357
0x18000930b  mov     rax, [r8+30h]
0x18000930f  lea     rbx, [rax+10h]
0x180009313  test    rbx, rbx
0x180009316  jz      short loc_180009377
0x180009318  test    rax, rax
0x18000931b  jz      short loc_180009377
0x18000931d  mov     [rbx], rax
0x180009320  call    cs:__imp_GetCurrentThreadId
0x180009326  lea     rcx, stru_180013368; lpCriticalSection
0x18000932d  mov     [rbx+8], eax
0x180009330  call    cs:__imp_EnterCriticalSection
0x180009336  mov     rax, cs:qword_180013390
0x18000933d  lea     rcx, stru_180013368; lpCriticalSection
0x180009344  mov     [rbx+10h], rax
0x180009348  mov     cs:qword_180013390, rbx
0x18000934f  call    cs:__imp_LeaveCriticalSection
0x180009355  jmp     short loc_18000936C
0x180009357  cmp     edx, 1
0x18000935a  jnz     short loc_18000936C
0x18000935c  mov     rcx, [r8+30h]
0x180009360  mov     rdx, [rcx]
0x180009363  mov     rax, [rdx+28h]
0x180009367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000936c  mov     eax, 1
0x180009371  add     rsp, 20h
0x180009375  pop     rbx
0x180009376  retn
0x180009377  mov     ecx, 0C0000005h; unsigned int
0x18000937c  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
