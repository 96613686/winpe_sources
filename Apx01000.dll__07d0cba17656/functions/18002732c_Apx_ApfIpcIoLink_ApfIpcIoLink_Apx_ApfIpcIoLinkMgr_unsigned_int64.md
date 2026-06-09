# Apx::ApfIpcIoLink::ApfIpcIoLink(Apx::ApfIpcIoLinkMgr *,unsigned __int64)

- ea: `0x18002732c`
- end: `0x180027519`
- name: `??0ApfIpcIoLink@Apx@@AEAA@PEAVApfIpcIoLinkMgr@1@_K@Z`
- size: `493`
- prototype: `Apx::ApfIpcIoLink *__fastcall(Apx::ApfIpcIoLink *this, struct Apx::ApfIpcIoLinkMgr *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180025ee0`

## callees

- `0x18000a12c`
- `0x18000c368`
- `0x18000d3c0`
- `0x18002732c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800273b1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800273b1`

## string_xrefs

- `0x1800274ac`: `onecoreuap\drivers\wdm\audio\backpln\apx\class\ipclinks\apfipciolink.cpp`

## pseudocode

```c
Apx::ApfIpcIoLink *__fastcall Apx::ApfIpcIoLink::ApfIpcIoLink(
        Apx::ApfIpcIoLink *this,
        struct Apx::ApfIpcIoLinkMgr *a2,
        __int64 a3)
{
  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &Apx::ApfIpcLink::`vftable';
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = a3;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_749d1720de943cdcac02263c8ddb543c_Traceguids);
  }
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 16), 0xFA0u);
  *((_QWORD *)this + 10) = (char *)this + 72;
  *((_QWORD *)this + 9) = (char *)this + 72;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_749d1720de943cdcac02263c8ddb543c_Traceguids);
  }
  *(_QWORD *)this = &Apx::ApfIpcIoLink::`vftable';
  *((_QWORD *)this + 13) = a2;
  *((_QWORD *)this + 14) = 0;
  Apx::ApfWorkItemQueue::ApfWorkItemQueue((Apx::ApfIpcIoLink *)((char *)this + 120));
  *((_QWORD *)this + 30) = &Apx::ApfIpcIoLink_CommandProcess::`vftable';
  *((_QWORD *)this + 31) = this;
  *((_QWORD *)this + 32) = 0;
  Apx::ApfWorkItemQueue::ApfWorkItemQueue((Apx::ApfIpcIoLink *)((char *)this + 264));
  *((_QWORD *)this + 48) = &Apx::ApfIpcIoLink_EventProcess::`vftable';
  *((_QWORD *)this + 49) = this;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = 0;
  *((_BYTE *)this + 432) = 1;
  *((_DWORD *)this + 109) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
  }
  imp_ApxObjectReferenceActual(0, (Apx::ApfVerify *)~*((_QWORD *)this + 13));
  *((_QWORD *)this + 51) = (char *)this + 400;
  *((_QWORD *)this + 50) = (char *)this + 400;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
  }
  return this;
}

```

## disassembly

