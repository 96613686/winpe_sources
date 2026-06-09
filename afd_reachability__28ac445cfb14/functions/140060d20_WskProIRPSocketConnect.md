# WskProIRPSocketConnect

- ea: `0x140060d20`
- end: `0x140061164`
- name: `WskProIRPSocketConnect`
- size: `1092`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140032d90`

## callees

- `0x140005b60`
- `0x14000f980`
- `0x140010760`
- `0x14001087c`
- `0x140013030`
- `0x1400159e0`
- `0x140015a2c`
- `0x14002e43c`
- `0x14005ed3c`
- `0x140060d20`
- `0x140072780`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140060e1b`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140060e1b`
- `ntoskrnl!PsReturnPoolQuota` at `0x140061059`
- `ntoskrnl!PsReturnPoolQuota` at `0x140061059`
- `ntoskrnl!KeInitializeSpinLock` at `0x140060ef0`
- `ntoskrnl!KeInitializeSpinLock` at `0x140060ef0`
- `ntoskrnl!ObfReferenceObject` at `0x140060dfe`
- `ntoskrnl!ObfReferenceObject` at `0x140060dfe`
- `ntoskrnl!IofCompleteRequest` at `0x14006113a`
- `ntoskrnl!IofCompleteRequest` at `0x14006113a`
- `ntoskrnl!ObfDereferenceObject` at `0x140061068`
- `ntoskrnl!ObfDereferenceObject` at `0x140061068`

## pseudocode

```c
__int64 __fastcall WskProIRPSocketConnect(PIRP Irp, __int64 a2)
{
  __int64 v4; // r13
  unsigned __int16 *v5; // r15
  signed __int32 v6; // eax
  ADDRESS_FAMILY *v7; // rax
  ADDRESS_FAMILY *v8; // rax
  __int16 v9; // dx
  __int16 v10; // r8
  PEPROCESS *v11; // rsi
  char v12; // r14
  void *v13; // rcx
  int v14; // edi
  char *v15; // rax
  char *v16; // rbx
  __int16 v17; // ax
  _QWORD *v18; // rcx
  int v19; // r9d
  _WORD *v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 *v23; // rcx
  int v24; // eax
  bool v25; // zf
  unsigned int v26; // edi
  __int64 v28; // [rsp+30h] [rbp-69h] BYREF
  ADDRESS_FAMILY *v29; // [rsp+38h] [rbp-61h]
  _QWORD v30[22]; // [rsp+40h] [rbp-59h] BYREF
  ADDRESS_FAMILY *v32; // [rsp+110h] [rbp+77h]
  __int64 *v33; // [rsp+118h] [rbp+7Fh]

  v28 = 0;
  memset(v30, 0, 0x80u);
  v4 = *(_QWORD *)(a2 + 8);
  v5 = *(unsigned __int16 **)(a2 + 16);
  do
  {
    v6 = *(_DWORD *)(v4 + 16);
    if ( (v6 & 1) != 0 )
    {
      v14 = -1073741816;
LABEL_51:
      Irp->IoStatus.Information = 0;
      Irp->IoStatus.Status = v14;
      IofCompleteRequest(Irp, 0);
      return (unsigned int)v14;
    }
  }
  while ( v6 != _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 16), v6 + 2, v6) );
  *(_BYTE *)(v4 + 72) = 1;
  v7 = (ADDRESS_FAMILY *)*((_QWORD *)v5 + 1);
  v33 = 0;
  v32 = v7;
  if ( !v7
    || *v7 >= 0x23u
    || SOCKADDR_SIZE(*v7) <= 2u
    || (v8 = (ADDRESS_FAMILY *)*((_QWORD *)v5 + 2), (v29 = v8) == 0)
    || *v8 >= 0x23u
    || SOCKADDR_SIZE(*v8) <= 2u
    || v9 != v10 )
  {
    v14 = -1073741503;
LABEL_48:
    AfdWskDereferenceClient(v4);
    if ( v33 )
      AfdTlDereferenceTransport(v33);
    goto LABEL_51;
  }
  v11 = (PEPROCESS *)(v5 + 24);
  v12 = 0;
  v13 = (void *)*((_QWORD *)v5 + 6);
  if ( v13 )
  {
    ObfReferenceObject(v13);
    v12 = 1;
    v14 = PsChargeProcessPoolQuota(*v11, (POOL_TYPE)512, 0xC8u);
    if ( v14 < 0 )
    {
LABEL_39:
      ObfDereferenceObject(*v11);
      goto LABEL_48;
    }
  }
  v15 = (char *)PplAllocateFromLookasideList((__int64)WskProPplSocket);
  v16 = v15;
  if ( !v15 )
  {
    v14 = -1073741670;
    goto LABEL_37;
  }
  memset(v15, 0, 0xC8u);
  *((_QWORD *)v16 + 21) = *v11;
  *((_QWORD *)v16 + 3) = &WskProAPIConnectionSocketDispatch;
  *(_WORD *)v16 = -21278;
  v17 = *(_WORD *)(v4 + 74) & 0xD0;
  *((_WORD *)v16 + 16) = v17;
  if ( v17 && !*((_QWORD *)v5 + 5)
    || (v18 = (_QWORD *)*((_QWORD *)v5 + 5), *((_QWORD *)v16 + 9) = v18, (v17 & 0x40) != 0) && !*v18
    || (v17 & 0x80u) != 0 && !v18[1]
    || (v17 & 0x10) != 0 && !v18[2] )
  {
    v14 = -1073741811;
LABEL_36:
    PplFreeToLookasideList((__int64)WskProPplSocket, v16);
LABEL_37:
    if ( !v12 )
      goto LABEL_48;
    PsReturnPoolQuota(*v11, (POOL_TYPE)512, 0xC8u);
    goto LABEL_39;
  }
  v16[2] = 2;
  *((_QWORD *)v16 + 8) = *((_QWORD *)v5 + 4);
  *((_DWORD *)v16 + 2) = 2;
  *((_QWORD *)v16 + 16) = v16 + 120;
  *((_QWORD *)v16 + 15) = v16 + 120;
  *((_DWORD *)v16 + 3) = 1;
  *((_QWORD *)v16 + 20) = v4;
  KeInitializeSpinLock((PKSPIN_LOCK)v16 + 2);
  if ( !*(_BYTE *)(v4 + 73) )
  {
    v20 = v5 + 2;
    LOBYTE(v19) = 1;
    if ( (unsigned __int8)AfdCheckTDIFilter(*v5, *v32, *((_DWORD *)v5 + 1), v19, (__int64)&v28) )
    {
      v21 = v28;
      goto LABEL_27;
    }
  }
  v20 = v5 + 2;
  v33 = (__int64 *)AfdTlFindAndReferenceTransport(*v32, *v5, *((unsigned int *)v5 + 1));
  v23 = v33;
  if ( v33 )
  {
    v22 = a2;
  }
  else
  {
    v21 = AfdWskSearchClientTdiMap(v4, *v5, *v32, *(unsigned int *)v20);
    if ( !v21 )
    {
      v14 = -1073741250;
      goto LABEL_36;
    }
LABEL_27:
    v22 = a2;
    v23 = WskTdiTransport;
    v33 = WskTdiTransport;
    *(_QWORD *)(a2 + 16) = v21;
  }
  *((_QWORD *)v16 + 6) = v23;
  *((_WORD *)v16 + 92) = *v32;
  v30[0] = WskProTLCreateConnectComplete;
  v30[1] = Irp;
  LOWORD(v30[3]) = *v32;
  v24 = v30[2];
  if ( *((__int64 **)v16 + 6) != WskTdiTransport )
    v24 = 0x20000000;
  LODWORD(v30[2]) = v24;
  WORD1(v30[3]) = *v5;
  WORD2(v30[3]) = *v20;
  v30[5] = *((_QWORD *)v5 + 6);
  v30[6] = *((_QWORD *)v5 + 7);
  v30[7] = *((_QWORD *)v5 + 8);
  v30[14] = WskProTLClientConnectDispatch;
  v30[11] = v29;
  *(_QWORD *)(v22 + 8) = v16;
  v25 = Irp->Cancel == 0;
  v30[9] = v16;
  v30[8] = v32;
  v30[12] = AfdInfiniteTimeout;
  if ( !v25 )
  {
    v14 = -1073741536;
    goto LABEL_36;
  }
  Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  *((_QWORD *)v16 + 12) = 0;
  _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)WskProCANCELTLConnect);
  v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)(*((_QWORD *)v16 + 6) + 40LL) + 40LL))(
          *(_QWORD *)(*((_QWORD *)v16 + 6) + 32LL),
          v30);
  if ( *((__int64 **)v16 + 6) != WskTdiTransport )
    *((_QWORD *)v16 + 12) = v30[13];
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 + 2, 0xFFFFFFFF) == 1 )
    WskProCleanupSocket(v16);
  if ( v26 != 259 )
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v30[0])(v30[1], v26, v30[10], v30[15]);
  return 259;
}

