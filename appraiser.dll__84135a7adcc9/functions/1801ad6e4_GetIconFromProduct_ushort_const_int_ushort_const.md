# GetIconFromProduct(ushort const *,int,ushort const *)

- ea: `0x1801ad6e4`
- end: `0x1801ad8a2`
- name: `?GetIconFromProduct@@YAJPEBGH0@Z`
- size: `446`
- prototype: `__int64 __fastcall(LPCWSTR szProduct, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1801acbdc`

## callees

- `0x1801ad098`
- `0x1801ad6e4`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1801ad74f`
- `KERNEL32!GetProcessHeap` at `0x1801ad7d6`
- `KERNEL32!GetProcessHeap` at `0x1801ad81c`
- `KERNEL32!GetProcessHeap` at `0x1801ad84c`
- `KERNEL32!GetProcessHeap` at `0x1801ad865`
- `KERNEL32!GetProcessHeap` at `0x1801ad74f`
- `KERNEL32!GetProcessHeap` at `0x1801ad7d6`
- `KERNEL32!GetProcessHeap` at `0x1801ad81c`
- `KERNEL32!GetProcessHeap` at `0x1801ad84c`
- `KERNEL32!GetProcessHeap` at `0x1801ad865`
- `KERNEL32!HeapAlloc` at `0x1801ad760`
- `KERNEL32!HeapAlloc` at `0x1801ad7e7`
- `KERNEL32!HeapAlloc` at `0x1801ad760`
- `KERNEL32!HeapAlloc` at `0x1801ad7e7`
- `KERNEL32!HeapFree` at `0x1801ad82a`
- `KERNEL32!HeapFree` at `0x1801ad85a`
- `KERNEL32!HeapFree` at `0x1801ad873`
- `KERNEL32!HeapFree` at `0x1801ad82a`
- `KERNEL32!HeapFree` at `0x1801ad85a`
- `KERNEL32!HeapFree` at `0x1801ad873`
- `MSI!MsiGetProductInfoW` at `0x1801ad72d`
- `MSI!MsiGetProductInfoW` at `0x1801ad789`
- `MSI!MsiGetProductInfoW` at `0x1801ad7b9`
- `MSI!MsiGetProductInfoW` at `0x1801ad80d`
- `MSI!MsiGetProductInfoW` at `0x1801ad72d`
- `MSI!MsiGetProductInfoW` at `0x1801ad789`
- `MSI!MsiGetProductInfoW` at `0x1801ad7b9`
- `MSI!MsiGetProductInfoW` at `0x1801ad80d`
- `MSI!MsiSetInternalUI` at `0x1801ad713`
- `MSI!MsiSetInternalUI` at `0x1801ad883`
- `MSI!MsiSetInternalUI` at `0x1801ad713`
- `MSI!MsiSetInternalUI` at `0x1801ad883`

## pseudocode

```c
__int64 __fastcall GetIconFromProduct(LPCWSTR szProduct, __int64 a2, unsigned __int16 *a3)
{
  INSTALLUILEVEL v5; // r15d
  UINT ProductInfoW; // eax
  WCHAR *v7; // rsi
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v10; // rax
  unsigned int v11; // ebx
  UINT v12; // eax
  __int64 v13; // rdx
  WCHAR *v14; // rdi
  SIZE_T v15; // rbx
  HANDLE v16; // rax
  WCHAR *v17; // rax
  HANDLE v18; // rax
  int IconFromMsi; // eax
  HANDLE v20; // rax
  HANDLE v21; // rax
  DWORD pcchValueBuf; // [rsp+58h] [rbp+38h] BYREF

  pcchValueBuf = 0;
  v5 = MsiSetInternalUI(INSTALLUILEVEL_NONE, 0);
  ProductInfoW = MsiGetProductInfoW(szProduct, L"LocalPackage", 0, &pcchValueBuf);
  if ( ProductInfoW == 234 || (v7 = 0, !ProductInfoW) )
  {
    ++pcchValueBuf;
    v8 = (int)(2 * pcchValueBuf);
    ProcessHeap = GetProcessHeap();
    v10 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v8);
    v7 = v10;
    if ( !v10 )
    {
      v11 = -2147024882;
      goto LABEL_21;
    }
    ProductInfoW = MsiGetProductInfoW(szProduct, L"LocalPackage", v10, &pcchValueBuf);
  }
  v11 = -2147467259;
  if ( !ProductInfoW && pcchValueBuf )
  {
    pcchValueBuf = 0;
    v12 = MsiGetProductInfoW(szProduct, L"ProductIcon", 0, &pcchValueBuf);
    if ( v12 == 234 || (v14 = 0, !v12) )
    {
      ++pcchValueBuf;
      v15 = (int)(2 * pcchValueBuf);
      v16 = GetProcessHeap();
      v17 = (WCHAR *)HeapAlloc(v16, 8u, v15);
      v14 = v17;
      if ( !v17 )
      {
        v11 = -2147024882;
        goto LABEL_19;
      }
      if ( MsiGetProductInfoW(szProduct, L"ProductIcon", v17, &pcchValueBuf) || !pcchValueBuf )
      {
        v18 = GetProcessHeap();
        HeapFree(v18, 0, v14);
        v14 = 0;
      }
    }
    IconFromMsi = GetIconFromMsi(v7, v13, v14, a3);
    v11 = 0;
    if ( IconFromMsi < 0 )
      v11 = IconFromMsi;
    if ( v14 )
    {
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v14);
    }
  }
