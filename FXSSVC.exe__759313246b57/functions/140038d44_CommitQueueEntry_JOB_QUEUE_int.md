# CommitQueueEntry(_JOB_QUEUE *,int)

- ea: `0x140038d44`
- end: `0x140039505`
- name: `?CommitQueueEntry@@YAHPEAU_JOB_QUEUE@@H@Z`
- size: `1985`
- prototype: `__int64 __fastcall(struct _JOB_QUEUE *, int)`
- caller_count: `7`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14003354c`
- `0x14003437c`
- `0x14003735c`
- `0x140038090`
- `0x14003de98`
- `0x14003fa40`
- `0x140040c14`

## callees

- `0x140002946`
- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140004cec`
- `0x140004fe4`
- `0x140037184`
- `0x140038870`
- `0x140038aa4`
- `0x140038d44`
- `0x14003995c`
- `0x14003b264`
- `0x14003c2fc`
- `0x14003ff64`
- `0x140040fb8`
- `0x1400698ec`
- `0x14006998c`
- `0x14006aec0`
- `0x14006e124`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x14003901b`
- `ADVAPI32!GetLengthSid` at `0x14003901b`
- `ADVAPI32!IsValidSid` at `0x140038da4`
- `ADVAPI32!IsValidSid` at `0x140038da4`
- `KERNEL32!GetLastError` at `0x14003929d`
- `KERNEL32!GetLastError` at `0x1400393cf`
- `KERNEL32!GetLastError` at `0x140039427`
- `KERNEL32!GetLastError` at `0x14003929d`
- `KERNEL32!GetLastError` at `0x1400393cf`
- `KERNEL32!GetLastError` at `0x140039427`
- `KERNEL32!CloseHandle` at `0x1400393a7`
- `KERNEL32!CloseHandle` at `0x1400394d4`
- `KERNEL32!CloseHandle` at `0x1400393a7`
- `KERNEL32!CloseHandle` at `0x1400394d4`
- `KERNEL32!DeleteFileW` at `0x1400393ff`
- `KERNEL32!DeleteFileW` at `0x1400393ff`

## pseudocode

```c
__int64 __fastcall CommitQueueEntry(struct _JOB_QUEUE *a1, int a2)
{
  void *v4; // rcx
  unsigned int v5; // r15d
  char *v6; // rax
  char *v7; // r14
  _WORD *v9; // r9
  _WORD *v10; // r10
  __int64 v11; // r11
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // esi
  _WORD *v16; // rcx
  __int64 v17; // r9
  CMapDeviceId *v18; // rcx
  __int64 v19; // rdx
  _WORD *v20; // rax
  _WORD *v21; // rdx
  _WORD *v22; // rcx
  void *v23; // rcx
  DWORD LengthSid; // eax
  __int64 v25; // rbx
  CMapDeviceId *v26; // rcx
  __int64 v27; // rdx
  void *File; // rax
  __int64 v29; // rbx
  int v30; // eax
  char LastError; // al
  int v32; // edx
  int v33; // r8d
  CMapDeviceId *v34; // rcx
  int v35; // edx
  unsigned __int64 v36; // [rsp+70h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  v4 = (void *)*((_QWORD *)a1 + 51);
  if ( v4 && !IsValidSid(v4) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        116,
        &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        *((unsigned int *)a1 + 8));
    }
    return 0;
  }
  v5 = CalcJobQueuePersistentSize(a1) + 1656;
  v6 = (char *)pMemAlloc(v5);
  v7 = v6;
  if ( !v6 )
    return 0;
  memset_0(v6, 0, v5);
  v9 = (_WORD *)((char *)a1 + 1176);
  v36 = 1656;
  v10 = v7 + 1136;
  *(_DWORD *)v7 = 1656;
  v11 = 2147483646;
  v12 = 256;
  *((_QWORD *)v7 + 1) = *((_QWORD *)a1 + 2);
  v13 = 2147483646;
  v14 = 256;
  *((_QWORD *)v7 + 2) = *((_QWORD *)a1 + 3);
  v15 = 1;
  *((_QWORD *)v7 + 48) = *((_QWORD *)a1 + 52);
  *((_QWORD *)v7 + 49) = *((_QWORD *)a1 + 53);
  *((_DWORD *)v7 + 6) = *((_DWORD *)a1 + 9);
  *((_DWORD *)v7 + 10) = *((_DWORD *)a1 + 461);
  *((_DWORD *)v7 + 412) = *((_DWORD *)a1 + 422);
  do
  {
    if ( !v13 )
      break;
    if ( !*v9 )
      break;
    *v10++ = *v9++;
    --v13;
    --v14;
  }
  while ( v14 );
  v16 = v10 - 1;
  v17 = v14 == 0 ? 0x8007007A : 0;
  if ( v14 )
    v16 = v10;
  *v16 = 0;
  if ( v14 )
  {
    v20 = (_WORD *)((char *)a1 + 648);
    v21 = v7 + 556;
    do
    {
      if ( !v11 )
        break;
      if ( !*v20 )
        break;
      *v21++ = *v20++;
      --v11;
      --v12;
    }
    while ( v12 );
    v22 = v21 - 1;
    v17 = v12 == 0 ? 0x8007007A : 0;
    if ( v12 )
      v22 = v21;
    *v22 = 0;
    if ( !v12 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_25;
      }
      v19 = 118;
      goto LABEL_24;
    }
    *((_DWORD *)v7 + 11) = *((_DWORD *)a1 + 16);
    *((_DWORD *)v7 + 48) = *((_DWORD *)a1 + 58);
    *((_DWORD *)v7 + 85) = *((_DWORD *)a1 + 95);
    *((_DWORD *)v7 + 84) = *((_DWORD *)a1 + 94);
    *((_DWORD *)v7 + 86) = *((_DWORD *)a1 + 97);
    if ( *((_DWORD *)a1 + 9) == 2 )
      *((_QWORD *)v7 + 68) = *(_QWORD *)(*((_QWORD *)a1 + 73) + 16LL);
    *((_DWORD *)v7 + 138) = *((_DWORD *)a1 + 148);
    *((_QWORD *)v7 + 140) = *((_QWORD *)a1 + 145);
    *((_QWORD *)v7 + 141) = *((_QWORD *)a1 + 146);
    v23 = (void *)*((_QWORD *)a1 + 51);
    if ( v23 )
    {
      LengthSid = GetLengthSid(v23);
      *((_QWORD *)v7 + 47) = 1656;
      v25 = LengthSid;
      memcpy_0(v7 + 1656, *((const void **)a1 + 51), LengthSid);
      v36 = v25 + 1656;
    }
    StoreString(*((unsigned __int16 **)a1 + 55), v5);
    *((_OWORD *)v7 + 69) = 0;
    StoreString(*((unsigned __int16 **)a1 + 7), v5);
    if ( *((_DWORD *)a1 + 9) == 32 || *((_DWORD *)a1 + 9) == 8 )
      StoreString(*((unsigned __int16 **)a1 + 9), v5);
    if ( !(unsigned int)JobParamsExSerialize(
                          (struct _JOB_QUEUE *)((char *)a1 + 80),
                          (struct _FAX_JOB_PARAM_EXW *)(v7 + 56),
                          (unsigned __int8 *)v7,
                          &v36,
                          v5) )
    {
      v15 = 122;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_105;
      }
      v27 = 119;
      goto LABEL_49;
    }
    if ( !(unsigned int)CoverPageExSerialize(
                          (struct _JOB_QUEUE *)((char *)a1 + 176),
                          (struct _FAX_COVERPAGE_INFO_EXW *)(v7 + 152),
                          (unsigned __int8 *)v7,
                          &v36,
                          v5) )
    {
      v15 = 122;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_105;
      }
      v27 = 120;
      goto LABEL_49;
    }
    if ( !(unsigned int)PersonalProfileSerialize(
                          (struct _JOB_QUEUE *)((char *)a1 + 240),
                          (struct _FAX_PERSONAL_PROFILEW *)(v7 + 200),
                          (unsigned __int8 *)v7,
                          &v36,
                          v5) )
    {
      v15 = 122;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_105;
      }
      v27 = 121;
      goto LABEL_49;
    }
    StoreString(*((unsigned __int16 **)a1 + 50), v5);
    if ( !(unsigned int)PersonalProfileSerialize(
                          (struct _JOB_QUEUE *)((char *)a1 + 448),
                          (struct _FAX_PERSONAL_PROFILEW *)(v7 + 408),
                          (unsigned __int8 *)v7,
                          &v36,
                          v5) )
    {
      v15 = 122;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_105;
      }
      v27 = 122;
