# CDlpRegistrar::~CDlpRegistrar(void)

- ea: `0x14002a46c`
- end: `0x14002a5fd`
- name: `??1CDlpRegistrar@@EEAA@XZ`
- size: `401`
- prototype: `void __fastcall(CDlpRegistrar *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002b400`

## callees

- `0x14002a46c`
- `0x14004dbc4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14002a58a`
- `KERNEL32!DeleteCriticalSection` at `0x14002a5ad`
- `KERNEL32!DeleteCriticalSection` at `0x14002a5d4`
- `KERNEL32!DeleteCriticalSection` at `0x14002a58a`
- `KERNEL32!DeleteCriticalSection` at `0x14002a5ad`
- `KERNEL32!DeleteCriticalSection` at `0x14002a5d4`
- `KERNEL32!HeapFree` at `0x14002a4e9`
- `KERNEL32!HeapFree` at `0x14002a524`
- `KERNEL32!HeapFree` at `0x14002a566`
- `KERNEL32!HeapFree` at `0x14002a4e9`
- `KERNEL32!HeapFree` at `0x14002a524`
- `KERNEL32!HeapFree` at `0x14002a566`
- `KERNEL32!GetProcessHeap` at `0x14002a4d5`
- `KERNEL32!GetProcessHeap` at `0x14002a510`
- `KERNEL32!GetProcessHeap` at `0x14002a552`
- `KERNEL32!GetProcessHeap` at `0x14002a4d5`
- `KERNEL32!GetProcessHeap` at `0x14002a510`
- `KERNEL32!GetProcessHeap` at `0x14002a552`

## pseudocode

```c
void __fastcall CDlpRegistrar::~CDlpRegistrar(CDlpRegistrar *this)
{
  char *v2; // rdi
  void *v3; // rbp
  HANDLE ProcessHeap; // rax
  void *v5; // rsi
  HANDLE v6; // rax
  void *v7; // rsi
  HANDLE v8; // rax

  *(_QWORD *)this = &CDlpRegistrar::`vftable'{for `CUnknownImpl<IDlpRegistrar>'};
  *((_QWORD *)this + 9) = &CDlpFile::`vftable';
  v2 = (char *)this + 256;
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 256, 0);
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 272, 0);
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 272, 0);
  v3 = (void *)*((_QWORD *)this + 35);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
    *((_QWORD *)this + 35) = 0;
  }
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(v2, 0);
  v5 = (void *)*((_QWORD *)v2 + 1);
  if ( v5 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v5);
    *((_QWORD *)v2 + 1) = 0;
  }
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 240, 0);
  v7 = (void *)*((_QWORD *)this + 31);
  if ( v7 )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v7);
    *((_QWORD *)this + 31) = 0;
  }
  if ( *((_DWORD *)this + 58) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
    *((_DWORD *)this + 58) = 0;
  }
  if ( *((_DWORD *)this + 44) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
    *((_DWORD *)this + 44) = 0;
  }
  *(_QWORD *)this = &CUnknownImpl<IDlpRegistrar>::`vftable';
  if ( *((_DWORD *)this + 16) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *((_DWORD *)this + 16) = 0;
  }
}

