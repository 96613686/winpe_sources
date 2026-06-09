# BiGetRegistryValue

- ea: `0x14001f324`
- end: `0x14001f56a`
- name: `BiGetRegistryValue`
- size: `582`
- prototype: `__int64 __fastcall(unsigned __int64, const WCHAR *, __int64, unsigned int, _QWORD *, ULONG *)`
- caller_count: `14`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140014574`
- `0x14001474c`
- `0x140018890`
- `0x140019bb8`
- `0x14001b64c`
- `0x14001b6ec`
- `0x14001b92c`
- `0x14001c0d4`
- `0x14001fd7c`
- `0x1400201ec`
- `0x140020298`
- `0x1400207d4`
- `0x14002445c`
- `0x140024cf0`

## callees

- `0x1400133e4`
- `0x14001f324`
- `0x14001f980`
- `0x1400265e2`

## import_xrefs

- `ntdll!ZwClose` at `0x14001f4fb`
- `ntdll!ZwClose` at `0x14001f4fb`
- `ntdll!ZwQueryValueKey` at `0x14001f3ed`
- `ntdll!ZwQueryValueKey` at `0x14001f453`
- `ntdll!ZwQueryValueKey` at `0x14001f3ed`
- `ntdll!ZwQueryValueKey` at `0x14001f453`
- `ntdll!RtlAllocateHeap` at `0x14001f418`
- `ntdll!RtlAllocateHeap` at `0x14001f4af`
- `ntdll!RtlAllocateHeap` at `0x14001f418`
- `ntdll!RtlAllocateHeap` at `0x14001f4af`
- `ntdll!RtlFreeHeap` at `0x14001f518`
- `ntdll!RtlFreeHeap` at `0x14001f518`
- `ntdll!RtlInitUnicodeString` at `0x14001f38b`
- `ntdll!RtlInitUnicodeString` at `0x14001f38b`

## pseudocode

```c
__int64 __fastcall BiGetRegistryValue(
        unsigned __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5,
        ULONG *a6)
{
  const WCHAR *v7; // rax
  unsigned int i; // r12d
  _DWORD *Heap; // r15
  NTSTATUS v11; // ebx
  HANDLE v12; // rsi
  PVOID v13; // rax
  ULONG ResultLength; // [rsp+30h] [rbp-68h] BYREF
  NTSTATUS v16; // [rsp+34h] [rbp-64h]
  ULONG v17; // [rsp+38h] [rbp-60h] BYREF
  HANDLE KeyHandle; // [rsp+40h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-50h] BYREF

  v7 = a2;
  v17 = 0;
  ResultLength = 0;
  DestinationString = 0;
  for ( i = 0; ; ++i )
  {
    Heap = 0;
    KeyHandle = 0;
    *a5 = 0;
    *a6 = 0;
    RtlInitUnicodeString(&DestinationString, v7);
    a1 &= ~2uLL;
    if ( a3 )
    {
      v11 = BiOpenKey(a1, a3, 131097, &KeyHandle);
      v16 = v11;
      v12 = KeyHandle;
      if ( v11 < 0 )
        goto LABEL_15;
    }
    else
    {
      v12 = (HANDLE)a1;
    }
    v11 = ZwQueryValueKey(v12, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
    v16 = v11;
    if ( v11 == -1073741789 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ResultLength);
      if ( !Heap )
        goto LABEL_8;
      v11 = ZwQueryValueKey(v12, &DestinationString, KeyValuePartialInformation, Heap, ResultLength, &v17);
      v16 = v11;
      if ( v11 >= 0 )
      {
        if ( Heap[1] == a4 )
        {
          ResultLength -= 12;
          v13 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ResultLength);
          *a5 = v13;
          if ( v13 )
          {
            memcpy_0(v13, Heap + 3, ResultLength);
            *a6 = ResultLength;
            v11 = 0;
          }
          else
          {
LABEL_8:
            v11 = -1073741670;
          }
        }
        else
        {
          BiLogMessage(4, L"Unexpected type for BCD element. Expected type: 0x%x Actual type: 0x%x", a4);
          v11 = -1073741788;
        }
        v16 = v11;
      }
    }
LABEL_15:
    if ( v12 != (HANDLE)a1 && v12 )
      ZwClose(v12);
    if ( Heap )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    if ( v11 != -1073741443 )
      break;
    __debugbreak();
    if ( i >= 5 )
      break;
    v7 = a2;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14001f324  mov     [rsp+arg_18], r9d
0x14001f329  mov     [rsp+arg_10], r8
0x14001f32e  mov     [rsp+arg_8], rdx
0x14001f333  push    rbx
0x14001f334  push    rsi
0x14001f335  push    r12
0x14001f337  push    r13
0x14001f339  push    r14
0x14001f33b  push    r15
0x14001f33d  sub     rsp, 68h
0x14001f341  mov     r13, r8
0x14001f344  mov     rax, rdx
0x14001f347  mov     r14, rcx
0x14001f34a  mov     [rsp+98h+var_60], 0
0x14001f352  mov     [rsp+98h+var_68], 0
0x14001f35a  xorps   xmm0, xmm0
0x14001f35d  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x14001f362  xor     r12d, r12d
0x14001f365  xor     r15d, r15d
0x14001f368  mov     [rsp+98h+KeyHandle], r15
0x14001f36d  mov     rcx, [rsp+98h+arg_20]
0x14001f375  mov     [rcx], r15
0x14001f378  mov     rcx, [rsp+98h+arg_28]
0x14001f380  mov     [rcx], r15d
0x14001f383  mov     rdx, rax; SourceString
0x14001f386  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x14001f38b  call    cs:__imp_RtlInitUnicodeString
0x14001f391  and     r14, 0FFFFFFFFFFFFFFFDh
0x14001f395  mov     [rsp+98h+arg_0], r14
0x14001f39d  test    r13, r13
0x14001f3a0  jz      short loc_14001F3CC
0x14001f3a2  lea     r9, [rsp+98h+KeyHandle]
0x14001f3a7  mov     r8d, 20019h
0x14001f3ad  mov     rdx, r13
0x14001f3b0  mov     rcx, r14
0x14001f3b3  call    BiOpenKey
0x14001f3b8  mov     ebx, eax
0x14001f3ba  mov     [rsp+98h+var_64], eax
0x14001f3be  mov     rsi, [rsp+98h+KeyHandle]
0x14001f3c3  test    eax, eax
0x14001f3c5  jns     short loc_14001F3CF
0x14001f3c7  jmp     loc_14001F4EE
0x14001f3cc  mov     rsi, r14
0x14001f3cf  lea     rax, [rsp+98h+var_68]
0x14001f3d4  mov     [rsp+98h+ResultLength], rax; ResultLength
0x14001f3d9  mov     [rsp+98h+Length], r15d; Length
0x14001f3de  xor     r9d, r9d; KeyValueInformation
0x14001f3e1  lea     r8d, [r9+2]; KeyValueInformationClass
0x14001f3e5  lea     rdx, [rsp+98h+DestinationString]; ValueName
0x14001f3ea  mov     rcx, rsi; KeyHandle
0x14001f3ed  call    cs:__imp_ZwQueryValueKey
0x14001f3f3  mov     ebx, eax
0x14001f3f5  mov     [rsp+98h+var_64], eax
0x14001f3f9  cmp     eax, 0C0000023h
0x14001f3fe  jnz     loc_14001F4EE
0x14001f404  mov     r8d, [rsp+98h+var_68]; Size
0x14001f409  mov     rcx, gs:60h
0x14001f412  xor     edx, edx; Flags
0x14001f414  mov     rcx, [rcx+30h]; HeapHandle
0x14001f418  call    cs:__imp_RtlAllocateHeap
0x14001f41e  mov     r15, rax
0x14001f421  test    rax, rax
0x14001f424  jnz     short loc_14001F430
0x14001f426  mov     ebx, 0C000009Ah
0x14001f42b  jmp     loc_14001F4EA
0x14001f430  mov     eax, [rsp+98h+var_68]
0x14001f434  lea     rcx, [rsp+98h+var_60]
0x14001f439  mov     [rsp+98h+ResultLength], rcx; ResultLength
0x14001f43e  mov     [rsp+98h+Length], eax; Length
0x14001f442  mov     r9, r15; KeyValueInformation
0x14001f445  mov     r8d, 2; KeyValueInformationClass
0x14001f44b  lea     rdx, [rsp+98h+DestinationString]; ValueName
0x14001f450  mov     rcx, rsi; KeyHandle
0x14001f453  call    cs:__imp_ZwQueryValueKey
0x14001f459  mov     ebx, eax
0x14001f45b  mov     [rsp+98h+var_64], eax
0x14001f45f  test    eax, eax
0x14001f461  js      loc_14001F4EE
0x14001f467  mov     r9d, [r15+4]
0x14001f46b  mov     eax, [rsp+98h+arg_18]
0x14001f472  cmp     r9d, eax
0x14001f475  jz      short loc_14001F492
0x14001f477  mov     r8d, eax
0x14001f47a  lea     rdx, aUnexpectedType; "Unexpected type for BCD element. Expect"...
0x14001f481  mov     ecx, 4
0x14001f486  call    BiLogMessage
0x14001f48b  mov     ebx, 0C0000024h
0x14001f490  jmp     short loc_14001F4EA
0x14001f492  mov     eax, [rsp+98h+var_68]
0x14001f496  add     eax, 0FFFFFFF4h
0x14001f499  mov     [rsp+98h+var_68], eax
0x14001f49d  mov     r8d, eax; Size
0x14001f4a0  mov     rcx, gs:60h
0x14001f4a9  xor     edx, edx; Flags
0x14001f4ab  mov     rcx, [rcx+30h]; HeapHandle
0x14001f4af  call    cs:__imp_RtlAllocateHeap
0x14001f4b5  mov     rcx, [rsp+98h+arg_20]
0x14001f4bd  mov     [rcx], rax
0x14001f4c0  test    rax, rax
0x14001f4c3  jz      loc_14001F426
0x14001f4c9  mov     r8d, [rsp+98h+var_68]; Size
0x14001f4ce  lea     rdx, [r15+0Ch]; Src
0x14001f4d2  mov     rcx, rax; void *
0x14001f4d5  call    memcpy_0
0x14001f4da  mov     eax, [rsp+98h+var_68]
0x14001f4de  mov     rcx, [rsp+98h+arg_28]
0x14001f4e6  mov     [rcx], eax
0x14001f4e8  xor     ebx, ebx
0x14001f4ea  mov     [rsp+98h+var_64], ebx
0x14001f4ee  cmp     rsi, r14
0x14001f4f1  jz      short loc_14001F501
0x14001f4f3  test    rsi, rsi
0x14001f4f6  jz      short loc_14001F501
0x14001f4f8  mov     rcx, rsi; Handle
0x14001f4fb  call    cs:__imp_ZwClose
0x14001f501  test    r15, r15
0x14001f504  jz      short loc_14001F51E
0x14001f506  mov     rcx, gs:60h
0x14001f50f  mov     r8, r15; P
0x14001f512  xor     edx, edx; Flags
0x14001f514  mov     rcx, [rcx+30h]; HeapHandle
0x14001f518  call    cs:__imp_RtlFreeHeap
0x14001f51e  cmp     ebx, 0C000017Dh
0x14001f524  jnz     short loc_14001F559
0x14001f526  int     3; Trap to Debugger
0x14001f527  jmp     short loc_14001F543
0x14001f529  mov     r12d, 5
0x14001f52f  mov     r13, [rsp+98h+arg_10]
0x14001f537  mov     r14, [rsp+98h+arg_0]
0x14001f53f  mov     ebx, [rsp+98h+var_64]
0x14001f543  cmp     r12d, 5
0x14001f547  jnb     short loc_14001F559
0x14001f549  inc     r12d
0x14001f54c  mov     rax, [rsp+98h+arg_8]
0x14001f554  jmp     loc_14001F365
0x14001f559  mov     eax, ebx
0x14001f55b  add     rsp, 68h
0x14001f55f  pop     r15
0x14001f561  pop     r14
0x14001f563  pop     r13
0x14001f565  pop     r12
0x14001f567  pop     rsi
0x14001f568  pop     rbx
0x14001f569  retn
```
