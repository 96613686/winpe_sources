# __delayLoadHelper2

- ea: `0x180021030`
- end: `0x18002162e`
- name: `__delayLoadHelper2`
- size: `1534`
- prototype: ``
- caller_count: `38`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180044756`
- `0x180044913`
- `0x180044a88`
- `0x180044b13`
- `0x180044c0a`
- `0x180044c95`
- `0x180044e82`
- `0x180044f85`
- `0x180045046`
- `0x1800450f5`
- `0x1800451ec`
- `0x1800452f5`
- `0x180045392`
- `0x18004542f`
- `0x1800454ba`
- `0x180045557`
- `0x1800455e2`
- `0x180045691`
- `0x180045740`
- `0x180045849`
- `0x18004592e`
- `0x180045a7f`
- `0x180045b0a`
- `0x180045b95`
- `0x180045c56`
- `0x180045ce1`
- `0x180045dc6`
- `0x180045e75`
- `0x180045f00`
- `0x180045f8b`
- `0x180046016`
- `0x1800460a1`
- `0x18004612c`
- `0x1800461db`
- `0x180046266`
- `0x180046315`
- `0x1800464e4`
- `0x1800465ff`

## callees

- `0x180021030`
- `0x180021634`
- `0x18002db00`
- `0x18006ec88`
- `0x18006ed48`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800213d0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800213d0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021527`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021527`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021371`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021371`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002107f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021256`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002107f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021256`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002114d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021314`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002114d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021597`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800213ad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021502`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800215e4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800213ad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021502`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800215e4`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180021131`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800212ff`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180021131`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800212ff`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(int *a1, CHAR *a2)
{
  __int64 v4; // r8
  unsigned int v5; // r9d
  int *v6; // rdx
  unsigned int i; // r10d
  __int64 v8; // rcx
  SIZE_T v9; // r8
  char *v10; // rbx
  SIZE_T v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // rcx
  volatile signed __int64 *v14; // rbx
  __int64 v15; // r9
  char *v16; // r15
  int v17; // eax
  HMODULE Library; // r14
  __int64 v19; // r13
  __int64 v20; // rax
  __int64 v21; // rdx
  FARPROC ProcAddress; // rdi
  PfnDliHook v23; // r8
  __int64 v24; // r8
  unsigned int v25; // r9d
  int *v26; // rdx
  unsigned int j; // r10d
  __int64 v28; // rax
  SIZE_T v29; // r8
  char *v30; // rbx
  DWORD v31; // r14d
  SIZE_T v32; // rsi
  signed __int64 v34; // rbx
  bool v35; // sf
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // r8
  __int128 v48; // [rsp+20h] [rbp-58h] BYREF
  LPCSTR lpLibFileName[2]; // [rsp+30h] [rbp-48h]
  LPCSTR lpProcName[2]; // [rsp+40h] [rbp-38h]
  __int128 v51; // [rsp+50h] [rbp-28h]
  DWORD LastError; // [rsp+60h] [rbp-18h]
  __int128 *flOldProtect; // [rsp+B0h] [rbp+38h] BYREF

  LastError = 0;
  v48 = 0;
  *(_OWORD *)lpLibFileName = 0;
  *(_OWORD *)lpProcName = 0;
  v51 = 0;
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( ++DloadSectionLockCount == 1 )
  {
    if ( *(_DWORD *)&byte_180000040[(int)off_18000003C + 68] > 0xDu )
    {
      v4 = *(unsigned int *)&byte_180000040[(int)off_18000003C + 176];
      if ( (_DWORD)v4 )
      {
        v5 = *(_DWORD *)((char *)&word_18000000C + v4);
        v6 = (int *)((char *)&_ImageBase
                   + (int)off_18000003C
                   + *(unsigned __int16 *)((char *)&word_180000014 + (int)off_18000003C)
                   + 24);
        for ( i = 0; i < *(unsigned __int16 *)((char *)&word_180000006 + (int)off_18000003C); ++i )
        {
          v8 = (unsigned int)v6[3];
          if ( v5 >= (unsigned int)v8 )
          {
            v9 = (unsigned int)v6[2];
            if ( v5 < (int)v9 + (int)v8 )
            {
              v10 = (char *)&_ImageBase + v8;
              if ( !(HINSTANCE__ *)((char *)&_ImageBase + v8) )
                break;
              if ( DloadSectionCommitPermanent )
              {
                v11 = (unsigned int)v6[2];
              }
              else
              {
                v35 = v6[9] < 0;
                DloadSectionCommitPermanent = 1;
                if ( !v35 )
                  __fastfail(0x19u);
                v11 = v9;
                DloadMakePermanentImageCommit((char *)&_ImageBase + v8, v9);
              }
              if ( !VirtualProtect(v10, v11, 4u, &DloadSectionOldProtection) )
                __fastfail(0x19u);
              goto LABEL_13;
            }
          }
          v6 += 10;
        }
      }
    }
    DloadSectionOldProtection = 4;
  }
LABEL_13:
  ReleaseSRWLockExclusive(&DloadSrwLock);
  v14 = (volatile signed __int64 *)((char *)&_ImageBase.unused + (unsigned int)a1[2]);
  v15 = (unsigned int)a1[7];
  v16 = (char *)&_ImageBase + (unsigned int)a1[5];
  lpLibFileName[1] = (char *)&_ImageBase + (unsigned int)a1[1];
  v17 = *a1;
  LODWORD(flOldProtect) = v15;
  LODWORD(v48) = 72;
  *((_QWORD *)&v48 + 1) = a1;
  lpLibFileName[0] = a2;
  LODWORD(lpProcName[0]) = 0;
  lpProcName[1] = 0;
  v51 = 0u;
  LastError = 0;
  if ( (v17 & 1) == 0 )
  {
    flOldProtect = &v48;
    DloadReleaseSectionWriteAccess(v13, v12, 0);
    RaiseException(0xC06D0057, 0, 1u, (const ULONG_PTR *)&flOldProtect);
    return 0;
  }
  Library = (HMODULE)*v14;
  v19 = 8LL * (unsigned int)((&a2[-a1[3]] - (CHAR *)&_ImageBase) >> 3);
  v20 = v19 + (unsigned int)a1[4];
  LODWORD(lpProcName[0]) = *(_QWORD *)((char *)&_ImageBase.unused + v20) >= 0LL;
  v21 = *(unsigned int *)((char *)&_ImageBase.unused + v20);
  if ( LODWORD(lpProcName[0]) )
    lpProcName[1] = (char *)&_ImageBase.unused + v21 + 2;
  else
    LODWORD(lpProcName[1]) = (unsigned __int16)v21;
  ProcAddress = 0;
  v23 = _pfnDliNotifyHook2;
  if ( _pfnDliNotifyHook2 )
  {
    v36 = ((__int64 (__fastcall *)(_QWORD, __int128 *))_pfnDliNotifyHook2)(0, &v48);
    v23 = _pfnDliNotifyHook2;
    ProcAddress = (FARPROC)v36;
    if ( v36 )
      goto LABEL_22;
    v15 = (unsigned int)flOldProtect;
  }
  if ( !Library )
  {
    if ( !v23 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, __int128 *))v23)(1, &v48)) == 0 )
    {
      Library = LoadLibraryExA(lpLibFileName[1], 0, 0);
      if ( !Library )
      {
        LastError = GetLastError();
        if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, &v48)) == 0 )
        {
          flOldProtect = &v48;
          DloadReleaseSectionWriteAccess(v38, v37, v39);
          RaiseException(0xC06D007E, 0, 1u, (const ULONG_PTR *)&flOldProtect);
          return (FARPROC)*((_QWORD *)&v51 + 1);
        }
      }
    }
    v34 = _InterlockedCompareExchange64(v14, (signed __int64)Library, 0);
    if ( v34 )
    {
      if ( Library != (HMODULE)-1LL )
        FreeLibrary(Library);
      if ( Library != (HMODULE)v34 )
        Library = (HMODULE)v34;
    }
    else if ( Library != (HMODULE)-1LL && a1[6] )
    {
      NewUnloadInfo(a1);
    }
    v23 = _pfnDliNotifyHook2;
    v15 = (unsigned int)flOldProtect;
  }
  *(_QWORD *)&v51 = Library;
  if ( v23 )
  {
    v40 = ((__int64 (__fastcall *)(__int64, __int128 *, PfnDliHook, __int64))v23)(2, &v48, v23, v15);
    v23 = _pfnDliNotifyHook2;
    ProcAddress = (FARPROC)v40;
    v15 = (unsigned int)flOldProtect;
  }
  if ( !ProcAddress )
  {
    if ( !a1[5]
      || !a1[7]
      || (v41 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v41) != 17744)
      || *(_DWORD *)((char *)Library + v41 + 8) != (_DWORD)v15
      || Library != *(HMODULE *)((char *)Library + v41 + 48)
      || (ProcAddress = *(FARPROC *)&v16[v19]) == 0 )
    {
      ProcAddress = GetProcAddress(Library, lpProcName[1]);
      if ( !ProcAddress )
      {
        LastError = GetLastError();
        if ( !_pfnDefaultDliFailureHook2 || (ProcAddress = (FARPROC)_pfnDefaultDliFailureHook2(4, &v48)) == 0 )
        {
          flOldProtect = &v48;
          DloadReleaseSectionWriteAccess(v43, v42, v44);
          RaiseException(0xC06D007F, 0, 1u, (const ULONG_PTR *)&flOldProtect);
          DloadAcquireSectionWriteAccess(v46, v45, v47);
          ProcAddress = (FARPROC)*((_QWORD *)&v51 + 1);
        }
      }
      v23 = _pfnDliNotifyHook2;
    }
  }
  *(_QWORD *)a2 = ProcAddress;