LABEL_49:
      WPP_SF_d(*((_QWORD *)v26 + 2), v27, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, *((unsigned int *)a1 + 8));
      goto LABEL_105;
    }
    if ( *((_DWORD *)a1 + 9) == 8 )
    {
      v15 = SerializeRoutingInfo(a1, (struct _JOB_QUEUE_FILE *)v7, &v36, v5);
      if ( !v15 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          GetLastError();
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
        }
        goto LABEL_105;
      }
    }
    File = (void *)InternalSafeCreateFile(*((LPCWSTR *)a1 + 7), 0x40000000u, 0, 2u, -2147483520);
    v29 = (__int64)File;
    if ( File == (void *)-1LL )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          124,
          (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
          *((_DWORD *)a1 + 8),
          *((_QWORD *)a1 + 7));
      }
      v15 = 0;
      goto LABEL_105;
    }
    v30 = CommitHashedQueueEntry(File, v7, v5);
    if ( !v30 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          129,
          (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
          *((_DWORD *)a1 + 8),
          *((_QWORD *)a1 + 7));
      }
      goto LABEL_104;
    }
    if ( a2 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_lSl(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          125,
          (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
          *((_DWORD *)a1 + 8),
          *((_QWORD *)a1 + 7),
          v30);
      }
      if ( !CloseHandle((HANDLE)v29)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_SDl(*((_QWORD *)WPP_GLOBAL_Control + 2), v32, v33, *((_QWORD *)v7 + 4), v29, LastError);
      }
      v29 = -1;
      if ( !DeleteFileW(*((LPCWSTR *)a1 + 7))
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LOBYTE(v30) = GetLastError();
        v34 = WPP_GLOBAL_Control;
        v35 = 127;
LABEL_97:
        WPP_SF_lSl(
          *((_QWORD *)v34 + 2),
          v35,
          (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
          *((_DWORD *)a1 + 8),
          *((_QWORD *)a1 + 7),
          v30);
      }
    }
    else
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v35 = 128;
        goto LABEL_97;
      }
    }
    v15 = 0;
    if ( v29 == -1 )
      goto LABEL_105;
