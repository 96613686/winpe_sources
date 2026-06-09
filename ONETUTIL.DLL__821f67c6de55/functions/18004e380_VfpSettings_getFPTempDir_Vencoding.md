# VfpSettings::getFPTempDir(Vencoding)

- ea: `0x18004e380`
- end: `0x18004e5d0`
- name: `?getFPTempDir@VfpSettings@@SA?AVVstring@@W4Vencoding@@@Z`
- size: `592`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x18004e5d0`
- `0x18004fab0`
- `0x180091ff0`

## callees

- `0x180038e20`
- `0x180040d60`
- `0x180040e60`
- `0x18004e380`
- `0x1800838f0`
- `0x180090610`
- `0x180092190`
- `0x1800938a0`
- `0x180095100`
- `0x180133d30`
- `0x180134070`
- `0x180134920`
- `0x1801503e0`
- `0x180150894`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!GetTempPathA` at `0x18004e3e6`
- `KERNEL32!GetTempPathA` at `0x18004e3fd`
- `KERNEL32!GetTempPathA` at `0x18004e3e6`
- `KERNEL32!GetTempPathA` at `0x18004e3fd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e49c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e568`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e5c2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e49c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e568`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e5c2`

## string_xrefs

- `0x18004e43d`: `WebTempDir`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
Vstring *__fastcall VfpSettings::getFPTempDir(Vstring *a1, int a2)
{
  signed int TempPathA; // eax
  int *v5; // rcx
  struct Vstatus *DirTree; // rax
  __int64 v7; // r9
  int *v8; // rcx
  char *v9; // rcx
  char *v11; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v12; // [rsp+30h] [rbp-D8h]
  __int64 v13; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v14[6]; // [rsp+40h] [rbp-C8h] BYREF
  CHAR v15[24]; // [rsp+70h] [rbp-98h] BYREF
  CHAR Buffer[272]; // [rsp+88h] [rbp-80h] BYREF

  v14[3] = -2;
  v14[4] = a1;
  *(_QWORD *)a1 = dword_1802AFD5C;
  _InterlockedIncrement(&dword_1802AFD50);
  LODWORD(v12) = 1;
  if ( (int)GetTempPathA(0, Buffer) > 0 )
  {
    TempPathA = GetTempPathA(0x104u, Buffer);
    if ( (unsigned __int64)TempPathA >= 0x104 )
      _report_rangecheckfailure();
    Buffer[TempPathA] = 0;
    RWCString::RWCString((RWCString *)&v11, Buffer);
    Vstring::doConvertToUtf8((Vstring *)&v11, v11, *((_DWORD *)v11 - 1), 0);
    RWCString::RWCString((RWCString *)&v13, "WebTempDir");
    Vpath::Vpath((Vpath *)v14, (const struct Vstring *)&v11, (const struct Vstring *)&v13, Class);
    v5 = (int *)(v13 - 12);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v13 - 12), 0xFFFFFFFF) == 1 && v5 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v5);
      else
        free(v5);
    }
    if ( Vpath::isDir((Vpath *)v14) || (DirTree = Vpath::createDirTree((Vpath *)v14, 0, 0)) == 0 )
    {
      RWCString::operator=(a1, v14);
    }
    else
    {
      (**(void (__fastcall ***)(struct Vstatus *, __int64))DirTree)(DirTree, 1);
      RWCString::operator=(a1, &v11);
      LOBYTE(v7) = 92;
      RWCString::strip(a1, v15, 2, v7);
      Vstring::operator=(a1, v15);
    }
    if ( !a2 )
      Vstring::convertToLCP(a1, 0);
    Vpath::ClearStat((Vpath *)v14);
    v14[5] = v14;
    v8 = (int *)(v14[0] - 12LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v14[0] - 12LL), 0xFFFFFFFF) == 1 && v8 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v8);
      else
        free(v8);
    }
    v9 = v11 - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 - 3, 0xFFFFFFFF) == 1 && v9 != (char *)&dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v9);
      else
        free(v9);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18004e380  mov     rax, rsp