LABEL_22:
  if ( v23 )
  {
    LastError = 0;
    *(_QWORD *)&v51 = Library;
    *((_QWORD *)&v51 + 1) = ProcAddress;
    ((void (__fastcall *)(__int64, __int128 *, PfnDliHook, __int64))v23)(5, &v48, v23, v15);
  }
  LODWORD(flOldProtect) = 0;
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( !--DloadSectionLockCount )
  {
    if ( *(_DWORD *)&byte_180000040[(int)off_18000003C + 68] > 0xDu )
    {
      v24 = *(unsigned int *)&byte_180000040[(int)off_18000003C + 176];
      if ( (_DWORD)v24 )
      {
        v25 = *(_DWORD *)((char *)&word_18000000C + v24);
        v26 = (int *)((char *)&_ImageBase
                    + (int)off_18000003C
                    + *(unsigned __int16 *)((char *)&word_180000014 + (int)off_18000003C)
                    + 24);
        for ( j = 0; j < *(unsigned __int16 *)((char *)&word_180000006 + (int)off_18000003C); ++j )
        {
          v28 = (unsigned int)v26[3];
          if ( v25 >= (unsigned int)v28 )
          {
            v29 = (unsigned int)v26[2];
            if ( v25 < (int)v29 + (int)v28 )
            {
              v30 = (char *)&_ImageBase + v28;
              if ( !(HINSTANCE__ *)((char *)&_ImageBase + v28) )
                break;
              v31 = DloadSectionOldProtection;
              if ( DloadSectionCommitPermanent )
              {
                v32 = (unsigned int)v26[2];
              }
              else
              {
                v35 = v26[9] < 0;
                DloadSectionCommitPermanent = 1;
                if ( !v35 )
                  __fastfail(0x19u);
                v32 = v29;
                DloadMakePermanentImageCommit((char *)&_ImageBase + v28, v29);
              }
              if ( !VirtualProtect(v30, v32, v31, (PDWORD)&flOldProtect) )
                __fastfail(0x19u);
              goto LABEL_36;
            }
          }
          v26 += 10;
        }
      }
    }
    LODWORD(flOldProtect) = 4;
  }
