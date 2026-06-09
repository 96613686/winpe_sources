# createUniqueTempFile(Vstring,Vstring,Vstring,long,long,long,Vstring *,void * *)

- ea: `0x18006fb10`
- end: `0x18006ff19`
- name: `?createUniqueTempFile@@YAPEAVVstatus@@VVstring@@00JJJPEAV2@PEAPEAX@Z`
- size: `1033`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18006f9e0`

## callees

- `0x18006c2a0`
- `0x18006fb10`
- `0x180070440`
- `0x1800838f0`
- `0x1800b54c0`
- `0x1800b5d80`
- `0x1800b6680`
- `0x1801342d0`
- `0x1801503e0`
- `0x18015197d`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18006fbc6`
- `KERNEL32!GetCurrentProcessId` at `0x18006fbc6`
- `KERNEL32!GetCurrentThreadId` at `0x18006fbe3`
- `KERNEL32!GetCurrentThreadId` at `0x18006fbe3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18006fe5d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18006fe94`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18006fec0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18006feed`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18006fe5d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18006fe94`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18006fec0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18006feed`
- `ole32!CoCreateGuid` at `0x18006fbc0`
- `ole32!CoCreateGuid` at `0x18006fbc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct Vstatus *__fastcall createUniqueTempFile(
        const void **a1,
        const void **a2,
        const void **a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        RWCString *a7,
        void **a8)
{
  struct Vstatus *v11; // rdi
  unsigned int v12; // esi
  DWORD v13; // ebx
  unsigned int v14; // eax
  const void *v15; // rdi
  size_t v16; // rbx
  unsigned int v17; // eax
  __int64 v18; // rcx
  const void *v19; // rdi
  size_t v20; // rbx
  unsigned int v21; // eax
  unsigned int v22; // eax
  __int64 v23; // rcx
  const void *v24; // rdi
  size_t v25; // rbx
  unsigned int v26; // edx
  struct Vstatus *v27; // rax
  int *v28; // rcx
  int *v29; // rcx
  int *v30; // rcx
  struct _SECURITY_ATTRIBUTES *v33; // [rsp+58h] [rbp-A8h]
  GUID pguid; // [rsp+80h] [rbp-80h] BYREF
  void *Block; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v36[516]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v37; // [rsp+29Ch] [rbp+19Ch]
  unsigned int v38; // [rsp+2A0h] [rbp+1A0h]

  v11 = 0;
  v12 = 0;
  Block = v36;
  v37 = 0;
  v38 = 512;
  pguid = (GUID)xmmword_180176AD0;
  v33 = (struct _SECURITY_ATTRIBUTES *)sub_18006C2A0();
  CoCreateGuid(&pguid);
  v13 = (GetCurrentProcessId() % 0xFFF1) << 16;
  pguid.Data1 = v13 | (GetCurrentThreadId() % 0xFFF1);
  do
  {
    ++v12;
    if ( v11 )
      (**(void (__fastcall ***)(struct Vstatus *, __int64))v11)(v11, 1);
    v14 = 0;
    v37 = 0;
    v15 = *a1;
    v16 = *((unsigned int *)*a1 - 1);
    if ( (unsigned int)v16 > v38 )
    {
      VstackBuffer512::reallocate((VstackBuffer512 *)&Block, v16);
      v14 = v37;
    }
    memcpy((char *)Block + v14, v15, v16);
    v17 = v16 + v37;
    v37 = v17;
    if ( v17 == v38 )
    {
      VstackBuffer512::reallocate((VstackBuffer512 *)&Block, 1u);
      v17 = v37;
    }
    *((_BYTE *)Block + v17) = 92;
    v18 = v37 + 1;
    v37 = v18;
    v19 = *a2;
    v20 = *((unsigned int *)*a2 - 1);
    if ( (int)v18 + (int)v20 > v38 )
    {
      VstackBuffer512::reallocate((VstackBuffer512 *)&Block, v20);
      v18 = v37;
    }
    memcpy((char *)Block + v18, v19, v20);
    v37 += v20;
    VstackBuffer512::appendPackedGuid((VstackBuffer512 *)&Block, &pguid);
    v21 = v37;
    if ( v37 > 0xF5 )
      v21 = 245;
    v37 = v21;
    if ( v21 == v38 )
    {
      VstackBuffer512::reallocate((VstackBuffer512 *)&Block, 1u);
      v21 = v37;
    }
    *((_BYTE *)Block + v21) = 95;
    ++v37;
    VstackBuffer512::appendUintBase10((VstackBuffer512 *)&Block, v12);
    v22 = v37;
    if ( v37 == v38 )
    {
      VstackBuffer512::reallocate((VstackBuffer512 *)&Block, 1u);
      v22 = v37;
    }
    *((_BYTE *)Block + v22) = 46;
    v23 = v37 + 1;
    v37 = v23;
    v24 = *a3;
    v25 = *((unsigned int *)*a3 - 1);
    if ( (int)v23 + (int)v25 > v38 )
    {
      VstackBuffer512::reallocate((VstackBuffer512 *)&Block, v25);
      v23 = v37;
    }
    memcpy((char *)Block + v23, v24, v25);
    v37 += v25;
    v26 = v37;
    *((_BYTE *)Block + v37) = 0;
    RWCString::replace(a7, 0, *(_DWORD *)(*(_QWORD *)a7 - 4LL), (const char *)Block, v26);
    v27 = VcreateFileUnimpersonated(a7, a4, a5, v33, 1u, a6, (void *)0xFFFFFFFFFFFFFFFFLL, a8);
    v11 = v27;
  }
  while ( v27
       && ((*(unsigned int (__fastcall **)(struct Vstatus *))(*(_QWORD *)v27 + 8LL))(v27) == 131089
        || (*(unsigned int (__fastcall **)(struct Vstatus *))(*(_QWORD *)v11 + 8LL))(v11) == 131165)
       && v12 != 100 );
  if ( Block != v36 )
  {
    if ( dword_1802B0018 )
      COWSAllocator::Free(Block);
    else
      free(Block);
  }
  v28 = (int *)((char *)*a1 - 12);
  if ( _InterlockedExchangeAdd(v28, 0xFFFFFFFF) == 1 && v28 != &dword_1802AFD50 )
  {
    if ( dword_1802B0018 )
      COWSAllocator::Free(v28);
    else
      free(v28);
  }
  v29 = (int *)((char *)*a2 - 12);
  if ( _InterlockedExchangeAdd(v29, 0xFFFFFFFF) == 1 && v29 != &dword_1802AFD50 )
  {
    if ( dword_1802B0018 )
      COWSAllocator::Free(v29);
    else
      free(v29);
  }
  v30 = (int *)((char *)*a3 - 12);
  if ( _InterlockedExchangeAdd(v30, 0xFFFFFFFF) == 1 && v30 != &dword_1802AFD50 )
  {
    if ( dword_1802B0018 )
      COWSAllocator::Free(v30);
    else
      free(v30);
  }
  return v11;
}

