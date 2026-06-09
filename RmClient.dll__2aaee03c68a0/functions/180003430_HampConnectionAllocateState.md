# HampConnectionAllocateState

- ea: `0x180003430`
- end: `0x180003970`
- name: `HampConnectionAllocateState`
- size: `1344`
- prototype: `__int64 __fastcall(__int64, void *, __int64, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001e00`
- `0x1800030a0`
- `0x180003170`
- `0x180003270`

## callees

- `0x180003430`
- `0x180003b50`
- `0x180003b80`
- `0x1800046e4`
- `0x18001ae8e`
- `0x18001aec0`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x180003852`
- `ntdll!RtlInitializeSRWLock` at `0x180003852`
- `ntdll!TpAllocWork` at `0x180003887`
- `ntdll!TpAllocWork` at `0x180003887`
- `ntdll!RtlAllocateHeap` at `0x18000381c`
- `ntdll!RtlAllocateHeap` at `0x18000381c`
- `RPCRT4!NdrClientCall3` at `0x180003608`
- `RPCRT4!NdrClientCall3` at `0x180003663`
- `RPCRT4!NdrClientCall3` at `0x180003695`
- `RPCRT4!NdrClientCall3` at `0x1800036d8`
- `RPCRT4!NdrClientCall3` at `0x18000370a`
- `RPCRT4!NdrClientCall3` at `0x18000373f`
- `RPCRT4!NdrClientCall3` at `0x180003775`
- `RPCRT4!NdrClientCall3` at `0x180003608`
- `RPCRT4!NdrClientCall3` at `0x180003663`
- `RPCRT4!NdrClientCall3` at `0x180003695`
- `RPCRT4!NdrClientCall3` at `0x1800036d8`
- `RPCRT4!NdrClientCall3` at `0x18000370a`
- `RPCRT4!NdrClientCall3` at `0x18000373f`
- `RPCRT4!NdrClientCall3` at `0x180003775`
- `RPCRT4!RpcBindingCreateW` at `0x180003563`
- `RPCRT4!RpcBindingCreateW` at `0x180003563`
- `RPCRT4!RpcBindingBind` at `0x18000357d`
- `RPCRT4!RpcBindingBind` at `0x18000357d`
- `RPCRT4!RpcBindingFree` at `0x1800037c4`
- `RPCRT4!RpcBindingFree` at `0x180003919`
- `RPCRT4!RpcBindingFree` at `0x1800037c4`
- `RPCRT4!RpcBindingFree` at `0x180003919`
- `RPCRT4!RpcExceptionFilter` at `0x18001b09e`
- `RPCRT4!RpcExceptionFilter` at `0x18001b09e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180003795`
- `RPCRT4!I_RpcMapWin32Status` at `0x180003795`

## pseudocode

```c
__int64 __fastcall HampConnectionAllocateState(__int64 a1, void *a2, __int64 a3, __int64 a4)
{
  RPC_STATUS v7; // eax
  void *Pointer; // rbx
  bool v9; // cc
  CLIENT_CALL_RETURN v10; // rax
  char v11; // si
  int v13; // ecx
  _QWORD *Heap; // rax
  _QWORD *v15; // rbx
  __int64 v16; // r12
  _QWORD *v17; // r15
  int v18; // r14d
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp-140h] BYREF
  RPC_BINDING_HANDLE v20; // [rsp+70h] [rbp-138h] BYREF
  __int64 v21; // [rsp+78h] [rbp-130h]
  CLIENT_CALL_RETURN v22; // [rsp+80h] [rbp-128h]
  CLIENT_CALL_RETURN v23; // [rsp+88h] [rbp-120h]
  CLIENT_CALL_RETURN v24; // [rsp+90h] [rbp-118h]
  CLIENT_CALL_RETURN v25; // [rsp+98h] [rbp-110h]
  CLIENT_CALL_RETURN v26; // [rsp+A0h] [rbp-108h]
  __int64 v27; // [rsp+A8h] [rbp-100h]
  __int64 v28; // [rsp+B0h] [rbp-F8h]
  RPC_BINDING_HANDLE_SECURITY_V1_W v29; // [rsp+B8h] [rbp-F0h] BYREF
  __int64 v30; // [rsp+E0h] [rbp-C8h] BYREF
  int v31; // [rsp+E8h] [rbp-C0h]
  int v32; // [rsp+ECh] [rbp-BCh]
  __int128 v33; // [rsp+F0h] [rbp-B8h]
  __int128 v34; // [rsp+100h] [rbp-A8h]
  __int64 v35; // [rsp+110h] [rbp-98h]
  RPC_BINDING_HANDLE_OPTIONS_V1 v36; // [rsp+118h] [rbp-90h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W v37; // [rsp+128h] [rbp-80h] BYREF

  v27 = a1;
  v28 = a4;
  v20 = 0;
  v21 = 0;
  Binding = 0;
  memset(&v37, 0, sizeof(v37));
  *(_QWORD *)&v36.ComTimeout = 5;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  *(_QWORD *)(&v29.Version + 1) = 0;
  HIDWORD(v29.ServerPrincName) = 0;
  v29.AuthIdentity = 0;
  v37.Version = 1;
  v37.ProtocolSequence = 3;
  *(_QWORD *)&v36.Version = 0x100000001LL;
  v30 = 5;
  v31 = 1;
  v32 = 3;
  v29.Version = 1;
  v29.AuthnLevel = 6;
  v29.AuthnSvc = 10;
  v29.SecurityQos = (RPC_SECURITY_QOS *)&v30;
  v7 = RpcBindingCreateW(&v37, &v29, &v36, &Binding);
  LODWORD(Pointer) = v7;
  v9 = v7 <= 0;
  if ( v7 || (v7 = RpcBindingBind(0, Binding, a2), LODWORD(Pointer) = v7, v9 = v7 <= 0, v7) )
  {
    if ( !v9 )
      LODWORD(Pointer) = (unsigned __int16)v7 | 0xC0070000;
  }
  else
  {
    v20 = Binding;
    Binding = 0;
    LODWORD(Pointer) = 0;
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( (int)Pointer < 0 )
  {
    v11 = 0;
    goto LABEL_19;
  }
  if ( *(_BYTE *)(a1 + 156) )
  {
    switch ( *(_BYTE *)(a1 + 156) )
    {
      case 1:
        Binding = 0;
        Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DEE0, 0, 0).Pointer;
        Binding = Pointer;
        break;
      case 2:
        v22.Simple = 0;
        v22.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DF70, 0, 0).Pointer;
        LODWORD(Pointer) = v22.Pointer;
        break;
      case 3:
        v23.Simple = 0;
        v10.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180020C70, 0, 0).Pointer;
        v23.Pointer = v10.Pointer;
        goto LABEL_9;
      case 4:
        v25.Simple = 0;
        v25.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DFA0, 0, 0).Pointer;
        LODWORD(Pointer) = v25.Pointer;
        break;
      case 5:
        v26.Simple = 0;
        v26.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001D4C0, 0, 0).Pointer;
        LODWORD(Pointer) = v26.Pointer;
        break;
      case 6:
        v24.Simple = 0;
        v24.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DD98, 0, 0).Pointer;
        LODWORD(Pointer) = v24.Pointer;
        break;
      default:
        LODWORD(Pointer) = -1073741127;
        break;
    }
  }
  else
  {
    *(_QWORD *)&v36.Version = 0;
    v10.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0).Pointer;
    *(CLIENT_CALL_RETURN *)&v36.Version = v10;
