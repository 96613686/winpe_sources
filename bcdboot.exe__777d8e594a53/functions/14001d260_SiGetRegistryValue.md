# SiGetRegistryValue

- ea: `0x14001d260`
- end: `0x14001d3f0`
- name: `SiGetRegistryValue`
- size: `400`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, __int64, _QWORD *, ULONG *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14001cbe4`
- `0x14001d3f8`
- `0x14001dca0`

## callees

- `0x14001d260`
- `0x14001d5bc`
- `0x1400265e2`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x14001d2ef`
- `ntdll!NtQueryValueKey` at `0x14001d358`
- `ntdll!NtQueryValueKey` at `0x14001d2ef`
- `ntdll!NtQueryValueKey` at `0x14001d358`
- `ntdll!RtlAllocateHeap` at `0x14001d323`
- `ntdll!RtlAllocateHeap` at `0x14001d38c`
- `ntdll!RtlAllocateHeap` at `0x14001d323`
- `ntdll!RtlAllocateHeap` at `0x14001d38c`
- `ntdll!RtlFreeHeap` at `0x14001d3d7`
- `ntdll!RtlFreeHeap` at `0x14001d3d7`
- `ntdll!NtClose` at `0x14001d3ba`
- `ntdll!NtClose` at `0x14001d3ba`
- `ntdll!RtlInitUnicodeString` at `0x14001d2af`
- `ntdll!RtlInitUnicodeString` at `0x14001d2af`

## pseudocode

