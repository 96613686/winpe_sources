# BaseSrvGetNextVDMCommand

- ea: `0x18000a960`
- end: `0x18000b15a`
- name: `BaseSrvGetNextVDMCommand`
- size: `2042`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006a10`
- `0x1800083dc`
- `0x180009698`
- `0x180009afc`
- `0x180009da4`
- `0x18000a1a0`
- `0x18000a4e0`
- `0x18000a50c`
- `0x18000a72c`
- `0x18000a8fc`
- `0x18000a960`
- `0x18000b458`
- `0x18000c5e4`
- `0x18000d707`

## import_xrefs

- `ntdll!NtClose` at `0x18000ad51`
- `ntdll!NtClose` at `0x18000ad51`
- `ntdll!RtlEnterCriticalSection` at `0x18000ab67`
- `ntdll!RtlEnterCriticalSection` at `0x18000ab67`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b118`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b130`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b118`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b130`
- `ntdll!NtSetEvent` at `0x18000ad41`
- `ntdll!NtSetEvent` at `0x18000ad41`
- `ntdll!NtResetEvent` at `0x18000b0ee`
- `ntdll!NtResetEvent` at `0x18000b0ee`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000a9da`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000aa41`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000aa67`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000aa8d`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000aab3`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000aadb`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ab03`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ab28`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ab4c`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000a9da`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000aa41`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000aa67`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000aa8d`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000aab3`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000aadb`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ab03`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ab28`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000ab4c`

## pseudocode

```c
__int64 __fastcall BaseSrvGetNextVDMCommand(__int64 a1)
{
  int v1; // ebx
  unsigned int *v2; // rdi
  __int16 v3; // ax
  __int64 v5; // rcx
  int v6; // esi
  __int64 *v7; // r14
  __int64 *j; // r12
  __int16 v9; // ax
  __int64 v11; // rcx
  int v12; // r10d
  int SharedWowRecordByTaskId; // r14d
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned int *i; // r15
  __int64 v17; // rsi
  int ConsoleRecordDosSesId; // eax
  __int16 v19; // r8
  char v20; // r10
  __int64 v21; // r15
  __int64 *v22; // rsi
  int v23; // eax
  void *v24; // rcx
  void *v25; // rcx
  unsigned int v26; // eax
  const void *v27; // rdx
  void *v28; // rcx
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
  LONG NumberOfWaitingThreads; // [rsp+20h] [rbp-30h] BYREF
  __int64 v44; // [rsp+28h] [rbp-28h] BYREF
  __int64 v45; // [rsp+30h] [rbp-20h] BYREF
  __int64 v46; // [rsp+38h] [rbp-18h] BYREF
  __int64 v47; // [rsp+40h] [rbp-10h] BYREF
  int v48; // [rsp+90h] [rbp+40h] BYREF
  int v49; // [rsp+A0h] [rbp+50h] BYREF
  int v50; // [rsp+A8h] [rbp+58h]

  v1 = 0;
  v2 = (unsigned int *)(a1 + 64);
  v3 = *(_WORD *)(a1 + 238);
  v45 = 0;
  v46 = 0;
  v5 = *(_QWORD *)(a1 + 8);
  v6 = v3 & 2;
  v47 = 0;
  v50 = v6;
  v7 = 0;
  NumberOfWaitingThreads = 0;
  j = 0;
  v44 = 0;
  v49 = v3 & 0x800;
  v48 = 0;
  if ( (int)BaseSrvGetVdmSequence(v5, &v48) < 0 || !(unsigned __int8)CsrValidateMessageBuffer(a1, v2 + 24, v2[26], 1) )
    return 3221225485LL;
  v9 = *((_WORD *)v2 + 87);
  if ( (v9 & 0x1000) != 0 )
    return BaseSrvEnumWowProcess(v2);
  if ( (v9 & 0x4000) != 0 )
    return BaseSrvEnumWowTask(v2);
  if ( v9 < 0 )
    return BaseSrvAddWowTask(a1, v48);
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
  RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
  if ( v6 )
  {
    if ( (*((_WORD *)v2 + 87) & 0x100) != 0 && *v2 )
    {
      SharedWowRecordByTaskId = BaseSrvFindSharedWowRecordByTaskId(v11, *v2, &v44, &v49);
      if ( SharedWowRecordByTaskId >= 0 )
      {
        v14 = v44;
        *(_QWORD *)(v44 + 8) = *((_QWORD *)v2 + 1);
        goto LABEL_24;
      }
    }
    else
    {
      SharedWowRecordByTaskId = BaseSrvFindSharedWowRecordByConsoleHandle(v11, *((_QWORD *)v2 + 1), &v44);
      if ( SharedWowRecordByTaskId >= 0 )
      {
        v14 = v44;
LABEL_24:
        if ( v48 == *(_DWORD *)(v14 + 80) )
        {
          v15 = BaseSrvpStaticServerData;
          *((_QWORD *)v2 + 2) = 0;
          *(_BYTE *)(v15 + 2037) = 0;
          for ( i = *(unsigned int **)(v14 + 56); i && i[1]; i = (unsigned int *)*((_QWORD *)i + 4) )
            ;
          if ( i )
          {
            v17 = *((_QWORD *)i + 3);
            if ( v12 )
            {
              SharedWowRecordByTaskId = BaseSrvFillPifInfo(*((_QWORD *)i + 3), v2);
              goto LABEL_132;
            }
LABEL_73:
            if ( (*((_WORD *)v2 + 87) & 0x400) == 0 )
            {
              if ( !*((_QWORD *)v2 + 8)
                || *(_WORD *)(v17 + 236) > *((_WORD *)v2 + 83)
                || *((_QWORD *)v2 + 9) && *(_WORD *)(v17 + 238) > *((_WORD *)v2 + 84)
                || *((_QWORD *)v2 + 12) && *(_DWORD *)(v17 + 80) > v2[26]
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
                v27 = *(const void **)(v17 + 40);
                if ( v27 )
                {
                  v28 = (void *)*((_QWORD *)v2 + 8);
                  if ( v28 )
                    memmove_0(v28, v27, *(unsigned __int16 *)(v17 + 236));
                }
                v29 = *(const void **)(v17 + 48);
                if ( v29 )
                {
                  v30 = (void *)*((_QWORD *)v2 + 9);
                  if ( v30 )
                    memmove_0(v30, v29, *(unsigned __int16 *)(v17 + 238));
                }
                v31 = *(const void **)(v17 + 56);
                if ( v31 )
                {
                  v32 = (void *)*((_QWORD *)v2 + 10);
                  if ( v32 )
                    memmove_0(v32, v31, *(unsigned __int16 *)(v17 + 240));
                }
                v33 = *(const void **)(v17 + 64);
                if ( v33 )
                {
                  v34 = (void *)*((_QWORD *)v2 + 11);
                  if ( v34 )
                    memmove_0(v34, v33, *(unsigned __int16 *)(v17 + 242));
                }
                v35 = *(const void **)(v17 + 208);
                if ( v35 )
                {
                  v36 = (void *)*((_QWORD *)v2 + 17);
                  if ( v36 )
                    memmove_0(v36, v35, *(unsigned int *)(v17 + 216));
                }
                v37 = *(const void **)(v17 + 224);
                if ( v37 )
                {
                  v38 = (void *)*((_QWORD *)v2 + 19);
                  if ( v38 )
                    memmove_0(v38, v37, *(unsigned int *)(v17 + 232));
                }
                v39 = *(const void **)(v17 + 72);
                if ( v39 )
                {
                  v40 = (void *)*((_QWORD *)v2 + 12);
                  if ( v40 )
                    memmove_0(v40, v39, *(unsigned int *)(v17 + 80));
                }
                if ( (*(_WORD *)(v17 + 244) & 0x200) != 0 )
                  memmove_0(*((void **)v2 + 14), (const void *)(v17 + 88), 0x68u);
                v41 = *(const void **)(v17 + 192);
                if ( v41 )
                {
                  v42 = (void *)*((_QWORD *)v2 + 15);
                  if ( v42 )
                    memmove_0(v42, v41, *(unsigned int *)(v17 + 200));
                }
                *(_BYTE *)(a1 + 240) = BaseSrvGetBatRecord(*((_QWORD *)v2 + 1)) != 0;
                *(_WORD *)(a1 + 228) = *(_WORD *)(v17 + 246);
                *(_DWORD *)(a1 + 112) = *(_DWORD *)(v17 + 12);
                *(_DWORD *)(a1 + 116) = *(_DWORD *)(v17 + 4);
                *(_WORD *)(a1 + 238) = *(_WORD *)(v17 + 244);
                if ( v50 )
                {
                  *v2 = *i;
                  i[1] = 1;
                }
                else
                {
                  *((_DWORD *)j + 2) = 2;
                }
                *(_QWORD *)(a1 + 88) = *(_QWORD *)(v17 + 16);
                *(_QWORD *)(a1 + 96) = *(_QWORD *)(v17 + 24);
                *(_QWORD *)(a1 + 104) = *(_QWORD *)(v17 + 32);
                BaseSrvFreeVDMInfo((PVOID)v17);
                if ( v50 )
                  *((_QWORD *)i + 3) = 0;
                else
                  j[4] = 0;
              }
              goto LABEL_132;
            }
            v26 = *(_DWORD *)(v17 + 80);
            if ( v26 > v2[26] )
              v1 = -1073741811;
            else
              memmove_0(*((void **)v2 + 12), *(const void **)(v17 + 72), v26);
            v2[26] = *(_DWORD *)(v17 + 80);
          }
          else
          {
            *(_QWORD *)((char *)v2 + 166) = 0;
            v2[40] = 0;
            v2[32] = 0;
            v2[26] = 0;
            v2[36] = 0;
          }
          goto LABEL_31;
        }
        goto LABEL_133;
      }
    }
LABEL_132:
    RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
    return (unsigned int)SharedWowRecordByTaskId;
  }
  if ( (*((_WORD *)v2 + 87) & 0x100) != 0 && *v2 )
    ConsoleRecordDosSesId = GetConsoleRecordDosSesId(*v2, &v45);
  else
    ConsoleRecordDosSesId = BaseSrvGetConsoleRecord(*((_QWORD *)v2 + 1), &v45);
  if ( ConsoleRecordDosSesId >= 0 )
  {
    v21 = v45;
    if ( v48 == *(_DWORD *)(v45 + 44) )
    {
      v22 = *(__int64 **)(v45 + 72);
      if ( v19 )
      {
        if ( v22 )
        {
          SharedWowRecordByTaskId = BaseSrvFillPifInfo(v22[4], v2);
          if ( !*v2 )
            goto LABEL_132;
          if ( !*(_QWORD *)(v21 + 8) )
          {
            *(_QWORD *)(v21 + 8) = *((_QWORD *)v2 + 1);
            *(_DWORD *)(v21 + 52) = 0;
            goto LABEL_132;
          }
        }
        SharedWowRecordByTaskId = -1073741811;
        goto LABEL_132;
      }
      v23 = v49;
      if ( !v49 )
      {
        if ( (v20 & 0x49) != 0 )
        {
          if ( (v20 & 8) != 0 && v2[14] )
          {
LABEL_55:
            while ( v22 )
            {
              if ( *((_DWORD *)v22 + 2) == 1 )
                goto LABEL_62;
              v22 = (__int64 *)*v22;
            }
            goto LABEL_31;
          }
        }
        else
        {
          if ( (v20 & 8) != 0 )
            goto LABEL_55;
          while ( v22 )
          {
            if ( *((_DWORD *)v22 + 2) == 2 )
              v7 = v22;
            v22 = (__int64 *)*v22;
          }
          v22 = v7;
          if ( !v7 )
            goto LABEL_31;
LABEL_62:
          v24 = (void *)v22[3];
          *((_DWORD *)v22 + 3) = v2[14];
          *((_DWORD *)v22 + 2) = 4;
          NtSetEvent(v24, 0);
          NtClose((HANDLE)v22[3]);
          v23 = v49;
          v22[3] = 0;
        }
      }
      for ( j = *(__int64 **)(v21 + 72); j; j = (__int64 *)*j )
      {
        if ( *((_DWORD *)j + 2) == 1 )
        {
          *((_QWORD *)v2 + 2) = 0;
          i = 0;
          v17 = j[4];
          goto LABEL_73;
        }
      }
      if ( !v23 && (*((_BYTE *)v2 + 174) & 0x88) != 0x88 )
      {
        v25 = *(void **)(v21 + 32);
        if ( v25 )
        {
          NtResetEvent(v25, &NumberOfWaitingThreads);
          goto LABEL_130;
        }
        if ( (int)BaseSrvCreatePairWaitHandles(&v46, &v47) >= 0 )
        {
          *(_QWORD *)(v21 + 32) = v46;
          *(_QWORD *)(v21 + 24) = v47;
LABEL_130:
          *((_QWORD *)v2 + 2) = *(_QWORD *)(v21 + 24);
LABEL_31:
          SharedWowRecordByTaskId = v1;
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
0x18000a960  mov     [rsp-38h+arg_8], rbx
0x18000a965  push    rbp
0x18000a966  push    rsi
0x18000a967  push    rdi
0x18000a968  push    r12
0x18000a96a  push    r13
0x18000a96c  push    r14
0x18000a96e  push    r15
0x18000a970  mov     rbp, rsp
0x18000a973  sub     rsp, 50h
0x18000a977  xor     ebx, ebx
0x18000a979  lea     rdi, [rcx+40h]
0x18000a97d  movzx   eax, word ptr [rdi+0AEh]
0x18000a984  lea     rdx, [rbp+arg_0]
0x18000a988  mov     esi, eax
0x18000a98a  mov     [rbp+var_20], rbx
0x18000a98e  mov     r13, rcx
0x18000a991  mov     [rbp+var_18], rbx
0x18000a995  mov     rcx, [rcx+8]
0x18000a999  and     eax, 800h
0x18000a99e  and     esi, 2
0x18000a9a1  mov     [rbp+var_10], rbx
0x18000a9a5  mov     [rbp+arg_18], esi
0x18000a9a8  mov     r14d, ebx
0x18000a9ab  mov     [rbp+NumberOfWaitingThreads], ebx
0x18000a9ae  mov     r12d, ebx
0x18000a9b1  mov     [rbp+var_28], rbx
0x18000a9b5  mov     [rbp+arg_10], eax
0x18000a9b8  mov     [rbp+arg_0], ebx
0x18000a9bb  call    BaseSrvGetVdmSequence
0x18000a9c0  test    eax, eax
0x18000a9c2  js      loc_18000B13C
0x18000a9c8  mov     r8d, [rdi+68h]
0x18000a9cc  lea     r15d, [rbx+1]
0x18000a9d0  mov     r9d, r15d
0x18000a9d3  lea     rdx, [rdi+60h]
0x18000a9d7  mov     rcx, r13
0x18000a9da  call    cs:__imp_CsrValidateMessageBuffer
0x18000a9e1  nop     dword ptr [rax+rax+00h]
0x18000a9e6  test    al, al
0x18000a9e8  jz      loc_18000B13C
0x18000a9ee  movzx   eax, word ptr [rdi+0AEh]
0x18000a9f5  bt      ax, 0Ch
0x18000a9fa  jnb     short loc_18000AA09
0x18000a9fc  mov     rcx, rdi
0x18000a9ff  call    BaseSrvEnumWowProcess
0x18000aa04  jmp     loc_18000B141
0x18000aa09  bt      ax, 0Eh
0x18000aa0e  jnb     short loc_18000AA1D
0x18000aa10  mov     rcx, rdi
0x18000aa13  call    BaseSrvEnumWowTask
0x18000aa18  jmp     loc_18000B141
0x18000aa1d  mov     rcx, r13
0x18000aa20  test    ax, ax
0x18000aa23  jns     short loc_18000AA32
0x18000aa25  mov     edx, [rbp+arg_0]
0x18000aa28  call    BaseSrvAddWowTask
0x18000aa2d  jmp     loc_18000B141
0x18000aa32  movzx   r8d, word ptr [rdi+0A6h]
0x18000aa3a  lea     rdx, [rdi+40h]
0x18000aa3e  mov     r9d, r15d
0x18000aa41  call    cs:__imp_CsrValidateMessageBuffer
0x18000aa48  nop     dword ptr [rax+rax+00h]
0x18000aa4d  test    al, al
0x18000aa4f  jz      loc_18000B13C
0x18000aa55  movzx   r8d, word ptr [rdi+0A8h]
0x18000aa5d  lea     rdx, [rdi+48h]
0x18000aa61  mov     r9d, r15d
0x18000aa64  mov     rcx, r13
0x18000aa67  call    cs:__imp_CsrValidateMessageBuffer
0x18000aa6e  nop     dword ptr [rax+rax+00h]
0x18000aa73  test    al, al
0x18000aa75  jz      loc_18000B13C
0x18000aa7b  movzx   r8d, word ptr [rdi+0AAh]
0x18000aa83  lea     rdx, [rdi+50h]
0x18000aa87  mov     r9d, r15d
0x18000aa8a  mov     rcx, r13
0x18000aa8d  call    cs:__imp_CsrValidateMessageBuffer
0x18000aa94  nop     dword ptr [rax+rax+00h]
0x18000aa99  test    al, al
0x18000aa9b  jz      loc_18000B13C
0x18000aaa1  movzx   r8d, word ptr [rdi+0ACh]
0x18000aaa9  lea     rdx, [rdi+58h]
0x18000aaad  mov     r9d, r15d
0x18000aab0  mov     rcx, r13
0x18000aab3  call    cs:__imp_CsrValidateMessageBuffer
0x18000aaba  nop     dword ptr [rax+rax+00h]
0x18000aabf  test    al, al
0x18000aac1  jz      loc_18000B13C
0x18000aac7  mov     r8d, [rdi+90h]
0x18000aace  lea     rdx, [rdi+88h]
0x18000aad5  mov     r9d, r15d
0x18000aad8  mov     rcx, r13
0x18000aadb  call    cs:__imp_CsrValidateMessageBuffer
0x18000aae2  nop     dword ptr [rax+rax+00h]
0x18000aae7  test    al, al
0x18000aae9  jz      loc_18000B13C
0x18000aaef  mov     r8d, [rdi+0A0h]
0x18000aaf6  lea     rdx, [rdi+98h]
0x18000aafd  mov     r9d, r15d
0x18000ab00  mov     rcx, r13
0x18000ab03  call    cs:__imp_CsrValidateMessageBuffer
0x18000ab0a  nop     dword ptr [rax+rax+00h]
0x18000ab0f  test    al, al
0x18000ab11  jz      loc_18000B13C
0x18000ab17  mov     r8d, [rdi+80h]
0x18000ab1e  lea     rdx, [rdi+78h]
0x18000ab22  mov     r9d, r15d
0x18000ab25  mov     rcx, r13
0x18000ab28  call    cs:__imp_CsrValidateMessageBuffer
0x18000ab2f  nop     dword ptr [rax+rax+00h]
0x18000ab34  test    al, al
0x18000ab36  jz      loc_18000B13C
0x18000ab3c  lea     rdx, [rdi+70h]
0x18000ab40  mov     r9d, r15d
0x18000ab43  mov     r8d, 68h ; 'h'
0x18000ab49  mov     rcx, r13
0x18000ab4c  call    cs:__imp_CsrValidateMessageBuffer
0x18000ab53  nop     dword ptr [rax+rax+00h]
0x18000ab58  test    al, al
0x18000ab5a  jz      loc_18000B13C
0x18000ab60  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000ab67  call    cs:__imp_RtlEnterCriticalSection
0x18000ab6e  nop     dword ptr [rax+rax+00h]
0x18000ab73  movzx   r10d, word ptr [rdi+0AEh]
0x18000ab7b  mov     eax, 100h
0x18000ab80  test    esi, esi
0x18000ab82  jz      loc_18000AC50
0x18000ab88  and     r10d, eax
0x18000ab8b  jz      short loc_18000ABB9
0x18000ab8d  cmp     [rdi], ebx
0x18000ab8f  jz      short loc_18000ABB9
0x18000ab91  mov     edx, [rdi]
0x18000ab93  lea     r9, [rbp+arg_10]
0x18000ab97  lea     r8, [rbp+var_28]
0x18000ab9b  call    BaseSrvFindSharedWowRecordByTaskId
0x18000aba0  mov     r14d, eax
0x18000aba3  test    eax, eax
0x18000aba5  js      loc_18000B111
0x18000abab  mov     rcx, [rbp+var_28]
0x18000abaf  mov     rax, [rdi+8]
0x18000abb3  mov     [rcx+8], rax
0x18000abb7  jmp     short loc_18000ABD5
0x18000abb9  mov     rdx, [rdi+8]
0x18000abbd  lea     r8, [rbp+var_28]
0x18000abc1  call    BaseSrvFindSharedWowRecordByConsoleHandle
0x18000abc6  mov     r14d, eax
0x18000abc9  test    eax, eax
0x18000abcb  js      loc_18000B111
0x18000abd1  mov     rcx, [rbp+var_28]
0x18000abd5  mov     eax, [rcx+50h]
0x18000abd8  cmp     [rbp+arg_0], eax
0x18000abdb  jnz     loc_18000B129
0x18000abe1  mov     rax, cs:BaseSrvpStaticServerData
0x18000abe8  mov     [rdi+10h], rbx
0x18000abec  mov     [rax+7F5h], bl
0x18000abf2  mov     r15, [rcx+38h]
0x18000abf6  jmp     short loc_18000AC02
0x18000abf8  cmp     [r15+4], ebx
0x18000abfc  jz      short loc_18000AC07
0x18000abfe  mov     r15, [r15+20h]
0x18000ac02  test    r15, r15
0x18000ac05  jnz     short loc_18000ABF8
0x18000ac07  test    r15, r15
0x18000ac0a  jnz     short loc_18000AC30
0x18000ac0c  mov     [rdi+0A6h], rbx
0x18000ac13  mov     [rdi+0A0h], ebx
0x18000ac19  mov     [rdi+80h], ebx
0x18000ac1f  mov     [rdi+68h], ebx
0x18000ac22  mov     [rdi+90h], ebx
0x18000ac28  mov     r14d, ebx
0x18000ac2b  jmp     loc_18000B111
0x18000ac30  mov     rsi, [r15+18h]
0x18000ac34  test    r10d, r10d
0x18000ac37  jz      loc_18000ADD6
0x18000ac3d  mov     rdx, rdi
0x18000ac40  mov     rcx, rsi
0x18000ac43  call    BaseSrvFillPifInfo
0x18000ac48  mov     r14d, eax
0x18000ac4b  jmp     loc_18000B111
0x18000ac50  movzx   r8d, r10w
0x18000ac54  and     r8w, ax
0x18000ac58  jz      short loc_18000AC6B
0x18000ac5a  cmp     [rdi], ebx
0x18000ac5c  jz      short loc_18000AC6B
0x18000ac5e  mov     ecx, [rdi]
0x18000ac60  lea     rdx, [rbp+var_20]
0x18000ac64  call    GetConsoleRecordDosSesId
0x18000ac69  jmp     short loc_18000AC78
0x18000ac6b  mov     rcx, [rdi+8]
0x18000ac6f  lea     rdx, [rbp+var_20]
0x18000ac73  call    BaseSrvGetConsoleRecord
0x18000ac78  test    eax, eax
0x18000ac7a  js      loc_18000B129
0x18000ac80  mov     r15, [rbp+var_20]
0x18000ac84  mov     eax, [r15+2Ch]
0x18000ac88  cmp     [rbp+arg_0], eax
0x18000ac8b  jnz     loc_18000B129
0x18000ac91  mov     rsi, [r15+48h]
0x18000ac95  test    r8w, r8w
0x18000ac99  jz      short loc_18000ACD9
0x18000ac9b  test    rsi, rsi
0x18000ac9e  jz      short loc_18000ACCE
0x18000aca0  mov     rcx, [rsi+20h]
0x18000aca4  mov     rdx, rdi
0x18000aca7  call    BaseSrvFillPifInfo
0x18000acac  mov     r14d, eax
0x18000acaf  cmp     [rdi], ebx
0x18000acb1  jz      loc_18000B111
0x18000acb7  cmp     [r15+8], rbx
0x18000acbb  jnz     short loc_18000ACCE
0x18000acbd  mov     rax, [rdi+8]
0x18000acc1  mov     [r15+8], rax
0x18000acc5  mov     [r15+34h], ebx
0x18000acc9  jmp     loc_18000B111
0x18000acce  mov     r14d, 0C000000Dh
0x18000acd4  jmp     loc_18000B111
0x18000acd9  mov     eax, [rbp+arg_10]
0x18000acdc  test    eax, eax
0x18000acde  jnz     loc_18000AD64
0x18000ace4  test    r10b, 49h
0x18000ace8  jz      short loc_18000ACF7
0x18000acea  test    r10b, 8
0x18000acee  jz      short loc_18000AD64
0x18000acf0  cmp     [rdi+38h], ebx
0x18000acf3  jz      short loc_18000AD64
0x18000acf5  jmp     short loc_18000AD08
0x18000acf7  test    r10b, 8
0x18000acfb  jz      short loc_18000AD1D
0x18000acfd  jmp     short loc_18000AD08
0x18000acff  cmp     dword ptr [rsi+8], 1
0x18000ad03  jz      short loc_18000AD2E
0x18000ad05  mov     rsi, [rsi]
0x18000ad08  test    rsi, rsi
0x18000ad0b  jnz     short loc_18000ACFF
0x18000ad0d  jmp     loc_18000AC28
0x18000ad12  cmp     dword ptr [rsi+8], 2
0x18000ad16  cmovz   r14, rsi
0x18000ad1a  mov     rsi, [rsi]
0x18000ad1d  test    rsi, rsi
0x18000ad20  jnz     short loc_18000AD12
0x18000ad22  mov     rsi, r14
0x18000ad25  test    r14, r14
0x18000ad28  jz      loc_18000AC28
0x18000ad2e  mov     eax, [rdi+38h]
0x18000ad31  xor     edx, edx; PreviousState
0x18000ad33  mov     rcx, [rsi+18h]; EventHandle
0x18000ad37  mov     [rsi+0Ch], eax
0x18000ad3a  mov     dword ptr [rsi+8], 4
0x18000ad41  call    cs:__imp_NtSetEvent
0x18000ad48  nop     dword ptr [rax+rax+00h]
0x18000ad4d  mov     rcx, [rsi+18h]; Handle
0x18000ad51  call    cs:__imp_NtClose
0x18000ad58  nop     dword ptr [rax+rax+00h]
0x18000ad5d  mov     eax, [rbp+arg_10]
0x18000ad60  mov     [rsi+18h], rbx
0x18000ad64  mov     r12, [r15+48h]
0x18000ad68  jmp     short loc_18000AD76
0x18000ad6a  cmp     dword ptr [r12+8], 1
0x18000ad70  jz      short loc_18000ADCA
0x18000ad72  mov     r12, [r12]
0x18000ad76  test    r12, r12
0x18000ad79  jnz     short loc_18000AD6A
0x18000ad7b  test    eax, eax
0x18000ad7d  jnz     loc_18000B107
0x18000ad83  mov     al, [rdi+0AEh]
0x18000ad89  and     al, 88h
0x18000ad8b  cmp     al, 88h
0x18000ad8d  jz      loc_18000B107
0x18000ad93  mov     rcx, [r15+20h]; EventHandle
0x18000ad97  test    rcx, rcx
0x18000ad9a  jnz     loc_18000B0EA
0x18000ada0  lea     rdx, [rbp+var_10]
0x18000ada4  lea     rcx, [rbp+var_18]
0x18000ada8  call    BaseSrvCreatePairWaitHandles
0x18000adad  test    eax, eax
0x18000adaf  js      loc_18000B107
0x18000adb5  mov     rax, [rbp+var_18]
0x18000adb9  mov     [r15+20h], rax
0x18000adbd  mov     rax, [rbp+var_10]
0x18000adc1  mov     [r15+18h], rax
0x18000adc5  jmp     loc_18000B0FA
0x18000adca  mov     [rdi+10h], rbx
0x18000adce  mov     r15, rbx
0x18000add1  mov     rsi, [r12+20h]
0x18000add6  mov     eax, 400h
0x18000addb  test    [rdi+0AEh], ax
0x18000ade2  jz      short loc_18000AE0E
0x18000ade4  mov     eax, [rsi+50h]
0x18000ade7  cmp     eax, [rdi+68h]
0x18000adea  ja      short loc_18000ADFE
0x18000adec  mov     rdx, [rsi+48h]; Src
0x18000adf0  mov     r8d, eax; Size
0x18000adf3  mov     rcx, [rdi+60h]; void *
0x18000adf7  call    memmove_0
0x18000adfc  jmp     short loc_18000AE03
0x18000adfe  mov     ebx, 0C000000Dh
0x18000ae03  mov     eax, [rsi+50h]
0x18000ae06  mov     [rdi+68h], eax
0x18000ae09  jmp     loc_18000AC28
  ... truncated ...
```
