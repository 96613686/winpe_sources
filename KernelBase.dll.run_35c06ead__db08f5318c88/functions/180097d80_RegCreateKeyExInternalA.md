# RegCreateKeyExInternalA

- ea: `0x180097d80`
- end: `0x1800980c5`
- name: `RegCreateKeyExInternalA`
- size: `837`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180097c40`
- `0x180097ca0`

## callees

- `0x18005a0c0`
- `0x18005bb80`
- `0x18005d0a0`
- `0x180097d80`
- `0x180099998`
- `0x18012d578`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x180097f4d`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180097f4d`
- `ntdll!RtlFreeUnicodeString` at `0x180097eda`
- `ntdll!RtlFreeUnicodeString` at `0x180097eee`
- `ntdll!RtlFreeUnicodeString` at `0x1800980ba`
- `ntdll!RtlFreeUnicodeString` at `0x180097eda`
- `ntdll!RtlFreeUnicodeString` at `0x180097eee`
- `ntdll!RtlFreeUnicodeString` at `0x1800980ba`
- `ntdll!RtlNtStatusToDosError` at `0x18009808c`
- `ntdll!RtlNtStatusToDosError` at `0x1800980a8`
- `ntdll!RtlNtStatusToDosError` at `0x18009808c`
- `ntdll!RtlNtStatusToDosError` at `0x1800980a8`
- `ntdll!RtlInitAnsiStringEx` at `0x180097f2f`
- `ntdll!RtlInitAnsiStringEx` at `0x180097f2f`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180097e39`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180097e39`
- `ntdll!RtlFreeHeap` at `0x18009807f`
- `ntdll!RtlFreeHeap` at `0x18009807f`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegGetVersion` at `0x18009803f`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegGetVersion` at `0x18009803f`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegCreateKey` at `0x180097ff8`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegCreateKey` at `0x180097ff8`

## pseudocode

```c
__int64 __fastcall RegCreateKeyExInternalA(
        void *a1,
        const char *a2,
        int a3,
        const char *a4,
        ULONG a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  HANDLE *v12; // r15
  ULONG v13; // edi
  PVOID *v14; // rsi
  unsigned __int64 v15; // r14
  int inited; // eax
  unsigned __int64 v18; // r14
  char v19; // al
  unsigned int v20; // ecx
  int v21; // [rsp+30h] [rbp-A8h]
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-88h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+60h] [rbp-78h] BYREF
  ULONG v24; // [rsp+70h] [rbp-68h]
  PVOID *v25; // [rsp+78h] [rbp-60h]
  __int64 v26; // [rsp+80h] [rbp-58h] BYREF
  __int64 v27; // [rsp+88h] [rbp-50h] BYREF
  struct _STRING DestinationString; // [rsp+90h] [rbp-48h] BYREF
  _BYTE v29[32]; // [rsp+A0h] [rbp-38h] BYREF
  HANDLE KeyHandle; // [rsp+E0h] [rbp+8h] BYREF

  KeyHandle = a1;
  Destination = 0;
  UnicodeString = 0;
  DestinationString = 0;
  memset(v29, 0, 28);
  v27 = 0;
  v26 = 0;
  if ( a1 == (void *)-2147483644LL || a1 == (void *)-2147483568LL || a1 == (void *)-2147483552LL )
    return 6;
  if ( a3 )
    return 87;
  if ( a2 )
  {
    v12 = (HANDLE *)a8;
    if ( a8 )
    {
      v13 = MapPredefinedHandleInternal(a1, &KeyHandle, &v27, &v26);
      if ( v13 )
      {
LABEL_18:
        CLOSE_LOCAL_HANDLE_INTERNAL(v27, v26);
        return v13;
      }
      if ( !RtlCreateUnicodeStringFromAsciiz(&Destination, a2) )
      {
        v13 = RtlNtStatusToDosError(-1073741801);
        goto LABEL_18;
      }
      Destination.Length += 2;
      if ( a4 )
      {
        inited = RtlInitAnsiStringEx(&DestinationString, a4);
        if ( inited < 0 || (inited = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u), inited < 0) )
        {
          v13 = RtlNtStatusToDosError(inited);
          goto LABEL_17;
        }
        UnicodeString.Length += 2;
      }
      else
      {
        *(_DWORD *)&UnicodeString.Length = 0;
        UnicodeString.Buffer = 0;
      }
      if ( !a7 )
      {
        v14 = 0;
LABEL_13:
        v25 = v14;
        v15 = (unsigned __int64)KeyHandle;
        if ( ((unsigned __int8)KeyHandle & 1) != 0 )
        {
          if ( (unsigned __int8)IsBaseRegCloseKeyPresent() )
          {
            LODWORD(KeyHandle) = 0;
            v18 = v15 & 0xFFFFFFFFFFFFFFFEuLL;
            if ( !(unsigned __int8)IsBaseRegCloseKeyPresent()
              || (unsigned int)BaseRegGetVersion(v18, &KeyHandle)
              || (v19 = 1, (_DWORD)KeyHandle != 6) )
            {
              v19 = 0;
            }
            v20 = a6 & 0xFFFFFCFF;
            if ( v19 )
              v20 = a6;
            v13 = BaseRegCreateKey(v18, &Destination, &UnicodeString, a5, v20, v14, v12, a9);
            v24 = v13;
            if ( !v13 )
              *v12 = (HANDLE)((unsigned __int64)*v12 | 1);
          }
        }
        else
        {
          v13 = BaseRegCreateKeyInternal(
                  KeyHandle,
                  &Destination,
                  &UnicodeString,
                  a5,
                  a6,
                  (__int64)v14,
                  v21,
                  v12,
                  (_DWORD *)a9,
                  (void *)a10);
        }
        RtlFreeUnicodeString(&UnicodeString);
        if ( v14 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14[1]);
        goto LABEL_17;
      }
      v13 = MapSAToRpcSA(a7, v29);
      if ( !v13 )
      {
        v14 = (PVOID *)v29;
        goto LABEL_13;
      }
      RtlFreeUnicodeString(&UnicodeString);
LABEL_17:
      RtlFreeUnicodeString(&Destination);
      goto LABEL_18;
    }
  }
  return 1010;
}

