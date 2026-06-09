# Vregistry::deleteSubKey(char const *,char)

- ea: `0x1800a4630`
- end: `0x1800a499b`
- name: `?deleteSubKey@Vregistry@@UEAAPEAVVstatus@@PEBDD@Z`
- size: `875`
- prototype: `struct Vstatus *__fastcall(Vregistry *__hidden this, const char *, char)`
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config`

## callers

- `0x18004d220`
- `0x1800a4630`
- `0x1800a5a80`

## callees

- `0x180008940`
- `0x18000afb0`
- `0x180040b90`
- `0x1800414c0`
- `0x180083790`
- `0x1800838f0`
- `0x180096770`
- `0x1800a3190`
- `0x1800a32c0`
- `0x1800a3700`
- `0x1800a4630`
- `0x1800a4f20`
- `0x1800a50a0`
- `0x1800b7a58`
- `0x1800b7b38`
- `0x1800b93d0`
- `0x1800bf4a0`
- `0x1800bfda0`
- `0x1801503e0`
- `0x1801519a0`

## import_xrefs

- `ADVAPI32!RegDeleteKeyA` at `0x1800a4910`
- `ADVAPI32!RegDeleteKeyA` at `0x1800a4910`
- `ADVAPI32!RegDeleteKeyW` at `0x1800a4908`
- `ADVAPI32!RegDeleteKeyW` at `0x1800a4908`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a46e4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a4714`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a4863`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a48d8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a46e4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a4714`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a4863`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a48d8`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a4934`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a4934`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
struct Vstatus *__fastcall Vregistry::deleteSubKey(Vregistry *this, const char *a2, char a3)
{
  VgenericStatus *v5; // rbx
  __int64 v6; // rax
  const char **v7; // rax
  int *v8; // rcx
  int *v9; // rcx
  struct Vstatus *inited; // rax
  struct Vstatus *v11; // r8
  unsigned int i; // edi
  struct Vstatus *v13; // rax
  struct Vstatus *v14; // rax
  char *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  int *v18; // rcx
  HKEY v19; // rdi
  int v20; // ecx
  LSTATUS v21; // eax
  unsigned int v22; // edi
  __int64 v23; // rsi
  VgenericStatus *v24; // rax
  char *v26; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+40h] [rbp-C8h] BYREF
  VgenericStatus *v28; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v29[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A8h]
  __int64 v31; // [rsp+68h] [rbp-A0h]
  _QWORD v32[3]; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v33[20]; // [rsp+88h] [rbp-80h] BYREF
  _WORD v34[256]; // [rsp+128h] [rbp+20h] BYREF
  LPCWSTR lpSubKey; // [rsp+328h] [rbp+220h]
  int v36; // [rsp+330h] [rbp+228h]
  char v37; // [rsp+334h] [rbp+22Ch]

  v32[1] = -2;
  v5 = 0;
  if ( a3 )
  {
    v6 = operator+(&v28, (char *)this + 8, "\\");
    v7 = (const char **)operator+(v32, v6, a2);
    Vregistry::Vregistry((Vregistry *)v33, *v7);
    v8 = (int *)(v32[0] - 12LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v32[0] - 12LL), 0xFFFFFFFF) == 1 && v8 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v8);
      else
        free(v8);
    }
    v9 = (int *)((char *)v28 - 12);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v28 - 3, 0xFFFFFFFF) == 1 && v9 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v9);
      else
        free(v9);
    }
    inited = (struct Vstatus *)(*(__int64 (__fastcall **)(_QWORD *, __int64, __int64))(v33[0] + 8LL))(
                                 v33,
                                 -2147483646,
                                 983103);
    v11 = inited;
    if ( inited || (inited = Vregistry::initNextSubKey((Vregistry *)v33), (v11 = inited) != 0) )
    {
      (**(void (__fastcall ***)(struct Vstatus *, __int64))inited)(v11, 1);
    }
    else
    {
      v26 = dword_1802AFD5C;
      _InterlockedIncrement(&dword_1802AFD50);
      VstringRWGVector::VstringRWGVector((VstringRWGVector *)v29, 4u);
      LODWORD(v30) = 0;
      v31 = 0;
      while ( Vregistry::nextSubKey((Vregistry *)v33, (struct Vstring *)&v26) )
        VstringVvector::insert((VstringVvector *)v29, (const struct Vstring *)&v26);
      for ( i = 0; i < (unsigned int)v30; ++i )
      {
        pVwstringVvector::boundsCheck((pVwstringVvector *)v29, i);
        v13 = Vregistry::deleteSubKey((Vregistry *)v33, *(const char **)(v29[1] + 8LL * i), 1);
        if ( v13 )
          (**(void (__fastcall ***)(struct Vstatus *, __int64))v13)(v13, 1);
      }
      v14 = Vregistry::closeKey((Vregistry *)v33);
      if ( v14 )
        (**(void (__fastcall ***)(struct Vstatus *, __int64))v14)(v14, 1);
      VstringVvector::~VstringVvector((VstringVvector *)v29);
      v15 = v26 - 12;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v26 - 3, 0xFFFFFFFF) == 1
        && v15 != (char *)&dword_1802AFD50 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v15);
        else
          free(v15);
      }
    }
    Vregistry::~Vregistry((Vregistry *)v33);
  }
  Vstring::Vstring((Vstring *)&v27, a2);
  lpSubKey = v34;
  v36 = 512;
  v34[0] = 0;
  v37 = 0;
  sub_1800B7B38((VstackStrLCP *)v34);
  v18 = (int *)(v27 - 12);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v27 - 12), 0xFFFFFFFF) == 1 && v18 != &dword_1802AFD50 )
  {
    if ( dword_1802B0018 )
      COWSAllocator::Free(v18);
    else
      free(v18);
  }
  v19 = (HKEY)*((_QWORD *)this + 3);
  if ( (unsigned __int8)sub_180096770(v18, v16, v17) )
    v20 = *(_DWORD *)(qword_1802B00B0 + 4);
  else
    v20 = 0;
  if ( v20 == 2 )
    v21 = RegDeleteKeyW(v19, lpSubKey);
  else
    v21 = RegDeleteKeyA(v19, (LPCSTR)lpSubKey);
  v22 = v21;
  if ( v21 )
  {
    v23 = *((_QWORD *)this + 1);
    if ( dword_1802B0018 )
      v24 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v24 = (VgenericStatus *)malloc(0x20u);
    v28 = v24;
    if ( v24 )
      v5 = VgenericStatus::VgenericStatus(v24, 0x30023u, 0, v22, a2, v23);
  }
  VstackStrLCP::~VstackStrLCP((VstackStrLCP *)v34);
  return v5;
}

