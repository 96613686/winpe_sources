# WskProIRPSocket

- ea: `0x14003e7b0`
- end: `0x14003eba1`
- name: `WskProIRPSocket`
- size: `1009`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140032db0`

## callees

- `0x14001087c`
- `0x140013030`
- `0x1400159e0`
- `0x140015a2c`
- `0x14002e43c`
- `0x14003e7b0`
- `0x14005eedc`
- `0x140072920`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x14003e848`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x14003e848`
- `ntoskrnl!PsReturnPoolQuota` at `0x14003ea90`
- `ntoskrnl!PsReturnPoolQuota` at `0x14003ea90`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003e9e0`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003e9e0`
- `ntoskrnl!ObfReferenceObject` at `0x14003e82a`
- `ntoskrnl!ObfReferenceObject` at `0x14003e82a`
- `ntoskrnl!IofCompleteRequest` at `0x14003eb77`
- `ntoskrnl!IofCompleteRequest` at `0x14003eb77`
- `ntoskrnl!ObfDereferenceObject` at `0x14003eaa0`
- `ntoskrnl!ObfDereferenceObject` at `0x14003eaa0`

## pseudocode

```c
__int64 __fastcall WskProIRPSocket(PIRP Irp, __int64 a2)
{
  __int64 v4; // r14
  unsigned __int16 *v5; // rsi
  signed __int32 v6; // eax
  int v7; // ebx
  void *v8; // rcx
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  int v11; // eax
  __int16 v12; // ax
  _QWORD *v13; // rcx
  bool v14; // zf
  __int16 v15; // ax
  _QWORD *v16; // rcx
  __int16 v17; // ax
  __int64 (__fastcall **v18)(int, int, int, int, __int64, __int64, __int64, __int64, __int64, PIRP); // rax
  int v19; // r9d
  _WORD *v20; // r15
  _WORD *v21; // rbx
  __int64 v22; // rax
  __int64 *v23; // rcx
  int v24; // eax
  unsigned int v25; // eax
  _QWORD v27[10]; // [rsp+30h] [rbp-50h] BYREF
  char v28; // [rsp+C8h] [rbp+48h]
  __int64 v29; // [rsp+D0h] [rbp+50h] BYREF

  v29 = 0;
  memset(v27, 0, sizeof(v27));
  v4 = *(_QWORD *)(a2 + 8);
  v5 = *(unsigned __int16 **)(a2 + 16);
  do
  {
    v6 = *(_DWORD *)(v4 + 16);
    if ( (v6 & 1) != 0 )
    {
      v7 = -1073741816;
      goto LABEL_55;
    }
  }
  while ( v6 != _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 16), v6 + 2, v6) );
  *(_BYTE *)(v4 + 72) = 1;
  if ( *v5 >= 0x23u )
  {
    v7 = -1073741811;
    goto LABEL_49;
  }
  v8 = (void *)*((_QWORD *)v5 + 4);
  v28 = 0;
  if ( v8 )
  {
    ObfReferenceObject(v8);
    v28 = 1;
    v7 = PsChargeProcessPoolQuota(*((PEPROCESS *)v5 + 4), (POOL_TYPE)512, 0xC8u);
    if ( v7 < 0 )
    {
LABEL_48:
      ObfDereferenceObject(*((PVOID *)v5 + 4));
      goto LABEL_49;
    }
  }
  v9 = PplAllocateFromLookasideList((__int64)WskProPplSocket);
  v10 = v9;
  if ( !v9 )
  {
    v7 = -1073741670;
    goto LABEL_46;
  }
  memset(v9, 0, 0xC8u);
  v10[21] = *((_QWORD *)v5 + 4);
  v11 = *((_DWORD *)v5 + 2);
  if ( (v11 & 2) != 0 )
  {
    if ( (v11 & 0xD) == 0 )
    {
      *(_WORD *)v10 = -21278;
      v10[3] = &WskProAPIConnectionSocketDispatch;
      v12 = *(_WORD *)(v4 + 74) & 0xD0;
      *((_WORD *)v10 + 16) = v12;
      if ( !v12 || *((_QWORD *)v5 + 3) )
      {
        v13 = (_QWORD *)*((_QWORD *)v5 + 3);
        v10[9] = v13;
        if ( ((v12 & 0x40) == 0 || *v13) && ((v12 & 0x80u) == 0 || v13[1]) )
        {
          if ( (v12 & 0x10) != 0 )
          {
            v14 = v13[2] == 0;
            goto LABEL_21;
          }
          goto LABEL_38;
        }
      }
    }
LABEL_12:
    v7 = -1073741811;
LABEL_45:
    PplFreeToLookasideList((__int64)WskProPplSocket, v10);
LABEL_46:
    if ( v28 )
    {
      PsReturnPoolQuota(*((PEPROCESS *)v5 + 4), (POOL_TYPE)512, 0xC8u);
      goto LABEL_48;
    }
LABEL_49:
    AfdWskDereferenceClient(v4);
LABEL_55:
    Irp->IoStatus.Information = 0;
    Irp->IoStatus.Status = v7;
    IofCompleteRequest(Irp, 0);
    return (unsigned int)v7;
  }
  if ( (v11 & 1) != 0 )
  {
    if ( (v11 & 0xC) != 0 )
      goto LABEL_12;
    *(_WORD *)v10 = -21279;
    v10[3] = &WskProAPIListenSocketDispatch;
    v10[11] = v10 + 10;
    v10[10] = v10 + 10;
    v15 = 512;
  }
  else
  {
    if ( (v11 & 4) == 0 )
    {
      if ( (v11 & 8) != 0 )
      {
        v18 = &WskProAPIStreamSocketDispatch;
        *(_WORD *)v10 = -21276;
        *((_WORD *)v10 + 16) = 0;
      }
      else
      {
        v18 = &WskProAPIBasicSocketDispatch;
        *(_WORD *)v10 = -21280;
      }
      v10[3] = v18;
      v10[9] = *((_QWORD *)v5 + 3);
      goto LABEL_38;
    }
    if ( (v11 & 8) != 0 )
      goto LABEL_12;
    *(_WORD *)v10 = -21277;
    v10[3] = &WskProAPIDatagramSocketDispatch;
    v10[11] = v10 + 10;
    v10[10] = v10 + 10;
    v15 = 256;
  }
  v17 = *(_WORD *)(v4 + 74) & v15;
  *((_WORD *)v10 + 16) = v17;
  if ( v17 && !*((_QWORD *)v5 + 3) )
    goto LABEL_12;
  v16 = (_QWORD *)*((_QWORD *)v5 + 3);
  v10[9] = v16;
  if ( v17 )
  {
    v14 = *v16 == 0;
LABEL_21:
    if ( v14 )
      goto LABEL_12;
  }
