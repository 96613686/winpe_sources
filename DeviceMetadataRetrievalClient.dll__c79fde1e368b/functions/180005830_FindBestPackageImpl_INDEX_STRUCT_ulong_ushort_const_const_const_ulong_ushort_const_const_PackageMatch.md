# FindBestPackageImpl(_INDEX_STRUCT *,ulong,ushort const * const * const,ulong,ushort const * const *,PackageMatch &)

- ea: `0x180005830`
- end: `0x180005a2f`
- name: `?FindBestPackageImpl@@YA_NPEAU_INDEX_STRUCT@@KQEBQEBGKPEBQEBGAEAUPackageMatch@@@Z`
- size: `511`
- prototype: `char __fastcall(RTL_SRWLOCK *, int, const unsigned __int16 *const *const, int, const unsigned __int16 *const *, struct PackageMatch *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005758`

## callees

- `0x180004dc4`
- `0x180005830`
- `0x180005a38`
- `0x180007f3c`

## import_xrefs

- `msvcrt!free` at `0x1800059c8`
- `msvcrt!free` at `0x180005a1c`
- `msvcrt!free` at `0x1800059c8`
- `msvcrt!free` at `0x180005a1c`
- `KERNEL32!GetProcessHeap` at `0x180005966`
- `KERNEL32!GetProcessHeap` at `0x1800059ac`
- `KERNEL32!GetProcessHeap` at `0x180005a00`
- `KERNEL32!GetProcessHeap` at `0x180005966`
- `KERNEL32!GetProcessHeap` at `0x1800059ac`
- `KERNEL32!GetProcessHeap` at `0x180005a00`
- `KERNEL32!HeapFree` at `0x1800059ba`
- `KERNEL32!HeapFree` at `0x180005a0e`
- `KERNEL32!HeapFree` at `0x1800059ba`
- `KERNEL32!HeapFree` at `0x180005a0e`
- `KERNEL32!GetFileAttributesW` at `0x180005977`
- `KERNEL32!GetFileAttributesW` at `0x180005977`
- `KERNEL32!CompareFileTime` at `0x1800058fd`
- `KERNEL32!CompareFileTime` at `0x1800058fd`
- `KERNEL32!AcquireSRWLockShared` at `0x18000586e`
- `KERNEL32!AcquireSRWLockShared` at `0x18000586e`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800058a8`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000592d`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800058a8`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000592d`

## pseudocode

```c
char __fastcall FindBestPackageImpl(
        RTL_SRWLOCK *a1,
        int a2,
        const unsigned __int16 *const *const a3,
        int a4,
        const unsigned __int16 *const *a5,
        struct PackageMatch *a6)
{
  RTL_SRWLOCK *v6; // r14
  int v7; // ebp
  int v9; // edi
  void *v11; // rcx
  void *v12; // rsi
  char *v13; // rbx
  char *v14; // rbp
  char *v15; // rdi
  bool v16; // cf
  bool v17; // zf
  char v18; // al
  unsigned int v19; // eax
  LONG v20; // eax
  WCHAR *ObjectString; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v23; // r8
  DWORD FileAttributesW; // eax
  HANDLE v25; // rax
  void *Block; // [rsp+30h] [rbp-48h] BYREF
  __int64 v28; // [rsp+38h] [rbp-40h]
  __int64 v29; // [rsp+40h] [rbp-38h]
  int v30; // [rsp+48h] [rbp-30h]

  v6 = a1 + 4;
  Block = 0;
  v7 = (int)a1;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v9 = (int)a3;
  AcquireSRWLockShared(a1 + 4);
  FindPackageMatches(v7, a2, v9, a4, (__int64)a5, (__int64)&Block);
  if ( !v28 )
  {
    ReleaseSRWLockShared(v6);
    v11 = Block;
    if ( Block )
      goto LABEL_31;
    return 0;
  }
  v12 = Block;
  v13 = (char *)Block;
  v14 = (char *)Block + 64 * v28;
  v15 = (char *)Block;
  if ( Block != v14 )
  {
    while ( 1 )
    {
      v13 += 64;
      if ( v13 == v14 )
        break;
      v16 = *(_DWORD *)v15 < *(_DWORD *)v13;
      v17 = *(_DWORD *)v15 == *(_DWORD *)v13;
      if ( *(_DWORD *)v15 != *(_DWORD *)v13 )
        goto LABEL_7;
      v18 = v13[4];
      if ( v15[4] != v18 )
        goto LABEL_12;
      v19 = *((_DWORD *)v15 + 2);
      v16 = v19 < *((_DWORD *)v13 + 2);
      v17 = v19 == *((_DWORD *)v13 + 2);
      if ( v19 == *((_DWORD *)v13 + 2) )
      {
        v20 = CompareFileTime((const FILETIME *)(v15 + 12), (const FILETIME *)(v13 + 12));
        if ( v20 )
        {
          v18 = v20 == -1;
          goto LABEL_12;
        }
      }
      else
      {
LABEL_7:
        v18 = !v16 && !v17;
LABEL_12:
        if ( v18 )
          v15 = v13;
      }
    }
  }
  ObjectString = MemGetObjectString((struct NDX_OBJREF *)(v15 + 24), 0);
  ReleaseSRWLockShared(v6);
  if ( !ObjectString )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids);
    ProcessHeap = GetProcessHeap();
    v23 = 0;
    goto LABEL_29;
  }
  FileAttributesW = GetFileAttributesW(ObjectString);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids);
    ProcessHeap = GetProcessHeap();
    v23 = ObjectString;
LABEL_29:
    HeapFree(ProcessHeap, 0, v23);
    if ( v12 )
    {
      v11 = v12;
LABEL_31:
      free(v11);
    }
    return 0;
  }
  *(_OWORD *)a6 = *(_OWORD *)v15;
  *((_OWORD *)a6 + 1) = *((_OWORD *)v15 + 1);
  *((_OWORD *)a6 + 2) = *((_OWORD *)v15 + 2);
  *((_OWORD *)a6 + 3) = *((_OWORD *)v15 + 3);
  v25 = GetProcessHeap();
  HeapFree(v25, 0, ObjectString);
  if ( v12 )
    free(v12);
  return 1;
}

```

