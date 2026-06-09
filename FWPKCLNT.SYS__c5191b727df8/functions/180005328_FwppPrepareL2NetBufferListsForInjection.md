# FwppPrepareL2NetBufferListsForInjection

- ea: `0x180005328`
- end: `0x1800055b7`
- name: `FwppPrepareL2NetBufferListsForInjection`
- size: `655`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006a4c`

## callees

- `0x180004904`
- `0x180004a60`
- `0x180005328`
- `0x18000c9b4`
- `0x18000cb3c`
- `0x180020400`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x180005380`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180005573`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000558e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180005573`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000558e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1800053a5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1800053dc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1800053a5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1800053dc`
- `NETIO!WfpNblInfoGetFlags` at `0x180005412`
- `NETIO!WfpNblInfoGetFlags` at `0x180005412`

## string_xrefs

- `0x1800054d7`: `ExAllocateFromNPagedLookasideList`
- `0x180005509`: `ExAllocateFromNPagedLookasideList`
- `0x1800054ef`: `WfpAllocFromNPagedLookasideList`
- `0x180005521`: `WfpAllocFromNPagedLookasideList`

## pseudocode

```c
__int64 __fastcall FwppPrepareL2NetBufferListsForInjection(
        __int64 a1,
        unsigned __int16 a2,
        unsigned int a3,
        __int64 a4,
        __int64 *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v10; // rbx
  __int64 *v11; // r15
  __int64 v12; // r12
  __int64 v13; // rcx
  _QWORD *PacketInfo; // rbp
  __int64 v15; // rcx
  _QWORD *v16; // rdi
  __int64 v17; // rcx
  _QWORD *v18; // rsi
  int v19; // r12d
  __int64 v20; // rcx
  int v21; // r8d
  const char *v22; // rdx
  __int64 v23; // rax
  __int64 v25; // rax
  __int64 v26; // rax

  v10 = 0;
  v11 = 0;
  v12 = a1;
  while ( 1 )
  {
    if ( !a5 )
      return v10;
    PacketInfo = (_QWORD *)FwppGetPacketInfo(a5);
    if ( !PacketInfo || PacketInfo == MmBadPointer || PacketInfo[41] )
      break;
    v16 = ExAllocateFromNPagedLookasideList(&stru_180048500);
    if ( !v16 )
    {
      v25 = WfpReportSysErrorAsNtStatus(v15, (int)"ExAllocateFromNPagedLookasideList", -1073741801);
      v10 = v25;
      if ( v25 )
      {
        WfpReportError(v25, (int)"WfpAllocFromNPagedLookasideList");
LABEL_26:
        WfpReportError(v10, (int)"FwppPrepareL2NetBufferListsForInjection");
        return v10;
      }
    }
    v16[2] = a6;
    v10 = 0;
    v16[3] = a7;
    *(_DWORD *)v16 = 1768978246;
    v18 = ExAllocateFromNPagedLookasideList(&stru_180048140);
    if ( !v18 )
    {
      v26 = WfpReportSysErrorAsNtStatus(v17, (int)"ExAllocateFromNPagedLookasideList", -1073741801);
      v10 = v26;
      if ( v26 )
      {
        WfpReportError(v26, (int)"WfpAllocFromNPagedLookasideList");
        goto LABEL_23;
      }
    }
    v18[1] = a8;
    v18[2] = a9;
    *v18 = v12;
    if ( (WfpNblInfoGetFlags(a5) & 2) != 0 )
    {
      FwppCleanupPreparedL2Nbls(v11);
      v21 = -1071513547;
      v22 = "FwppPrepareL2NetBufferListsForInjection";
LABEL_12:
      v23 = WfpReportSysErrorAsNtStatus(v20, (int)v22, v21);
      goto LABEL_13;
    }
    v19 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))qword_180048108)(a5, a3, a4, a2);
    if ( v19 )
    {
      FwppCleanupPreparedL2Nbls(v11);
      v21 = v19;
      v22 = "allocateNblContext";
      goto LABEL_12;
    }
    a5[14] = (__int64)v11;
    v11 = a5;
    (*((void (__fastcall **)(__int64 *, __int64 (__fastcall *)(), _QWORD *))qword_180048108 + 6))(
      a5,
      FwppL2InjectComplete,
      v18);
    v12 = a1;
    v16[1] = PacketInfo;
    PacketInfo[41] = v16;
    a5 = (__int64 *)*a5;
  }
  v23 = WfpReportSysErrorAsNtStatus(v13, (int)"FwppPrepareL2NetBufferListsForInjection", -1071513547);
  v18 = 0;
  v16 = 0;
