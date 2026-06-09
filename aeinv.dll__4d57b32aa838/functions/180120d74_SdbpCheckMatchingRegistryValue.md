# SdbpCheckMatchingRegistryValue

- ea: `0x180120d74`
- end: `0x1801210f3`
- name: `SdbpCheckMatchingRegistryValue`
- size: `895`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, wchar_t *String1, int, __int64, int, __int64, void *Buf1, size_t Size, _DWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180120b8c`
- `0x18012164c`

## callees

- `0x1800197d4`
- `0x18001b0b8`
- `0x18001cce4`
- `0x18005a7c0`
- `0x18006ce28`
- `0x180120d74`
- `0x180125484`
- `0x18012549c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180120e54`
- `ntdll!RtlAllocateHeap` at `0x180120f5a`
- `ntdll!RtlAllocateHeap` at `0x180121096`
- `ntdll!RtlAllocateHeap` at `0x180120e54`
- `ntdll!RtlAllocateHeap` at `0x180120f5a`
- `ntdll!RtlAllocateHeap` at `0x180121096`
- `ntdll!RtlInitUnicodeString` at `0x180120dfa`
- `ntdll!RtlInitUnicodeString` at `0x180120dfa`
- `ntdll!ZwQueryValueKey` at `0x180120e1e`
- `ntdll!ZwQueryValueKey` at `0x180120ea0`
- `ntdll!ZwQueryValueKey` at `0x180120e1e`
- `ntdll!ZwQueryValueKey` at `0x180120ea0`

## string_xrefs

- `0x180120dc2`: `dbRegistryDefaultName`
- `0x180120ead`: `Failed to read value`
- `0x180120f22`: `Unknown registry value data type`
- `0x180120e6f`: `SdbpCheckMatchingRegistryValue`
- `0x180120ebd`: `SdbpCheckMatchingRegistryValue`

## pseudocode

```c
__int64 __fastcall SdbpCheckMatchingRegistryValue(
        HANDLE KeyHandle,
        wchar_t *String1,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        void *Buf1,
        size_t Size,
        _DWORD *a9)
{
  PCWSTR v12; // r15
  _WORD *v13; // rsi
  _DWORD *v14; // rdi
  unsigned int v15; // ebx
  const WCHAR *v16; // rdx
  int v17; // eax
  NTSTATUS v18; // eax
  _DWORD *Heap; // rax
  const char *v20; // r9
  int v21; // r8d
  int v22; // ecx
  _DWORD *v23; // r14
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  bool v29; // zf
  _WORD *v30; // rax
  _WORD *i; // rcx
  _WORD *v33; // rax
  PCWSTR SourceString; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+98h] [rbp+48h] BYREF
  __int64 v37; // [rsp+A8h] [rbp+58h]

  v37 = a4;
  SourceString = 0;
  ResultLength = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  DestinationString = 0;
  if ( !String1 || !*String1 )
    goto LABEL_38;
  v15 = 0;
  if ( wcsicmp(String1, L"dbRegistryDefaultName") )
  {
    v17 = AslStringDuplicate(&SourceString, String1);
    v12 = SourceString;
    if ( v17 < 0 )
      goto LABEL_42;
    v16 = SourceString;
  }
  else
  {
    v16 = 0;
  }
  RtlInitUnicodeString(&DestinationString, v16);
  v18 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, 0, 0, &ResultLength);
  if ( v18 < 0 && v18 != -2147483643 && v18 != -1073741789 )
  {
    v15 = 1;
    goto LABEL_42;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, ResultLength);
  v14 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, (unsigned int)"SdbpCheckMatchingRegistryValue", 1249, (unsigned int)"Failed to allocate memory");
    goto LABEL_42;
  }
  if ( ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, Heap, ResultLength, &ResultLength) >= 0 )
  {
    if ( !a3 )
    {
      *a9 = 1;
LABEL_18:
      v15 = 1;
      goto LABEL_39;
    }
    v22 = v14[1];
    if ( v22 != a3 )
      goto LABEL_18;
    v23 = (_DWORD *)((char *)v14 + (unsigned int)v14[2]);
    v24 = v22 - 1;
    if ( v24 && (v25 = v24 - 1) != 0 )
    {
      v26 = v25 - 1;
      if ( !v26 )
      {
        if ( Size != v14[3] )
          goto LABEL_52;
        v29 = memcmp_0(Buf1, (char *)v14 + (unsigned int)v14[2], Size) == 0;
LABEL_37:
        if ( v29 )
          goto LABEL_38;
LABEL_52:
        v15 = 1;
        goto LABEL_39;
      }
      v27 = v26 - 1;
      if ( !v27 )
      {
        v29 = a5 == *v23;
        goto LABEL_37;
      }
      v28 = v27 - 3;
      if ( v28 )
      {
        if ( v28 != 4 )
        {
          v20 = "Unknown registry value data type";
          v21 = 1396;
          goto LABEL_15;
        }
        v29 = a6 == *(_QWORD *)v23;
        goto LABEL_37;
      }
      v30 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v14[3] + 2LL);
      v13 = v30;
      if ( !v30 )
      {
        v21 = 1321;
LABEL_49:
        v20 = "Failed to allocate memory";
        goto LABEL_15;
      }
      memmove_0(v30, v23, (unsigned int)v14[3]);
      v13[(unsigned __int64)(unsigned int)v14[3] >> 1] = 0;
      for ( i = v13; i < (_WORD *)((char *)v13 + (v14[3] & 0xFFFFFFFE)); ++i )
      {
        if ( !*i )
        {
          if ( !i[1] )
            break;
          *i = 59;
        }
      }
    }
    else
    {
      v33 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v14[3] + 2LL);
      v13 = v33;
      if ( !v33 )
      {
        v21 = 1297;
        goto LABEL_49;
      }
      memmove_0(v33, v23, (unsigned int)v14[3]);
      v13[(unsigned __int64)(unsigned int)v14[3] >> 1] = 0;
    }
    if ( !(unsigned int)AslStringPatternMatchExW(v37, v13) )
      goto LABEL_52;
