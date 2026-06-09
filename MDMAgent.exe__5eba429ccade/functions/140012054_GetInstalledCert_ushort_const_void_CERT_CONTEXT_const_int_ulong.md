# GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)

- ea: `0x140012054`
- end: `0x140012187`
- name: `?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z`
- size: `307`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, const struct _CERT_CONTEXT **, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140011eb4`

## callees

- `0x140012054`
- `0x140012190`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001209f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012143`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001209f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012143`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400120ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400120ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012152`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012152`
- `DMCmnUtils!HexStringToBinary` at `0x14001208c`
- `DMCmnUtils!HexStringToBinary` at `0x1400120d5`
- `DMCmnUtils!HexStringToBinary` at `0x14001208c`
- `DMCmnUtils!HexStringToBinary` at `0x1400120d5`
- `CRYPT32!CertFreeCertificateContext` at `0x140012170`
- `CRYPT32!CertFreeCertificateContext` at `0x140012170`
- `CRYPT32!CertCloseStore` at `0x140012162`
- `CRYPT32!CertCloseStore` at `0x140012162`

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
  int InstalledCertHelper; // ebx
  unsigned int v11; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  HANDLE v15; // rax
  const struct _CERT_CONTEXT *v17; // [rsp+30h] [rbp-20h] BYREF
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
0x140012054  push    rbp
0x140012056  push    rbx
0x140012057  push    rsi
0x140012058  push    rdi
0x140012059  push    r12
0x14001205b  push    r14
0x14001205d  push    r15
0x14001205f  mov     rbp, rsp
0x140012062  sub     rsp, 50h
0x140012066  xor     esi, esi
0x140012068  mov     r15, r8
0x14001206b  mov     r12, rdx
0x14001206e  mov     [rbp+arg_20], rsi
0x140012072  xorps   xmm0, xmm0
0x140012075  lea     r8, [rbp+dwBytes]
0x140012079  xor     edi, edi
0x14001207b  xor     edx, edx
0x14001207d  lea     r9d, [rsi+1]
0x140012081  mov     [rbp+var_20], rdi
0x140012085  mov     r14, rcx
0x140012088  movups  xmmword ptr [rbp+dwBytes], xmm0
0x14001208c  call    cs:__imp_HexStringToBinary
0x140012092  mov     ebx, eax
0x140012094  test    eax, eax
0x140012096  js      loc_14001213C
0x14001209c  mov     ebx, dword ptr [rbp+dwBytes]
0x14001209f  call    cs:__imp_GetProcessHeap
0x1400120a5  mov     r8d, ebx; dwBytes
0x1400120a8  lea     edx, [rsi+8]; dwFlags
0x1400120ab  mov     rcx, rax; hHeap
0x1400120ae  call    cs:__imp_HeapAlloc
0x1400120b4  mov     [rbp+dwBytes+8], rax
0x1400120b8  test    rax, rax
0x1400120bb  jnz     short loc_1400120C4
0x1400120bd  mov     ebx, 8007000Eh
0x1400120c2  jmp     short loc_14001213C
0x1400120c4  mov     rdx, [rbp+dwBytes+8]
0x1400120c8  lea     r8, [rbp+dwBytes]
0x1400120cc  mov     r9d, 1
0x1400120d2  mov     rcx, r14
0x1400120d5  call    cs:__imp_HexStringToBinary
0x1400120db  mov     ebx, eax
0x1400120dd  test    eax, eax
0x1400120df  js      short loc_14001213C
0x1400120e1  lea     rax, [rbp+var_20]
0x1400120e5  mov     edx, 0A0000h
0x1400120ea  lea     r9, [rbp+arg_20]
0x1400120ee  mov     [rsp+50h+var_30], rax
0x1400120f3  lea     r8, [rbp+dwBytes]
0x1400120f7  call    GetInstalledCertHelper
0x1400120fc  mov     ebx, eax
0x1400120fe  test    eax, eax
0x140012100  jns     short loc_14001212D
0x140012102  lea     rax, [rbp+var_20]
0x140012106  mov     edx, 10000h
0x14001210b  lea     r9, [rbp+arg_20]
0x14001210f  mov     [rsp+50h+var_30], rax
0x140012114  lea     r8, [rbp+dwBytes]
0x140012118  call    GetInstalledCertHelper
0x14001211d  mov     ebx, eax
0x14001211f  test    eax, eax
0x140012121  jns     short loc_14001212D
0x140012123  mov     rsi, [rbp+arg_20]
0x140012127  mov     rdi, [rbp+var_20]
0x14001212b  jmp     short loc_14001213C
0x14001212d  mov     rax, [rbp+arg_20]
0x140012131  mov     [r12], rax
0x140012135  mov     rax, [rbp+var_20]
0x140012139  mov     [r15], rax
0x14001213c  cmp     [rbp+dwBytes+8], 0
0x140012141  jz      short loc_140012158
0x140012143  call    cs:__imp_GetProcessHeap
0x140012149  mov     r8, [rbp+dwBytes+8]; lpMem
0x14001214d  xor     edx, edx; dwFlags
0x14001214f  mov     rcx, rax; hHeap
0x140012152  call    cs:__imp_HeapFree
0x140012158  test    rsi, rsi
0x14001215b  jz      short loc_140012168
0x14001215d  xor     edx, edx; dwFlags
0x14001215f  mov     rcx, rsi; hCertStore
0x140012162  call    cs:__imp_CertCloseStore
0x140012168  test    rdi, rdi
0x14001216b  jz      short loc_140012176
0x14001216d  mov     rcx, rdi; pCertContext
0x140012170  call    cs:__imp_CertFreeCertificateContext
0x140012176  mov     eax, ebx
0x140012178  add     rsp, 50h
0x14001217c  pop     r15
0x14001217e  pop     r14
0x140012180  pop     r12
0x140012182  pop     rdi
0x140012183  pop     rsi
0x140012184  pop     rbx
0x140012185  pop     rbp
0x140012186  retn
```
