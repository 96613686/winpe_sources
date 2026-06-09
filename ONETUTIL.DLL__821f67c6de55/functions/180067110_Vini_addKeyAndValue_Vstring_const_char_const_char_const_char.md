# Vini::addKeyAndValue(Vstring const &,char const *,char const *,char)

- ea: `0x180067110`
- end: `0x1800673b8`
- name: `?addKeyAndValue@Vini@@QEAAPEAVVstatus@@AEBVVstring@@PEBD1D@Z`
- size: `680`
- prototype: `struct Vstatus *(Vini *__hidden this, const struct Vstring *, const char *, const char *, char)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180040b90`
- `0x180040e60`
- `0x180048e50`
- `0x180067110`
- `0x1800673b8`
- `0x180083790`
- `0x1800838f0`
- `0x1800b93d0`

## import_xrefs

- `KERNEL32!WritePrivateProfileStringA` at `0x1800671ad`
- `KERNEL32!WritePrivateProfileStringA` at `0x18006729f`
- `KERNEL32!WritePrivateProfileStringA` at `0x1800671ad`
- `KERNEL32!WritePrivateProfileStringA` at `0x18006729f`
- `KERNEL32!GetLastError` at `0x1800671f5`
- `KERNEL32!GetLastError` at `0x1800672e9`
- `KERNEL32!GetLastError` at `0x1800671f5`
- `KERNEL32!GetLastError` at `0x1800672e9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800671e8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800672db`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180067364`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180067391`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800671e8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800672db`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180067364`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180067391`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180067212`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180067307`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180067212`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180067307`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
struct Vstatus *__fastcall Vini::addKeyAndValue(
        LPCSTR *this,
        const struct Vstring *a2,
        const char *a3,
        const char *a4,
        char a5)
{
  LPCSTR *v10; // rax
  _BOOL8 v11; // rbx
  int *v12; // rcx
  __int64 v13; // rbx
  DWORD v14; // esi
  VgenericStatus *v15; // rax
  VgenericStatus *v16; // rbx
  LPCSTR *v17; // rax
  bool v18; // r12
  int *v19; // rcx
  __int64 v20; // rsi
  DWORD LastError; // r12d
  VgenericStatus *v22; // rax
  CHAR *v23; // rcx
  CHAR *v24; // rcx
  LPCSTR lpKeyName; // [rsp+30h] [rbp-40h] BYREF
  LPCSTR lpString; // [rsp+38h] [rbp-38h] BYREF
  __int64 v27; // [rsp+40h] [rbp-30h] BYREF
  __int64 v28; // [rsp+48h] [rbp-28h] BYREF
  __int64 v29; // [rsp+50h] [rbp-20h] BYREF
  _QWORD v30[2]; // [rsp+58h] [rbp-18h] BYREF
  VgenericStatus *v31; // [rsp+68h] [rbp-8h]

  v30[1] = -2;
  if ( a5 && a4 )
    return (struct Vstatus *)sub_1800673B8();
  Vstring::Vstring((Vstring *)&lpKeyName, a3);
  if ( !*(_BYTE *)this )
    Vstring::convertToLCP((Vstring *)&lpKeyName, 0);
  if ( a4 )
  {
    Vstring::Vstring((Vstring *)&lpString, a4);
    if ( !*(_BYTE *)this )
      Vstring::convertToLCP((Vstring *)&lpString, 0);
    v31 = (VgenericStatus *)&v28;
    v28 = *(_QWORD *)a2;
    _InterlockedIncrement((volatile signed __int32 *)(v28 - 12));
    v17 = (LPCSTR *)sub_180048E50(v30, &v28);
    v18 = !WritePrivateProfileStringA(*v17, lpKeyName, lpString, this[2]);
    v19 = (int *)(v30[0] - 12LL);
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v30[0] - 12LL)) && v19 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v19);
      else
        free(v19);
    }
    if ( v18 )
    {
      v20 = *(_QWORD *)a2;
      LastError = GetLastError();
      if ( dword_1802B0018 )
        v22 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
      else
        v22 = (VgenericStatus *)malloc(0x20u);
      v31 = v22;
      if ( v22 )
        v16 = VgenericStatus::VgenericStatus(v22, 0x20020u, LastError, v20, a3, a4);
      else
        v16 = 0;
    }
    else
    {
      v16 = 0;
    }
    v23 = (CHAR *)(lpString - 12);
    if ( !_InterlockedDecrement((volatile signed __int32 *)lpString - 3) && v23 != (CHAR *)&dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v23);
      else
        free(v23);
    }
  }
  else
  {
    v31 = (VgenericStatus *)&v27;
    v27 = *(_QWORD *)a2;
    _InterlockedIncrement((volatile signed __int32 *)(v27 - 12));
    v10 = (LPCSTR *)sub_180048E50(&v29, &v27);
    v11 = !WritePrivateProfileStringA(*v10, lpKeyName, 0, this[2]);
    v12 = (int *)(v29 - 12);
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v29 - 12)) && v12 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v12);
      else
        free(v12);
    }
    if ( v11 )
    {
      v13 = *(_QWORD *)a2;
      v14 = GetLastError();
      if ( dword_1802B0018 )
        v15 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
      else
        v15 = (VgenericStatus *)malloc(0x20u);
      v31 = v15;
      if ( v15 )
        v16 = VgenericStatus::VgenericStatus(v15, 0x20020u, v14, v13, a3, 0);
      else
        v16 = 0;
    }
    else
    {
      v16 = 0;
    }
  }
  v24 = (CHAR *)(lpKeyName - 12);
  if ( !_InterlockedDecrement((volatile signed __int32 *)lpKeyName - 3) && v24 != (CHAR *)&dword_1802AFD50 )
  {
    if ( dword_1802B0018 )
      COWSAllocator::Free(v24);
    else
      free(v24);
  }
  return v16;
}

```