LABEL_38:
    *a9 = 1;
    v15 = 1;
    if ( !v14 )
      goto LABEL_40;
    goto LABEL_39;
  }
  v20 = "Failed to read value";
  v21 = 1260;
LABEL_15:
  AslLogCallPrintf(1, (unsigned int)"SdbpCheckMatchingRegistryValue", v21, (_DWORD)v20);
LABEL_39:
  AslFree(NtCurrentPeb()->ProcessHeap, v14);
LABEL_40:
  if ( v13 )
    AslFree(NtCurrentPeb()->ProcessHeap, v13);
LABEL_42:
  if ( v12 )
    AslFree(NtCurrentPeb()->ProcessHeap, v12);
  return v15;
}

```

## disassembly

```asm
0x180120d74  mov     [rsp-38h+arg_0], rbx
0x180120d79  mov     [rsp-38h+arg_18], r9
0x180120d7e  push    rbp
0x180120d7f  push    rsi
0x180120d80  push    rdi
0x180120d81  push    r12
0x180120d83  push    r13
0x180120d85  push    r14
0x180120d87  push    r15
0x180120d89  mov     rbp, rsp
0x180120d8c  sub     rsp, 50h
0x180120d90  xor     eax, eax
0x180120d92  xorps   xmm0, xmm0
0x180120d95  mov     [rbp+SourceString], rax
0x180120d99  mov     r12d, r8d
0x180120d9c  mov     [rbp+arg_8], eax
0x180120d9f  mov     r14, rdx
0x180120da2  mov     r13, rcx
0x180120da5  mov     r15d, eax
0x180120da8  mov     esi, eax
0x180120daa  mov     edi, eax
0x180120dac  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180120db0  test    rdx, rdx
0x180120db3  jz      loc_180120FDF
0x180120db9  cmp     [rdx], ax
0x180120dbc  jz      loc_180120FDF
0x180120dc2  lea     rdx, aDbregistrydefa; "dbRegistryDefaultName"
0x180120dc9  mov     rcx, r14; String1
0x180120dcc  mov     ebx, eax
0x180120dce  call    _wcsicmp
0x180120dd3  test    eax, eax
0x180120dd5  jnz     short loc_180120DDB
0x180120dd7  xor     edx, edx
0x180120dd9  jmp     short loc_180120DF6
0x180120ddb  mov     rdx, r14
0x180120dde  lea     rcx, [rbp+SourceString]
0x180120de2  call    AslStringDuplicate
0x180120de7  mov     r15, [rbp+SourceString]
0x180120deb  test    eax, eax
0x180120ded  js      loc_180121025
0x180120df3  mov     rdx, r15; SourceString
0x180120df6  lea     rcx, [rbp+DestinationString]; DestinationString
0x180120dfa  call    cs:__imp_RtlInitUnicodeString
0x180120e00  xor     r9d, r9d; KeyValueInformation
0x180120e03  lea     rax, [rbp+arg_8]
0x180120e07  mov     [rsp+50h+ResultLength], rax; ResultLength
0x180120e0c  lea     rdx, [rbp+DestinationString]; ValueName
0x180120e10  mov     rcx, r13; KeyHandle
0x180120e13  mov     [rsp+50h+Length], ebx; Length
0x180120e17  lea     r14d, [r9+1]
0x180120e1b  mov     r8d, r14d; KeyValueInformationClass
0x180120e1e  call    cs:__imp_ZwQueryValueKey
0x180120e24  test    eax, eax
0x180120e26  jns     short loc_180120E3E
0x180120e28  cmp     eax, 80000005h
0x180120e2d  jz      short loc_180120E3E
0x180120e2f  cmp     eax, 0C0000023h
0x180120e34  jz      short loc_180120E3E
0x180120e36  mov     ebx, r14d
0x180120e39  jmp     loc_180121025
0x180120e3e  mov     rcx, gs:60h
0x180120e47  mov     edx, 8; Flags
0x180120e4c  mov     r8d, [rbp+arg_8]; Size
0x180120e50  mov     rcx, [rcx+30h]; HeapHandle
0x180120e54  call    cs:__imp_RtlAllocateHeap
0x180120e5a  mov     rdi, rax
0x180120e5d  test    rax, rax
0x180120e60  jnz     short loc_180120E83
0x180120e62  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x180120e69  mov     r8d, 4E1h
0x180120e6f  lea     rdx, aSdbpcheckmatch_7; "SdbpCheckMatchingRegistryValue"
0x180120e76  mov     ecx, r14d
0x180120e79  call    AslLogCallPrintf
0x180120e7e  jmp     loc_180121025
0x180120e83  lea     rax, [rbp+arg_8]
0x180120e87  mov     r9, rdi; KeyValueInformation
0x180120e8a  mov     [rsp+50h+ResultLength], rax; ResultLength
0x180120e8f  lea     rdx, [rbp+DestinationString]; ValueName
0x180120e93  mov     eax, [rbp+arg_8]
0x180120e96  mov     r8d, r14d; KeyValueInformationClass
0x180120e99  mov     rcx, r13; KeyHandle
0x180120e9c  mov     [rsp+50h+Length], eax; Length
0x180120ea0  call    cs:__imp_ZwQueryValueKey
0x180120ea6  xor     r13d, r13d
0x180120ea9  test    eax, eax
0x180120eab  jns     short loc_180120ECE
0x180120ead  lea     r9, aFailedToReadVa_0; "Failed to read value"
0x180120eb4  mov     r8d, 4ECh
0x180120eba  mov     ecx, r14d
0x180120ebd  lea     rdx, aSdbpcheckmatch_7; "SdbpCheckMatchingRegistryValue"
0x180120ec4  call    AslLogCallPrintf
0x180120ec9  jmp     loc_180120FF6
0x180120ece  test    r12d, r12d
0x180120ed1  jnz     short loc_180120EE5
0x180120ed3  mov     rax, [rbp+arg_40]
0x180120eda  mov     [rax], r14d
0x180120edd  mov     ebx, r14d
0x180120ee0  jmp     loc_180120FF6
0x180120ee5  mov     ecx, [rdi+4]
0x180120ee8  cmp     ecx, r12d
0x180120eeb  jnz     short loc_180120EDD
0x180120eed  mov     r14d, [rdi+8]
0x180120ef1  add     r14, rdi
0x180120ef4  sub     ecx, 1
0x180120ef7  jz      loc_18012107C
0x180120efd  sub     ecx, 1
0x180120f00  jz      loc_18012107C
0x180120f06  sub     ecx, 1
0x180120f09  jz      loc_180121059
0x180120f0f  sub     ecx, 1
0x180120f12  jz      loc_180120FD3
0x180120f18  sub     ecx, 3
0x180120f1b  jz      short loc_180120F40
0x180120f1d  cmp     ecx, 4
0x180120f20  jz      short loc_180120F34
0x180120f22  lea     r9, aUnknownRegistr; "Unknown registry value data type"
0x180120f29  mov     r8d, 574h
0x180120f2f  jmp     loc_1801210B1
0x180120f34  mov     rax, [r14]
0x180120f37  cmp     [rbp+arg_28], rax
0x180120f3b  jmp     loc_180120FD9
0x180120f40  mov     rcx, gs:60h
0x180120f49  mov     edx, 8; Flags
0x180120f4e  mov     r8d, [rdi+0Ch]
0x180120f52  add     r8, 2; Size
0x180120f56  mov     rcx, [rcx+30h]; HeapHandle
0x180120f5a  call    cs:__imp_RtlAllocateHeap
0x180120f60  mov     rsi, rax
0x180120f63  test    rax, rax
0x180120f66  jnz     short loc_180120F73
0x180120f68  mov     r8d, 529h
0x180120f6e  jmp     loc_1801210AA
0x180120f73  mov     r8d, [rdi+0Ch]; Size
0x180120f77  mov     rdx, r14; Src
0x180120f7a  mov     rcx, rsi; void *
0x180120f7d  call    memmove_0
0x180120f82  mov     ecx, [rdi+0Ch]
0x180120f85  shr     rcx, 1
0x180120f88  mov     [rsi+rcx*2], r13w
0x180120f8d  mov     rcx, rsi
0x180120f90  mov     eax, [rdi+0Ch]
0x180120f93  and     rax, 0FFFFFFFFFFFFFFFEh
0x180120f97  add     rax, rsi
0x180120f9a  cmp     rsi, rax
0x180120f9d  jnb     loc_1801210D5
0x180120fa3  lea     rax, [rcx+2]
0x180120fa7  cmp     [rcx], r13w
0x180120fab  jnz     short loc_180120FBC
0x180120fad  cmp     [rax], r13w
0x180120fb1  jz      loc_1801210D5
0x180120fb7  mov     word ptr [rcx], 3Bh ; ';'
0x180120fbc  mov     rcx, rax
0x180120fbf  mov     eax, [rdi+0Ch]
0x180120fc2  and     rax, 0FFFFFFFFFFFFFFFEh
0x180120fc6  add     rax, rsi
0x180120fc9  cmp     rcx, rax
0x180120fcc  jb      short loc_180120FA3
0x180120fce  jmp     loc_1801210D5
0x180120fd3  mov     eax, [r14]
0x180120fd6  cmp     [rbp+arg_20], eax
0x180120fd9  jnz     loc_1801210E9
0x180120fdf  mov     rax, [rbp+arg_40]
0x180120fe6  mov     dword ptr [rax], 1
0x180120fec  mov     ebx, 1
0x180120ff1  test    rdi, rdi
0x180120ff4  jz      short loc_18012100B
0x180120ff6  mov     rcx, gs:60h
0x180120fff  mov     rdx, rdi
0x180121002  mov     rcx, [rcx+30h]
0x180121006  call    AslFree
0x18012100b  test    rsi, rsi
0x18012100e  jz      short loc_180121025
0x180121010  mov     rcx, gs:60h
0x180121019  mov     rdx, rsi
0x18012101c  mov     rcx, [rcx+30h]
0x180121020  call    AslFree
0x180121025  test    r15, r15
0x180121028  jz      short loc_18012103F
0x18012102a  mov     rcx, gs:60h
0x180121033  mov     rdx, r15
0x180121036  mov     rcx, [rcx+30h]
0x18012103a  call    AslFree
0x18012103f  mov     eax, ebx
0x180121041  mov     rbx, [rsp+50h+arg_0]
0x180121049  add     rsp, 50h
0x18012104d  pop     r15
0x18012104f  pop     r14
0x180121051  pop     r13
0x180121053  pop     r12
0x180121055  pop     rdi
0x180121056  pop     rsi
0x180121057  pop     rbp
0x180121058  retn
0x180121059  mov     eax, [rdi+0Ch]
0x18012105c  mov     r8, [rbp+Size]; Size
0x180121060  cmp     r8, rax
0x180121063  jnz     loc_1801210E9
0x180121069  mov     rcx, [rbp+Buf1]; Buf1
0x18012106d  mov     rdx, r14; Buf2
0x180121070  call    memcmp_0
0x180121075  test    eax, eax
0x180121077  jmp     loc_180120FD9
0x18012107c  mov     rcx, gs:60h
0x180121085  mov     edx, 8; Flags
0x18012108a  mov     r8d, [rdi+0Ch]
0x18012108e  add     r8, 2; Size
0x180121092  mov     rcx, [rcx+30h]; HeapHandle
0x180121096  call    cs:__imp_RtlAllocateHeap
0x18012109c  mov     rsi, rax
0x18012109f  test    rax, rax
0x1801210a2  jnz     short loc_1801210BB
0x1801210a4  mov     r8d, 511h
0x1801210aa  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x1801210b1  mov     ecx, 1
0x1801210b6  jmp     loc_180120EBD
0x1801210bb  mov     r8d, [rdi+0Ch]; Size
0x1801210bf  mov     rdx, r14; Src
0x1801210c2  mov     rcx, rsi; void *
0x1801210c5  call    memmove_0
0x1801210ca  mov     ecx, [rdi+0Ch]
0x1801210cd  shr     rcx, 1
0x1801210d0  mov     [rsi+rcx*2], r13w
0x1801210d5  mov     rcx, [rbp+arg_18]
0x1801210d9  mov     rdx, rsi
0x1801210dc  call    AslStringPatternMatchExW
0x1801210e1  test    eax, eax
0x1801210e3  jnz     loc_180120FDF
0x1801210e9  mov     ebx, 1
0x1801210ee  jmp     loc_180120FF6
```