LABEL_19:
  if ( v7 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v7);
  }
LABEL_21:
  if ( v5 )
    MsiSetInternalUI(v5, 0);
  return v11;
}

```

## disassembly

```asm
0x1801ad6e4  mov     [rsp-28h+arg_0], rbx
0x1801ad6e9  mov     [rsp-28h+arg_10], rsi
0x1801ad6ee  mov     [rsp-28h+pcchValueBuf], edx
0x1801ad6f2  push    rbp
0x1801ad6f3  push    rdi
0x1801ad6f4  push    r12
0x1801ad6f6  push    r14
0x1801ad6f8  push    r15
0x1801ad6fa  mov     rbp, rsp
0x1801ad6fd  sub     rsp, 20h
0x1801ad701  xor     edx, edx; phWnd
0x1801ad703  mov     [rbp+pcchValueBuf], 0
0x1801ad70a  mov     r14, rcx
0x1801ad70d  mov     r12, r8
0x1801ad710  lea     ecx, [rdx+2]; dwUILevel
0x1801ad713  call    cs:__imp_MsiSetInternalUI
0x1801ad719  lea     r9, [rbp+pcchValueBuf]; pcchValueBuf
0x1801ad71d  xor     r8d, r8d; lpValueBuf
0x1801ad720  lea     rdx, szAttribute; "LocalPackage"
0x1801ad727  mov     rcx, r14; szProduct
0x1801ad72a  mov     r15d, eax
0x1801ad72d  call    cs:__imp_MsiGetProductInfoW
0x1801ad733  mov     edi, 0EAh
0x1801ad738  cmp     eax, edi
0x1801ad73a  jz      short loc_1801AD742
0x1801ad73c  xor     esi, esi
0x1801ad73e  test    eax, eax
0x1801ad740  jnz     short loc_1801AD78F
0x1801ad742  mov     eax, [rbp+pcchValueBuf]
0x1801ad745  inc     eax
0x1801ad747  mov     [rbp+pcchValueBuf], eax
0x1801ad74a  add     eax, eax
0x1801ad74c  movsxd  rbx, eax
0x1801ad74f  call    cs:__imp_GetProcessHeap
0x1801ad755  mov     r8, rbx; dwBytes
0x1801ad758  mov     edx, 8; dwFlags
0x1801ad75d  mov     rcx, rax; hHeap
0x1801ad760  call    cs:__imp_HeapAlloc
0x1801ad766  mov     rsi, rax
0x1801ad769  test    rax, rax
0x1801ad76c  jnz     short loc_1801AD778
0x1801ad76e  mov     ebx, 8007000Eh
0x1801ad773  jmp     loc_1801AD879
0x1801ad778  lea     r9, [rbp+pcchValueBuf]; pcchValueBuf
0x1801ad77c  mov     r8, rax; lpValueBuf
0x1801ad77f  lea     rdx, szAttribute; "LocalPackage"
0x1801ad786  mov     rcx, r14; szProduct
0x1801ad789  call    cs:__imp_MsiGetProductInfoW
0x1801ad78f  mov     ebx, 80004005h
0x1801ad794  test    eax, eax
0x1801ad796  jnz     loc_1801AD860
0x1801ad79c  cmp     [rbp+pcchValueBuf], eax
0x1801ad79f  jz      loc_1801AD860
0x1801ad7a5  lea     r9, [rbp+pcchValueBuf]; pcchValueBuf
0x1801ad7a9  mov     [rbp+pcchValueBuf], eax
0x1801ad7ac  xor     r8d, r8d; lpValueBuf
0x1801ad7af  lea     rdx, aProducticon; "ProductIcon"
0x1801ad7b6  mov     rcx, r14; szProduct
0x1801ad7b9  call    cs:__imp_MsiGetProductInfoW
0x1801ad7bf  cmp     eax, edi
0x1801ad7c1  jz      short loc_1801AD7C9
0x1801ad7c3  xor     edi, edi
0x1801ad7c5  test    eax, eax
0x1801ad7c7  jnz     short loc_1801AD832
0x1801ad7c9  mov     eax, [rbp+pcchValueBuf]
0x1801ad7cc  inc     eax
0x1801ad7ce  mov     [rbp+pcchValueBuf], eax
0x1801ad7d1  add     eax, eax
0x1801ad7d3  movsxd  rbx, eax
0x1801ad7d6  call    cs:__imp_GetProcessHeap
0x1801ad7dc  mov     r8, rbx; dwBytes
0x1801ad7df  mov     edx, 8; dwFlags
0x1801ad7e4  mov     rcx, rax; hHeap
0x1801ad7e7  call    cs:__imp_HeapAlloc
0x1801ad7ed  mov     rdi, rax
0x1801ad7f0  test    rax, rax
0x1801ad7f3  jnz     short loc_1801AD7FC
0x1801ad7f5  mov     ebx, 8007000Eh
0x1801ad7fa  jmp     short loc_1801AD860
0x1801ad7fc  lea     r9, [rbp+pcchValueBuf]; pcchValueBuf
0x1801ad800  mov     r8, rdi; lpValueBuf
0x1801ad803  lea     rdx, aProducticon; "ProductIcon"
0x1801ad80a  mov     rcx, r14; szProduct
0x1801ad80d  call    cs:__imp_MsiGetProductInfoW
0x1801ad813  test    eax, eax
0x1801ad815  jnz     short loc_1801AD81C
0x1801ad817  cmp     [rbp+pcchValueBuf], eax
0x1801ad81a  jnz     short loc_1801AD832
0x1801ad81c  call    cs:__imp_GetProcessHeap
0x1801ad822  mov     r8, rdi; lpMem
0x1801ad825  xor     edx, edx; dwFlags
0x1801ad827  mov     rcx, rax; hHeap
0x1801ad82a  call    cs:__imp_HeapFree
0x1801ad830  xor     edi, edi
0x1801ad832  mov     r9, r12; unsigned __int16 *
0x1801ad835  mov     r8, rdi; unsigned __int16 *
0x1801ad838  mov     rcx, rsi; szDatabasePath
0x1801ad83b  call    ?GetIconFromMsi@@YAJPEBGHPEAG0@Z; GetIconFromMsi(ushort const *,int,ushort *,ushort const *)
0x1801ad840  xor     ebx, ebx
0x1801ad842  test    eax, eax
0x1801ad844  cmovs   ebx, eax
0x1801ad847  test    rdi, rdi
0x1801ad84a  jz      short loc_1801AD860
0x1801ad84c  call    cs:__imp_GetProcessHeap
0x1801ad852  mov     r8, rdi; lpMem
0x1801ad855  xor     edx, edx; dwFlags
0x1801ad857  mov     rcx, rax; hHeap
0x1801ad85a  call    cs:__imp_HeapFree
0x1801ad860  test    rsi, rsi
0x1801ad863  jz      short loc_1801AD879
0x1801ad865  call    cs:__imp_GetProcessHeap
0x1801ad86b  mov     r8, rsi; lpMem
0x1801ad86e  xor     edx, edx; dwFlags
0x1801ad870  mov     rcx, rax; hHeap
0x1801ad873  call    cs:__imp_HeapFree
0x1801ad879  test    r15d, r15d
0x1801ad87c  jz      short loc_1801AD889
0x1801ad87e  xor     edx, edx; phWnd
0x1801ad880  mov     ecx, r15d; dwUILevel
0x1801ad883  call    cs:__imp_MsiSetInternalUI
0x1801ad889  mov     rsi, [rsp+20h+arg_10]
0x1801ad88e  mov     eax, ebx
0x1801ad890  mov     rbx, [rsp+20h+arg_0]
0x1801ad895  add     rsp, 20h
0x1801ad899  pop     r15
0x1801ad89b  pop     r14
0x1801ad89d  pop     r12
0x1801ad89f  pop     rdi
0x1801ad8a0  pop     rbp
0x1801ad8a1  retn
```
