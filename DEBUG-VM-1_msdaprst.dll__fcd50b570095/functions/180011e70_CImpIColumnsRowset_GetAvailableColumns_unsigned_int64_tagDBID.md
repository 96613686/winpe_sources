# CImpIColumnsRowset::GetAvailableColumns(unsigned __int64 *,tagDBID * *)

- ea: `0x180011e70`
- end: `0x180011f7c`
- name: `?GetAvailableColumns@CImpIColumnsRowset@@UEAAJPEA_KPEAPEAUtagDBID@@@Z`
- size: `268`
- prototype: `__int64 __fastcall(CImpIColumnsRowset *__hidden this, unsigned __int64 *, struct tagDBID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180011e70`
- `0x180015fb4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180011e9b`
- `KERNEL32!GetCurrentThreadId` at `0x180011e9b`
- `KERNEL32!LeaveCriticalSection` at `0x180011f3b`
- `KERNEL32!LeaveCriticalSection` at `0x180011f6a`
- `KERNEL32!LeaveCriticalSection` at `0x180011f3b`
- `KERNEL32!LeaveCriticalSection` at `0x180011f6a`
- `ole32!CoTaskMemAlloc` at `0x180011ed2`
- `ole32!CoTaskMemAlloc` at `0x180011ed2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180011eb2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180011eb2`
- `MSDART!UMSEnterCSWraper` at `0x180011e8b`
- `MSDART!UMSEnterCSWraper` at `0x180011e8b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIColumnsRowset::GetAvailableColumns(
        CImpIColumnsRowset *this,
        unsigned __int64 *a2,
        struct tagDBID **a3)
{
  __int64 v5; // rbx
  DWORD *v6; // rdi
  struct tagDBID *v7; // rax
  int v8; // ecx
  __int64 i; // r8
  __int64 v10; // rcx
  __int64 v11; // rax
  bool v12; // zf
  __int64 v13; // rcx
  unsigned int v15; // esi
  __int64 v16; // rcx

  v5 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v5);
  v6 = (DWORD *)(v5 + 8);
  if ( !*(_DWORD *)(v5 + 12) )
    *v6 = GetCurrentThreadId();
  ++*(_DWORD *)(v5 + 12);
  ++*(_DWORD *)(v5 + 16);
  SetErrorInfo(0, 0);
  if ( !a2 || !a3 )
  {
    v8 = -2147024809;
    goto LABEL_13;
  }
  *a2 = 31;
  v7 = (struct tagDBID *)CoTaskMemAlloc(0x3E0u);
  *a3 = v7;
  if ( !v7 )
  {
    v8 = -2147024882;
LABEL_13:
    v15 = Exit(v8, 0);
    --*(_DWORD *)(v5 + 16);
    v12 = (*(_DWORD *)(v5 + 12))-- == 1;
    if ( v12 )
      *v6 = -1;
    v16 = *(_QWORD *)v5;
    --*(_DWORD *)(v16 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 8));
    return v15;
  }
  for ( i = 11; i != 31; ++i )
  {
    v10 = 32 * i;
    v11 = (__int64)*a3;
    *(_OWORD *)(v10 + v11) = *((_OWORD *)&g_rgDesiredColumn + 5 * i);
    *(_OWORD *)(v10 + v11 + 16) = *((_OWORD *)&g_rgDesiredColumn + 5 * i + 1);
  }
  --*(_DWORD *)(v5 + 16);
  v12 = (*(_DWORD *)(v5 + 12))-- == 1;
  if ( v12 )
    *v6 = -1;
  v13 = *(_QWORD *)v5;
  --*(_DWORD *)(v13 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
  return 0;
}

```

## disassembly