```asm
0x18002732c  mov     [rsp+arg_8], rbx
0x180027331  mov     [rsp+arg_10], rdi
0x180027336  mov     [rsp+arg_0], rcx
0x18002733b  push    r15
0x18002733d  sub     rsp, 30h
0x180027341  mov     rdi, rdx
0x180027344  mov     rbx, rcx
0x180027347  mov     dword ptr [rcx+8], 1
0x18002734e  lea     rax, ??_7ApfIpcLink@Apx@@6B@; const Apx::ApfIpcLink::`vftable'
0x180027355  mov     [rcx], rax
0x180027358  mov     qword ptr [rcx+38h], 0
0x180027360  mov     [rcx+40h], r8
0x180027364  mov     qword ptr [rcx+58h], 0
0x18002736c  mov     qword ptr [rcx+60h], 0
0x180027374  lea     r15, WPP_GLOBAL_Control
0x18002737b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027382  cmp     rcx, r15
0x180027385  jz      short loc_1800273A8
0x180027387  test    byte ptr [rcx+1Ch], 1
0x18002738b  jz      short loc_1800273A8
0x18002738d  cmp     byte ptr [rcx+19h], 5
0x180027391  jb      short loc_1800273A8
0x180027393  mov     edx, 0Ah
0x180027398  lea     r8, WPP_749d1720de943cdcac02263c8ddb543c_Traceguids
0x18002739f  mov     rcx, [rcx+10h]
0x1800273a3  call    WPP_SF_
0x1800273a8  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800273ac  mov     edx, 0FA0h; dwSpinCount
0x1800273b1  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800273b7  lea     rax, [rbx+48h]
0x1800273bb  mov     [rax+8], rax
0x1800273bf  mov     [rax], rax
0x1800273c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800273c9  cmp     rcx, r15
0x1800273cc  jz      short loc_1800273F0
0x1800273ce  test    byte ptr [rcx+1Ch], 1
0x1800273d2  jz      short loc_1800273F0
0x1800273d4  cmp     byte ptr [rcx+19h], 5
0x1800273d8  jb      short loc_1800273F0
0x1800273da  mov     edx, 0Bh
0x1800273df  lea     r8, WPP_749d1720de943cdcac02263c8ddb543c_Traceguids
0x1800273e6  mov     rcx, [rcx+10h]
0x1800273ea  call    WPP_SF_
0x1800273ef  nop
0x1800273f0  lea     rax, ??_7ApfIpcIoLink@Apx@@6B@; const Apx::ApfIpcIoLink::`vftable'
0x1800273f7  mov     [rbx], rax
0x1800273fa  mov     [rbx+68h], rdi
0x1800273fe  mov     qword ptr [rbx+70h], 0
0x180027406  lea     rcx, [rbx+78h]; this
0x18002740a  call    ??0ApfWorkItemQueue@Apx@@QEAA@XZ; Apx::ApfWorkItemQueue::ApfWorkItemQueue(void)
0x18002740f  nop
0x180027410  lea     rax, ??_7ApfIpcIoLink_CommandProcess@Apx@@6B@; const Apx::ApfIpcIoLink_CommandProcess::`vftable'
0x180027417  mov     [rbx+0F0h], rax
0x18002741e  mov     [rbx+0F8h], rbx
0x180027425  mov     qword ptr [rbx+100h], 0
0x180027430  lea     rcx, [rbx+108h]; this
0x180027437  call    ??0ApfWorkItemQueue@Apx@@QEAA@XZ; Apx::ApfWorkItemQueue::ApfWorkItemQueue(void)
0x18002743c  lea     rax, ??_7ApfIpcIoLink_EventProcess@Apx@@6B@; const Apx::ApfIpcIoLink_EventProcess::`vftable'
0x180027443  mov     [rbx+180h], rax
0x18002744a  mov     [rbx+188h], rbx
0x180027451  mov     qword ptr [rbx+1A0h], 0
0x18002745c  mov     qword ptr [rbx+1A8h], 0
0x180027467  mov     byte ptr [rbx+1B0h], 1
0x18002746e  mov     dword ptr [rbx+1B4h], 0
0x180027478  mov     rcx, cs:WPP_GLOBAL_Control
0x18002747f  cmp     rcx, r15
0x180027482  jz      short loc_1800274A5
0x180027484  test    byte ptr [rcx+1Ch], 1
0x180027488  jz      short loc_1800274A5
0x18002748a  cmp     byte ptr [rcx+19h], 5
0x18002748e  jb      short loc_1800274A5
0x180027490  mov     edx, 0Dh
0x180027495  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x18002749c  mov     rcx, [rcx+10h]
0x1800274a0  call    WPP_SF_
0x1800274a5  mov     rdx, [rbx+68h]
0x1800274a9  not     rdx; Apx::ApfVerify *
0x1800274ac  lea     rax, aOnecoreuapDriv_1; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x1800274b3  mov     [rsp+38h+var_18], rax
0x1800274b8  xor     ecx, ecx; this
0x1800274ba  lea     r9d, [rcx+59h]
0x1800274be  mov     r8d, 44787041h
0x1800274c4  call    imp_ApxObjectReferenceActual
0x1800274c9  lea     rax, [rbx+190h]
0x1800274d0  mov     [rax+8], rax
0x1800274d4  mov     [rax], rax
0x1800274d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800274de  cmp     rcx, r15
0x1800274e1  jz      short loc_180027505
0x1800274e3  test    byte ptr [rcx+1Ch], 1
0x1800274e7  jz      short loc_180027505
0x1800274e9  cmp     byte ptr [rcx+19h], 5
0x1800274ed  jb      short loc_180027505
0x1800274ef  mov     edx, 0Eh
0x1800274f4  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x1800274fb  mov     rcx, [rcx+10h]
0x1800274ff  call    WPP_SF_
0x180027504  nop
0x180027505  mov     rax, rbx
0x180027508  mov     rbx, [rsp+38h+arg_8]
0x18002750d  mov     rdi, [rsp+38h+arg_10]
0x180027512  add     rsp, 30h
0x180027516  pop     r15
0x180027518  retn
```
