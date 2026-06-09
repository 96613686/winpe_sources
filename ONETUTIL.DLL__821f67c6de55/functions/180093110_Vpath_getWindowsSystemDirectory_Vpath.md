# Vpath::getWindowsSystemDirectory(Vpath &)

- ea: `0x180093110`
- end: `0x1800932e5`
- name: `?getWindowsSystemDirectory@Vpath@@SAPEAVVstatus@@AEAV1@@Z`
- size: `469`
- prototype: `struct Vstatus *__fastcall(struct Vpath *)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x180040c60`
- `0x180083790`
- `0x1800838f0`
- `0x180090560`
- `0x180090bf0`
- `0x180093110`
- `0x180095100`
- `0x180096770`
- `0x1800b79c0`
- `0x1800b7a58`
- `0x1800b93d0`
- `0x1801503e0`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x1800931b3`
- `KERNEL32!GetSystemDirectoryW` at `0x1800931b3`
- `KERNEL32!GetSystemDirectoryA` at `0x1800931bb`
- `KERNEL32!GetSystemDirectoryA` at `0x1800931bb`
- `KERNEL32!GetLastError` at `0x1800931c5`
- `KERNEL32!GetLastError` at `0x1800931c5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009327b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800932a9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009327b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800932a9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800931e1`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800931e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct Vstatus *__fastcall Vpath::getWindowsSystemDirectory(struct Vpath *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  VgenericStatus *v7; // rbx
  __int64 v8; // rcx
  unsigned __int64 v9; // rdi
  int v10; // ecx
  UINT SystemDirectoryW; // eax
  DWORD LastError; // edi
  VgenericStatus *v13; // rax
  Vpath *v14; // rax
  int *v15; // rcx
  int *v16; // rcx
  __int64 v18; // [rsp+28h] [rbp-E0h] BYREF
  VgenericStatus *v19; // [rsp+30h] [rbp-D8h]
  _QWORD v20[4]; // [rsp+38h] [rbp-D0h] BYREF
  _BYTE v21[512]; // [rsp+58h] [rbp-B0h] BYREF
  LPWSTR lpBuffer; // [rsp+258h] [rbp+150h]
  int v23; // [rsp+260h] [rbp+158h]

  v20[3] = -2;
  sub_1800B79C0((VstackStrLCP *)v21);
  v7 = 0;
  if ( (unsigned __int8)sub_180096770(v3, v2, v4) )
    v8 = *(unsigned int *)(qword_1802B00B0 + 4);
  else
    v8 = 0;
  if ( (_DWORD)v8 == 2 )
    v9 = (unsigned __int64)v23 >> 1;
  else
    LODWORD(v9) = v23;
  if ( (unsigned __int8)sub_180096770(v8, v5, v6) )
    v10 = *(_DWORD *)(qword_1802B00B0 + 4);
  else
    v10 = 0;
  if ( v10 == 2 )
    SystemDirectoryW = GetSystemDirectoryW(lpBuffer, v9);
  else
    SystemDirectoryW = GetSystemDirectoryA((LPSTR)lpBuffer, v9);
  if ( SystemDirectoryW )
  {
    Vstring::Vstring((Vstring *)&v18, (const struct VstackStrLCP *)v21);
    v14 = Vpath::Vpath((Vpath *)v20, (const struct Vstring *)&v18);
    Vpath::operator=(a1, v14);
    Vpath::ClearStat((Vpath *)v20);
    v19 = (VgenericStatus *)v20;
    v15 = (int *)(v20[0] - 12LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v20[0] - 12LL), 0xFFFFFFFF) == 1 && v15 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v15);
      else
        free(v15);
    }
    v16 = (int *)(v18 - 12);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v18 - 12), 0xFFFFFFFF) == 1 && v16 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v16);
      else
        free(v16);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( dword_1802B0018 )
      v13 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v13 = (VgenericStatus *)malloc(0x20u);
    v19 = v13;
    if ( v13 )
      v7 = VgenericStatus::VgenericStatus(v13, 0x20030u, LastError);
  }
  VstackStrLCP::~VstackStrLCP((VstackStrLCP *)v21);
  return v7;
}

```

## disassembly

