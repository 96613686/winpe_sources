# GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)

- ea: `0x1400128b0`
- end: `0x140012a14`
- name: `?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z`
- size: `356`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, const struct _CERT_CONTEXT **, int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400126d4`

## callees

- `0x1400128b0`
- `0x140012a1c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012901`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400129b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012901`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400129b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140012916`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140012916`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400129cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400129cc`
- `DMCmnUtils!HexStringToBinary` at `0x1400128e8`
- `DMCmnUtils!HexStringToBinary` at `0x140012943`
- `DMCmnUtils!HexStringToBinary` at `0x1400128e8`
- `DMCmnUtils!HexStringToBinary` at `0x140012943`
- `CRYPT32!CertFreeCertificateContext` at `0x1400129f6`
- `CRYPT32!CertFreeCertificateContext` at `0x1400129f6`
- `CRYPT32!CertCloseStore` at `0x1400129e2`
- `CRYPT32!CertCloseStore` at `0x1400129e2`

## pseudocode

```c
__int64 __fastcall GetInstalledCert(
        const unsigned __int16 *a1,
        void **a2,
        const struct _CERT_CONTEXT **a3,
        __int64 a4,
        unsigned int *a5)
{
  unsigned int *v5; // rsi
  const CERT_CONTEXT *v8; // rdi
  signed int InstalledCertHelper; // ebx
  unsigned int v11; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  HANDLE v15; // rax
  PCCERT_CONTEXT v17; // [rsp+30h] [rbp-20h] BYREF
  SIZE_T dwBytes[2]; // [rsp+38h] [rbp-18h] BYREF

  v5 = 0;
  a5 = 0;
  v8 = 0;
  v17 = 0;
  *(_OWORD *)dwBytes = 0;
  InstalledCertHelper = HexStringToBinary(a1, 0, dwBytes, 1);
  if ( InstalledCertHelper >= 0 )
  {
    v11 = dwBytes[0];
    ProcessHeap = GetProcessHeap();
    dwBytes[1] = (SIZE_T)HeapAlloc(ProcessHeap, 8u, v11);
    if ( dwBytes[1] )
    {
      InstalledCertHelper = HexStringToBinary(a1, dwBytes[1], dwBytes, 1);
      if ( InstalledCertHelper >= 0 )
      {
        InstalledCertHelper = GetInstalledCertHelper(v13, 655360, dwBytes, &a5, &v17);
        if ( InstalledCertHelper >= 0
          || (InstalledCertHelper = GetInstalledCertHelper(v14, 0x10000, dwBytes, &a5, &v17), InstalledCertHelper >= 0) )
        {
          *a2 = a5;
          *a3 = v17;
        }
        else
        {
          v5 = a5;
          v8 = v17;
        }
      }
    }
    else
    {
      InstalledCertHelper = -2147024882;
    }
  }
  if ( dwBytes[1] )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, (LPVOID)dwBytes[1]);
  }
  if ( v5 )
    CertCloseStore(v5, 0);
  if ( v8 )
    CertFreeCertificateContext(v8);
  return (unsigned int)InstalledCertHelper;
}

