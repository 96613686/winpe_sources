# Vregistry::insertKeySecurity(Vstring const &,ulong,_ACCESS_MODE,ulong)

- ea: `0x1800a4210`
- end: `0x1800a43a8`
- name: `?insertKeySecurity@Vregistry@@QEAAPEAVVstatus@@AEBVVstring@@KW4_ACCESS_MODE@@K@Z`
- size: `408`
- prototype: `struct Vstatus *__fastcall(Vregistry *__hidden this, const struct Vstring *, unsigned int, enum _ACCESS_MODE, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a5350`

## callees

- `0x180083790`
- `0x1800838f0`
- `0x1800a3f20`
- `0x1800a4210`
- `0x1800b93d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800a42fb`
- `KERNEL32!GetLastError` at `0x1800a42fb`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1800a42ed`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1800a42ed`
- `ADVAPI32!RegGetKeySecurity` at `0x1800a4251`
- `ADVAPI32!RegGetKeySecurity` at `0x1800a4282`
- `ADVAPI32!RegGetKeySecurity` at `0x1800a4251`
- `ADVAPI32!RegGetKeySecurity` at `0x1800a4282`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a4385`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a4385`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a426b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a42a7`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a4318`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a426b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a42a7`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a4318`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct Vstatus *__fastcall Vregistry::insertKeySecurity(
        HKEY *this,
        const struct Vstring *a2,
        unsigned int a3,
        enum _ACCESS_MODE a4,
        unsigned int a5)
{
  void *v9; // rax
  void *v10; // rdi
  unsigned int KeySecurity; // esi
  HKEY v12; // rbx
  VgenericStatus *v13; // rax
  VgenericStatus *v14; // rbx
  HKEY v15; // rbx
  DWORD LastError; // esi
  VgenericStatus *v17; // rax
  BOOL bDaclDefaulted; // [rsp+30h] [rbp-38h] BYREF
  BOOL bDaclPresent; // [rsp+34h] [rbp-34h] BYREF
  PACL pDacl[2]; // [rsp+38h] [rbp-30h] BYREF
  VgenericStatus *v22; // [rsp+48h] [rbp-20h]
  size_t Size; // [rsp+70h] [rbp+8h] BYREF

  pDacl[1] = (PACL)-2LL;
  LODWORD(Size) = 0;
  RegGetKeySecurity(this[3], 4u, 0, (LPDWORD)&Size);
  if ( dword_1802B0018 )
    v9 = COWSAllocator::AllocCurrentHeap((unsigned int)Size);
  else
    v9 = malloc((unsigned int)Size);
  v10 = v9;
  KeySecurity = RegGetKeySecurity(this[3], 4u, v9, (LPDWORD)&Size);
  if ( KeySecurity )
  {
    v12 = this[1];
    if ( dword_1802B0018 )
      v13 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v13 = (VgenericStatus *)malloc(0x20u);
    v22 = v13;
    if ( v13 )
      v14 = VgenericStatus::VgenericStatus(v13, 0x3006Fu, 0, KeySecurity, v12);
    else
      v14 = 0;
  }
  else if ( GetSecurityDescriptorDacl(v10, &bDaclPresent, pDacl, &bDaclDefaulted) )
  {
    v14 = Vregistry::setKeySecurity((Vregistry *)this, a2, a3, a4, a5, pDacl[0]);
  }
  else
  {
    v15 = this[1];
    LastError = GetLastError();
    if ( dword_1802B0018 )
      v17 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v17 = (VgenericStatus *)malloc(0x20u);
    v22 = v17;
    if ( v17 )
      v14 = VgenericStatus::VgenericStatus(v17, 0x3006Fu, 0, LastError, v15);
    else
      v14 = 0;
  }
  if ( dword_1802B0018 )
    COWSAllocator::Free(v10);
  else
    free(v10);
  return v14;
}

