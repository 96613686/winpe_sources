# Apx::ApfCircuitFactory::Initialize(_APX_CIRCUIT_FACTORY_CONFIG *)

- ea: `0x180011408`
- end: `0x1800116f4`
- name: `?Initialize@ApfCircuitFactory@Apx@@AEAAJPEAU_APX_CIRCUIT_FACTORY_CONFIG@@@Z`
- size: `748`
- prototype: `__int64 __fastcall(unsigned __int64 this, struct _APX_CIRCUIT_FACTORY_CONFIG *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180011cd0`

## callees

- `0x18000163c`
- `0x180001d30`
- `0x180009d28`
- `0x18000a12c`
- `0x18000caac`
- `0x18001051c`
- `0x180011260`
- `0x180011408`
- `0x180011e6c`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Apx::ApfCircuitFactory::Initialize(unsigned __int64 this, struct _APX_CIRCUIT_FACTORY_CONFIG *a2)
{
  __int64 v4; // rax
  int v5; // eax
  int v6; // esi
  _DWORD *v7; // rbx
  _OWORD *v8; // rax
  __int64 v9; // rax
  int IpcLinkMgr; // eax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v15; // [rsp+30h] [rbp-69h] BYREF
  __int64 v16; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v17[2]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v18[32]; // [rsp+50h] [rbp-49h] BYREF
  _QWORD *v19; // [rsp+70h] [rbp-29h]
  __int64 v20; // [rsp+78h] [rbp-21h]
  char *v21; // [rsp+80h] [rbp-19h]
  __int64 v22; // [rsp+88h] [rbp-11h]
  __int64 *v23; // [rsp+90h] [rbp-9h]
  __int64 v24; // [rsp+98h] [rbp-1h]
  __int64 *v25; // [rsp+A0h] [rbp+7h]
  __int64 v26; // [rsp+A8h] [rbp+Fh]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
  }
  if ( (*((_BYTE *)a2 + 4) & 1) != 0 )
    *(_DWORD *)(this + 16) |= 1u;
  v4 = *((_QWORD *)a2 + 2);
  if ( v4 )
  {
    *(_OWORD *)(this + 144) = *(_OWORD *)v4;
    *(_QWORD *)(this + 160) = *(_QWORD *)(v4 + 16);
  }
  v5 = Apx::ApfWorkItemQueue::Initialize((Apx::ApfWorkItemQueue *)(this + 168));
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = (_OWORD *)*((_QWORD *)a2 + 1);
    v7 = (_DWORD *)(this + 20);
    *(_OWORD *)(this + 120) = *v8;
    v9 = *(unsigned int *)(this + 56);
    *(_DWORD *)(this + 20) = 2;
    *(_DWORD *)(this + 20 + 4 * v9 + 4) = 2;
    if ( ++*(_DWORD *)(this + 56) >= 8u )
      *(_DWORD *)(this + 56) = 0;
    IpcLinkMgr = Apx::ApfCircuitFactory::GetIpcLinkMgr((Apx::ApfCircuitFactory *)this);
    v6 = IpcLinkMgr;
    if ( IpcLinkMgr >= 0 )
    {
      v11 = *(unsigned int *)(this + 56);
      *v7 = 3;
      v7[v11 + 1] = 3;
      if ( ++*(_DWORD *)(this + 56) >= 8u )
        *(_DWORD *)(this + 56) = 0;
      v6 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(this + 136) + 16LL))(*(_QWORD *)(this + 136));
      if ( v6 >= 0 )
      {
        v6 = 0;
        goto LABEL_32;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_qqd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          &WPP_88d8f9f30453351596b6a72932727db3_Traceguids,
          ~this,
          ~*(_QWORD *)(this + 136),
          v6);
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        &WPP_88d8f9f30453351596b6a72932727db3_Traceguids,
        ~this,
        IpcLinkMgr);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids, ~this, v5);
    }
    v7 = (_DWORD *)(this + 20);
  }
  v12 = (unsigned int)v7[9];
  *v7 = 7;
  v7[v12 + 1] = 7;
  if ( ++v7[9] >= 8u )
    v7[9] = 0;
