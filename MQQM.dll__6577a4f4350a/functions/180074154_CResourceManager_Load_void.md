# CResourceManager::Load(void *)

- ea: `0x180074154`
- end: `0x180074369`
- name: `?Load@CResourceManager@@QEAAHPEAX@Z`
- size: `533`
- prototype: `__int64 __fastcall(CResourceManager *__hidden this, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180074370`

## callees

- `0x180009924`
- `0x180061aa4`
- `0x1800637b8`
- `0x180072518`
- `0x180072648`
- `0x180072750`
- `0x180074154`
- `0x18009bd1c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800742c6`
- `KERNEL32!LeaveCriticalSection` at `0x18007432f`
- `KERNEL32!LeaveCriticalSection` at `0x180074340`
- `KERNEL32!LeaveCriticalSection` at `0x18007434c`
- `KERNEL32!LeaveCriticalSection` at `0x1800742c6`
- `KERNEL32!LeaveCriticalSection` at `0x18007432f`
- `KERNEL32!LeaveCriticalSection` at `0x180074340`
- `KERNEL32!LeaveCriticalSection` at `0x18007434c`
- `KERNEL32!ReadFile` at `0x18007418e`
- `KERNEL32!ReadFile` at `0x1800741c8`
- `KERNEL32!ReadFile` at `0x180074201`
- `KERNEL32!ReadFile` at `0x1800742ef`
- `KERNEL32!ReadFile` at `0x18007431c`
- `KERNEL32!ReadFile` at `0x18007418e`
- `KERNEL32!ReadFile` at `0x1800741c8`
- `KERNEL32!ReadFile` at `0x180074201`
- `KERNEL32!ReadFile` at `0x1800742ef`
- `KERNEL32!ReadFile` at `0x18007431c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CResourceManager::Load(CResourceManager *this, void *a2)
{
  unsigned int i; // r15d
  CTransaction *v5; // rax
  CTransaction *v6; // r14
  CTransaction *v8; // [rsp+30h] [rbp-20h] BYREF
  _QWORD Buffer[3]; // [rsp+38h] [rbp-18h] BYREF
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v11; // [rsp+90h] [rbp+40h] BYREF
  int v12; // [rsp+98h] [rbp+48h] BYREF

  NumberOfBytesRead = 0;
  if ( ReadFile(a2, (char *)this + 112, 0x10u, &NumberOfBytesRead, 0) )
  {
    if ( NumberOfBytesRead == 16 )
    {
      Buffer[0] = 0;
      if ( ReadFile(a2, Buffer, 8u, &NumberOfBytesRead, 0) )
      {
        if ( NumberOfBytesRead == 8 )
        {
          v11 = 0;
          if ( ReadFile(a2, &v11, 4u, &NumberOfBytesRead, 0) )
          {
            if ( NumberOfBytesRead == 4 )
            {
              Buffer[1] = (char *)this + 2808;
              CCriticalSection::Lock((CResourceManager *)((char *)this + 2808));
              for ( i = 0; i < v11; ++i )
              {
                v5 = (CTransaction *)MmAllocate(0x268u);
                Buffer[2] = v5;
                if ( v5 )
                  v6 = CTransaction::CTransaction(v5, this, 0, 0);
                else
                  v6 = 0;
                v8 = v6;
                if ( !CTransaction::Load(v6, a2) )
                {
                  P<CTransaction>::~P<CTransaction>(&v8);
                  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2808));
                  return 0;
                }
                v12 = *((_DWORD *)v6 + 4);
                *(_QWORD *)CMap<unsigned long,unsigned long const &,CTransaction *,CTransaction *>::operator[](
                             (char *)this + 56,
                             &v12) = v6;
                *(_QWORD *)CMap<BOID,BOID const &,CTransaction *,CTransaction *>::operator[](
                             (char *)this + 8,
                             (char *)v6 + 28) = v6;
                v8 = 0;
                P<CTransaction>::~P<CTransaction>(&v8);
              }
              if ( ReadFile(a2, (char *)this + 128, 4u, &NumberOfBytesRead, 0)
                && NumberOfBytesRead == 4
                && ReadFile(a2, (char *)this + 132, 4u, &NumberOfBytesRead, 0)
                && NumberOfBytesRead == 4 )
              {
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2808));
                return 1;
              }
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2808));
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180074154  mov     [rsp-28h+arg_8], rbx
0x180074159  push    rbp
0x18007415a  push    rsi
0x18007415b  push    rdi
0x18007415c  push    r14
0x18007415e  push    r15
0x180074160  mov     rbp, rsp
0x180074163  sub     rsp, 50h
0x180074167  mov     rdi, rdx
0x18007416a  mov     rsi, rcx
0x18007416d  mov     [rbp+NumberOfBytesRead], 0
0x180074174  lea     rdx, [rcx+70h]; lpBuffer
0x180074178  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x180074181  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180074185  mov     r8d, 10h; nNumberOfBytesToRead
0x18007418b  mov     rcx, rdi; hFile
0x18007418e  call    cs:__imp_ReadFile
0x180074194  test    eax, eax
0x180074196  jz      loc_180074353
0x18007419c  cmp     [rbp+NumberOfBytesRead], 10h
0x1800741a0  jnz     loc_180074353
0x1800741a6  mov     [rbp+Buffer], 0
0x1800741ae  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x1800741b7  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800741bb  mov     r8d, 8; nNumberOfBytesToRead
0x1800741c1  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800741c5  mov     rcx, rdi; hFile
0x1800741c8  call    cs:__imp_ReadFile
0x1800741ce  test    eax, eax
0x1800741d0  jz      loc_180074353
0x1800741d6  cmp     [rbp+NumberOfBytesRead], 8
0x1800741da  jnz     loc_180074353
0x1800741e0  mov     [rbp+arg_10], 0
0x1800741e7  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x1800741f0  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800741f4  mov     r8d, 4; nNumberOfBytesToRead
0x1800741fa  lea     rdx, [rbp+arg_10]; lpBuffer
0x1800741fe  mov     rcx, rdi; hFile
0x180074201  call    cs:__imp_ReadFile
0x180074207  test    eax, eax
0x180074209  jz      loc_180074353
0x18007420f  cmp     [rbp+NumberOfBytesRead], 4
0x180074213  jnz     loc_180074353
0x180074219  lea     rbx, [rsi+0AF8h]
0x180074220  mov     [rbp+var_10], rbx
0x180074224  mov     rcx, rbx; this
0x180074227  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18007422c  nop
0x18007422d  xor     r15d, r15d
0x180074230  cmp     r15d, [rbp+arg_10]
0x180074234  jnb     loc_1800742D2
0x18007423a  mov     ecx, 268h; unsigned __int64
0x18007423f  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180074244  mov     [rbp+var_8], rax
0x180074248  test    rax, rax
0x18007424b  jz      short loc_180074263
0x18007424d  xor     r9d, r9d; int
0x180074250  xor     r8d, r8d; unsigned int
0x180074253  mov     rdx, rsi; struct CResourceManager *
0x180074256  mov     rcx, rax; this
0x180074259  call    ??0CTransaction@@QEAA@PEAVCResourceManager@@KH@Z; CTransaction::CTransaction(CResourceManager *,ulong,int)
0x18007425e  mov     r14, rax
0x180074261  jmp     short loc_180074266
0x180074263  xor     r14d, r14d
0x180074266  mov     [rbp+var_20], r14
0x18007426a  mov     rdx, rdi; void *
0x18007426d  mov     rcx, r14; this
0x180074270  call    ?Load@CTransaction@@QEAAHPEAX@Z; CTransaction::Load(void *)
0x180074275  test    eax, eax
0x180074277  jz      short loc_1800742B9
0x180074279  mov     eax, [r14+10h]
0x18007427d  mov     [rbp+arg_18], eax
0x180074280  lea     rcx, [rsi+38h]
0x180074284  lea     rdx, [rbp+arg_18]
0x180074288  call    ??A?$CMap@KAEBKPEAVCTransaction@@PEAV1@@@QEAAAEAPEAVCTransaction@@AEBK@Z; CMap<ulong,ulong const &,CTransaction *,CTransaction *>::operator[](ulong const &)
0x18007428d  mov     [rax], r14
0x180074290  lea     rdx, [r14+1Ch]
0x180074294  lea     rcx, [rsi+8]
0x180074298  call    ??A?$CMap@UBOID@@AEBU1@PEAVCTransaction@@PEAV2@@@QEAAAEAPEAVCTransaction@@AEBUBOID@@@Z; CMap<BOID,BOID const &,CTransaction *,CTransaction *>::operator[](BOID const &)
0x18007429d  mov     [rax], r14
0x1800742a0  mov     [rbp+var_20], 0
0x1800742a8  lea     rcx, [rbp+var_20]
0x1800742ac  call    ??1?$P@VCTransaction@@@@QEAA@XZ; P<CTransaction>::~P<CTransaction>(void)
0x1800742b1  inc     r15d
0x1800742b4  jmp     loc_180074230
0x1800742b9  lea     rcx, [rbp+var_20]
0x1800742bd  call    ??1?$P@VCTransaction@@@@QEAA@XZ; P<CTransaction>::~P<CTransaction>(void)
0x1800742c2  nop
0x1800742c3  mov     rcx, rbx; lpCriticalSection
0x1800742c6  call    cs:__imp_LeaveCriticalSection
0x1800742cc  nop
0x1800742cd  jmp     loc_180074353
0x1800742d2  lea     rdx, [rsi+80h]; lpBuffer
0x1800742d9  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x1800742e2  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800742e6  mov     r8d, 4; nNumberOfBytesToRead
0x1800742ec  mov     rcx, rdi; hFile
0x1800742ef  call    cs:__imp_ReadFile
0x1800742f5  test    eax, eax
0x1800742f7  jz      short loc_180074349
0x1800742f9  cmp     [rbp+NumberOfBytesRead], 4
0x1800742fd  jnz     short loc_180074349
0x1800742ff  lea     rdx, [rsi+84h]; lpBuffer
0x180074306  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x18007430f  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180074313  mov     r8d, 4; nNumberOfBytesToRead
0x180074319  mov     rcx, rdi; hFile
0x18007431c  call    cs:__imp_ReadFile
0x180074322  test    eax, eax
0x180074324  jz      short loc_18007433D
0x180074326  cmp     [rbp+NumberOfBytesRead], 4
0x18007432a  jnz     short loc_18007433D
0x18007432c  mov     rcx, rbx; lpCriticalSection
0x18007432f  call    cs:__imp_LeaveCriticalSection
0x180074335  nop
0x180074336  mov     eax, 1
0x18007433b  jmp     short loc_180074355
0x18007433d  mov     rcx, rbx; lpCriticalSection
0x180074340  call    cs:__imp_LeaveCriticalSection
0x180074346  nop
0x180074347  jmp     short loc_180074353
0x180074349  mov     rcx, rbx; lpCriticalSection
0x18007434c  call    cs:__imp_LeaveCriticalSection
0x180074352  nop
0x180074353  xor     eax, eax
0x180074355  mov     rbx, [rsp+50h+arg_8]
0x18007435d  add     rsp, 50h
0x180074361  pop     r15
0x180074363  pop     r14
0x180074365  pop     rdi
0x180074366  pop     rsi
0x180074367  pop     rbp
0x180074368  retn
```
