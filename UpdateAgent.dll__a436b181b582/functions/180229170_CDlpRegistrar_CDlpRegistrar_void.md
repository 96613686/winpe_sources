# CDlpRegistrar::~CDlpRegistrar(void)

- ea: `0x180229170`
- end: `0x1802292e2`
- name: `??1CDlpRegistrar@@EEAA@XZ`
- size: `370`
- prototype: `void __fastcall(CDlpRegistrar *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18022a1b0`

## callees

- `0x180229170`
- `0x18024d68c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18022927b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18022929e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1802292c5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18022927b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18022929e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1802292c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802291c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180229201`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180229243`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802291c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180229201`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180229243`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802291da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180229215`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180229257`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802291da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180229215`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180229257`

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
  v2 = (char *)this + 256;
  *((_QWORD *)this + 9) = &CDlpFile::`vftable';
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
0x180229170  push    rbx
0x180229172  push    rbp
0x180229173  push    rsi
0x180229174  push    rdi
0x180229175  sub     rsp, 28h
0x180229179  lea     rax, ??_7CDlpRegistrar@@6B?$CUnknownImpl@VIDlpRegistrar@@@@@; const CDlpRegistrar::`vftable'{for `CUnknownImpl<IDlpRegistrar>'}
0x180229180  mov     rbx, rcx
0x180229183  mov     [rcx], rax
0x180229186  lea     rdi, [rcx+100h]
0x18022918d  lea     rax, ??_7CDlpFile@@6B@; const CDlpFile::`vftable'
0x180229194  xor     edx, edx
0x180229196  mov     [rcx+48h], rax
0x18022919a  mov     rcx, rdi
0x18022919d  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x1802291a2  lea     rsi, [rbx+110h]
0x1802291a9  xor     edx, edx
0x1802291ab  mov     rcx, rsi
0x1802291ae  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x1802291b3  xor     edx, edx
0x1802291b5  mov     rcx, rsi
0x1802291b8  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x1802291bd  mov     rbp, [rsi+8]
0x1802291c1  test    rbp, rbp
0x1802291c4  jz      short loc_1802291EE
0x1802291c6  call    cs:__imp_GetProcessHeap
0x1802291cd  nop     dword ptr [rax+rax+00h]
0x1802291d2  mov     r8, rbp; lpMem
0x1802291d5  xor     edx, edx; dwFlags
0x1802291d7  mov     rcx, rax; hHeap
0x1802291da  call    cs:__imp_HeapFree
0x1802291e1  nop     dword ptr [rax+rax+00h]
0x1802291e6  mov     qword ptr [rsi+8], 0
0x1802291ee  xor     edx, edx
0x1802291f0  mov     rcx, rdi
0x1802291f3  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x1802291f8  mov     rsi, [rdi+8]
0x1802291fc  test    rsi, rsi
0x1802291ff  jz      short loc_180229229
0x180229201  call    cs:__imp_GetProcessHeap
0x180229208  nop     dword ptr [rax+rax+00h]
0x18022920d  mov     r8, rsi; lpMem
0x180229210  xor     edx, edx; dwFlags
0x180229212  mov     rcx, rax; hHeap
0x180229215  call    cs:__imp_HeapFree
0x18022921c  nop     dword ptr [rax+rax+00h]
0x180229221  mov     qword ptr [rdi+8], 0
0x180229229  lea     rdi, [rbx+0F0h]
0x180229230  xor     edx, edx
0x180229232  mov     rcx, rdi
0x180229235  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18022923a  mov     rsi, [rdi+8]
0x18022923e  test    rsi, rsi
0x180229241  jz      short loc_18022926B
0x180229243  call    cs:__imp_GetProcessHeap
0x18022924a  nop     dword ptr [rax+rax+00h]
0x18022924f  mov     r8, rsi; lpMem
0x180229252  xor     edx, edx; dwFlags
0x180229254  mov     rcx, rax; hHeap
0x180229257  call    cs:__imp_HeapFree
0x18022925e  nop     dword ptr [rax+rax+00h]
0x180229263  mov     qword ptr [rdi+8], 0
0x18022926b  lea     rdi, [rbx+0C0h]
0x180229272  cmp     dword ptr [rdi+28h], 0
0x180229276  jz      short loc_18022928E
0x180229278  mov     rcx, rdi; lpCriticalSection
0x18022927b  call    cs:__imp_DeleteCriticalSection
0x180229282  nop     dword ptr [rax+rax+00h]
0x180229287  mov     dword ptr [rdi+28h], 0
0x18022928e  lea     rdi, [rbx+88h]
0x180229295  cmp     dword ptr [rdi+28h], 0
0x180229299  jz      short loc_1802292B1
0x18022929b  mov     rcx, rdi; lpCriticalSection
0x18022929e  call    cs:__imp_DeleteCriticalSection
0x1802292a5  nop     dword ptr [rax+rax+00h]
0x1802292aa  mov     dword ptr [rdi+28h], 0
0x1802292b1  lea     rax, ??_7?$CUnknownImpl@VIDlpRegistrar@@@@6B@; const CUnknownImpl<IDlpRegistrar>::`vftable'
0x1802292b8  mov     [rbx], rax
0x1802292bb  cmp     dword ptr [rbx+40h], 0
0x1802292bf  jz      short loc_1802292D8
0x1802292c1  lea     rcx, [rbx+18h]; lpCriticalSection
0x1802292c5  call    cs:__imp_DeleteCriticalSection
0x1802292cc  nop     dword ptr [rax+rax+00h]
0x1802292d1  mov     dword ptr [rbx+40h], 0
0x1802292d8  add     rsp, 28h
0x1802292dc  pop     rdi
0x1802292dd  pop     rsi
0x1802292de  pop     rbp
0x1802292df  pop     rbx
0x1802292e0  retn
```
