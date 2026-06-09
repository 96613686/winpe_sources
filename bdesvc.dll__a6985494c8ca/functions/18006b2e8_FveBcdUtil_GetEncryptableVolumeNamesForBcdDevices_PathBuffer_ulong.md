# FveBcdUtil::GetEncryptableVolumeNamesForBcdDevices(PathBuffer * *,ulong *)

- ea: `0x18006b2e8`
- end: `0x18006b9f2`
- name: `?GetEncryptableVolumeNamesForBcdDevices@FveBcdUtil@@SAJPEAPEAVPathBuffer@@PEAK@Z`
- size: `1802`
- prototype: `__int64 __fastcall(struct PathBuffer **, unsigned int *)`
- caller_count: `3`
- callee_count: `20`
- tags: `installer_update`

## callers

- `0x18002f734`
- `0x18004d7f0`
- `0x18004e620`

## callees

- `0x180001fe8`
- `0x1800020e0`
- `0x180009f30`
- `0x180009f60`
- `0x18001b7f0`
- `0x18001b890`
- `0x1800240e8`
- `0x180025ed4`
- `0x18002f28c`
- `0x180034070`
- `0x1800345ec`
- `0x180034d28`
- `0x1800352c1`
- `0x1800352e5`
- `0x1800352f1`
- `0x180035309`
- `0x180048c8c`
- `0x18006aa50`
- `0x18006b2e8`
- `0x18006b9f8`

## import_xrefs

- `bcd!BcdOpenSystemStore` at `0x18006b383`
- `bcd!BcdOpenSystemStore` at `0x18006b383`
- `bcd!BcdCloseStore` at `0x18006b8fc`
- `bcd!BcdCloseStore` at `0x18006b8fc`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::GetEncryptableVolumeNamesForBcdDevices(struct PathBuffer **a1, unsigned int *a2)
{
  int v2; // r13d
  int v3; // eax
  int v4; // eax
  unsigned int v5; // ebx
  PVOID *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  PathBuffer *v9; // rdi
  unsigned __int64 v10; // rbx
  __int64 v11; // rax
  bool v12; // cf
  unsigned __int64 v13; // rax
  unsigned __int64 *v14; // rax
  int UniqueBcdDevicePaths; // eax
  __int64 v16; // r12
  __int64 v17; // rax
  unsigned __int64 v18; // rax
  _QWORD *v19; // rax
  PathBuffer *v20; // rsi
  __int64 v21; // r14
  __int64 v22; // r15
  int v23; // eax
  int v24; // eax
  int IsVolumeEncryptable_0; // eax
  int VolumeNameW_0; // eax
  int v27; // eax
  PVOID *v28; // rcx
  __int64 v29; // rdx
  PVOID *v30; // rcx
  PVOID *v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  unsigned int v35[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  int v37; // [rsp+40h] [rbp-C0h] BYREF
  void *v38; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  struct PathBuffer **v40; // [rsp+58h] [rbp-A8h]
  PSRWLOCK v41[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v42[264]; // [rsp+80h] [rbp-80h] BYREF

  v39 = (__int64)a2;
  v40 = a1;
  v36 = -1;
  v38 = 0;
  v37 = 0;
  memset_0(v42, 0, 0x208u);
  v2 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids);
  v3 = BcdOpenSystemStore(&v38);
  v4 = FromNtStatus(v3);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_100;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
        (unsigned int)v4);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 0x40) == 0 )
      goto LABEL_100;
    v7 = 48;
    v8 = v5;
    goto LABEL_98;
  }
  v9 = 0;
  v10 = 10;
  for ( v35[0] = 10; ; v10 = v35[0] )
  {
    if ( v9 )
      PathBuffer::`vector deleting destructor'(v9);
    v11 = 8 * v10;
    if ( !is_mul_ok(v10, 8u) )
      v11 = -1;
    v12 = __CFADD__(v11, 8);
    v13 = v11 + 8;
    if ( v12 )
      v13 = -1;
    v14 = (unsigned __int64 *)operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v14
      || (v9 = (PathBuffer *)(v14 + 1),
          *v14 = v10,
          `vector constructor iterator'(v14 + 1, 8u, v10, (void *(*)(void *))PathBuffer::PathBuffer),
          !v9) )
    {
      v5 = -2147024882;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_100;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
          2147942414LL);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 0x40) == 0 )
        goto LABEL_100;
      v7 = 50;
      v8 = 2147942414LL;