LABEL_13:
  v10 = v23;
  if ( !v23 )
    return v10;
  if ( v18 )
    ExFreeToNPagedLookasideList(&stru_180048140, v18);
LABEL_23:
  if ( v16 )
    ExFreeToNPagedLookasideList(&stru_180048500, v16);
  if ( v10 )
    goto LABEL_26;
  return v10;
}

```

## disassembly

```asm
0x180005328  mov     rax, rsp
0x18000532b  mov     [rax+20h], r9
0x18000532f  mov     [rax+18h], r8d
0x180005333  mov     [rax+10h], dx
0x180005337  mov     [rax+8], rcx
0x18000533b  push    rbx
0x18000533c  push    rbp
0x18000533d  push    rsi
0x18000533e  push    rdi
0x18000533f  push    r12
0x180005341  push    r13
0x180005343  push    r14
0x180005345  push    r15
0x180005347  sub     rsp, 38h
0x18000534b  mov     r14, [rsp+78h+arg_20]
0x180005353  xor     ebx, ebx
0x180005355  mov     r13, [rsp+78h+arg_30]
0x18000535d  xor     r15d, r15d
0x180005360  mov     r12, rcx
0x180005363  test    r14, r14
0x180005366  jz      loc_1800054BC
0x18000536c  mov     rcx, r14
0x18000536f  call    FwppGetPacketInfo
0x180005374  mov     rbp, rax
0x180005377  test    rax, rax
0x18000537a  jz      loc_180005549
0x180005380  mov     rax, cs:MmBadPointer
0x180005387  cmp     rbp, [rax]
0x18000538a  jz      loc_180005549
0x180005390  cmp     qword ptr [rbp+148h], 0
0x180005398  jnz     loc_180005549
0x18000539e  lea     rcx, stru_180048500; Lookaside
0x1800053a5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1800053ac  nop     dword ptr [rax+rax+00h]
0x1800053b1  mov     rdi, rax
0x1800053b4  test    rax, rax
0x1800053b7  jz      loc_1800054D1
0x1800053bd  mov     rax, [rsp+78h+arg_28]
0x1800053c5  lea     rcx, stru_180048140; Lookaside
0x1800053cc  mov     [rdi+10h], rax
0x1800053d0  xor     ebx, ebx
0x1800053d2  mov     [rdi+18h], r13
0x1800053d6  mov     dword ptr [rdi], 69707746h
0x1800053dc  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1800053e3  nop     dword ptr [rax+rax+00h]
0x1800053e8  mov     rsi, rax
0x1800053eb  test    rax, rax
0x1800053ee  jz      loc_180005503
0x1800053f4  mov     rax, [rsp+78h+arg_38]
0x1800053fc  mov     rcx, r14
0x1800053ff  mov     [rsi+8], rax
0x180005403  mov     rax, [rsp+78h+arg_40]
0x18000540b  mov     [rsi+10h], rax
0x18000540f  mov     [rsi], r12
0x180005412  call    cs:__imp_WfpNblInfoGetFlags
0x180005419  nop     dword ptr [rax+rax+00h]
0x18000541e  test    al, 2
0x180005420  jnz     short loc_180005496
0x180005422  mov     rax, cs:qword_180048108
0x180005429  mov     rcx, r14
0x18000542c  movzx   r9d, [rsp+78h+arg_8]
0x180005435  mov     r8, [rsp+78h+arg_18]
0x18000543d  mov     edx, [rsp+78h+arg_10]
0x180005444  mov     rax, [rax]
0x180005447  call    _guard_dispatch_icall
0x18000544c  mov     r12d, eax
0x18000544f  test    eax, eax
0x180005451  jnz     loc_180005532
0x180005457  mov     [r14+70h], r15
0x18000545b  lea     rdx, FwppL2InjectComplete
0x180005462  mov     rax, cs:qword_180048108
0x180005469  mov     r8, rsi
0x18000546c  mov     rcx, r14
0x18000546f  mov     r15, r14
0x180005472  mov     rax, [rax+30h]
0x180005476  call    _guard_dispatch_icall
0x18000547b  mov     r12, [rsp+78h+arg_0]
0x180005483  mov     [rdi+8], rbp
0x180005487  mov     [rbp+148h], rdi
0x18000548e  mov     r14, [r14]
0x180005491  jmp     loc_180005363
0x180005496  mov     rcx, r15
0x180005499  call    FwppCleanupPreparedL2Nbls
0x18000549e  mov     r8d, 0C0220035h
0x1800054a4  lea     rdx, aFwpppreparel2n; "FwppPrepareL2NetBufferListsForInjection"
0x1800054ab  call    WfpReportSysErrorAsNtStatus
0x1800054b0  mov     rbx, rax
0x1800054b3  test    rax, rax
0x1800054b6  jnz     loc_180005564
0x1800054bc  mov     rax, rbx
0x1800054bf  add     rsp, 38h
0x1800054c3  pop     r15
0x1800054c5  pop     r14
0x1800054c7  pop     r13
0x1800054c9  pop     r12
0x1800054cb  pop     rdi
0x1800054cc  pop     rsi
0x1800054cd  pop     rbp
0x1800054ce  pop     rbx
0x1800054cf  retn
0x1800054d1  mov     r8d, 0C0000017h
0x1800054d7  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x1800054de  call    WfpReportSysErrorAsNtStatus
0x1800054e3  mov     rbx, rax
0x1800054e6  test    rax, rax
0x1800054e9  jz      loc_1800053BD
0x1800054ef  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x1800054f6  mov     rcx, rax
0x1800054f9  call    WfpReportError
0x1800054fe  jmp     loc_1800055A3
0x180005503  mov     r8d, 0C0000017h
0x180005509  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x180005510  call    WfpReportSysErrorAsNtStatus
0x180005515  mov     rbx, rax
0x180005518  test    rax, rax
0x18000551b  jz      loc_1800053F4
0x180005521  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x180005528  mov     rcx, rax
0x18000552b  call    WfpReportError
0x180005530  jmp     short loc_18000557F
0x180005532  mov     rcx, r15
0x180005535  call    FwppCleanupPreparedL2Nbls
0x18000553a  mov     r8d, r12d
0x18000553d  lea     rdx, aAllocatenblcon; "allocateNblContext"
0x180005544  jmp     loc_1800054AB
0x180005549  mov     r8d, 0C0220035h
0x18000554f  lea     rdx, aFwpppreparel2n; "FwppPrepareL2NetBufferListsForInjection"
0x180005556  call    WfpReportSysErrorAsNtStatus
0x18000555b  xor     esi, esi
0x18000555d  xor     edi, edi
0x18000555f  jmp     loc_1800054B0
0x180005564  test    rsi, rsi
0x180005567  jz      short loc_18000557F
0x180005569  mov     rdx, rsi; Entry
0x18000556c  lea     rcx, stru_180048140; Lookaside
0x180005573  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000557a  nop     dword ptr [rax+rax+00h]
0x18000557f  test    rdi, rdi
0x180005582  jz      short loc_18000559A
0x180005584  mov     rdx, rdi; Entry
0x180005587  lea     rcx, stru_180048500; Lookaside
0x18000558e  call    cs:__imp_ExFreeToNPagedLookasideList
0x180005595  nop     dword ptr [rax+rax+00h]
0x18000559a  test    rbx, rbx
0x18000559d  jz      loc_1800054BC
0x1800055a3  lea     rdx, aFwpppreparel2n; "FwppPrepareL2NetBufferListsForInjection"
0x1800055aa  mov     rcx, rbx
0x1800055ad  call    WfpReportError
0x1800055b2  jmp     loc_1800054BC
```