```

## disassembly

```asm
0x180097d80  mov     r11, rsp
0x180097d83  mov     [r11+10h], rbx
0x180097d87  mov     [r11+18h], rsi
0x180097d8b  mov     [r11+8], rcx
0x180097d8f  push    rdi
0x180097d90  push    r14
0x180097d92  push    r15
0x180097d94  sub     rsp, 0C0h
0x180097d9b  mov     r14, r9
0x180097d9e  mov     rsi, rdx
0x180097da1  xorps   xmm0, xmm0
0x180097da4  movups  xmmword ptr [rsp+0D8h+Destination.Length], xmm0
0x180097da9  xorps   xmm1, xmm1
0x180097dac  movups  xmmword ptr [rsp+0D8h+UnicodeString.Length], xmm1
0x180097db1  movups  xmmword ptr [r11-48h], xmm0
0x180097db6  xor     eax, eax
0x180097db8  movups  xmmword ptr [r11-38h], xmm0
0x180097dbd  movups  xmmword ptr [r11-2Ch], xmm0
0x180097dc2  xor     ebx, ebx
0x180097dc4  mov     [r11-50h], rbx
0x180097dc8  mov     [r11-58h], rbx
0x180097dcc  cmp     rcx, 0FFFFFFFF80000004h
0x180097dd3  jz      loc_180098062
0x180097dd9  cmp     rcx, 0FFFFFFFF80000050h
0x180097de0  jz      loc_180098062
0x180097de6  cmp     rcx, 0FFFFFFFF80000060h
0x180097ded  jz      loc_180098062
0x180097df3  test    r8d, r8d
0x180097df6  jnz     loc_180098099
0x180097dfc  test    rdx, rdx
0x180097dff  jz      loc_18009802A
0x180097e05  mov     r15, [rsp+0D8h+arg_38]
0x180097e0d  test    r15, r15
0x180097e10  jz      loc_18009802A
0x180097e16  lea     r9, [r11-58h]
0x180097e1a  lea     r8, [r11-50h]
0x180097e1e  lea     rdx, [r11+8]
0x180097e22  call    MapPredefinedHandleInternal
0x180097e27  mov     edi, eax
0x180097e29  test    eax, eax
0x180097e2b  jnz     loc_180097EF4
0x180097e31  mov     rdx, rsi; Source
0x180097e34  lea     rcx, [rsp+0D8h+Destination]; Destination
0x180097e39  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x180097e3f  test    al, al
0x180097e41  jz      loc_1800980A3
0x180097e47  add     [rsp+0D8h+Destination.Length], 2
0x180097e4d  test    r14, r14
0x180097e50  jnz     loc_180097F24
0x180097e56  mov     dword ptr [rsp+0D8h+UnicodeString.Length], ebx
0x180097e5a  mov     [rsp+0D8h+UnicodeString.Buffer], rbx
0x180097e5f  mov     rcx, [rsp+0D8h+arg_30]
0x180097e67  test    rcx, rcx
0x180097e6a  jnz     loc_180097F66
0x180097e70  mov     rsi, rbx
0x180097e73  mov     [rsp+0D8h+var_60], rsi
0x180097e78  mov     r14, [rsp+0D8h+KeyHandle]
0x180097e80  test    r14b, 1
0x180097e84  jnz     loc_180097F8A
0x180097e8a  mov     rax, [rsp+0D8h+arg_48]
0x180097e92  mov     [rsp+0D8h+var_90], rax; __int64
0x180097e97  mov     rax, [rsp+0D8h+arg_40]
0x180097e9f  mov     [rsp+0D8h+var_98], rax; __int64
0x180097ea4  mov     [rsp+0D8h+var_A0], r15; __int64
0x180097ea9  mov     [rsp+0D8h+var_B0], rsi; __int64
0x180097eae  mov     eax, [rsp+0D8h+arg_28]
0x180097eb5  mov     [rsp+0D8h+var_B8], eax; int
0x180097eb9  mov     r9d, [rsp+0D8h+arg_20]
0x180097ec1  lea     r8, [rsp+0D8h+UnicodeString]
0x180097ec6  lea     rdx, [rsp+0D8h+Destination]; Source
0x180097ecb  mov     rcx, r14; KeyHandle
0x180097ece  call    BaseRegCreateKeyInternal
0x180097ed3  mov     edi, eax
0x180097ed5  lea     rcx, [rsp+0D8h+UnicodeString]; UnicodeString
0x180097eda  call    cs:__imp_RtlFreeUnicodeString
0x180097ee0  test    rsi, rsi
0x180097ee3  jnz     loc_18009806C
0x180097ee9  lea     rcx, [rsp+0D8h+Destination]; UnicodeString
0x180097eee  call    cs:__imp_RtlFreeUnicodeString
0x180097ef4  mov     rdx, [rsp+0D8h+var_58]
0x180097efc  mov     rcx, [rsp+0D8h+var_50]
0x180097f04  call    CLOSE_LOCAL_HANDLE_INTERNAL
0x180097f09  mov     eax, edi
0x180097f0b  lea     r11, [rsp+0D8h+var_18]
0x180097f13  mov     rbx, [r11+28h]
0x180097f17  mov     rsi, [r11+30h]
0x180097f1b  mov     rsp, r11
0x180097f1e  pop     r15
0x180097f20  pop     r14
0x180097f22  pop     rdi
0x180097f23  retn
0x180097f24  mov     rdx, r14; SourceString
0x180097f27  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x180097f2f  call    cs:__imp_RtlInitAnsiStringEx
0x180097f35  test    eax, eax
0x180097f37  js      loc_18009808A
0x180097f3d  mov     r8b, 1; AllocateDestinationString
0x180097f40  lea     rdx, [rsp+0D8h+DestinationString]; SourceString
0x180097f48  lea     rcx, [rsp+0D8h+UnicodeString]; DestinationString
0x180097f4d  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180097f53  test    eax, eax
0x180097f55  js      loc_18009808A
0x180097f5b  add     [rsp+0D8h+UnicodeString.Length], 2
0x180097f61  jmp     loc_180097E5F
0x180097f66  lea     rdx, [rsp+0D8h+var_38]
0x180097f6e  call    MapSAToRpcSA
0x180097f73  mov     edi, eax
0x180097f75  test    eax, eax
0x180097f77  jnz     loc_1800980B5
0x180097f7d  lea     rsi, [rsp+0D8h+var_38]
0x180097f85  jmp     loc_180097E73
0x180097f8a  call    IsBaseRegCloseKeyPresent
0x180097f8f  test    al, al
0x180097f91  jz      loc_180097ED5
0x180097f97  mov     dword ptr [rsp+0D8h+KeyHandle], ebx
0x180097f9e  and     r14, 0FFFFFFFFFFFFFFFEh
0x180097fa2  call    IsBaseRegCloseKeyPresent
0x180097fa7  test    al, al
0x180097fa9  jnz     loc_180098034
0x180097faf  mov     al, bl
0x180097fb1  mov     ecx, [rsp+0D8h+arg_28]
0x180097fb8  and     ecx, 0FFFFFCFFh
0x180097fbe  test    al, al
0x180097fc0  cmovnz  ecx, [rsp+0D8h+arg_28]
0x180097fc8  mov     rax, [rsp+0D8h+arg_40]
0x180097fd0  mov     [rsp+0D8h+var_A0], rax
0x180097fd5  mov     [rsp+0D8h+var_A8], r15
0x180097fda  mov     [rsp+0D8h+var_B0], rsi
0x180097fdf  mov     [rsp+0D8h+var_B8], ecx
0x180097fe3  mov     r9d, [rsp+0D8h+arg_20]
0x180097feb  lea     r8, [rsp+0D8h+UnicodeString]
0x180097ff0  lea     rdx, [rsp+0D8h+Destination]
0x180097ff5  mov     rcx, r14
0x180097ff8  call    cs:__imp_BaseRegCreateKey
0x180097ffe  mov     edi, eax
0x180098000  mov     [rsp+0D8h+var_68], eax
0x180098004  jmp     short loc_180098019
0x180098006  mov     edi, eax
0x180098008  mov     [rsp+0D8h+var_68], eax
0x18009800c  mov     r15, [rsp+0D8h+arg_38]
0x180098014  mov     rsi, [rsp+0D8h+var_60]
0x180098019  test    edi, edi
0x18009801b  jnz     loc_180097ED5
0x180098021  or      qword ptr [r15], 1
0x180098025  jmp     loc_180097ED5
0x18009802a  mov     eax, 3F2h
0x18009802f  jmp     loc_180097F0B
0x180098034  lea     rdx, [rsp+0D8h+KeyHandle]
0x18009803c  mov     rcx, r14
0x18009803f  call    cs:__imp_BaseRegGetVersion
0x180098045  test    eax, eax
0x180098047  jnz     loc_180097FAF
0x18009804d  cmp     dword ptr [rsp+0D8h+KeyHandle], 6
0x180098055  mov     al, 1
0x180098057  jz      loc_180097FB1
0x18009805d  jmp     loc_180097FAF
0x180098062  mov     eax, 6
0x180098067  jmp     loc_180097F0B
0x18009806c  mov     rcx, gs:60h
0x180098075  mov     r8, [rsi+8]; P
0x180098079  xor     edx, edx; Flags
0x18009807b  mov     rcx, [rcx+30h]; HeapHandle
0x18009807f  call    cs:__imp_RtlFreeHeap
0x180098085  jmp     loc_180097EE9
0x18009808a  mov     ecx, eax; Status
0x18009808c  call    cs:__imp_RtlNtStatusToDosError
0x180098092  mov     edi, eax
0x180098094  jmp     loc_180097EE9
0x180098099  mov     eax, 57h ; 'W'
0x18009809e  jmp     loc_180097F0B
0x1800980a3  mov     ecx, 0C0000017h; Status
0x1800980a8  call    cs:__imp_RtlNtStatusToDosError
0x1800980ae  mov     edi, eax
0x1800980b0  jmp     loc_180097EF4
0x1800980b5  lea     rcx, [rsp+0D8h+UnicodeString]; UnicodeString
0x1800980ba  call    cs:__imp_RtlFreeUnicodeString
0x1800980c0  jmp     loc_180097EE9
```