LABEL_9:
    LODWORD(Pointer) = v10.Pointer;
  }
  v11 = 1;
  if ( (int)Pointer >= 0 )
  {
    *(_QWORD *)(a1 + 8) = v21;
    v13 = *(unsigned __int8 *)(a1 + 156);
    if ( v13 != 3 )
    {
      if ( *(_BYTE *)(a1 + 156) )
      {
        if ( (unsigned int)(v13 - 1) >= 2 )
          goto LABEL_28;
      }
      else
      {
        LODWORD(Pointer) = HampConnectionDeserializeActivities(a1, a4);
        if ( (int)Pointer < 0 )
          goto LABEL_19;
      }
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x48u);
    v15 = Heap;
    if ( Heap )
    {
      v16 = a1 + 16;
      v17 = (_QWORD *)(a1 + 24);
      memset_0(Heap, 0, 0x48u);
      v15[6] = *(_QWORD *)(a1 + 16);
      RtlInitializeSRWLock(v15 + 4);
      v15[3] = v15 + 2;
      v15[2] = v15 + 2;
      v15[5] = HampIpcChannelWnfCallback;
      v15[1] = a1 + 24;
      *((_DWORD *)v15 + 16) &= ~1u;
      v18 = TpAllocWork(v15 + 7, RmpClientWnfMessageQueueWorker, v15, 0);
      if ( v18 >= 0 )
      {
        v18 = RmSubscriptionStart(v16, v15);
        if ( v18 >= 0 )
        {
          *v17 = v15;
          v15 = 0;
          v18 = 0;
        }
      }
    }
    else
    {
      v18 = -1073741801;
    }
    if ( v15 )
      RmpClientWnfDestroySubscription(v15);
    if ( v18 < 0 )
    {
      LODWORD(Pointer) = v18;
      goto LABEL_19;
    }
LABEL_28:
    LODWORD(Pointer) = 0;
  }