```

## disassembly

```asm
0x1800a4210  mov     rax, rsp
0x1800a4213  push    rdi
0x1800a4214  push    r14
0x1800a4216  push    r15
0x1800a4218  sub     rsp, 50h
0x1800a421c  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800a4224  mov     [rax+10h], rbx
0x1800a4228  mov     [rax+18h], rbp
0x1800a422c  mov     [rax+20h], rsi
0x1800a4230  mov     ebp, r9d
0x1800a4233  mov     r14d, r8d
0x1800a4236  mov     r15, rdx
0x1800a4239  mov     rbx, rcx
0x1800a423c  and     dword ptr [rax+8], 0
0x1800a4240  lea     r9, [rax+8]; lpcbSecurityDescriptor
0x1800a4244  xor     r8d, r8d; pSecurityDescriptor
0x1800a4247  lea     esi, [r8+4]
0x1800a424b  mov     edx, esi; SecurityInformation
0x1800a424d  mov     rcx, [rcx+18h]; hKey
0x1800a4251  call    cs:RegGetKeySecurity
0x1800a4257  mov     ecx, dword ptr [rsp+68h+Size]; unsigned __int64
0x1800a425b  cmp     cs:dword_1802B0018, 0
0x1800a4262  jz      short loc_1800A426B
0x1800a4264  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800a4269  jmp     short loc_1800A4271
0x1800a426b  call    cs:malloc
0x1800a4271  mov     rdi, rax
0x1800a4274  lea     r9, [rsp+68h+Size]; lpcbSecurityDescriptor
0x1800a4279  mov     r8, rax; pSecurityDescriptor
0x1800a427c  mov     edx, esi; SecurityInformation
0x1800a427e  mov     rcx, [rbx+18h]; hKey
0x1800a4282  call    cs:RegGetKeySecurity
0x1800a4288  mov     esi, eax
0x1800a428a  test    eax, eax
0x1800a428c  jz      short loc_1800A42DB
0x1800a428e  mov     rbx, [rbx+8]
0x1800a4292  mov     ecx, 20h ; ' '; unsigned __int64
0x1800a4297  cmp     cs:dword_1802B0018, 0
0x1800a429e  jz      short loc_1800A42A7
0x1800a42a0  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800a42a5  jmp     short loc_1800A42AD
0x1800a42a7  call    cs:malloc
0x1800a42ad  mov     [rsp+68h+var_20], rax
0x1800a42b2  test    rax, rax
0x1800a42b5  jz      short loc_1800A42D4
0x1800a42b7  mov     qword ptr [rsp+68h+var_48], rbx
0x1800a42bc  mov     r9d, esi
0x1800a42bf  xor     r8d, r8d; int
0x1800a42c2  mov     edx, 3006Fh; unsigned int
0x1800a42c7  mov     rcx, rax; this
0x1800a42ca  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x1800a42cf  mov     rbx, rax
0x1800a42d2  jmp     short loc_1800A42D6
0x1800a42d4  xor     ebx, ebx
0x1800a42d6  jmp     loc_1800A4372
0x1800a42db  lea     r9, [rsp+68h+bDaclDefaulted]; lpbDaclDefaulted
0x1800a42e0  lea     r8, [rsp+68h+pDacl]; pDacl
0x1800a42e5  lea     rdx, [rsp+68h+bDaclPresent]; lpbDaclPresent
0x1800a42ea  mov     rcx, rdi; pSecurityDescriptor
0x1800a42ed  call    cs:GetSecurityDescriptorDacl
0x1800a42f3  test    eax, eax
0x1800a42f5  jnz     short loc_1800A4349
0x1800a42f7  mov     rbx, [rbx+8]
0x1800a42fb  call    cs:GetLastError
0x1800a4301  mov     esi, eax
0x1800a4303  mov     ecx, 20h ; ' '; unsigned __int64
0x1800a4308  cmp     cs:dword_1802B0018, 0
0x1800a430f  jz      short loc_1800A4318
0x1800a4311  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800a4316  jmp     short loc_1800A431E
0x1800a4318  call    cs:malloc
0x1800a431e  mov     [rsp+68h+var_20], rax
0x1800a4323  test    rax, rax
0x1800a4326  jz      short loc_1800A4345
0x1800a4328  mov     qword ptr [rsp+68h+var_48], rbx
0x1800a432d  mov     r9d, esi
0x1800a4330  xor     r8d, r8d; int
0x1800a4333  mov     edx, 3006Fh; unsigned int
0x1800a4338  mov     rcx, rax; this
0x1800a433b  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x1800a4340  mov     rbx, rax
0x1800a4343  jmp     short loc_1800A4347
0x1800a4345  xor     ebx, ebx
0x1800a4347  jmp     short loc_1800A4372
0x1800a4349  mov     rax, [rsp+68h+pDacl]
0x1800a434e  mov     [rsp+68h+var_40], rax; struct _ACL *
0x1800a4353  mov     eax, [rsp+68h+arg_20]
0x1800a435a  mov     [rsp+68h+var_48], eax; unsigned int
0x1800a435e  mov     r9d, ebp; enum _ACCESS_MODE
0x1800a4361  mov     r8d, r14d; unsigned int
0x1800a4364  mov     rdx, r15; struct Vstring *
0x1800a4367  mov     rcx, rbx; this
0x1800a436a  call    ?setKeySecurity@Vregistry@@QEAAPEAVVstatus@@AEBVVstring@@KW4_ACCESS_MODE@@KPEAU_ACL@@@Z; Vregistry::setKeySecurity(Vstring const &,ulong,_ACCESS_MODE,ulong,_ACL *)
0x1800a436f  mov     rbx, rax
0x1800a4372  mov     rcx, rdi; void *
0x1800a4375  cmp     cs:dword_1802B0018, 0
0x1800a437c  jz      short loc_1800A4385
0x1800a437e  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800a4383  jmp     short loc_1800A438B
0x1800a4385  call    cs:free
0x1800a438b  mov     rax, rbx
0x1800a438e  lea     r11, [rsp+68h+var_18]
0x1800a4393  mov     rbx, [r11+28h]
0x1800a4397  mov     rbp, [r11+30h]
0x1800a439b  mov     rsi, [r11+38h]
0x1800a439f  mov     rsp, r11
0x1800a43a2  pop     r15
0x1800a43a4  pop     r14
0x1800a43a6  pop     rdi
0x1800a43a7  retn
```
