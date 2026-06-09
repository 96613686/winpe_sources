# RestoreRecipientJob(ushort const *)

- ea: `0x14003f308`
- end: `0x14003f77c`
- name: `?RestoreRecipientJob@@YAHPEBG@Z`
- size: `1140`
- prototype: `__int64 __fastcall(WCHAR *lpFileName, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x14003f784`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x140038090`
- `0x140039e88`
- `0x14003c834`
- `0x14003f308`
- `0x1400410ec`
- `0x14006998c`
- `0x14006af2c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003f399`
- `KERNEL32!GetLastError` at `0x14003f45d`
- `KERNEL32!GetLastError` at `0x14003f508`
- `KERNEL32!GetLastError` at `0x14003f687`
- `KERNEL32!GetLastError` at `0x14003f6ea`
- `KERNEL32!GetLastError` at `0x14003f399`
- `KERNEL32!GetLastError` at `0x14003f45d`
- `KERNEL32!GetLastError` at `0x14003f508`
- `KERNEL32!GetLastError` at `0x14003f687`
- `KERNEL32!GetLastError` at `0x14003f6ea`
- `KERNEL32!DeleteFileW` at `0x14003f435`
- `KERNEL32!DeleteFileW` at `0x14003f435`

## pseudocode

```c
__int64 __fastcall RestoreRecipientJob(WCHAR *lpFileName, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // eax
  struct _JOB_QUEUE_FILE *v6; // rdi
  DWORD LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  struct _LIST_ENTRY *Flink; // rdx
  char v11; // al
  int v12; // edx
  unsigned int v13; // esi
  unsigned int v15; // eax
  struct _JOB_QUEUE *v16; // rax
  struct _JOB_QUEUE *v17; // rbx
  _WORD *v18; // rcx
  __int64 v19; // r10
  _WORD *v20; // r8
  __int64 v21; // rax
  __int64 v22; // rdx
  _WORD *v23; // rcx
  __int64 v24; // r9
  CMapDeviceId *v25; // rcx
  __int64 v26; // rdx
  _WORD *v27; // rax
  __int64 v28; // rdx
  _WORD *v29; // r8
  _WORD *v30; // rcx
  unsigned __int16 *v31; // rax
  void *v32; // rcx
  unsigned __int16 *v33; // rax
  int v34; // eax
  struct _JOB_QUEUE_FILE *v35; // [rsp+68h] [rbp+10h] BYREF

  v35 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  v5 = ReadJobQueueFile(lpFileName, &v35, a3, a4);
  v6 = v35;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    LastError = GetLastError();
    v8 = 67;
    goto LABEL_10;
  }
  if ( !(unsigned int)FixupJobQueueFile(v35) )
    goto LABEL_25;
  Flink = g_QueueListHead.Flink;
  if ( g_QueueListHead.Flink == &g_QueueListHead )
    goto LABEL_15;
  while ( Flink[1].Flink != (struct _LIST_ENTRY *)*((_QWORD *)v6 + 68) )
  {
    Flink = Flink->Flink;
    if ( Flink == &g_QueueListHead )
      goto LABEL_15;
  }
  if ( !Flink )
  {
LABEL_15:
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ii(*((_QWORD *)WPP_GLOBAL_Control + 2), Flink, v9, *((_QWORD *)v6 + 68), *((_QWORD *)v6 + 1));
    }
    if ( DeleteFileW(lpFileName)
      || WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    v11 = GetLastError();
    v12 = 69;
LABEL_24:
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      (_DWORD)lpFileName,
      v11);
    goto LABEL_25;
  }
  v15 = *((_DWORD *)v6 + 10);
  v13 = 1;
  if ( v15 == 2 )
  {
    v15 = 1;
    if ( *((_DWORD *)v6 + 138) )
      v15 = 64;
  }
  v16 = AddRecipientJob(
          &g_QueueListHead,
          (struct _JOB_QUEUE *)Flink,
          (struct _JOB_QUEUE_FILE *)((char *)v6 + 408),
          0,
          v15);
  v17 = v16;
  if ( !v16 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    v11 = GetLastError();
    v12 = 70;
    goto LABEL_24;
  }
  v18 = (_WORD *)((char *)v6 + 1136);
  v19 = 2147483646;
  *((_DWORD *)v16 + 422) = *((_DWORD *)v6 + 412);
  v20 = (_WORD *)((char *)v16 + 1176);
  v21 = 2147483646;
  v22 = 256;
  do
  {
    if ( !v21 )
      break;
    if ( !*v18 )
      break;
    *v20++ = *v18++;
    --v21;
    --v22;
  }
  while ( v22 );
  v23 = v20 - 1;
  v24 = v22 == 0 ? 0x8007007A : 0;
  if ( v22 )
    v23 = v20;
  *v23 = 0;
  if ( !v22 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    v26 = 71;
    goto LABEL_47;
  }
  v27 = (_WORD *)((char *)v6 + 556);
  v28 = 256;
  v29 = (_WORD *)((char *)v17 + 648);
  do
  {
    if ( !v19 )
      break;
    if ( !*v27 )
      break;
    *v29++ = *v27++;
    --v19;
    --v28;
  }
  while ( v28 );
  v30 = v29 - 1;
  v24 = v28 == 0 ? 0x8007007A : 0;
  if ( v28 )
    v30 = v29;
  *v30 = 0;
  if ( !v28 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    v26 = 72;
LABEL_47:
    WPP_SF_d(*((_QWORD *)v25 + 2), v26, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v24);
    goto LABEL_25;
  }
  v31 = StringDup(lpFileName);
  *((_QWORD *)v17 + 7) = v31;
  if ( lpFileName && !v31 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    LastError = GetLastError();
    v8 = 73;
    goto LABEL_10;
  }
  v32 = (void *)*((_QWORD *)v17 + 9);
  *((_QWORD *)v17 + 2) = *((_QWORD *)v6 + 1);
  pMemFree(v32);
  v33 = StringDup(*((unsigned __int16 **)v6 + 6));
  *((_QWORD *)v17 + 9) = v33;
  if ( *((_QWORD *)v6 + 6) && !v33 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    LastError = GetLastError();
    v8 = 74;
LABEL_10:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, LastError);
LABEL_25:
    v13 = 0;
    goto LABEL_26;
  }
  *((_DWORD *)v17 + 148) = *((_DWORD *)v6 + 138);
  v34 = *((_DWORD *)v17 + 461);
  if ( (v34 & 0x200) != 0 )
  {
    ++*(_DWORD *)(*((_QWORD *)v17 + 73) + 380LL);
  }
  else if ( (v34 & 0x100) != 0 )
  {
    ++*(_DWORD *)(*((_QWORD *)v17 + 73) + 376LL);
  }
  else if ( (v34 & 0x80u) != 0 )
  {
    ++*(_DWORD *)(*((_QWORD *)v17 + 73) + 384LL);
  }
  *((_QWORD *)v17 + 145) = *((_QWORD *)v6 + 140);
  *((_QWORD *)v17 + 146) = *((_QWORD *)v6 + 141);
  *((_DWORD *)v17 + 21) = *((_DWORD *)v6 + 15);
  *((_QWORD *)v17 + 3) = *((_QWORD *)v6 + 2);