```

## disassembly

```asm
0x14002a46c  mov     rax, rsp
0x14002a46f  push    rdi
0x14002a470  sub     rsp, 30h
0x14002a474  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x14002a47c  mov     [rax+8], rbx
0x14002a480  mov     [rax+10h], rbp
0x14002a484  mov     [rax+18h], rsi
0x14002a488  mov     rbx, rcx
0x14002a48b  lea     rax, ??_7CDlpRegistrar@@6B?$CUnknownImpl@VIDlpRegistrar@@@@@; const CDlpRegistrar::`vftable'{for `CUnknownImpl<IDlpRegistrar>'}
0x14002a492  mov     [rcx], rax
0x14002a495  lea     rax, ??_7CDlpFile@@6B@; const CDlpFile::`vftable'
0x14002a49c  mov     [rcx+48h], rax
0x14002a4a0  lea     rdi, [rcx+100h]
0x14002a4a7  xor     edx, edx
0x14002a4a9  mov     rcx, rdi
0x14002a4ac  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x14002a4b1  lea     rsi, [rbx+110h]
0x14002a4b8  xor     edx, edx
0x14002a4ba  mov     rcx, rsi
0x14002a4bd  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x14002a4c2  xor     edx, edx
0x14002a4c4  mov     rcx, rsi
0x14002a4c7  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x14002a4cc  mov     rbp, [rsi+8]
0x14002a4d0  test    rbp, rbp
0x14002a4d3  jz      short loc_14002A4FD
0x14002a4d5  call    cs:__imp_GetProcessHeap
0x14002a4dc  nop     dword ptr [rax+rax+00h]
0x14002a4e1  mov     rcx, rax; hHeap
0x14002a4e4  mov     r8, rbp; lpMem
0x14002a4e7  xor     edx, edx; dwFlags
0x14002a4e9  call    cs:__imp_HeapFree
0x14002a4f0  nop     dword ptr [rax+rax+00h]
0x14002a4f5  mov     qword ptr [rsi+8], 0
0x14002a4fd  xor     edx, edx
0x14002a4ff  mov     rcx, rdi
0x14002a502  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x14002a507  mov     rsi, [rdi+8]
0x14002a50b  test    rsi, rsi
0x14002a50e  jz      short loc_14002A538
0x14002a510  call    cs:__imp_GetProcessHeap
0x14002a517  nop     dword ptr [rax+rax+00h]
0x14002a51c  mov     rcx, rax; hHeap
0x14002a51f  mov     r8, rsi; lpMem
0x14002a522  xor     edx, edx; dwFlags
0x14002a524  call    cs:__imp_HeapFree
0x14002a52b  nop     dword ptr [rax+rax+00h]
0x14002a530  mov     qword ptr [rdi+8], 0
0x14002a538  lea     rdi, [rbx+0F0h]
0x14002a53f  xor     edx, edx
0x14002a541  mov     rcx, rdi
0x14002a544  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x14002a549  mov     rsi, [rdi+8]
0x14002a54d  test    rsi, rsi
0x14002a550  jz      short loc_14002A57A
0x14002a552  call    cs:__imp_GetProcessHeap
0x14002a559  nop     dword ptr [rax+rax+00h]
0x14002a55e  mov     rcx, rax; hHeap
0x14002a561  mov     r8, rsi; lpMem
0x14002a564  xor     edx, edx; dwFlags
0x14002a566  call    cs:__imp_HeapFree
0x14002a56d  nop     dword ptr [rax+rax+00h]
0x14002a572  mov     qword ptr [rdi+8], 0
0x14002a57a  lea     rdi, [rbx+0C0h]
0x14002a581  cmp     dword ptr [rdi+28h], 0
0x14002a585  jz      short loc_14002A59D
0x14002a587  mov     rcx, rdi; lpCriticalSection
0x14002a58a  call    cs:__imp_DeleteCriticalSection
0x14002a591  nop     dword ptr [rax+rax+00h]
0x14002a596  mov     dword ptr [rdi+28h], 0
0x14002a59d  lea     rdi, [rbx+88h]
0x14002a5a4  cmp     dword ptr [rdi+28h], 0
0x14002a5a8  jz      short loc_14002A5C0
0x14002a5aa  mov     rcx, rdi; lpCriticalSection
0x14002a5ad  call    cs:__imp_DeleteCriticalSection
0x14002a5b4  nop     dword ptr [rax+rax+00h]
0x14002a5b9  mov     dword ptr [rdi+28h], 0
0x14002a5c0  lea     rax, ??_7?$CUnknownImpl@VIDlpRegistrar@@@@6B@; const CUnknownImpl<IDlpRegistrar>::`vftable'
0x14002a5c7  mov     [rbx], rax
0x14002a5ca  cmp     dword ptr [rbx+40h], 0
0x14002a5ce  jz      short loc_14002A5E7
0x14002a5d0  lea     rcx, [rbx+18h]; lpCriticalSection
0x14002a5d4  call    cs:__imp_DeleteCriticalSection
0x14002a5db  nop     dword ptr [rax+rax+00h]
0x14002a5e0  mov     dword ptr [rbx+40h], 0
0x14002a5e7  mov     rbx, [rsp+38h+arg_0]
0x14002a5ec  mov     rbp, [rsp+38h+arg_8]
0x14002a5f1  mov     rsi, [rsp+38h+arg_10]
0x14002a5f6  add     rsp, 30h
0x14002a5fa  pop     rdi
0x14002a5fb  retn
```
