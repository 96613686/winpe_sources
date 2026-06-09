# CDlpActionInterfaceCollection::~CDlpActionInterfaceCollection(void)

- ea: `0x140029ca8`
- end: `0x140029d7a`
- name: `??1CDlpActionInterfaceCollection@@UEAA@XZ`
- size: `210`
- prototype: `void __fastcall(CDlpActionInterfaceCollection *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002b310`

## callees

- `0x140029ca8`
- `0x14004dbc4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140029d56`
- `KERNEL32!DeleteCriticalSection` at `0x140029d56`
- `KERNEL32!HeapFree` at `0x140029cf2`
- `KERNEL32!HeapFree` at `0x140029d2e`
- `KERNEL32!HeapFree` at `0x140029cf2`
- `KERNEL32!HeapFree` at `0x140029d2e`
- `KERNEL32!GetProcessHeap` at `0x140029cde`
- `KERNEL32!GetProcessHeap` at `0x140029d1a`
- `KERNEL32!GetProcessHeap` at `0x140029cde`
- `KERNEL32!GetProcessHeap` at `0x140029d1a`

## pseudocode

```c
void __fastcall CDlpActionInterfaceCollection::~CDlpActionInterfaceCollection(CDlpActionInterfaceCollection *this)
{
  char *v2; // rdi
  void *v3; // rsi
  HANDLE ProcessHeap; // rax
  void *v5; // rsi
  HANDLE v6; // rax

  v2 = (char *)this + 128;
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 128, 0);
  v3 = (void *)*((_QWORD *)v2 + 1);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
    *((_QWORD *)v2 + 1) = 0;
  }
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 112, 0);
  v5 = (void *)*((_QWORD *)this + 15);
  if ( v5 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v5);
    *((_QWORD *)this + 15) = 0;
  }
  *(_QWORD *)this = &CUnknownImpl<IDlpActionInterfaceCollection>::`vftable';
  if ( *((_DWORD *)this + 16) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *((_DWORD *)this + 16) = 0;
  }
}

```

## disassembly

```asm
0x140029ca8  push    rdi
0x140029caa  sub     rsp, 30h
0x140029cae  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140029cb7  mov     [rsp+38h+arg_0], rbx
0x140029cbc  mov     [rsp+38h+arg_8], rsi
0x140029cc1  mov     rbx, rcx
0x140029cc4  lea     rdi, [rcx+80h]
0x140029ccb  xor     edx, edx
0x140029ccd  mov     rcx, rdi
0x140029cd0  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x140029cd5  mov     rsi, [rdi+8]
0x140029cd9  test    rsi, rsi
0x140029cdc  jz      short loc_140029D06
0x140029cde  call    cs:__imp_GetProcessHeap
0x140029ce5  nop     dword ptr [rax+rax+00h]
0x140029cea  mov     rcx, rax; hHeap
0x140029ced  mov     r8, rsi; lpMem
0x140029cf0  xor     edx, edx; dwFlags
0x140029cf2  call    cs:__imp_HeapFree
0x140029cf9  nop     dword ptr [rax+rax+00h]
0x140029cfe  mov     qword ptr [rdi+8], 0
0x140029d06  xor     edx, edx
0x140029d08  lea     rcx, [rbx+70h]
0x140029d0c  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x140029d11  mov     rsi, [rbx+78h]
0x140029d15  test    rsi, rsi
0x140029d18  jz      short loc_140029D42
0x140029d1a  call    cs:__imp_GetProcessHeap
0x140029d21  nop     dword ptr [rax+rax+00h]
0x140029d26  mov     rcx, rax; hHeap
0x140029d29  mov     r8, rsi; lpMem
0x140029d2c  xor     edx, edx; dwFlags
0x140029d2e  call    cs:__imp_HeapFree
0x140029d35  nop     dword ptr [rax+rax+00h]
0x140029d3a  mov     qword ptr [rbx+78h], 0
0x140029d42  lea     rax, ??_7?$CUnknownImpl@VIDlpActionInterfaceCollection@@@@6B@; const CUnknownImpl<IDlpActionInterfaceCollection>::`vftable'
0x140029d49  mov     [rbx], rax
0x140029d4c  cmp     dword ptr [rbx+40h], 0
0x140029d50  jz      short loc_140029D69
0x140029d52  lea     rcx, [rbx+18h]; lpCriticalSection
0x140029d56  call    cs:__imp_DeleteCriticalSection
0x140029d5d  nop     dword ptr [rax+rax+00h]
0x140029d62  mov     dword ptr [rbx+40h], 0
0x140029d69  mov     rbx, [rsp+38h+arg_0]
0x140029d6e  mov     rsi, [rsp+38h+arg_8]
0x140029d73  add     rsp, 30h
0x140029d77  pop     rdi
0x140029d78  retn
```
