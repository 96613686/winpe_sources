# Apx::ApfIpcIoLinkMgr::ApfIpcIoLinkMgr(_GUID const *,bool,void (*)(void *,bool,bool),void *)

- ea: `0x180025888`
- end: `0x1800259d0`
- name: `??0ApfIpcIoLinkMgr@Apx@@AEAA@PEBU_GUID@@_NP6AXPEAX11@Z2@Z`
- size: `328`
- prototype: `Apx::ApfIpcIoLinkMgr *__fastcall(Apx::ApfIpcIoLinkMgr *this, const struct _GUID *, char, void (*)(void *, bool, bool), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011260`

## callees

- `0x1800027c8`
- `0x18000a12c`
- `0x180025888`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800258fd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800258fd`

## pseudocode

```c
Apx::ApfIpcIoLinkMgr *__fastcall Apx::ApfIpcIoLinkMgr::ApfIpcIoLinkMgr(
        Apx::ApfIpcIoLinkMgr *this,
        const struct _GUID *a2,
        char a3,
        void (*a4)(void *, bool, bool),
        void *a5)
{
  __int128 v8; // xmm0

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &Apx::ApfIpcLinkMgr::`vftable';
  *((_QWORD *)this + 7) = Apx::ApfCircuitFactory::OnIpcReady;
  *((_QWORD *)this + 8) = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_908fdabb6ad03a658653e342fffc33fd_Traceguids);
  }
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 16), 0xFA0u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_908fdabb6ad03a658653e342fffc33fd_Traceguids);
  }
  *(_QWORD *)this = &Apx::ApfIpcIoLinkMgr::`vftable';
  v8 = (__int128)*a2;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *(_OWORD *)((char *)this + 72) = v8;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *((_BYTE *)this + 116) = a3;
  *((_BYTE *)this + 117) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
  memset_0((char *)this + 118, 0, 0x20Au);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
  return this;
}

```

## disassembly

```asm
0x180025888  push    rbx
0x18002588a  push    rsi
0x18002588b  push    rdi
0x18002588c  push    r15
0x18002588e  sub     rsp, 28h
0x180025892  lea     rax, ??_7ApfIpcLinkMgr@Apx@@6B@; const Apx::ApfIpcLinkMgr::`vftable'
0x180025899  mov     dword ptr [rcx+8], 1
0x1800258a0  mov     [rcx], rax
0x1800258a3  mov     dil, r8b
0x1800258a6  lea     rax, ?OnIpcReady@ApfCircuitFactory@Apx@@CAXPEAX_N1@Z; Apx::ApfCircuitFactory::OnIpcReady(void *,bool,bool)
0x1800258ad  mov     rsi, rdx
0x1800258b0  mov     [rcx+38h], rax
0x1800258b4  mov     rbx, rcx
0x1800258b7  mov     rax, [rsp+48h+arg_20]
0x1800258bc  mov     [rcx+40h], rax
0x1800258c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258c7  lea     r15, WPP_GLOBAL_Control
0x1800258ce  cmp     rcx, r15
0x1800258d1  jz      short loc_1800258F4
0x1800258d3  test    byte ptr [rcx+1Ch], 1
0x1800258d7  jz      short loc_1800258F4
0x1800258d9  cmp     byte ptr [rcx+19h], 5
0x1800258dd  jb      short loc_1800258F4
0x1800258df  mov     rcx, [rcx+10h]
0x1800258e3  lea     r8, WPP_908fdabb6ad03a658653e342fffc33fd_Traceguids
0x1800258ea  mov     edx, 0Ah
0x1800258ef  call    WPP_SF_
0x1800258f4  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800258f8  mov     edx, 0FA0h; dwSpinCount
0x1800258fd  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180025903  mov     rcx, cs:WPP_GLOBAL_Control
0x18002590a  cmp     rcx, r15
0x18002590d  jz      short loc_180025930
0x18002590f  test    byte ptr [rcx+1Ch], 1
0x180025913  jz      short loc_180025930
0x180025915  cmp     byte ptr [rcx+19h], 5
0x180025919  jb      short loc_180025930
0x18002591b  mov     rcx, [rcx+10h]
0x18002591f  lea     r8, WPP_908fdabb6ad03a658653e342fffc33fd_Traceguids
0x180025926  mov     edx, 0Bh
0x18002592b  call    WPP_SF_
0x180025930  lea     rax, ??_7ApfIpcIoLinkMgr@Apx@@6B@; const Apx::ApfIpcIoLinkMgr::`vftable'
0x180025937  mov     [rbx], rax
0x18002593a  xor     eax, eax
0x18002593c  movups  xmm0, xmmword ptr [rsi]
0x18002593f  mov     [rbx+58h], rax
0x180025943  mov     [rbx+60h], rax
0x180025947  movdqu  xmmword ptr [rbx+48h], xmm0
0x18002594c  mov     [rbx+68h], rax
0x180025950  mov     [rbx+70h], eax
0x180025953  mov     [rbx+74h], dil
0x180025957  mov     [rbx+75h], al
0x18002595a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025961  cmp     rcx, r15
0x180025964  jz      short loc_180025985
0x180025966  test    byte ptr [rcx+1Ch], 1
0x18002596a  jz      short loc_180025985
0x18002596c  cmp     byte ptr [rcx+19h], 5
0x180025970  jb      short loc_180025985
0x180025972  mov     rcx, [rcx+10h]
0x180025976  lea     edx, [rax+0Dh]
0x180025979  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180025980  call    WPP_SF_
0x180025985  lea     rcx, [rbx+76h]; void *
0x180025989  xor     edx, edx; Val
0x18002598b  mov     r8d, 20Ah; Size
0x180025991  call    memset_0
0x180025996  mov     rcx, cs:WPP_GLOBAL_Control
0x18002599d  cmp     rcx, r15
0x1800259a0  jz      short loc_1800259C3
0x1800259a2  test    byte ptr [rcx+1Ch], 1
0x1800259a6  jz      short loc_1800259C3
0x1800259a8  cmp     byte ptr [rcx+19h], 5
0x1800259ac  jb      short loc_1800259C3
0x1800259ae  mov     rcx, [rcx+10h]
0x1800259b2  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x1800259b9  mov     edx, 0Eh
0x1800259be  call    WPP_SF_
0x1800259c3  mov     rax, rbx
0x1800259c6  add     rsp, 28h
0x1800259ca  pop     r15
0x1800259cc  pop     rdi
0x1800259cd  pop     rsi
0x1800259ce  pop     rbx
0x1800259cf  retn
```