LABEL_104:
    CloseHandle((HANDLE)v29);
    goto LABEL_105;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_25;
  }
  v19 = 117;
LABEL_24:
  WPP_SF_d(*((_QWORD *)v18 + 2), v19, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v17);
LABEL_25:
  v15 = 0;
LABEL_105:
  pMemFree(v7);
  return v15;
}

```

## disassembly

```asm
0x140038d44  mov     [rsp+arg_8], rbx
0x140038d49  mov     [rsp+arg_10], rsi
0x140038d4e  push    rdi
0x140038d4f  push    r12
0x140038d51  push    r13
0x140038d53  push    r14
0x140038d55  push    r15
0x140038d57  sub     rsp, 40h
0x140038d5b  mov     r13d, edx
0x140038d5e  mov     rdi, rcx
0x140038d61  mov     rcx, cs:WPP_GLOBAL_Control
0x140038d68  lea     rbx, WPP_GLOBAL_Control
0x140038d6f  mov     r12b, 4
0x140038d72  cmp     rcx, rbx
0x140038d75  jz      short loc_140038D98
0x140038d77  test    [rcx+1Ch], r12b
0x140038d7b  jz      short loc_140038D98
0x140038d7d  cmp     byte ptr [rcx+19h], 5
0x140038d81  jb      short loc_140038D98
0x140038d83  mov     rcx, [rcx+10h]
0x140038d87  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140038d8e  mov     edx, 73h ; 's'
0x140038d93  call    WPP_SF_
0x140038d98  mov     rcx, [rdi+198h]; pSid
0x140038d9f  test    rcx, rcx
0x140038da2  jz      short loc_140038DE5
0x140038da4  call    cs:__imp_IsValidSid
0x140038dab  nop     dword ptr [rax+rax+00h]
0x140038db0  test    eax, eax
0x140038db2  jnz     short loc_140038DE5
0x140038db4  mov     rcx, cs:WPP_GLOBAL_Control
0x140038dbb  cmp     rcx, rbx
0x140038dbe  jz      short loc_140038E07
0x140038dc0  test    [rcx+1Ch], r12b
0x140038dc4  jz      short loc_140038E07
0x140038dc6  cmp     byte ptr [rcx+19h], 2
0x140038dca  jb      short loc_140038E07
0x140038dcc  mov     r9d, [rdi+20h]
0x140038dd0  lea     edx, [rax+74h]
0x140038dd3  mov     rcx, [rcx+10h]
0x140038dd7  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140038dde  call    WPP_SF_d
0x140038de3  jmp     short loc_140038E07
0x140038de5  mov     rcx, rdi; struct _JOB_QUEUE *
0x140038de8  call    ?CalcJobQueuePersistentSize@@YAKQEAU_JOB_QUEUE@@@Z; CalcJobQueuePersistentSize(_JOB_QUEUE * const)
0x140038ded  lea     r15d, [rax+678h]
0x140038df4  mov     ecx, r15d; dwBytes
0x140038df7  mov     ebx, r15d
0x140038dfa  call    pMemAlloc
0x140038dff  mov     r14, rax
0x140038e02  test    rax, rax
0x140038e05  jnz     short loc_140038E0E
0x140038e07  xor     eax, eax
0x140038e09  jmp     loc_1400394EA
0x140038e0e  mov     r8, rbx; Size
0x140038e11  xor     edx, edx; Val
0x140038e13  mov     rcx, r14; void *
0x140038e16  call    memset_0
0x140038e1b  mov     eax, 678h
0x140038e20  lea     r9, [rdi+498h]
0x140038e27  mov     [rsp+68h+arg_0], rax
0x140038e2c  lea     r10, [r14+470h]
0x140038e33  mov     [r14], eax
0x140038e36  mov     r11d, 7FFFFFFEh
0x140038e3c  mov     rax, [rdi+10h]
0x140038e40  mov     r8d, 100h
0x140038e46  mov     [r14+8], rax
0x140038e4a  mov     ecx, r11d
0x140038e4d  mov     rax, [rdi+18h]
0x140038e51  mov     edx, r8d
0x140038e54  mov     [r14+10h], rax
0x140038e58  mov     esi, 1
0x140038e5d  mov     rax, [rdi+1A0h]
0x140038e64  xor     ebx, ebx
0x140038e66  mov     [r14+180h], rax
0x140038e6d  mov     rax, [rdi+1A8h]
0x140038e74  mov     [r14+188h], rax
0x140038e7b  mov     eax, [rdi+24h]
0x140038e7e  mov     [r14+18h], eax
0x140038e82  mov     eax, [rdi+734h]
0x140038e88  mov     [r14+28h], eax
0x140038e8c  mov     eax, [rdi+698h]
0x140038e92  mov     [r14+670h], eax
0x140038e99  test    rcx, rcx
0x140038e9c  jz      short loc_140038EBB
0x140038e9e  movzx   eax, word ptr [r9]
0x140038ea2  test    ax, ax
0x140038ea5  jz      short loc_140038EBB
0x140038ea7  mov     [r10], ax
0x140038eab  add     r9, 2
0x140038eaf  add     r10, 2
0x140038eb3  sub     rcx, rsi
0x140038eb6  sub     rdx, rsi
0x140038eb9  jnz     short loc_140038E99
0x140038ebb  mov     rax, rdx
0x140038ebe  lea     rcx, [r10-2]
0x140038ec2  neg     rax
0x140038ec5  sbb     r9d, r9d
0x140038ec8  not     r9d
0x140038ecb  and     r9d, 8007007Ah
0x140038ed2  test    rdx, rdx
0x140038ed5  cmovnz  rcx, r10
0x140038ed9  mov     [rcx], bx
0x140038edc  jnz     short loc_140038F19
0x140038ede  mov     rcx, cs:WPP_GLOBAL_Control
0x140038ee5  lea     r15, WPP_GLOBAL_Control
0x140038eec  cmp     rcx, r15
0x140038eef  jz      short loc_140038F12
0x140038ef1  test    [rcx+1Ch], r12b
0x140038ef5  jz      short loc_140038F12
0x140038ef7  cmp     byte ptr [rcx+19h], 2
0x140038efb  jb      short loc_140038F12
0x140038efd  mov     edx, 75h ; 'u'
0x140038f02  mov     rcx, [rcx+10h]
0x140038f06  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140038f0d  call    WPP_SF_d
0x140038f12  mov     esi, ebx
0x140038f14  jmp     loc_1400394E0
0x140038f19  lea     rax, [rdi+288h]
0x140038f20  lea     rdx, [r14+22Ch]
0x140038f27  test    r11, r11
0x140038f2a  jz      short loc_140038F47
0x140038f2c  movzx   ecx, word ptr [rax]
0x140038f2f  test    cx, cx
0x140038f32  jz      short loc_140038F47
0x140038f34  mov     [rdx], cx
0x140038f37  add     rax, 2
0x140038f3b  add     rdx, 2
0x140038f3f  sub     r11, rsi
0x140038f42  sub     r8, rsi
0x140038f45  jnz     short loc_140038F27
0x140038f47  mov     rax, r8
0x140038f4a  lea     rcx, [rdx-2]
0x140038f4e  neg     rax
0x140038f51  sbb     r9d, r9d
0x140038f54  not     r9d
0x140038f57  and     r9d, 8007007Ah
0x140038f5e  test    r8, r8
0x140038f61  cmovnz  rcx, rdx
0x140038f65  mov     [rcx], bx
0x140038f68  jnz     short loc_140038F93
0x140038f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140038f71  lea     r15, WPP_GLOBAL_Control
0x140038f78  cmp     rcx, r15
0x140038f7b  jz      short loc_140038F12
0x140038f7d  test    [rcx+1Ch], r12b
0x140038f81  jz      short loc_140038F12
0x140038f83  cmp     byte ptr [rcx+19h], 2
0x140038f87  jb      short loc_140038F12
0x140038f89  mov     edx, 76h ; 'v'
0x140038f8e  jmp     loc_140038F02
0x140038f93  mov     eax, [rdi+40h]
0x140038f96  mov     [r14+2Ch], eax
0x140038f9a  mov     eax, [rdi+0E8h]
0x140038fa0  mov     [r14+0C0h], eax
0x140038fa7  mov     eax, [rdi+17Ch]
0x140038fad  mov     [r14+154h], eax
0x140038fb4  mov     eax, [rdi+178h]
0x140038fba  mov     [r14+150h], eax
0x140038fc1  mov     eax, [rdi+184h]
0x140038fc7  mov     [r14+158h], eax
0x140038fce  cmp     dword ptr [rdi+24h], 2
0x140038fd2  jnz     short loc_140038FE6
0x140038fd4  mov     rax, [rdi+248h]
0x140038fdb  mov     rcx, [rax+10h]
0x140038fdf  mov     [r14+220h], rcx
0x140038fe6  mov     eax, [rdi+250h]
0x140038fec  mov     [r14+228h], eax
0x140038ff3  mov     rax, [rdi+488h]
0x140038ffa  mov     [r14+460h], rax
0x140039001  mov     rax, [rdi+490h]
0x140039008  mov     [r14+468h], rax
0x14003900f  mov     rcx, [rdi+198h]; pSid
0x140039016  test    rcx, rcx
0x140039019  jz      short loc_140039056
0x14003901b  call    cs:__imp_GetLengthSid
0x140039022  nop     dword ptr [rax+rax+00h]
0x140039027  mov     qword ptr [r14+178h], 678h
0x140039032  lea     rcx, [r14+678h]; void *
0x140039039  mov     rdx, [rdi+198h]; Src
0x140039040  mov     r8d, eax; Size
0x140039043  mov     ebx, eax
0x140039045  call    memcpy_0
0x14003904a  lea     rax, [rbx+678h]
0x140039051  mov     [rsp+68h+arg_0], rax
0x140039056  mov     rcx, [rdi+1B8h]; unsigned __int16 *
0x14003905d  lea     rdx, [r14+190h]
0x140039064  lea     r9, [rsp+68h+arg_0]
0x140039069  mov     [rsp+68h+var_48], r15d; int
0x14003906e  mov     r8, r14
0x140039071  call    StoreString
0x140039076  xorps   xmm0, xmm0
0x140039079  mov     [rsp+68h+var_48], r15d; int
0x14003907e  movups  xmmword ptr [r14+450h], xmm0
0x140039086  mov     rcx, [rdi+38h]; unsigned __int16 *
0x14003908a  lea     r9, [rsp+68h+arg_0]
0x14003908f  mov     r8, r14
0x140039092  lea     rdx, [r14+20h]
0x140039096  call    StoreString
0x14003909b  cmp     dword ptr [rdi+24h], 20h ; ' '
0x14003909f  jz      short loc_1400390A7
0x1400390a1  cmp     dword ptr [rdi+24h], 8
0x1400390a5  jnz     short loc_1400390C1
0x1400390a7  mov     rcx, [rdi+48h]; unsigned __int16 *
0x1400390ab  lea     rdx, [r14+30h]
0x1400390af  lea     r9, [rsp+68h+arg_0]
0x1400390b4  mov     [rsp+68h+var_48], r15d; int
0x1400390b9  mov     r8, r14
0x1400390bc  call    StoreString
0x1400390c1  lea     rdx, [r14+38h]; struct _FAX_JOB_PARAM_EXW *
0x1400390c5  mov     [rsp+68h+var_48], r15d; unsigned int
0x1400390ca  lea     rcx, [rdi+50h]; struct _FAX_JOB_PARAM_EXW *
0x1400390ce  mov     r8, r14; unsigned __int8 *
0x1400390d1  lea     r9, [rsp+68h+arg_0]; unsigned __int64 *
0x1400390d6  call    ?JobParamsExSerialize@@YAHPEBU_FAX_JOB_PARAM_EXW@@PEAU1@PEAEPEA_KK@Z; JobParamsExSerialize(_FAX_JOB_PARAM_EXW const *,_FAX_JOB_PARAM_EXW *,uchar *,unsigned __int64 *,ulong)
0x1400390db  test    eax, eax
0x1400390dd  jnz     short loc_140039129
0x1400390df  lea     esi, [rax+7Ah]
0x1400390e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400390e9  lea     r15, WPP_GLOBAL_Control
0x1400390f0  cmp     rcx, r15
0x1400390f3  jz      loc_1400394E0
0x1400390f9  test    [rcx+1Ch], r12b
0x1400390fd  jz      loc_1400394E0
0x140039103  cmp     byte ptr [rcx+19h], 2
0x140039107  jb      loc_1400394E0
0x14003910d  lea     edx, [rax+77h]
0x140039110  mov     r9d, [rdi+20h]
0x140039114  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003911b  mov     rcx, [rcx+10h]
0x14003911f  call    WPP_SF_d
0x140039124  jmp     loc_1400394E0
0x140039129  lea     rdx, [r14+98h]; struct _FAX_COVERPAGE_INFO_EXW *
0x140039130  mov     [rsp+68h+var_48], r15d; unsigned int
0x140039135  lea     rcx, [rdi+0B0h]; struct _FAX_COVERPAGE_INFO_EXW *
0x14003913c  mov     r8, r14; unsigned __int8 *
0x14003913f  lea     r9, [rsp+68h+arg_0]; unsigned __int64 *
0x140039144  call    ?CoverPageExSerialize@@YAHPEBU_FAX_COVERPAGE_INFO_EXW@@PEAU1@PEAEPEA_KK@Z; CoverPageExSerialize(_FAX_COVERPAGE_INFO_EXW const *,_FAX_COVERPAGE_INFO_EXW *,uchar *,unsigned __int64 *,ulong)
0x140039149  test    eax, eax
0x14003914b  jnz     short loc_140039180
0x14003914d  lea     esi, [rax+7Ah]
0x140039150  mov     rcx, cs:WPP_GLOBAL_Control
0x140039157  lea     r15, WPP_GLOBAL_Control
0x14003915e  cmp     rcx, r15
0x140039161  jz      loc_1400394E0
0x140039167  test    [rcx+1Ch], r12b
0x14003916b  jz      loc_1400394E0
0x140039171  cmp     byte ptr [rcx+19h], 2
0x140039175  jb      loc_1400394E0
0x14003917b  lea     edx, [rax+78h]
0x14003917e  jmp     short loc_140039110
0x140039180  lea     rdx, [r14+0C8h]; struct _FAX_PERSONAL_PROFILEW *
0x140039187  mov     [rsp+68h+var_48], r15d; unsigned int
0x14003918c  lea     rcx, [rdi+0F0h]; struct _FAX_PERSONAL_PROFILEW *
0x140039193  mov     r8, r14; unsigned __int8 *
0x140039196  lea     r9, [rsp+68h+arg_0]; unsigned __int64 *
0x14003919b  call    ?PersonalProfileSerialize@@YAHPEBU_FAX_PERSONAL_PROFILEW@@PEAU1@PEAEPEA_KK@Z; PersonalProfileSerialize(_FAX_PERSONAL_PROFILEW const *,_FAX_PERSONAL_PROFILEW *,uchar *,unsigned __int64 *,ulong)
0x1400391a0  test    eax, eax
0x1400391a2  jnz     short loc_1400391DA
0x1400391a4  lea     esi, [rax+7Ah]
0x1400391a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400391ae  lea     r15, WPP_GLOBAL_Control
0x1400391b5  cmp     rcx, r15
0x1400391b8  jz      loc_1400394E0
0x1400391be  test    [rcx+1Ch], r12b
0x1400391c2  jz      loc_1400394E0
0x1400391c8  cmp     byte ptr [rcx+19h], 2
0x1400391cc  jb      loc_1400394E0
0x1400391d2  lea     edx, [rax+79h]
0x1400391d5  jmp     loc_140039110
0x1400391da  mov     rcx, [rdi+190h]; unsigned __int16 *
0x1400391e1  lea     rdx, [r14+170h]
0x1400391e8  lea     r9, [rsp+68h+arg_0]
0x1400391ed  mov     [rsp+68h+var_48], r15d; int
0x1400391f2  mov     r8, r14
0x1400391f5  call    StoreString
0x1400391fa  lea     rdx, [r14+198h]; struct _FAX_PERSONAL_PROFILEW *
0x140039201  mov     [rsp+68h+var_48], r15d; unsigned int
0x140039206  lea     rcx, [rdi+1C0h]; struct _FAX_PERSONAL_PROFILEW *
0x14003920d  mov     r8, r14; unsigned __int8 *
0x140039210  lea     r9, [rsp+68h+arg_0]; unsigned __int64 *
0x140039215  call    ?PersonalProfileSerialize@@YAHPEBU_FAX_PERSONAL_PROFILEW@@PEAU1@PEAEPEA_KK@Z; PersonalProfileSerialize(_FAX_PERSONAL_PROFILEW const *,_FAX_PERSONAL_PROFILEW *,uchar *,unsigned __int64 *,ulong)
0x14003921a  test    eax, eax
0x14003921c  jnz     short loc_140039253
0x14003921e  lea     esi, [rax+7Ah]
0x140039221  mov     rcx, cs:WPP_GLOBAL_Control
0x140039228  lea     r15, WPP_GLOBAL_Control
0x14003922f  cmp     rcx, r15
0x140039232  jz      loc_1400394E0
0x140039238  test    [rcx+1Ch], r12b
0x14003923c  jz      loc_1400394E0
0x140039242  cmp     byte ptr [rcx+19h], 2
0x140039246  jb      loc_1400394E0
0x14003924c  mov     edx, esi
0x14003924e  jmp     loc_140039110
0x140039253  cmp     dword ptr [rdi+24h], 8
0x140039257  jnz     short loc_1400392D0
0x140039259  mov     r9d, r15d; unsigned int
0x14003925c  lea     r8, [rsp+68h+arg_0]; unsigned __int64 *
0x140039261  mov     rdx, r14; struct _JOB_QUEUE_FILE *
  ... truncated ...
```
