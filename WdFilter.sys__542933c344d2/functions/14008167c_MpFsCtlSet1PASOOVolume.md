# MpFsCtlSet1PASOOVolume

- ea: `0x14008167c`
- end: `0x140081805`
- name: `MpFsCtlSet1PASOOVolume`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400448f0`

## callees

- `0x1400018a4`
- `0x1400118d0`
- `0x14008167c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14008176e`
- `ntoskrnl!ProbeForRead` at `0x14008176e`
- `ntoskrnl!IoThreadToProcess` at `0x1400816da`
- `ntoskrnl!IoThreadToProcess` at `0x140081702`
- `ntoskrnl!IoThreadToProcess` at `0x1400816da`
- `ntoskrnl!IoThreadToProcess` at `0x140081702`
- `FLTMGR!FltReleaseContext` at `0x1400817db`
- `FLTMGR!FltReleaseContext` at `0x1400817db`
- `FLTMGR!FltGetInstanceContext` at `0x14008179f`
- `FLTMGR!FltGetInstanceContext` at `0x14008179f`

## pseudocode

```c
__int64 __fastcall MpFsCtlSet1PASOOVolume(__int64 a1, __int64 a2)
{
  struct _KPROCESS *v5; // rbx
  struct _KPROCESS *v6; // rbx
  __int64 v7; // rax
  __int64 *v8; // rbx
  NTSTATUS InstanceContext; // ebx
  PFLT_CONTEXT v10; // rcx
  __int64 v11; // [rsp+20h] [rbp-38h]
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-28h] BYREF

  Context = 0;
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL) < 8u )
    return 3221225507LL;
  v5 = *(struct _KPROCESS **)(MpData + 232);
  if ( IoThreadToProcess(KeGetCurrentThread()) == v5
    || (v6 = *(struct _KPROCESS **)(MpData + 256), IoThreadToProcess(KeGetCurrentThread()) == v6) )
  {
    v7 = *(_QWORD *)(a1 + 16);
    v8 = *(__int64 **)(v7 + 48);
    ProbeForRead(v8, *(unsigned int *)(v7 + 32), 4u);
    v11 = *v8;
    InstanceContext = FltGetInstanceContext(*(PFLT_INSTANCE *)(a2 + 24), &Context);
    if ( InstanceContext >= 0 )
    {
      v10 = Context;
      if ( *((_DWORD *)Context + 30) == 13 )
      {
        InstanceContext = -1073741637;
      }
      else
      {
        if ( BYTE4(v11) == 1 )
          _InterlockedOr((volatile signed __int32 *)Context + 20, 0x40u);
        else
          _InterlockedAnd((volatile signed __int32 *)Context + 20, 0xFFFFFFBF);
        v10 = Context;
      }
      FltReleaseContext(v10);
    }
    return (unsigned int)InstanceContext;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        31,
        WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids,
        *(unsigned int *)(MpData + 868));
    return 3221225506LL;
  }
}

