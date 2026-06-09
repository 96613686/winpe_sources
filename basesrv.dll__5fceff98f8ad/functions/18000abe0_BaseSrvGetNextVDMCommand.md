# BaseSrvGetNextVDMCommand

- ea: `0x18000abe0`
- end: `0x18000b3fa`
- name: `BaseSrvGetNextVDMCommand`
- size: `2074`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006ca0`
- `0x1800086cc`
- `0x18000996c`
- `0x180009de8`
- `0x18000a090`
- `0x18000a424`
- `0x18000a764`
- `0x18000a790`
- `0x18000a9b4`
- `0x18000ab84`
- `0x18000abe0`
- `0x18000b704`
- `0x18000c9c0`
- `0x18000db11`

## import_xrefs

- `ntdll!NtClose` at `0x18000afeb`
- `ntdll!NtClose` at `0x18000afeb`
- `ntdll!RtlEnterCriticalSection` at `0x18000adf8`
- `ntdll!RtlEnterCriticalSection` at `0x18000adf8`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b3b9`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b3d0`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b3b9`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b3d0`
- `ntdll!NtSetEvent` at `0x18000afdb`
- `ntdll!NtSetEvent` at `0x18000afdb`
- `ntdll!NtResetEvent` at `0x18000b391`
- `ntdll!NtResetEvent` at `0x18000b391`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ac4a`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000acb7`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ace0`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ad09`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ad32`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ad5d`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ad88`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000adb0`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000add5`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ac4a`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000acb7`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ace0`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ad09`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ad32`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ad5d`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ad88`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000adb0`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000add5`

## pseudocode

```c
__int64 __fastcall BaseSrvGetNextVDMCommand(__int64 a1)
{
  __int64 *j; // r15
  unsigned int *v2; // rbx
  __int16 v3; // si
  __int64 v5; // rcx
  unsigned int *i; // r12
  void **v7; // r13
  __int16 v8; // ax
  _QWORD *v10; // r14
  __int64 v11; // rcx
  __int64 v12; // rdx
  int SharedWowRecordByTaskId; // esi
  int v14; // r10d
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdi
  __int64 v18; // rcx
  int ConsoleRecordDosSesId; // eax
  __int16 v20; // r8
  char v21; // r10
  __int64 v22; // r14
  __int64 *v23; // rdi
  int v24; // esi
  __int64 *v25; // rax
  void *v26; // rcx
  void *v27; // rcx
  unsigned int v28; // eax
  const void *v29; // rdx
  void *v30; // rcx
  const void *v31; // rdx
  void *v32; // rcx
  const void *v33; // rdx
  void *v34; // rcx
  const void *v35; // rdx
  void *v36; // rcx
  const void *v37; // rdx
  void *v38; // rcx
  const void *v39; // rdx
  void *v40; // rcx
  const void *v41; // rdx
  void *v42; // rcx
  const void *v43; // rdx
  void *v44; // rcx
  __int64 BatRecord; // rax
  int v46; // r14d
  __int64 v47; // [rsp+20h] [rbp-20h] BYREF
  __int64 v48; // [rsp+28h] [rbp-18h] BYREF
  __int64 v49; // [rsp+30h] [rbp-10h] BYREF
  __int64 v50; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v51; // [rsp+80h] [rbp+40h] BYREF
  int v52; // [rsp+90h] [rbp+50h]
  LONG NumberOfWaitingThreads; // [rsp+98h] [rbp+58h] BYREF

  j = 0;
  v2 = (unsigned int *)(a1 + 64);
  v3 = *(_WORD *)(a1 + 238);
  v48 = 0;
  v5 = *(_QWORD *)(a1 + 8);
  i = 0;
  v49 = 0;
  v50 = 0;
  NumberOfWaitingThreads = 0;
  v47 = 0;
  v51 = 0;
  if ( (int)BaseSrvGetVdmSequence(v5, &v51) < 0 )
    return 3221225485LL;
  v7 = (void **)(v2 + 24);
  if ( !(unsigned __int8)CsrValidateMessageBuffer(a1, v2 + 24, v2[26], 1) )
    return 3221225485LL;
  v8 = *((_WORD *)v2 + 87);
  if ( (v8 & 0x1000) != 0 )
    return BaseSrvEnumWowProcess(v2);
  if ( (v8 & 0x4000) != 0 )
    return BaseSrvEnumWowTask(v2);
  if ( v8 < 0 )
    return BaseSrvAddWowTask(a1, v51);
  v10 = v2 + 16;
  if ( !(unsigned __int8)CsrValidateMessageBuffer(a1, v2 + 16, *((unsigned __int16 *)v2 + 83), 1)
    || !(unsigned __int8)CsrValidateMessageBuffer(a1, v2 + 18, *((unsigned __int16 *)v2 + 84), 1)
    || !(unsigned __int8)CsrValidateMessageBuffer(a1, v2 + 20, *((unsigned __int16 *)v2 + 85), 1)
    || !(unsigned __int8)CsrValidateMessageBuffer(a1, v2 + 22, *((unsigned __int16 *)v2 + 86), 1)
    || !(unsigned __int8)CsrValidateMessageBuffer(a1, v2 + 34, v2[36], 1)
    || !(unsigned __int8)CsrValidateMessageBuffer(a1, v2 + 38, v2[40], 1)
    || !(unsigned __int8)CsrValidateMessageBuffer(a1, v2 + 30, v2[32], 1)
    || !(unsigned __int8)CsrValidateMessageBuffer(a1, v2 + 28, 104, 1) )
  {
    return 3221225485LL;
  }
  v52 = v3 & 2;
  RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
  if ( (v3 & 2) != 0 )
  {
    if ( (*((_WORD *)v2 + 87) & 0x100) != 0 && (v12 = *v2, (_DWORD)v12) )
    {
      SharedWowRecordByTaskId = BaseSrvFindSharedWowRecordByTaskId(v11, v12, &v47, &v48);
      if ( SharedWowRecordByTaskId >= 0 )
      {
        v15 = v47;
        *(_QWORD *)(v47 + 8) = *((_QWORD *)v2 + 1);
        goto LABEL_24;
      }
    }
    else
    {
      SharedWowRecordByTaskId = BaseSrvFindSharedWowRecordByConsoleHandle(v11, *((_QWORD *)v2 + 1), &v47);
      if ( SharedWowRecordByTaskId >= 0 )
      {
        v15 = v47;
LABEL_24:
        if ( v51 == *(_DWORD *)(v15 + 80) )
        {
          v16 = BaseSrvpStaticServerData;
          *((_QWORD *)v2 + 2) = 0;
          *(_BYTE *)(v16 + 2037) = 0;
          for ( i = *(unsigned int **)(v15 + 56); i && i[1]; i = (unsigned int *)*((_QWORD *)i + 4) )
            ;
          if ( i )
          {
            v17 = *((_QWORD *)i + 3);
            if ( v14 )
            {
              SharedWowRecordByTaskId = BaseSrvFillPifInfo(*((_QWORD *)i + 3), v2);
            }
            else
            {
LABEL_73:
              if ( (*((_WORD *)v2 + 87) & 0x400) != 0 )
              {
                v28 = *(_DWORD *)(v17 + 80);
                if ( v28 > v2[26] )
                {
                  SharedWowRecordByTaskId = -1073741811;
                }
                else
                {
                  memmove_0(*v7, *(const void **)(v17 + 72), v28);
                  SharedWowRecordByTaskId = 0;
                }
                v2[26] = *(_DWORD *)(v17 + 80);
              }
              else
              {
                if ( !*v10
                  || *(_WORD *)(v17 + 236) > *((_WORD *)v2 + 83)
                  || *((_QWORD *)v2 + 9) && *(_WORD *)(v17 + 238) > *((_WORD *)v2 + 84)
                  || *v7 && *(_DWORD *)(v17 + 80) > v2[26]
                  || *((_QWORD *)v2 + 10) && *(_WORD *)(v17 + 240) > *((_WORD *)v2 + 85)
                  || *((_QWORD *)v2 + 11) && *(_WORD *)(v17 + 242) > *((_WORD *)v2 + 86)
                  || *((_QWORD *)v2 + 17) && *(_DWORD *)(v17 + 216) > v2[36]
                  || *((_QWORD *)v2 + 19) && *(_DWORD *)(v17 + 232) > v2[40]
                  || *((_QWORD *)v2 + 15) && *(_DWORD *)(v17 + 200) > v2[32] )
                {
                  SharedWowRecordByTaskId = -1073741811;
                }
                else
                {
                  SharedWowRecordByTaskId = 0;
                }
                *((_WORD *)v2 + 83) = *(_WORD *)(v17 + 236);
                *((_WORD *)v2 + 84) = *(_WORD *)(v17 + 238);
                *((_WORD *)v2 + 85) = *(_WORD *)(v17 + 240);
                v2[26] = *(_DWORD *)(v17 + 80);
                *((_WORD *)v2 + 86) = *(_WORD *)(v17 + 242);
                v2[32] = *(_DWORD *)(v17 + 200);
                v2[36] = *(_DWORD *)(v17 + 216);
                v2[40] = *(_DWORD *)(v17 + 232);
                if ( SharedWowRecordByTaskId >= 0 )
                {
                  v29 = *(const void **)(v17 + 40);
                  if ( v29 )
                  {
                    v30 = (void *)*((_QWORD *)v2 + 8);
                    if ( v30 )
                      memmove_0(v30, v29, *(unsigned __int16 *)(v17 + 236));
                  }
                  v31 = *(const void **)(v17 + 48);
                  if ( v31 )
                  {
                    v32 = (void *)*((_QWORD *)v2 + 9);
                    if ( v32 )
                      memmove_0(v32, v31, *(unsigned __int16 *)(v17 + 238));
                  }
                  v33 = *(const void **)(v17 + 56);
                  if ( v33 )
                  {
                    v34 = (void *)*((_QWORD *)v2 + 10);
                    if ( v34 )
                      memmove_0(v34, v33, *(unsigned __int16 *)(v17 + 240));
                  }
                  v35 = *(const void **)(v17 + 64);
                  if ( v35 )
                  {
                    v36 = (void *)*((_QWORD *)v2 + 11);
                    if ( v36 )
                      memmove_0(v36, v35, *(unsigned __int16 *)(v17 + 242));
                  }
                  v37 = *(const void **)(v17 + 208);
                  if ( v37 )
                  {
                    v38 = (void *)*((_QWORD *)v2 + 17);
                    if ( v38 )
                      memmove_0(v38, v37, *(unsigned int *)(v17 + 216));
                  }
                  v39 = *(const void **)(v17 + 224);
                  if ( v39 )
                  {
                    v40 = (void *)*((_QWORD *)v2 + 19);
                    if ( v40 )
                      memmove_0(v40, v39, *(unsigned int *)(v17 + 232));
                  }
                  v41 = *(const void **)(v17 + 72);
                  if ( v41 )
                  {
                    v42 = (void *)*((_QWORD *)v2 + 12);
                    if ( v42 )
                      memmove_0(v42, v41, *(unsigned int *)(v17 + 80));
                  }
                  if ( (*(_WORD *)(v17 + 244) & 0x200) != 0 )
                    memmove_0(*((void **)v2 + 14), (const void *)(v17 + 88), 0x68u);
                  v43 = *(const void **)(v17 + 192);
                  if ( v43 )
                  {
                    v44 = (void *)*((_QWORD *)v2 + 15);
                    if ( v44 )
                      memmove_0(v44, v43, *(unsigned int *)(v17 + 200));
                  }
                  BatRecord = BaseSrvGetBatRecord(*((_QWORD *)v2 + 1));
                  v46 = v52;
                  *((_BYTE *)v2 + 176) = BatRecord != 0;
                  *((_WORD *)v2 + 82) = *(_WORD *)(v17 + 246);
                  v2[12] = *(_DWORD *)(v17 + 12);
                  v2[13] = *(_DWORD *)(v17 + 4);
                  *((_WORD *)v2 + 87) = *(_WORD *)(v17 + 244);
                  if ( v46 )
                  {
                    *v2 = *i;
                    i[1] = 1;
                  }
                  else
                  {
                    *((_DWORD *)j + 2) = 2;
                  }
                  *((_QWORD *)v2 + 3) = *(_QWORD *)(v17 + 16);
                  *((_QWORD *)v2 + 4) = *(_QWORD *)(v17 + 24);
                  *((_QWORD *)v2 + 5) = *(_QWORD *)(v17 + 32);
                  BaseSrvFreeVDMInfo((PVOID)v17);
                  if ( v46 )
                    *((_QWORD *)i + 3) = 0;
                  else
                    j[4] = 0;
                }
              }
            }
            goto LABEL_132;
          }
          *(_QWORD *)((char *)v2 + 166) = 0;
          v2[40] = 0;
          v2[32] = 0;
          v2[26] = 0;
          v2[36] = 0;
          goto LABEL_31;
        }
        goto LABEL_133;
      }
    }
LABEL_132:
    RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
    return (unsigned int)SharedWowRecordByTaskId;
  }
  if ( (*((_WORD *)v2 + 87) & 0x100) != 0 && (v18 = *v2, (_DWORD)v18) )
    ConsoleRecordDosSesId = GetConsoleRecordDosSesId(v18, &v48);
  else
    ConsoleRecordDosSesId = BaseSrvGetConsoleRecord(*((_QWORD *)v2 + 1), &v48);
  if ( ConsoleRecordDosSesId >= 0 )
  {
    v22 = v48;
    if ( v51 == *(_DWORD *)(v48 + 44) )
    {
      v23 = *(__int64 **)(v48 + 72);
      if ( v20 )
      {
        if ( v23 )
        {
          SharedWowRecordByTaskId = BaseSrvFillPifInfo(v23[4], v2);
          if ( !*v2 )
            goto LABEL_132;
          if ( !*(_QWORD *)(v22 + 8) )
          {
            *(_QWORD *)(v22 + 8) = *((_QWORD *)v2 + 1);
            *(_DWORD *)(v22 + 52) = 0;
            goto LABEL_132;
          }
        }
        SharedWowRecordByTaskId = -1073741811;
        goto LABEL_132;
      }
      v24 = v3 & 0x800;
      if ( !v24 )
      {
        if ( (v21 & 0x49) != 0 )
        {
          if ( (v21 & 8) != 0 && v2[14] )
          {
LABEL_55:
            while ( v23 )
            {
              if ( *((_DWORD *)v23 + 2) == 1 )
                goto LABEL_62;
              v23 = (__int64 *)*v23;
            }
            goto LABEL_31;
          }
        }
        else
        {
          if ( (v21 & 8) != 0 )
            goto LABEL_55;
          v25 = 0;
          while ( v23 )
          {
            if ( *((_DWORD *)v23 + 2) == 2 )
              v25 = v23;
            v23 = (__int64 *)*v23;
          }
          v23 = v25;
          if ( !v25 )
          {
LABEL_31:
            SharedWowRecordByTaskId = 0;
            goto LABEL_132;
          }
LABEL_62:
          v26 = (void *)v23[3];
          *((_DWORD *)v23 + 3) = v2[14];
          *((_DWORD *)v23 + 2) = 4;
          NtSetEvent(v26, 0);
          NtClose((HANDLE)v23[3]);
          v23[3] = 0;
        }
      }
      for ( j = *(__int64 **)(v22 + 72); j; j = (__int64 *)*j )
      {
        if ( *((_DWORD *)j + 2) == 1 )
        {
          *((_QWORD *)v2 + 2) = 0;
          v10 = v2 + 16;
          v17 = j[4];
          goto LABEL_73;
        }
      }
      if ( !v24 && (*((_BYTE *)v2 + 174) & 0x88) != 0x88 )
      {
        v27 = *(void **)(v22 + 32);
        if ( v27 )
        {
          NtResetEvent(v27, &NumberOfWaitingThreads);
          goto LABEL_130;
        }
        if ( (int)BaseSrvCreatePairWaitHandles(&v49, &v50) >= 0 )
        {
          *(_QWORD *)(v22 + 32) = v49;
          *(_QWORD *)(v22 + 24) = v50;
LABEL_130:
          SharedWowRecordByTaskId = 0;
          *((_QWORD *)v2 + 2) = *(_QWORD *)(v22 + 24);
          goto LABEL_132;
        }
      }
      *((_QWORD *)v2 + 2) = 0;
      SharedWowRecordByTaskId = -1073741801;
      goto LABEL_132;
    }
  }
LABEL_133:
  RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
  return 3221225485LL;
}

