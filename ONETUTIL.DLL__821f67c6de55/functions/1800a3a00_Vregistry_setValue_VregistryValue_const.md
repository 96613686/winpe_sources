# Vregistry::setValue(VregistryValue const &)

- ea: `0x1800a3a00`
- end: `0x1800a3bef`
- name: `?setValue@Vregistry@@UEAAPEAVVstatus@@AEBVVregistryValue@@@Z`
- size: `495`
- prototype: `struct Vstatus *__fastcall(Vregistry *__hidden this, const struct VregistryValue *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800a53f0`

## callees

- `0x180083790`
- `0x1800838f0`
- `0x180096770`
- `0x1800a3a00`
- `0x1800b7a58`
- `0x1800b7b38`
- `0x1800b93d0`
- `0x1801503e0`
- `0x1801519a0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800a3b5d`
- `ADVAPI32!RegSetValueExW` at `0x1800a3b5d`
- `ADVAPI32!RegSetValueExA` at `0x1800a3b65`
- `ADVAPI32!RegSetValueExA` at `0x1800a3b65`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a3ab3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a3ab3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a3b92`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a3b92`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct Vstatus *__fastcall Vregistry::setValue(HKEY *this, const struct VregistryValue *a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rbx
  DWORD v7; // r15d
  __int64 v8; // rdi
  int *v9; // rcx
  DWORD cbData; // esi
  const BYTE *lpData; // r14
  HKEY v13; // r12
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  int v17; // ecx
  LSTATUS v18; // eax
  unsigned int v19; // esi
  __int64 v20; // rdi
  VgenericStatus *v21; // rax
  DWORD v22; // [rsp+3Ch] [rbp-CCh]
  __int64 v23; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v24[2]; // [rsp+48h] [rbp-C0h] BYREF
  _WORD v25[256]; // [rsp+58h] [rbp-B0h] BYREF
  LPCWSTR lpValueName; // [rsp+258h] [rbp+150h]
  int v27; // [rsp+260h] [rbp+158h]
  char v28; // [rsp+264h] [rbp+15Ch]

  v24[1] = -2;
  v6 = 0;
  v7 = *((_DWORD *)a2 + 2);
  if ( v7 == 1 )
  {
    v24[0] = *((_QWORD *)a2 + 4);
    _InterlockedAdd((volatile signed __int32 *)(v24[0] - 12LL), 1u);
    LOBYTE(a4) = 1;
    v8 = (*((__int64 (__fastcall **)(HKEY *, const struct VregistryValue *, _QWORD *, __int64))*this + 6))(
           this,
           a2,
           v24,
           a4);
    v9 = (int *)(v24[0] - 12LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v24[0] - 12LL), 0xFFFFFFFF) == 1 && v9 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v9);
      else
        free(v9);
    }
    return (struct Vstatus *)v8;
  }
  else
  {
    if ( v7 - 4 <= 1 )
    {
      cbData = 4;
      LODWORD(v23) = *((_DWORD *)a2 + 4);
      lpData = (const BYTE *)&v23;
    }
    else if ( v7 == 3 || *((_BYTE *)a2 + 12) )
    {
      cbData = *((_DWORD *)a2 + 4);
      lpData = (const BYTE *)*((_QWORD *)a2 + 3);
    }
    else
    {
      lpData = 0;
      cbData = v22;
    }
    lpValueName = v25;
    v27 = 512;
    v25[0] = 0;
    v28 = 0;
    sub_1800B7B38((VstackStrLCP *)v25);
    v13 = this[3];
    if ( (unsigned __int8)sub_180096770(v15, v14, v16) )
      v17 = *(_DWORD *)(qword_1802B00B0 + 4);
    else
      v17 = 0;
    if ( v17 == 2 )
      v18 = RegSetValueExW(v13, lpValueName, 0, v7, lpData, cbData);
    else
      v18 = RegSetValueExA(v13, (LPCSTR)lpValueName, 0, v7, lpData, cbData);
    v19 = v18;
    VstackStrLCP::~VstackStrLCP((VstackStrLCP *)v25);
    if ( v19 )
    {
      v20 = *(_QWORD *)a2;
      if ( dword_1802B0018 )
        v21 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
      else
        v21 = (VgenericStatus *)malloc(0x20u);
      v24[0] = v21;
      if ( v21 )
        return VgenericStatus::VgenericStatus(v21, 0x30007u, v19, v19, v20);
      return (struct Vstatus *)v6;
    }
    else
    {
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1800a3a00  mov     rax, rsp
0x1800a3a03  push    rbp
0x1800a3a04  push    rdi
0x1800a3a05  push    r12
0x1800a3a07  push    r14
0x1800a3a09  push    r15
0x1800a3a0b  lea     rbp, [rax-198h]
0x1800a3a12  sub     rsp, 270h
0x1800a3a19  mov     qword ptr [rsp+290h+var_248], 0FFFFFFFFFFFFFFFEh
0x1800a3a22  mov     [rax+18h], rbx
0x1800a3a26  mov     [rax+20h], rsi
0x1800a3a2a  mov     rax, cs:__security_cookie
0x1800a3a31  xor     rax, rsp
0x1800a3a34  mov     [rbp+190h+var_30], rax
0x1800a3a3b  mov     rdi, rdx
0x1800a3a3e  mov     r12, rcx
0x1800a3a41  xor     ebx, ebx
0x1800a3a43  mov     [rsp+290h+var_260], ebx
0x1800a3a47  mov     r15d, [rdx+8]
0x1800a3a4b  lea     esi, [rbx+1]
0x1800a3a4e  cmp     r15d, esi
0x1800a3a51  jnz     short loc_1800A3AC1
0x1800a3a53  mov     rax, [rdx+20h]
0x1800a3a57  mov     [rsp+290h+var_250], rax
0x1800a3a5c  lock add [rax-0Ch], esi
0x1800a3a60  mov     [rsp+290h+var_260], esi
0x1800a3a64  mov     rax, [rcx]
0x1800a3a67  mov     r9b, sil
0x1800a3a6a  lea     r8, [rsp+290h+var_250]
0x1800a3a6f  mov     rax, [rax+30h]
0x1800a3a73  call    cs:__guard_dispatch_icall_fptr
0x1800a3a79  mov     rdi, rax
0x1800a3a7c  and     esi, 0FFFFFFFEh
0x1800a3a7f  mov     [rsp+290h+var_260], esi
0x1800a3a83  mov     rcx, [rsp+290h+var_250]
0x1800a3a88  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800a3a8c  or      edx, 0FFFFFFFFh
0x1800a3a8f  lock xadd [rcx], edx
0x1800a3a93  cmp     edx, 1
0x1800a3a96  jnz     short loc_1800A3AB9
0x1800a3a98  lea     rax, dword_1802AFD50
0x1800a3a9f  cmp     rcx, rax
0x1800a3aa2  jz      short loc_1800A3AB9
0x1800a3aa4  cmp     cs:dword_1802B0018, ebx
0x1800a3aaa  jz      short loc_1800A3AB3
0x1800a3aac  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800a3ab1  jmp     short loc_1800A3AB9
0x1800a3ab3  call    cs:free
0x1800a3ab9  mov     rax, rdi
0x1800a3abc  jmp     loc_1800A3BC4
0x1800a3ac1  lea     eax, [r15-4]
0x1800a3ac5  cmp     eax, esi
0x1800a3ac7  jbe     short loc_1800A3AE6
0x1800a3ac9  cmp     r15d, 3
0x1800a3acd  jz      short loc_1800A3AD4
0x1800a3acf  cmp     [rdx+0Ch], bl
0x1800a3ad2  jz      short loc_1800A3ADD
0x1800a3ad4  mov     esi, [rdx+10h]
0x1800a3ad7  mov     r14, [rdx+18h]
0x1800a3adb  jmp     short loc_1800A3AF7
0x1800a3add  mov     r14, rbx
0x1800a3ae0  mov     esi, [rsp+290h+var_25C]
0x1800a3ae4  jmp     short loc_1800A3AF7
0x1800a3ae6  mov     esi, 4
0x1800a3aeb  mov     eax, [rdx+10h]
0x1800a3aee  mov     dword ptr [rsp+290h+var_258], eax
0x1800a3af2  lea     r14, [rsp+290h+var_258]
0x1800a3af7  lea     rax, [rsp+290h+var_240]
0x1800a3afc  mov     [rbp+190h+lpValueName], rax
0x1800a3b03  mov     [rbp+190h+var_38], 200h
0x1800a3b0d  mov     [rsp+290h+var_240], bx
0x1800a3b12  mov     [rbp+190h+var_34], bl
0x1800a3b18  lea     rcx, [rsp+290h+var_240]; this
0x1800a3b1d  call    sub_1800B7B38
0x1800a3b22  nop
0x1800a3b23  mov     r12, [r12+18h]
0x1800a3b28  call    sub_180096770
0x1800a3b2d  test    al, al
0x1800a3b2f  jz      short loc_1800A3B3D
0x1800a3b31  mov     rax, cs:qword_1802B00B0
0x1800a3b38  mov     ecx, [rax+4]
0x1800a3b3b  jmp     short loc_1800A3B3F
0x1800a3b3d  mov     ecx, ebx
0x1800a3b3f  mov     [rsp+290h+cbData], esi; cbData
0x1800a3b43  mov     r9d, r15d; dwType
0x1800a3b46  xor     r8d, r8d; Reserved
0x1800a3b49  mov     rdx, [rbp+190h+lpValueName]; lpValueName
0x1800a3b50  mov     [rsp+290h+lpData], r14; lpData
0x1800a3b55  cmp     ecx, 2
0x1800a3b58  mov     rcx, r12; hKey
0x1800a3b5b  jnz     short loc_1800A3B65
0x1800a3b5d  call    cs:RegSetValueExW
0x1800a3b63  jmp     short loc_1800A3B6B
0x1800a3b65  call    cs:RegSetValueExA
0x1800a3b6b  mov     esi, eax
0x1800a3b6d  lea     rcx, [rsp+290h+var_240]; this
0x1800a3b72  call    ??1VstackStrLCP@@QEAA@XZ_0; VstackStrLCP::~VstackStrLCP(void)
0x1800a3b77  test    esi, esi
0x1800a3b79  jz      short loc_1800A3BC2
0x1800a3b7b  mov     rdi, [rdi]
0x1800a3b7e  mov     ecx, 20h ; ' '; unsigned __int64
0x1800a3b83  cmp     cs:dword_1802B0018, ebx
0x1800a3b89  jz      short loc_1800A3B92
0x1800a3b8b  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800a3b90  jmp     short loc_1800A3B98
0x1800a3b92  call    cs:malloc
0x1800a3b98  mov     [rsp+290h+var_250], rax
0x1800a3b9d  test    rax, rax
0x1800a3ba0  jz      short loc_1800A3BBD
0x1800a3ba2  mov     [rsp+290h+lpData], rdi
0x1800a3ba7  mov     r9d, esi
0x1800a3baa  mov     r8d, esi; int
0x1800a3bad  mov     edx, 30007h; unsigned int
0x1800a3bb2  mov     rcx, rax; this
0x1800a3bb5  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x1800a3bba  mov     rbx, rax
0x1800a3bbd  mov     rax, rbx
0x1800a3bc0  jmp     short loc_1800A3BC4
0x1800a3bc2  xor     eax, eax
0x1800a3bc4  mov     rcx, [rbp+190h+var_30]
0x1800a3bcb  xor     rcx, rsp
0x1800a3bce  call    sub_1801503E0
0x1800a3bd3  lea     r11, [rsp+290h+var_20]
0x1800a3bdb  mov     rbx, [r11+40h]
0x1800a3bdf  mov     rsi, [r11+48h]
0x1800a3be3  mov     rsp, r11
0x1800a3be6  pop     r15
0x1800a3be8  pop     r14
0x1800a3bea  pop     r12
0x1800a3bec  pop     rdi
0x1800a3bed  pop     rbp
0x1800a3bee  retn
```
