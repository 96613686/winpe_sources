# __delayLoadHelper2

- ea: `0x18000f070`
- end: `0x18000f5dc`
- name: `__delayLoadHelper2`
- size: `1388`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004026a`

## callees

- `0x18000ef30`
- `0x18000f070`
- `0x18000f5f0`
- `0x18000f6c0`
- `0x18000f8a0`
- `0x180077bb4`
- `0x180080010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18000f453`
- `KERNEL32!RaiseException` at `0x18000f4ea`
- `KERNEL32!RaiseException` at `0x18000f5b0`
- `KERNEL32!RaiseException` at `0x18000f453`
- `KERNEL32!RaiseException` at `0x18000f4ea`
- `KERNEL32!RaiseException` at `0x18000f5b0`
- `KERNEL32!FreeLibrary` at `0x18000f502`
- `KERNEL32!FreeLibrary` at `0x18000f502`
- `KERNEL32!GetProcAddress` at `0x18000f551`
- `KERNEL32!GetProcAddress` at `0x18000f551`
- `KERNEL32!GetLastError` at `0x18000f49d`
- `KERNEL32!GetLastError` at `0x18000f563`
- `KERNEL32!GetLastError` at `0x18000f49d`
- `KERNEL32!GetLastError` at `0x18000f563`
- `KERNEL32!VirtualProtect` at `0x18000f16e`
- `KERNEL32!VirtualProtect` at `0x18000f386`
- `KERNEL32!VirtualProtect` at `0x18000f16e`
- `KERNEL32!VirtualProtect` at `0x18000f386`
- `KERNEL32!LoadLibraryExA` at `0x18000f48b`
- `KERNEL32!LoadLibraryExA` at `0x18000f48b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f0c0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f29e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f0c0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f29e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f185`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f39b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f185`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f39b`

## pseudocode

```c
__int64 __fastcall _delayLoadHelper2(int *a1, CHAR *a2)
{
  __int64 v4; // r8
  unsigned int v5; // r10d
  unsigned int v6; // r8d
  int *v7; // rdx
  __int64 v8; // rcx
  SIZE_T v9; // r9
  char *v10; // rbx
  SIZE_T v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  volatile signed __int64 *v15; // r14
  __int64 v16; // rcx
  char *v17; // r15
  int v18; // eax
  HMODULE Library; // rdi
  __int64 v20; // r13
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 Hook; // rbx
  __int64 v24; // r8
  unsigned int v25; // r10d
  unsigned int v26; // r8d
  int *v27; // rdx
  __int64 v28; // rax
  SIZE_T v29; // r9
  char *v30; // rdi
  DWORD v31; // r14d
  SIZE_T v32; // rsi
  signed __int64 v34; // rbx
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  __int128 v44; // [rsp+20h] [rbp-50h] BYREF
  LPCSTR lpLibFileName[2]; // [rsp+30h] [rbp-40h]
  LPCSTR lpProcName[2]; // [rsp+40h] [rbp-30h]
  __int128 v47; // [rsp+50h] [rbp-20h]
  DWORD LastError; // [rsp+60h] [rbp-10h]
  __int128 *flOldProtect; // [rsp+B0h] [rbp+40h] BYREF

  LastError = 0;
  v44 = 0;
  *(_OWORD *)lpLibFileName = 0;
  *(_OWORD *)lpProcName = 0;
  v47 = 0;
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( ++DloadSectionLockCount == 1 )
  {
    if ( *(_DWORD *)&byte_180000040[(int)off_18000003C + 68] > 0xDu )
    {
      v4 = *(unsigned int *)&byte_180000040[(int)off_18000003C + 176];
      if ( (_DWORD)v4 )
      {
        v5 = 0;
        v6 = *(_DWORD *)((char *)&word_18000000C + v4);
        v7 = (int *)((char *)&_ImageBase
                   + (int)off_18000003C
                   + *(unsigned __int16 *)((char *)&word_180000014 + (int)off_18000003C)
                   + 24);
        while ( v5 < *(unsigned __int16 *)((char *)&word_180000006 + (int)off_18000003C) )
        {
          v8 = (unsigned int)v7[3];
          if ( v6 >= (unsigned int)v8 )
          {
            v9 = (unsigned int)v7[2];
            if ( v6 < (int)v9 + (int)v8 )
            {
              v10 = (char *)&_ImageBase + v8;
              if ( !(struct HINSTANCE__ *)((char *)&_ImageBase + v8) )
                break;
              if ( DloadSectionCommitPermanent )
              {
                v11 = (unsigned int)v7[2];
              }
              else
              {
                DloadSectionCommitPermanent = 1;
                if ( v7[9] >= 0 )
                  __fastfail(0x19u);
                v11 = v9;
                DloadMakePermanentImageCommit(v10, v9);
              }
              if ( !VirtualProtect(v10, v11, 4u, &DloadSectionOldProtection) )
                __fastfail(0x19u);
              goto LABEL_13;
            }
          }
          ++v5;
          v7 += 10;
        }
      }
    }
    DloadSectionOldProtection = 4;
  }
LABEL_13:
  ReleaseSRWLockExclusive(&DloadSrwLock);
  v15 = (volatile signed __int64 *)((char *)&_ImageBase.unused + (unsigned int)a1[2]);
  v16 = (unsigned int)a1[7];
  v17 = (char *)&_ImageBase + (unsigned int)a1[5];
  lpLibFileName[1] = (char *)&_ImageBase + (unsigned int)a1[1];
  v18 = *a1;
  LODWORD(flOldProtect) = v16;
  LODWORD(v44) = 72;
  *((_QWORD *)&v44 + 1) = a1;
  lpLibFileName[0] = a2;
  LODWORD(lpProcName[0]) = 0;
  lpProcName[1] = 0;
  v47 = 0u;
  LastError = 0;
  if ( (v18 & 1) == 0 )
  {
    flOldProtect = &v44;
    DloadReleaseSectionWriteAccess(v16, v12, v13, v14, v44, *((_QWORD *)&v44 + 1), lpLibFileName[0]);
    RaiseException(0xC06D0057, 0, 1u, (const ULONG_PTR *)&flOldProtect);
    return 0;
  }
  Library = (HMODULE)*v15;
  v20 = 8LL * (unsigned int)((&a2[-a1[3]] - (CHAR *)&_ImageBase) >> 3);
  v21 = v20 + (unsigned int)a1[4];
  LODWORD(lpProcName[0]) = *(_QWORD *)((char *)&_ImageBase.unused + v21) >= 0LL;
  v22 = *(unsigned int *)((char *)&_ImageBase.unused + v21);
  if ( LODWORD(lpProcName[0]) )
    lpProcName[1] = (char *)&_ImageBase.unused + v22 + 2;
  else
    LODWORD(lpProcName[1]) = (unsigned __int16)v22;
  Hook = PhotoBase_DelayLoadHook(0, (__int64)&v44);
  if ( !Hook )
  {
    if ( !Library )
    {
      Library = (HMODULE)PhotoBase_DelayLoadHook(1, (__int64)&v44);
      if ( !Library )
      {
        Library = LoadLibraryExA(lpLibFileName[1], 0, 0);
        if ( !Library )
        {
          LastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, &v44)) == 0 )
          {
            flOldProtect = &v44;
            DloadReleaseSectionWriteAccess(v36, v35, v37, v38, v44, *((_QWORD *)&v44 + 1), lpLibFileName[0]);
            RaiseException(0xC06D007E, 0, 1u, (const ULONG_PTR *)&flOldProtect);
            return *((_QWORD *)&v47 + 1);
          }
        }
      }
      v34 = _InterlockedCompareExchange64(v15, (signed __int64)Library, 0);
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
    }
    *(_QWORD *)&v47 = Library;
    Hook = PhotoBase_DelayLoadHook(2, (__int64)&v44);
    if ( !Hook )
    {
      if ( !a1[5]
        || !a1[7]
        || (v39 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v39) != 17744)
        || *(_DWORD *)((char *)Library + v39 + 8) != (_DWORD)flOldProtect
        || Library != *(HMODULE *)((char *)Library + v39 + 48)
        || (Hook = *(_QWORD *)&v17[v20]) == 0 )
      {
        Hook = (__int64)GetProcAddress(Library, lpProcName[1]);
        if ( !Hook )
        {
          LastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Hook = _pfnDefaultDliFailureHook2(4, &v44)) == 0 )
          {
            flOldProtect = &v44;
            DloadReleaseSectionWriteAccess(v41, v40, v42, v43, v44, *((_QWORD *)&v44 + 1), lpLibFileName[0]);
            RaiseException(0xC06D007F, 0, 1u, (const ULONG_PTR *)&flOldProtect);
            DloadAcquireSectionWriteAccess();
            Hook = *((_QWORD *)&v47 + 1);
          }
        }
      }
    }
    *(_QWORD *)a2 = Hook;
  }
  *(_QWORD *)&v47 = Library;
  LastError = 0;
  *((_QWORD *)&v47 + 1) = Hook;
  PhotoBase_DelayLoadHook(5, (__int64)&v44);
  LODWORD(flOldProtect) = 0;
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( !--DloadSectionLockCount )
  {
    if ( *(_DWORD *)&byte_180000040[(int)off_18000003C + 68] > 0xDu )
    {
      v24 = *(unsigned int *)&byte_180000040[(int)off_18000003C + 176];
      if ( (_DWORD)v24 )
      {
        v25 = 0;
        v26 = *(_DWORD *)((char *)&word_18000000C + v24);
        v27 = (int *)((char *)&_ImageBase
                    + (int)off_18000003C
                    + *(unsigned __int16 *)((char *)&word_180000014 + (int)off_18000003C)
                    + 24);
        while ( v25 < *(unsigned __int16 *)((char *)&word_180000006 + (int)off_18000003C) )
        {
          v28 = (unsigned int)v27[3];
          if ( v26 >= (unsigned int)v28 )
          {
            v29 = (unsigned int)v27[2];
            if ( v26 < (int)v29 + (int)v28 )
            {
              v30 = (char *)&_ImageBase + v28;
              if ( !(struct HINSTANCE__ *)((char *)&_ImageBase + v28) )
                break;
              v31 = DloadSectionOldProtection;
              if ( DloadSectionCommitPermanent )
              {
                v32 = (unsigned int)v27[2];
              }
              else
              {
                DloadSectionCommitPermanent = 1;
                if ( v27[9] >= 0 )
                  __fastfail(0x19u);
                v32 = v29;
                DloadMakePermanentImageCommit((char *)&_ImageBase + v28, v29);
              }
              if ( !VirtualProtect(v30, v32, v31, (PDWORD)&flOldProtect) )
                __fastfail(0x19u);
              goto LABEL_36;
            }
          }
          ++v25;
          v27 += 10;
        }
      }
    }
    LODWORD(flOldProtect) = 4;
  }