LABEL_32:
  v13 = *((_QWORD *)ApxTelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v13 > 4u
    && (*(_QWORD *)(v13 + 16) & 0x400000000001LL) != 0
    && (*(_QWORD *)(v13 + 24) & 0x400000000001LL) == *(_QWORD *)(v13 + 24) )
  {
    LODWORD(v15) = v6;
    v25 = &v15;
    v23 = &v16;
    v21 = (char *)(this + 120);
    v26 = 4;
    v19 = v17;
    v24 = 8;
    v22 = 16;
    v20 = 8;
    ((void (__fastcall *)(__int64, char *, _QWORD, _QWORD, int, _BYTE *, __int64, unsigned __int64, __int64, _QWORD))tlgWriteTransfer_EventWriteTransfer)(
      v13,
      byte_18002E4EB,
      0,
      0,
      6,
      v18,
      v15,
      ~this,
      2048,
      v17[1]);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180011408  push    rbp
0x18001140a  push    rbx
0x18001140b  push    rsi
0x18001140c  push    rdi
0x18001140d  push    r12
0x18001140f  push    r13
0x180011411  lea     rbp, [rsp-2Fh]
0x180011416  sub     rsp, 0C8h
0x18001141d  mov     rax, cs:__security_cookie
0x180011424  xor     rax, rsp
0x180011427  mov     [rbp+57h+var_40], rax
0x18001142b  mov     rbx, rdx
0x18001142e  mov     rdi, rcx
0x180011431  mov     rcx, cs:WPP_GLOBAL_Control
0x180011438  lea     r12, WPP_GLOBAL_Control
0x18001143f  lea     r13, WPP_88d8f9f30453351596b6a72932727db3_Traceguids
0x180011446  cmp     rcx, r12
0x180011449  jz      short loc_180011468
0x18001144b  test    byte ptr [rcx+1Ch], 1
0x18001144f  jz      short loc_180011468
0x180011451  cmp     byte ptr [rcx+19h], 5
0x180011455  jb      short loc_180011468
0x180011457  mov     rcx, [rcx+10h]
0x18001145b  mov     edx, 11h
0x180011460  mov     r8, r13
0x180011463  call    WPP_SF_
0x180011468  test    byte ptr [rbx+4], 1
0x18001146c  jz      short loc_180011472
0x18001146e  or      dword ptr [rdi+10h], 1
0x180011472  mov     rax, [rbx+10h]
0x180011476  test    rax, rax
0x180011479  jz      short loc_180011492
0x18001147b  movups  xmm0, xmmword ptr [rax]
0x18001147e  movups  xmmword ptr [rdi+90h], xmm0
0x180011485  movsd   xmm1, qword ptr [rax+10h]
0x18001148a  movsd   qword ptr [rdi+0A0h], xmm1
0x180011492  lea     rcx, [rdi+0A8h]; this
0x180011499  call    ?Initialize@ApfWorkItemQueue@Apx@@QEAAJXZ; Apx::ApfWorkItemQueue::Initialize(void)
0x18001149e  mov     esi, eax
0x1800114a0  test    eax, eax
0x1800114a2  jns     short loc_1800114E0
0x1800114a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114ab  cmp     rcx, r12
0x1800114ae  jz      short loc_1800114D7
0x1800114b0  test    byte ptr [rcx+1Ch], 20h
0x1800114b4  jz      short loc_1800114D7
0x1800114b6  cmp     byte ptr [rcx+19h], 2
0x1800114ba  jb      short loc_1800114D7
0x1800114bc  mov     rcx, [rcx+10h]
0x1800114c0  mov     r9, rdi
0x1800114c3  not     r9
0x1800114c6  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1800114ca  mov     edx, 12h
0x1800114cf  mov     r8, r13
0x1800114d2  call    WPP_SF_qd
0x1800114d7  lea     rbx, [rdi+14h]
0x1800114db  jmp     loc_1800115D9
0x1800114e0  mov     rax, [rbx+8]
0x1800114e4  lea     rbx, [rdi+14h]
0x1800114e8  movups  xmm0, xmmword ptr [rax]
0x1800114eb  movdqu  xmmword ptr [rdi+78h], xmm0
0x1800114f0  mov     eax, [rbx+24h]
0x1800114f3  mov     dword ptr [rbx], 2
0x1800114f9  mov     dword ptr [rbx+rax*4+4], 2
0x180011501  inc     dword ptr [rbx+24h]
0x180011504  cmp     dword ptr [rbx+24h], 8
0x180011508  jb      short loc_180011511
0x18001150a  mov     dword ptr [rbx+24h], 0
0x180011511  mov     rcx, rdi; this
0x180011514  call    ?GetIpcLinkMgr@ApfCircuitFactory@Apx@@AEAAJXZ; Apx::ApfCircuitFactory::GetIpcLinkMgr(void)
0x180011519  mov     esi, eax
0x18001151b  test    eax, eax
0x18001151d  jns     short loc_180011560
0x18001151f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011526  cmp     rcx, r12
0x180011529  jz      loc_1800115D9
0x18001152f  test    byte ptr [rcx+1Ch], 20h
0x180011533  jz      loc_1800115D9
0x180011539  cmp     byte ptr [rcx+19h], 2
0x18001153d  jb      loc_1800115D9
0x180011543  mov     rcx, [rcx+10h]
0x180011547  mov     r9, rdi
0x18001154a  not     r9
0x18001154d  mov     dword ptr [rsp+0F0h+var_D0], eax
0x180011551  mov     edx, 13h
0x180011556  mov     r8, r13
0x180011559  call    WPP_SF_qd
0x18001155e  jmp     short loc_1800115D9
0x180011560  mov     eax, [rbx+24h]
0x180011563  mov     ecx, 3
0x180011568  mov     [rbx], ecx
0x18001156a  mov     [rbx+rax*4+4], ecx
0x18001156e  inc     dword ptr [rbx+24h]
0x180011571  cmp     dword ptr [rbx+24h], 8
0x180011575  jb      short loc_18001157E
0x180011577  mov     dword ptr [rbx+24h], 0
0x18001157e  mov     rcx, [rdi+88h]
0x180011585  mov     rax, [rcx]
0x180011588  mov     rax, [rax+10h]
0x18001158c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011591  mov     esi, eax
0x180011593  test    eax, eax
0x180011595  jns     short loc_1800115F9
0x180011597  mov     rcx, cs:WPP_GLOBAL_Control
0x18001159e  cmp     rcx, r12
0x1800115a1  jz      short loc_1800115D9
0x1800115a3  test    byte ptr [rcx+1Ch], 20h
0x1800115a7  jz      short loc_1800115D9
0x1800115a9  cmp     byte ptr [rcx+19h], 2
0x1800115ad  jb      short loc_1800115D9
0x1800115af  mov     rax, [rdi+88h]
0x1800115b6  mov     r9, rdi
0x1800115b9  mov     rcx, [rcx+10h]
0x1800115bd  not     rax
0x1800115c0  not     r9
0x1800115c3  mov     dword ptr [rsp+0F0h+var_C8], esi
0x1800115c7  mov     edx, 14h
0x1800115cc  mov     [rsp+0F0h+var_D0], rax
0x1800115d1  mov     r8, r13
0x1800115d4  call    WPP_SF_qqd
0x1800115d9  mov     eax, [rbx+24h]
0x1800115dc  mov     ecx, 7
0x1800115e1  mov     [rbx], ecx
0x1800115e3  mov     [rbx+rax*4+4], ecx
0x1800115e7  inc     dword ptr [rbx+24h]
0x1800115ea  cmp     dword ptr [rbx+24h], 8
0x1800115ee  jb      short loc_1800115FB
0x1800115f0  mov     dword ptr [rbx+24h], 0
0x1800115f7  jmp     short loc_1800115FB
0x1800115f9  xor     esi, esi
0x1800115fb  call    ?Instance@ApxTelemetryProvider@@KAPEAV1@XZ; ApxTelemetryProvider::Instance(void)
0x180011600  mov     rcx, [rax+8]
0x180011604  mov     eax, [rcx]
0x180011606  cmp     eax, 4
0x180011609  jbe     loc_1800116AD
0x18001160f  mov     rdx, [rcx+18h]
0x180011613  mov     r8, 400000000001h
0x18001161d  mov     rax, [rcx+10h]
0x180011621  test    r8, rax
0x180011624  jz      loc_1800116AD
0x18001162a  mov     rax, rdx
0x18001162d  and     rax, r8
0x180011630  cmp     rax, rdx
0x180011633  jnz     short loc_1800116AD
0x180011635  lea     rdx, [rbp+57h+var_C0]
0x180011639  mov     dword ptr [rbp+57h+var_C0], esi
0x18001163c  mov     [rbp+57h+var_50], rdx
0x180011640  mov     rax, rdi
0x180011643  not     rax
0x180011646  mov     [rbp+57h+var_B0], 800h
0x18001164e  mov     [rbp+57h+var_B8], rax
0x180011652  lea     rdx, [rbp+57h+var_B8]
0x180011656  lea     rax, [rdi+78h]
0x18001165a  mov     [rbp+57h+var_60], rdx
0x18001165e  mov     [rbp+57h+var_70], rax
0x180011662  lea     rdx, byte_18002E4EB
0x180011669  lea     rax, [rbp+57h+var_B0]
0x18001166d  mov     [rbp+57h+var_48], 4
0x180011675  mov     [rbp+57h+var_80], rax
0x180011679  xor     r9d, r9d
0x18001167c  lea     rax, [rbp+57h+var_A0]
0x180011680  mov     [rbp+57h+var_58], 8
0x180011688  mov     [rsp+0F0h+var_C8], rax
0x18001168d  xor     r8d, r8d
0x180011690  mov     dword ptr [rsp+0F0h+var_D0], 6
0x180011698  mov     [rbp+57h+var_68], 10h
0x1800116a0  mov     [rbp+57h+var_78], 8
0x1800116a8  call    _tlgWriteTransfer_EventWriteTransfer
0x1800116ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116b4  cmp     rcx, r12
0x1800116b7  jz      short loc_1800116D6
0x1800116b9  test    byte ptr [rcx+1Ch], 1
0x1800116bd  jz      short loc_1800116D6
0x1800116bf  cmp     byte ptr [rcx+19h], 5
0x1800116c3  jb      short loc_1800116D6
0x1800116c5  mov     rcx, [rcx+10h]
0x1800116c9  mov     edx, 15h
0x1800116ce  mov     r8, r13
0x1800116d1  call    WPP_SF_
0x1800116d6  mov     eax, esi
0x1800116d8  mov     rcx, [rbp+57h+var_40]
0x1800116dc  xor     rcx, rsp; StackCookie
0x1800116df  call    __security_check_cookie
0x1800116e4  add     rsp, 0C8h
0x1800116eb  pop     r13
0x1800116ed  pop     r12
0x1800116ef  pop     rdi
0x1800116f0  pop     rsi
0x1800116f1  pop     rbx
0x1800116f2  pop     rbp
0x1800116f3  retn
```
