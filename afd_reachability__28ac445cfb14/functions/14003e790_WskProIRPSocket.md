# WskProIRPSocket

- ea: `0x14003e790`
- end: `0x14003eb81`
- name: `WskProIRPSocket`
- size: `1009`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140032d90`

## callees

- `0x14001087c`
- `0x140013030`
- `0x1400159e0`
- `0x140015a2c`
- `0x14002e43c`
- `0x14003e790`
- `0x14005ed3c`
- `0x140072780`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x14003e828`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x14003e828`
- `ntoskrnl!PsReturnPoolQuota` at `0x14003ea70`
- `ntoskrnl!PsReturnPoolQuota` at `0x14003ea70`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003e9c0`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003e9c0`
- `ntoskrnl!ObfReferenceObject` at `0x14003e80a`
- `ntoskrnl!ObfReferenceObject` at `0x14003e80a`
- `ntoskrnl!IofCompleteRequest` at `0x14003eb57`
- `ntoskrnl!IofCompleteRequest` at `0x14003eb57`
- `ntoskrnl!ObfDereferenceObject` at `0x14003ea80`
- `ntoskrnl!ObfDereferenceObject` at `0x14003ea80`

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
0x14003e790  mov     [rsp-38h+arg_0], rbx
0x14003e795  push    rbp
0x14003e796  push    rsi
0x14003e797  push    rdi
0x14003e798  push    r12
0x14003e79a  push    r13
0x14003e79c  push    r14
0x14003e79e  push    r15
0x14003e7a0  mov     rbp, rsp
0x14003e7a3  sub     rsp, 80h
0x14003e7aa  xor     r15d, r15d
0x14003e7ad  mov     r13, rdx
0x14003e7b0  mov     r12, rcx
0x14003e7b3  mov     [rbp+arg_10], r15
0x14003e7b7  xor     edx, edx; Val
0x14003e7b9  lea     rcx, [rbp+var_50]; void *
0x14003e7bd  lea     r8d, [r15+50h]; Size
0x14003e7c1  call    memset
0x14003e7c6  mov     r14, [r13+8]
0x14003e7ca  lea     ebx, [r15+1]
0x14003e7ce  mov     rsi, [r13+10h]
0x14003e7d2  mov     eax, [r14+10h]
0x14003e7d6  test    bl, al
0x14003e7d8  jnz     loc_14003EB43
0x14003e7de  lea     ecx, [rax+2]
0x14003e7e1  lock cmpxchg [r14+10h], ecx
0x14003e7e7  jnz     short loc_14003E7D2
0x14003e7e9  mov     [r14+48h], bl
0x14003e7ed  cmp     word ptr [rsi], 23h ; '#'
0x14003e7f1  jb      short loc_14003E7FD
0x14003e7f3  mov     ebx, 0C000000Dh
0x14003e7f8  jmp     loc_14003EA8C
0x14003e7fd  mov     rcx, [rsi+20h]; Object
0x14003e801  mov     [rbp+arg_8], r15b
0x14003e805  test    rcx, rcx
0x14003e808  jz      short loc_14003E843
0x14003e80a  call    cs:__imp_ObfReferenceObject
0x14003e811  nop     dword ptr [rax+rax+00h]
0x14003e816  mov     rcx, [rsi+20h]; Process
0x14003e81a  mov     edx, 200h; PoolType
0x14003e81f  mov     r8d, 0C8h; Amount
0x14003e825  mov     [rbp+arg_8], bl
0x14003e828  call    cs:__imp_PsChargeProcessPoolQuota
0x14003e82f  nop     dword ptr [rax+rax+00h]
0x14003e834  mov     ebx, eax
0x14003e836  test    eax, eax
0x14003e838  js      loc_14003EA7C
0x14003e83e  mov     ebx, 1
0x14003e843  mov     rcx, cs:WskProPplSocket
0x14003e84a  call    PplAllocateFromLookasideList
0x14003e84f  mov     rdi, rax
0x14003e852  test    rax, rax
0x14003e855  jnz     short loc_14003E861
0x14003e857  mov     ebx, 0C000009Ah
0x14003e85c  jmp     loc_14003EA5B
0x14003e861  xor     edx, edx; Val
0x14003e863  mov     r8d, 0C8h; Size
0x14003e869  mov     rcx, rdi; void *
0x14003e86c  call    memset
0x14003e871  mov     rax, [rsi+20h]
0x14003e875  mov     [rdi+0A8h], rax
0x14003e87c  mov     eax, [rsi+8]
0x14003e87f  test    al, 2
0x14003e881  jz      short loc_14003E8E6
0x14003e883  test    al, 0Dh
0x14003e885  jz      short loc_14003E891
0x14003e887  mov     ebx, 0C000000Dh
0x14003e88c  jmp     loc_14003EA4C
0x14003e891  lea     rax, WskProAPIConnectionSocketDispatch
0x14003e898  mov     word ptr [rdi], 0ACE2h
0x14003e89d  mov     [rdi+18h], rax
0x14003e8a1  mov     eax, 0D0h
0x14003e8a6  and     ax, [r14+4Ah]
0x14003e8ab  mov     [rdi+20h], ax
0x14003e8af  jz      short loc_14003E8B7
0x14003e8b1  cmp     [rsi+18h], r15
0x14003e8b5  jz      short loc_14003E887
0x14003e8b7  mov     rcx, [rsi+18h]
0x14003e8bb  mov     [rdi+48h], rcx
0x14003e8bf  test    al, 40h
0x14003e8c1  jz      short loc_14003E8C8
0x14003e8c3  cmp     [rcx], r15
0x14003e8c6  jz      short loc_14003E887
0x14003e8c8  test    al, al
0x14003e8ca  jns     short loc_14003E8D2
0x14003e8cc  cmp     [rcx+8], r15
0x14003e8d0  jz      short loc_14003E887
0x14003e8d2  test    al, 10h
0x14003e8d4  jz      loc_14003E998
0x14003e8da  cmp     [rcx+10h], r15
0x14003e8de  jnz     loc_14003E998
0x14003e8e4  jmp     short loc_14003E887
0x14003e8e6  test    bl, al
0x14003e8e8  jz      short loc_14003E922
0x14003e8ea  test    al, 0Ch
0x14003e8ec  jnz     short loc_14003E887
0x14003e8ee  lea     rax, WskProAPIListenSocketDispatch
0x14003e8f5  mov     word ptr [rdi], 0ACE1h
0x14003e8fa  mov     [rdi+18h], rax
0x14003e8fe  lea     rax, [rdi+50h]
0x14003e902  mov     [rax+8], rax
0x14003e906  mov     [rax], rax
0x14003e909  mov     eax, 200h
0x14003e90e  jmp     short loc_14003E953
0x14003e910  mov     rcx, [rsi+18h]
0x14003e914  mov     [rdi+48h], rcx
0x14003e918  test    ax, ax
0x14003e91b  jz      short loc_14003E998
0x14003e91d  cmp     [rcx], r15
0x14003e920  jmp     short loc_14003E8DE
0x14003e922  mov     ecx, eax
0x14003e924  and     ecx, 8
0x14003e927  test    al, 4
0x14003e929  jz      short loc_14003E969
0x14003e92b  test    ecx, ecx
0x14003e92d  jnz     loc_14003E887
0x14003e933  lea     rax, WskProAPIDatagramSocketDispatch
0x14003e93a  mov     word ptr [rdi], 0ACE3h
0x14003e93f  mov     [rdi+18h], rax
0x14003e943  lea     rax, [rdi+50h]
0x14003e947  mov     [rax+8], rax
0x14003e94b  mov     [rax], rax
0x14003e94e  mov     eax, 100h
0x14003e953  and     ax, [r14+4Ah]
0x14003e958  mov     [rdi+20h], ax
0x14003e95c  jz      short loc_14003E910
0x14003e95e  cmp     [rsi+18h], r15
0x14003e962  jnz     short loc_14003E910
0x14003e964  jmp     loc_14003E887
0x14003e969  test    ecx, ecx
0x14003e96b  jz      short loc_14003E980
0x14003e96d  lea     rax, WskProAPIStreamSocketDispatch
0x14003e974  mov     word ptr [rdi], 0ACE4h
0x14003e979  mov     [rdi+20h], r15w
0x14003e97e  jmp     short loc_14003E98C
0x14003e980  lea     rax, WskProAPIBasicSocketDispatch
0x14003e987  mov     word ptr [rdi], 0ACE0h
0x14003e98c  mov     [rdi+18h], rax
0x14003e990  mov     rax, [rsi+18h]
0x14003e994  mov     [rdi+48h], rax
0x14003e998  mov     [rdi+2], r15b
0x14003e99c  lea     rcx, [rdi+10h]; SpinLock
0x14003e9a0  mov     rax, [rsi+10h]
0x14003e9a4  mov     [rdi+40h], rax
0x14003e9a8  lea     rax, [rdi+78h]
0x14003e9ac  mov     [rdi+8], ebx
0x14003e9af  mov     [rax+8], rax
0x14003e9b3  mov     [rax], rax
0x14003e9b6  mov     [rdi+0Ch], ebx
0x14003e9b9  mov     [rdi+0A0h], r14
0x14003e9c0  call    cs:__imp_KeInitializeSpinLock
0x14003e9c7  nop     dword ptr [rax+rax+00h]
0x14003e9cc  cmp     [r14+49h], r15b
0x14003e9d0  jnz     short loc_14003EA0F
0x14003e9d2  movzx   edx, word ptr [rsi]
0x14003e9d5  lea     rax, [rbp+arg_10]
0x14003e9d9  lea     r15, [rsi+4]
0x14003e9dd  mov     [rsp+80h+var_60], rax
0x14003e9e2  mov     r8d, [r15]
0x14003e9e5  lea     rbx, [rsi+2]
0x14003e9e9  movzx   ecx, word ptr [rbx]
0x14003e9ec  mov     r9b, 1
0x14003e9ef  call    AfdCheckTDIFilter
0x14003e9f4  test    al, al
0x14003e9f6  jz      short loc_14003EA0F
0x14003e9f8  mov     rax, [rbp+arg_10]
0x14003e9fc  lea     rdx, WskTdiTransport
0x14003ea03  mov     [r13+10h], rax
0x14003ea07  mov     rcx, rdx
0x14003ea0a  jmp     loc_14003EAA0
0x14003ea0f  movzx   ecx, word ptr [rsi]
0x14003ea12  lea     r15, [rsi+4]
0x14003ea16  mov     r8d, [r15]
0x14003ea19  lea     rbx, [rsi+2]
0x14003ea1d  movzx   edx, word ptr [rbx]
0x14003ea20  call    AfdTlFindAndReferenceTransport
0x14003ea25  mov     rcx, rax
0x14003ea28  test    rax, rax
0x14003ea2b  jnz     short loc_14003EA99
0x14003ea2d  movzx   r8d, word ptr [rsi]
0x14003ea31  mov     rcx, r14
0x14003ea34  movzx   edx, word ptr [rbx]
0x14003ea37  mov     r9d, [r15]
0x14003ea3a  call    AfdWskSearchClientTdiMap
0x14003ea3f  test    rax, rax
0x14003ea42  jnz     short loc_14003E9FC
0x14003ea44  mov     ebx, 0C000023Eh
0x14003ea49  xor     r15d, r15d
0x14003ea4c  mov     rcx, cs:WskProPplSocket
0x14003ea53  mov     rdx, rdi
0x14003ea56  call    PplFreeToLookasideList
0x14003ea5b  cmp     [rbp+arg_8], r15b
0x14003ea5f  jz      short loc_14003EA8C
0x14003ea61  mov     rcx, [rsi+20h]; Process
0x14003ea65  mov     edx, 200h; PoolType
0x14003ea6a  mov     r8d, 0C8h; Amount
0x14003ea70  call    cs:__imp_PsReturnPoolQuota
0x14003ea77  nop     dword ptr [rax+rax+00h]
0x14003ea7c  mov     rcx, [rsi+20h]; Object
0x14003ea80  call    cs:__imp_ObfDereferenceObject
0x14003ea87  nop     dword ptr [rax+rax+00h]
0x14003ea8c  mov     rcx, r14
0x14003ea8f  call    AfdWskDereferenceClient
0x14003ea94  jmp     loc_14003EB48
0x14003ea99  lea     rdx, WskTdiTransport
0x14003eaa0  mov     [rdi+30h], rcx
0x14003eaa4  movzx   eax, word ptr [rsi]
0x14003eaa7  mov     [rdi+0B8h], ax
0x14003eaae  lea     rax, WskProTLCreateEndpointComplete
0x14003eab5  mov     [rbp+var_50], rax
0x14003eab9  mov     [rbp+var_48], r12
0x14003eabd  movzx   eax, word ptr [rsi]
0x14003eac0  mov     [rbp+var_38], ax
0x14003eac4  cmp     [rdi+30h], rdx
0x14003eac8  mov     edx, 1
0x14003eacd  mov     eax, [rbp+var_40]
0x14003ead0  cmovnz  eax, edx
0x14003ead3  mov     [rbp+var_40], eax
0x14003ead6  movzx   eax, word ptr [rbx]
0x14003ead9  mov     [rbp+var_36], ax
0x14003eadd  movzx   eax, word ptr [r15]
0x14003eae1  mov     [rbp+var_34], ax
0x14003eae5  mov     rax, [rsi+20h]
0x14003eae9  mov     [rbp+var_28], rax
0x14003eaed  mov     rax, [rsi+28h]
0x14003eaf1  mov     [rbp+var_20], rax
0x14003eaf5  mov     rax, [rsi+30h]
0x14003eaf9  mov     [rbp+var_18], rax
0x14003eafd  mov     [r13+8], rdi
0x14003eb01  mov     rax, [r12+0B8h]
0x14003eb09  or      [rax+3], dl
0x14003eb0c  lea     rdx, [rbp+var_50]
0x14003eb10  mov     rax, [rcx+28h]
0x14003eb14  mov     rcx, [rcx+20h]
0x14003eb18  mov     rax, [rax+10h]
0x14003eb1c  call    _guard_dispatch_icall
0x14003eb21  mov     ebx, 103h
0x14003eb26  cmp     eax, ebx
0x14003eb28  jz      short loc_14003EB63
0x14003eb2a  mov     r9, [rbp+var_8]
0x14003eb2e  mov     edx, eax
0x14003eb30  mov     rax, [rbp+var_50]
0x14003eb34  mov     r8, [rbp+var_10]
0x14003eb38  mov     rcx, [rbp+var_48]
0x14003eb3c  call    _guard_dispatch_icall
0x14003eb41  jmp     short loc_14003EB63
0x14003eb43  mov     ebx, 0C0000008h
0x14003eb48  xor     edx, edx; PriorityBoost
0x14003eb4a  mov     [r12+38h], r15
0x14003eb4f  mov     rcx, r12; Irp
0x14003eb52  mov     [r12+30h], ebx
0x14003eb57  call    cs:__imp_IofCompleteRequest
0x14003eb5e  nop     dword ptr [rax+rax+00h]
0x14003eb63  mov     eax, ebx
0x14003eb65  mov     rbx, [rsp+80h+arg_0]
0x14003eb6d  add     rsp, 80h
0x14003eb74  pop     r15
0x14003eb76  pop     r14
0x14003eb78  pop     r13
0x14003eb7a  pop     r12
0x14003eb7c  pop     rdi
0x14003eb7d  pop     rsi
0x14003eb7e  pop     rbp
0x14003eb7f  retn
```