LABEL_36:
  ReleaseSRWLockExclusive(&DloadSrwLock);
  return Hook;
}

```

## disassembly

```asm
0x18000f070  push    rbp
0x18000f072  push    rbx
0x18000f073  push    rsi
0x18000f074  push    rdi
0x18000f075  push    r12
0x18000f077  push    r14
0x18000f079  push    r15
0x18000f07b  mov     rbp, rsp
0x18000f07e  sub     rsp, 70h
0x18000f082  xorps   xmm0, xmm0
0x18000f085  lea     rbx, __ImageBase
0x18000f08c  xor     eax, eax
0x18000f08e  xor     edi, edi
0x18000f090  test    cs:dword_180082370, 1000h
0x18000f09a  mov     r12, rdx
0x18000f09d  mov     rsi, rcx
0x18000f0a0  mov     [rbp+var_10], eax
0x18000f0a3  movups  [rbp+var_50], xmm0
0x18000f0a7  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x18000f0ab  movups  xmmword ptr [rbp+lpProcName], xmm0
0x18000f0af  movups  [rbp+var_20], xmm0
0x18000f0b3  jz      loc_18000F192
0x18000f0b9  lea     rcx, DloadSrwLock; SRWLock
0x18000f0c0  call    cs:__imp_AcquireSRWLockExclusive
0x18000f0c6  mov     eax, cs:DloadSectionLockCount
0x18000f0cc  inc     eax
0x18000f0ce  mov     cs:DloadSectionLockCount, eax
0x18000f0d4  cmp     eax, 1
0x18000f0d7  jnz     loc_18000F17E
0x18000f0dd  movsxd  rcx, cs:off_18000003C
0x18000f0e4  add     rcx, rbx
0x18000f0e7  cmp     dword ptr [rcx+84h], 0Dh
0x18000f0ee  jbe     loc_18000F329
0x18000f0f4  mov     r8d, [rcx+0F0h]
0x18000f0fb  test    r8d, r8d
0x18000f0fe  jz      loc_18000F329
0x18000f104  movzx   edx, word ptr [rcx+14h]
0x18000f108  mov     r10d, edi
0x18000f10b  mov     r8d, [r8+rbx+0Ch]
0x18000f110  add     rdx, 18h
0x18000f114  movzx   r11d, word ptr [rcx+6]
0x18000f119  add     rdx, rcx
0x18000f11c  cmp     r10d, r11d
0x18000f11f  jnb     loc_18000F329
0x18000f125  mov     ecx, [rdx+0Ch]
0x18000f128  cmp     r8d, ecx
0x18000f12b  jb      short loc_18000F13A
0x18000f12d  mov     r9d, [rdx+8]
0x18000f131  lea     eax, [r9+rcx]
0x18000f135  cmp     r8d, eax
0x18000f138  jb      short loc_18000F143
0x18000f13a  inc     r10d
0x18000f13d  add     rdx, 28h ; '('
0x18000f141  jmp     short loc_18000F11C
0x18000f143  add     rbx, rcx
0x18000f146  jz      loc_18000F329
0x18000f14c  cmp     cs:DloadSectionCommitPermanent, edi
0x18000f152  jz      loc_18000F338
0x18000f158  mov     rdi, r9
0x18000f15b  lea     r9, DloadSectionOldProtection; lpflOldProtect
0x18000f162  mov     r8d, 4; flNewProtect
0x18000f168  mov     rdx, rdi; dwSize
0x18000f16b  mov     rcx, rbx; lpAddress
0x18000f16e  call    cs:__imp_VirtualProtect
0x18000f174  test    eax, eax
0x18000f176  jz      loc_18000F476
0x18000f17c  xor     edi, edi
0x18000f17e  lea     rcx, DloadSrwLock; SRWLock
0x18000f185  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f18b  lea     rbx, __ImageBase
0x18000f192  mov     eax, [rsi+4]
0x18000f195  mov     r14d, [rsi+8]
0x18000f199  add     rax, rbx
0x18000f19c  mov     r15d, [rsi+14h]
0x18000f1a0  add     r14, rbx
0x18000f1a3  mov     ecx, [rsi+1Ch]
0x18000f1a6  add     r15, rbx
0x18000f1a9  mov     [rbp+lpLibFileName+8], rax
0x18000f1ad  mov     eax, [rsi]
0x18000f1af  mov     dword ptr [rbp+flOldProtect], ecx
0x18000f1b2  mov     dword ptr [rbp+var_50], 48h ; 'H'
0x18000f1b9  mov     qword ptr [rbp+var_50+8], rsi
0x18000f1bd  mov     [rbp+lpLibFileName], r12
0x18000f1c1  mov     dword ptr [rbp+lpProcName], edi
0x18000f1c4  mov     [rbp+lpProcName+8], rdi
0x18000f1c8  mov     qword ptr [rbp+var_20], rdi
0x18000f1cc  mov     qword ptr [rbp+var_20+8], rdi
0x18000f1d0  mov     [rbp+var_10], edi
0x18000f1d3  test    al, 1
0x18000f1d5  jz      loc_18000F435
0x18000f1db  mov     eax, [rsi+0Ch]
0x18000f1de  mov     rcx, r12
0x18000f1e1  mov     rdi, [r14]
0x18000f1e4  sub     rcx, rax
0x18000f1e7  sub     rcx, rbx
0x18000f1ea  mov     [rsp+70h+arg_10], r13
0x18000f1f2  sar     rcx, 3
0x18000f1f6  mov     eax, ecx
0x18000f1f8  xor     ecx, ecx
0x18000f1fa  lea     r13, ds:0[rax*8]
0x18000f202  mov     eax, [rsi+10h]
0x18000f205  add     rax, r13
0x18000f208  cmp     [rax+rbx], rcx
0x18000f20c  setnl   cl
0x18000f20f  mov     dword ptr [rbp+lpProcName], ecx
0x18000f212  mov     edx, [rax+rbx]
0x18000f215  test    ecx, ecx
0x18000f217  jz      loc_18000F31E
0x18000f21d  lea     rax, __ImageBase.unused+2
0x18000f224  add     rax, rdx
0x18000f227  mov     [rbp+lpProcName+8], rax
0x18000f22b  lea     rdx, [rbp+var_50]
0x18000f22f  xor     ecx, ecx
0x18000f231  call    PhotoBase_DelayLoadHook
0x18000f236  mov     rbx, rax
0x18000f239  test    rax, rax
0x18000f23c  jnz     short loc_18000F269
0x18000f23e  test    rdi, rdi
0x18000f241  jz      loc_18000F3C4
0x18000f247  lea     rdx, [rbp+var_50]
0x18000f24b  mov     qword ptr [rbp+var_20], rdi
0x18000f24f  mov     ecx, 2
0x18000f254  call    PhotoBase_DelayLoadHook
0x18000f259  mov     rbx, rax
0x18000f25c  test    rax, rax
0x18000f25f  jz      loc_18000F514
0x18000f265  mov     [r12], rbx
0x18000f269  xor     esi, esi
0x18000f26b  mov     qword ptr [rbp+var_20], rdi
0x18000f26f  lea     rdx, [rbp+var_50]
0x18000f273  mov     [rbp+var_10], esi
0x18000f276  mov     ecx, 5
0x18000f27b  mov     qword ptr [rbp+var_20+8], rbx
0x18000f27f  call    PhotoBase_DelayLoadHook
0x18000f284  test    cs:dword_180082370, 1000h
0x18000f28e  mov     dword ptr [rbp+flOldProtect], esi
0x18000f291  jz      loc_18000F3A1
0x18000f297  lea     rcx, DloadSrwLock; SRWLock
0x18000f29e  call    cs:__imp_AcquireSRWLockExclusive
0x18000f2a4  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18000f2ab  jnz     loc_18000F394
0x18000f2b1  movsxd  rcx, cs:off_18000003C
0x18000f2b8  lea     rdi, __ImageBase
0x18000f2bf  add     rcx, rdi
0x18000f2c2  cmp     dword ptr [rcx+84h], 0Dh
0x18000f2c9  jbe     loc_18000F3BB
0x18000f2cf  mov     r8d, [rcx+0F0h]
0x18000f2d6  test    r8d, r8d
0x18000f2d9  jz      loc_18000F3BB
0x18000f2df  movzx   edx, word ptr [rcx+14h]
0x18000f2e3  mov     r10d, esi
0x18000f2e6  mov     r8d, [r8+rdi+0Ch]
0x18000f2eb  add     rdx, 18h
0x18000f2ef  movzx   r11d, word ptr [rcx+6]
0x18000f2f4  add     rdx, rcx
0x18000f2f7  cmp     r10d, r11d
0x18000f2fa  jnb     loc_18000F3BB
0x18000f300  mov     eax, [rdx+0Ch]
0x18000f303  cmp     r8d, eax
0x18000f306  jb      short loc_18000F315
0x18000f308  mov     r9d, [rdx+8]
0x18000f30c  lea     ecx, [r9+rax]
0x18000f310  cmp     r8d, ecx
0x18000f313  jb      short loc_18000F35E
0x18000f315  inc     r10d
0x18000f318  add     rdx, 28h ; '('
0x18000f31c  jmp     short loc_18000F2F7
0x18000f31e  movzx   eax, dx
0x18000f321  mov     dword ptr [rbp+lpProcName+8], eax
0x18000f324  jmp     loc_18000F22B
0x18000f329  mov     cs:DloadSectionOldProtection, 4
0x18000f333  jmp     loc_18000F17E
0x18000f338  mov     cs:DloadSectionCommitPermanent, 1
0x18000f342  cmp     [rdx+24h], edi
0x18000f345  jge     loc_18000F46A
0x18000f34b  mov     rdx, r9
0x18000f34e  mov     rcx, rbx
0x18000f351  mov     rdi, r9
0x18000f354  call    DloadMakePermanentImageCommit
0x18000f359  jmp     loc_18000F15B
0x18000f35e  add     rdi, rax
0x18000f361  jz      short loc_18000F3BB
0x18000f363  cmp     cs:DloadSectionCommitPermanent, esi
0x18000f369  mov     r14d, cs:DloadSectionOldProtection
0x18000f370  jz      loc_18000F40F
0x18000f376  mov     rsi, r9
0x18000f379  lea     r9, [rbp+flOldProtect]; lpflOldProtect
0x18000f37d  mov     r8d, r14d; flNewProtect
0x18000f380  mov     rdx, rsi; dwSize
0x18000f383  mov     rcx, rdi; lpAddress
0x18000f386  call    cs:__imp_VirtualProtect
0x18000f38c  test    eax, eax
0x18000f38e  jz      loc_18000F5D0
0x18000f394  lea     rcx, DloadSrwLock; SRWLock
0x18000f39b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f3a1  mov     rax, rbx
0x18000f3a4  mov     r13, [rsp+70h+arg_10]
0x18000f3ac  add     rsp, 70h
0x18000f3b0  pop     r15
0x18000f3b2  pop     r14
0x18000f3b4  pop     r12
0x18000f3b6  pop     rdi
0x18000f3b7  pop     rsi
0x18000f3b8  pop     rbx
0x18000f3b9  pop     rbp
0x18000f3ba  retn
0x18000f3bb  mov     dword ptr [rbp+flOldProtect], 4
0x18000f3c2  jmp     short loc_18000F394
0x18000f3c4  lea     rdx, [rbp+var_50]
0x18000f3c8  mov     ecx, 1
0x18000f3cd  call    PhotoBase_DelayLoadHook
0x18000f3d2  mov     rdi, rax
0x18000f3d5  test    rax, rax
0x18000f3d8  jz      loc_18000F482
0x18000f3de  xor     eax, eax
0x18000f3e0  lock cmpxchg [r14], rdi
0x18000f3e5  mov     rbx, rax
0x18000f3e8  jnz     loc_18000F4F9
0x18000f3ee  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000f3f2  jz      loc_18000F247
0x18000f3f8  cmp     dword ptr [rsi+18h], 0
0x18000f3fc  jz      loc_18000F247
0x18000f402  mov     rcx, rsi
0x18000f405  call    NewUnloadInfo
0x18000f40a  jmp     loc_18000F247
0x18000f40f  mov     cs:DloadSectionCommitPermanent, 1
0x18000f419  cmp     [rdx+24h], esi
0x18000f41c  jge     loc_18000F5C4
0x18000f422  mov     rdx, r9
0x18000f425  mov     rcx, rdi
0x18000f428  mov     rsi, r9
0x18000f42b  call    DloadMakePermanentImageCommit
0x18000f430  jmp     loc_18000F379
0x18000f435  lea     rax, [rbp+var_50]
0x18000f439  mov     [rbp+flOldProtect], rax
0x18000f43d  call    DloadReleaseSectionWriteAccess
0x18000f442  lea     r9, [rbp+flOldProtect]; lpArguments
0x18000f446  xor     edx, edx; dwExceptionFlags
0x18000f448  mov     ecx, 0C06D0057h; dwExceptionCode
0x18000f44d  mov     r8d, 1; nNumberOfArguments
0x18000f453  call    cs:__imp_RaiseException
0x18000f459  xor     eax, eax
0x18000f45b  add     rsp, 70h
0x18000f45f  pop     r15
0x18000f461  pop     r14
0x18000f463  pop     r12
0x18000f465  pop     rdi
0x18000f466  pop     rsi
0x18000f467  pop     rbx
0x18000f468  pop     rbp
0x18000f469  retn
0x18000f46a  mov     ecx, 19h
0x18000f46f  int     29h; Win8: RtlFailFast(ecx)
0x18000f471  jmp     loc_18000F34B
0x18000f476  mov     ecx, 19h
0x18000f47b  int     29h; Win8: RtlFailFast(ecx)
0x18000f47d  jmp     loc_18000F17C
0x18000f482  mov     rcx, [rbp+lpLibFileName+8]; lpLibFileName
0x18000f486  xor     r8d, r8d; dwFlags
0x18000f489  xor     edx, edx; hFile
0x18000f48b  call    cs:__imp_LoadLibraryExA
0x18000f491  mov     rdi, rax
0x18000f494  test    rax, rax
0x18000f497  jnz     loc_18000F3DE
0x18000f49d  call    cs:__imp_GetLastError
0x18000f4a3  mov     [rbp+var_10], eax
0x18000f4a6  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18000f4ad  test    rax, rax
0x18000f4b0  jz      short loc_18000F4CC
0x18000f4b2  lea     rdx, [rbp+var_50]
0x18000f4b6  mov     ecx, 3
0x18000f4bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4c0  mov     rdi, rax
0x18000f4c3  test    rax, rax
0x18000f4c6  jnz     loc_18000F3DE
0x18000f4cc  lea     rax, [rbp+var_50]
0x18000f4d0  mov     [rbp+flOldProtect], rax
0x18000f4d4  call    DloadReleaseSectionWriteAccess
0x18000f4d9  lea     r9, [rbp+flOldProtect]; lpArguments
0x18000f4dd  xor     edx, edx; dwExceptionFlags
0x18000f4df  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18000f4e4  mov     r8d, 1; nNumberOfArguments
0x18000f4ea  call    cs:__imp_RaiseException
0x18000f4f0  mov     rax, qword ptr [rbp+var_20+8]
0x18000f4f4  jmp     loc_18000F3A4
0x18000f4f9  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000f4fd  jz      short loc_18000F508
0x18000f4ff  mov     rcx, rdi; hLibModule
0x18000f502  call    cs:__imp_FreeLibrary
0x18000f508  cmp     rdi, rbx
0x18000f50b  cmovnz  rdi, rbx
0x18000f50f  jmp     loc_18000F247
0x18000f514  cmp     dword ptr [rsi+14h], 0
0x18000f518  jz      short loc_18000F54A
0x18000f51a  cmp     dword ptr [rsi+1Ch], 0
0x18000f51e  jz      short loc_18000F54A
0x18000f520  movsxd  rax, dword ptr [rdi+3Ch]
0x18000f524  cmp     dword ptr [rax+rdi], 4550h
0x18000f52b  jnz     short loc_18000F54A
0x18000f52d  mov     ecx, dword ptr [rbp+flOldProtect]
  ... truncated ...
```