LABEL_26:
  pMemFree(v6);
  return v13;
}

```

## disassembly

```asm
0x14003f308  mov     [rsp+arg_0], rbx
0x14003f30d  mov     [rsp+arg_10], rbp
0x14003f312  push    rsi
0x14003f313  push    rdi
0x14003f314  push    r12
0x14003f316  push    r13
0x14003f318  push    r14
0x14003f31a  sub     rsp, 30h
0x14003f31e  xor     r14d, r14d
0x14003f321  mov     rbp, rcx
0x14003f324  mov     [rsp+58h+arg_8], r14
0x14003f329  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f330  lea     r12, WPP_GLOBAL_Control
0x14003f337  lea     r13, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003f33e  cmp     rcx, r12
0x14003f341  jz      short loc_14003F35F
0x14003f343  test    byte ptr [rcx+1Ch], 4
0x14003f347  jz      short loc_14003F35F
0x14003f349  cmp     byte ptr [rcx+19h], 5
0x14003f34d  jb      short loc_14003F35F
0x14003f34f  mov     rcx, [rcx+10h]
0x14003f353  lea     edx, [r14+42h]
0x14003f357  mov     r8, r13
0x14003f35a  call    WPP_SF_
0x14003f35f  lea     rdx, [rsp+58h+arg_8]; struct _JOB_QUEUE_FILE **
0x14003f364  mov     rcx, rbp; lpFileName
0x14003f367  call    ?ReadJobQueueFile@@YAHPEBGPEAPEAU_JOB_QUEUE_FILE@@@Z; ReadJobQueueFile(ushort const *,_JOB_QUEUE_FILE * *)
0x14003f36c  mov     rdi, [rsp+58h+arg_8]
0x14003f371  test    eax, eax
0x14003f373  jnz     short loc_14003F3C5
0x14003f375  mov     rax, cs:WPP_GLOBAL_Control
0x14003f37c  cmp     rax, r12
0x14003f37f  jz      loc_14003F488
0x14003f385  test    byte ptr [rax+1Ch], 4
0x14003f389  jz      loc_14003F488
0x14003f38f  cmp     byte ptr [rax+19h], 2
0x14003f393  jb      loc_14003F488
0x14003f399  call    cs:__imp_GetLastError
0x14003f3a0  nop     dword ptr [rax+rax+00h]
0x14003f3a5  mov     edx, 43h ; 'C'
0x14003f3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f3b1  mov     r9d, eax
0x14003f3b4  mov     r8, r13
0x14003f3b7  mov     rcx, [rcx+10h]
0x14003f3bb  call    WPP_SF_d
0x14003f3c0  jmp     loc_14003F488
0x14003f3c5  mov     rcx, rdi; struct _JOB_QUEUE_FILE *
0x14003f3c8  call    ?FixupJobQueueFile@@YAHPEAU_JOB_QUEUE_FILE@@@Z; FixupJobQueueFile(_JOB_QUEUE_FILE *)
0x14003f3cd  test    eax, eax
0x14003f3cf  jz      loc_14003F488
0x14003f3d5  mov     rdx, cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink; struct _JOB_QUEUE *
0x14003f3dc  lea     r10, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x14003f3e3  cmp     rdx, r10
0x14003f3e6  jz      short loc_14003F401
0x14003f3e8  mov     rax, [rdi+220h]
0x14003f3ef  cmp     [rdx+10h], rax
0x14003f3f3  jz      loc_14003F4AD
0x14003f3f9  mov     rdx, [rdx]
0x14003f3fc  cmp     rdx, r10
0x14003f3ff  jnz     short loc_14003F3EF
0x14003f401  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f408  cmp     rcx, r12
0x14003f40b  jz      short loc_14003F432
0x14003f40d  test    byte ptr [rcx+1Ch], 4
0x14003f411  jz      short loc_14003F432
0x14003f413  cmp     byte ptr [rcx+19h], 2
0x14003f417  jb      short loc_14003F432
0x14003f419  mov     rax, [rdi+8]
0x14003f41d  mov     r9, [rdi+220h]
0x14003f424  mov     rcx, [rcx+10h]
0x14003f428  mov     qword ptr [rsp+58h+var_38], rax
0x14003f42d  call    WPP_SF_ii
0x14003f432  mov     rcx, rbp; lpFileName
0x14003f435  call    cs:__imp_DeleteFileW
0x14003f43c  nop     dword ptr [rax+rax+00h]
0x14003f441  test    eax, eax
0x14003f443  jnz     short loc_14003F488
0x14003f445  mov     rax, cs:WPP_GLOBAL_Control
0x14003f44c  cmp     rax, r12
0x14003f44f  jz      short loc_14003F488
0x14003f451  test    byte ptr [rax+1Ch], 4
0x14003f455  jz      short loc_14003F488
0x14003f457  cmp     byte ptr [rax+19h], 2
0x14003f45b  jb      short loc_14003F488
0x14003f45d  call    cs:__imp_GetLastError
0x14003f464  nop     dword ptr [rax+rax+00h]
0x14003f469  mov     edx, 45h ; 'E'
0x14003f46e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f475  mov     r9, rbp
0x14003f478  mov     r8, r13
0x14003f47b  mov     [rsp+58h+var_38], eax
0x14003f47f  mov     rcx, [rcx+10h]
0x14003f483  call    WPP_SF_Sd
0x14003f488  mov     esi, r14d
0x14003f48b  mov     rcx, rdi; lpMem
0x14003f48e  call    pMemFree
0x14003f493  mov     rbx, [rsp+58h+arg_0]
0x14003f498  mov     eax, esi
0x14003f49a  mov     rbp, [rsp+58h+arg_10]
0x14003f49f  add     rsp, 30h
0x14003f4a3  pop     r14
0x14003f4a5  pop     r13
0x14003f4a7  pop     r12
0x14003f4a9  pop     rdi
0x14003f4aa  pop     rsi
0x14003f4ab  retn
0x14003f4ad  test    rdx, rdx
0x14003f4b0  jz      loc_14003F401
0x14003f4b6  mov     eax, [rdi+28h]
0x14003f4b9  mov     esi, 1
0x14003f4be  cmp     eax, 2
0x14003f4c1  jnz     short loc_14003F4D2
0x14003f4c3  cmp     [rdi+228h], r14d
0x14003f4ca  lea     ecx, [rsi+3Fh]
0x14003f4cd  mov     eax, esi
0x14003f4cf  cmovnz  eax, ecx
0x14003f4d2  lea     r8, [rdi+198h]; struct _FAX_PERSONAL_PROFILEW *
0x14003f4d9  mov     [rsp+58h+var_38], eax; unsigned int
0x14003f4dd  xor     r9d, r9d; int
0x14003f4e0  mov     rcx, r10; struct _LIST_ENTRY *
0x14003f4e3  call    ?AddRecipientJob@@YAPEAU_JOB_QUEUE@@QEAU_LIST_ENTRY@@PEAU1@PEBU_FAX_PERSONAL_PROFILEW@@HK@Z; AddRecipientJob(_LIST_ENTRY * const,_JOB_QUEUE *,_FAX_PERSONAL_PROFILEW const *,int,ulong)
0x14003f4e8  mov     rbx, rax
0x14003f4eb  test    rax, rax
0x14003f4ee  jnz     short loc_14003F51C
0x14003f4f0  mov     rax, cs:WPP_GLOBAL_Control
0x14003f4f7  cmp     rax, r12
0x14003f4fa  jz      short loc_14003F488
0x14003f4fc  test    byte ptr [rax+1Ch], 4
0x14003f500  jz      short loc_14003F488
0x14003f502  cmp     byte ptr [rax+19h], 2
0x14003f506  jb      short loc_14003F488
0x14003f508  call    cs:__imp_GetLastError
0x14003f50f  nop     dword ptr [rax+rax+00h]
0x14003f514  lea     edx, [rbx+46h]
0x14003f517  jmp     loc_14003F46E
0x14003f51c  mov     eax, [rdi+670h]
0x14003f522  lea     rcx, [rdi+470h]
0x14003f529  mov     r10d, 7FFFFFFEh
0x14003f52f  mov     [rbx+698h], eax
0x14003f535  mov     r11d, 100h
0x14003f53b  lea     r8, [rbx+498h]
0x14003f542  mov     eax, r10d
0x14003f545  mov     edx, r11d
0x14003f548  test    rax, rax
0x14003f54b  jz      short loc_14003F56B
0x14003f54d  movzx   r9d, word ptr [rcx]
0x14003f551  test    r9w, r9w
0x14003f555  jz      short loc_14003F56B
0x14003f557  mov     [r8], r9w
0x14003f55b  add     rcx, 2
0x14003f55f  add     r8, 2
0x14003f563  sub     rax, rsi
0x14003f566  sub     rdx, rsi
0x14003f569  jnz     short loc_14003F548
0x14003f56b  mov     rax, rdx
0x14003f56e  lea     rcx, [r8-2]
0x14003f572  neg     rax
0x14003f575  sbb     r9d, r9d
0x14003f578  not     r9d
0x14003f57b  and     r9d, 8007007Ah
0x14003f582  test    rdx, rdx
0x14003f585  cmovnz  rcx, r8
0x14003f589  mov     [rcx], r14w
0x14003f58d  jnz     short loc_14003F5C9
0x14003f58f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f596  cmp     rcx, r12
0x14003f599  jz      loc_14003F488
0x14003f59f  test    byte ptr [rcx+1Ch], 4
0x14003f5a3  jz      loc_14003F488
0x14003f5a9  cmp     byte ptr [rcx+19h], 2
0x14003f5ad  jb      loc_14003F488
0x14003f5b3  mov     edx, 47h ; 'G'
0x14003f5b8  mov     rcx, [rcx+10h]
0x14003f5bc  mov     r8, r13
0x14003f5bf  call    WPP_SF_d
0x14003f5c4  jmp     loc_14003F488
0x14003f5c9  lea     rax, [rdi+22Ch]
0x14003f5d0  mov     rdx, r11
0x14003f5d3  lea     r8, [rbx+288h]
0x14003f5da  test    r10, r10
0x14003f5dd  jz      short loc_14003F5FB
0x14003f5df  movzx   ecx, word ptr [rax]
0x14003f5e2  test    cx, cx
0x14003f5e5  jz      short loc_14003F5FB
0x14003f5e7  mov     [r8], cx
0x14003f5eb  add     rax, 2
0x14003f5ef  add     r8, 2
0x14003f5f3  sub     r10, rsi
0x14003f5f6  sub     rdx, rsi
0x14003f5f9  jnz     short loc_14003F5DA
0x14003f5fb  mov     rax, rdx
0x14003f5fe  lea     rcx, [r8-2]
0x14003f602  neg     rax
0x14003f605  sbb     r9d, r9d
0x14003f608  not     r9d
0x14003f60b  and     r9d, 8007007Ah
0x14003f612  test    rdx, rdx
0x14003f615  cmovnz  rcx, r8
0x14003f619  mov     [rcx], r14w
0x14003f61d  jnz     short loc_14003F64D
0x14003f61f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f626  cmp     rcx, r12
0x14003f629  jz      loc_14003F488
0x14003f62f  test    byte ptr [rcx+1Ch], 4
0x14003f633  jz      loc_14003F488
0x14003f639  cmp     byte ptr [rcx+19h], 2
0x14003f63d  jb      loc_14003F488
0x14003f643  mov     edx, 48h ; 'H'
0x14003f648  jmp     loc_14003F5B8
0x14003f64d  mov     rcx, rbp; unsigned __int16 *
0x14003f650  call    StringDup
0x14003f655  mov     [rbx+38h], rax
0x14003f659  test    rbp, rbp
0x14003f65c  jz      short loc_14003F69D
0x14003f65e  test    rax, rax
0x14003f661  jnz     short loc_14003F69D
0x14003f663  mov     rax, cs:WPP_GLOBAL_Control
0x14003f66a  cmp     rax, r12
0x14003f66d  jz      loc_14003F488
0x14003f673  test    byte ptr [rax+1Ch], 4
0x14003f677  jz      loc_14003F488
0x14003f67d  cmp     byte ptr [rax+19h], 2
0x14003f681  jb      loc_14003F488
0x14003f687  call    cs:__imp_GetLastError
0x14003f68e  nop     dword ptr [rax+rax+00h]
0x14003f693  mov     edx, 49h ; 'I'
0x14003f698  jmp     loc_14003F3AA
0x14003f69d  mov     rax, [rdi+8]
0x14003f6a1  mov     rcx, [rbx+48h]; lpMem
0x14003f6a5  mov     [rbx+10h], rax
0x14003f6a9  call    pMemFree
0x14003f6ae  mov     rcx, [rdi+30h]; unsigned __int16 *
0x14003f6b2  call    StringDup
0x14003f6b7  mov     [rbx+48h], rax
0x14003f6bb  cmp     [rdi+30h], r14
0x14003f6bf  jz      short loc_14003F700
0x14003f6c1  test    rax, rax
0x14003f6c4  jnz     short loc_14003F700
0x14003f6c6  mov     rax, cs:WPP_GLOBAL_Control
0x14003f6cd  cmp     rax, r12
0x14003f6d0  jz      loc_14003F488
0x14003f6d6  test    byte ptr [rax+1Ch], 4
0x14003f6da  jz      loc_14003F488
0x14003f6e0  cmp     byte ptr [rax+19h], 2
0x14003f6e4  jb      loc_14003F488
0x14003f6ea  call    cs:__imp_GetLastError
0x14003f6f1  nop     dword ptr [rax+rax+00h]
0x14003f6f6  mov     edx, 4Ah ; 'J'
0x14003f6fb  jmp     loc_14003F3AA
0x14003f700  mov     eax, [rdi+228h]
0x14003f706  mov     [rbx+250h], eax
0x14003f70c  mov     eax, [rbx+734h]
0x14003f712  bt      eax, 9
0x14003f716  jnb     short loc_14003F727
0x14003f718  mov     rax, [rbx+248h]
0x14003f71f  add     [rax+17Ch], esi
0x14003f725  jmp     short loc_14003F74D
0x14003f727  bt      eax, 8
0x14003f72b  jnb     short loc_14003F73C
0x14003f72d  mov     rax, [rbx+248h]
0x14003f734  add     [rax+178h], esi
0x14003f73a  jmp     short loc_14003F74D
0x14003f73c  test    al, al
0x14003f73e  jns     short loc_14003F74D
0x14003f740  mov     rax, [rbx+248h]
0x14003f747  add     [rax+180h], esi
0x14003f74d  mov     rax, [rdi+460h]
0x14003f754  mov     [rbx+488h], rax
0x14003f75b  mov     rax, [rdi+468h]
0x14003f762  mov     [rbx+490h], rax
0x14003f769  mov     eax, [rdi+3Ch]
0x14003f76c  mov     [rbx+54h], eax
0x14003f76f  mov     rax, [rdi+10h]
0x14003f773  mov     [rbx+18h], rax
0x14003f777  jmp     loc_14003F48B
```
