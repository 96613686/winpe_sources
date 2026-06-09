# Vpath::getWindowsDirectory(Vpath &)

- ea: `0x180092d70`
- end: `0x18009310d`
- name: `?getWindowsDirectory@Vpath@@SAPEAVVstatus@@AEAV1@@Z`
- size: `925`
- prototype: `struct Vstatus *__fastcall(struct Vpath *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting`

## callees

- `0x180040c60`
- `0x1800488f4`
- `0x180083790`
- `0x1800838f0`
- `0x180083b70`
- `0x180083bb0`
- `0x180083bf0`
- `0x180090560`
- `0x180090bf0`
- `0x180092d70`
- `0x180095100`
- `0x180096770`
- `0x1800b79c0`
- `0x1800b7a58`
- `0x1800b93d0`
- `0x1801503e0`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180092edd`
- `KERNEL32!FreeLibrary` at `0x180092edd`
- `KERNEL32!GetProcAddress` at `0x180092e3e`
- `KERNEL32!GetProcAddress` at `0x180092e7b`
- `KERNEL32!GetProcAddress` at `0x180092e3e`
- `KERNEL32!GetProcAddress` at `0x180092e7b`
- `KERNEL32!GetLastError` at `0x180092dcd`
- `KERNEL32!GetLastError` at `0x180092f62`
- `KERNEL32!GetLastError` at `0x180092fee`
- `KERNEL32!GetLastError` at `0x180092dcd`
- `KERNEL32!GetLastError` at `0x180092f62`
- `KERNEL32!GetLastError` at `0x180092fee`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800930a4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800930d2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800930a4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800930d2`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180092de7`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180092f7e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18009300a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180092de7`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180092f7e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18009300a`

## string_xrefs

- `0x180092db9`: `KERNEL32.DLL`
- `0x180092e26`: `GetSystemWindowsDirectoryW`
- `0x180092e2d`: `GetSystemWindowsDirectoryA`
- `0x180092e63`: `GetWindowsDirectoryW`
- `0x180092e6a`: `GetWindowsDirectoryA`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
struct Vstatus *__fastcall Vpath::getWindowsDirectory(struct Vpath *a1)
{
  VgenericStatus *v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // rcx
  HMODULE v5; // rsi
  __int64 v6; // r8
  DWORD v7; // edi
  VgenericStatus *v8; // rax
  int v9; // ecx
  const CHAR *v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rcx
  FARPROC ProcAddress; // rdi
  __int64 v14; // r8
  int v15; // ecx
  const CHAR *v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rcx
  int v23; // ecx
  unsigned __int64 v24; // rax
  DWORD LastError; // edi
  VgenericStatus *v26; // rax
  int v27; // ecx
  unsigned __int64 v28; // rax
  DWORD v29; // edi
  VgenericStatus *v30; // rax
  Vpath *v31; // rax
  int *v32; // rcx
  int *v33; // rcx
  char IsCurrentHeapLocal; // [rsp+28h] [rbp-E0h]
  bool v36; // [rsp+29h] [rbp-DFh]
  __int64 v37; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v38[5]; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v39[512]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+268h] [rbp+160h]
  int v41; // [rsp+270h] [rbp+168h]

  v38[3] = -2;
  v2 = 0;
  if ( qword_1802B0038 )
    goto LABEL_30;
  v5 = sub_1800488F4("KERNEL32.DLL");
  if ( v5 )
  {
    if ( (unsigned __int8)sub_180096770(v4, v3, v6) )
      v9 = *(_DWORD *)(qword_1802B00B0 + 4);
    else
      v9 = 0;
    v10 = "GetSystemWindowsDirectoryA";
    if ( v9 == 2 )
      v10 = "GetSystemWindowsDirectoryW";
    ProcAddress = GetProcAddress(v5, v10);
    if ( !ProcAddress )
    {
      if ( (unsigned __int8)sub_180096770(v12, v11, v14) )
        v15 = *(_DWORD *)(qword_1802B00B0 + 4);
      else
        v15 = 0;
      v16 = "GetWindowsDirectoryA";
      if ( v15 == 2 )
        v16 = "GetWindowsDirectoryW";
      ProcAddress = GetProcAddress(v5, v16);
    }
    if ( dword_1802B0018 )
    {
      IsCurrentHeapLocal = COWSAllocator::IsCurrentHeapLocal();
      v36 = IsCurrentHeapLocal == 1;
      if ( IsCurrentHeapLocal == 1 )
        COWSAllocator::UseGlobalHeap();
    }
    _InterlockedExchange64(&qword_1802B0038, (__int64)ProcAddress);
    if ( dword_1802B0018 && v36 )
    {
      if ( IsCurrentHeapLocal )
        COWSAllocator::UseLocalHeap();
      else
        COWSAllocator::UseGlobalHeap();
    }
    FreeLibrary(v5);
LABEL_30:
    sub_1800B79C0((VstackStrLCP *)v39);
    if ( (unsigned __int8)sub_180096770(v18, v17, v19) )
      v22 = *(unsigned int *)(qword_1802B00B0 + 4);
    else
      v22 = 0;
    if ( (_DWORD)v22 == 2 )
    {
      if ( (unsigned __int8)sub_180096770(v22, v20, v21) )
        v23 = *(_DWORD *)(qword_1802B00B0 + 4);
      else
        v23 = 0;
      if ( v23 == 2 )
        v24 = (unsigned __int64)v41 >> 1;
      else
        LODWORD(v24) = v41;
      if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD))qword_1802B0038)(v40, (unsigned int)v24) )
      {
        LastError = GetLastError();
        if ( dword_1802B0018 )
          v26 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
        else
          v26 = (VgenericStatus *)malloc(0x20u);
        if ( v26 )
          v2 = VgenericStatus::VgenericStatus(v26, 0x2002Fu, LastError);
LABEL_70:
        VstackStrLCP::~VstackStrLCP((VstackStrLCP *)v39);
        return v2;
      }
    }
    else
    {
      if ( (unsigned __int8)sub_180096770(v22, v20, v21) )
        v27 = *(_DWORD *)(qword_1802B00B0 + 4);
      else
        v27 = 0;
      if ( v27 == 2 )
        v28 = (unsigned __int64)v41 >> 1;
      else
        LODWORD(v28) = v41;
      if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD))qword_1802B0038)(v40, (unsigned int)v28) )
      {
        v29 = GetLastError();
        if ( dword_1802B0018 )
          v30 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
        else
          v30 = (VgenericStatus *)malloc(0x20u);
        if ( v30 )
          v2 = VgenericStatus::VgenericStatus(v30, 0x2002Fu, v29);
        goto LABEL_70;
      }
    }
    Vstring::Vstring((Vstring *)&v37, (const struct VstackStrLCP *)v39);
    v31 = Vpath::Vpath((Vpath *)v38, (const struct Vstring *)&v37);
    Vpath::operator=(a1, v31);
    Vpath::ClearStat((Vpath *)v38);
    v32 = (int *)(v38[0] - 12LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v38[0] - 12LL), 0xFFFFFFFF) == 1 && v32 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v32);
      else
        free(v32);
    }
    v33 = (int *)(v37 - 12);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v37 - 12), 0xFFFFFFFF) == 1 && v33 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v33);
      else
        free(v33);
    }
    goto LABEL_70;
  }
  v7 = GetLastError();
  if ( dword_1802B0018 )
    v8 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
  else
    v8 = (VgenericStatus *)malloc(0x20u);
  if ( v8 )
    return VgenericStatus::VgenericStatus(v8, 0x2002Fu, v7);
  return v2;
}

```