```

## disassembly

```asm
0x1400128b0  push    rbp
0x1400128b2  push    rbx
0x1400128b3  push    rsi
0x1400128b4  push    rdi
0x1400128b5  push    r12
0x1400128b7  push    r14
0x1400128b9  push    r15
0x1400128bb  mov     rbp, rsp
0x1400128be  sub     rsp, 50h
0x1400128c2  xor     esi, esi
0x1400128c4  mov     r15, r8
0x1400128c7  mov     r12, rdx
0x1400128ca  mov     [rbp+arg_20], rsi
0x1400128ce  xorps   xmm0, xmm0
0x1400128d1  lea     r8, [rbp+dwBytes]
0x1400128d5  xor     edi, edi
0x1400128d7  xor     edx, edx
0x1400128d9  lea     r9d, [rsi+1]
0x1400128dd  mov     [rbp+var_20], rdi
0x1400128e1  mov     r14, rcx
0x1400128e4  movups  xmmword ptr [rbp+dwBytes], xmm0
0x1400128e8  call    cs:__imp_HexStringToBinary
0x1400128ef  nop     dword ptr [rax+rax+00h]
0x1400128f4  mov     ebx, eax
0x1400128f6  test    eax, eax
0x1400128f8  js      loc_1400129B0
0x1400128fe  mov     ebx, dword ptr [rbp+dwBytes]
0x140012901  call    cs:__imp_GetProcessHeap
0x140012908  nop     dword ptr [rax+rax+00h]
0x14001290d  mov     r8d, ebx; dwBytes
0x140012910  lea     edx, [rsi+8]; dwFlags
0x140012913  mov     rcx, rax; hHeap
0x140012916  call    cs:__imp_HeapAlloc
0x14001291d  nop     dword ptr [rax+rax+00h]
0x140012922  mov     [rbp+dwBytes+8], rax
0x140012926  test    rax, rax
0x140012929  jnz     short loc_140012932
0x14001292b  mov     ebx, 8007000Eh
0x140012930  jmp     short loc_1400129B0
0x140012932  mov     rdx, [rbp+dwBytes+8]
0x140012936  lea     r8, [rbp+dwBytes]
0x14001293a  mov     r9d, 1
0x140012940  mov     rcx, r14
0x140012943  call    cs:__imp_HexStringToBinary
0x14001294a  nop     dword ptr [rax+rax+00h]
0x14001294f  mov     ebx, eax
0x140012951  test    eax, eax
0x140012953  js      short loc_1400129B0
0x140012955  lea     rax, [rbp+var_20]
0x140012959  mov     edx, 0A0000h
0x14001295e  lea     r9, [rbp+arg_20]
0x140012962  mov     [rsp+50h+var_30], rax
0x140012967  lea     r8, [rbp+dwBytes]
0x14001296b  call    GetInstalledCertHelper
0x140012970  mov     ebx, eax
0x140012972  test    eax, eax
0x140012974  jns     short loc_1400129A1
0x140012976  lea     rax, [rbp+var_20]
0x14001297a  mov     edx, 10000h
0x14001297f  lea     r9, [rbp+arg_20]
0x140012983  mov     [rsp+50h+var_30], rax
0x140012988  lea     r8, [rbp+dwBytes]
0x14001298c  call    GetInstalledCertHelper
0x140012991  mov     ebx, eax
0x140012993  test    eax, eax
0x140012995  jns     short loc_1400129A1
0x140012997  mov     rsi, [rbp+arg_20]
0x14001299b  mov     rdi, [rbp+var_20]
0x14001299f  jmp     short loc_1400129B0
0x1400129a1  mov     rax, [rbp+arg_20]
0x1400129a5  mov     [r12], rax
0x1400129a9  mov     rax, [rbp+var_20]
0x1400129ad  mov     [r15], rax
0x1400129b0  cmp     [rbp+dwBytes+8], 0
0x1400129b5  jz      short loc_1400129D8
0x1400129b7  call    cs:__imp_GetProcessHeap
0x1400129be  nop     dword ptr [rax+rax+00h]
0x1400129c3  mov     r8, [rbp+dwBytes+8]; lpMem
0x1400129c7  xor     edx, edx; dwFlags
0x1400129c9  mov     rcx, rax; hHeap
0x1400129cc  call    cs:__imp_HeapFree
0x1400129d3  nop     dword ptr [rax+rax+00h]
0x1400129d8  test    rsi, rsi
0x1400129db  jz      short loc_1400129EE
0x1400129dd  xor     edx, edx; dwFlags
0x1400129df  mov     rcx, rsi; hCertStore
0x1400129e2  call    cs:__imp_CertCloseStore
0x1400129e9  nop     dword ptr [rax+rax+00h]
0x1400129ee  test    rdi, rdi
0x1400129f1  jz      short loc_140012A02
0x1400129f3  mov     rcx, rdi; pCertContext
0x1400129f6  call    cs:__imp_CertFreeCertificateContext
0x1400129fd  nop     dword ptr [rax+rax+00h]
0x140012a02  mov     eax, ebx
0x140012a04  add     rsp, 50h
0x140012a08  pop     r15
0x140012a0a  pop     r14
0x140012a0c  pop     r12
0x140012a0e  pop     rdi
0x140012a0f  pop     rsi
0x140012a10  pop     rbx
0x140012a11  pop     rbp
0x140012a12  retn
```