LABEL_36:
  ReleaseSRWLockExclusive(&DloadSrwLock);
  return ProcAddress;
}

```

## disassembly

```asm
0x180021030  push    rbp
0x180021032  push    rbx
0x180021033  push    rsi
0x180021034  push    rdi
0x180021035  push    r12
0x180021037  push    r15
0x180021039  mov     rbp, rsp
0x18002103c  sub     rsp, 78h
0x180021040  xorps   xmm0, xmm0
0x180021043  lea     rdi, __ImageBase
0x18002104a  xor     eax, eax
0x18002104c  xor     r8d, r8d
0x18002104f  test    cs:dword_180075DE0, 1000h
0x180021059  mov     r12, rdx
0x18002105c  mov     rsi, rcx
0x18002105f  mov     [rbp+var_18], eax
0x180021062  movups  [rbp+var_58], xmm0
0x180021066  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x18002106a  movups  xmmword ptr [rbp+lpProcName], xmm0
0x18002106e  movups  [rbp+var_28], xmm0
0x180021072  jz      loc_180021156
0x180021078  lea     rcx, DloadSrwLock; SRWLock
0x18002107f  call    cs:__imp_AcquireSRWLockExclusive
0x180021085  mov     eax, cs:DloadSectionLockCount
0x18002108b  inc     eax
0x18002108d  mov     cs:DloadSectionLockCount, eax
0x180021093  cmp     eax, 1
0x180021096  jnz     loc_180021146
0x18002109c  movsxd  rcx, cs:off_18000003C
0x1800210a3  add     rcx, rdi
0x1800210a6  cmp     dword ptr [rcx+84h], 0Dh
0x1800210ad  jbe     loc_180021342
0x1800210b3  mov     r8d, [rcx+0F0h]
0x1800210ba  test    r8d, r8d
0x1800210bd  jz      loc_180021342
0x1800210c3  movzx   edx, word ptr [rcx+14h]
0x1800210c7  mov     r9d, [r8+rdi+0Ch]
0x1800210cc  add     rdx, 18h
0x1800210d0  movzx   r11d, word ptr [rcx+6]
0x1800210d5  add     rdx, rcx
0x1800210d8  xor     r10d, r10d
0x1800210db  cmp     r10d, r11d
0x1800210de  jnb     loc_180021342
0x1800210e4  mov     ecx, [rdx+0Ch]
0x1800210e7  cmp     r9d, ecx
0x1800210ea  jb      short loc_1800210F9
0x1800210ec  mov     r8d, [rdx+8]
0x1800210f0  lea     eax, [r8+rcx]
0x1800210f4  cmp     r9d, eax
0x1800210f7  jb      short loc_180021102
0x1800210f9  inc     r10d
0x1800210fc  add     rdx, 28h ; '('
0x180021100  jmp     short loc_1800210DB
0x180021102  mov     rbx, rcx
0x180021105  add     rbx, rdi
0x180021108  jz      loc_180021342
0x18002110e  cmp     cs:DloadSectionCommitPermanent, 0
0x180021115  jz      loc_180021455
0x18002111b  mov     rdi, r8
0x18002111e  lea     r9, DloadSectionOldProtection; lpflOldProtect
0x180021125  mov     r8d, 4; flNewProtect
0x18002112b  mov     rdx, rdi; dwSize
0x18002112e  mov     rcx, rbx; lpAddress
0x180021131  call    cs:__imp_VirtualProtect
0x180021137  test    eax, eax
0x180021139  jz      loc_18002147F
0x18002113f  lea     rdi, __ImageBase
0x180021146  lea     rcx, DloadSrwLock; SRWLock
0x18002114d  call    cs:__imp_ReleaseSRWLockExclusive
0x180021153  xor     r8d, r8d
0x180021156  mov     eax, [rsi+4]
0x180021159  mov     ebx, [rsi+8]
0x18002115c  add     rax, rdi
0x18002115f  mov     r15d, [rsi+14h]
0x180021163  add     rbx, rdi
0x180021166  mov     r9d, [rsi+1Ch]
0x18002116a  add     r15, rdi
0x18002116d  mov     [rbp+lpLibFileName+8], rax
0x180021171  mov     eax, [rsi]
0x180021173  mov     dword ptr [rbp+flOldProtect], r9d
0x180021177  mov     dword ptr [rbp+var_58], 48h ; 'H'
0x18002117e  mov     qword ptr [rbp+var_58+8], rsi
0x180021182  mov     [rbp+lpLibFileName], r12
0x180021186  mov     dword ptr [rbp+lpProcName], r8d
0x18002118a  mov     [rbp+lpProcName+8], r8
0x18002118e  mov     qword ptr [rbp+var_28], r8
0x180021192  mov     qword ptr [rbp+var_28+8], r8
0x180021196  mov     [rbp+var_18], r8d
0x18002119a  test    al, 1
0x18002119c  jz      loc_18002138F
0x1800211a2  mov     eax, [rsi+0Ch]
0x1800211a5  mov     rcx, r12
0x1800211a8  sub     rcx, rax
0x1800211ab  mov     [rsp+78h+arg_10], r13
0x1800211b3  sub     rcx, rdi
0x1800211b6  mov     [rsp+78h+var_8], r14
0x1800211bb  mov     r14, [rbx]
0x1800211be  sar     rcx, 3
0x1800211c2  mov     eax, ecx
0x1800211c4  mov     ecx, r8d
0x1800211c7  lea     r13, ds:0[rax*8]
0x1800211cf  mov     eax, [rsi+10h]
0x1800211d2  add     rax, r13
0x1800211d5  cmp     qword ptr [rax+rdi], 0
0x1800211da  setnl   cl
0x1800211dd  mov     dword ptr [rbp+lpProcName], ecx
0x1800211e0  mov     edx, [rax+rdi]
0x1800211e3  test    ecx, ecx
0x1800211e5  jz      loc_180021337
0x1800211eb  lea     rax, __ImageBase.unused+2
0x1800211f2  add     rax, rdx
0x1800211f5  mov     [rbp+lpProcName+8], rax
0x1800211f9  mov     rdi, r8
0x1800211fc  mov     r8, cs:__pfnDliNotifyHook2
0x180021203  test    r8, r8
0x180021206  jnz     loc_18002148B
0x18002120c  test    r14, r14
0x18002120f  jz      loc_1800213C2
0x180021215  mov     qword ptr [rbp+var_28], r14
0x180021219  test    r8, r8
0x18002121c  jnz     loc_180021539
0x180021222  test    rdi, rdi
0x180021225  jz      loc_18002135A
0x18002122b  mov     [r12], rdi
0x18002122f  test    r8, r8
0x180021232  jnz     loc_180021412
0x180021238  test    cs:dword_180075DE0, 1000h
0x180021242  mov     dword ptr [rbp+flOldProtect], 0
0x180021249  jz      loc_18002131A
0x18002124f  lea     rcx, DloadSrwLock; SRWLock
0x180021256  call    cs:__imp_AcquireSRWLockExclusive
0x18002125c  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180021263  jnz     loc_18002130D
0x180021269  movsxd  rcx, cs:off_18000003C
0x180021270  lea     rbx, __ImageBase
0x180021277  add     rcx, rbx
0x18002127a  cmp     dword ptr [rcx+84h], 0Dh
0x180021281  jbe     loc_180021351
0x180021287  mov     r8d, [rcx+0F0h]
0x18002128e  test    r8d, r8d
0x180021291  jz      loc_180021351
0x180021297  movzx   edx, word ptr [rcx+14h]
0x18002129b  mov     r9d, [r8+rbx+0Ch]
0x1800212a0  add     rdx, 18h
0x1800212a4  movzx   r11d, word ptr [rcx+6]
0x1800212a9  add     rdx, rcx
0x1800212ac  xor     r10d, r10d
0x1800212af  cmp     r10d, r11d
0x1800212b2  jnb     loc_180021351
0x1800212b8  mov     eax, [rdx+0Ch]
0x1800212bb  cmp     r9d, eax
0x1800212be  jb      short loc_1800212CD
0x1800212c0  mov     r8d, [rdx+8]
0x1800212c4  lea     ecx, [r8+rax]
0x1800212c8  cmp     r9d, ecx
0x1800212cb  jb      short loc_1800212D6
0x1800212cd  inc     r10d
0x1800212d0  add     rdx, 28h ; '('
0x1800212d4  jmp     short loc_1800212AF
0x1800212d6  add     rbx, rax
0x1800212d9  jz      short loc_180021351
0x1800212db  cmp     cs:DloadSectionCommitPermanent, 0
0x1800212e2  mov     r14d, cs:DloadSectionOldProtection
0x1800212e9  jz      loc_1800215F8
0x1800212ef  mov     rsi, r8
0x1800212f2  lea     r9, [rbp+flOldProtect]; lpflOldProtect
0x1800212f6  mov     r8d, r14d; flNewProtect
0x1800212f9  mov     rdx, rsi; dwSize
0x1800212fc  mov     rcx, rbx; lpAddress
0x1800212ff  call    cs:__imp_VirtualProtect
0x180021305  test    eax, eax
0x180021307  jz      loc_180021622
0x18002130d  lea     rcx, DloadSrwLock; SRWLock
0x180021314  call    cs:__imp_ReleaseSRWLockExclusive
0x18002131a  mov     rax, rdi
0x18002131d  mov     r13, [rsp+78h+arg_10]
0x180021325  mov     r14, [rsp+78h+var_8]
0x18002132a  add     rsp, 78h
0x18002132e  pop     r15
0x180021330  pop     r12
0x180021332  pop     rdi
0x180021333  pop     rsi
0x180021334  pop     rbx
0x180021335  pop     rbp
0x180021336  retn
0x180021337  movzx   eax, dx
0x18002133a  mov     dword ptr [rbp+lpProcName+8], eax
0x18002133d  jmp     loc_1800211F9
0x180021342  mov     cs:DloadSectionOldProtection, 4
0x18002134c  jmp     loc_180021146
0x180021351  mov     dword ptr [rbp+flOldProtect], 4
0x180021358  jmp     short loc_18002130D
0x18002135a  cmp     dword ptr [rsi+14h], 0
0x18002135e  jz      short loc_18002136A
0x180021360  cmp     dword ptr [rsi+1Ch], 0
0x180021364  jnz     loc_18002155D
0x18002136a  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x18002136e  mov     rcx, r14; hModule
0x180021371  call    cs:__imp_GetProcAddress
0x180021377  mov     rdi, rax
0x18002137a  test    rax, rax
0x18002137d  jz      loc_180021597
0x180021383  mov     r8, cs:__pfnDliNotifyHook2
0x18002138a  jmp     loc_18002122B
0x18002138f  lea     rax, [rbp+var_58]
0x180021393  mov     [rbp+flOldProtect], rax
0x180021397  call    DloadReleaseSectionWriteAccess
0x18002139c  lea     r9, [rbp+flOldProtect]; lpArguments
0x1800213a0  xor     edx, edx; dwExceptionFlags
0x1800213a2  mov     ecx, 0C06D0057h; dwExceptionCode
0x1800213a7  mov     r8d, 1; nNumberOfArguments
0x1800213ad  call    cs:__imp_RaiseException
0x1800213b3  xor     eax, eax
0x1800213b5  add     rsp, 78h
0x1800213b9  pop     r15
0x1800213bb  pop     r12
0x1800213bd  pop     rdi
0x1800213be  pop     rsi
0x1800213bf  pop     rbx
0x1800213c0  pop     rbp
0x1800213c1  retn
0x1800213c2  test    r8, r8
0x1800213c5  jnz     short loc_180021437
0x1800213c7  mov     rcx, [rbp+lpLibFileName+8]; lpLibFileName
0x1800213cb  xor     r8d, r8d; dwFlags
0x1800213ce  xor     edx, edx; hFile
0x1800213d0  call    cs:__imp_LoadLibraryExA
0x1800213d6  mov     r14, rax
0x1800213d9  test    rax, rax
0x1800213dc  jz      loc_1800214B5
0x1800213e2  xor     eax, eax
0x1800213e4  lock cmpxchg [rbx], r14
0x1800213e9  mov     rbx, rax
0x1800213ec  jnz     loc_18002151E
0x1800213f2  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800213f6  jz      short loc_180021402
0x1800213f8  cmp     dword ptr [rsi+18h], 0
0x1800213fc  jnz     loc_180021511
0x180021402  mov     r8, cs:__pfnDliNotifyHook2
0x180021409  mov     r9d, dword ptr [rbp+flOldProtect]
0x18002140d  jmp     loc_180021215
0x180021412  lea     rdx, [rbp+var_58]
0x180021416  mov     [rbp+var_18], 0
0x18002141d  mov     ecx, 5
0x180021422  mov     qword ptr [rbp+var_28], r14
0x180021426  mov     rax, r8
0x180021429  mov     qword ptr [rbp+var_28+8], rdi
0x18002142d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021432  jmp     loc_180021238
0x180021437  lea     rdx, [rbp+var_58]
0x18002143b  mov     ecx, 1
0x180021440  mov     rax, r8
0x180021443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021448  mov     r14, rax
0x18002144b  test    rax, rax
0x18002144e  jnz     short loc_1800213E2
0x180021450  jmp     loc_1800213C7
0x180021455  cmp     dword ptr [rdx+24h], 0
0x180021459  mov     cs:DloadSectionCommitPermanent, 1
0x180021463  jl      short loc_18002146C
0x180021465  mov     ecx, 19h
0x18002146a  int     29h; Win8: RtlFailFast(ecx)
0x18002146c  mov     rdx, r8
0x18002146f  mov     rcx, rbx
0x180021472  mov     rdi, r8
0x180021475  call    DloadMakePermanentImageCommit
0x18002147a  jmp     loc_18002111E
0x18002147f  mov     ecx, 19h
0x180021484  int     29h; Win8: RtlFailFast(ecx)
0x180021486  jmp     loc_18002113F
0x18002148b  lea     rdx, [rbp+var_58]
0x18002148f  xor     ecx, ecx
0x180021491  mov     rax, r8
0x180021494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021499  mov     r8, cs:__pfnDliNotifyHook2
0x1800214a0  mov     rdi, rax
0x1800214a3  test    rax, rax
0x1800214a6  jnz     loc_18002122F
0x1800214ac  mov     r9d, dword ptr [rbp+flOldProtect]
0x1800214b0  jmp     loc_18002120C
0x1800214b5  call    cs:__imp_GetLastError
0x1800214bb  mov     [rbp+var_18], eax
0x1800214be  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800214c5  test    rax, rax
0x1800214c8  jz      short loc_1800214E4
0x1800214ca  lea     rdx, [rbp+var_58]
0x1800214ce  mov     ecx, 3
0x1800214d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214d8  mov     r14, rax
0x1800214db  test    rax, rax
0x1800214de  jnz     loc_1800213E2
0x1800214e4  lea     rax, [rbp+var_58]
0x1800214e8  mov     [rbp+flOldProtect], rax
0x1800214ec  call    DloadReleaseSectionWriteAccess
0x1800214f1  lea     r9, [rbp+flOldProtect]; lpArguments
0x1800214f5  xor     edx, edx; dwExceptionFlags
0x1800214f7  mov     ecx, 0C06D007Eh; dwExceptionCode
0x1800214fc  mov     r8d, 1; nNumberOfArguments
0x180021502  call    cs:__imp_RaiseException
0x180021508  mov     rax, qword ptr [rbp+var_28+8]
  ... truncated ...
```