LABEL_19:
  if ( v11 )
    RpcBindingFree(&v20);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180003430  mov     r11, rsp
0x180003433  push    rbx
0x180003434  push    rsi
0x180003435  push    rdi
0x180003436  push    r12
0x180003438  push    r14
0x18000343a  push    r15
0x18000343c  sub     rsp, 178h
0x180003443  mov     rax, cs:__security_cookie
0x18000344a  xor     rax, rsp
0x18000344d  mov     [rsp+1A8h+var_48], rax
0x180003455  mov     r15, r9
0x180003458  mov     r12d, r8d
0x18000345b  mov     rsi, rdx
0x18000345e  mov     r14, rcx
0x180003461  mov     [rsp+1A8h+var_100], rcx
0x180003469  mov     [rsp+1A8h+var_F8], r9
0x180003471  xor     edi, edi
0x180003473  mov     [rsp+1A8h+var_138], rdi
0x180003478  mov     [rsp+1A8h+var_130], rdi
0x18000347d  mov     [rsp+1A8h+Binding], rdi
0x180003482  xorps   xmm0, xmm0
0x180003485  xor     eax, eax
0x180003487  movups  xmmword ptr [r11-80h], xmm0
0x18000348c  movups  xmmword ptr [r11-70h], xmm0
0x180003491  movups  xmmword ptr [r11-60h], xmm0
0x180003496  mov     [r11-50h], rax
0x18000349a  mov     qword ptr [r11-88h], 5
0x1800034a5  movdqu  [rsp+1A8h+var_B8], xmm0
0x1800034ae  xorps   xmm1, xmm1
0x1800034b1  movdqu  [rsp+1A8h+var_A8], xmm1
0x1800034ba  mov     [r11-98h], rdi
0x1800034c1  mov     [r11-0ECh], rdi
0x1800034c8  mov     [rsp+1A8h+var_E4], edi
0x1800034cf  mov     [r11-0D8h], rdi
0x1800034d6  mov     dword ptr [r11-80h], 1
0x1800034de  mov     dword ptr [r11-78h], 3
0x1800034e6  mov     dword ptr [rsp+1A8h+var_90], 1
0x1800034f1  mov     dword ptr [rsp+1A8h+var_90+4], 1
0x1800034fc  mov     qword ptr [r11-0C8h], 5
0x180003507  mov     [rsp+1A8h+var_C0], 1
0x180003512  mov     [rsp+1A8h+var_BC], 3
0x18000351d  mov     [rsp+1A8h+var_F0], 1
0x180003528  mov     [rsp+1A8h+var_E0], 6
0x180003533  mov     [rsp+1A8h+var_DC], 0Ah
0x18000353e  lea     rax, [r11-0C8h]
0x180003545  mov     [r11-0D0h], rax
0x18000354c  lea     r9, [rsp+1A8h+Binding]; Binding
0x180003551  lea     r8, [r11-90h]; Options
0x180003558  lea     rdx, [r11-0F0h]; Security
0x18000355f  lea     rcx, [r11-80h]; Template
0x180003563  call    cs:__imp_RpcBindingCreateW
0x180003569  mov     ebx, eax
0x18000356b  test    eax, eax
0x18000356d  jnz     loc_1800038FB
0x180003573  mov     r8, rsi; IfSpec
0x180003576  mov     rdx, [rsp+1A8h+Binding]; Binding
0x18000357b  xor     ecx, ecx; pAsync
0x18000357d  call    cs:__imp_RpcBindingBind
0x180003583  mov     ebx, eax
0x180003585  test    eax, eax
0x180003587  jnz     loc_1800038FB
0x18000358d  mov     r9, [rsp+1A8h+Binding]
0x180003592  mov     [rsp+1A8h+var_138], r9
0x180003597  mov     [rsp+1A8h+Binding], rdi
0x18000359c  mov     ebx, edi
0x18000359e  cmp     [rsp+1A8h+Binding], rdi
0x1800035a3  jnz     loc_180003914
0x1800035a9  test    ebx, ebx
0x1800035ab  js      loc_1800038B0
0x1800035b1  movzx   eax, byte ptr [r14+9Ch]
0x1800035b9  test    eax, eax
0x1800035bb  jnz     short loc_180003621
0x1800035bd  mov     r8, [r15]
0x1800035c0  mov     qword ptr [rsp+1A8h+var_90], rdi
0x1800035c8  lea     rax, [r14+10h]
0x1800035cc  lea     rcx, [r15+10h]
0x1800035d0  lea     rdx, [r15+8]
0x1800035d4  lea     r10, [rsp+1A8h+var_130]
0x1800035d9  mov     [rsp+1A8h+var_158], r10
0x1800035de  mov     [rsp+1A8h+var_160], rax
0x1800035e3  mov     [rsp+1A8h+var_168], rcx
0x1800035e8  mov     [rsp+1A8h+var_170], rdx
0x1800035ed  mov     [rsp+1A8h+var_178], r8
0x1800035f2  mov     dword ptr [rsp+1A8h+var_180], r12d
0x1800035f7  mov     [rsp+1A8h+var_188], r14
0x1800035fc  xor     r8d, r8d; pReturnValue
0x1800035ff  xor     edx, edx; nProcNum
0x180003601  lea     rcx, pProxyInfo; pProxyInfo
0x180003608  call    cs:__imp_NdrClientCall3
0x18000360e  mov     qword ptr [rsp+1A8h+var_90], rax
0x180003616  mov     ebx, eax
0x180003618  mov     [rsp+1A8h+var_148], eax
0x18000361c  jmp     loc_180003791
0x180003621  dec     eax; switch 6 cases
0x180003623  cmp     eax, 5
0x180003626  ja      def_18000363F; jumptable 000000018000363F default case
0x18000362c  cdqe
0x18000362e  lea     rdx, __ImageBase
0x180003635  mov     ecx, ds:(jpt_18000363F - 180000000h)[rdx+rax*4]
0x18000363c  add     rcx, rdx
0x18000363f  jmp     rcx; switch jump
0x180003641  mov     [rsp+1A8h+var_128], rdi; jumptable 000000018000363F case 2
0x180003649  lea     rax, [r14+10h]
0x18000364d  mov     [rsp+1A8h+var_180], rax
0x180003652  mov     [rsp+1A8h+var_188], r14
0x180003657  xor     r8d, r8d; pReturnValue
0x18000365a  xor     edx, edx; nProcNum
0x18000365c  lea     rcx, stru_18001DF70; pProxyInfo
0x180003663  call    cs:__imp_NdrClientCall3
0x180003669  mov     [rsp+1A8h+var_128], rax
0x180003671  mov     ebx, eax
0x180003673  mov     [rsp+1A8h+var_148], eax
0x180003677  jmp     loc_180003791
0x18000367c  mov     [rsp+1A8h+var_108], rdi; jumptable 000000018000363F case 5
0x180003684  mov     [rsp+1A8h+var_188], r14
0x180003689  xor     r8d, r8d; pReturnValue
0x18000368c  xor     edx, edx; nProcNum
0x18000368e  lea     rcx, stru_18001D4C0; pProxyInfo
0x180003695  call    cs:__imp_NdrClientCall3
0x18000369b  mov     [rsp+1A8h+var_108], rax
0x1800036a3  mov     ebx, eax
0x1800036a5  mov     [rsp+1A8h+var_148], eax
0x1800036a9  jmp     loc_180003791
0x1800036ae  mov     rcx, [r15]; jumptable 000000018000363F case 6
0x1800036b1  mov     [rsp+1A8h+var_118], rdi
0x1800036b9  lea     rax, [r14+10h]
0x1800036bd  mov     [rsp+1A8h+var_178], rax
0x1800036c2  mov     [rsp+1A8h+var_180], r14
0x1800036c7  mov     [rsp+1A8h+var_188], rcx
0x1800036cc  xor     r8d, r8d; pReturnValue
0x1800036cf  xor     edx, edx; nProcNum
0x1800036d1  lea     rcx, stru_18001DD98; pProxyInfo
0x1800036d8  call    cs:__imp_NdrClientCall3
0x1800036de  mov     [rsp+1A8h+var_118], rax
0x1800036e6  mov     ebx, eax
0x1800036e8  mov     [rsp+1A8h+var_148], eax
0x1800036ec  jmp     loc_180003791
0x1800036f1  mov     [rsp+1A8h+var_110], rdi; jumptable 000000018000363F case 4
0x1800036f9  mov     [rsp+1A8h+var_188], r14
0x1800036fe  xor     r8d, r8d; pReturnValue
0x180003701  xor     edx, edx; nProcNum
0x180003703  lea     rcx, stru_18001DFA0; pProxyInfo
0x18000370a  call    cs:__imp_NdrClientCall3
0x180003710  mov     [rsp+1A8h+var_110], rax
0x180003718  mov     ebx, eax
0x18000371a  mov     [rsp+1A8h+var_148], eax
0x18000371e  jmp     short loc_180003791
0x180003720  mov     [rsp+1A8h+Binding], rdi; jumptable 000000018000363F case 1
0x180003725  lea     rax, [r14+10h]
0x180003729  mov     [rsp+1A8h+var_180], rax
0x18000372e  mov     [rsp+1A8h+var_188], r14
0x180003733  xor     r8d, r8d; pReturnValue
0x180003736  xor     edx, edx; nProcNum
0x180003738  lea     rcx, stru_18001DEE0; pProxyInfo
0x18000373f  call    cs:__imp_NdrClientCall3
0x180003745  mov     rbx, rax
0x180003748  mov     [rsp+1A8h+Binding], rax
0x18000374d  mov     [rsp+1A8h+var_148], eax
0x180003751  jmp     short loc_180003791
0x180003753  mov     [rsp+1A8h+var_120], rdi; jumptable 000000018000363F case 3
0x18000375b  lea     rax, [r14+10h]
0x18000375f  mov     [rsp+1A8h+var_180], rax
0x180003764  mov     [rsp+1A8h+var_188], r14
0x180003769  xor     r8d, r8d; pReturnValue
0x18000376c  xor     edx, edx; nProcNum
0x18000376e  lea     rcx, stru_180020C70; pProxyInfo
0x180003775  call    cs:__imp_NdrClientCall3
0x18000377b  mov     [rsp+1A8h+var_120], rax
0x180003783  jmp     loc_180003616
0x180003788  mov     ebx, 0C00002B9h; jumptable 000000018000363F default case
0x18000378d  mov     [rsp+1A8h+var_148], ebx
0x180003791  jmp     short loc_1800037B3
0x180003793  mov     ecx, eax; Status
0x180003795  call    cs:__imp_I_RpcMapWin32Status
0x18000379b  mov     ebx, eax
0x18000379d  mov     [rsp+1A8h+var_148], eax
0x1800037a1  xor     edi, edi
0x1800037a3  mov     r14, [rsp+1A8h+var_100]
0x1800037ab  mov     r15, [rsp+1A8h+var_F8]
0x1800037b3  mov     sil, 1
0x1800037b6  test    ebx, ebx
0x1800037b8  jns     short loc_1800037ED
0x1800037ba  test    sil, sil
0x1800037bd  jz      short loc_1800037CA
0x1800037bf  lea     rcx, [rsp+1A8h+var_138]; Binding
0x1800037c4  call    cs:__imp_RpcBindingFree
0x1800037ca  mov     eax, ebx
0x1800037cc  mov     rcx, [rsp+1A8h+var_48]
0x1800037d4  xor     rcx, rsp; StackCookie
0x1800037d7  call    __security_check_cookie
0x1800037dc  add     rsp, 178h
0x1800037e3  pop     r15
0x1800037e5  pop     r14
0x1800037e7  pop     r12
0x1800037e9  pop     rdi
0x1800037ea  pop     rsi
0x1800037eb  pop     rbx
0x1800037ec  retn
0x1800037ed  mov     rax, [rsp+1A8h+var_130]
0x1800037f2  mov     [r14+8], rax
0x1800037f6  movzx   ecx, byte ptr [r14+9Ch]
0x1800037fe  cmp     ecx, 3
0x180003801  jnz     loc_1800038D5
0x180003807  mov     rcx, gs:60h
0x180003810  xor     edx, edx; Flags
0x180003812  mov     r8d, 48h ; 'H'; Size
0x180003818  mov     rcx, [rcx+30h]; HeapHandle
0x18000381c  call    cs:__imp_RtlAllocateHeap
0x180003822  mov     rbx, rax
0x180003825  test    rax, rax
0x180003828  jz      loc_180003940
0x18000382e  lea     r12, [r14+10h]
0x180003832  lea     r15, [r14+18h]
0x180003836  xor     edx, edx; Val
0x180003838  mov     r8d, 48h ; 'H'; Size
0x18000383e  mov     rcx, rax; void *
0x180003841  call    memset_0
0x180003846  mov     rax, [r12]
0x18000384a  mov     [rbx+30h], rax
0x18000384e  lea     rcx, [rbx+20h]
0x180003852  call    cs:__imp_RtlInitializeSRWLock
0x180003858  lea     rax, [rbx+10h]
0x18000385c  mov     [rax+8], rax
0x180003860  mov     [rax], rax
0x180003863  lea     rax, HampIpcChannelWnfCallback
0x18000386a  mov     [rbx+28h], rax
0x18000386e  mov     [rbx+8], r15
0x180003872  and     dword ptr [rbx+40h], 0FFFFFFFEh
0x180003876  lea     rcx, [rbx+38h]
0x18000387a  xor     r9d, r9d
0x18000387d  mov     r8, rbx
0x180003880  lea     rdx, RmpClientWnfMessageQueueWorker
0x180003887  call    cs:__imp_TpAllocWork
0x18000388d  mov     r14d, eax
0x180003890  test    eax, eax
0x180003892  jns     short loc_1800038B8
0x180003894  test    rbx, rbx
0x180003897  jnz     loc_18000394B
0x18000389d  test    r14d, r14d
0x1800038a0  js      short loc_1800038F3
0x1800038a2  mov     r14d, edi
0x1800038a5  test    edi, edi
0x1800038a7  js      short loc_1800038F3
0x1800038a9  mov     ebx, edi
0x1800038ab  jmp     loc_1800037BA
0x1800038b0  xor     sil, sil
0x1800038b3  jmp     loc_1800037BA
0x1800038b8  mov     rdx, rbx
0x1800038bb  mov     rcx, r12
0x1800038be  call    RmSubscriptionStart
0x1800038c3  mov     r14d, eax
0x1800038c6  test    eax, eax
0x1800038c8  js      short loc_180003894
0x1800038ca  mov     [r15], rbx
0x1800038cd  mov     rbx, rdi
0x1800038d0  mov     r14d, edi
0x1800038d3  jmp     short loc_180003894
0x1800038d5  test    ecx, ecx
0x1800038d7  jnz     short loc_180003929
0x1800038d9  mov     rdx, r15
0x1800038dc  mov     rcx, r14
0x1800038df  call    HampConnectionDeserializeActivities
0x1800038e4  mov     ebx, eax
0x1800038e6  test    eax, eax
0x1800038e8  jns     loc_180003807
0x1800038ee  jmp     loc_1800037BA
0x1800038f3  mov     ebx, r14d
0x1800038f6  jmp     loc_1800037BA
0x1800038fb  mov     r9, [rsp+1A8h+var_138]
0x180003900  jle     loc_18000359E
0x180003906  movzx   ebx, ax
0x180003909  or      ebx, 0C0070000h
0x18000390f  jmp     loc_18000359E
0x180003914  lea     rcx, [rsp+1A8h+Binding]; Binding
0x180003919  call    cs:__imp_RpcBindingFree
0x18000391f  mov     r9, [rsp+1A8h+var_138]
0x180003924  jmp     loc_1800035A9
0x180003929  sub     ecx, 1
0x18000392c  jz      loc_180003807
0x180003932  cmp     ecx, 1
0x180003935  jz      loc_180003807
0x18000393b  jmp     loc_1800038A9
0x180003940  mov     r14d, 0C0000017h
0x180003946  jmp     loc_180003894
0x18000394b  mov     rcx, rbx
0x18000394e  call    RmpClientWnfDestroySubscription
0x180003953  jmp     loc_18000389D
0x18001b090  push    rbp
0x18001b092  sub     rsp, 60h
0x18001b096  mov     rbp, rdx
0x18001b099  mov     rcx, [rcx]
0x18001b09c  mov     ecx, [rcx]; ExceptionCode
0x18001b09e  call    cs:__imp_RpcExceptionFilter
0x18001b0a4  nop
0x18001b0a5  add     rsp, 60h
0x18001b0a9  pop     rbp
0x18001b0aa  retn
```
