# Vregistry::deleteValue(char const *)

- ea: `0x1800a43b0`
- end: `0x1800a4508`
- name: `?deleteValue@Vregistry@@UEAAPEAVVstatus@@PEBD@Z`
- size: `344`
- prototype: `struct Vstatus *__fastcall(Vregistry *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18004d130`
- `0x1800a5750`

## callees

- `0x180040b90`
- `0x180083790`
- `0x1800838f0`
- `0x180096770`
- `0x1800a43b0`
- `0x1800b7a58`
- `0x1800b7b38`
- `0x1800b93d0`
- `0x1801503e0`

## import_xrefs

- `ADVAPI32!RegDeleteValueA` at `0x1800a448e`
- `ADVAPI32!RegDeleteValueA` at `0x1800a448e`
- `ADVAPI32!RegDeleteValueW` at `0x1800a4486`
- `ADVAPI32!RegDeleteValueW` at `0x1800a4486`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a4456`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a4456`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a44ae`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a44ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct Vstatus *__fastcall Vregistry::deleteValue(Vregistry *this, const char *a2)
{
  VgenericStatus *v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  int *v7; // rcx
  HKEY v8; // rdi
  int v9; // ecx
  LSTATUS v10; // eax
  unsigned int v11; // edi
  VgenericStatus *v12; // rax
  _QWORD v14[2]; // [rsp+38h] [rbp-D0h] BYREF
  _WORD v15[256]; // [rsp+48h] [rbp-C0h] BYREF
  LPCWSTR lpValueName; // [rsp+248h] [rbp+140h]
  int v17; // [rsp+250h] [rbp+148h]
  char v18; // [rsp+254h] [rbp+14Ch]

  v14[1] = -2;
  Vstring::Vstring((Vstring *)v14, a2);
  lpValueName = v15;
  v17 = 512;
  v4 = 0;
  v15[0] = 0;
  v18 = 0;
  sub_1800B7B38((VstackStrLCP *)v15);
  v7 = (int *)(v14[0] - 12LL);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v14[0] - 12LL), 0xFFFFFFFF) == 1 && v7 != &dword_1802AFD50 )
  {
    if ( dword_1802B0018 )
      COWSAllocator::Free(v7);
    else
      free(v7);
  }
  v8 = (HKEY)*((_QWORD *)this + 3);
  if ( (unsigned __int8)sub_180096770(v7, v5, v6) )
    v9 = *(_DWORD *)(qword_1802B00B0 + 4);
  else
    v9 = 0;
  if ( v9 == 2 )
    v10 = RegDeleteValueW(v8, lpValueName);
  else
    v10 = RegDeleteValueA(v8, (LPCSTR)lpValueName);
  v11 = v10;
  if ( v10 )
  {
    if ( dword_1802B0018 )
      v12 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v12 = (VgenericStatus *)malloc(0x20u);
    v14[0] = v12;
    if ( v12 )
      v4 = VgenericStatus::VgenericStatus(v12, 0x30021u, 0, v11, a2);
  }
  VstackStrLCP::~VstackStrLCP((VstackStrLCP *)v15);
  return v4;
}

```

## disassembly

