# WskProIRPSocketConnect

- ea: `0x140060ec0`
- end: `0x140061304`
- name: `WskProIRPSocketConnect`
- size: `1092`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140032db0`

## callees

- `0x140005b60`
- `0x14000f980`
- `0x140010760`
- `0x14001087c`
- `0x140013030`
- `0x1400159e0`
- `0x140015a2c`
- `0x14002e43c`
- `0x14005eedc`
- `0x140060ec0`
- `0x140072920`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140060fbb`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140060fbb`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400611f9`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400611f9`
- `ntoskrnl!KeInitializeSpinLock` at `0x140061090`
- `ntoskrnl!KeInitializeSpinLock` at `0x140061090`
- `ntoskrnl!ObfReferenceObject` at `0x140060f9e`
- `ntoskrnl!ObfReferenceObject` at `0x140060f9e`
- `ntoskrnl!IofCompleteRequest` at `0x1400612da`
- `ntoskrnl!IofCompleteRequest` at `0x1400612da`
- `ntoskrnl!ObfDereferenceObject` at `0x140061208`
- `ntoskrnl!ObfDereferenceObject` at `0x140061208`

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
0x140060ec0  mov     [rsp-8+arg_0], rbx
0x140060ec5  mov     [rsp-8+arg_8], rdx
0x140060eca  push    rbp
0x140060ecb  push    rsi
0x140060ecc  push    rdi
0x140060ecd  push    r12
0x140060ecf  push    r13
0x140060ed1  push    r14
0x140060ed3  push    r15
0x140060ed5  lea     rbp, [rsp-27h]
0x140060eda  sub     rsp, 0C0h
0x140060ee1  mov     rbx, rdx
0x140060ee4  mov     r12, rcx
0x140060ee7  xor     edi, edi
0x140060ee9  lea     rcx, [rbp+57h+var_B0]; void *
0x140060eed  xor     edx, edx; Val
0x140060eef  mov     [rbp+57h+var_C0], rdi
0x140060ef3  mov     r8d, 80h; Size
0x140060ef9  call    memset
0x140060efe  mov     r13, [rbx+8]
0x140060f02  mov     r15, [rbx+10h]
0x140060f06  mov     eax, [r13+10h]
0x140060f0a  test    al, 1
0x140060f0c  jnz     loc_1400612C2
0x140060f12  lea     ecx, [rax+2]
0x140060f15  lock cmpxchg [r13+10h], ecx
0x140060f1b  jnz     short loc_140060F06
0x140060f1d  mov     byte ptr [r13+48h], 1
0x140060f22  mov     rax, [r15+8]
0x140060f26  mov     [rbp+57h+arg_18], rdi
0x140060f2a  mov     [rbp+57h+arg_10], rax
0x140060f2e  test    rax, rax
0x140060f31  jz      loc_1400612A2
0x140060f37  movzx   edx, word ptr [rax]
0x140060f3a  cmp     dx, 23h ; '#'
0x140060f3e  jnb     loc_1400612A2
0x140060f44  movzx   ecx, dx; af
0x140060f47  call    SOCKADDR_SIZE
0x140060f4c  cmp     al, 2
0x140060f4e  jbe     loc_1400612A2
0x140060f54  mov     rax, [r15+10h]
0x140060f58  mov     [rbp+57h+var_B8], rax
0x140060f5c  test    rax, rax
0x140060f5f  jz      loc_1400612A2
0x140060f65  movzx   r8d, word ptr [rax]
0x140060f69  cmp     r8w, 23h ; '#'
0x140060f6e  jnb     loc_1400612A2
0x140060f74  movzx   ecx, r8w; af
0x140060f78  call    SOCKADDR_SIZE
0x140060f7d  cmp     al, 2
0x140060f7f  jbe     loc_1400612A2
0x140060f85  cmp     dx, r8w
0x140060f89  jnz     loc_1400612A2
0x140060f8f  lea     rsi, [r15+30h]
0x140060f93  mov     r14b, dil
0x140060f96  mov     rcx, [rsi]; Object
0x140060f99  test    rcx, rcx
0x140060f9c  jz      short loc_140060FD3
0x140060f9e  call    cs:__imp_ObfReferenceObject
0x140060fa5  nop     dword ptr [rax+rax+00h]
0x140060faa  mov     rcx, [rsi]; Process
0x140060fad  mov     edx, 200h; PoolType
0x140060fb2  mov     r8d, 0C8h; Amount
0x140060fb8  mov     r14b, 1
0x140060fbb  call    cs:__imp_PsChargeProcessPoolQuota
0x140060fc2  nop     dword ptr [rax+rax+00h]
0x140060fc7  mov     edi, eax
0x140060fc9  test    eax, eax
0x140060fcb  js      loc_140061205
0x140060fd1  xor     edi, edi
0x140060fd3  mov     rcx, cs:WskProPplSocket
0x140060fda  call    PplAllocateFromLookasideList
0x140060fdf  mov     rbx, rax
0x140060fe2  test    rax, rax
0x140060fe5  jnz     short loc_140060FF1
0x140060fe7  mov     edi, 0C000009Ah
0x140060fec  jmp     loc_1400611E2
0x140060ff1  xor     edx, edx; Val
0x140060ff3  mov     r8d, 0C8h; Size
0x140060ff9  mov     rcx, rbx; void *
0x140060ffc  call    memset
0x140061001  mov     rax, [rsi]
0x140061004  mov     [rbx+0A8h], rax
0x14006100b  lea     rax, WskProAPIConnectionSocketDispatch
0x140061012  mov     [rbx+18h], rax
0x140061016  mov     eax, 0D0h
0x14006101b  mov     word ptr [rbx], 0ACE2h
0x140061020  and     ax, [r13+4Ah]
0x140061025  mov     [rbx+20h], ax
0x140061029  jz      short loc_14006103B
0x14006102b  cmp     [r15+28h], rdi
0x14006102f  jnz     short loc_14006103B
0x140061031  mov     edi, 0C000000Dh
0x140061036  jmp     loc_1400611D3
0x14006103b  mov     rcx, [r15+28h]
0x14006103f  mov     [rbx+48h], rcx
0x140061043  test    al, 40h
0x140061045  jz      short loc_14006104C
0x140061047  cmp     [rcx], rdi
0x14006104a  jz      short loc_140061031
0x14006104c  test    al, al
0x14006104e  jns     short loc_140061056
0x140061050  cmp     [rcx+8], rdi
0x140061054  jz      short loc_140061031
0x140061056  test    al, 10h
0x140061058  jz      short loc_140061060
0x14006105a  cmp     [rcx+10h], rdi
0x14006105e  jz      short loc_140061031
0x140061060  mov     byte ptr [rbx+2], 2
0x140061064  lea     rcx, [rbx+10h]; SpinLock
0x140061068  mov     rax, [r15+20h]
0x14006106c  mov     [rbx+40h], rax
0x140061070  lea     rax, [rbx+78h]
0x140061074  mov     dword ptr [rbx+8], 2
0x14006107b  mov     [rax+8], rax
0x14006107f  mov     [rax], rax
0x140061082  mov     dword ptr [rbx+0Ch], 1
0x140061089  mov     [rbx+0A0h], r13
0x140061090  call    cs:__imp_KeInitializeSpinLock
0x140061097  nop     dword ptr [rax+rax+00h]
0x14006109c  cmp     [r13+49h], dil
0x1400610a0  jnz     short loc_1400610E5
0x1400610a2  mov     rdx, [rbp+57h+arg_10]
0x1400610a6  lea     rax, [rbp+57h+var_C0]
0x1400610aa  movzx   ecx, word ptr [r15]
0x1400610ae  lea     rdi, [r15+4]
0x1400610b2  mov     r8d, [rdi]
0x1400610b5  mov     r9b, 1
0x1400610b8  mov     [rsp+0F0h+var_D0], rax
0x1400610bd  movzx   edx, word ptr [rdx]
0x1400610c0  call    AfdCheckTDIFilter
0x1400610c5  test    al, al
0x1400610c7  jz      short loc_1400610E5
0x1400610c9  mov     rax, [rbp+57h+var_C0]
0x1400610cd  mov     rdx, [rbp+57h+arg_8]
0x1400610d1  lea     r9, WskTdiTransport
0x1400610d8  mov     rcx, r9
0x1400610db  mov     [rbp+57h+arg_18], rcx
0x1400610df  mov     [rdx+10h], rax
0x1400610e3  jmp     short loc_140061139
0x1400610e5  mov     rax, [rbp+57h+arg_10]
0x1400610e9  lea     rdi, [r15+4]
0x1400610ed  movzx   edx, word ptr [r15]
0x1400610f1  mov     r8d, [rdi]
0x1400610f4  movzx   ecx, word ptr [rax]
0x1400610f7  call    AfdTlFindAndReferenceTransport
0x1400610fc  mov     [rbp+57h+arg_18], rax
0x140061100  mov     rcx, rax
0x140061103  test    rax, rax
0x140061106  jnz     short loc_14006112E
0x140061108  mov     rax, [rbp+57h+arg_10]
0x14006110c  mov     rcx, r13
0x14006110f  movzx   edx, word ptr [r15]
0x140061113  mov     r9d, [rdi]
0x140061116  movzx   r8d, word ptr [rax]
0x14006111a  call    AfdWskSearchClientTdiMap
0x14006111f  test    rax, rax
0x140061122  jnz     short loc_1400610CD
0x140061124  mov     edi, 0C000023Eh
0x140061129  jmp     loc_1400611D3
0x14006112e  mov     rdx, [rbp+57h+arg_8]
0x140061132  lea     r9, WskTdiTransport
0x140061139  mov     [rbx+30h], rcx
0x14006113d  mov     r8d, 20000000h
0x140061143  mov     rcx, [rbp+57h+arg_10]
0x140061147  movzx   eax, word ptr [rcx]
0x14006114a  mov     [rbx+0B8h], ax
0x140061151  lea     rax, WskProTLCreateConnectComplete
0x140061158  mov     [rbp+57h+var_B0], rax
0x14006115c  mov     [rbp+57h+var_A8], r12
0x140061160  movzx   eax, word ptr [rcx]
0x140061163  mov     [rbp+57h+var_98], ax
0x140061167  cmp     [rbx+30h], r9
0x14006116b  mov     eax, [rbp+57h+var_A0]
0x14006116e  cmovnz  eax, r8d
0x140061172  mov     [rbp+57h+var_A0], eax
0x140061175  movzx   eax, word ptr [r15]
0x140061179  mov     [rbp+57h+var_96], ax
0x14006117d  movzx   eax, word ptr [rdi]
0x140061180  mov     [rbp+57h+var_94], ax
0x140061184  mov     rax, [r15+30h]
0x140061188  mov     [rbp+57h+var_88], rax
0x14006118c  mov     rax, [r15+38h]
0x140061190  mov     [rbp+57h+var_80], rax
0x140061194  mov     rax, [r15+40h]
0x140061198  mov     [rbp+57h+var_78], rax
0x14006119c  lea     rax, WskProTLClientConnectDispatch
0x1400611a3  mov     [rbp+57h+var_40], rax
0x1400611a7  mov     rax, [rbp+57h+var_B8]
0x1400611ab  mov     [rbp+57h+var_58], rax
0x1400611af  mov     rax, cs:AfdInfiniteTimeout
0x1400611b6  mov     [rdx+8], rbx
0x1400611ba  cmp     byte ptr [r12+44h], 0
0x1400611c0  mov     [rbp+57h+var_68], rbx
0x1400611c4  mov     [rbp+57h+var_70], rcx
0x1400611c8  mov     [rbp+57h+var_50], rax
0x1400611cc  jz      short loc_140061219
0x1400611ce  mov     edi, 0C0000120h
0x1400611d3  mov     rcx, cs:WskProPplSocket
0x1400611da  mov     rdx, rbx
0x1400611dd  call    PplFreeToLookasideList
0x1400611e2  test    r14b, r14b
0x1400611e5  jz      loc_1400612A7
0x1400611eb  mov     rcx, [rsi]; Process
0x1400611ee  mov     edx, 200h; PoolType
0x1400611f3  mov     r8d, 0C8h; Amount
0x1400611f9  call    cs:__imp_PsReturnPoolQuota
0x140061200  nop     dword ptr [rax+rax+00h]
0x140061205  mov     rcx, [rsi]; Object
0x140061208  call    cs:__imp_ObfDereferenceObject
0x14006120f  nop     dword ptr [rax+rax+00h]
0x140061214  jmp     loc_1400612A7
0x140061219  mov     rax, [r12+0B8h]
0x140061221  lea     rdx, [rbp+57h+var_B0]
0x140061225  or      byte ptr [rax+3], 1
0x140061229  lea     rax, WskProCANCELTLConnect
0x140061230  mov     qword ptr [rbx+60h], 0
0x140061238  xchg    rax, [r12+68h]
0x14006123d  mov     rcx, [rbx+30h]
0x140061241  mov     rax, [rcx+28h]
0x140061245  mov     rcx, [rcx+20h]
0x140061249  mov     rax, [rax+28h]
0x14006124d  call    _guard_dispatch_icall
0x140061252  mov     edi, eax
0x140061254  lea     rax, WskTdiTransport
0x14006125b  cmp     [rbx+30h], rax
0x14006125f  jz      short loc_140061269
0x140061261  mov     rcx, [rbp+57h+var_48]
0x140061265  mov     [rbx+60h], rcx
0x140061269  or      ecx, 0FFFFFFFFh
0x14006126c  lock xadd [rbx+8], ecx
0x140061271  cmp     ecx, 1
0x140061274  jnz     short loc_14006127E
0x140061276  mov     rcx, rbx; Entry
0x140061279  call    WskProCleanupSocket
0x14006127e  mov     ebx, 103h
0x140061283  cmp     edi, ebx
0x140061285  jz      short loc_14006129E
0x140061287  mov     r9, [rbp+57h+var_38]
0x14006128b  mov     edx, edi
0x14006128d  mov     r8, [rbp+57h+var_60]
0x140061291  mov     rcx, [rbp+57h+var_A8]
0x140061295  mov     rax, [rbp+57h+var_B0]
0x140061299  call    _guard_dispatch_icall
0x14006129e  mov     eax, ebx
0x1400612a0  jmp     short loc_1400612E8
0x1400612a2  mov     edi, 0C0000141h
0x1400612a7  mov     rcx, r13
0x1400612aa  call    AfdWskDereferenceClient
0x1400612af  mov     rax, [rbp+57h+arg_18]
0x1400612b3  test    rax, rax
0x1400612b6  jz      short loc_1400612C7
0x1400612b8  mov     rcx, rax
0x1400612bb  call    AfdTlDereferenceTransport
0x1400612c0  jmp     short loc_1400612C7
0x1400612c2  mov     edi, 0C0000008h
0x1400612c7  xor     edx, edx; PriorityBoost
0x1400612c9  mov     qword ptr [r12+38h], 0
0x1400612d2  mov     rcx, r12; Irp
0x1400612d5  mov     [r12+30h], edi
0x1400612da  call    cs:__imp_IofCompleteRequest
0x1400612e1  nop     dword ptr [rax+rax+00h]
0x1400612e6  mov     eax, edi
0x1400612e8  mov     rbx, [rsp+0F0h+arg_0]
0x1400612f0  add     rsp, 0C0h
0x1400612f7  pop     r15
0x1400612f9  pop     r14
0x1400612fb  pop     r13
0x1400612fd  pop     r12
0x1400612ff  pop     rdi
0x140061300  pop     rsi
0x140061301  pop     rbp
0x140061302  retn
```
