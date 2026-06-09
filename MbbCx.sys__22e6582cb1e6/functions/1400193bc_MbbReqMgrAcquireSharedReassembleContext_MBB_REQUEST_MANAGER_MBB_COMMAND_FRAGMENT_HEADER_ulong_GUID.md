# MbbReqMgrAcquireSharedReassembleContext(_MBB_REQUEST_MANAGER *,_MBB_COMMAND_FRAGMENT_HEADER *,ulong,_GUID)

- ea: `0x1400193bc`
- end: `0x1400196a3`
- name: `?MbbReqMgrAcquireSharedReassembleContext@@YAPEAU_MBB_REASSEMBLE_CONTEXT@@PEAU_MBB_REQUEST_MANAGER@@PEAU_MBB_COMMAND_FRAGMENT_HEADER@@KU_GUID@@@Z`
- size: `743`
- prototype: `struct _MBB_REASSEMBLE_CONTEXT *__fastcall(struct _MBB_REQUEST_MANAGER *, struct _MBB_COMMAND_FRAGMENT_HEADER *, unsigned int, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140012900`
- `0x1400130b8`

## callees

- `0x140001db8`
- `0x140005644`
- `0x1400193bc`
- `0x14001a87c`
- `0x14001afd8`
- `0x14001b900`
- `0x14001fcf4`
- `0x14003e100`
- `0x140047e50`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400195b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001961f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400195b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001961f`

## pseudocode

```c
struct _MBB_REASSEMBLE_CONTEXT *__fastcall MbbReqMgrAcquireSharedReassembleContext(
        struct _MBB_REQUEST_MANAGER *a1,
        struct _MBB_COMMAND_FRAGMENT_HEADER *a2,
        unsigned int a3,
        struct _GUID *a4)
{
  bool v4; // zf
  unsigned __int64 v5; // rdi
  bool v9; // cf
  int v10; // edx
  int v11; // ecx
  char (near **CommandString)[32]; // rax
  int v13; // edx
  int v14; // ecx
  int v15; // eax
  int v16; // edx
  __int64 v17; // r8
  int v18; // ecx
  GUID v20; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v21[20]; // [rsp+50h] [rbp-20h] BYREF

  v4 = *((_DWORD *)a2 + 4) == 0;
  v5 = (unsigned __int64)a1 + 336;
  memset(v21, 0, sizeof(v21));
  if ( v4 )
  {
    if ( *(_DWORD *)a2 == -2147483645 )
    {
      if ( *((_DWORD *)a2 + 1) < 0x30u )
        goto LABEL_10;
      v9 = a3 < 0x30;
    }
    else
    {
      if ( *(_DWORD *)a2 != -2147483641 || *((_DWORD *)a2 + 1) < 0x2Cu )
        goto LABEL_10;
      v9 = a3 < 0x2C;
    }
    if ( !v9 )
    {
      *(_DWORD *)&v21[16] = *((_DWORD *)a2 + 9);
      *(_DWORD *)v21 = _byteswap_ulong(*((_DWORD *)a2 + 5));
      *(_WORD *)&v21[4] = __ROR2__(*((_WORD *)a2 + 12), 8);
      *(_WORD *)&v21[6] = __ROR2__(*((_WORD *)a2 + 13), 8);
      *(_QWORD *)&v21[8] = *(_QWORD *)((char *)a2 + 28);
    }
  }
LABEL_10:
  MbbReqMgrLockManager(a1);
  if ( *((_BYTE *)a1 + 328) == 1 )
  {
    v11 = *((_DWORD *)a2 + 2);
    if ( *(_DWORD *)(v5 + 36) == v11
      && *(_DWORD *)(v5 + 40) == *((_DWORD *)a2 + 3)
      && *(_DWORD *)(v5 + 44) == *((_DWORD *)a2 + 4) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 4;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          4,
          41,
          (__int64)WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids,
          v11);
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        CommandString = MbbUtilGetCommandString((struct _MBB_COMMAND *)v21);
        WPP_RECORDER_SF_DDs(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          4,
          42,
          (__int64)WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids,
          *((_DWORD *)a2 + 2),
          *(_DWORD *)(v5 + 36),
          (__int64)CommandString);
      }
      v5 = 0;
    }
  }
  else
  {
    v14 = *((_DWORD *)a2 + 4);
    if ( v14 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 4;
        WPP_RECORDER_SF_Ddd(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          4,
          44,
          (__int64)WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids,
          *((_DWORD *)a2 + 2),
          v14,
          *((_DWORD *)a2 + 3));
      }
      v5 = 0;
      goto LABEL_30;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 4;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        4,
        43,
        (__int64)WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids,
        *((_DWORD *)a2 + 2));
    }
    v15 = *(_DWORD *)&v21[16];
    *(_OWORD *)(v5 + 56) = *(_OWORD *)v21;
    *(_DWORD *)(v5 + 72) = v15;
    *(_DWORD *)(v5 + 36) = *((_DWORD *)a2 + 2);
    *(_DWORD *)(v5 + 40) = *((_DWORD *)a2 + 3);
    *((_BYTE *)a1 + 328) = 1;
  }
  if ( v5 )
  {
    *(_DWORD *)(v5 + 44) = *((_DWORD *)a2 + 4) + 1;
    if ( *((_DWORD *)a2 + 4) )
      v5 &= -(__int64)((unsigned __int8)MbbReqMgrTimerDisarm(a1, 1) != 0);
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 22, *((_BYTE *)a1 + 184));
    return (struct _MBB_REASSEMBLE_CONTEXT *)v5;
  }