```asm
0x1800a43b0  mov     rax, rsp
0x1800a43b3  push    rbp
0x1800a43b4  push    rsi
0x1800a43b5  push    rdi
0x1800a43b6  lea     rbp, [rax-178h]
0x1800a43bd  sub     rsp, 260h
0x1800a43c4  mov     qword ptr [rsp+270h+var_238], 0FFFFFFFFFFFFFFFEh
0x1800a43cd  mov     [rax+18h], rbx
0x1800a43d1  mov     rax, cs:__security_cookie
0x1800a43d8  xor     rax, rsp
0x1800a43db  mov     [rbp+170h+var_20], rax
0x1800a43e2  mov     rsi, rdx
0x1800a43e5  mov     rdi, rcx
0x1800a43e8  lea     rcx, [rsp+270h+var_240]; this
0x1800a43ed  call    ??0Vstring@@QEAA@PEBD@Z; Vstring::Vstring(char const *)
0x1800a43f2  nop
0x1800a43f3  lea     rax, [rsp+270h+var_230]
0x1800a43f8  mov     [rbp+170h+lpValueName], rax
0x1800a43ff  mov     [rbp+170h+var_28], 200h
0x1800a4409  xor     ebx, ebx
0x1800a440b  mov     [rsp+270h+var_230], bx
0x1800a4410  mov     [rbp+170h+var_24], bl
0x1800a4416  lea     rdx, [rsp+270h+var_240]
0x1800a441b  lea     rcx, [rsp+270h+var_230]; this
0x1800a4420  call    sub_1800B7B38
0x1800a4425  nop
0x1800a4426  mov     rcx, [rsp+270h+var_240]
0x1800a442b  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800a442f  or      eax, 0FFFFFFFFh
0x1800a4432  lock xadd [rcx], eax
0x1800a4436  cmp     eax, 1
0x1800a4439  jnz     short loc_1800A445C
0x1800a443b  lea     rax, dword_1802AFD50
0x1800a4442  cmp     rcx, rax
0x1800a4445  jz      short loc_1800A445C
0x1800a4447  cmp     cs:dword_1802B0018, ebx
0x1800a444d  jz      short loc_1800A4456
0x1800a444f  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800a4454  jmp     short loc_1800A445C
0x1800a4456  call    cs:free
0x1800a445c  mov     rdi, [rdi+18h]
0x1800a4460  call    sub_180096770
0x1800a4465  test    al, al
0x1800a4467  jz      short loc_1800A4475
0x1800a4469  mov     rax, cs:qword_1802B00B0
0x1800a4470  mov     ecx, [rax+4]
0x1800a4473  jmp     short loc_1800A4477
0x1800a4475  mov     ecx, ebx
0x1800a4477  mov     rdx, [rbp+170h+lpValueName]; lpValueName
0x1800a447e  cmp     ecx, 2
0x1800a4481  mov     rcx, rdi; hKey
0x1800a4484  jnz     short loc_1800A448E
0x1800a4486  call    cs:RegDeleteValueW
0x1800a448c  jmp     short loc_1800A4494
0x1800a448e  call    cs:RegDeleteValueA
0x1800a4494  mov     edi, eax
0x1800a4496  test    eax, eax
0x1800a4498  jz      short loc_1800A44D9
0x1800a449a  mov     ecx, 20h ; ' '; unsigned __int64
0x1800a449f  cmp     cs:dword_1802B0018, ebx
0x1800a44a5  jz      short loc_1800A44AE
0x1800a44a7  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800a44ac  jmp     short loc_1800A44B4
0x1800a44ae  call    cs:malloc
0x1800a44b4  mov     [rsp+270h+var_240], rax
0x1800a44b9  test    rax, rax
0x1800a44bc  jz      short loc_1800A44D9
0x1800a44be  mov     [rsp+20h], rsi
0x1800a44c3  mov     r9d, edi
0x1800a44c6  xor     r8d, r8d; int
0x1800a44c9  mov     edx, 30021h; unsigned int
0x1800a44ce  mov     rcx, rax; this
0x1800a44d1  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x1800a44d6  mov     rbx, rax
0x1800a44d9  lea     rcx, [rsp+270h+var_230]; this
0x1800a44de  call    ??1VstackStrLCP@@QEAA@XZ_0; VstackStrLCP::~VstackStrLCP(void)
0x1800a44e3  mov     rax, rbx
0x1800a44e6  mov     rcx, [rbp+170h+var_20]
0x1800a44ed  xor     rcx, rsp
0x1800a44f0  call    sub_1801503E0
0x1800a44f5  mov     rbx, [rsp+270h+arg_10]
0x1800a44fd  add     rsp, 260h
0x1800a4504  pop     rdi
0x1800a4505  pop     rsi
0x1800a4506  pop     rbp
0x1800a4507  retn
```
