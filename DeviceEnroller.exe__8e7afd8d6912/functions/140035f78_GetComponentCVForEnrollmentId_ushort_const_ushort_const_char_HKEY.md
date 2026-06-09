# GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)

- ea: `0x140035f78`
- end: `0x140036109`
- name: `?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z`
- size: `401`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, char *, HKEY)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140036110`

## callees

- `0x1400042f0`
- `0x140035f78`

## import_xrefs

- `DMCmnUtils!UnicodeToMB` at `0x14003603a`
- `DMCmnUtils!UnicodeToMB` at `0x14003603a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003606c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400360d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003606c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400360d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003605e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400360c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003605e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400360c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140035fbf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140035fbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400360e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400360e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140035ff3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140035ff3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetComponentCVForEnrollmentId(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        char *a3,
        HKEY a4)
{
  int v5; // esi
  void *v6; // rdi
  HANDLE ProcessHeap; // rax
  void *v8; // rdi
  __int64 v9; // rax
  char *v10; // rdx
  __int64 v11; // rcx
  char v12; // r8
  char *v13; // rax
  HANDLE v14; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v17; // [rsp+34h] [rbp-CCh] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID *p_lpMem; // [rsp+48h] [rbp-B8h]
  char *v21; // [rsp+50h] [rbp-B0h] BYREF
  char v22; // [rsp+58h] [rbp-A8h]
  unsigned __int16 Data[136]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  RegOpenKeyExW(a4, a2, 0, 0x20019u, &hKey);
  cbData = 258;
  if ( !RegQueryValueExW(hKey, L"OmaDmSession", 0, 0, (LPBYTE)Data, &cbData) )
  {
    lpMem = 0;
    v17 = 0;
    p_lpMem = &lpMem;
    v21 = 0;
    v22 = 1;
    v5 = UnicodeToMB(Data, 0xFDE9u, &v21, &v17);
    if ( v22 )
    {
      v6 = *p_lpMem;
      *p_lpMem = v21;
      if ( v6 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v6);
      }
    }
    v8 = lpMem;
    if ( v5 >= 0 )
    {
      v9 = 2147483646;
      v10 = (char *)lpMem;
      v11 = 129;
      do
      {
        if ( !v9 )
          break;
        v12 = *v10;
        if ( !*v10 )
          break;
        ++v10;
        *a3++ = v12;
        --v9;
        --v11;
      }
      while ( v11 );
      v13 = a3 - 1;
      if ( v11 )
        v13 = a3;
      *v13 = 0;
    }
    lpMem = 0;
    if ( v8 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v8);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x140035f78  mov     [rsp-8+arg_0], rbx
0x140035f7d  push    rbp
0x140035f7e  push    rsi
0x140035f7f  push    rdi
0x140035f80  lea     rbp, [rsp-80h]
0x140035f85  sub     rsp, 180h
0x140035f8c  mov     rax, cs:__security_cookie
0x140035f93  xor     rax, rsp
0x140035f96  mov     [rbp+90h+var_20], rax
0x140035f9a  mov     rax, r9
0x140035f9d  mov     rbx, r8
0x140035fa0  mov     [rsp+190h+hKey], 0
0x140035fa9  lea     rcx, [rsp+190h+hKey]
0x140035fae  mov     [rsp+190h+phkResult], rcx; phkResult
0x140035fb3  mov     r9d, 20019h; samDesired
0x140035fb9  xor     r8d, r8d; ulOptions
0x140035fbc  mov     rcx, rax; hKey
0x140035fbf  call    cs:__imp_RegOpenKeyExW
0x140035fc5  mov     [rsp+190h+cbData], 102h
0x140035fcd  lea     rax, [rsp+190h+cbData]
0x140035fd2  mov     [rsp+190h+lpcbData], rax; lpcbData
0x140035fd7  lea     rax, [rsp+190h+Data]
0x140035fdc  mov     [rsp+190h+phkResult], rax; lpData
0x140035fe1  xor     r9d, r9d; lpType
0x140035fe4  xor     r8d, r8d; lpReserved
0x140035fe7  lea     rdx, c_szCvValueNameOmaDmSession; "OmaDmSession"
0x140035fee  mov     rcx, [rsp+190h+hKey]; hKey
0x140035ff3  call    cs:__imp_RegQueryValueExW
0x140035ff9  test    eax, eax
0x140035ffb  jnz     loc_1400360D8
0x140036001  mov     [rsp+190h+lpMem], 0
0x14003600a  mov     [rsp+190h+var_15C], eax
0x14003600e  lea     rax, [rsp+190h+lpMem]
0x140036013  mov     [rsp+190h+var_148], rax
0x140036018  mov     [rsp+190h+var_140], 0
0x140036021  mov     [rsp+190h+var_138], 1
0x140036026  lea     r9, [rsp+190h+var_15C]
0x14003602b  lea     r8, [rsp+190h+var_140]
0x140036030  mov     edx, 0FDE9h
0x140036035  lea     rcx, [rsp+190h+Data]
0x14003603a  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x140036040  mov     esi, eax
0x140036042  cmp     [rsp+190h+var_138], 0
0x140036047  jz      short loc_140036072
0x140036049  mov     rdx, [rsp+190h+var_148]
0x14003604e  mov     rdi, [rdx]
0x140036051  mov     rcx, [rsp+190h+var_140]
0x140036056  mov     [rdx], rcx
0x140036059  test    rdi, rdi
0x14003605c  jz      short loc_140036072
0x14003605e  call    cs:__imp_GetProcessHeap
0x140036064  mov     rcx, rax; hHeap
0x140036067  mov     r8, rdi; lpMem
0x14003606a  xor     edx, edx; dwFlags
0x14003606c  call    cs:__imp_HeapFree
0x140036072  mov     rdi, [rsp+190h+lpMem]
0x140036077  test    esi, esi
0x140036079  js      short loc_1400360B5
0x14003607b  mov     eax, 7FFFFFFEh
0x140036080  mov     rdx, rdi
0x140036083  mov     ecx, 81h
0x140036088  test    rax, rax
0x14003608b  jz      short loc_1400360A7
0x14003608d  mov     r8b, [rdx]
0x140036090  test    r8b, r8b
0x140036093  jz      short loc_1400360A7
0x140036095  inc     rdx
0x140036098  mov     [rbx], r8b
0x14003609b  inc     rbx
0x14003609e  dec     rax
0x1400360a1  sub     rcx, 1
0x1400360a5  jnz     short loc_140036088
0x1400360a7  lea     rax, [rbx-1]
0x1400360ab  test    rcx, rcx
0x1400360ae  cmovnz  rax, rbx
0x1400360b2  mov     byte ptr [rax], 0
0x1400360b5  mov     [rsp+190h+lpMem], 0
0x1400360be  test    rdi, rdi
0x1400360c1  jz      short loc_1400360D8
0x1400360c3  call    cs:__imp_GetProcessHeap
0x1400360c9  mov     rcx, rax; hHeap
0x1400360cc  mov     r8, rdi; lpMem
0x1400360cf  xor     edx, edx; dwFlags
0x1400360d1  call    cs:__imp_HeapFree
0x1400360d7  nop
0x1400360d8  mov     rcx, [rsp+190h+hKey]; hKey
0x1400360dd  test    rcx, rcx
0x1400360e0  jz      short loc_1400360E8
0x1400360e2  call    cs:__imp_RegCloseKey
0x1400360e8  xor     eax, eax
0x1400360ea  mov     rcx, [rbp+90h+var_20]
0x1400360ee  xor     rcx, rsp; StackCookie
0x1400360f1  call    __security_check_cookie
0x1400360f6  mov     rbx, [rsp+190h+arg_0]
0x1400360fe  add     rsp, 180h
0x140036105  pop     rdi
0x140036106  pop     rsi
0x140036107  pop     rbp
0x140036108  retn
```