LABEL_98:
      WPP_SF_d(v6[2], v7, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v8);
      goto LABEL_99;
    }
    UniqueBcdDevicePaths = FveBcdUtil::GetUniqueBcdDevicePaths(v38, v9, v35);
    v5 = UniqueBcdDevicePaths;
    if ( UniqueBcdDevicePaths != -2147024774 )
      break;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, 2147942522LL);
  }
  if ( UniqueBcdDevicePaths < 0 )
  {
    v31 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
          (unsigned int)UniqueBcdDevicePaths);
        v31 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 0x40) != 0 )
        WPP_SF_d(v31[2], 53, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v5);
    }
    goto LABEL_91;
  }
  v16 = v35[0];
  v17 = 8LL * v35[0];
  if ( !is_mul_ok(v35[0], 8u) )
    v17 = -1;
  v12 = __CFADD__(v17, 8);
  v18 = v17 + 8;
  if ( v12 )
    v18 = -1;
  v19 = operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v19
    || (v20 = (PathBuffer *)(v19 + 1),
        *v19 = v16,
        `vector constructor iterator'(v19 + 1, 8u, (unsigned int)v16, (void *(*)(void *))PathBuffer::PathBuffer),
        !v20) )
  {
    v5 = -2147024882;
    v30 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
          2147942414LL);
        v30 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 0x40) != 0 )
        WPP_SF_d(v30[2], 55, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, 2147942414LL);
    }
    goto LABEL_91;
  }
  v21 = 0;
  v22 = 0;
  if ( !(_DWORD)v16 )
  {
LABEL_57:
    *v40 = v20;
    *(_DWORD *)v39 = v21;
    goto LABEL_91;
  }
  while ( 2 )
  {
    if ( v36 != -1 )
    {
      FveCloseVolume_0(v36);
      v36 = -1;
    }
    v23 = StringCchPrintfW(v42, 0x104u, L"\\\\?\\GLOBALROOT%s", *((_QWORD *)v9 + v22));
    v5 = v23;
    if ( v23 < 0 )
    {
      v28 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
            (unsigned int)v23);
          v28 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 0x40) != 0 )
        {
          v29 = 57;
          goto LABEL_76;
        }
      }
      goto LABEL_77;
    }
    v24 = FveOpenVolumeW_0(v42, 0, &v36);
    v5 = v24;
    if ( v24 == -2144272310 || v24 == -2144272363 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
          (unsigned int)v24);
LABEL_55:
      v5 = 0;
LABEL_56:
      v22 = (unsigned int)(v22 + 1);
      if ( (unsigned int)v22 >= (unsigned int)v16 )
        goto LABEL_57;
      continue;
    }
    break;
  }
  if ( v24 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
        (unsigned int)v24);
    if ( v2 >= 0 )
      v2 = v5;
    goto LABEL_55;
  }
  IsVolumeEncryptable_0 = FveIsVolumeEncryptable_0(v36);
  if ( IsVolumeEncryptable_0 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
        (unsigned int)IsVolumeEncryptable_0);
    goto LABEL_56;
  }
  v37 = 260;
  VolumeNameW_0 = FveGetVolumeNameW_0(v36, &v37, v42);
  v5 = VolumeNameW_0;
  if ( VolumeNameW_0 >= 0 )
  {
    v27 = PathBuffer::Initialize((PathBuffer *)((char *)v20 + 8 * v21), v42);
    v5 = v27;
    if ( v27 < 0 )
    {
      v28 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            63,
            &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
            (unsigned int)v27);
          v28 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 0x40) != 0 )
        {
          v29 = 64;
LABEL_76:
          WPP_SF_d(v28[2], v29, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v5);
          goto LABEL_77;
        }
      }
      goto LABEL_77;
    }
    v21 = (unsigned int)(v21 + 1);
    goto LABEL_56;
  }
  v28 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
        (unsigned int)VolumeNameW_0);
      v28 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 0x40) != 0 )
    {
      v29 = 62;
      goto LABEL_76;
    }
  }
LABEL_77:
  PathBuffer::`vector deleting destructor'(v20);
LABEL_91:
  PathBuffer::`vector deleting destructor'(v9);
LABEL_99:
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_100:
  if ( v36 != -1 )
  {
    FveCloseVolume_0(v36);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v36 = -1;
  }
  if ( v38 )
  {
    BcdCloseStore(v38);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 < 0 )
  {
    TelemetryProviderRegistrar::TelemetryProviderRegistrar(
      (TelemetryProviderRegistrar *)v41,
      &g_hBitLockerBcdUpdateProvider,
      &g_bitLockerBcdUpdateProviderInitLock,
      &g_bitLockerBcdUpdateProviderRefCount);
    if ( (unsigned int)dword_18009A468 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A468, 0x400000000000LL) )
    {
      v39 = 0x1000000;
      v35[0] = v2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (int)&dword_18009A468,
        (int)&byte_18008E437,
        v32,
        v33,
        (__int64)v35,
        (__int64)&v39);
    }
    TelemetryProviderRegistrar::~TelemetryProviderRegistrar(v41);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    WPP_SF_d(v6[2], 65, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18006b2e8  mov     [rsp-8+arg_10], rbx
0x18006b2ed  push    rbp
0x18006b2ee  push    rsi
0x18006b2ef  push    rdi
0x18006b2f0  push    r12
0x18006b2f2  push    r13
0x18006b2f4  push    r14
0x18006b2f6  push    r15
0x18006b2f8  lea     rbp, [rsp-1A0h]
0x18006b300  sub     rsp, 2A0h
0x18006b307  mov     rax, cs:__security_cookie
0x18006b30e  xor     rax, rsp
0x18006b311  mov     [rbp+1D0h+var_40], rax
0x18006b318  mov     [rsp+2D0h+var_280], rdx
0x18006b31d  or      r12, 0FFFFFFFFFFFFFFFFh
0x18006b321  mov     [rsp+2D0h+var_278], rcx
0x18006b326  xor     edx, edx; Val
0x18006b328  lea     rcx, [rbp+1D0h+var_250]; void *
0x18006b32c  mov     [rsp+2D0h+var_298], r12
0x18006b331  mov     r8d, 208h; Size
0x18006b337  mov     [rsp+2D0h+var_288], 0
0x18006b340  mov     [rsp+2D0h+var_290], 0
0x18006b348  call    memset_0
0x18006b34d  xor     r13d, r13d
0x18006b350  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b357  lea     r15, WPP_GLOBAL_Control
0x18006b35e  cmp     rcx, r15
0x18006b361  jz      short loc_18006B37E
0x18006b363  test    byte ptr [rcx+1Ch], 20h
0x18006b367  jz      short loc_18006B37E
0x18006b369  mov     rcx, [rcx+10h]
0x18006b36d  lea     edx, [r12+2Fh]
0x18006b372  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18006b379  call    WPP_SF_
0x18006b37e  lea     rcx, [rsp+2D0h+var_288]
0x18006b383  call    cs:__imp_BcdOpenSystemStore
0x18006b38a  nop     dword ptr [rax+rax+00h]
0x18006b38f  mov     ecx, eax; int
0x18006b391  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18006b396  mov     ebx, eax
0x18006b398  test    eax, eax
0x18006b39a  jns     short loc_18006B3F1
0x18006b39c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b3a3  cmp     rcx, r15
0x18006b3a6  jz      loc_18006B8D2
0x18006b3ac  test    byte ptr [rcx+1Ch], 2
0x18006b3b0  jz      short loc_18006B3D1
0x18006b3b2  mov     rcx, [rcx+10h]
0x18006b3b6  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18006b3bd  mov     edx, 2Fh ; '/'
0x18006b3c2  mov     r9d, eax
0x18006b3c5  call    WPP_SF_d
0x18006b3ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b3d1  cmp     rcx, r15
0x18006b3d4  jz      loc_18006B8D2
0x18006b3da  test    byte ptr [rcx+1Ch], 40h
0x18006b3de  jz      loc_18006B8D2
0x18006b3e4  mov     edx, 30h ; '0'
0x18006b3e9  mov     r9d, ebx
0x18006b3ec  jmp     loc_18006B8BB
0x18006b3f1  xor     edi, edi
0x18006b3f3  mov     ebx, 0Ah
0x18006b3f8  mov     [rsp+2D0h+var_2A0], ebx
0x18006b3fc  mov     r14d, 8007007Ah
0x18006b402  lea     esi, [rdi+8]
0x18006b405  test    rdi, rdi
0x18006b408  jz      short loc_18006B412
0x18006b40a  mov     rcx, rdi; this
0x18006b40d  call    ??_EPathBuffer@@QEAAPEAXI@Z; PathBuffer::`vector deleting destructor'(uint)
0x18006b412  mov     rax, rsi
0x18006b415  mul     rbx
0x18006b418  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006b41f  cmovb   rax, r12
0x18006b423  add     rax, rsi
0x18006b426  cmovb   rax, r12
0x18006b42a  mov     rcx, rax; unsigned __int64
0x18006b42d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006b432  test    rax, rax
0x18006b435  jz      loc_18006B870
0x18006b43b  lea     rdi, [rax+8]
0x18006b43f  mov     [rax], rbx
0x18006b442  mov     rcx, rdi; void *
0x18006b445  lea     r9, ??0PathBuffer@@QEAA@XZ; void *(*)(void *)
0x18006b44c  mov     r8, rbx; unsigned __int64
0x18006b44f  mov     rdx, rsi; unsigned __int64
0x18006b452  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18006b457  test    rdi, rdi
0x18006b45a  jz      loc_18006B870
0x18006b460  mov     rcx, [rsp+2D0h+var_288]; void *
0x18006b465  lea     r8, [rsp+2D0h+var_2A0]; unsigned int *
0x18006b46a  mov     rdx, rdi; struct PathBuffer *
0x18006b46d  call    ?GetUniqueBcdDevicePaths@FveBcdUtil@@CAJPEAXPEAVPathBuffer@@PEAK@Z; FveBcdUtil::GetUniqueBcdDevicePaths(void *,PathBuffer *,ulong *)
0x18006b472  mov     ebx, eax
0x18006b474  cmp     eax, r14d
0x18006b477  jnz     short loc_18006B4AC
0x18006b479  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b480  cmp     rcx, r15
0x18006b483  jz      short loc_18006B4A3
0x18006b485  test    [rcx+1Ch], sil
0x18006b489  jz      short loc_18006B4A3
0x18006b48b  mov     rcx, [rcx+10h]
0x18006b48f  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18006b496  mov     edx, 33h ; '3'
0x18006b49b  mov     r9d, r14d
0x18006b49e  call    WPP_SF_d
0x18006b4a3  mov     ebx, [rsp+2D0h+var_2A0]
0x18006b4a7  jmp     loc_18006B405
0x18006b4ac  test    ebx, ebx
0x18006b4ae  js      loc_18006B812
0x18006b4b4  mov     r12d, [rsp+2D0h+var_2A0]
0x18006b4b9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006b4c0  mov     rax, rsi
0x18006b4c3  mul     r12
0x18006b4c6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006b4cd  cmovb   rax, rcx
0x18006b4d1  add     rax, rsi
0x18006b4d4  cmovb   rax, rcx
0x18006b4d8  mov     rcx, rax; unsigned __int64
0x18006b4db  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006b4e0  test    rax, rax
0x18006b4e3  jz      loc_18006B7B1
0x18006b4e9  lea     rsi, [rax+8]
0x18006b4ed  mov     [rax], r12
0x18006b4f0  mov     rcx, rsi; void *
0x18006b4f3  lea     r9, ??0PathBuffer@@QEAA@XZ; void *(*)(void *)
0x18006b4fa  mov     r8d, r12d; unsigned __int64
0x18006b4fd  mov     edx, 8; unsigned __int64
0x18006b502  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18006b507  test    rsi, rsi
0x18006b50a  jz      loc_18006B7B1
0x18006b510  xor     r14d, r14d
0x18006b513  xor     r15d, r15d
0x18006b516  test    r12d, r12d
0x18006b519  jz      loc_18006B689
0x18006b51f  mov     rcx, [rsp+2D0h+var_298]
0x18006b524  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006b528  jz      short loc_18006B538
0x18006b52a  call    FveCloseVolume_0
0x18006b52f  mov     [rsp+2D0h+var_298], 0FFFFFFFFFFFFFFFFh
0x18006b538  mov     r9, [rdi+r15*8]
0x18006b53c  lea     r8, aGlobalrootS; "\\\\?\\GLOBALROOT%s"
0x18006b543  mov     edx, 104h; unsigned __int64
0x18006b548  lea     rcx, [rbp+1D0h+var_250]; unsigned __int16 *
0x18006b54c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006b551  mov     ebx, eax
0x18006b553  test    eax, eax
0x18006b555  js      loc_18006B74C
0x18006b55b  lea     r8, [rsp+2D0h+var_298]
0x18006b560  xor     edx, edx
0x18006b562  lea     rcx, [rbp+1D0h+var_250]
0x18006b566  call    FveOpenVolumeW_0
0x18006b56b  mov     ebx, eax
0x18006b56d  cmp     eax, 8031004Ah
0x18006b572  jz      loc_18006B64A
0x18006b578  cmp     eax, 80310015h
0x18006b57d  jz      loc_18006B64A
0x18006b583  test    eax, eax
0x18006b585  jns     short loc_18006B5C4
0x18006b587  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b58e  lea     rax, WPP_GLOBAL_Control
0x18006b595  cmp     rcx, rax
0x18006b598  jz      short loc_18006B5B8
0x18006b59a  test    byte ptr [rcx+1Ch], 4
0x18006b59e  jz      short loc_18006B5B8
0x18006b5a0  mov     rcx, [rcx+10h]
0x18006b5a4  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18006b5ab  mov     edx, 3Bh ; ';'
0x18006b5b0  mov     r9d, ebx
0x18006b5b3  call    WPP_SF_d
0x18006b5b8  test    r13d, r13d
0x18006b5bb  cmovns  r13d, ebx
0x18006b5bf  jmp     loc_18006B67B
0x18006b5c4  mov     rcx, [rsp+2D0h+var_298]
0x18006b5c9  call    FveIsVolumeEncryptable_0
0x18006b5ce  test    eax, eax
0x18006b5d0  jns     short loc_18006B60D
0x18006b5d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b5d9  lea     rdx, WPP_GLOBAL_Control
0x18006b5e0  cmp     rcx, rdx
0x18006b5e3  jz      loc_18006B67D
0x18006b5e9  test    byte ptr [rcx+1Ch], 8
0x18006b5ed  jz      loc_18006B67D
0x18006b5f3  mov     rcx, [rcx+10h]
0x18006b5f7  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18006b5fe  mov     edx, 3Ch ; '<'
0x18006b603  mov     r9d, eax
0x18006b606  call    WPP_SF_d
0x18006b60b  jmp     short loc_18006B67D
0x18006b60d  mov     rcx, [rsp+2D0h+var_298]
0x18006b612  lea     r8, [rbp+1D0h+var_250]
0x18006b616  lea     rdx, [rsp+2D0h+var_290]
0x18006b61b  mov     [rsp+2D0h+var_290], 104h
0x18006b623  call    FveGetVolumeNameW_0
0x18006b628  mov     ebx, eax
0x18006b62a  test    eax, eax
0x18006b62c  js      loc_18006B6FE
0x18006b632  lea     rcx, [rsi+r14*8]; this
0x18006b636  lea     rdx, [rbp+1D0h+var_250]; unsigned __int16 *
0x18006b63a  call    ?Initialize@PathBuffer@@QEAAJPEBG@Z; PathBuffer::Initialize(ushort const *)
0x18006b63f  mov     ebx, eax
0x18006b641  test    eax, eax
0x18006b643  js      short loc_18006B6A5
0x18006b645  inc     r14d
0x18006b648  jmp     short loc_18006B67D
0x18006b64a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b651  lea     rax, WPP_GLOBAL_Control
0x18006b658  cmp     rcx, rax
0x18006b65b  jz      short loc_18006B67B
0x18006b65d  test    byte ptr [rcx+1Ch], 8
0x18006b661  jz      short loc_18006B67B
0x18006b663  mov     rcx, [rcx+10h]
0x18006b667  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18006b66e  mov     edx, 3Ah ; ':'
0x18006b673  mov     r9d, ebx
0x18006b676  call    WPP_SF_d
0x18006b67b  xor     ebx, ebx
0x18006b67d  inc     r15d
0x18006b680  cmp     r15d, r12d
0x18006b683  jb      loc_18006B51F
0x18006b689  mov     rax, [rsp+2D0h+var_278]
0x18006b68e  lea     r15, WPP_GLOBAL_Control
0x18006b695  mov     [rax], rsi
0x18006b698  mov     rax, [rsp+2D0h+var_280]
0x18006b69d  mov     [rax], r14d
0x18006b6a0  jmp     loc_18006B80C
0x18006b6a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b6ac  lea     r15, WPP_GLOBAL_Control
0x18006b6b3  cmp     rcx, r15
0x18006b6b6  jz      loc_18006B7A7
0x18006b6bc  test    byte ptr [rcx+1Ch], 2
0x18006b6c0  jz      short loc_18006B6E1
0x18006b6c2  mov     rcx, [rcx+10h]
0x18006b6c6  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18006b6cd  mov     edx, 3Fh ; '?'
0x18006b6d2  mov     r9d, ebx
0x18006b6d5  call    WPP_SF_d
0x18006b6da  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b6e1  cmp     rcx, r15
0x18006b6e4  jz      loc_18006B7A7
0x18006b6ea  test    byte ptr [rcx+1Ch], 40h
0x18006b6ee  jz      loc_18006B7A7
0x18006b6f4  mov     edx, 40h ; '@'
0x18006b6f9  jmp     loc_18006B794
0x18006b6fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b705  lea     r15, WPP_GLOBAL_Control
0x18006b70c  cmp     rcx, r15
0x18006b70f  jz      loc_18006B7A7
0x18006b715  test    byte ptr [rcx+1Ch], 2
0x18006b719  jz      short loc_18006B73A
0x18006b71b  mov     rcx, [rcx+10h]
0x18006b71f  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18006b726  mov     edx, 3Dh ; '='
0x18006b72b  mov     r9d, ebx
0x18006b72e  call    WPP_SF_d
0x18006b733  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b73a  cmp     rcx, r15
0x18006b73d  jz      short loc_18006B7A7
0x18006b73f  test    byte ptr [rcx+1Ch], 40h
0x18006b743  jz      short loc_18006B7A7
0x18006b745  mov     edx, 3Eh ; '>'
0x18006b74a  jmp     short loc_18006B794
0x18006b74c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b753  lea     r15, WPP_GLOBAL_Control
0x18006b75a  cmp     rcx, r15
0x18006b75d  jz      short loc_18006B7A7
0x18006b75f  test    byte ptr [rcx+1Ch], 2
0x18006b763  jz      short loc_18006B784
0x18006b765  mov     rcx, [rcx+10h]
0x18006b769  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18006b770  mov     edx, 38h ; '8'
0x18006b775  mov     r9d, ebx
0x18006b778  call    WPP_SF_d
0x18006b77d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b784  cmp     rcx, r15
0x18006b787  jz      short loc_18006B7A7
0x18006b789  test    byte ptr [rcx+1Ch], 40h
0x18006b78d  jz      short loc_18006B7A7
0x18006b78f  mov     edx, 39h ; '9'
0x18006b794  mov     rcx, [rcx+10h]
0x18006b798  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18006b79f  mov     r9d, ebx
0x18006b7a2  call    WPP_SF_d
0x18006b7a7  mov     rcx, rsi; this
0x18006b7aa  call    ??_EPathBuffer@@QEAAPEAXI@Z; PathBuffer::`vector deleting destructor'(uint)
0x18006b7af  jmp     short loc_18006B80C
0x18006b7b1  mov     esi, 8007000Eh
0x18006b7b6  mov     ebx, esi
0x18006b7b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b7bf  cmp     rcx, r15
0x18006b7c2  jz      short loc_18006B80C
0x18006b7c4  test    byte ptr [rcx+1Ch], 2
0x18006b7c8  jz      short loc_18006B7E9
0x18006b7ca  mov     rcx, [rcx+10h]
0x18006b7ce  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18006b7d5  mov     edx, 36h ; '6'
0x18006b7da  mov     r9d, esi
0x18006b7dd  call    WPP_SF_d
0x18006b7e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b7e9  cmp     rcx, r15
0x18006b7ec  jz      short loc_18006B80C
  ... truncated ...
```
