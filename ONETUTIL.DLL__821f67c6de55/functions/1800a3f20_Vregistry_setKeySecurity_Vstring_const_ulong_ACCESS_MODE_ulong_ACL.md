# Vregistry::setKeySecurity(Vstring const &,ulong,_ACCESS_MODE,ulong,_ACL *)

- ea: `0x1800a3f20`
- end: `0x1800a420b`
- name: `?setKeySecurity@Vregistry@@QEAAPEAVVstatus@@AEBVVstring@@KW4_ACCESS_MODE@@KPEAU_ACL@@@Z`
- size: `747`
- prototype: `struct Vstatus *__fastcall(Vregistry *__hidden this, const struct Vstring *, unsigned int, enum _ACCESS_MODE, unsigned int, struct _ACL *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a4210`
- `0x1800a5350`

## callees

- `0x18000e8cc`
- `0x18000eae4`
- `0x18000eba8`
- `0x1800410b0`
- `0x180083790`
- `0x1800838f0`
- `0x180096770`
- `0x180097024`
- `0x1800a3f20`
- `0x1800b93d0`
- `0x180103634`
- `0x180133d30`
- `0x18015170e`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800a41db`
- `KERNEL32!LocalFree` at `0x1800a41db`
- `KERNEL32!GetProcAddress` at `0x1800a3fda`
- `KERNEL32!GetProcAddress` at `0x1800a3fda`
- `KERNEL32!GetLastError` at `0x1800a4187`
- `KERNEL32!GetLastError` at `0x1800a4187`
- `ADVAPI32!RegSetKeySecurity` at `0x1800a412a`
- `ADVAPI32!RegSetKeySecurity` at `0x1800a412a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a400f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a400f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a405a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a4153`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a41a4`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a405a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a4153`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a41a4`

## string_xrefs