```asm
0x180011e70  push    rbx
0x180011e72  push    rsi
0x180011e73  push    rdi
0x180011e74  push    r14
0x180011e76  sub     rsp, 28h
0x180011e7a  mov     rsi, r8
0x180011e7d  mov     r14, rdx
0x180011e80  mov     rbx, [rcx+18h]
0x180011e84  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180011e88  mov     rcx, rbx
0x180011e8b  call    cs:__imp_UMSEnterCSWraper
0x180011e91  lea     rdi, [rbx+8]
0x180011e95  cmp     dword ptr [rbx+0Ch], 0
0x180011e99  jnz     short loc_180011EA3
0x180011e9b  call    cs:__imp_GetCurrentThreadId
0x180011ea1  mov     [rdi], eax
0x180011ea3  inc     dword ptr [rbx+0Ch]
0x180011ea6  inc     dword ptr [rbx+10h]
0x180011ea9  mov     [rsp+48h+arg_0], rbx
0x180011eae  xor     edx, edx; perrinfo
0x180011eb0  xor     ecx, ecx; dwReserved
0x180011eb2  call    cs:__imp_SetErrorInfo
0x180011eb8  test    r14, r14
0x180011ebb  jz      loc_180011F45
0x180011ec1  test    rsi, rsi
0x180011ec4  jz      short loc_180011F45
0x180011ec6  mov     qword ptr [r14], 1Fh
0x180011ecd  mov     ecx, 3E0h; cb
0x180011ed2  call    cs:__imp_CoTaskMemAlloc
0x180011ed8  mov     [rsi], rax
0x180011edb  test    rax, rax
0x180011ede  jnz     short loc_180011EE7
0x180011ee0  mov     ecx, 8007000Eh
0x180011ee5  jmp     short loc_180011F4A
0x180011ee7  mov     r8d, 0Bh
0x180011eed  lea     rdx, [r8+r8*4]
0x180011ef1  add     rdx, rdx
0x180011ef4  lea     r9, ?g_rgDesiredColumn@@3QBUtagDESIREDCOLUMNS@@B; tagDESIREDCOLUMNS const near * const g_rgDesiredColumn
0x180011efb  mov     rcx, r8
0x180011efe  shl     rcx, 5
0x180011f02  mov     rax, [rsi]
0x180011f05  movups  xmm0, xmmword ptr [r9+rdx*8]
0x180011f0a  movups  xmmword ptr [rcx+rax], xmm0
0x180011f0e  movups  xmm1, xmmword ptr [r9+rdx*8+10h]
0x180011f14  movups  xmmword ptr [rcx+rax+10h], xmm1
0x180011f19  inc     r8
0x180011f1c  cmp     r8, 1Fh
0x180011f20  jnz     short loc_180011EED
0x180011f22  dec     dword ptr [rbx+10h]
0x180011f25  sub     dword ptr [rbx+0Ch], 1
0x180011f29  jnz     short loc_180011F31
0x180011f2b  mov     dword ptr [rdi], 0FFFFFFFFh
0x180011f31  mov     rcx, [rbx]
0x180011f34  dec     dword ptr [rcx+30h]
0x180011f37  add     rcx, 8; lpCriticalSection
0x180011f3b  call    cs:__imp_LeaveCriticalSection
0x180011f41  xor     eax, eax
0x180011f43  jmp     short loc_180011F72
0x180011f45  mov     ecx, 80070057h; int
0x180011f4a  xor     edx, edx; unsigned int
0x180011f4c  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180011f51  mov     esi, eax
0x180011f53  or      edx, 0FFFFFFFFh
0x180011f56  add     [rbx+10h], edx
0x180011f59  add     [rbx+0Ch], edx
0x180011f5c  jnz     short loc_180011F60
0x180011f5e  mov     [rdi], edx
0x180011f60  mov     rcx, [rbx]
0x180011f63  dec     dword ptr [rcx+30h]
0x180011f66  add     rcx, 8; lpCriticalSection
0x180011f6a  call    cs:__imp_LeaveCriticalSection
0x180011f70  mov     eax, esi
0x180011f72  add     rsp, 28h
0x180011f76  pop     r14
0x180011f78  pop     rdi
0x180011f79  pop     rsi
0x180011f7a  pop     rbx
0x180011f7b  retn
```