## disassembly

```asm
0x180067110  mov     rax, rsp
0x180067113  push    rbp
0x180067114  push    r14
0x180067116  push    r15
0x180067118  mov     rbp, rsp
0x18006711b  sub     rsp, 70h
0x18006711f  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x180067127  mov     [rax+8], rbx
0x18006712b  mov     [rax+10h], rsi
0x18006712f  mov     [rax+18h], rdi
0x180067133  mov     [rax+20h], r12
0x180067137  mov     rbx, r9
0x18006713a  mov     r15, r8
0x18006713d  mov     rsi, rdx
0x180067140  mov     rdi, rcx
0x180067143  cmp     [rbp+arg_20], 0
0x180067147  jz      short loc_180067158
0x180067149  test    rbx, rbx
0x18006714c  jz      short loc_180067158
0x18006714e  call    sub_1800673B8
0x180067153  jmp     loc_18006739A
0x180067158  mov     rdx, r15; char *
0x18006715b  lea     rcx, [rbp+lpKeyName]; this
0x18006715f  call    ??0Vstring@@QEAA@PEBD@Z; Vstring::Vstring(char const *)
0x180067164  nop
0x180067165  cmp     byte ptr [rdi], 0
0x180067168  jnz     short loc_180067175
0x18006716a  xor     edx, edx; unsigned int
0x18006716c  lea     rcx, [rbp+lpKeyName]; this
0x180067170  call    ?convertToLCP@Vstring@@QEAAJI@Z; Vstring::convertToLCP(uint)
0x180067175  test    rbx, rbx
0x180067178  jnz     loc_180067252
0x18006717e  lea     rax, [rbp+var_30]
0x180067182  mov     [rbp+var_8], rax
0x180067186  mov     rax, [rsi]
0x180067189  mov     [rbp+var_30], rax
0x18006718d  lock inc dword ptr [rax-0Ch]
0x180067191  lea     rdx, [rbp+var_30]
0x180067195  lea     rcx, [rbp+var_20]
0x180067199  call    sub_180048E50
0x18006719e  nop
0x18006719f  mov     r9, [rdi+10h]; lpFileName
0x1800671a3  xor     r8d, r8d; lpString
0x1800671a6  mov     rdx, [rbp+lpKeyName]; lpKeyName
0x1800671aa  mov     rcx, [rax]; lpAppName
0x1800671ad  call    cs:WritePrivateProfileStringA
0x1800671b3  test    eax, eax
0x1800671b5  setz    bl
0x1800671b8  mov     rcx, [rbp+var_20]
0x1800671bc  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800671c0  or      edi, 0FFFFFFFFh
0x1800671c3  mov     eax, edi
0x1800671c5  lock xadd [rcx], eax
0x1800671c9  lea     r14, dword_1802AFD50
0x1800671d0  add     eax, edi
0x1800671d2  jnz     short loc_1800671EE
0x1800671d4  cmp     rcx, r14
0x1800671d7  jz      short loc_1800671EE
0x1800671d9  cmp     cs:dword_1802B0018, eax
0x1800671df  jz      short loc_1800671E8
0x1800671e1  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800671e6  jmp     short loc_1800671EE
0x1800671e8  call    cs:free
0x1800671ee  test    bl, bl
0x1800671f0  jz      short loc_18006724B
0x1800671f2  mov     rbx, [rsi]
0x1800671f5  call    cs:GetLastError
0x1800671fb  mov     esi, eax
0x1800671fd  mov     ecx, 20h ; ' '; unsigned __int64
0x180067202  cmp     cs:dword_1802B0018, 0
0x180067209  jz      short loc_180067212
0x18006720b  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180067210  jmp     short loc_180067218
0x180067212  call    cs:malloc
0x180067218  mov     [rbp+var_8], rax
0x18006721c  test    rax, rax
0x18006721f  jz      short loc_180067244
0x180067221  and     [rsp+70h+var_48], 0
0x180067227  mov     [rsp+70h+var_50], r15
0x18006722c  mov     r9, rbx
0x18006722f  mov     r8d, esi; int
0x180067232  mov     edx, 20020h; unsigned int
0x180067237  mov     rcx, rax; this
0x18006723a  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x18006723f  mov     rbx, rax
0x180067242  jmp     short loc_180067246
0x180067244  xor     ebx, ebx
0x180067246  jmp     loc_18006736B
0x18006724b  xor     ebx, ebx
0x18006724d  jmp     loc_18006736B
0x180067252  mov     rdx, rbx; char *
0x180067255  lea     rcx, [rbp+lpString]; this
0x180067259  call    ??0Vstring@@QEAA@PEBD@Z; Vstring::Vstring(char const *)
0x18006725e  nop
0x18006725f  cmp     byte ptr [rdi], 0
0x180067262  jnz     short loc_18006726F
0x180067264  xor     edx, edx; unsigned int
0x180067266  lea     rcx, [rbp+lpString]; this
0x18006726a  call    ?convertToLCP@Vstring@@QEAAJI@Z; Vstring::convertToLCP(uint)
0x18006726f  lea     rax, [rbp+var_28]
0x180067273  mov     [rbp+var_8], rax
0x180067277  mov     rax, [rsi]
0x18006727a  mov     [rbp+var_28], rax
0x18006727e  lock inc dword ptr [rax-0Ch]
0x180067282  lea     rdx, [rbp+var_28]
0x180067286  lea     rcx, [rbp+var_18]
0x18006728a  call    sub_180048E50
0x18006728f  nop
0x180067290  mov     r9, [rdi+10h]; lpFileName
0x180067294  mov     r8, [rbp+lpString]; lpString
0x180067298  mov     rdx, [rbp+lpKeyName]; lpKeyName
0x18006729c  mov     rcx, [rax]; lpAppName
0x18006729f  call    cs:WritePrivateProfileStringA
0x1800672a5  test    eax, eax
0x1800672a7  setz    r12b
0x1800672ab  mov     rcx, [rbp+var_18]
0x1800672af  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800672b3  or      edi, 0FFFFFFFFh
0x1800672b6  mov     eax, edi
0x1800672b8  lock xadd [rcx], eax
0x1800672bc  lea     r14, dword_1802AFD50
0x1800672c3  add     eax, edi
0x1800672c5  jnz     short loc_1800672E1
0x1800672c7  cmp     rcx, r14
0x1800672ca  jz      short loc_1800672E1
0x1800672cc  cmp     cs:dword_1802B0018, eax
0x1800672d2  jz      short loc_1800672DB
0x1800672d4  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800672d9  jmp     short loc_1800672E1
0x1800672db  call    cs:free
0x1800672e1  test    r12b, r12b
0x1800672e4  jz      short loc_18006733C
0x1800672e6  mov     rsi, [rsi]
0x1800672e9  call    cs:GetLastError
0x1800672ef  mov     r12d, eax
0x1800672f2  mov     ecx, 20h ; ' '; unsigned __int64
0x1800672f7  cmp     cs:dword_1802B0018, 0
0x1800672fe  jz      short loc_180067307
0x180067300  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180067305  jmp     short loc_18006730D
0x180067307  call    cs:malloc
0x18006730d  mov     [rbp+var_8], rax
0x180067311  test    rax, rax
0x180067314  jz      short loc_180067338
0x180067316  mov     [rsp+70h+var_48], rbx
0x18006731b  mov     [rsp+70h+var_50], r15
0x180067320  mov     r9, rsi
0x180067323  mov     r8d, r12d; int
0x180067326  mov     edx, 20020h; unsigned int
0x18006732b  mov     rcx, rax; this
0x18006732e  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x180067333  mov     rbx, rax
0x180067336  jmp     short loc_18006733A
0x180067338  xor     ebx, ebx
0x18006733a  jmp     short loc_18006733E
0x18006733c  xor     ebx, ebx
0x18006733e  mov     rcx, [rbp+lpString]
0x180067342  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x180067346  mov     eax, edi
0x180067348  lock xadd [rcx], eax
0x18006734c  add     eax, edi
0x18006734e  jnz     short loc_18006736B
0x180067350  cmp     rcx, r14
0x180067353  jz      short loc_18006736B
0x180067355  cmp     cs:dword_1802B0018, eax
0x18006735b  jz      short loc_180067364
0x18006735d  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x180067362  jmp     short loc_18006736B
0x180067364  call    cs:free
0x18006736a  nop
0x18006736b  mov     rcx, [rbp+lpKeyName]
0x18006736f  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x180067373  mov     eax, edi
0x180067375  lock xadd [rcx], eax
0x180067379  add     eax, edi
0x18006737b  jnz     short loc_180067397
0x18006737d  cmp     rcx, r14
0x180067380  jz      short loc_180067397
0x180067382  cmp     cs:dword_1802B0018, eax
0x180067388  jz      short loc_180067391
0x18006738a  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18006738f  jmp     short loc_180067397
0x180067391  call    cs:free
0x180067397  mov     rax, rbx
0x18006739a  lea     r11, [rsp+70h+var_s0]
0x18006739f  mov     rbx, [r11+20h]
0x1800673a3  mov     rsi, [r11+28h]
0x1800673a7  mov     rdi, [r11+30h]
0x1800673ab  mov     r12, [r11+38h]
0x1800673af  mov     rsp, r11
0x1800673b2  pop     r15
0x1800673b4  pop     r14
0x1800673b6  pop     rbp
0x1800673b7  retn
```