```c
__int64 __fastcall SiGetRegistryValue(__int64 a1, const WCHAR *a2, __int64 a3, __int64 a4, _QWORD *a5, ULONG *a6)
{
  _QWORD *v6; // r15
  ULONG *v7; // r14
  _DWORD *v8; // rsi
  HANDLE v9; // rdi
  __int64 v11; // rcx
  __int64 v12; // r8
  int v13; // eax
  NTSTATUS v14; // ebx
  NTSTATUS v15; // eax
  _DWORD *Heap; // rax
  PVOID v17; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  ULONG v20; // [rsp+70h] [rbp+30h] BYREF
  int v21; // [rsp+74h] [rbp+34h]
  HANDLE Handle; // [rsp+80h] [rbp+40h] BYREF
  ULONG ResultLength; // [rsp+88h] [rbp+48h] BYREF

  v21 = HIDWORD(a1);
  v6 = a5;
  v7 = a6;
  v8 = 0;
  v20 = 0;
  v9 = 0;
  ResultLength = 0;
  *a5 = 0;
  *v7 = 0;
  DestinationString = 0;
  Handle = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  if ( !a3 || (v13 = SiOpenRegistryKey(v11, a3, v12, &Handle), v9 = Handle, v14 = v13, v13 >= 0) )
  {
    v15 = NtQueryValueKey(v9, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
    v14 = v15;
    if ( v15 == -1073741789 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ResultLength);
      v8 = Heap;
      if ( !Heap )
        goto LABEL_7;
      v14 = NtQueryValueKey(v9, &DestinationString, KeyValuePartialInformation, Heap, ResultLength, &v20);
      if ( v14 < 0 )
        goto LABEL_13;
      if ( v8[1] != 1 )
      {
        v14 = -1073741788;
        goto LABEL_13;
      }
      ResultLength -= 12;
      v17 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ResultLength);
      *v6 = v17;
      if ( !v17 )
      {
LABEL_7:
        v14 = -1073741670;
        goto LABEL_13;
      }
      memcpy_0(v17, v8 + 3, ResultLength);
      v14 = 0;
      *v7 = ResultLength;
    }
    else if ( v15 >= 0 )
    {
      v14 = -1073741823;
    }
  }
LABEL_13:
  if ( v9 )
    NtClose(v9);
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14001d260  mov     [rsp-28h+arg_8], rbx
0x14001d265  mov     [rsp-28h+arg_18], r9d
0x14001d26a  mov     qword ptr [rsp-28h+arg_0], rcx
0x14001d26f  push    rbp
0x14001d270  push    rsi
0x14001d271  push    rdi
0x14001d272  push    r14
0x14001d274  push    r15
0x14001d276  mov     rbp, rsp
0x14001d279  sub     rsp, 40h
0x14001d27d  mov     r15, [rbp+arg_20]
0x14001d281  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001d285  mov     r14, [rbp+arg_28]
0x14001d289  xorps   xmm0, xmm0
0x14001d28c  xor     esi, esi
0x14001d28e  mov     [rbp+arg_0], 0
0x14001d295  xor     edi, edi
0x14001d297  mov     [rbp+arg_18], 0
0x14001d29e  mov     [r15], rsi
0x14001d2a1  mov     rbx, r8
0x14001d2a4  mov     [r14], esi
0x14001d2a7  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001d2ab  mov     [rbp+Handle], rdi
0x14001d2af  call    cs:__imp_RtlInitUnicodeString
0x14001d2b5  test    rbx, rbx
0x14001d2b8  jz      short loc_14001D2D4
0x14001d2ba  lea     r9, [rbp+Handle]
0x14001d2be  mov     rdx, rbx
0x14001d2c1  call    SiOpenRegistryKey
0x14001d2c6  mov     rdi, [rbp+Handle]
0x14001d2ca  mov     ebx, eax
0x14001d2cc  test    eax, eax
0x14001d2ce  js      loc_14001D3B2
0x14001d2d4  xor     r9d, r9d; KeyValueInformation
0x14001d2d7  lea     rax, [rbp+arg_18]
0x14001d2db  mov     [rsp+40h+ResultLength], rax; ResultLength
0x14001d2e0  lea     rdx, [rbp+DestinationString]; ValueName
0x14001d2e4  mov     rcx, rdi; KeyHandle
0x14001d2e7  mov     [rsp+40h+Length], esi; Length
0x14001d2eb  lea     r8d, [r9+2]; KeyValueInformationClass
0x14001d2ef  call    cs:__imp_NtQueryValueKey
0x14001d2f5  mov     ebx, eax
0x14001d2f7  cmp     eax, 0C0000023h
0x14001d2fc  jz      short loc_14001D310
0x14001d2fe  test    eax, eax
0x14001d300  js      loc_14001D3B2
0x14001d306  mov     ebx, 0C0000001h
0x14001d30b  jmp     loc_14001D3B2
0x14001d310  mov     rcx, gs:60h
0x14001d319  xor     edx, edx; Flags
0x14001d31b  mov     r8d, [rbp+arg_18]; Size
0x14001d31f  mov     rcx, [rcx+30h]; HeapHandle
0x14001d323  call    cs:__imp_RtlAllocateHeap
0x14001d329  mov     rsi, rax
0x14001d32c  test    rax, rax
0x14001d32f  jnz     short loc_14001D338
0x14001d331  mov     ebx, 0C000009Ah
0x14001d336  jmp     short loc_14001D3B2
0x14001d338  lea     rax, [rbp+arg_0]
0x14001d33c  mov     r9, rsi; KeyValueInformation
0x14001d33f  mov     [rsp+40h+ResultLength], rax; ResultLength
0x14001d344  lea     rdx, [rbp+DestinationString]; ValueName
0x14001d348  mov     eax, [rbp+arg_18]
0x14001d34b  mov     r8d, 2; KeyValueInformationClass
0x14001d351  mov     rcx, rdi; KeyHandle
0x14001d354  mov     [rsp+40h+Length], eax; Length
0x14001d358  call    cs:__imp_NtQueryValueKey
0x14001d35e  mov     ebx, eax
0x14001d360  test    eax, eax
0x14001d362  js      short loc_14001D3B2
0x14001d364  cmp     dword ptr [rsi+4], 1
0x14001d368  jz      short loc_14001D371
0x14001d36a  mov     ebx, 0C0000024h
0x14001d36f  jmp     short loc_14001D3B2
0x14001d371  mov     eax, [rbp+arg_18]
0x14001d374  xor     edx, edx; Flags
0x14001d376  add     eax, 0FFFFFFF4h
0x14001d379  mov     [rbp+arg_18], eax
0x14001d37c  mov     rcx, gs:60h
0x14001d385  mov     r8d, eax; Size
0x14001d388  mov     rcx, [rcx+30h]; HeapHandle
0x14001d38c  call    cs:__imp_RtlAllocateHeap
0x14001d392  mov     [r15], rax
0x14001d395  test    rax, rax
0x14001d398  jz      short loc_14001D331
0x14001d39a  mov     r8d, [rbp+arg_18]; Size
0x14001d39e  lea     rdx, [rsi+0Ch]; Src
0x14001d3a2  mov     rcx, rax; void *
0x14001d3a5  call    memcpy_0
0x14001d3aa  mov     eax, [rbp+arg_18]
0x14001d3ad  xor     ebx, ebx
0x14001d3af  mov     [r14], eax
0x14001d3b2  test    rdi, rdi
0x14001d3b5  jz      short loc_14001D3C0
0x14001d3b7  mov     rcx, rdi; Handle
0x14001d3ba  call    cs:__imp_NtClose
0x14001d3c0  test    rsi, rsi
0x14001d3c3  jz      short loc_14001D3DD
0x14001d3c5  mov     rcx, gs:60h
0x14001d3ce  mov     r8, rsi; P
0x14001d3d1  xor     edx, edx; Flags
0x14001d3d3  mov     rcx, [rcx+30h]; HeapHandle
0x14001d3d7  call    cs:__imp_RtlFreeHeap
0x14001d3dd  mov     eax, ebx
0x14001d3df  mov     rbx, [rsp+40h+arg_8]
0x14001d3e4  add     rsp, 40h
0x14001d3e8  pop     r15
0x14001d3ea  pop     r14
0x14001d3ec  pop     rdi
0x14001d3ed  pop     rsi
0x14001d3ee  pop     rbp
0x14001d3ef  retn
```