```

## disassembly

```asm
0x1800a4630  mov     rax, rsp
0x1800a4633  push    rbp
0x1800a4634  push    rdi
0x1800a4635  push    r12
0x1800a4637  push    r14
0x1800a4639  push    r15
0x1800a463b  lea     rbp, [rax-268h]
0x1800a4642  sub     rsp, 340h
0x1800a4649  mov     [rsp+360h+var_2F0], 0FFFFFFFFFFFFFFFEh
0x1800a4652  mov     [rax+18h], rbx
0x1800a4656  mov     [rax+20h], rsi
0x1800a465a  mov     rax, cs:__security_cookie
0x1800a4661  xor     rax, rsp
0x1800a4664  mov     [rbp+260h+var_30], rax
0x1800a466b  mov     r14, rdx
0x1800a466e  mov     rsi, rcx
0x1800a4671  or      r15d, 0FFFFFFFFh
0x1800a4675  lea     r12, dword_1802AFD50
0x1800a467c  xor     ebx, ebx
0x1800a467e  test    r8b, r8b
0x1800a4681  jz      loc_1800A4873
0x1800a4687  lea     rdx, [rcx+8]
0x1800a468b  lea     r8, SubBlock; "\\"
0x1800a4692  lea     rcx, [rsp+360h+var_320]
0x1800a4697  call    ??H@YA?AVVstring@@AEBV0@PEBD@Z; operator+(Vstring const &,char const *)
0x1800a469c  nop
0x1800a469d  mov     r8, r14
0x1800a46a0  mov     rdx, rax
0x1800a46a3  lea     rcx, [rsp+360h+var_2F8]
0x1800a46a8  call    ??H@YA?AVVstring@@AEBV0@PEBD@Z; operator+(Vstring const &,char const *)
0x1800a46ad  nop
0x1800a46ae  mov     rdx, [rax]; char *
0x1800a46b1  lea     rcx, [rbp+260h+var_2E0]; this
0x1800a46b5  call    ??0Vregistry@@QEAA@PEBD@Z; Vregistry::Vregistry(char const *)
0x1800a46ba  nop
0x1800a46bb  mov     rcx, [rsp+360h+var_2F8]
0x1800a46c0  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800a46c4  mov     eax, r15d
0x1800a46c7  lock xadd [rcx], eax
0x1800a46cb  add     eax, r15d
0x1800a46ce  jnz     short loc_1800A46EB
0x1800a46d0  cmp     rcx, r12
0x1800a46d3  jz      short loc_1800A46EB
0x1800a46d5  cmp     cs:dword_1802B0018, ebx
0x1800a46db  jz      short loc_1800A46E4
0x1800a46dd  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800a46e2  jmp     short loc_1800A46EB
0x1800a46e4  call    cs:free
0x1800a46ea  nop
0x1800a46eb  mov     rcx, [rsp+360h+var_320]
0x1800a46f0  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800a46f4  mov     eax, r15d
0x1800a46f7  lock xadd [rcx], eax
0x1800a46fb  add     eax, r15d
0x1800a46fe  jnz     short loc_1800A471A
0x1800a4700  cmp     rcx, r12
0x1800a4703  jz      short loc_1800A471A
0x1800a4705  cmp     cs:dword_1802B0018, ebx
0x1800a470b  jz      short loc_1800A4714
0x1800a470d  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800a4712  jmp     short loc_1800A471A
0x1800a4714  call    cs:free
0x1800a471a  mov     rax, [rbp+260h+var_2E0]
0x1800a471e  mov     rdx, 0FFFFFFFF80000002h
0x1800a4725  mov     r8d, 0F003Fh
0x1800a472b  lea     rcx, [rbp+260h+var_2E0]
0x1800a472f  mov     rax, [rax+8]
0x1800a4733  call    cs:__guard_dispatch_icall_fptr
0x1800a4739  mov     r8, rax
0x1800a473c  test    rax, rax
0x1800a473f  jnz     short loc_1800A4752
0x1800a4741  lea     rcx, [rbp+260h+var_2E0]; this
0x1800a4745  call    ?initNextSubKey@Vregistry@@QEAAPEAVVstatus@@XZ; Vregistry::initNextSubKey(void)
0x1800a474a  mov     r8, rax
0x1800a474d  test    rax, rax
0x1800a4750  jz      short loc_1800A476B
0x1800a4752  mov     rcx, [rax]
0x1800a4755  mov     rax, [rcx]
0x1800a4758  mov     edx, 1
0x1800a475d  mov     rcx, r8
0x1800a4760  call    cs:__guard_dispatch_icall_fptr
0x1800a4766  jmp     loc_1800A486A
0x1800a476b  lea     rax, dword_1802AFD5C
0x1800a4772  mov     [rsp+360h+var_330], rax
0x1800a4777  lock inc cs:dword_1802AFD50
0x1800a477e  mov     edx, 4; unsigned int
0x1800a4783  lea     rcx, [rsp+360h+var_318]; this
0x1800a4788  call    ??0VstringRWGVector@@QEAA@I@Z; VstringRWGVector::VstringRWGVector(uint)
0x1800a478d  nop
0x1800a478e  mov     dword ptr [rsp+360h+var_308], ebx
0x1800a4792  mov     [rsp+360h+var_300], rbx
0x1800a4797  jmp     short loc_1800A47A8
0x1800a4799  lea     rdx, [rsp+360h+var_330]; struct Vstring *
0x1800a479e  lea     rcx, [rsp+360h+var_318]; this
0x1800a47a3  call    ?insert@VstringVvector@@QEAAXAEBVVstring@@@Z; VstringVvector::insert(Vstring const &)
0x1800a47a8  lea     rdx, [rsp+360h+var_330]; struct Vstring *
0x1800a47ad  lea     rcx, [rbp+260h+var_2E0]; this
0x1800a47b1  call    ?nextSubKey@Vregistry@@QEAADAEAVVstring@@@Z; Vregistry::nextSubKey(Vstring &)
0x1800a47b6  test    al, al
0x1800a47b8  jnz     short loc_1800A4799
0x1800a47ba  mov     edi, ebx
0x1800a47bc  cmp     dword ptr [rsp+360h+var_308], ebx
0x1800a47c0  jbe     short loc_1800A4809
0x1800a47c2  mov     edx, edi; unsigned int
0x1800a47c4  lea     rcx, [rsp+360h+var_318]; this
0x1800a47c9  call    ?boundsCheck@pVwstringVvector@@IEBAXI@Z; pVwstringVvector::boundsCheck(uint)
0x1800a47ce  mov     edx, edi
0x1800a47d0  mov     rax, qword ptr [rsp+360h+var_310]
0x1800a47d5  mov     r8b, 1; char
0x1800a47d8  mov     rdx, [rax+rdx*8]; char *
0x1800a47dc  lea     rcx, [rbp+260h+var_2E0]; this
0x1800a47e0  call    ?deleteSubKey@Vregistry@@UEAAPEAVVstatus@@PEBDD@Z; Vregistry::deleteSubKey(char const *,char)
0x1800a47e5  mov     r8, rax
0x1800a47e8  test    rax, rax
0x1800a47eb  jz      short loc_1800A4801
0x1800a47ed  mov     rcx, [rax]
0x1800a47f0  mov     rax, [rcx]
0x1800a47f3  mov     edx, 1
0x1800a47f8  mov     rcx, r8
0x1800a47fb  call    cs:__guard_dispatch_icall_fptr
0x1800a4801  inc     edi
0x1800a4803  cmp     edi, dword ptr [rsp+360h+var_308]
0x1800a4807  jb      short loc_1800A47C2
0x1800a4809  lea     rcx, [rbp+260h+var_2E0]; this
0x1800a480d  call    ?closeKey@Vregistry@@QEAAPEAVVstatus@@XZ; Vregistry::closeKey(void)
0x1800a4812  mov     r8, rax
0x1800a4815  test    rax, rax
0x1800a4818  jz      short loc_1800A482F
0x1800a481a  mov     rcx, [rax]
0x1800a481d  mov     rax, [rcx]
0x1800a4820  mov     edx, 1
0x1800a4825  mov     rcx, r8
0x1800a4828  call    cs:__guard_dispatch_icall_fptr
0x1800a482e  nop
0x1800a482f  lea     rcx, [rsp+360h+var_318]; this
0x1800a4834  call    ??1VstringVvector@@QEAA@XZ; VstringVvector::~VstringVvector(void)
0x1800a4839  nop
0x1800a483a  mov     rcx, [rsp+360h+var_330]
0x1800a483f  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800a4843  mov     eax, r15d
0x1800a4846  lock xadd [rcx], eax
0x1800a484a  add     eax, r15d
0x1800a484d  jnz     short loc_1800A486A
0x1800a484f  cmp     rcx, r12
0x1800a4852  jz      short loc_1800A486A
0x1800a4854  cmp     cs:dword_1802B0018, ebx
0x1800a485a  jz      short loc_1800A4863
0x1800a485c  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800a4861  jmp     short loc_1800A486A
0x1800a4863  call    cs:free
0x1800a4869  nop
0x1800a486a  lea     rcx, [rbp+260h+var_2E0]; this
0x1800a486e  call    ??1Vregistry@@UEAA@XZ; Vregistry::~Vregistry(void)
0x1800a4873  mov     rdx, r14; char *
0x1800a4876  lea     rcx, [rsp+360h+var_328]; this
0x1800a487b  call    ??0Vstring@@QEAA@PEBD@Z; Vstring::Vstring(char const *)
0x1800a4880  nop
0x1800a4881  lea     rax, [rbp+260h+var_240]
0x1800a4885  mov     [rbp+260h+lpSubKey], rax
0x1800a488c  mov     [rbp+260h+var_38], 200h
0x1800a4896  mov     [rbp+260h+var_240], bx
0x1800a489a  mov     [rbp+260h+var_34], bl
0x1800a48a0  lea     rdx, [rsp+360h+var_328]
0x1800a48a5  lea     rcx, [rbp+260h+var_240]; this
0x1800a48a9  call    sub_1800B7B38
0x1800a48ae  nop
0x1800a48af  mov     rcx, [rsp+360h+var_328]
0x1800a48b4  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800a48b8  mov     eax, r15d
0x1800a48bb  lock xadd [rcx], eax
0x1800a48bf  add     eax, r15d
0x1800a48c2  jnz     short loc_1800A48DE
0x1800a48c4  cmp     rcx, r12
0x1800a48c7  jz      short loc_1800A48DE
0x1800a48c9  cmp     cs:dword_1802B0018, ebx
0x1800a48cf  jz      short loc_1800A48D8
0x1800a48d1  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800a48d6  jmp     short loc_1800A48DE
0x1800a48d8  call    cs:free
0x1800a48de  mov     rdi, [rsi+18h]
0x1800a48e2  call    sub_180096770
0x1800a48e7  test    al, al
0x1800a48e9  jz      short loc_1800A48F7
0x1800a48eb  mov     rax, cs:qword_1802B00B0
0x1800a48f2  mov     ecx, [rax+4]
0x1800a48f5  jmp     short loc_1800A48F9
0x1800a48f7  mov     ecx, ebx
0x1800a48f9  mov     rdx, [rbp+260h+lpSubKey]; lpSubKey
0x1800a4900  cmp     ecx, 2
0x1800a4903  mov     rcx, rdi; hKey
0x1800a4906  jnz     short loc_1800A4910
0x1800a4908  call    cs:RegDeleteKeyW
0x1800a490e  jmp     short loc_1800A4916
0x1800a4910  call    cs:RegDeleteKeyA
0x1800a4916  mov     edi, eax
0x1800a4918  test    eax, eax
0x1800a491a  jz      short loc_1800A4964
0x1800a491c  mov     rsi, [rsi+8]
0x1800a4920  mov     ecx, 20h ; ' '; unsigned __int64
0x1800a4925  cmp     cs:dword_1802B0018, ebx
0x1800a492b  jz      short loc_1800A4934
0x1800a492d  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800a4932  jmp     short loc_1800A493A
0x1800a4934  call    cs:malloc
0x1800a493a  mov     [rsp+360h+var_320], rax
0x1800a493f  test    rax, rax
0x1800a4942  jz      short loc_1800A4964
0x1800a4944  mov     [rsp+360h+var_338], rsi
0x1800a4949  mov     [rsp+360h+var_340], r14
0x1800a494e  mov     r9d, edi
0x1800a4951  xor     r8d, r8d; int
0x1800a4954  mov     edx, 30023h; unsigned int
0x1800a4959  mov     rcx, rax; this
0x1800a495c  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x1800a4961  mov     rbx, rax
0x1800a4964  lea     rcx, [rbp+260h+var_240]; this
0x1800a4968  call    ??1VstackStrLCP@@QEAA@XZ_0; VstackStrLCP::~VstackStrLCP(void)
0x1800a496d  mov     rax, rbx
0x1800a4970  mov     rcx, [rbp+260h+var_30]
0x1800a4977  xor     rcx, rsp
0x1800a497a  call    sub_1801503E0
0x1800a497f  lea     r11, [rsp+360h+var_20]
0x1800a4987  mov     rbx, [r11+40h]
0x1800a498b  mov     rsi, [r11+48h]
0x1800a498f  mov     rsp, r11
0x1800a4992  pop     r15
0x1800a4994  pop     r14
0x1800a4996  pop     r12
0x1800a4998  pop     rdi
0x1800a4999  pop     rbp
0x1800a499a  retn
```
