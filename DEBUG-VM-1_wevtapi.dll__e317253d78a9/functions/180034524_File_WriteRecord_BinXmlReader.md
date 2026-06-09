# File::WriteRecord(BinXmlReader &)

- ea: `0x180034524`
- end: `0x1800346f4`
- name: `?WriteRecord@File@@QEAAKAEAVBinXmlReader@@@Z`
- size: `464`
- prototype: `unsigned int __fastcall(File *__hidden this, struct BinXmlReader *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180027510`

## callees

- `0x180030dfc`
- `0x180031064`
- `0x1800323a4`
- `0x180032f54`
- `0x18003409c`
- `0x180034524`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180034582`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180034582`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003468f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003468f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall File::WriteRecord(File *this, struct BinXmlReader *a2)
{
  void (__fastcall ***v5)(_QWORD, LPCWSTR, __int64); // r15
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v8; // r14d
  __int64 v9; // [rsp+38h] [rbp-40h] BYREF
  char v10; // [rsp+40h] [rbp-38h]
  __int64 v11; // [rsp+98h] [rbp+20h] BYREF

  if ( (*((_BYTE *)this + 825) & 4) != 0 )
    return 19;
  v5 = (void (__fastcall ***)(_QWORD, LPCWSTR, __int64))*((_QWORD *)a2 + 22);
  ((void (__fastcall *)(void (__fastcall ***)(_QWORD, LPCWSTR, __int64), __int64 *))(*v5)[3])(v5, &v11);
  v9 = (__int64)this + 664;
  AcquireSRWLockExclusive((PSRWLOCK)this + 83);
  v10 = 1;
  while ( *((_BYTE *)this + 838) )
    utl::condition_variable_any::wait<utl::unique_lock<utl::shared_mutex>>((PCONDITION_VARIABLE)this + 93);
  v6 = File::WriteOneEventToBuffer((LPCWSTR *)this, a2, v5, v11, (__int64)&v9);
  if ( v6 != 111 )
    goto LABEL_16;
  v7 = *(_QWORD *)(*((_QWORD *)this + 20) + 16LL);
  if ( v7 == -1 )
  {
    v6 = 87;
    goto LABEL_16;
  }
  v6 = File::GrowFileInPlace(this, v7 + 1, (__int64)&v9);
  if ( !v6 )
    goto LABEL_15;
  if ( (*((_BYTE *)this + 825) & 1) != 0 )
  {
LABEL_18:
    v6 = 1502;
    goto LABEL_16;
  }
  if ( (*((_BYTE *)this + 825) & 2) != 0 )
  {
    SetLastError(0x5DEu);
    goto LABEL_18;
  }
  if ( v6 == 1502 || v6 == 112 )
  {
    v6 = File::OverwriteOldestChunk(this, *(_QWORD *)(*((_QWORD *)this + 20) + 16LL) + 1LL);
    if ( !v6 )
    {
LABEL_15:
      v8 = *((_DWORD *)this + 204);
      v6 = File::WriteOneEventToBuffer((LPCWSTR *)this, a2, v5, v11, (__int64)&v9);
      *((_DWORD *)this + 204) = v8;
    }
  }
LABEL_16:
  utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(&v9);
  if ( v6 && *((_BYTE *)this + 835) )
  {
    if ( *((_BYTE *)this + 834) )
      return 111;
  }
  return v6;
}