## disassembly

```asm
0x180005830  mov     rax, rsp
0x180005833  push    rbx
0x180005834  push    rbp
0x180005835  push    rsi
0x180005836  push    rdi
0x180005837  push    r14
0x180005839  sub     rsp, 50h
0x18000583d  lea     r14, [rcx+20h]
0x180005841  mov     qword ptr [rax-48h], 0
0x180005849  mov     rbp, rcx
0x18000584c  mov     qword ptr [rax-40h], 0
0x180005854  mov     rcx, r14; SRWLock
0x180005857  mov     qword ptr [rax-38h], 0
0x18000585f  mov     ebx, r9d
0x180005862  mov     dword ptr [rax-30h], 0
0x180005869  mov     rdi, r8
0x18000586c  mov     esi, edx
0x18000586e  call    cs:__imp_AcquireSRWLockShared
0x180005874  lea     rax, [rsp+78h+Block]
0x180005879  mov     r9d, ebx
0x18000587c  mov     [rsp+78h+var_50], rax
0x180005881  mov     r8, rdi
0x180005884  mov     rax, [rsp+78h+arg_20]
0x18000588c  mov     edx, esi
0x18000588e  mov     rcx, rbp
0x180005891  mov     [rsp+78h+var_58], rax
0x180005896  call    ?FindPackageMatches@@YAXPEAU_INDEX_STRUCT@@KPEBQEBGK1AEAV?$CAtlArray@UPackageMatch@@V?$CElementTraits@UPackageMatch@@@ATL@@@ATL@@@Z; FindPackageMatches(_INDEX_STRUCT *,ulong,ushort const * const *,ulong,ushort const * const *,ATL::CAtlArray<PackageMatch,ATL::CElementTraits<PackageMatch>> &)
0x18000589b  mov     rbp, [rsp+78h+var_40]
0x1800058a0  test    rbp, rbp
0x1800058a3  jnz     short loc_1800058C1
0x1800058a5  mov     rcx, r14; SRWLock
0x1800058a8  call    cs:__imp_ReleaseSRWLockShared
0x1800058ae  mov     rcx, [rsp+78h+Block]
0x1800058b3  test    rcx, rcx
0x1800058b6  jz      loc_180005A22
0x1800058bc  jmp     loc_180005A1C
0x1800058c1  mov     rsi, [rsp+78h+Block]
0x1800058c6  shl     rbp, 6
0x1800058ca  mov     rbx, rsi
0x1800058cd  add     rbp, rsi
0x1800058d0  mov     rdi, rsi
0x1800058d3  cmp     rsi, rbp
0x1800058d6  jz      short loc_18000591C
0x1800058d8  jmp     short loc_180005913
0x1800058da  mov     eax, [rdi]
0x1800058dc  cmp     eax, [rbx]
0x1800058de  jz      short loc_1800058E5
0x1800058e0  setnbe  al
0x1800058e3  jmp     short loc_18000590D
0x1800058e5  mov     al, [rbx+4]
0x1800058e8  cmp     [rdi+4], al
0x1800058eb  jnz     short loc_18000590D
0x1800058ed  mov     eax, [rdi+8]
0x1800058f0  cmp     eax, [rbx+8]
0x1800058f3  jnz     short loc_1800058E0
0x1800058f5  lea     rdx, [rbx+0Ch]; lpFileTime2
0x1800058f9  lea     rcx, [rdi+0Ch]; lpFileTime1
0x1800058fd  call    cs:__imp_CompareFileTime
0x180005903  test    eax, eax
0x180005905  jz      short loc_180005913
0x180005907  cmp     eax, 0FFFFFFFFh
0x18000590a  setz    al
0x18000590d  test    al, al
0x18000590f  cmovnz  rdi, rbx
0x180005913  add     rbx, 40h ; '@'
0x180005917  cmp     rbx, rbp
0x18000591a  jnz     short loc_1800058DA
0x18000591c  lea     rcx, [rdi+18h]; struct NDX_OBJREF *
0x180005920  xor     edx, edx; int
0x180005922  call    ?MemGetObjectString@@YAPEAGPEAUNDX_OBJREF@@J@Z; MemGetObjectString(NDX_OBJREF *,long)
0x180005927  mov     rcx, r14; SRWLock
0x18000592a  mov     rbx, rax
0x18000592d  call    cs:__imp_ReleaseSRWLockShared
0x180005933  test    rbx, rbx
0x180005936  jnz     short loc_180005974
0x180005938  mov     rcx, cs:WPP_GLOBAL_Control
0x18000593f  lea     rax, WPP_GLOBAL_Control
0x180005946  cmp     rcx, rax
0x180005949  jz      short loc_180005966
0x18000594b  test    byte ptr [rcx+1Ch], 1
0x18000594f  jz      short loc_180005966
0x180005951  mov     rcx, [rcx+10h]
0x180005955  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x18000595c  mov     edx, 98h
0x180005961  call    WPP_SF_
0x180005966  call    cs:__imp_GetProcessHeap
0x18000596c  xor     r8d, r8d
0x18000596f  jmp     loc_180005A09
0x180005974  mov     rcx, rbx; lpFileName
0x180005977  call    cs:__imp_GetFileAttributesW
0x18000597d  cmp     eax, 0FFFFFFFFh
0x180005980  jz      short loc_1800059D2
0x180005982  test    al, 10h
0x180005984  jnz     short loc_1800059D2
0x180005986  movups  xmm0, xmmword ptr [rdi]
0x180005989  mov     rax, [rsp+78h+arg_28]
0x180005991  movaps  xmmword ptr [rax], xmm0
0x180005994  movups  xmm1, xmmword ptr [rdi+10h]
0x180005998  movaps  xmmword ptr [rax+10h], xmm1
0x18000599c  movups  xmm0, xmmword ptr [rdi+20h]
0x1800059a0  movaps  xmmword ptr [rax+20h], xmm0
0x1800059a4  movups  xmm1, xmmword ptr [rdi+30h]
0x1800059a8  movaps  xmmword ptr [rax+30h], xmm1
0x1800059ac  call    cs:__imp_GetProcessHeap
0x1800059b2  mov     r8, rbx; lpMem
0x1800059b5  xor     edx, edx; dwFlags
0x1800059b7  mov     rcx, rax; hHeap
0x1800059ba  call    cs:__imp_HeapFree
0x1800059c0  test    rsi, rsi
0x1800059c3  jz      short loc_1800059CE
0x1800059c5  mov     rcx, rsi; Block
0x1800059c8  call    cs:__imp_free
0x1800059ce  mov     al, 1
0x1800059d0  jmp     short loc_180005A24
0x1800059d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059d9  lea     rax, WPP_GLOBAL_Control
0x1800059e0  cmp     rcx, rax
0x1800059e3  jz      short loc_180005A00
0x1800059e5  test    byte ptr [rcx+1Ch], 1
0x1800059e9  jz      short loc_180005A00
0x1800059eb  mov     rcx, [rcx+10h]
0x1800059ef  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x1800059f6  mov     edx, 99h
0x1800059fb  call    WPP_SF_
0x180005a00  call    cs:__imp_GetProcessHeap
0x180005a06  mov     r8, rbx; lpMem
0x180005a09  xor     edx, edx; dwFlags
0x180005a0b  mov     rcx, rax; hHeap
0x180005a0e  call    cs:__imp_HeapFree
0x180005a14  test    rsi, rsi
0x180005a17  jz      short loc_180005A22
0x180005a19  mov     rcx, rsi; Block
0x180005a1c  call    cs:__imp_free
0x180005a22  xor     al, al
0x180005a24  add     rsp, 50h
0x180005a28  pop     r14
0x180005a2a  pop     rdi
0x180005a2b  pop     rsi
0x180005a2c  pop     rbp
0x180005a2d  pop     rbx
0x180005a2e  retn
```