```

## disassembly

```asm
0x140060d20  mov     [rsp-8+arg_0], rbx
0x140060d25  mov     [rsp-8+arg_8], rdx
0x140060d2a  push    rbp
0x140060d2b  push    rsi
0x140060d2c  push    rdi
0x140060d2d  push    r12
0x140060d2f  push    r13
0x140060d31  push    r14
0x140060d33  push    r15
0x140060d35  lea     rbp, [rsp-27h]
0x140060d3a  sub     rsp, 0C0h
0x140060d41  mov     rbx, rdx
0x140060d44  mov     r12, rcx
0x140060d47  xor     edi, edi
0x140060d49  lea     rcx, [rbp+57h+var_B0]; void *
0x140060d4d  xor     edx, edx; Val
0x140060d4f  mov     [rbp+57h+var_C0], rdi
0x140060d53  mov     r8d, 80h; Size
0x140060d59  call    memset
0x140060d5e  mov     r13, [rbx+8]
0x140060d62  mov     r15, [rbx+10h]
0x140060d66  mov     eax, [r13+10h]
0x140060d6a  test    al, 1
0x140060d6c  jnz     loc_140061122
0x140060d72  lea     ecx, [rax+2]
0x140060d75  lock cmpxchg [r13+10h], ecx
0x140060d7b  jnz     short loc_140060D66
0x140060d7d  mov     byte ptr [r13+48h], 1
0x140060d82  mov     rax, [r15+8]
0x140060d86  mov     [rbp+57h+arg_18], rdi
0x140060d8a  mov     [rbp+57h+arg_10], rax
0x140060d8e  test    rax, rax
0x140060d91  jz      loc_140061102
0x140060d97  movzx   edx, word ptr [rax]
0x140060d9a  cmp     dx, 23h ; '#'
0x140060d9e  jnb     loc_140061102
0x140060da4  movzx   ecx, dx; af
0x140060da7  call    SOCKADDR_SIZE
0x140060dac  cmp     al, 2
0x140060dae  jbe     loc_140061102
0x140060db4  mov     rax, [r15+10h]
0x140060db8  mov     [rbp+57h+var_B8], rax
0x140060dbc  test    rax, rax
0x140060dbf  jz      loc_140061102
0x140060dc5  movzx   r8d, word ptr [rax]
0x140060dc9  cmp     r8w, 23h ; '#'
0x140060dce  jnb     loc_140061102
0x140060dd4  movzx   ecx, r8w; af
0x140060dd8  call    SOCKADDR_SIZE
0x140060ddd  cmp     al, 2
0x140060ddf  jbe     loc_140061102
0x140060de5  cmp     dx, r8w
0x140060de9  jnz     loc_140061102
0x140060def  lea     rsi, [r15+30h]
0x140060df3  mov     r14b, dil
0x140060df6  mov     rcx, [rsi]; Object
0x140060df9  test    rcx, rcx
0x140060dfc  jz      short loc_140060E33
0x140060dfe  call    cs:__imp_ObfReferenceObject
0x140060e05  nop     dword ptr [rax+rax+00h]
0x140060e0a  mov     rcx, [rsi]; Process
0x140060e0d  mov     edx, 200h; PoolType
0x140060e12  mov     r8d, 0C8h; Amount
0x140060e18  mov     r14b, 1
0x140060e1b  call    cs:__imp_PsChargeProcessPoolQuota
0x140060e22  nop     dword ptr [rax+rax+00h]
0x140060e27  mov     edi, eax
0x140060e29  test    eax, eax
0x140060e2b  js      loc_140061065
0x140060e31  xor     edi, edi
0x140060e33  mov     rcx, cs:WskProPplSocket
0x140060e3a  call    PplAllocateFromLookasideList
0x140060e3f  mov     rbx, rax
0x140060e42  test    rax, rax
0x140060e45  jnz     short loc_140060E51
0x140060e47  mov     edi, 0C000009Ah
0x140060e4c  jmp     loc_140061042
0x140060e51  xor     edx, edx; Val
0x140060e53  mov     r8d, 0C8h; Size
0x140060e59  mov     rcx, rbx; void *
0x140060e5c  call    memset
0x140060e61  mov     rax, [rsi]
0x140060e64  mov     [rbx+0A8h], rax
0x140060e6b  lea     rax, WskProAPIConnectionSocketDispatch
0x140060e72  mov     [rbx+18h], rax
0x140060e76  mov     eax, 0D0h
0x140060e7b  mov     word ptr [rbx], 0ACE2h
0x140060e80  and     ax, [r13+4Ah]
0x140060e85  mov     [rbx+20h], ax
0x140060e89  jz      short loc_140060E9B
0x140060e8b  cmp     [r15+28h], rdi
0x140060e8f  jnz     short loc_140060E9B
0x140060e91  mov     edi, 0C000000Dh
0x140060e96  jmp     loc_140061033
0x140060e9b  mov     rcx, [r15+28h]
0x140060e9f  mov     [rbx+48h], rcx
0x140060ea3  test    al, 40h
0x140060ea5  jz      short loc_140060EAC
0x140060ea7  cmp     [rcx], rdi
0x140060eaa  jz      short loc_140060E91
0x140060eac  test    al, al
0x140060eae  jns     short loc_140060EB6
0x140060eb0  cmp     [rcx+8], rdi
0x140060eb4  jz      short loc_140060E91
0x140060eb6  test    al, 10h
0x140060eb8  jz      short loc_140060EC0
0x140060eba  cmp     [rcx+10h], rdi
0x140060ebe  jz      short loc_140060E91
0x140060ec0  mov     byte ptr [rbx+2], 2
0x140060ec4  lea     rcx, [rbx+10h]; SpinLock
0x140060ec8  mov     rax, [r15+20h]
0x140060ecc  mov     [rbx+40h], rax
0x140060ed0  lea     rax, [rbx+78h]
0x140060ed4  mov     dword ptr [rbx+8], 2
0x140060edb  mov     [rax+8], rax
0x140060edf  mov     [rax], rax
0x140060ee2  mov     dword ptr [rbx+0Ch], 1
0x140060ee9  mov     [rbx+0A0h], r13
0x140060ef0  call    cs:__imp_KeInitializeSpinLock
0x140060ef7  nop     dword ptr [rax+rax+00h]
0x140060efc  cmp     [r13+49h], dil
0x140060f00  jnz     short loc_140060F45
0x140060f02  mov     rdx, [rbp+57h+arg_10]
0x140060f06  lea     rax, [rbp+57h+var_C0]
0x140060f0a  movzx   ecx, word ptr [r15]
0x140060f0e  lea     rdi, [r15+4]
0x140060f12  mov     r8d, [rdi]
0x140060f15  mov     r9b, 1
0x140060f18  mov     [rsp+0F0h+var_D0], rax
0x140060f1d  movzx   edx, word ptr [rdx]
0x140060f20  call    AfdCheckTDIFilter
0x140060f25  test    al, al
0x140060f27  jz      short loc_140060F45
0x140060f29  mov     rax, [rbp+57h+var_C0]
0x140060f2d  mov     rdx, [rbp+57h+arg_8]
0x140060f31  lea     r9, WskTdiTransport
0x140060f38  mov     rcx, r9
0x140060f3b  mov     [rbp+57h+arg_18], rcx
0x140060f3f  mov     [rdx+10h], rax
0x140060f43  jmp     short loc_140060F99
0x140060f45  mov     rax, [rbp+57h+arg_10]
0x140060f49  lea     rdi, [r15+4]
0x140060f4d  movzx   edx, word ptr [r15]
0x140060f51  mov     r8d, [rdi]
0x140060f54  movzx   ecx, word ptr [rax]
0x140060f57  call    AfdTlFindAndReferenceTransport
0x140060f5c  mov     [rbp+57h+arg_18], rax
0x140060f60  mov     rcx, rax
0x140060f63  test    rax, rax
0x140060f66  jnz     short loc_140060F8E
0x140060f68  mov     rax, [rbp+57h+arg_10]
0x140060f6c  mov     rcx, r13
0x140060f6f  movzx   edx, word ptr [r15]
0x140060f73  mov     r9d, [rdi]
0x140060f76  movzx   r8d, word ptr [rax]
0x140060f7a  call    AfdWskSearchClientTdiMap
0x140060f7f  test    rax, rax
0x140060f82  jnz     short loc_140060F2D
0x140060f84  mov     edi, 0C000023Eh
0x140060f89  jmp     loc_140061033
0x140060f8e  mov     rdx, [rbp+57h+arg_8]
0x140060f92  lea     r9, WskTdiTransport
0x140060f99  mov     [rbx+30h], rcx
0x140060f9d  mov     r8d, 20000000h
0x140060fa3  mov     rcx, [rbp+57h+arg_10]
0x140060fa7  movzx   eax, word ptr [rcx]
0x140060faa  mov     [rbx+0B8h], ax
0x140060fb1  lea     rax, WskProTLCreateConnectComplete
0x140060fb8  mov     [rbp+57h+var_B0], rax
0x140060fbc  mov     [rbp+57h+var_A8], r12
0x140060fc0  movzx   eax, word ptr [rcx]
0x140060fc3  mov     [rbp+57h+var_98], ax
0x140060fc7  cmp     [rbx+30h], r9
0x140060fcb  mov     eax, [rbp+57h+var_A0]
0x140060fce  cmovnz  eax, r8d
0x140060fd2  mov     [rbp+57h+var_A0], eax
0x140060fd5  movzx   eax, word ptr [r15]
0x140060fd9  mov     [rbp+57h+var_96], ax
0x140060fdd  movzx   eax, word ptr [rdi]
0x140060fe0  mov     [rbp+57h+var_94], ax
0x140060fe4  mov     rax, [r15+30h]
0x140060fe8  mov     [rbp+57h+var_88], rax
0x140060fec  mov     rax, [r15+38h]
0x140060ff0  mov     [rbp+57h+var_80], rax
0x140060ff4  mov     rax, [r15+40h]
0x140060ff8  mov     [rbp+57h+var_78], rax
0x140060ffc  lea     rax, WskProTLClientConnectDispatch
0x140061003  mov     [rbp+57h+var_40], rax
0x140061007  mov     rax, [rbp+57h+var_B8]
0x14006100b  mov     [rbp+57h+var_58], rax
0x14006100f  mov     rax, cs:AfdInfiniteTimeout
0x140061016  mov     [rdx+8], rbx
0x14006101a  cmp     byte ptr [r12+44h], 0
0x140061020  mov     [rbp+57h+var_68], rbx
0x140061024  mov     [rbp+57h+var_70], rcx
0x140061028  mov     [rbp+57h+var_50], rax
0x14006102c  jz      short loc_140061079
0x14006102e  mov     edi, 0C0000120h
0x140061033  mov     rcx, cs:WskProPplSocket
0x14006103a  mov     rdx, rbx
0x14006103d  call    PplFreeToLookasideList
0x140061042  test    r14b, r14b
0x140061045  jz      loc_140061107
0x14006104b  mov     rcx, [rsi]; Process
0x14006104e  mov     edx, 200h; PoolType
0x140061053  mov     r8d, 0C8h; Amount
0x140061059  call    cs:__imp_PsReturnPoolQuota
0x140061060  nop     dword ptr [rax+rax+00h]
0x140061065  mov     rcx, [rsi]; Object
0x140061068  call    cs:__imp_ObfDereferenceObject
0x14006106f  nop     dword ptr [rax+rax+00h]
0x140061074  jmp     loc_140061107
0x140061079  mov     rax, [r12+0B8h]
0x140061081  lea     rdx, [rbp+57h+var_B0]
0x140061085  or      byte ptr [rax+3], 1
0x140061089  lea     rax, WskProCANCELTLConnect
0x140061090  mov     qword ptr [rbx+60h], 0
0x140061098  xchg    rax, [r12+68h]
0x14006109d  mov     rcx, [rbx+30h]
0x1400610a1  mov     rax, [rcx+28h]
0x1400610a5  mov     rcx, [rcx+20h]
0x1400610a9  mov     rax, [rax+28h]
0x1400610ad  call    _guard_dispatch_icall
0x1400610b2  mov     edi, eax
0x1400610b4  lea     rax, WskTdiTransport
0x1400610bb  cmp     [rbx+30h], rax
0x1400610bf  jz      short loc_1400610C9
0x1400610c1  mov     rcx, [rbp+57h+var_48]
0x1400610c5  mov     [rbx+60h], rcx
0x1400610c9  or      ecx, 0FFFFFFFFh
0x1400610cc  lock xadd [rbx+8], ecx
0x1400610d1  cmp     ecx, 1
0x1400610d4  jnz     short loc_1400610DE
0x1400610d6  mov     rcx, rbx; Entry
0x1400610d9  call    WskProCleanupSocket
0x1400610de  mov     ebx, 103h
0x1400610e3  cmp     edi, ebx
0x1400610e5  jz      short loc_1400610FE
0x1400610e7  mov     r9, [rbp+57h+var_38]
0x1400610eb  mov     edx, edi
0x1400610ed  mov     r8, [rbp+57h+var_60]
0x1400610f1  mov     rcx, [rbp+57h+var_A8]
0x1400610f5  mov     rax, [rbp+57h+var_B0]
0x1400610f9  call    _guard_dispatch_icall
0x1400610fe  mov     eax, ebx
0x140061100  jmp     short loc_140061148
0x140061102  mov     edi, 0C0000141h
0x140061107  mov     rcx, r13
0x14006110a  call    AfdWskDereferenceClient
0x14006110f  mov     rax, [rbp+57h+arg_18]
0x140061113  test    rax, rax
0x140061116  jz      short loc_140061127
0x140061118  mov     rcx, rax
0x14006111b  call    AfdTlDereferenceTransport
0x140061120  jmp     short loc_140061127
0x140061122  mov     edi, 0C0000008h
0x140061127  xor     edx, edx; PriorityBoost
0x140061129  mov     qword ptr [r12+38h], 0
0x140061132  mov     rcx, r12; Irp
0x140061135  mov     [r12+30h], edi
0x14006113a  call    cs:__imp_IofCompleteRequest
0x140061141  nop     dword ptr [rax+rax+00h]
0x140061146  mov     eax, edi
0x140061148  mov     rbx, [rsp+0F0h+arg_0]
0x140061150  add     rsp, 0C0h
0x140061157  pop     r15
0x140061159  pop     r14
0x14006115b  pop     r13
0x14006115d  pop     r12
0x14006115f  pop     rdi
0x140061160  pop     rsi
0x140061161  pop     rbp
0x140061162  retn
```
