# ChangeApplicationServices::Initialize(__MIDL___MIDL_itf_winsync_0000_0000_0002,ISyncSessionState *)

- ea: `0x180048250`
- end: `0x180048339`
- name: `?Initialize@ChangeApplicationServices@@UEAAJW4__MIDL___MIDL_itf_winsync_0000_0000_0002@@PEAUISyncSessionState@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(ChangeApplicationServices *__hidden this, enum __MIDL___MIDL_itf_winsync_0000_0000_0002, struct ISyncSessionState *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x1800477f0`
- `0x180048250`
- `0x180094010`

## string_xrefs

- `0x180048286`: `ChangeApplicationServices::Initialize`
- `0x180048310`: `ChangeApplicationServices::Initialize`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::Initialize(
        ChangeApplicationServices *this,
        unsigned int a2,
        struct ISyncSessionState *a3)
{
  PVOID *v6; // rcx
  int v7; // ebx
  __int64 v8; // rcx

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::Initialize");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 <= 2 )
  {
    v7 = ChangeApplicationServices::ChangeState((__int64)this, 1);
    if ( v7 >= 0 )
    {
      *((_DWORD *)this + 16) = a2;
      v8 = *((_QWORD *)this + 9);
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      *((_QWORD *)this + 9) = a3;
      if ( a3 )
        ((void (__fastcall *)(struct ISyncSessionState *))a3->lpVtbl->AddRef)(a3);
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v7 = -2147024809;
  }
  if ( v6 != &WPP_GLOBAL_Control && *((char *)v6 + 28) < 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      13,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::Initialize",
      v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180048250  push    rbx
0x180048252  push    rbp
0x180048253  push    rsi
0x180048254  push    rdi
0x180048255  push    r14
0x180048257  sub     rsp, 30h
0x18004825b  mov     rsi, r8
0x18004825e  mov     ebp, edx
0x180048260  mov     rdi, rcx
0x180048263  mov     rcx, cs:WPP_GLOBAL_Control
0x18004826a  lea     r14, WPP_GLOBAL_Control
0x180048271  cmp     rcx, r14
0x180048274  jz      short loc_1800482A5
0x180048276  test    byte ptr [rcx+1Ch], 80h
0x18004827a  jz      short loc_1800482A5
0x18004827c  cmp     byte ptr [rcx+19h], 5
0x180048280  jb      short loc_1800482A5
0x180048282  mov     rcx, [rcx+10h]
0x180048286  lea     r9, aChangeapplicat_28; "ChangeApplicationServices::Initialize"
0x18004828d  mov     edx, 0Ch
0x180048292  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180048299  call    WPP_SF_s
0x18004829e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800482a5  cmp     ebp, 2
0x1800482a8  jbe     short loc_1800482B1
0x1800482aa  mov     ebx, 80070057h
0x1800482af  jmp     short loc_1800482FB
0x1800482b1  mov     edx, 1
0x1800482b6  mov     rcx, rdi
0x1800482b9  call    ?ChangeState@ChangeApplicationServices@@AEAAJW4ChangeApplicationServicesState@@@Z; ChangeApplicationServices::ChangeState(ChangeApplicationServicesState)
0x1800482be  mov     ebx, eax
0x1800482c0  test    eax, eax
0x1800482c2  js      short loc_1800482F4
0x1800482c4  mov     [rdi+40h], ebp
0x1800482c7  mov     rcx, [rdi+48h]
0x1800482cb  test    rcx, rcx
0x1800482ce  jz      short loc_1800482DC
0x1800482d0  mov     rdx, [rcx]
0x1800482d3  mov     rax, [rdx+10h]
0x1800482d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482dc  mov     [rdi+48h], rsi
0x1800482e0  test    rsi, rsi
0x1800482e3  jz      short loc_1800482F4
0x1800482e5  mov     rax, [rsi]
0x1800482e8  mov     rcx, rsi
0x1800482eb  mov     rax, [rax+8]
0x1800482ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800482fb  cmp     rcx, r14
0x1800482fe  jz      short loc_18004832C
0x180048300  test    byte ptr [rcx+1Ch], 80h
0x180048304  jz      short loc_18004832C
0x180048306  cmp     byte ptr [rcx+19h], 5
0x18004830a  jb      short loc_18004832C
0x18004830c  mov     rcx, [rcx+10h]
0x180048310  lea     r9, aChangeapplicat_28; "ChangeApplicationServices::Initialize"
0x180048317  mov     edx, 0Dh
0x18004831c  mov     [rsp+58h+var_38], ebx
0x180048320  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180048327  call    WPP_SF_sD
0x18004832c  mov     eax, ebx
0x18004832e  add     rsp, 30h
0x180048332  pop     r14
0x180048334  pop     rdi
0x180048335  pop     rsi
0x180048336  pop     rbp
0x180048337  pop     rbx
0x180048338  retn
```