0x18004e383  push    rbp
0x18004e384  lea     rbp, [rax-0A8h]
0x18004e38b  sub     rsp, 1A0h
0x18004e392  mov     [rsp+1A0h+var_150], 0FFFFFFFFFFFFFFFEh
0x18004e39b  mov     [rax+10h], rbx
0x18004e39f  mov     [rax+18h], rdi
0x18004e3a3  mov     [rax+20h], r15
0x18004e3a7  mov     rax, cs:__security_cookie
0x18004e3ae  xor     rax, rsp
0x18004e3b1  mov     [rbp+0A0h+var_10], rax
0x18004e3b8  mov     edi, edx
0x18004e3ba  mov     rbx, rcx
0x18004e3bd  mov     [rsp+1A0h+var_148], rcx
0x18004e3c2  and     dword ptr [rsp+1A0h+var_178], 0
0x18004e3c7  lea     rax, dword_1802AFD5C
0x18004e3ce  mov     [rcx], rax
0x18004e3d1  lock inc cs:dword_1802AFD50
0x18004e3d8  mov     dword ptr [rsp+1A0h+var_178], 1
0x18004e3e0  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18004e3e4  xor     ecx, ecx; nBufferLength
0x18004e3e6  call    cs:GetTempPathA
0x18004e3ec  test    eax, eax
0x18004e3ee  jle     loc_18004E597
0x18004e3f4  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18004e3f8  mov     ecx, 104h; nBufferLength
0x18004e3fd  call    cs:GetTempPathA
0x18004e403  movsxd  rcx, eax
0x18004e406  cmp     rcx, 104h
0x18004e40d  jnb     loc_18004E5CA
0x18004e413  mov     [rbp+rcx+0A0h+Buffer], 0
0x18004e418  lea     rdx, [rbp+0A0h+Buffer]; char *
0x18004e41c  lea     rcx, [rsp+1A0h+var_180]; this
0x18004e421  call    ??0RWCString@@QEAA@PEBD@Z; RWCString::RWCString(char const *)
0x18004e426  nop
0x18004e427  mov     rdx, [rsp+1A0h+var_180]; char *
0x18004e42c  xor     r9d, r9d; unsigned int
0x18004e42f  mov     r8d, [rdx-4]; unsigned int
0x18004e433  lea     rcx, [rsp+1A0h+var_180]; this
0x18004e438  call    ?doConvertToUtf8@Vstring@@AEAAJPEBDII@Z; Vstring::doConvertToUtf8(char const *,uint,uint)
0x18004e43d  lea     rdx, aWebtempdir; "WebTempDir"
0x18004e444  lea     rcx, [rsp+1A0h+var_170]; this
0x18004e449  call    ??0RWCString@@QEAA@PEBD@Z; RWCString::RWCString(char const *)
0x18004e44e  nop
0x18004e44f  lea     r9, Class; char *
0x18004e456  lea     r8, [rsp+1A0h+var_170]; struct Vstring *
0x18004e45b  lea     rdx, [rsp+1A0h+var_180]; struct Vstring *
0x18004e460  lea     rcx, [rsp+1A0h+var_168]; this
0x18004e465  call    ??0Vpath@@QEAA@AEBVVstring@@0PEBD@Z; Vpath::Vpath(Vstring const &,Vstring const &,char const *)
0x18004e46a  nop
0x18004e46b  mov     rcx, [rsp+1A0h+var_170]
0x18004e470  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18004e474  or      eax, 0FFFFFFFFh
0x18004e477  lock xadd [rcx], eax
0x18004e47b  lea     r15, dword_1802AFD50
0x18004e482  cmp     eax, 1
0x18004e485  jnz     short loc_18004E4A2
0x18004e487  cmp     rcx, r15
0x18004e48a  jz      short loc_18004E4A2
0x18004e48c  cmp     cs:dword_1802B0018, 0
0x18004e493  jz      short loc_18004E49C
0x18004e495  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18004e49a  jmp     short loc_18004E4A2
0x18004e49c  call    cs:free
0x18004e4a2  lea     rcx, [rsp+1A0h+var_168]; this
0x18004e4a7  call    ?isDir@Vpath@@QEAADXZ; Vpath::isDir(void)
0x18004e4ac  test    al, al
0x18004e4ae  jnz     short loc_18004E50D
0x18004e4b0  xor     r8d, r8d; unsigned int *
0x18004e4b3  xor     edx, edx; struct Vstring *
0x18004e4b5  lea     rcx, [rsp+1A0h+var_168]; this
0x18004e4ba  call    ?createDirTree@Vpath@@QEAAPEAVVstatus@@PEAVVstring@@PEAK@Z; Vpath::createDirTree(Vstring *,ulong *)
0x18004e4bf  mov     r8, rax
0x18004e4c2  test    rax, rax
0x18004e4c5  jz      short loc_18004E50D
0x18004e4c7  mov     rcx, [rax]
0x18004e4ca  mov     rax, [rcx]
0x18004e4cd  mov     edx, 1
0x18004e4d2  mov     rcx, r8
0x18004e4d5  call    cs:__guard_dispatch_icall_fptr
0x18004e4db  lea     rdx, [rsp+1A0h+var_180]
0x18004e4e0  mov     rcx, rbx
0x18004e4e3  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x18004e4e8  mov     r9b, 5Ch ; '\'
0x18004e4eb  mov     r8d, 2
0x18004e4f1  lea     rdx, [rsp+1A0h+var_138]
0x18004e4f6  mov     rcx, rbx
0x18004e4f9  call    ?strip@RWCString@@QEAA?AVRWCSubString@@W4stripType@1@D@Z; RWCString::strip(RWCString::stripType,char)
0x18004e4fe  lea     rdx, [rsp+1A0h+var_138]
0x18004e503  mov     rcx, rbx
0x18004e506  call    ??4Vstring@@QEAAAEAV0@AEBVRWCSubString@@@Z; Vstring::operator=(RWCSubString const &)
0x18004e50b  jmp     short loc_18004E51A
0x18004e50d  lea     rdx, [rsp+1A0h+var_168]
0x18004e512  mov     rcx, rbx
0x18004e515  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x18004e51a  test    edi, edi
0x18004e51c  jnz     short loc_18004E529
0x18004e51e  xor     edx, edx; unsigned int
0x18004e520  mov     rcx, rbx; this
0x18004e523  call    ?convertToLCP@Vstring@@QEAAJI@Z; Vstring::convertToLCP(uint)
0x18004e528  nop
0x18004e529  lea     rcx, [rsp+1A0h+var_168]; this
0x18004e52e  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x18004e533  nop
0x18004e534  lea     rax, [rsp+1A0h+var_168]
0x18004e539  mov     qword ptr [rsp+1A0h+var_140], rax
0x18004e53e  mov     rcx, [rsp+1A0h+var_168]
0x18004e543  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18004e547  or      eax, 0FFFFFFFFh
0x18004e54a  lock xadd [rcx], eax
0x18004e54e  cmp     eax, 1
0x18004e551  jnz     short loc_18004E56F
0x18004e553  cmp     rcx, r15
0x18004e556  jz      short loc_18004E56F
0x18004e558  cmp     cs:dword_1802B0018, 0
0x18004e55f  jz      short loc_18004E568
0x18004e561  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18004e566  jmp     short loc_18004E56F
0x18004e568  call    cs:free
0x18004e56e  nop
0x18004e56f  mov     rcx, [rsp+1A0h+var_180]
0x18004e574  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18004e578  or      eax, 0FFFFFFFFh
0x18004e57b  lock xadd [rcx], eax
0x18004e57f  cmp     eax, 1
0x18004e582  jnz     short loc_18004E597
0x18004e584  cmp     rcx, r15
0x18004e587  jz      short loc_18004E597
0x18004e589  cmp     cs:dword_1802B0018, 0
0x18004e590  jz      short loc_18004E5C2
0x18004e592  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18004e597  mov     rax, rbx
0x18004e59a  mov     rcx, [rbp+0A0h+var_10]
0x18004e5a1  xor     rcx, rsp
0x18004e5a4  call    sub_1801503E0
0x18004e5a9  lea     r11, [rsp+1A0h+var_s0]
0x18004e5b1  mov     rbx, [r11+18h]
0x18004e5b5  mov     rdi, [r11+20h]
0x18004e5b9  mov     r15, [r11+28h]
0x18004e5bd  mov     rsp, r11
0x18004e5c0  pop     rbp
0x18004e5c1  retn
0x18004e5c2  call    cs:free
0x18004e5c8  jmp     short loc_18004E597
0x18004e5ca  call    __report_rangecheckfailure
```