```

## disassembly

```asm
0x180034524  mov     [rsp+arg_8], rbx
0x180034529  mov     [rsp+arg_0], rcx
0x18003452e  push    rsi
0x18003452f  push    rdi
0x180034530  push    r13
0x180034532  push    r14
0x180034534  push    r15
0x180034536  sub     rsp, 50h
0x18003453a  mov     r13, rdx
0x18003453d  mov     rdi, rcx
0x180034540  test    byte ptr [rcx+339h], 4
0x180034547  jz      short loc_180034553
0x180034549  mov     eax, 13h
0x18003454e  jmp     loc_1800346DF
0x180034553  mov     r15, [rdx+0B0h]
0x18003455a  mov     rax, [r15]
0x18003455d  lea     rdx, [rsp+78h+arg_18]
0x180034565  mov     rcx, r15
0x180034568  mov     rax, [rax+18h]
0x18003456c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034571  lea     rcx, [rdi+298h]; SRWLock
0x180034578  mov     [rsp+78h+var_40], rcx
0x18003457d  mov     [rsp+78h+var_38], 0
0x180034582  call    cs:__imp_AcquireSRWLockExclusive
0x180034588  mov     [rsp+78h+var_38], 1
0x18003458d  cmp     byte ptr [rdi+346h], 0
0x180034594  jz      short loc_1800345A9
0x180034596  lea     rdx, [rsp+78h+var_40]
0x18003459b  lea     rcx, [rdi+2E8h]; ConditionVariable
0x1800345a2  call    ??$wait@V?$unique_lock@Vshared_mutex@utl@@@utl@@@condition_variable_any@utl@@QEAAXAEAV?$unique_lock@Vshared_mutex@utl@@@1@@Z; utl::condition_variable_any::wait<utl::unique_lock<utl::shared_mutex>>(utl::unique_lock<utl::shared_mutex> &)
0x1800345a7  jmp     short loc_18003458D
0x1800345a9  lea     rax, [rsp+78h+var_40]
0x1800345ae  mov     [rsp+78h+var_58], rax; __int64
0x1800345b3  mov     r9, [rsp+78h+arg_18]
0x1800345bb  mov     r8, r15
0x1800345be  mov     rdx, r13
0x1800345c1  mov     rcx, rdi; this
0x1800345c4  call    ?WriteOneEventToBuffer@File@@AEAAKAEAVBinXmlReader@@PEAVAbstractPublishedEventRecord@@U_FILETIME@@AEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::WriteOneEventToBuffer(BinXmlReader &,AbstractPublishedEventRecord *,_FILETIME,utl::unique_lock<utl::shared_mutex> &)
0x1800345c9  mov     ebx, eax
0x1800345cb  mov     esi, 6Fh ; 'o'
0x1800345d0  cmp     eax, esi
0x1800345d2  jnz     loc_18003467D
0x1800345d8  mov     rax, [rdi+0A0h]
0x1800345df  mov     rdx, [rax+10h]
0x1800345e3  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800345e7  jnz     short loc_1800345F1
0x1800345e9  lea     ebx, [rsi-18h]
0x1800345ec  jmp     loc_18003467D
0x1800345f1  inc     rdx; unsigned __int64
0x1800345f4  lea     r8, [rsp+78h+var_40]; __int64
0x1800345f9  mov     rcx, rdi; this
0x1800345fc  call    ?GrowFileInPlace@File@@AEAAK_KAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::GrowFileInPlace(unsigned __int64,utl::unique_lock<utl::shared_mutex> &)
0x180034601  mov     ebx, eax
0x180034603  test    eax, eax
0x180034605  jz      short loc_18003464D
0x180034607  mov     cl, [rdi+339h]
0x18003460d  mov     al, cl
0x18003460f  and     al, 1
0x180034611  mov     byte ptr [rsp+78h+arg_10], al
0x180034618  jnz     short loc_180034695
0x18003461a  test    cl, 2
0x18003461d  jnz     short loc_18003468A
0x18003461f  cmp     ebx, 5DEh
0x180034625  jz      short loc_18003462C
0x180034627  cmp     ebx, 70h ; 'p'
0x18003462a  jnz     short loc_18003467D
0x18003462c  mov     rax, [rdi+0A0h]
0x180034633  mov     rdx, [rax+10h]
0x180034637  inc     rdx; unsigned __int64
0x18003463a  lea     r8, [rsp+78h+var_40]
0x18003463f  mov     rcx, rdi; this
0x180034642  call    ?OverwriteOldestChunk@File@@AEAAK_KAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::OverwriteOldestChunk(unsigned __int64,utl::unique_lock<utl::shared_mutex> &)
0x180034647  mov     ebx, eax
0x180034649  test    eax, eax
0x18003464b  jnz     short loc_18003467D
0x18003464d  mov     r14d, [rdi+330h]
0x180034654  lea     rax, [rsp+78h+var_40]
0x180034659  mov     [rsp+78h+var_58], rax; __int64
0x18003465e  mov     r9, [rsp+78h+arg_18]
0x180034666  mov     r8, r15
0x180034669  mov     rdx, r13
0x18003466c  mov     rcx, rdi; this
0x18003466f  call    ?WriteOneEventToBuffer@File@@AEAAKAEAVBinXmlReader@@PEAVAbstractPublishedEventRecord@@U_FILETIME@@AEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::WriteOneEventToBuffer(BinXmlReader &,AbstractPublishedEventRecord *,_FILETIME,utl::unique_lock<utl::shared_mutex> &)
0x180034674  mov     ebx, eax
0x180034676  mov     [rdi+330h], r14d
0x18003467d  lea     rcx, [rsp+78h+var_40]
0x180034682  call    ??1?$unique_lock@Vshared_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(void)
0x180034687  nop
0x180034688  jmp     short loc_1800346B0
0x18003468a  mov     ecx, 5DEh; dwErrCode
0x18003468f  call    cs:__imp_SetLastError
0x180034695  mov     ebx, 5DEh
0x18003469a  jmp     short loc_18003467D
0x18003469c  mov     esi, 6Fh ; 'o'
0x1800346a1  mov     rdi, [rsp+78h+arg_0]
0x1800346a9  mov     ebx, [rsp+78h+arg_10]
0x1800346b0  test    ebx, ebx
0x1800346b2  jz      short loc_1800346DD
0x1800346b4  jmp     short loc_1800346CA
0x1800346b6  mov     esi, 6Fh ; 'o'
0x1800346bb  mov     rdi, [rsp+78h+arg_0]
0x1800346c3  mov     ebx, [rsp+78h+arg_10]
0x1800346ca  cmp     byte ptr [rdi+343h], 0
0x1800346d1  jz      short loc_1800346DD
0x1800346d3  cmp     byte ptr [rdi+342h], 0
0x1800346da  cmovnz  ebx, esi
0x1800346dd  mov     eax, ebx
0x1800346df  mov     rbx, [rsp+78h+arg_8]
0x1800346e7  add     rsp, 50h
0x1800346eb  pop     r15
0x1800346ed  pop     r14
0x1800346ef  pop     r13
0x1800346f1  pop     rdi
0x1800346f2  pop     rsi
0x1800346f3  retn
```
