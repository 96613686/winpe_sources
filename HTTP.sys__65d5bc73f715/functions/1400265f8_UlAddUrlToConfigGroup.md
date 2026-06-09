# UlAddUrlToConfigGroup

- ea: `0x1400265f8`
- end: `0x14002699d`
- name: `UlAddUrlToConfigGroup`
- size: `933`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, PIRP)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400165a0`

## callees

- `0x14000a350`
- `0x1400193f8`
- `0x1400251b8`
- `0x1400256f0`
- `0x1400265f8`
- `0x140027840`
- `0x140074ad8`
- `0x1400a16c8`
- `0x1401503f0`
- `0x140167c40`
- `0x1401c3e00`
- `0x1401c6e34`
- `0x1401c8c38`
- `0x1401c8cb0`
- `0x1401c9430`
- `0x1401da550`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400267fa`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400267fa`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x140026729`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x140026729`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026806`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026806`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026820`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026820`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026716`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026716`

## pseudocode

```c
__int64 __fastcall UlAddUrlToConfigGroup(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, PIRP a6)
{
  char v9; // r14
  int v10; // ecx
  int v11; // r8d
  __int64 *v12; // rbx
  PIRP Irp; // r13
  __int64 v14; // r14
  __int64 v15; // rbx
  __int64 v16; // r15
  int v17; // ebx
  PVOID v18; // r8
  __int64 v20; // rbx
  int v21; // r9d
  volatile signed __int32 *ObjectFromOpaqueId; // rax
  volatile signed __int32 *v23; // rdi
  int v24; // ecx
  int v25; // r8d
  int v26; // eax
  __int64 v27; // r8
  int v28[48]; // [rsp+50h] [rbp-79h] BYREF
  PVOID P; // [rsp+120h] [rbp+57h] BYREF
  __int64 v30; // [rsp+128h] [rbp+5Fh]
  __int64 v31; // [rsp+138h] [rbp+6Fh]

  v31 = a4;
  P = 0;
  v9 = a4;
  memset(v28, 0, 0x88u);
  v12 = (__int64 *)(a3 + 8);
  Irp = a6;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qqSqLl(v10, 102, v11, a1, a2, *v12, v9, a5, a6->RequestorMode);
  v14 = *(_QWORD *)(a2 + 8);
  v30 = *(_QWORD *)(a2 + 16);
  if ( (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_Si(v10, 103, v11, *v12, v14);
  v15 = *v12;
  v16 = *(_QWORD *)(a1 + 56);
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qqLqq(1028, 27, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v16, v15, 1, &P, v28);
  P = 0;
  v17 = HttpParseUrl(v16 + 4396, v15, 257, v28);
  if ( v17 >= 0 )
  {
    v18 = *(PVOID *)&v28[2];
    P = *(PVOID *)&v28[2];
  }
  else
  {
    v18 = P;
  }
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
  {
    WPP_SF_qqD(1028, 28, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v18, v28, v17);
    v18 = P;
  }
  if ( v17 >= 0 )
  {
    if ( (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
      WPP_SF_S(1284, 105, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v18);
    v20 = *(_QWORD *)(a1 + 56);
    KeEnterCriticalRegion();
    ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v20 + 1368));
    if ( *(_DWORD *)a2 == 1 )
    {
      ObjectFromOpaqueId = (volatile signed __int32 *)UxGetObjectFromOpaqueId(
                                                        v14,
                                                        2,
                                                        (unsigned int)UlReferenceServerSession,
                                                        (unsigned int)UlValidateConfigGroup,
                                                        a1);
      v23 = ObjectFromOpaqueId;
      if ( !ObjectFromOpaqueId || *ObjectFromOpaqueId != 1245932629 )
      {
        v17 = -1073741811;
LABEL_28:
        if ( v23 )
        {
LABEL_29:
          v26 = _InterlockedDecrement(v23 + 1);
          if ( UxDebugCheckRefcount && v26 <= -1 )
            UlBugCheckEx(3u, (ULONG_PTR)(v23 + 1), 0xBu, v26);
          if ( !v26 )
            UlFreeConfigGroup((PVOID)v23);
          goto LABEL_32;
        }
        goto LABEL_32;
      }
      v17 = UlpRegisterUrlNamespace((unsigned int)v28, v30, (_DWORD)ObjectFromOpaqueId, v31, a5, Irp->RequestorMode);
      UlEventLogAddUrl(v24, v14, (int)v28, v17, Irp);
      if ( (xmmword_1401A2CA0 & 0x10) != 0 )
        WPP_SF_diS(v28[2], 106, v25, v17, v14, *(__int64 *)&v28[2]);
      if ( v17 < 0 )
        goto LABEL_29;
    }
    else
    {
      if ( *(_DWORD *)a2 || (v27 = *(_QWORD *)(a2 + 32)) == 0 )
      {
        v17 = -1073741811;
        goto LABEL_32;
      }
      v23 = 0;
      v17 = UlpAddReservationEntry(
              *(_QWORD *)(a1 + 56),
              (unsigned int)v28,
              v27,
              v21,
              v31,
              a5,
              Irp->RequestorMode,
              (__int64)Irp,
              1);
      if ( v17 < 0 )
      {
LABEL_32:
        ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 1368LL));
        KeLeaveCriticalRegion();
        goto LABEL_33;
      }
    }
    UlFlushCacheForAddUrl(*(_QWORD *)(a1 + 56), v28);
    goto LABEL_28;
  }
  if ( (xmmword_1401A2C90 & 0x10) == 0 )
    goto LABEL_13;
  WPP_SF_S(516, 104, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, *(_QWORD *)(a3 + 8));
LABEL_33:
  v18 = P;
LABEL_13:
  if ( v18 )
  {
    ExFreePoolWithTag(v18, 0);
    P = 0;
  }
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 107, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)v17);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1400265f8  mov     [rsp-8+arg_10], rbx
0x1400265fd  mov     [rsp-8+arg_18], r9
0x140026602  push    rbp
0x140026603  push    rsi
0x140026604  push    rdi
0x140026605  push    r12
0x140026607  push    r13
0x140026609  push    r14
0x14002660b  push    r15
0x14002660d  lea     rbp, [rsp-17h]
0x140026612  sub     rsp, 0E0h
0x140026619  mov     r12, r8
0x14002661c  mov     [rbp+47h+P], 0
0x140026624  mov     rdi, rdx
0x140026627  mov     rsi, rcx
0x14002662a  xor     edx, edx; Val
0x14002662c  lea     rcx, [rbp+47h+var_C0]; void *
0x140026630  mov     r8d, 88h; Size
0x140026636  mov     r14, r9
0x140026639  call    memset
0x14002663e  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140026645  lea     rbx, [r12+8]
0x14002664a  mov     r13, [rbp+47h+arg_28]
0x14002664e  jnz     loc_140026850
0x140026654  mov     rax, [rdi+10h]
0x140026658  mov     r14, [rdi+8]
0x14002665c  mov     [rbp+47h+arg_8], rax
0x140026660  test    byte ptr cs:xmmword_1401A2CA0+8, 10h
0x140026667  jnz     loc_140026884
0x14002666d  mov     rbx, [rbx]
0x140026670  mov     r15, [rsi+38h]
0x140026674  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x14002667b  jnz     loc_14002689B
0x140026681  lea     rcx, [r15+112Ch]
0x140026688  mov     [rbp+47h+P], 0
0x140026690  lea     r9, [rbp+47h+var_C0]
0x140026694  mov     r8d, 101h
0x14002669a  mov     rdx, rbx
0x14002669d  call    HttpParseUrl
0x1400266a2  mov     ebx, eax
0x1400266a4  test    eax, eax
0x1400266a6  jns     loc_1400268D8
0x1400266ac  mov     r8, [rbp+47h+P]
0x1400266b0  mov     r15b, 10h
0x1400266b3  test    byte ptr cs:xmmword_1401A2CA0, r15b
0x1400266ba  jnz     loc_1400268E5
0x1400266c0  test    ebx, ebx
0x1400266c2  jns     short loc_140026705
0x1400266c4  test    byte ptr cs:xmmword_1401A2C90, r15b
0x1400266cb  jnz     loc_140026914
0x1400266d1  test    r8, r8
0x1400266d4  jnz     loc_14002681B
0x1400266da  test    byte ptr cs:xmmword_1401A2CA0, r15b
0x1400266e1  jnz     loc_14002697F
0x1400266e7  mov     eax, ebx
0x1400266e9  mov     rbx, [rsp+110h+arg_10]
0x1400266f1  add     rsp, 0E0h
0x1400266f8  pop     r15
0x1400266fa  pop     r14
0x1400266fc  pop     r13
0x1400266fe  pop     r12
0x140026700  pop     rdi
0x140026701  pop     rsi
0x140026702  pop     rbp
0x140026703  retn
0x140026705  test    byte ptr cs:xmmword_1401A2CA0+8, r15b
0x14002670c  jnz     loc_140026934
0x140026712  mov     rbx, [rsi+38h]
0x140026716  call    cs:__imp_KeEnterCriticalRegion
0x14002671d  nop     dword ptr [rax+rax+00h]
0x140026722  mov     rcx, [rbx+558h]
0x140026729  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x140026730  nop     dword ptr [rax+rax+00h]
0x140026735  mov     eax, [rdi]
0x140026737  cmp     eax, 1
0x14002673a  jnz     loc_1401733F6
0x140026740  lea     r9, UlValidateConfigGroup
0x140026747  mov     [rsp+110h+Irp], rsi
0x14002674c  lea     r8, UlReferenceServerSession
0x140026753  mov     rcx, r14
0x140026756  lea     edx, [rax+1]
0x140026759  call    UxGetObjectFromOpaqueId
0x14002675e  mov     rdi, rax
0x140026761  test    rax, rax
0x140026764  jz      short loc_1400267C7
0x140026766  cmp     dword ptr [rax], 4A436C55h
0x14002676c  jnz     short loc_1400267C7
0x14002676e  mov     al, [r13+40h]
0x140026772  lea     rcx, [rbp+47h+var_C0]
0x140026776  mov     r9, [rbp+47h+arg_18]
0x14002677a  mov     r8, rdi
0x14002677d  mov     rdx, [rbp+47h+arg_8]
0x140026781  mov     byte ptr [rsp+110h+var_E8], al
0x140026785  mov     eax, [rbp+47h+arg_20]
0x140026788  mov     dword ptr [rsp+110h+Irp], eax
0x14002678c  call    UlpRegisterUrlNamespace
0x140026791  mov     r9d, eax; int
0x140026794  mov     [rsp+110h+Irp], r13; Irp
0x140026799  lea     r8, [rbp+47h+var_C0]; int
0x14002679d  mov     rdx, r14; int
0x1400267a0  mov     ebx, eax
0x1400267a2  call    UlEventLogAddUrl
0x1400267a7  test    byte ptr cs:xmmword_1401A2CA0, r15b
0x1400267ae  jnz     loc_140026952
0x1400267b4  test    ebx, ebx
0x1400267b6  js      short loc_1400267D1
0x1400267b8  mov     rcx, [rsi+38h]
0x1400267bc  lea     rdx, [rbp+47h+var_C0]
0x1400267c0  call    UlFlushCacheForAddUrl
0x1400267c5  jmp     short loc_1400267CC
0x1400267c7  mov     ebx, 0C000000Dh
0x1400267cc  test    rdi, rdi
0x1400267cf  jz      short loc_1400267EF
0x1400267d1  lea     rdx, [rdi+4]; BugCheckParameter2
0x1400267d5  or      eax, 0FFFFFFFFh
0x1400267d8  lock xadd [rdx], eax
0x1400267dc  dec     eax
0x1400267de  cmp     cs:UxDebugCheckRefcount, 0
0x1400267e5  jnz     short loc_140026839
0x1400267e7  test    eax, eax
0x1400267e9  jz      loc_140026972
0x1400267ef  mov     rcx, [rsi+38h]
0x1400267f3  mov     rcx, [rcx+558h]
0x1400267fa  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x140026801  nop     dword ptr [rax+rax+00h]
0x140026806  call    cs:__imp_KeLeaveCriticalRegion
0x14002680d  nop     dword ptr [rax+rax+00h]
0x140026812  mov     r8, [rbp+47h+P]
0x140026816  jmp     loc_1400266D1
0x14002681b  xor     edx, edx; Tag
0x14002681d  mov     rcx, r8; P
0x140026820  call    cs:__imp_ExFreePoolWithTag
0x140026827  nop     dword ptr [rax+rax+00h]
0x14002682c  mov     [rbp+47h+P], 0
0x140026834  jmp     loc_1400266DA
0x140026839  cmp     eax, 0FFFFFFFFh
0x14002683c  jg      short loc_1400267E7
0x14002683e  mov     ecx, 3; BugCheckParameter1
0x140026843  movsxd  r9, eax; BugCheckParameter4
0x140026846  lea     r8d, [rcx+8]; BugCheckParameter3
0x14002684a  call    UlBugCheckEx
0x140026850  movsx   eax, byte ptr [r13+40h]
0x140026855  mov     edx, 66h ; 'f'
0x14002685a  mov     [rsp+110h+var_D0], eax
0x14002685e  mov     r9, rsi
0x140026861  mov     eax, [rbp+47h+arg_20]
0x140026864  mov     dword ptr [rsp+110h+var_D8], eax
0x140026868  mov     rax, [rbx]
0x14002686b  mov     [rsp+110h+var_E0], r14
0x140026870  mov     [rsp+110h+var_E8], rax
0x140026875  mov     [rsp+110h+Irp], rdi
0x14002687a  call    WPP_SF_qqSqLl
0x14002687f  jmp     loc_140026654
0x140026884  mov     r9, [rbx]
0x140026887  mov     edx, 67h ; 'g'
0x14002688c  mov     [rsp+110h+Irp], r14
0x140026891  call    WPP_SF_Si
0x140026896  jmp     loc_14002666D
0x14002689b  lea     rax, [rbp+47h+var_C0]
0x14002689f  mov     edx, 1Bh
0x1400268a4  mov     [rsp+110h+var_D8], rax
0x1400268a9  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x1400268b0  lea     rax, [rbp+47h+P]
0x1400268b4  mov     ecx, 404h
0x1400268b9  mov     [rsp+110h+var_E0], rax
0x1400268be  mov     r9, r15
0x1400268c1  mov     dword ptr [rsp+110h+var_E8], 1
0x1400268c9  mov     [rsp+110h+Irp], rbx
0x1400268ce  call    WPP_SF_qqLqq
0x1400268d3  jmp     loc_140026681
0x1400268d8  mov     r8, [rbp+47h+var_B8]
0x1400268dc  mov     [rbp+47h+P], r8
0x1400268e0  jmp     loc_1400266B0
0x1400268e5  lea     rax, [rbp+47h+var_C0]
0x1400268e9  mov     dword ptr [rsp+110h+var_E8], ebx
0x1400268ed  mov     r9, r8
0x1400268f0  mov     [rsp+110h+Irp], rax
0x1400268f5  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x1400268fc  mov     edx, 1Ch
0x140026901  mov     ecx, 404h
0x140026906  call    WPP_SF_qqD
0x14002690b  mov     r8, [rbp+47h+P]
0x14002690f  jmp     loc_1400266C0
0x140026914  mov     r9, [r12+8]
0x140026919  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x140026920  mov     edx, 68h ; 'h'
0x140026925  mov     ecx, 204h
0x14002692a  call    WPP_SF_S
0x14002692f  jmp     loc_140026812
0x140026934  mov     r9, r8
0x140026937  mov     edx, 69h ; 'i'
0x14002693c  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x140026943  mov     ecx, 504h
0x140026948  call    WPP_SF_S
0x14002694d  jmp     loc_140026712
0x140026952  mov     rcx, [rbp+47h+var_B8]
0x140026956  mov     edx, 6Ah ; 'j'
0x14002695b  mov     [rsp+110h+var_E8], rcx
0x140026960  mov     r9d, ebx
0x140026963  mov     [rsp+110h+Irp], r14
0x140026968  call    WPP_SF_diS
0x14002696d  jmp     loc_1400267B4
0x140026972  mov     rcx, rdi; P
0x140026975  call    UlFreeConfigGroup
0x14002697a  jmp     loc_1400267EF
0x14002697f  mov     edx, 6Bh ; 'k'
0x140026984  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x14002698b  mov     ecx, 404h
0x140026990  mov     r9d, ebx
0x140026993  call    WPP_SF_d
0x140026998  jmp     loc_1400266E7
0x1401733f6  test    eax, eax
0x1401733f8  jnz     short loc_140173443
0x1401733fa  mov     r8, [rdi+20h]
0x1401733fe  test    r8, r8
0x140173401  jz      short loc_140173443
0x140173403  mov     al, [r13+40h]
0x140173407  lea     rdx, [rbp+47h+var_C0]
0x14017340b  mov     rcx, [rsi+38h]
0x14017340f  xor     edi, edi
0x140173411  mov     byte ptr [rsp+110h+var_D0], 1
0x140173416  mov     [rsp+110h+var_D8], r13
0x14017341b  mov     byte ptr [rsp+110h+var_E0], al
0x14017341f  mov     eax, [rbp+47h+arg_20]
0x140173422  mov     dword ptr [rsp+110h+var_E8], eax
0x140173426  mov     rax, [rbp+47h+arg_18]
0x14017342a  mov     [rsp+110h+Irp], rax
0x14017342f  call    UlpAddReservationEntry
0x140173434  mov     ebx, eax
0x140173436  test    eax, eax
0x140173438  js      loc_1400267EF
0x14017343e  jmp     loc_1400267B8
0x140173443  mov     ebx, 0C000000Dh
0x140173448  jmp     loc_1400267EF
```