```

## disassembly

```asm
0x14008167c  mov     [rsp+arg_10], rbx
0x140081681  push    rsi
0x140081682  push    rdi
0x140081683  push    r14
0x140081685  sub     rsp, 40h
0x140081689  mov     rax, cs:__security_cookie
0x140081690  xor     rax, rsp
0x140081693  mov     [rsp+58h+var_20], rax
0x140081698  mov     rsi, rdx
0x14008169b  mov     r14, rcx
0x14008169e  mov     [rsp+58h+var_30], rdx
0x1400816a3  xor     edi, edi
0x1400816a5  mov     [rsp+58h+var_38], rdi
0x1400816aa  mov     [rsp+58h+Context], rdi
0x1400816af  mov     rax, [rcx+10h]
0x1400816b3  cmp     dword ptr [rax+20h], 8
0x1400816b7  jnb     short loc_1400816C3
0x1400816b9  mov     eax, 0C0000023h
0x1400816be  jmp     loc_1400817E9
0x1400816c3  mov     rcx, gs:188h; Thread
0x1400816cc  mov     rax, cs:MpData
0x1400816d3  mov     rbx, [rax+0E8h]
0x1400816da  call    cs:__imp_IoThreadToProcess
0x1400816e1  nop     dword ptr [rax+rax+00h]
0x1400816e6  cmp     rax, rbx
0x1400816e9  jz      short loc_14008175A
0x1400816eb  mov     rcx, gs:188h; Thread
0x1400816f4  mov     rax, cs:MpData
0x1400816fb  mov     rbx, [rax+100h]
0x140081702  call    cs:__imp_IoThreadToProcess
0x140081709  nop     dword ptr [rax+rax+00h]
0x14008170e  cmp     rax, rbx
0x140081711  jz      short loc_14008175A
0x140081713  lea     rax, WPP_GLOBAL_Control
0x14008171a  mov     rcx, cs:WPP_GLOBAL_Control
0x140081721  cmp     rcx, rax
0x140081724  jz      short loc_140081750
0x140081726  mov     eax, [rcx+2Ch]
0x140081729  test    al, 1
0x14008172b  jz      short loc_140081750
0x14008172d  mov     rcx, [rcx+18h]
0x140081731  mov     edx, 1Fh
0x140081736  mov     r9, cs:MpData
0x14008173d  mov     r9d, [r9+364h]
0x140081744  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x14008174b  call    WPP_SF_d
0x140081750  mov     eax, 0C0000022h
0x140081755  jmp     loc_1400817E9
0x14008175a  mov     rax, [r14+10h]
0x14008175e  mov     rbx, [rax+30h]
0x140081762  mov     edx, [rax+20h]; Length
0x140081765  mov     r8d, 4; Alignment
0x14008176b  mov     rcx, rbx; Address
0x14008176e  call    cs:__imp_ProbeForRead
0x140081775  nop     dword ptr [rax+rax+00h]
0x14008177a  mov     rax, [rbx]
0x14008177d  mov     [rsp+58h+var_38], rax
0x140081782  jmp     short loc_14008178B
0x140081784  mov     edi, eax
0x140081786  mov     rsi, [rsp+58h+var_30]
0x14008178b  test    edi, edi
0x14008178d  jns     short loc_140081796
0x14008178f  lfence
0x140081792  mov     eax, edi
0x140081794  jmp     short loc_1400817E9
0x140081796  lea     rdx, [rsp+58h+Context]; Context
0x14008179b  mov     rcx, [rsi+18h]; Instance
0x14008179f  call    cs:__imp_FltGetInstanceContext
0x1400817a6  nop     dword ptr [rax+rax+00h]
0x1400817ab  mov     ebx, eax
0x1400817ad  test    eax, eax
0x1400817af  js      short loc_1400817E7
0x1400817b1  mov     rcx, [rsp+58h+Context]
0x1400817b6  cmp     dword ptr [rcx+78h], 0Dh
0x1400817ba  jnz     short loc_1400817C3
0x1400817bc  mov     ebx, 0C00000BBh
0x1400817c1  jmp     short loc_1400817DB
0x1400817c3  cmp     byte ptr [rsp+58h+var_38+4], 1
0x1400817c8  jnz     short loc_1400817D1
0x1400817ca  lock or dword ptr [rcx+50h], 40h
0x1400817cf  jmp     short loc_1400817D6
0x1400817d1  lock and dword ptr [rcx+50h], 0FFFFFFBFh
0x1400817d6  mov     rcx, [rsp+58h+Context]; Context
0x1400817db  call    cs:__imp_FltReleaseContext
0x1400817e2  nop     dword ptr [rax+rax+00h]
0x1400817e7  mov     eax, ebx
0x1400817e9  mov     rcx, [rsp+58h+var_20]
0x1400817ee  xor     rcx, rsp; StackCookie
0x1400817f1  call    __security_check_cookie
0x1400817f6  mov     rbx, [rsp+58h+arg_10]
0x1400817fb  add     rsp, 40h
0x1400817ff  pop     r14
0x140081801  pop     rdi
0x140081802  pop     rsi
0x140081803  retn
```