```

## disassembly

```asm
0x18000abe0  mov     [rsp-38h+arg_8], rbx
0x18000abe5  push    rbp
0x18000abe6  push    rsi
0x18000abe7  push    rdi
0x18000abe8  push    r12
0x18000abea  push    r13
0x18000abec  push    r14
0x18000abee  push    r15
0x18000abf0  mov     rbp, rsp
0x18000abf3  sub     rsp, 40h
0x18000abf7  xor     r15d, r15d
0x18000abfa  lea     rbx, [rcx+40h]
0x18000abfe  movzx   esi, word ptr [rbx+0AEh]
0x18000ac05  lea     rdx, [rbp+arg_0]
0x18000ac09  mov     rdi, rcx
0x18000ac0c  mov     [rbp+var_18], r15
0x18000ac10  mov     rcx, [rcx+8]
0x18000ac14  mov     r12d, r15d
0x18000ac17  mov     [rbp+var_10], r15
0x18000ac1b  mov     [rbp+var_8], r15
0x18000ac1f  mov     [rbp+NumberOfWaitingThreads], r15d
0x18000ac23  mov     [rbp+var_20], r15
0x18000ac27  mov     [rbp+arg_0], r15d
0x18000ac2b  call    BaseSrvGetVdmSequence
0x18000ac30  test    eax, eax
0x18000ac32  js      loc_18000B3DC
0x18000ac38  mov     r8d, [rbx+68h]
0x18000ac3c  lea     r13, [rbx+60h]
0x18000ac40  mov     rdx, r13
0x18000ac43  lea     r9d, [r15+1]
0x18000ac47  mov     rcx, rdi
0x18000ac4a  call    cs:__imp_CsrValidateMessageBuffer
0x18000ac51  nop     dword ptr [rax+rax+00h]
0x18000ac56  test    al, al
0x18000ac58  jz      loc_18000B3DC
0x18000ac5e  movzx   eax, word ptr [rbx+0AEh]
0x18000ac65  bt      ax, 0Ch
0x18000ac6a  jnb     short loc_18000AC79
0x18000ac6c  mov     rcx, rbx
0x18000ac6f  call    BaseSrvEnumWowProcess
0x18000ac74  jmp     loc_18000B3E1
0x18000ac79  bt      ax, 0Eh
0x18000ac7e  jnb     short loc_18000AC8D
0x18000ac80  mov     rcx, rbx
0x18000ac83  call    BaseSrvEnumWowTask
0x18000ac88  jmp     loc_18000B3E1
0x18000ac8d  mov     rcx, rdi
0x18000ac90  test    ax, ax
0x18000ac93  jns     short loc_18000ACA2
0x18000ac95  mov     edx, [rbp+arg_0]
0x18000ac98  call    BaseSrvAddWowTask
0x18000ac9d  jmp     loc_18000B3E1
0x18000aca2  movzx   r8d, word ptr [rbx+0A6h]
0x18000acaa  lea     r14, [rbx+40h]
0x18000acae  mov     rdx, r14
0x18000acb1  mov     r9d, 1
0x18000acb7  call    cs:__imp_CsrValidateMessageBuffer
0x18000acbe  nop     dword ptr [rax+rax+00h]
0x18000acc3  test    al, al
0x18000acc5  jz      loc_18000B3DC
0x18000accb  movzx   r8d, word ptr [rbx+0A8h]
0x18000acd3  lea     rdx, [rbx+48h]
0x18000acd7  mov     r9d, 1
0x18000acdd  mov     rcx, rdi
0x18000ace0  call    cs:__imp_CsrValidateMessageBuffer
0x18000ace7  nop     dword ptr [rax+rax+00h]
0x18000acec  test    al, al
0x18000acee  jz      loc_18000B3DC
0x18000acf4  movzx   r8d, word ptr [rbx+0AAh]
0x18000acfc  lea     rdx, [rbx+50h]
0x18000ad00  mov     r9d, 1
0x18000ad06  mov     rcx, rdi
0x18000ad09  call    cs:__imp_CsrValidateMessageBuffer
0x18000ad10  nop     dword ptr [rax+rax+00h]
0x18000ad15  test    al, al
0x18000ad17  jz      loc_18000B3DC
0x18000ad1d  movzx   r8d, word ptr [rbx+0ACh]
0x18000ad25  lea     rdx, [rbx+58h]
0x18000ad29  mov     r9d, 1
0x18000ad2f  mov     rcx, rdi
0x18000ad32  call    cs:__imp_CsrValidateMessageBuffer
0x18000ad39  nop     dword ptr [rax+rax+00h]
0x18000ad3e  test    al, al
0x18000ad40  jz      loc_18000B3DC
0x18000ad46  mov     r8d, [rbx+90h]
0x18000ad4d  lea     rdx, [rbx+88h]
0x18000ad54  mov     r9d, 1
0x18000ad5a  mov     rcx, rdi
0x18000ad5d  call    cs:__imp_CsrValidateMessageBuffer
0x18000ad64  nop     dword ptr [rax+rax+00h]
0x18000ad69  test    al, al
0x18000ad6b  jz      loc_18000B3DC
0x18000ad71  mov     r8d, [rbx+0A0h]
0x18000ad78  lea     rdx, [rbx+98h]
0x18000ad7f  mov     r9d, 1
0x18000ad85  mov     rcx, rdi
0x18000ad88  call    cs:__imp_CsrValidateMessageBuffer
0x18000ad8f  nop     dword ptr [rax+rax+00h]
0x18000ad94  test    al, al
0x18000ad96  jz      loc_18000B3DC
0x18000ad9c  mov     r8d, [rbx+80h]
0x18000ada3  lea     rdx, [rbx+78h]
0x18000ada7  mov     r9d, 1
0x18000adad  mov     rcx, rdi
0x18000adb0  call    cs:__imp_CsrValidateMessageBuffer
0x18000adb7  nop     dword ptr [rax+rax+00h]
0x18000adbc  test    al, al
0x18000adbe  jz      loc_18000B3DC
0x18000adc4  mov     r9d, 1
0x18000adca  lea     rdx, [rbx+70h]
0x18000adce  mov     rcx, rdi
0x18000add1  lea     r8d, [r9+67h]
0x18000add5  call    cs:__imp_CsrValidateMessageBuffer
0x18000addc  nop     dword ptr [rax+rax+00h]
0x18000ade1  test    al, al
0x18000ade3  jz      loc_18000B3DC
0x18000ade9  mov     edi, esi
0x18000adeb  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000adf2  and     edi, 2
0x18000adf5  mov     [rbp+arg_10], edi
0x18000adf8  call    cs:__imp_RtlEnterCriticalSection
0x18000adff  nop     dword ptr [rax+rax+00h]
0x18000ae04  movzx   r10d, word ptr [rbx+0AEh]
0x18000ae0c  mov     eax, 100h
0x18000ae11  test    edi, edi
0x18000ae13  jz      loc_18000AEE6
0x18000ae19  and     r10d, eax
0x18000ae1c  jz      short loc_18000AE49
0x18000ae1e  mov     edx, [rbx]
0x18000ae20  test    edx, edx
0x18000ae22  jz      short loc_18000AE49
0x18000ae24  lea     r9, [rbp+var_18]
0x18000ae28  lea     r8, [rbp+var_20]
0x18000ae2c  call    BaseSrvFindSharedWowRecordByTaskId
0x18000ae31  mov     esi, eax
0x18000ae33  test    eax, eax
0x18000ae35  js      loc_18000B3B2
0x18000ae3b  mov     rcx, [rbp+var_20]
0x18000ae3f  mov     rax, [rbx+8]
0x18000ae43  mov     [rcx+8], rax
0x18000ae47  jmp     short loc_18000AE64
0x18000ae49  mov     rdx, [rbx+8]
0x18000ae4d  lea     r8, [rbp+var_20]
0x18000ae51  call    BaseSrvFindSharedWowRecordByConsoleHandle
0x18000ae56  mov     esi, eax
0x18000ae58  test    eax, eax
0x18000ae5a  js      loc_18000B3B2
0x18000ae60  mov     rcx, [rbp+var_20]
0x18000ae64  mov     eax, [rcx+50h]
0x18000ae67  cmp     [rbp+arg_0], eax
0x18000ae6a  jnz     loc_18000B3C9
0x18000ae70  mov     rax, cs:BaseSrvpStaticServerData
0x18000ae77  mov     [rbx+10h], r15
0x18000ae7b  mov     [rax+7F5h], r15b
0x18000ae82  mov     r12, [rcx+38h]
0x18000ae86  jmp     short loc_18000AE94
0x18000ae88  cmp     [r12+4], r15d
0x18000ae8d  jz      short loc_18000AE99
0x18000ae8f  mov     r12, [r12+20h]
0x18000ae94  test    r12, r12
0x18000ae97  jnz     short loc_18000AE88
0x18000ae99  test    r12, r12
0x18000ae9c  jnz     short loc_18000AEC6
0x18000ae9e  mov     [rbx+0A6h], r15
0x18000aea5  mov     [rbx+0A0h], r15d
0x18000aeac  mov     [rbx+80h], r15d
0x18000aeb3  mov     [rbx+68h], r15d
0x18000aeb7  mov     [rbx+90h], r15d
0x18000aebe  mov     esi, r15d
0x18000aec1  jmp     loc_18000B3B2
0x18000aec6  mov     rdi, [r12+18h]
0x18000aecb  test    r10d, r10d
0x18000aece  jz      loc_18000B06B
0x18000aed4  mov     rdx, rbx
0x18000aed7  mov     rcx, rdi
0x18000aeda  call    BaseSrvFillPifInfo
0x18000aedf  mov     esi, eax
0x18000aee1  jmp     loc_18000B3B2
0x18000aee6  movzx   r8d, r10w
0x18000aeea  and     r8w, ax
0x18000aeee  jz      short loc_18000AF01
0x18000aef0  mov     ecx, [rbx]
0x18000aef2  test    ecx, ecx
0x18000aef4  jz      short loc_18000AF01
0x18000aef6  lea     rdx, [rbp+var_18]
0x18000aefa  call    GetConsoleRecordDosSesId
0x18000aeff  jmp     short loc_18000AF0E
0x18000af01  mov     rcx, [rbx+8]
0x18000af05  lea     rdx, [rbp+var_18]
0x18000af09  call    BaseSrvGetConsoleRecord
0x18000af0e  test    eax, eax
0x18000af10  js      loc_18000B3C9
0x18000af16  mov     r14, [rbp+var_18]
0x18000af1a  mov     eax, [r14+2Ch]
0x18000af1e  cmp     [rbp+arg_0], eax
0x18000af21  jnz     loc_18000B3C9
0x18000af27  mov     rdi, [r14+48h]
0x18000af2b  test    r8w, r8w
0x18000af2f  jz      short loc_18000AF6E
0x18000af31  test    rdi, rdi
0x18000af34  jz      short loc_18000AF64
0x18000af36  mov     rcx, [rdi+20h]
0x18000af3a  mov     rdx, rbx
0x18000af3d  call    BaseSrvFillPifInfo
0x18000af42  mov     esi, eax
0x18000af44  cmp     [rbx], r15d
0x18000af47  jz      loc_18000B3B2
0x18000af4d  cmp     [r14+8], r15
0x18000af51  jnz     short loc_18000AF64
0x18000af53  mov     rax, [rbx+8]
0x18000af57  mov     [r14+8], rax
0x18000af5b  mov     [r14+34h], r15d
0x18000af5f  jmp     loc_18000B3B2
0x18000af64  mov     esi, 0C000000Dh
0x18000af69  jmp     loc_18000B3B2
0x18000af6e  and     esi, 800h
0x18000af74  jnz     loc_18000AFFB
0x18000af7a  test    r10b, 49h
0x18000af7e  jz      short loc_18000AF8E
0x18000af80  test    r10b, 8
0x18000af84  jz      short loc_18000AFFB
0x18000af86  cmp     [rbx+38h], r15d
0x18000af8a  jz      short loc_18000AFFB
0x18000af8c  jmp     short loc_18000AFA2
0x18000af8e  test    r10b, 8
0x18000af92  jnz     short loc_18000AFA2
0x18000af94  mov     rax, r15
0x18000af97  jmp     short loc_18000AFB7
0x18000af99  cmp     dword ptr [rdi+8], 1
0x18000af9d  jz      short loc_18000AFC8
0x18000af9f  mov     rdi, [rdi]
0x18000afa2  test    rdi, rdi
0x18000afa5  jnz     short loc_18000AF99
0x18000afa7  jmp     loc_18000AEBE
0x18000afac  cmp     dword ptr [rdi+8], 2
0x18000afb0  cmovz   rax, rdi
0x18000afb4  mov     rdi, [rdi]
0x18000afb7  test    rdi, rdi
0x18000afba  jnz     short loc_18000AFAC
0x18000afbc  mov     rdi, rax
0x18000afbf  test    rax, rax
0x18000afc2  jz      loc_18000AEBE
0x18000afc8  mov     eax, [rbx+38h]
0x18000afcb  xor     edx, edx; PreviousState
0x18000afcd  mov     rcx, [rdi+18h]; EventHandle
0x18000afd1  mov     [rdi+0Ch], eax
0x18000afd4  mov     dword ptr [rdi+8], 4
0x18000afdb  call    cs:__imp_NtSetEvent
0x18000afe2  nop     dword ptr [rax+rax+00h]
0x18000afe7  mov     rcx, [rdi+18h]; Handle
0x18000afeb  call    cs:__imp_NtClose
0x18000aff2  nop     dword ptr [rax+rax+00h]
0x18000aff7  mov     [rdi+18h], r15
0x18000affb  mov     r15, [r14+48h]
0x18000afff  jmp     short loc_18000B00B
0x18000b001  cmp     dword ptr [r15+8], 1
0x18000b006  jz      short loc_18000B05F
0x18000b008  mov     r15, [r15]
0x18000b00b  test    r15, r15
0x18000b00e  jnz     short loc_18000B001
0x18000b010  test    esi, esi
0x18000b012  jnz     loc_18000B3A9
0x18000b018  mov     al, [rbx+0AEh]
0x18000b01e  and     al, 88h
0x18000b020  cmp     al, 88h
0x18000b022  jz      loc_18000B3A9
0x18000b028  mov     rcx, [r14+20h]; EventHandle
0x18000b02c  test    rcx, rcx
0x18000b02f  jnz     loc_18000B38D
0x18000b035  lea     rdx, [rbp+var_8]
0x18000b039  lea     rcx, [rbp+var_10]
0x18000b03d  call    BaseSrvCreatePairWaitHandles
0x18000b042  test    eax, eax
0x18000b044  js      loc_18000B3A9
0x18000b04a  mov     rax, [rbp+var_10]
0x18000b04e  mov     [r14+20h], rax
0x18000b052  mov     rax, [rbp+var_8]
0x18000b056  mov     [r14+18h], rax
0x18000b05a  jmp     loc_18000B39D
0x18000b05f  mov     [rbx+10h], r12
0x18000b063  lea     r14, [rbx+40h]
0x18000b067  mov     rdi, [r15+20h]
0x18000b06b  mov     eax, 400h
0x18000b070  test    [rbx+0AEh], ax
0x18000b077  jz      short loc_18000B0A5
0x18000b079  mov     eax, [rdi+50h]
0x18000b07c  cmp     eax, [rbx+68h]
0x18000b07f  ja      short loc_18000B095
0x18000b081  mov     rdx, [rdi+48h]; Src
0x18000b085  mov     r8d, eax; Size
0x18000b088  mov     rcx, [r13+0]; void *
0x18000b08c  call    memmove_0
0x18000b091  xor     esi, esi
0x18000b093  jmp     short loc_18000B09A
0x18000b095  mov     esi, 0C000000Dh
0x18000b09a  mov     eax, [rdi+50h]
0x18000b09d  mov     [rbx+68h], eax
0x18000b0a0  jmp     loc_18000B3B2
0x18000b0a5  cmp     qword ptr [r14], 0
0x18000b0a9  jz      loc_18000B164
  ... truncated ...
```