```

## disassembly

```asm
0x18006fb10  push    rbp
0x18006fb12  push    rbx
0x18006fb13  push    rsi
0x18006fb14  push    rdi
0x18006fb15  push    r12
0x18006fb17  push    r13
0x18006fb19  push    r14
0x18006fb1b  push    r15
0x18006fb1d  lea     rbp, [rsp-1C8h]
0x18006fb25  sub     rsp, 2C8h
0x18006fb2c  mov     [rsp+300h+var_2A0], 0FFFFFFFFFFFFFFFEh
0x18006fb35  mov     rax, cs:__security_cookie
0x18006fb3c  xor     rax, rsp
0x18006fb3f  mov     [rbp+200h+var_50], rax
0x18006fb46  mov     [rsp+300h+var_2B8], r9d
0x18006fb4b  mov     r12, r8
0x18006fb4e  mov     r15, rdx
0x18006fb51  mov     r14, rcx
0x18006fb54  mov     [rsp+300h+var_298], rcx
0x18006fb59  mov     [rsp+300h+var_290], rdx
0x18006fb5e  mov     [rsp+300h+var_288], r8
0x18006fb63  mov     eax, [rbp+200h+arg_20]
0x18006fb69  mov     [rsp+300h+var_2BC], eax
0x18006fb6d  mov     eax, [rbp+200h+arg_28]
0x18006fb73  mov     [rsp+300h+var_2C0], eax
0x18006fb77  mov     r13, [rbp+200h+arg_30]
0x18006fb7e  mov     rax, [rbp+200h+arg_38]
0x18006fb85  mov     [rsp+300h+var_2B0], rax
0x18006fb8a  xor     edi, edi
0x18006fb8c  xor     esi, esi
0x18006fb8e  lea     rax, [rbp+200h+var_268]
0x18006fb92  mov     [rbp+200h+Block], rax
0x18006fb96  and     [rbp+200h+var_64], esi
0x18006fb9c  mov     [rbp+200h+var_60], 200h
0x18006fba6  movups  xmm0, cs:xmmword_180176AD0
0x18006fbad  movdqu  xmmword ptr [rbp+200h+pguid.Data1], xmm0
0x18006fbb2  call    sub_18006C2A0
0x18006fbb7  mov     [rsp+300h+var_2A8], rax
0x18006fbbc  lea     rcx, [rbp+200h+pguid]; pguid
0x18006fbc0  call    cs:CoCreateGuid
0x18006fbc6  call    cs:GetCurrentProcessId
0x18006fbcc  mov     ebx, eax
0x18006fbce  mov     eax, 80078071h
0x18006fbd3  mul     ebx
0x18006fbd5  shr     edx, 0Fh
0x18006fbd8  imul    ecx, edx, 0FFF1h
0x18006fbde  sub     ebx, ecx
0x18006fbe0  shl     ebx, 10h
0x18006fbe3  call    cs:GetCurrentThreadId
0x18006fbe9  mov     r8d, eax
0x18006fbec  mov     eax, 80078071h
0x18006fbf1  mul     r8d
0x18006fbf4  shr     edx, 0Fh
0x18006fbf7  imul    ecx, edx, 0FFF1h
0x18006fbfd  sub     r8d, ecx
0x18006fc00  or      r8d, ebx
0x18006fc03  mov     [rbp+200h+pguid.Data1], r8d
0x18006fc07  xor     ebx, ebx
0x18006fc09  inc     esi
0x18006fc0b  test    rdi, rdi
0x18006fc0e  jz      short loc_18006FC24
0x18006fc10  mov     rax, [rdi]
0x18006fc13  mov     edx, 1
0x18006fc18  mov     rcx, rdi
0x18006fc1b  mov     rax, [rax]
0x18006fc1e  call    cs:__guard_dispatch_icall_fptr
0x18006fc24  mov     eax, ebx
0x18006fc26  mov     [rbp+200h+var_64], ebx
0x18006fc2c  mov     rdi, [r14]
0x18006fc2f  mov     ebx, [rdi-4]
0x18006fc32  cmp     ebx, [rbp+200h+var_60]
0x18006fc38  jbe     short loc_18006FC4B
0x18006fc3a  mov     edx, ebx; unsigned int
0x18006fc3c  lea     rcx, [rbp+200h+Block]; this
0x18006fc40  call    ?reallocate@VstackBuffer512@@AEAAXI@Z; VstackBuffer512::reallocate(uint)
0x18006fc45  mov     eax, [rbp+200h+var_64]
0x18006fc4b  mov     r8, rbx; Size
0x18006fc4e  mov     ecx, eax
0x18006fc50  add     rcx, [rbp+200h+Block]; void *
0x18006fc54  mov     rdx, rdi; Src
0x18006fc57  call    memcpy
0x18006fc5c  mov     eax, [rbp+200h+var_64]
0x18006fc62  add     eax, ebx
0x18006fc64  mov     [rbp+200h+var_64], eax
0x18006fc6a  cmp     eax, [rbp+200h+var_60]
0x18006fc70  jnz     short loc_18006FC86
0x18006fc72  mov     edx, 1; unsigned int
0x18006fc77  lea     rcx, [rbp+200h+Block]; this
0x18006fc7b  call    ?reallocate@VstackBuffer512@@AEAAXI@Z; VstackBuffer512::reallocate(uint)
0x18006fc80  mov     eax, [rbp+200h+var_64]
0x18006fc86  mov     ecx, eax
0x18006fc88  mov     rax, [rbp+200h+Block]
0x18006fc8c  mov     byte ptr [rcx+rax], 5Ch ; '\'
0x18006fc90  mov     ecx, [rbp+200h+var_64]
0x18006fc96  inc     ecx
0x18006fc98  mov     [rbp+200h+var_64], ecx
0x18006fc9e  mov     rdi, [r15]
0x18006fca1  mov     ebx, [rdi-4]
0x18006fca4  lea     eax, [rcx+rbx]
0x18006fca7  cmp     eax, [rbp+200h+var_60]
0x18006fcad  jbe     short loc_18006FCC0
0x18006fcaf  mov     edx, ebx; unsigned int
0x18006fcb1  lea     rcx, [rbp+200h+Block]; this
0x18006fcb5  call    ?reallocate@VstackBuffer512@@AEAAXI@Z; VstackBuffer512::reallocate(uint)
0x18006fcba  mov     ecx, [rbp+200h+var_64]
0x18006fcc0  mov     r8, rbx; Size
0x18006fcc3  add     rcx, [rbp+200h+Block]; void *
0x18006fcc7  mov     rdx, rdi; Src
0x18006fcca  call    memcpy
0x18006fccf  add     [rbp+200h+var_64], ebx
0x18006fcd5  lea     rdx, [rbp+200h+pguid]; struct _GUID *
0x18006fcd9  lea     rcx, [rbp+200h+Block]; this
0x18006fcdd  call    ?appendPackedGuid@VstackBuffer512@@QEAAAEAV1@PEBU_GUID@@@Z; VstackBuffer512::appendPackedGuid(_GUID const *)
0x18006fce2  mov     eax, [rbp+200h+var_64]
0x18006fce8  mov     ecx, 0F5h
0x18006fced  cmp     eax, ecx
0x18006fcef  cmova   eax, ecx
0x18006fcf2  mov     [rbp+200h+var_64], eax
0x18006fcf8  cmp     eax, [rbp+200h+var_60]
0x18006fcfe  jnz     short loc_18006FD14
0x18006fd00  mov     edx, 1; unsigned int
0x18006fd05  lea     rcx, [rbp+200h+Block]; this
0x18006fd09  call    ?reallocate@VstackBuffer512@@AEAAXI@Z; VstackBuffer512::reallocate(uint)
0x18006fd0e  mov     eax, [rbp+200h+var_64]
0x18006fd14  mov     ecx, eax
0x18006fd16  mov     rax, [rbp+200h+Block]
0x18006fd1a  mov     byte ptr [rcx+rax], 5Fh ; '_'
0x18006fd1e  inc     [rbp+200h+var_64]
0x18006fd24  mov     edx, esi; unsigned int
0x18006fd26  lea     rcx, [rbp+200h+Block]; this
0x18006fd2a  call    ?appendUintBase10@VstackBuffer512@@QEAAIK@Z; VstackBuffer512::appendUintBase10(ulong)
0x18006fd2f  mov     eax, [rbp+200h+var_64]
0x18006fd35  cmp     eax, [rbp+200h+var_60]
0x18006fd3b  jnz     short loc_18006FD51
0x18006fd3d  mov     edx, 1; unsigned int
0x18006fd42  lea     rcx, [rbp+200h+Block]; this
0x18006fd46  call    ?reallocate@VstackBuffer512@@AEAAXI@Z; VstackBuffer512::reallocate(uint)
0x18006fd4b  mov     eax, [rbp+200h+var_64]
0x18006fd51  mov     ecx, eax
0x18006fd53  mov     rax, [rbp+200h+Block]
0x18006fd57  mov     byte ptr [rcx+rax], 2Eh ; '.'
0x18006fd5b  mov     ecx, [rbp+200h+var_64]
0x18006fd61  inc     ecx
0x18006fd63  mov     [rbp+200h+var_64], ecx
0x18006fd69  mov     rdi, [r12]
0x18006fd6d  mov     ebx, [rdi-4]
0x18006fd70  lea     eax, [rcx+rbx]
0x18006fd73  cmp     eax, [rbp+200h+var_60]
0x18006fd79  jbe     short loc_18006FD8C
0x18006fd7b  mov     edx, ebx; unsigned int
0x18006fd7d  lea     rcx, [rbp+200h+Block]; this
0x18006fd81  call    ?reallocate@VstackBuffer512@@AEAAXI@Z; VstackBuffer512::reallocate(uint)
0x18006fd86  mov     ecx, [rbp+200h+var_64]
0x18006fd8c  mov     r8, rbx; Size
0x18006fd8f  add     rcx, [rbp+200h+Block]; void *
0x18006fd93  mov     rdx, rdi; Src
0x18006fd96  call    memcpy
0x18006fd9b  mov     edx, [rbp+200h+var_64]
0x18006fda1  add     edx, ebx
0x18006fda3  mov     [rbp+200h+var_64], edx
0x18006fda9  mov     rax, [rbp+200h+Block]
0x18006fdad  xor     ebx, ebx
0x18006fdaf  mov     [rdx+rax], bl
0x18006fdb2  mov     rax, [r13+0]
0x18006fdb6  mov     [rsp+300h+var_2E0], edx; unsigned int
0x18006fdba  mov     r9, [rbp+200h+Block]; char *
0x18006fdbe  mov     r8d, [rax-4]; unsigned int
0x18006fdc2  xor     edx, edx; unsigned int
0x18006fdc4  mov     rcx, r13; this
0x18006fdc7  call    ?replace@RWCString@@QEAAAEAV1@IIPEBDI@Z; RWCString::replace(uint,uint,char const *,uint)
0x18006fdcc  mov     rax, [rsp+300h+var_2B0]
0x18006fdd1  mov     [rsp+300h+var_2C8], rax; void **
0x18006fdd6  or      [rsp+300h+var_2D0], 0FFFFFFFFFFFFFFFFh
0x18006fddc  mov     eax, [rsp+300h+var_2C0]
0x18006fde0  mov     [rsp+300h+var_2D8], eax; unsigned int
0x18006fde4  mov     [rsp+300h+var_2E0], 1; DWORD
0x18006fdec  mov     r9, [rsp+300h+var_2A8]; struct _SECURITY_ATTRIBUTES *
0x18006fdf1  mov     r8d, [rsp+300h+var_2BC]; unsigned int
0x18006fdf6  mov     edx, [rsp+300h+var_2B8]; unsigned int
0x18006fdfa  mov     rcx, r13; struct Vstring *
0x18006fdfd  call    ?VcreateFileUnimpersonated@@YAPEAVVstatus@@PEBVVstring@@KKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEAPEAX@Z; VcreateFileUnimpersonated(Vstring const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,void * *)
0x18006fe02  mov     rdi, rax
0x18006fe05  test    rax, rax
0x18006fe08  jz      short loc_18006FE41
0x18006fe0a  mov     rax, [rax]
0x18006fe0d  mov     rcx, rdi
0x18006fe10  mov     rax, [rax+8]
0x18006fe14  call    cs:__guard_dispatch_icall_fptr
0x18006fe1a  cmp     eax, 20011h
0x18006fe1f  jz      short loc_18006FE38
0x18006fe21  mov     rax, [rdi]
0x18006fe24  mov     rcx, rdi
0x18006fe27  mov     rax, [rax+8]
0x18006fe2b  call    cs:__guard_dispatch_icall_fptr
0x18006fe31  cmp     eax, 2005Dh
0x18006fe36  jnz     short loc_18006FE41
0x18006fe38  cmp     esi, 64h ; 'd'
0x18006fe3b  jnz     loc_18006FC09
0x18006fe41  lea     rax, [rbp+200h+var_268]
0x18006fe45  mov     rcx, [rbp+200h+Block]; void *
0x18006fe49  cmp     rcx, rax
0x18006fe4c  jz      short loc_18006FE64
0x18006fe4e  cmp     cs:dword_1802B0018, ebx
0x18006fe54  jz      short loc_18006FE5D
0x18006fe56  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18006fe5b  jmp     short loc_18006FE64
0x18006fe5d  call    cs:free
0x18006fe63  nop
0x18006fe64  mov     rcx, [r14]
0x18006fe67  sub     rcx, 0Ch; void *
0x18006fe6b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006fe6f  mov     eax, esi
0x18006fe71  lock xadd [rcx], eax
0x18006fe75  lea     r14, dword_1802AFD50
0x18006fe7c  add     eax, esi
0x18006fe7e  jnz     short loc_18006FE9B
0x18006fe80  cmp     rcx, r14
0x18006fe83  jz      short loc_18006FE9B
0x18006fe85  cmp     cs:dword_1802B0018, ebx
0x18006fe8b  jz      short loc_18006FE94
0x18006fe8d  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18006fe92  jmp     short loc_18006FE9B
0x18006fe94  call    cs:free
0x18006fe9a  nop
0x18006fe9b  mov     rcx, [r15]
0x18006fe9e  sub     rcx, 0Ch; void *
0x18006fea2  mov     eax, esi
0x18006fea4  lock xadd [rcx], eax
0x18006fea8  add     eax, esi
0x18006feaa  jnz     short loc_18006FEC7
0x18006feac  cmp     rcx, r14
0x18006feaf  jz      short loc_18006FEC7
0x18006feb1  cmp     cs:dword_1802B0018, ebx
0x18006feb7  jz      short loc_18006FEC0
0x18006feb9  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18006febe  jmp     short loc_18006FEC7
0x18006fec0  call    cs:free
0x18006fec6  nop
0x18006fec7  mov     rcx, [r12]
0x18006fecb  sub     rcx, 0Ch; void *
0x18006fecf  mov     eax, esi
0x18006fed1  lock xadd [rcx], eax
0x18006fed5  add     eax, esi
0x18006fed7  jnz     short loc_18006FEF3
0x18006fed9  cmp     rcx, r14
0x18006fedc  jz      short loc_18006FEF3
0x18006fede  cmp     cs:dword_1802B0018, ebx
0x18006fee4  jz      short loc_18006FEED
0x18006fee6  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18006feeb  jmp     short loc_18006FEF3
0x18006feed  call    cs:free
0x18006fef3  mov     rax, rdi
0x18006fef6  mov     rcx, [rbp+200h+var_50]
0x18006fefd  xor     rcx, rsp
0x18006ff00  call    sub_1801503E0
0x18006ff05  add     rsp, 2C8h
0x18006ff0c  pop     r15
0x18006ff0e  pop     r14
0x18006ff10  pop     r13
0x18006ff12  pop     r12
0x18006ff14  pop     rdi
0x18006ff15  pop     rsi
0x18006ff16  pop     rbx
0x18006ff17  pop     rbp
0x18006ff18  retn
```