LABEL_30:
  KeReleaseSpinLock((PKSPIN_LOCK)a1 + 22, *((_BYTE *)a1 + 184));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v16) = 4;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      4,
      45,
      (__int64)WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids,
      *((_DWORD *)a2 + 2));
  }
  v17 = *(_QWORD *)a1;
  v18 = *((_DWORD *)a2 + 2);
  v20 = *a4;
  MbbUtilSendMbimError(v18, 2, v17, &v20, (struct _MBB_COMMAND *)v21);
  return (struct _MBB_REASSEMBLE_CONTEXT *)v5;
}

```

## disassembly

```asm
0x1400193bc  push    rbp
0x1400193be  push    rbx
0x1400193bf  push    rsi
0x1400193c0  push    rdi
0x1400193c1  push    r12
0x1400193c3  push    r14
0x1400193c5  push    r15
0x1400193c7  mov     rbp, rsp
0x1400193ca  sub     rsp, 70h
0x1400193ce  mov     rax, cs:__security_cookie
0x1400193d5  xor     rax, rsp
0x1400193d8  mov     [rbp+var_8], rax
0x1400193dc  cmp     dword ptr [rdx+10h], 0
0x1400193e0  lea     rdi, [rcx+150h]
0x1400193e7  xorps   xmm0, xmm0
0x1400193ea  mov     dword ptr [rbp+var_20], 0
0x1400193f1  movups  xmmword ptr [rbp+var_20+4], xmm0
0x1400193f5  mov     r12, r9
0x1400193f8  mov     rbx, rdx
0x1400193fb  mov     r14, rcx
0x1400193fe  jnz     short loc_140019456
0x140019400  mov     eax, [rdx]
0x140019402  cmp     eax, 80000003h
0x140019407  jnz     short loc_140019415
0x140019409  cmp     dword ptr [rdx+4], 30h ; '0'
0x14001940d  jb      short loc_140019456
0x14001940f  cmp     r8d, 30h ; '0'
0x140019413  jmp     short loc_140019426
0x140019415  cmp     eax, 80000007h
0x14001941a  jnz     short loc_140019456
0x14001941c  cmp     dword ptr [rdx+4], 2Ch ; ','
0x140019420  jb      short loc_140019456
0x140019422  cmp     r8d, 2Ch ; ','
0x140019426  jb      short loc_140019456
0x140019428  mov     eax, [rdx+24h]
0x14001942b  mov     dword ptr [rbp+var_20+10h], eax
0x14001942e  mov     eax, [rdx+14h]
0x140019431  bswap   eax
0x140019433  mov     dword ptr [rbp+var_20], eax
0x140019436  movzx   eax, word ptr [rdx+18h]
0x14001943a  ror     ax, 8
0x14001943e  mov     word ptr [rbp+var_20+4], ax
0x140019442  movzx   eax, word ptr [rdx+1Ah]
0x140019446  ror     ax, 8
0x14001944a  mov     word ptr [rbp+var_20+6], ax
0x14001944e  mov     rax, [rdx+1Ch]
0x140019452  mov     qword ptr [rbp+var_20+8], rax
0x140019456  call    ?MbbReqMgrLockManager@@YAXPEAU_MBB_REQUEST_MANAGER@@@Z; MbbReqMgrLockManager(_MBB_REQUEST_MANAGER *)
0x14001945b  cmp     byte ptr [r14+148h], 1
0x140019463  jnz     loc_140019516
0x140019469  mov     ecx, [rbx+8]
0x14001946c  lea     r15, WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids
0x140019473  cmp     [rdi+24h], ecx
0x140019476  jnz     short loc_1400194C7
0x140019478  mov     eax, [rbx+0Ch]
0x14001947b  cmp     [rdi+28h], eax
0x14001947e  jnz     short loc_1400194C7
0x140019480  mov     eax, [rbx+10h]
0x140019483  cmp     [rdi+2Ch], eax
0x140019486  jnz     short loc_1400194C7
0x140019488  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001948f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140019496  jz      loc_140019581
0x14001949c  mov     [rsp+70h+var_48], ecx
0x1400194a0  mov     r9d, 29h ; ')'
0x1400194a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400194ad  mov     [rsp+70h+var_50], r15
0x1400194b2  lea     r8d, [r9-25h]
0x1400194b6  mov     rcx, [rcx+40h]
0x1400194ba  mov     dl, r8b
0x1400194bd  call    WPP_RECORDER_SF_d
0x1400194c2  jmp     loc_140019581
0x1400194c7  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400194ce  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400194d5  jz      short loc_140019512
0x1400194d7  lea     rcx, [rbp+var_20]; Source1
0x1400194db  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x1400194e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400194e7  mov     r9d, 2Ah ; '*'
0x1400194ed  mov     [rsp+70h+var_38], rax
0x1400194f2  mov     eax, [rdi+24h]
0x1400194f5  mov     [rsp+70h+var_40], eax
0x1400194f9  mov     eax, [rbx+8]
0x1400194fc  lea     r8d, [r9-26h]
0x140019500  mov     rcx, [rcx+40h]
0x140019504  mov     [rsp+70h+var_48], eax
0x140019508  mov     [rsp+70h+var_50], r15
0x14001950d  call    WPP_RECORDER_SF_DDs
0x140019512  xor     edi, edi
0x140019514  jmp     short loc_140019581
0x140019516  mov     ecx, [rbx+10h]
0x140019519  test    ecx, ecx
0x14001951b  jnz     loc_1400195C8
0x140019521  lea     rsi, WPP_RECORDER_INITIALIZED
0x140019528  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001952f  lea     r15, WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids
0x140019536  jz      short loc_14001955F
0x140019538  mov     eax, [rbx+8]
0x14001953b  lea     r8d, [rcx+4]
0x14001953f  lea     r9d, [rcx+2Bh]
0x140019543  mov     [rsp+70h+var_48], eax
0x140019547  mov     rcx, cs:WPP_GLOBAL_Control
0x14001954e  mov     dl, r8b
0x140019551  mov     [rsp+70h+var_50], r15
0x140019556  mov     rcx, [rcx+40h]
0x14001955a  call    WPP_RECORDER_SF_d
0x14001955f  mov     eax, dword ptr [rbp+var_20+10h]
0x140019562  movups  xmm0, xmmword ptr [rbp+var_20]
0x140019566  movups  xmmword ptr [rdi+38h], xmm0
0x14001956a  mov     [rdi+48h], eax
0x14001956d  mov     eax, [rbx+8]
0x140019570  mov     [rdi+24h], eax
0x140019573  mov     eax, [rbx+0Ch]
0x140019576  mov     [rdi+28h], eax
0x140019579  mov     byte ptr [r14+148h], 1
0x140019581  test    rdi, rdi
0x140019584  jz      loc_140019615
0x14001958a  mov     eax, [rbx+10h]
0x14001958d  inc     eax
0x14001958f  mov     [rdi+2Ch], eax
0x140019592  cmp     dword ptr [rbx+10h], 0
0x140019596  jz      short loc_1400195AD
0x140019598  mov     edx, 1
0x14001959d  mov     rcx, r14
0x1400195a0  call    ?MbbReqMgrTimerDisarm@@YAEPEAU_MBB_REQUEST_MANAGER@@W4MBB_TIMER_TYPE@@E@Z; MbbReqMgrTimerDisarm(_MBB_REQUEST_MANAGER *,MBB_TIMER_TYPE,uchar)
0x1400195a5  neg     al
0x1400195a7  sbb     rcx, rcx
0x1400195aa  and     rdi, rcx
0x1400195ad  lea     rcx, [r14+0B0h]; SpinLock
0x1400195b4  mov     dl, [rcx+8]; NewIrql
0x1400195b7  call    cs:__imp_KeReleaseSpinLock
0x1400195be  nop     dword ptr [rax+rax+00h]
0x1400195c3  jmp     loc_140019684
0x1400195c8  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400195cf  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400195d6  lea     r15, WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids
0x1400195dd  jz      short loc_140019613
0x1400195df  mov     eax, [rbx+0Ch]
0x1400195e2  mov     r9d, 2Ch ; ','
0x1400195e8  mov     dword ptr [rsp+70h+var_38], eax
0x1400195ec  mov     eax, [rbx+8]
0x1400195ef  mov     [rsp+70h+var_40], ecx
0x1400195f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400195fa  lea     r8d, [r9-28h]
0x1400195fe  mov     [rsp+70h+var_48], eax
0x140019602  mov     dl, r8b
0x140019605  mov     [rsp+70h+var_50], r15
0x14001960a  mov     rcx, [rcx+40h]
0x14001960e  call    WPP_RECORDER_SF_Ddd
0x140019613  xor     edi, edi
0x140019615  lea     rcx, [r14+0B0h]; SpinLock
0x14001961c  mov     dl, [rcx+8]; NewIrql
0x14001961f  call    cs:__imp_KeReleaseSpinLock
0x140019626  nop     dword ptr [rax+rax+00h]
0x14001962b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140019632  jz      short loc_14001965D
0x140019634  mov     rcx, cs:WPP_GLOBAL_Control
0x14001963b  mov     r9d, 2Dh ; '-'
0x140019641  mov     eax, [rbx+8]
0x140019644  mov     [rsp+70h+var_48], eax
0x140019648  mov     [rsp+70h+var_50], r15
0x14001964d  mov     rcx, [rcx+40h]
0x140019651  lea     r8d, [r9-29h]
0x140019655  mov     dl, r8b
0x140019658  call    WPP_RECORDER_SF_d
0x14001965d  movaps  xmm0, xmmword ptr [r12]
0x140019662  lea     rax, [rbp+var_20]
0x140019666  mov     r8, [r14]
0x140019669  lea     r9, [rbp+var_30]
0x14001966d  mov     ecx, [rbx+8]
0x140019670  mov     edx, 2
0x140019675  movdqa  [rbp+var_30], xmm0
0x14001967a  mov     [rsp+70h+var_50], rax
0x14001967f  call    ?MbbUtilSendMbimError@@YAXKW4_MBB_ERROR@@PEAU_MINIPORT_ADAPTER_CONTEXT@@U_GUID@@PEAU_MBB_COMMAND@@@Z; MbbUtilSendMbimError(ulong,_MBB_ERROR,_MINIPORT_ADAPTER_CONTEXT *,_GUID,_MBB_COMMAND *)
0x140019684  mov     rax, rdi
0x140019687  mov     rcx, [rbp+var_8]
0x14001968b  xor     rcx, rsp; StackCookie
0x14001968e  call    __security_check_cookie
0x140019693  add     rsp, 70h
0x140019697  pop     r15
0x140019699  pop     r14
0x14001969b  pop     r12
0x14001969d  pop     rdi
0x14001969e  pop     rsi
0x14001969f  pop     rbx
0x1400196a0  pop     rbp
0x1400196a1  retn
```