LABEL_38:
  *((_BYTE *)v10 + 2) = 0;
  v10[8] = *((_QWORD *)v5 + 2);
  *((_DWORD *)v10 + 2) = 1;
  v10[16] = v10 + 15;
  v10[15] = v10 + 15;
  *((_DWORD *)v10 + 3) = 1;
  v10[20] = v4;
  KeInitializeSpinLock(v10 + 2);
  if ( *(_BYTE *)(v4 + 73)
    || (v20 = v5 + 2,
        v21 = v5 + 1,
        LOBYTE(v19) = 1,
        !(unsigned __int8)AfdCheckTDIFilter(v5[1], *v5, *((_DWORD *)v5 + 1), v19, (__int64)&v29)) )
  {
    v20 = v5 + 2;
    v21 = v5 + 1;
    v23 = (__int64 *)AfdTlFindAndReferenceTransport(*v5, v5[1], *((unsigned int *)v5 + 1));
    if ( v23 )
      goto LABEL_50;
    v22 = AfdWskSearchClientTdiMap(v4, (unsigned __int16)*v21, *v5, *(unsigned int *)v20);
    if ( !v22 )
    {
      v7 = -1073741250;
      goto LABEL_45;
    }
  }
  else
  {
    v22 = v29;
  }
  *(_QWORD *)(a2 + 16) = v22;
  v23 = WskTdiTransport;