- `0x1800a3fbe`: `SetEntriesInAclW`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct Vstatus *__fastcall Vregistry::setKeySecurity(
        Vregistry *this,
        const struct Vstring *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        struct _ACL *a6)
{
  VgenericStatus *v10; // rdi
  __int64 v11; // rsi
  unsigned int v12; // ebx
  __int64 v13; // r15
  __int64 (__fastcall *v14)(__int64, _QWORD *, struct _ACL *, HLOCAL *); // rax
  LPCSTR v15; // rbx
  CHAR *v16; // rcx
  __int64 v17; // rdi
  CHAR *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rbx
  HLOCAL v21; // r15
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int16 v25; // cx
  __int64 v26; // rbx
  DWORD LastError; // edi
  CHAR *v28; // rax
  LPCSTR lpProcName; // [rsp+38h] [rbp-49h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-41h] BYREF
  __int64 v32; // [rsp+48h] [rbp-39h] BYREF
  _QWORD v33[7]; // [rsp+50h] [rbp-31h] BYREF
  _BYTE pSecurityDescriptor[2]; // [rsp+88h] [rbp+7h] BYREF
  __int16 v35; // [rsp+8Ah] [rbp+9h]

  v33[6] = -2;
  memset(v33, 0, 0x30u);
  Vstring::getUnicode(a2, &v32);
  v33[0] = __PAIR64__(a4, a3);
  LODWORD(v33[1]) = a5;
  HIDWORD(v33[3]) = 1;
  LODWORD(v33[4]) = 0;
  v33[5] = v32;
  v10 = 0;
  hMem = 0;
  v11 = sub_180097024();
  if ( !(unsigned __int8)sub_18000E8CC(v11) )
  {
    v12 = 1114;
LABEL_12:
    v17 = *((_QWORD *)this + 1);
    if ( dword_1802B0018 )
      v18 = (CHAR *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v18 = (CHAR *)malloc(0x20u);
    lpProcName = v18;
    if ( v18 )
    {
LABEL_16:
      v10 = VgenericStatus::VgenericStatus((VgenericStatus *)v18, 0x30070u, 0, v12, v17);
      goto LABEL_39;
    }
    v10 = 0;
    goto LABEL_39;
  }
  v13 = *(_QWORD *)(v11 + 64);
  v14 = *(__int64 (__fastcall **)(__int64, _QWORD *, struct _ACL *, HLOCAL *))v11;
  if ( !*(_QWORD *)v11 )
  {
    RWCString::RWCString((RWCString *)&lpProcName, "SetEntriesInAclW");
    v15 = lpProcName;
    *(_QWORD *)v11 = GetProcAddress(*(HMODULE *)(v13 + 16), lpProcName);
    v16 = (CHAR *)(v15 - 12);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 - 3, 0xFFFFFFFF) == 1 && v16 != (CHAR *)&dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v16);
      else
        free(v16);
    }
    v14 = *(__int64 (__fastcall **)(__int64, _QWORD *, struct _ACL *, HLOCAL *))v11;
    if ( !*(_QWORD *)v11 )
    {
      v12 = 1157;
      goto LABEL_12;
    }
  }
  v12 = v14(1, v33, a6, &hMem);
  if ( v12 )
    goto LABEL_12;
  v19 = sub_180097024();
  if ( !(unsigned int)sub_18000EAE4(v19, pSecurityDescriptor)
    || (v20 = sub_180097024(), v21 = hMem, !(unsigned __int8)sub_18000E8CC(v20))
    || !(unsigned __int8)sub_18000EBA8(v20 + 16, *(_QWORD *)(v20 + 64))
    || !(*(unsigned int (__fastcall **)(_BYTE *, __int64, HLOCAL))(v20 + 16))(pSecurityDescriptor, 1, v21) )
  {
    v26 = *((_QWORD *)this + 1);
    LastError = GetLastError();
    if ( dword_1802B0018 )
      v28 = (CHAR *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v28 = (CHAR *)malloc(0x20u);
    lpProcName = v28;
    if ( v28 )
      v10 = VgenericStatus::VgenericStatus((VgenericStatus *)v28, 0x30070u, 0, LastError, v26);
    else
      v10 = 0;
    goto LABEL_39;
  }
  if ( (unsigned __int8)sub_180096770(v23, v22, v24) )
    v25 = *(_WORD *)(qword_1802B00B0 + 12);
  else
    v25 = 0;
  if ( v25 > 4 )
    v35 |= 0x500u;
  v12 = RegSetKeySecurity(*((HKEY *)this + 3), 4u, pSecurityDescriptor);
  if ( v12 )
  {
    v17 = *((_QWORD *)this + 1);
    if ( dword_1802B0018 )
      v18 = (CHAR *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v18 = (CHAR *)malloc(0x20u);
    lpProcName = v18;
    if ( v18 )
      goto LABEL_16;
    v10 = 0;
  }
LABEL_39:
  if ( hMem )
    LocalFree(hMem);
  Vwstring::~Vwstring((Vwstring *)&v32);
  return v10;
}

```

## disassembly

```asm
0x1800a3f20  mov     rax, rsp
0x1800a3f23  push    rbp
0x1800a3f24  push    r14
0x1800a3f26  push    r15
0x1800a3f28  lea     rbp, [rax-4Fh]
0x1800a3f2c  sub     rsp, 0B0h
0x1800a3f33  mov     [rbp+47h+var_48], 0FFFFFFFFFFFFFFFEh
0x1800a3f3b  mov     [rax+8], rbx
0x1800a3f3f  mov     [rax+10h], rsi
0x1800a3f43  mov     [rax+18h], rdi
0x1800a3f47  mov     esi, r9d
0x1800a3f4a  mov     edi, r8d
0x1800a3f4d  mov     rbx, rdx
0x1800a3f50  mov     r14, rcx
0x1800a3f53  xor     edx, edx; Val
0x1800a3f55  lea     r8d, [rdx+30h]; Size
0x1800a3f59  lea     rcx, [rbp+47h+var_78]; void *
0x1800a3f5d  call    memset
0x1800a3f62  lea     rdx, [rbp+47h+var_80]
0x1800a3f66  mov     rcx, rbx
0x1800a3f69  call    ?getUnicode@Vstring@@QEBA?AVVwstring@@XZ; Vstring::getUnicode(void)
0x1800a3f6e  nop
0x1800a3f6f  mov     [rbp+47h+var_78], edi
0x1800a3f72  mov     [rbp+47h+var_74], esi
0x1800a3f75  mov     eax, [rbp+47h+arg_20]
0x1800a3f78  mov     [rbp+47h+var_70], eax
0x1800a3f7b  mov     [rbp+47h+var_5C], 1
0x1800a3f82  and     [rbp+47h+var_58], 0
0x1800a3f86  mov     rax, [rbp+47h+var_80]
0x1800a3f8a  mov     [rbp+47h+var_50], rax
0x1800a3f8e  xor     edi, edi
0x1800a3f90  and     [rbp+47h+hMem], rdi
0x1800a3f94  call    sub_180097024
0x1800a3f99  mov     rsi, rax
0x1800a3f9c  mov     rcx, rax
0x1800a3f9f  call    sub_18000E8CC
0x1800a3fa4  test    al, al
0x1800a3fa6  jnz     short loc_1800A3FB2
0x1800a3fa8  mov     ebx, 45Ah
0x1800a3fad  jmp     loc_1800A4041
0x1800a3fb2  mov     r15, [rsi+40h]
0x1800a3fb6  mov     rax, [rsi]
0x1800a3fb9  test    rax, rax
0x1800a3fbc  jnz     short loc_1800A4024
0x1800a3fbe  lea     rdx, aSetentriesinac; "SetEntriesInAclW"
0x1800a3fc5  lea     rcx, [rbp+47h+lpProcName]; this
0x1800a3fc9  call    ??0RWCString@@QEAA@PEBD@Z; RWCString::RWCString(char const *)
0x1800a3fce  nop
0x1800a3fcf  mov     rbx, [rbp+47h+lpProcName]
0x1800a3fd3  mov     rdx, rbx; lpProcName
0x1800a3fd6  mov     rcx, [r15+10h]; hModule
0x1800a3fda  call    cs:GetProcAddress
0x1800a3fe0  mov     [rsi], rax
0x1800a3fe3  lea     rcx, [rbx-0Ch]; void *
0x1800a3fe7  or      eax, 0FFFFFFFFh
0x1800a3fea  lock xadd [rcx], eax
0x1800a3fee  cmp     eax, 1
0x1800a3ff1  jnz     short loc_1800A4015
0x1800a3ff3  lea     rax, dword_1802AFD50
0x1800a3ffa  cmp     rcx, rax
0x1800a3ffd  jz      short loc_1800A4015
0x1800a3fff  cmp     cs:dword_1802B0018, 0
0x1800a4006  jz      short loc_1800A400F
0x1800a4008  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800a400d  jmp     short loc_1800A4015
0x1800a400f  call    cs:free
0x1800a4015  mov     rax, [rsi]
0x1800a4018  test    rax, rax
0x1800a401b  jnz     short loc_1800A4024
0x1800a401d  mov     ebx, 485h
0x1800a4022  jmp     short loc_1800A4041
0x1800a4024  lea     r9, [rbp+47h+hMem]
0x1800a4028  mov     r8, [rbp+47h+arg_28]
0x1800a402c  lea     rdx, [rbp+47h+var_78]
0x1800a4030  mov     ecx, 1
0x1800a4035  call    cs:__guard_dispatch_icall_fptr
0x1800a403b  mov     ebx, eax
0x1800a403d  test    eax, eax
0x1800a403f  jz      short loc_1800A408D
0x1800a4041  mov     rdi, [r14+8]
0x1800a4045  mov     ecx, 20h ; ' '; unsigned __int64
0x1800a404a  cmp     cs:dword_1802B0018, 0
0x1800a4051  jz      short loc_1800A405A
0x1800a4053  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800a4058  jmp     short loc_1800A4060
0x1800a405a  call    cs:malloc
0x1800a4060  mov     [rbp+47h+lpProcName], rax
0x1800a4064  test    rax, rax
0x1800a4067  jz      short loc_1800A4086
0x1800a4069  mov     [rsp+0C0h+var_A0], rdi
0x1800a406e  mov     r9d, ebx
0x1800a4071  xor     r8d, r8d; int
0x1800a4074  mov     edx, 30070h; unsigned int
0x1800a4079  mov     rcx, rax; this
0x1800a407c  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x1800a4081  mov     rdi, rax
0x1800a4084  jmp     short loc_1800A4088
0x1800a4086  xor     edi, edi
0x1800a4088  jmp     loc_1800A41D2
0x1800a408d  call    sub_180097024
0x1800a4092  lea     rdx, [rbp+47h+pSecurityDescriptor]
0x1800a4096  mov     rcx, rax
0x1800a4099  call    sub_18000EAE4
0x1800a409e  test    eax, eax
0x1800a40a0  jz      loc_1800A4183
0x1800a40a6  call    sub_180097024
0x1800a40ab  mov     rbx, rax
0x1800a40ae  mov     r15, [rbp+47h+hMem]
0x1800a40b2  mov     rcx, rax
0x1800a40b5  call    sub_18000E8CC
0x1800a40ba  test    al, al
0x1800a40bc  jz      loc_1800A4183
0x1800a40c2  mov     rdx, [rbx+40h]
0x1800a40c6  lea     rcx, [rbx+10h]
0x1800a40ca  call    sub_18000EBA8
0x1800a40cf  test    al, al
0x1800a40d1  jz      loc_1800A4183
0x1800a40d7  xor     r9d, r9d
0x1800a40da  mov     r8, r15
0x1800a40dd  lea     edx, [r9+1]
0x1800a40e1  lea     rcx, [rbp+47h+pSecurityDescriptor]
0x1800a40e5  mov     rax, [rbx+10h]
0x1800a40e9  call    cs:__guard_dispatch_icall_fptr
0x1800a40ef  test    eax, eax
0x1800a40f1  jz      loc_1800A4183
0x1800a40f7  call    sub_180096770
0x1800a40fc  test    al, al
0x1800a40fe  jz      short loc_1800A410D
0x1800a4100  mov     rax, cs:qword_1802B00B0
0x1800a4107  movzx   ecx, word ptr [rax+0Ch]
0x1800a410b  jmp     short loc_1800A410F
0x1800a410d  xor     ecx, ecx
0x1800a410f  mov     edx, 4; SecurityInformation
0x1800a4114  cmp     cx, dx
0x1800a4117  jle     short loc_1800A4122
0x1800a4119  mov     eax, 500h
0x1800a411e  or      [rbp+47h+var_3E], ax
0x1800a4122  lea     r8, [rbp+47h+pSecurityDescriptor]; pSecurityDescriptor
0x1800a4126  mov     rcx, [r14+18h]; hKey
0x1800a412a  call    cs:RegSetKeySecurity
0x1800a4130  mov     ebx, eax
0x1800a4132  test    eax, eax
0x1800a4134  jz      loc_1800A41D2
0x1800a413a  mov     rdi, [r14+8]
0x1800a413e  mov     ecx, 20h ; ' '; unsigned __int64
0x1800a4143  cmp     cs:dword_1802B0018, 0
0x1800a414a  jz      short loc_1800A4153
0x1800a414c  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800a4151  jmp     short loc_1800A4159
0x1800a4153  call    cs:malloc
0x1800a4159  mov     [rbp+47h+lpProcName], rax
0x1800a415d  test    rax, rax
0x1800a4160  jz      short loc_1800A417F
0x1800a4162  mov     [rsp+0C0h+var_A0], rdi
0x1800a4167  mov     r9d, ebx
0x1800a416a  xor     r8d, r8d; int
0x1800a416d  mov     edx, 30070h; unsigned int
0x1800a4172  mov     rcx, rax; this
0x1800a4175  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x1800a417a  mov     rdi, rax
0x1800a417d  jmp     short loc_1800A4181
0x1800a417f  xor     edi, edi
0x1800a4181  jmp     short loc_1800A41D2
0x1800a4183  mov     rbx, [r14+8]
0x1800a4187  call    cs:GetLastError
0x1800a418d  mov     edi, eax
0x1800a418f  mov     ecx, 20h ; ' '; unsigned __int64
0x1800a4194  cmp     cs:dword_1802B0018, 0
0x1800a419b  jz      short loc_1800A41A4
0x1800a419d  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800a41a2  jmp     short loc_1800A41AA
0x1800a41a4  call    cs:malloc
0x1800a41aa  mov     [rbp+47h+lpProcName], rax
0x1800a41ae  test    rax, rax
0x1800a41b1  jz      short loc_1800A41D0
0x1800a41b3  mov     [rsp+0C0h+var_A0], rbx
0x1800a41b8  mov     r9d, edi
0x1800a41bb  xor     r8d, r8d; int
0x1800a41be  mov     edx, 30070h; unsigned int
0x1800a41c3  mov     rcx, rax; this
0x1800a41c6  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x1800a41cb  mov     rdi, rax
0x1800a41ce  jmp     short loc_1800A41D2
0x1800a41d0  xor     edi, edi
0x1800a41d2  mov     rcx, [rbp+47h+hMem]; hMem
0x1800a41d6  test    rcx, rcx
0x1800a41d9  jz      short loc_1800A41E2
0x1800a41db  call    cs:LocalFree
0x1800a41e1  nop
0x1800a41e2  lea     rcx, [rbp+47h+var_80]; this
0x1800a41e6  call    ??1Vwstring@@QEAA@XZ_0; Vwstring::~Vwstring(void)
0x1800a41eb  mov     rax, rdi
0x1800a41ee  lea     r11, [rsp+0C0h+var_10]
0x1800a41f6  mov     rbx, [r11+20h]
0x1800a41fa  mov     rsi, [r11+28h]
0x1800a41fe  mov     rdi, [r11+30h]
0x1800a4202  mov     rsp, r11
0x1800a4205  pop     r15
0x1800a4207  pop     r14
0x1800a4209  pop     rbp
0x1800a420a  retn
```