```asm
0x180093110  mov     rax, rsp
0x180093113  push    rbp
0x180093114  lea     rbp, [rax-178h]
0x18009311b  sub     rsp, 270h
0x180093122  mov     qword ptr [rsp+270h+var_228], 0FFFFFFFFFFFFFFFEh
0x18009312b  mov     [rax+10h], rbx
0x18009312f  mov     [rax+18h], rsi
0x180093133  mov     [rax+20h], rdi
0x180093137  mov     rax, cs:__security_cookie
0x18009313e  xor     rax, rsp
0x180093141  mov     [rbp+170h+var_10], rax
0x180093148  mov     rsi, rcx
0x18009314b  xor     r8d, r8d
0x18009314e  mov     edx, 104h
0x180093153  lea     rcx, [rsp+270h+var_220]; this
0x180093158  call    sub_1800B79C0
0x18009315d  nop
0x18009315e  call    sub_180096770
0x180093163  xor     ebx, ebx
0x180093165  test    al, al
0x180093167  jz      short loc_180093175
0x180093169  mov     rax, cs:qword_1802B00B0
0x180093170  mov     ecx, [rax+4]
0x180093173  jmp     short loc_180093177
0x180093175  mov     ecx, ebx
0x180093177  cmp     ecx, 2
0x18009317a  jnz     short loc_180093188
0x18009317c  movsxd  rdi, [rbp+170h+var_18]
0x180093183  shr     rdi, 1
0x180093186  jmp     short loc_18009318E
0x180093188  mov     edi, [rbp+170h+var_18]
0x18009318e  call    sub_180096770
0x180093193  test    al, al
0x180093195  jz      short loc_1800931A3
0x180093197  mov     rax, cs:qword_1802B00B0
0x18009319e  mov     ecx, [rax+4]
0x1800931a1  jmp     short loc_1800931A5
0x1800931a3  mov     ecx, ebx
0x1800931a5  mov     edx, edi; uSize
0x1800931a7  cmp     ecx, 2
0x1800931aa  mov     rcx, [rbp+170h+lpBuffer]; lpBuffer
0x1800931b1  jnz     short loc_1800931BB
0x1800931b3  call    cs:GetSystemDirectoryW
0x1800931b9  jmp     short loc_1800931C1
0x1800931bb  call    cs:GetSystemDirectoryA
0x1800931c1  test    eax, eax
0x1800931c3  jnz     short loc_180093209
0x1800931c5  call    cs:GetLastError
0x1800931cb  mov     edi, eax
0x1800931cd  mov     ecx, 20h ; ' '; unsigned __int64
0x1800931d2  cmp     cs:dword_1802B0018, ebx
0x1800931d8  jz      short loc_1800931E1
0x1800931da  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800931df  jmp     short loc_1800931E7
0x1800931e1  call    cs:malloc
0x1800931e7  mov     [rsp+270h+var_248], rax
0x1800931ec  test    rax, rax
0x1800931ef  jz      short loc_180093204
0x1800931f1  mov     r8d, edi; int
0x1800931f4  mov     edx, 20030h; unsigned int
0x1800931f9  mov     rcx, rax; this
0x1800931fc  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x180093201  mov     rbx, rax
0x180093204  jmp     loc_1800932B0
0x180093209  lea     rdx, [rsp+270h+var_220]; struct VstackStrLCP *
0x18009320e  lea     rcx, [rsp+270h+var_250]; this
0x180093213  call    ??0Vstring@@QEAA@AEBVVstackStrLCP@@@Z; Vstring::Vstring(VstackStrLCP const &)
0x180093218  nop
0x180093219  lea     rdx, [rsp+270h+var_250]; struct Vstring *
0x18009321e  lea     rcx, [rsp+270h+var_240]; this
0x180093223  call    ??0Vpath@@QEAA@AEBVVstring@@@Z; Vpath::Vpath(Vstring const &)
0x180093228  nop
0x180093229  mov     rdx, rax
0x18009322c  mov     rcx, rsi
0x18009322f  call    ??4Vpath@@QEAAAEAV0@AEBV0@@Z; Vpath::operator=(Vpath const &)
0x180093234  nop
0x180093235  lea     rcx, [rsp+270h+var_240]; this
0x18009323a  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x18009323f  nop
0x180093240  lea     rax, [rsp+270h+var_240]
0x180093245  mov     [rsp+270h+var_248], rax
0x18009324a  mov     rcx, [rsp+270h+var_240]
0x18009324f  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x180093253  or      edi, 0FFFFFFFFh
0x180093256  mov     eax, edi
0x180093258  lock xadd [rcx], eax
0x18009325c  lea     rsi, dword_1802AFD50
0x180093263  add     eax, edi
0x180093265  jnz     short loc_180093282
0x180093267  cmp     rcx, rsi
0x18009326a  jz      short loc_180093282
0x18009326c  cmp     cs:dword_1802B0018, ebx
0x180093272  jz      short loc_18009327B
0x180093274  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x180093279  jmp     short loc_180093282
0x18009327b  call    cs:free
0x180093281  nop
0x180093282  mov     rcx, [rsp+270h+var_250]
0x180093287  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18009328b  mov     eax, edi
0x18009328d  lock xadd [rcx], eax
0x180093291  add     eax, edi
0x180093293  jnz     short loc_1800932B0
0x180093295  cmp     rcx, rsi
0x180093298  jz      short loc_1800932B0
0x18009329a  cmp     cs:dword_1802B0018, ebx
0x1800932a0  jz      short loc_1800932A9
0x1800932a2  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800932a7  jmp     short loc_1800932B0
0x1800932a9  call    cs:free
0x1800932af  nop
0x1800932b0  lea     rcx, [rsp+270h+var_220]; this
0x1800932b5  call    ??1VstackStrLCP@@QEAA@XZ_0; VstackStrLCP::~VstackStrLCP(void)
0x1800932ba  mov     rax, rbx
0x1800932bd  mov     rcx, [rbp+170h+var_10]
0x1800932c4  xor     rcx, rsp
0x1800932c7  call    sub_1801503E0
0x1800932cc  lea     r11, [rsp+270h+var_s0]
0x1800932d4  mov     rbx, [r11+18h]
0x1800932d8  mov     rsi, [r11+20h]
0x1800932dc  mov     rdi, [r11+28h]
0x1800932e0  mov     rsp, r11
0x1800932e3  pop     rbp
0x1800932e4  retn
```