LABEL_50:
  v10[6] = v23;
  *((_WORD *)v10 + 92) = *v5;
  v27[0] = WskProTLCreateEndpointComplete;
  v27[1] = Irp;
  LOWORD(v27[3]) = *v5;
  v24 = v27[2];
  if ( (__int64 *)v10[6] != WskTdiTransport )
    v24 = 1;
  LODWORD(v27[2]) = v24;
  WORD1(v27[3]) = *v21;
  WORD2(v27[3]) = *v20;
  v27[5] = *((_QWORD *)v5 + 4);
  v27[6] = *((_QWORD *)v5 + 5);
  v27[7] = *((_QWORD *)v5 + 6);
  *(_QWORD *)(a2 + 8) = v10;
  Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  v25 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(v23[5] + 16))(v23[4], v27);
  v7 = 259;
  if ( v25 != 259 )
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v27[0])(v27[1], v25, v27[8], v27[9]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14003e7b0  mov     [rsp-38h+arg_0], rbx
0x14003e7b5  push    rbp
0x14003e7b6  push    rsi
0x14003e7b7  push    rdi
0x14003e7b8  push    r12
0x14003e7ba  push    r13
0x14003e7bc  push    r14
0x14003e7be  push    r15
0x14003e7c0  mov     rbp, rsp
0x14003e7c3  sub     rsp, 80h
0x14003e7ca  xor     r15d, r15d
0x14003e7cd  mov     r13, rdx
0x14003e7d0  mov     r12, rcx
0x14003e7d3  mov     [rbp+arg_10], r15
0x14003e7d7  xor     edx, edx; Val
0x14003e7d9  lea     rcx, [rbp+var_50]; void *
0x14003e7dd  lea     r8d, [r15+50h]; Size
0x14003e7e1  call    memset
0x14003e7e6  mov     r14, [r13+8]
0x14003e7ea  lea     ebx, [r15+1]
0x14003e7ee  mov     rsi, [r13+10h]
0x14003e7f2  mov     eax, [r14+10h]
0x14003e7f6  test    bl, al
0x14003e7f8  jnz     loc_14003EB63
0x14003e7fe  lea     ecx, [rax+2]
0x14003e801  lock cmpxchg [r14+10h], ecx
0x14003e807  jnz     short loc_14003E7F2
0x14003e809  mov     [r14+48h], bl
0x14003e80d  cmp     word ptr [rsi], 23h ; '#'
0x14003e811  jb      short loc_14003E81D
0x14003e813  mov     ebx, 0C000000Dh
0x14003e818  jmp     loc_14003EAAC
0x14003e81d  mov     rcx, [rsi+20h]; Object
0x14003e821  mov     [rbp+arg_8], r15b
0x14003e825  test    rcx, rcx
0x14003e828  jz      short loc_14003E863
0x14003e82a  call    cs:__imp_ObfReferenceObject
0x14003e831  nop     dword ptr [rax+rax+00h]
0x14003e836  mov     rcx, [rsi+20h]; Process
0x14003e83a  mov     edx, 200h; PoolType
0x14003e83f  mov     r8d, 0C8h; Amount
0x14003e845  mov     [rbp+arg_8], bl
0x14003e848  call    cs:__imp_PsChargeProcessPoolQuota
0x14003e84f  nop     dword ptr [rax+rax+00h]
0x14003e854  mov     ebx, eax
0x14003e856  test    eax, eax
0x14003e858  js      loc_14003EA9C
0x14003e85e  mov     ebx, 1
0x14003e863  mov     rcx, cs:WskProPplSocket
0x14003e86a  call    PplAllocateFromLookasideList
0x14003e86f  mov     rdi, rax
0x14003e872  test    rax, rax
0x14003e875  jnz     short loc_14003E881
0x14003e877  mov     ebx, 0C000009Ah
0x14003e87c  jmp     loc_14003EA7B
0x14003e881  xor     edx, edx; Val
0x14003e883  mov     r8d, 0C8h; Size
0x14003e889  mov     rcx, rdi; void *
0x14003e88c  call    memset
0x14003e891  mov     rax, [rsi+20h]
0x14003e895  mov     [rdi+0A8h], rax
0x14003e89c  mov     eax, [rsi+8]
0x14003e89f  test    al, 2
0x14003e8a1  jz      short loc_14003E906
0x14003e8a3  test    al, 0Dh
0x14003e8a5  jz      short loc_14003E8B1
0x14003e8a7  mov     ebx, 0C000000Dh
0x14003e8ac  jmp     loc_14003EA6C
0x14003e8b1  lea     rax, WskProAPIConnectionSocketDispatch
0x14003e8b8  mov     word ptr [rdi], 0ACE2h
0x14003e8bd  mov     [rdi+18h], rax
0x14003e8c1  mov     eax, 0D0h
0x14003e8c6  and     ax, [r14+4Ah]
0x14003e8cb  mov     [rdi+20h], ax
0x14003e8cf  jz      short loc_14003E8D7
0x14003e8d1  cmp     [rsi+18h], r15
0x14003e8d5  jz      short loc_14003E8A7
0x14003e8d7  mov     rcx, [rsi+18h]
0x14003e8db  mov     [rdi+48h], rcx
0x14003e8df  test    al, 40h
0x14003e8e1  jz      short loc_14003E8E8
0x14003e8e3  cmp     [rcx], r15
0x14003e8e6  jz      short loc_14003E8A7
0x14003e8e8  test    al, al
0x14003e8ea  jns     short loc_14003E8F2
0x14003e8ec  cmp     [rcx+8], r15
0x14003e8f0  jz      short loc_14003E8A7
0x14003e8f2  test    al, 10h
0x14003e8f4  jz      loc_14003E9B8
0x14003e8fa  cmp     [rcx+10h], r15
0x14003e8fe  jnz     loc_14003E9B8
0x14003e904  jmp     short loc_14003E8A7
0x14003e906  test    bl, al
0x14003e908  jz      short loc_14003E942
0x14003e90a  test    al, 0Ch
0x14003e90c  jnz     short loc_14003E8A7
0x14003e90e  lea     rax, WskProAPIListenSocketDispatch
0x14003e915  mov     word ptr [rdi], 0ACE1h
0x14003e91a  mov     [rdi+18h], rax
0x14003e91e  lea     rax, [rdi+50h]
0x14003e922  mov     [rax+8], rax
0x14003e926  mov     [rax], rax
0x14003e929  mov     eax, 200h
0x14003e92e  jmp     short loc_14003E973
0x14003e930  mov     rcx, [rsi+18h]
0x14003e934  mov     [rdi+48h], rcx
0x14003e938  test    ax, ax
0x14003e93b  jz      short loc_14003E9B8
0x14003e93d  cmp     [rcx], r15
0x14003e940  jmp     short loc_14003E8FE
0x14003e942  mov     ecx, eax
0x14003e944  and     ecx, 8
0x14003e947  test    al, 4
0x14003e949  jz      short loc_14003E989
0x14003e94b  test    ecx, ecx
0x14003e94d  jnz     loc_14003E8A7
0x14003e953  lea     rax, WskProAPIDatagramSocketDispatch
0x14003e95a  mov     word ptr [rdi], 0ACE3h
0x14003e95f  mov     [rdi+18h], rax
0x14003e963  lea     rax, [rdi+50h]
0x14003e967  mov     [rax+8], rax
0x14003e96b  mov     [rax], rax
0x14003e96e  mov     eax, 100h
0x14003e973  and     ax, [r14+4Ah]
0x14003e978  mov     [rdi+20h], ax
0x14003e97c  jz      short loc_14003E930
0x14003e97e  cmp     [rsi+18h], r15
0x14003e982  jnz     short loc_14003E930
0x14003e984  jmp     loc_14003E8A7
0x14003e989  test    ecx, ecx
0x14003e98b  jz      short loc_14003E9A0
0x14003e98d  lea     rax, WskProAPIStreamSocketDispatch
0x14003e994  mov     word ptr [rdi], 0ACE4h
0x14003e999  mov     [rdi+20h], r15w
0x14003e99e  jmp     short loc_14003E9AC
0x14003e9a0  lea     rax, WskProAPIBasicSocketDispatch
0x14003e9a7  mov     word ptr [rdi], 0ACE0h
0x14003e9ac  mov     [rdi+18h], rax
0x14003e9b0  mov     rax, [rsi+18h]
0x14003e9b4  mov     [rdi+48h], rax
0x14003e9b8  mov     [rdi+2], r15b
0x14003e9bc  lea     rcx, [rdi+10h]; SpinLock
0x14003e9c0  mov     rax, [rsi+10h]
0x14003e9c4  mov     [rdi+40h], rax
0x14003e9c8  lea     rax, [rdi+78h]
0x14003e9cc  mov     [rdi+8], ebx
0x14003e9cf  mov     [rax+8], rax
0x14003e9d3  mov     [rax], rax
0x14003e9d6  mov     [rdi+0Ch], ebx
0x14003e9d9  mov     [rdi+0A0h], r14
0x14003e9e0  call    cs:__imp_KeInitializeSpinLock
0x14003e9e7  nop     dword ptr [rax+rax+00h]
0x14003e9ec  cmp     [r14+49h], r15b
0x14003e9f0  jnz     short loc_14003EA2F
0x14003e9f2  movzx   edx, word ptr [rsi]
0x14003e9f5  lea     rax, [rbp+arg_10]
0x14003e9f9  lea     r15, [rsi+4]
0x14003e9fd  mov     [rsp+80h+var_60], rax
0x14003ea02  mov     r8d, [r15]
0x14003ea05  lea     rbx, [rsi+2]
0x14003ea09  movzx   ecx, word ptr [rbx]
0x14003ea0c  mov     r9b, 1
0x14003ea0f  call    AfdCheckTDIFilter
0x14003ea14  test    al, al
0x14003ea16  jz      short loc_14003EA2F
0x14003ea18  mov     rax, [rbp+arg_10]
0x14003ea1c  lea     rdx, WskTdiTransport
0x14003ea23  mov     [r13+10h], rax
0x14003ea27  mov     rcx, rdx
0x14003ea2a  jmp     loc_14003EAC0
0x14003ea2f  movzx   ecx, word ptr [rsi]
0x14003ea32  lea     r15, [rsi+4]
0x14003ea36  mov     r8d, [r15]
0x14003ea39  lea     rbx, [rsi+2]
0x14003ea3d  movzx   edx, word ptr [rbx]
0x14003ea40  call    AfdTlFindAndReferenceTransport
0x14003ea45  mov     rcx, rax
0x14003ea48  test    rax, rax
0x14003ea4b  jnz     short loc_14003EAB9
0x14003ea4d  movzx   r8d, word ptr [rsi]
0x14003ea51  mov     rcx, r14
0x14003ea54  movzx   edx, word ptr [rbx]
0x14003ea57  mov     r9d, [r15]
0x14003ea5a  call    AfdWskSearchClientTdiMap
0x14003ea5f  test    rax, rax
0x14003ea62  jnz     short loc_14003EA1C
0x14003ea64  mov     ebx, 0C000023Eh
0x14003ea69  xor     r15d, r15d
0x14003ea6c  mov     rcx, cs:WskProPplSocket
0x14003ea73  mov     rdx, rdi
0x14003ea76  call    PplFreeToLookasideList
0x14003ea7b  cmp     [rbp+arg_8], r15b
0x14003ea7f  jz      short loc_14003EAAC
0x14003ea81  mov     rcx, [rsi+20h]; Process
0x14003ea85  mov     edx, 200h; PoolType
0x14003ea8a  mov     r8d, 0C8h; Amount
0x14003ea90  call    cs:__imp_PsReturnPoolQuota
0x14003ea97  nop     dword ptr [rax+rax+00h]
0x14003ea9c  mov     rcx, [rsi+20h]; Object
0x14003eaa0  call    cs:__imp_ObfDereferenceObject
0x14003eaa7  nop     dword ptr [rax+rax+00h]
0x14003eaac  mov     rcx, r14
0x14003eaaf  call    AfdWskDereferenceClient
0x14003eab4  jmp     loc_14003EB68
0x14003eab9  lea     rdx, WskTdiTransport
0x14003eac0  mov     [rdi+30h], rcx
0x14003eac4  movzx   eax, word ptr [rsi]
0x14003eac7  mov     [rdi+0B8h], ax
0x14003eace  lea     rax, WskProTLCreateEndpointComplete
0x14003ead5  mov     [rbp+var_50], rax
0x14003ead9  mov     [rbp+var_48], r12
0x14003eadd  movzx   eax, word ptr [rsi]
0x14003eae0  mov     [rbp+var_38], ax
0x14003eae4  cmp     [rdi+30h], rdx
0x14003eae8  mov     edx, 1
0x14003eaed  mov     eax, [rbp+var_40]
0x14003eaf0  cmovnz  eax, edx
0x14003eaf3  mov     [rbp+var_40], eax
0x14003eaf6  movzx   eax, word ptr [rbx]
0x14003eaf9  mov     [rbp+var_36], ax
0x14003eafd  movzx   eax, word ptr [r15]
0x14003eb01  mov     [rbp+var_34], ax
0x14003eb05  mov     rax, [rsi+20h]
0x14003eb09  mov     [rbp+var_28], rax
0x14003eb0d  mov     rax, [rsi+28h]
0x14003eb11  mov     [rbp+var_20], rax
0x14003eb15  mov     rax, [rsi+30h]
0x14003eb19  mov     [rbp+var_18], rax
0x14003eb1d  mov     [r13+8], rdi
0x14003eb21  mov     rax, [r12+0B8h]
0x14003eb29  or      [rax+3], dl
0x14003eb2c  lea     rdx, [rbp+var_50]
0x14003eb30  mov     rax, [rcx+28h]
0x14003eb34  mov     rcx, [rcx+20h]
0x14003eb38  mov     rax, [rax+10h]
0x14003eb3c  call    _guard_dispatch_icall
0x14003eb41  mov     ebx, 103h
0x14003eb46  cmp     eax, ebx
0x14003eb48  jz      short loc_14003EB83
0x14003eb4a  mov     r9, [rbp+var_8]
0x14003eb4e  mov     edx, eax
0x14003eb50  mov     rax, [rbp+var_50]
0x14003eb54  mov     r8, [rbp+var_10]
0x14003eb58  mov     rcx, [rbp+var_48]
0x14003eb5c  call    _guard_dispatch_icall
0x14003eb61  jmp     short loc_14003EB83
0x14003eb63  mov     ebx, 0C0000008h
0x14003eb68  xor     edx, edx; PriorityBoost
0x14003eb6a  mov     [r12+38h], r15
0x14003eb6f  mov     rcx, r12; Irp
0x14003eb72  mov     [r12+30h], ebx
0x14003eb77  call    cs:__imp_IofCompleteRequest
0x14003eb7e  nop     dword ptr [rax+rax+00h]
0x14003eb83  mov     eax, ebx
0x14003eb85  mov     rbx, [rsp+80h+arg_0]
0x14003eb8d  add     rsp, 80h
0x14003eb94  pop     r15
0x14003eb96  pop     r14
0x14003eb98  pop     r13
0x14003eb9a  pop     r12
0x14003eb9c  pop     rdi
0x14003eb9d  pop     rsi
0x14003eb9e  pop     rbp
0x14003eb9f  retn
```