## disassembly

```asm
0x180092d70  mov     rax, rsp
0x180092d73  push    rbp
0x180092d74  push    rdi
0x180092d75  push    r14
0x180092d77  lea     rbp, [rax-198h]
0x180092d7e  sub     rsp, 280h
0x180092d85  mov     [rsp+290h+var_240], 0FFFFFFFFFFFFFFFEh
0x180092d8e  mov     [rax+10h], rbx
0x180092d92  mov     [rax+18h], rsi
0x180092d96  mov     rax, cs:__security_cookie
0x180092d9d  xor     rax, rsp
0x180092da0  mov     [rbp+190h+var_20], rax
0x180092da7  mov     r14, rcx
0x180092daa  xor     ebx, ebx
0x180092dac  cmp     cs:qword_1802B0038, rbx
0x180092db3  jnz     loc_180092EE3
0x180092db9  lea     rcx, aKernel32Dll_1; "KERNEL32.DLL"
0x180092dc0  call    sub_1800488F4
0x180092dc5  mov     rsi, rax
0x180092dc8  test    rax, rax
0x180092dcb  jnz     short loc_180092E0F
0x180092dcd  call    cs:GetLastError
0x180092dd3  mov     edi, eax
0x180092dd5  lea     ecx, [rbx+20h]; unsigned __int64
0x180092dd8  cmp     cs:dword_1802B0018, ebx
0x180092dde  jz      short loc_180092DE7
0x180092de0  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180092de5  jmp     short loc_180092DED
0x180092de7  call    cs:malloc
0x180092ded  mov     [rsp+290h+var_268], rax
0x180092df2  test    rax, rax
0x180092df5  jz      short loc_180092E0A
0x180092df7  mov     r8d, edi; int
0x180092dfa  mov     edx, 2002Fh; unsigned int
0x180092dff  mov     rcx, rax; this
0x180092e02  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x180092e07  mov     rbx, rax
0x180092e0a  jmp     loc_1800930E3
0x180092e0f  call    sub_180096770
0x180092e14  test    al, al
0x180092e16  jz      short loc_180092E24
0x180092e18  mov     rax, cs:qword_1802B00B0
0x180092e1f  mov     ecx, [rax+4]
0x180092e22  jmp     short loc_180092E26
0x180092e24  mov     ecx, ebx
0x180092e26  lea     rax, aGetsystemwindo; "GetSystemWindowsDirectoryW"
0x180092e2d  lea     rdx, aGetsystemwindo_0; "GetSystemWindowsDirectoryA"
0x180092e34  cmp     ecx, 2
0x180092e37  cmovz   rdx, rax; lpProcName
0x180092e3b  mov     rcx, rsi; hModule
0x180092e3e  call    cs:GetProcAddress
0x180092e44  mov     rdi, rax
0x180092e47  test    rax, rax
0x180092e4a  jnz     short loc_180092E84
0x180092e4c  call    sub_180096770
0x180092e51  test    al, al
0x180092e53  jz      short loc_180092E61
0x180092e55  mov     rax, cs:qword_1802B00B0
0x180092e5c  mov     ecx, [rax+4]
0x180092e5f  jmp     short loc_180092E63
0x180092e61  mov     ecx, ebx
0x180092e63  lea     rax, aGetwindowsdire_0; "GetWindowsDirectoryW"
0x180092e6a  lea     rdx, aGetwindowsdire_1; "GetWindowsDirectoryA"
0x180092e71  cmp     ecx, 2
0x180092e74  cmovz   rdx, rax; lpProcName
0x180092e78  mov     rcx, rsi; hModule
0x180092e7b  call    cs:GetProcAddress
0x180092e81  mov     rdi, rax
0x180092e84  cmp     cs:dword_1802B0018, ebx
0x180092e8a  jz      short loc_180092EB3
0x180092e8c  call    ?IsCurrentHeapLocal@COWSAllocator@@SADXZ; COWSAllocator::IsCurrentHeapLocal(void)
0x180092e91  mov     byte ptr [rsp+290h+var_270], al
0x180092e95  cmp     al, 1
0x180092e97  setz    cl
0x180092e9a  mov     byte ptr [rsp+290h+var_270+1], cl
0x180092e9e  test    cl, cl
0x180092ea0  jz      short loc_180092EB3
0x180092ea2  test    al, al
0x180092ea4  jz      short loc_180092EAD
0x180092ea6  call    ?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x180092eab  jmp     short loc_180092EB3
0x180092ead  call    ?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x180092eb2  nop
0x180092eb3  xchg    rdi, cs:qword_1802B0038
0x180092eba  cmp     cs:dword_1802B0018, ebx
0x180092ec0  jz      short loc_180092EDA
0x180092ec2  cmp     byte ptr [rsp+290h+var_270+1], bl
0x180092ec6  jz      short loc_180092EDA
0x180092ec8  cmp     byte ptr [rsp+290h+var_270], bl
0x180092ecc  jz      short loc_180092ED5
0x180092ece  call    ?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x180092ed3  jmp     short loc_180092EDA
0x180092ed5  call    ?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x180092eda  mov     rcx, rsi; hLibModule
0x180092edd  call    cs:FreeLibrary
0x180092ee3  xor     r8d, r8d
0x180092ee6  mov     edx, 104h
0x180092eeb  lea     rcx, [rsp+290h+var_230]; this
0x180092ef0  call    sub_1800B79C0
0x180092ef5  nop
0x180092ef6  call    sub_180096770
0x180092efb  test    al, al
0x180092efd  jz      short loc_180092F0B
0x180092eff  mov     rax, cs:qword_1802B00B0
0x180092f06  mov     ecx, [rax+4]
0x180092f09  jmp     short loc_180092F0D
0x180092f0b  mov     ecx, ebx
0x180092f0d  cmp     ecx, 2
0x180092f10  jnz     loc_180092FA6
0x180092f16  call    sub_180096770
0x180092f1b  test    al, al
0x180092f1d  jz      short loc_180092F2B
0x180092f1f  mov     rax, cs:qword_1802B00B0
0x180092f26  mov     ecx, [rax+4]
0x180092f29  jmp     short loc_180092F2D
0x180092f2b  mov     ecx, ebx
0x180092f2d  cmp     ecx, 2
0x180092f30  jnz     short loc_180092F3E
0x180092f32  movsxd  rax, [rbp+190h+var_28]
0x180092f39  shr     rax, 1
0x180092f3c  jmp     short loc_180092F44
0x180092f3e  mov     eax, [rbp+190h+var_28]
0x180092f44  mov     edx, eax
0x180092f46  mov     rcx, [rbp+190h+var_30]
0x180092f4d  mov     rax, cs:qword_1802B0038
0x180092f54  call    cs:__guard_dispatch_icall_fptr
0x180092f5a  test    eax, eax
0x180092f5c  jnz     loc_180093032
0x180092f62  call    cs:GetLastError
0x180092f68  mov     edi, eax
0x180092f6a  mov     ecx, 20h ; ' '; unsigned __int64
0x180092f6f  cmp     cs:dword_1802B0018, ebx
0x180092f75  jz      short loc_180092F7E
0x180092f77  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180092f7c  jmp     short loc_180092F84
0x180092f7e  call    cs:malloc
0x180092f84  mov     [rsp+290h+var_268], rax
0x180092f89  test    rax, rax
0x180092f8c  jz      short loc_180092FA1
0x180092f8e  mov     r8d, edi; int
0x180092f91  mov     edx, 2002Fh; unsigned int
0x180092f96  mov     rcx, rax; this
0x180092f99  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x180092f9e  mov     rbx, rax
0x180092fa1  jmp     loc_1800930D9
0x180092fa6  call    sub_180096770
0x180092fab  test    al, al
0x180092fad  jz      short loc_180092FBB
0x180092faf  mov     rax, cs:qword_1802B00B0
0x180092fb6  mov     ecx, [rax+4]
0x180092fb9  jmp     short loc_180092FBD
0x180092fbb  mov     ecx, ebx
0x180092fbd  cmp     ecx, 2
0x180092fc0  jnz     short loc_180092FCE
0x180092fc2  movsxd  rax, [rbp+190h+var_28]
0x180092fc9  shr     rax, 1
0x180092fcc  jmp     short loc_180092FD4
0x180092fce  mov     eax, [rbp+190h+var_28]
0x180092fd4  mov     edx, eax
0x180092fd6  mov     rcx, [rbp+190h+var_30]
0x180092fdd  mov     rax, cs:qword_1802B0038
0x180092fe4  call    cs:__guard_dispatch_icall_fptr
0x180092fea  test    eax, eax
0x180092fec  jnz     short loc_180093032
0x180092fee  call    cs:GetLastError
0x180092ff4  mov     edi, eax
0x180092ff6  mov     ecx, 20h ; ' '; unsigned __int64
0x180092ffb  cmp     cs:dword_1802B0018, ebx
0x180093001  jz      short loc_18009300A
0x180093003  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180093008  jmp     short loc_180093010
0x18009300a  call    cs:malloc
0x180093010  mov     [rsp+290h+var_268], rax
0x180093015  test    rax, rax
0x180093018  jz      short loc_18009302D
0x18009301a  mov     r8d, edi; int
0x18009301d  mov     edx, 2002Fh; unsigned int
0x180093022  mov     rcx, rax; this
0x180093025  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x18009302a  mov     rbx, rax
0x18009302d  jmp     loc_1800930D9
0x180093032  lea     rdx, [rsp+290h+var_230]; struct VstackStrLCP *
0x180093037  lea     rcx, [rsp+290h+var_260]; this
0x18009303c  call    ??0Vstring@@QEAA@AEBVVstackStrLCP@@@Z; Vstring::Vstring(VstackStrLCP const &)
0x180093041  nop
0x180093042  lea     rdx, [rsp+290h+var_260]; struct Vstring *
0x180093047  lea     rcx, [rsp+290h+var_258]; this
0x18009304c  call    ??0Vpath@@QEAA@AEBVVstring@@@Z; Vpath::Vpath(Vstring const &)
0x180093051  nop
0x180093052  mov     rdx, rax
0x180093055  mov     rcx, r14
0x180093058  call    ??4Vpath@@QEAAAEAV0@AEBV0@@Z; Vpath::operator=(Vpath const &)
0x18009305d  nop
0x18009305e  lea     rcx, [rsp+290h+var_258]; this
0x180093063  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x180093068  nop
0x180093069  lea     rax, [rsp+290h+var_258]
0x18009306e  mov     [rsp+290h+var_268], rax
0x180093073  mov     rcx, [rsp+290h+var_258]
0x180093078  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18009307c  or      edi, 0FFFFFFFFh
0x18009307f  mov     eax, edi
0x180093081  lock xadd [rcx], eax
0x180093085  lea     rsi, dword_1802AFD50
0x18009308c  add     eax, edi
0x18009308e  jnz     short loc_1800930AB
0x180093090  cmp     rcx, rsi
0x180093093  jz      short loc_1800930AB
0x180093095  cmp     cs:dword_1802B0018, ebx
0x18009309b  jz      short loc_1800930A4
0x18009309d  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800930a2  jmp     short loc_1800930AB
0x1800930a4  call    cs:free
0x1800930aa  nop
0x1800930ab  mov     rcx, [rsp+290h+var_260]
0x1800930b0  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800930b4  mov     eax, edi
0x1800930b6  lock xadd [rcx], eax
0x1800930ba  add     eax, edi
0x1800930bc  jnz     short loc_1800930D9
0x1800930be  cmp     rcx, rsi
0x1800930c1  jz      short loc_1800930D9
0x1800930c3  cmp     cs:dword_1802B0018, ebx
0x1800930c9  jz      short loc_1800930D2
0x1800930cb  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800930d0  jmp     short loc_1800930D9
0x1800930d2  call    cs:free
0x1800930d8  nop
0x1800930d9  lea     rcx, [rsp+290h+var_230]; this
0x1800930de  call    ??1VstackStrLCP@@QEAA@XZ_0; VstackStrLCP::~VstackStrLCP(void)
0x1800930e3  mov     rax, rbx
0x1800930e6  mov     rcx, [rbp+190h+var_20]
0x1800930ed  xor     rcx, rsp
0x1800930f0  call    sub_1801503E0
0x1800930f5  lea     r11, [rsp+290h+var_10]
0x1800930fd  mov     rbx, [r11+28h]
0x180093101  mov     rsi, [r11+30h]
0x180093105  mov     rsp, r11
0x180093108  pop     r14
0x18009310a  pop     rdi
0x18009310b  pop     rbp
0x18009310c  retn
```
