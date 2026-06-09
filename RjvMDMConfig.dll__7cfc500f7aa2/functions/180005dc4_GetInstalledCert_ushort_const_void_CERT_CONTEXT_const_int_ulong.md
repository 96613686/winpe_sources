# GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)

- ea: `0x180005dc4`
- end: `0x180005f10`
- name: `?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z`
- size: `332`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, const struct _CERT_CONTEXT **, int, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800039fc`
- `0x180005bfc`

## callees

- `0x180005dc4`
- `0x180005f18`
- `0x180016e78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005ec8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005ec8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005e1f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005e1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005eb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005eb3`
- `CRYPT32!CertFreeCertificateContext` at `0x180005ef2`
- `CRYPT32!CertFreeCertificateContext` at `0x180005ef2`
- `CRYPT32!CertCloseStore` at `0x180005ede`
- `CRYPT32!CertCloseStore` at `0x180005ede`

## pseudocode

```c
__int64 __fastcall GetInstalledCert(
        const unsigned __int16 *a1,
        void **a2,
        const struct _CERT_CONTEXT **a3,
        __int64 a4,
        unsigned int *a5)
{
  unsigned int *v7; // rsi
  const CERT_CONTEXT *v8; // rdi
  signed int InstalledCertHelper; // ebx
  unsigned int v11; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  HANDLE v15; // rax
  PCCERT_CONTEXT v17; // [rsp+30h] [rbp-20h] BYREF
  SIZE_T dwBytes[2]; // [rsp+38h] [rbp-18h] BYREF

  v7 = 0;
  v8 = 0;
  a5 = 0;
  v17 = 0;
  *(_OWORD *)dwBytes = 0;
  InstalledCertHelper = HexStringToBinary(a1, 0, dwBytes);
  if ( InstalledCertHelper >= 0 )
  {
    v11 = dwBytes[0];
    ProcessHeap = GetProcessHeap();
    dwBytes[1] = (SIZE_T)HeapAlloc(ProcessHeap, 8u, v11);
    if ( dwBytes[1] )
    {
      InstalledCertHelper = HexStringToBinary(a1, dwBytes[1], dwBytes);
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
          v7 = a5;
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
  if ( v7 )
    CertCloseStore(v7, 0);
  if ( v8 )
    CertFreeCertificateContext(v8);
  return (unsigned int)InstalledCertHelper;
}

```

## disassembly

```asm
0x180005dc4  push    rbp
0x180005dc6  push    rbx
0x180005dc7  push    rsi
0x180005dc8  push    rdi
0x180005dc9  push    r12
0x180005dcb  push    r14
0x180005dcd  push    r15
0x180005dcf  mov     rbp, rsp
0x180005dd2  sub     rsp, 50h
0x180005dd6  mov     r15, r8
0x180005dd9  mov     r12, rdx
0x180005ddc  xorps   xmm0, xmm0
0x180005ddf  lea     r8, [rbp+dwBytes]
0x180005de3  xor     esi, esi
0x180005de5  xor     edi, edi
0x180005de7  xor     edx, edx
0x180005de9  mov     [rbp+arg_20], rsi
0x180005ded  mov     [rbp+var_20], rdi
0x180005df1  mov     r14, rcx
0x180005df4  movups  xmmword ptr [rbp+dwBytes], xmm0
0x180005df8  call    HexStringToBinary
0x180005dfd  mov     ebx, eax
0x180005dff  test    eax, eax
0x180005e01  js      loc_180005EAC
0x180005e07  mov     ebx, dword ptr [rbp+dwBytes]
0x180005e0a  call    cs:__imp_GetProcessHeap
0x180005e11  nop     dword ptr [rax+rax+00h]
0x180005e16  mov     r8d, ebx; dwBytes
0x180005e19  lea     edx, [rsi+8]; dwFlags
0x180005e1c  mov     rcx, rax; hHeap
0x180005e1f  call    cs:__imp_HeapAlloc
0x180005e26  nop     dword ptr [rax+rax+00h]
0x180005e2b  mov     [rbp+dwBytes+8], rax
0x180005e2f  test    rax, rax
0x180005e32  jnz     short loc_180005E3B
0x180005e34  mov     ebx, 8007000Eh
0x180005e39  jmp     short loc_180005EAC
0x180005e3b  mov     rdx, [rbp+dwBytes+8]
0x180005e3f  lea     r8, [rbp+dwBytes]
0x180005e43  mov     rcx, r14
0x180005e46  call    HexStringToBinary
0x180005e4b  mov     ebx, eax
0x180005e4d  test    eax, eax
0x180005e4f  js      short loc_180005EAC
0x180005e51  lea     rax, [rbp+var_20]
0x180005e55  mov     edx, 0A0000h
0x180005e5a  lea     r9, [rbp+arg_20]
0x180005e5e  mov     [rsp+50h+var_30], rax
0x180005e63  lea     r8, [rbp+dwBytes]
0x180005e67  call    GetInstalledCertHelper
0x180005e6c  mov     ebx, eax
0x180005e6e  test    eax, eax
0x180005e70  jns     short loc_180005E9D
0x180005e72  lea     rax, [rbp+var_20]
0x180005e76  mov     edx, 10000h
0x180005e7b  lea     r9, [rbp+arg_20]
0x180005e7f  mov     [rsp+50h+var_30], rax
0x180005e84  lea     r8, [rbp+dwBytes]
0x180005e88  call    GetInstalledCertHelper
0x180005e8d  mov     ebx, eax
0x180005e8f  test    eax, eax
0x180005e91  jns     short loc_180005E9D
0x180005e93  mov     rsi, [rbp+arg_20]
0x180005e97  mov     rdi, [rbp+var_20]
0x180005e9b  jmp     short loc_180005EAC
0x180005e9d  mov     rax, [rbp+arg_20]
0x180005ea1  mov     [r12], rax
0x180005ea5  mov     rax, [rbp+var_20]
0x180005ea9  mov     [r15], rax
0x180005eac  cmp     [rbp+dwBytes+8], 0
0x180005eb1  jz      short loc_180005ED4
0x180005eb3  call    cs:__imp_GetProcessHeap
0x180005eba  nop     dword ptr [rax+rax+00h]
0x180005ebf  mov     r8, [rbp+dwBytes+8]; lpMem
0x180005ec3  xor     edx, edx; dwFlags
0x180005ec5  mov     rcx, rax; hHeap
0x180005ec8  call    cs:__imp_HeapFree
0x180005ecf  nop     dword ptr [rax+rax+00h]
0x180005ed4  test    rsi, rsi
0x180005ed7  jz      short loc_180005EEA
0x180005ed9  xor     edx, edx; dwFlags
0x180005edb  mov     rcx, rsi; hCertStore
0x180005ede  call    cs:__imp_CertCloseStore
0x180005ee5  nop     dword ptr [rax+rax+00h]
0x180005eea  test    rdi, rdi
0x180005eed  jz      short loc_180005EFE
0x180005eef  mov     rcx, rdi; pCertContext
0x180005ef2  call    cs:__imp_CertFreeCertificateContext
0x180005ef9  nop     dword ptr [rax+rax+00h]
0x180005efe  mov     eax, ebx
0x180005f00  add     rsp, 50h
0x180005f04  pop     r15
0x180005f06  pop     r14
0x180005f08  pop     r12
0x180005f0a  pop     rdi
0x180005f0b  pop     rsi
0x180005f0c  pop     rbx
0x180005f0d  pop     rbp
0x180005f0e  retn
```
