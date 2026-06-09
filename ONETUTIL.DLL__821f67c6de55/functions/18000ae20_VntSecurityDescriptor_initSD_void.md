# VntSecurityDescriptor::initSD(void)

- ea: `0x18000ae20`
- end: `0x18000af58`
- name: `?initSD@VntSecurityDescriptor@@IEAAPEAVVstatus@@XZ`
- size: `312`
- prototype: `struct Vstatus *__fastcall(VntSecurityDescriptor *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a830`
- `0x18000ac50`

## callees

- `0x18000ae20`
- `0x180083790`
- `0x1800b93d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000aeaa`
- `KERNEL32!GetLastError` at `0x18000af02`
- `KERNEL32!GetLastError` at `0x18000aeaa`
- `KERNEL32!GetLastError` at `0x18000af02`
- `ADVAPI32!GetFileSecurityW` at `0x18000ae62`
- `ADVAPI32!GetFileSecurityW` at `0x18000ae9d`
- `ADVAPI32!GetFileSecurityW` at `0x18000ae62`
- `ADVAPI32!GetFileSecurityW` at `0x18000ae9d`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18000aef5`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18000aef5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000ae7b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000aec6`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000af1e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000ae7b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000aec6`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000af1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct Vstatus *__fastcall VntSecurityDescriptor::initSD(VntSecurityDescriptor *this)
{
  __int64 v2; // rbx
  void *v3; // rax
  LPCWSTR v4; // rdi
  DWORD LastError; // esi
  VgenericStatus *v6; // rax
  LPCWSTR v8; // rdi
  DWORD v9; // esi
  VgenericStatus *v10; // rax
  size_t Size; // [rsp+50h] [rbp+8h] BYREF
  VgenericStatus *v12; // [rsp+58h] [rbp+10h]

  v2 = 0;
  if ( !*((_QWORD *)this + 5) )
  {
    LODWORD(Size) = 0;
    GetFileSecurityW(*((LPCWSTR *)this + 1), 4u, 0, 0, (LPDWORD)&Size);
    if ( dword_1802B0018 )
      v3 = COWSAllocator::AllocCurrentHeap((unsigned int)Size);
    else
      v3 = malloc((unsigned int)Size);
    *((_QWORD *)this + 5) = v3;
    if ( !GetFileSecurityW(*((LPCWSTR *)this + 1), 4u, v3, Size, (LPDWORD)&Size) )
    {
      v4 = *(LPCWSTR *)this;
      LastError = GetLastError();
      if ( dword_1802B0018 )
        v6 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
      else
        v6 = (VgenericStatus *)malloc(0x20u);
      v12 = v6;
      if ( v6 )
        return VgenericStatus::VgenericStatus(v6, 0xE002Cu, LastError, v4);
      return (struct Vstatus *)v2;
    }
    if ( !IsValidSecurityDescriptor(*((PSECURITY_DESCRIPTOR *)this + 5)) )
    {
      v8 = *(LPCWSTR *)this;
      v9 = GetLastError();
      if ( dword_1802B0018 )
        v10 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
      else
        v10 = (VgenericStatus *)malloc(0x20u);
      v12 = v10;
      if ( v10 )
        return VgenericStatus::VgenericStatus(v10, 0xE002Cu, v9, v8);
      return (struct Vstatus *)v2;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000ae20  mov     rax, rsp
0x18000ae23  push    rdi
0x18000ae24  sub     rsp, 40h
0x18000ae28  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18000ae30  mov     [rax+18h], rbx
0x18000ae34  mov     [rax+20h], rsi
0x18000ae38  mov     rdi, rcx
0x18000ae3b  xor     ebx, ebx
0x18000ae3d  cmp     [rcx+28h], rbx
0x18000ae41  jnz     loc_18000AF46
0x18000ae47  mov     [rax+8], ebx
0x18000ae4a  lea     rax, [rax+8]
0x18000ae4e  mov     [rsp+48h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18000ae53  xor     r9d, r9d; nLength
0x18000ae56  xor     r8d, r8d; pSecurityDescriptor
0x18000ae59  lea     esi, [rbx+4]
0x18000ae5c  mov     edx, esi; RequestedInformation
0x18000ae5e  mov     rcx, [rcx+8]; lpFileName
0x18000ae62  call    cs:GetFileSecurityW
0x18000ae68  mov     ecx, dword ptr [rsp+48h+Size]; unsigned __int64
0x18000ae6c  cmp     cs:dword_1802B0018, ebx
0x18000ae72  jz      short loc_18000AE7B
0x18000ae74  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18000ae79  jmp     short loc_18000AE81
0x18000ae7b  call    cs:malloc
0x18000ae81  mov     [rdi+28h], rax
0x18000ae85  lea     rcx, [rsp+48h+Size]
0x18000ae8a  mov     [rsp+48h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x18000ae8f  mov     r9d, dword ptr [rsp+48h+Size]; nLength
0x18000ae94  mov     r8, rax; pSecurityDescriptor
0x18000ae97  mov     edx, esi; RequestedInformation
0x18000ae99  mov     rcx, [rdi+8]; lpFileName
0x18000ae9d  call    cs:GetFileSecurityW
0x18000aea3  test    eax, eax
0x18000aea5  jnz     short loc_18000AEF1
0x18000aea7  mov     rdi, [rdi]
0x18000aeaa  call    cs:GetLastError
0x18000aeb0  mov     esi, eax
0x18000aeb2  mov     ecx, 20h ; ' '; unsigned __int64
0x18000aeb7  cmp     cs:dword_1802B0018, ebx
0x18000aebd  jz      short loc_18000AEC6
0x18000aebf  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18000aec4  jmp     short loc_18000AECC
0x18000aec6  call    cs:malloc
0x18000aecc  mov     [rsp+48h+arg_8], rax
0x18000aed1  test    rax, rax
0x18000aed4  jz      short loc_18000AEEC
0x18000aed6  mov     r9, rdi
0x18000aed9  mov     r8d, esi; int
0x18000aedc  mov     edx, 0E002Ch; unsigned int
0x18000aee1  mov     rcx, rax; this
0x18000aee4  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x18000aee9  mov     rbx, rax
0x18000aeec  mov     rax, rbx
0x18000aeef  jmp     short loc_18000AF48
0x18000aef1  mov     rcx, [rdi+28h]; pSecurityDescriptor
0x18000aef5  call    cs:IsValidSecurityDescriptor
0x18000aefb  test    eax, eax
0x18000aefd  jnz     short loc_18000AF46
0x18000aeff  mov     rdi, [rdi]
0x18000af02  call    cs:GetLastError
0x18000af08  mov     esi, eax
0x18000af0a  mov     ecx, 20h ; ' '; unsigned __int64
0x18000af0f  cmp     cs:dword_1802B0018, ebx
0x18000af15  jz      short loc_18000AF1E
0x18000af17  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18000af1c  jmp     short loc_18000AF24
0x18000af1e  call    cs:malloc
0x18000af24  mov     [rsp+48h+arg_8], rax
0x18000af29  test    rax, rax
0x18000af2c  jz      short loc_18000AF44
0x18000af2e  mov     r9, rdi
0x18000af31  mov     r8d, esi; int
0x18000af34  mov     edx, 0E002Ch; unsigned int
0x18000af39  mov     rcx, rax; this
0x18000af3c  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x18000af41  mov     rbx, rax
0x18000af44  jmp     short loc_18000AEEC
0x18000af46  xor     eax, eax
0x18000af48  mov     rbx, [rsp+48h+arg_10]
0x18000af4d  mov     rsi, [rsp+48h+arg_18]
0x18000af52  add     rsp, 40h
0x18000af56  pop     rdi
0x18000af57  retn
```
