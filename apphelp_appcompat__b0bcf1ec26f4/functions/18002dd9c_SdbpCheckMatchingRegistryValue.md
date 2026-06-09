# SdbpCheckMatchingRegistryValue

- ea: `0x18002dd9c`
- end: `0x18002e121`
- name: `SdbpCheckMatchingRegistryValue`
- size: `901`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, wchar_t *String1@<rdx>, int, __int64, void *Buf1, size_t Size, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18002dba4`
- `0x18004e30c`

## callees

- `0x18000bd50`
- `0x18000f114`
- `0x18001577c`
- `0x180018f20`
- `0x18002dd9c`
- `0x180039a5a`
- `0x180059211`
- `0x180059229`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002de22`
- `ntdll!RtlInitUnicodeString` at `0x18002de22`
- `ntdll!ZwQueryValueKey` at `0x18002de46`
- `ntdll!ZwQueryValueKey` at `0x18002dec8`
- `ntdll!ZwQueryValueKey` at `0x18002de46`
- `ntdll!ZwQueryValueKey` at `0x18002dec8`
- `ntdll!RtlAllocateHeap` at `0x18002de7c`
- `ntdll!RtlAllocateHeap` at `0x18002df82`
- `ntdll!RtlAllocateHeap` at `0x18002e0be`
- `ntdll!RtlAllocateHeap` at `0x18002de7c`
- `ntdll!RtlAllocateHeap` at `0x18002df82`
- `ntdll!RtlAllocateHeap` at `0x18002e0be`

## string_xrefs

- `0x18002ddea`: `dbRegistryDefaultName`
- `0x18002de97`: `SdbpCheckMatchingRegistryValue`
- `0x18002dee5`: `SdbpCheckMatchingRegistryValue`
- `0x18002df4a`: `Unknown registry value data type`
- `0x18002ded5`: `Failed to read value`

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
  __int64 v21; // r8
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
  if ( wcsicmp_0(String1, L"dbRegistryDefaultName") )
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
    AslLogCallPrintf(1, "SdbpCheckMatchingRegistryValue", 1249, "Failed to allocate memory");
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
    if ( !(unsigned int)AslStringPatternMatchExW(v37, v13, 0, 0) )
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
  AslLogCallPrintf(1, "SdbpCheckMatchingRegistryValue", v21, v20);
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
0x18002dd9c  mov     [rsp-38h+arg_0], rbx
0x18002dda1  mov     [rsp-38h+arg_18], r9
0x18002dda6  push    rbp
0x18002dda7  push    rsi
0x18002dda8  push    rdi
0x18002dda9  push    r12
0x18002ddab  push    r13
0x18002ddad  push    r14
0x18002ddaf  push    r15
0x18002ddb1  mov     rbp, rsp
0x18002ddb4  sub     rsp, 50h
0x18002ddb8  xor     eax, eax
0x18002ddba  xorps   xmm0, xmm0
0x18002ddbd  mov     [rbp+SourceString], rax
0x18002ddc1  mov     r12d, r8d
0x18002ddc4  mov     [rbp+arg_8], eax
0x18002ddc7  mov     r14, rdx
0x18002ddca  mov     r13, rcx
0x18002ddcd  mov     r15d, eax
0x18002ddd0  mov     esi, eax
0x18002ddd2  mov     edi, eax
0x18002ddd4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002ddd8  test    rdx, rdx
0x18002dddb  jz      loc_18002E007
0x18002dde1  cmp     [rdx], ax
0x18002dde4  jz      loc_18002E007
0x18002ddea  lea     rdx, aDbregistrydefa; "dbRegistryDefaultName"
0x18002ddf1  mov     rcx, r14; String1
0x18002ddf4  mov     ebx, eax
0x18002ddf6  call    _wcsicmp_0
0x18002ddfb  test    eax, eax
0x18002ddfd  jnz     short loc_18002DE03
0x18002ddff  xor     edx, edx
0x18002de01  jmp     short loc_18002DE1E
0x18002de03  mov     rdx, r14
0x18002de06  lea     rcx, [rbp+SourceString]
0x18002de0a  call    AslStringDuplicate
0x18002de0f  mov     r15, [rbp+SourceString]
0x18002de13  test    eax, eax
0x18002de15  js      loc_18002E04D
0x18002de1b  mov     rdx, r15; SourceString
0x18002de1e  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002de22  call    cs:__imp_RtlInitUnicodeString
0x18002de28  xor     r9d, r9d; KeyValueInformation
0x18002de2b  lea     rax, [rbp+arg_8]
0x18002de2f  mov     [rsp+50h+ResultLength], rax; ResultLength
0x18002de34  lea     rdx, [rbp+DestinationString]; ValueName
0x18002de38  mov     rcx, r13; KeyHandle
0x18002de3b  mov     [rsp+50h+Length], ebx; Length
0x18002de3f  lea     r14d, [r9+1]
0x18002de43  mov     r8d, r14d; KeyValueInformationClass
0x18002de46  call    cs:__imp_ZwQueryValueKey
0x18002de4c  test    eax, eax
0x18002de4e  jns     short loc_18002DE66
0x18002de50  cmp     eax, 80000005h
0x18002de55  jz      short loc_18002DE66
0x18002de57  cmp     eax, 0C0000023h
0x18002de5c  jz      short loc_18002DE66
0x18002de5e  mov     ebx, r14d
0x18002de61  jmp     loc_18002E04D
0x18002de66  mov     rcx, gs:60h
0x18002de6f  mov     edx, 8; Flags
0x18002de74  mov     r8d, [rbp+arg_8]; Size
0x18002de78  mov     rcx, [rcx+30h]; HeapHandle
0x18002de7c  call    cs:__imp_RtlAllocateHeap
0x18002de82  mov     rdi, rax
0x18002de85  test    rax, rax
0x18002de88  jnz     short loc_18002DEAB
0x18002de8a  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x18002de91  mov     r8d, 4E1h
0x18002de97  lea     rdx, aSdbpcheckmatch_7; "SdbpCheckMatchingRegistryValue"
0x18002de9e  mov     ecx, r14d
0x18002dea1  call    AslLogCallPrintf
0x18002dea6  jmp     loc_18002E04D
0x18002deab  lea     rax, [rbp+arg_8]
0x18002deaf  mov     r9, rdi; KeyValueInformation
0x18002deb2  mov     [rsp+50h+ResultLength], rax; ResultLength
0x18002deb7  lea     rdx, [rbp+DestinationString]; ValueName
0x18002debb  mov     eax, [rbp+arg_8]
0x18002debe  mov     r8d, r14d; KeyValueInformationClass
0x18002dec1  mov     rcx, r13; KeyHandle
0x18002dec4  mov     [rsp+50h+Length], eax; Length
0x18002dec8  call    cs:__imp_ZwQueryValueKey
0x18002dece  xor     r13d, r13d
0x18002ded1  test    eax, eax
0x18002ded3  jns     short loc_18002DEF6
0x18002ded5  lea     r9, aFailedToReadVa_2; "Failed to read value"
0x18002dedc  mov     r8d, 4ECh
0x18002dee2  mov     ecx, r14d
0x18002dee5  lea     rdx, aSdbpcheckmatch_7; "SdbpCheckMatchingRegistryValue"
0x18002deec  call    AslLogCallPrintf
0x18002def1  jmp     loc_18002E01E
0x18002def6  test    r12d, r12d
0x18002def9  jnz     short loc_18002DF0D
0x18002defb  mov     rax, [rbp+arg_40]
0x18002df02  mov     [rax], r14d
0x18002df05  mov     ebx, r14d
0x18002df08  jmp     loc_18002E01E
0x18002df0d  mov     ecx, [rdi+4]
0x18002df10  cmp     ecx, r12d
0x18002df13  jnz     short loc_18002DF05
0x18002df15  mov     r14d, [rdi+8]
0x18002df19  add     r14, rdi
0x18002df1c  sub     ecx, 1
0x18002df1f  jz      loc_18002E0A4
0x18002df25  sub     ecx, 1
0x18002df28  jz      loc_18002E0A4
0x18002df2e  sub     ecx, 1
0x18002df31  jz      loc_18002E081
0x18002df37  sub     ecx, 1
0x18002df3a  jz      loc_18002DFFB
0x18002df40  sub     ecx, 3
0x18002df43  jz      short loc_18002DF68
0x18002df45  cmp     ecx, 4
0x18002df48  jz      short loc_18002DF5C
0x18002df4a  lea     r9, aUnknownRegistr; "Unknown registry value data type"
0x18002df51  mov     r8d, 574h
0x18002df57  jmp     loc_18002E0D9
0x18002df5c  mov     rax, [r14]
0x18002df5f  cmp     [rbp+arg_28], rax
0x18002df63  jmp     loc_18002E001
0x18002df68  mov     rcx, gs:60h
0x18002df71  mov     edx, 8; Flags
0x18002df76  mov     r8d, [rdi+0Ch]
0x18002df7a  add     r8, 2; Size
0x18002df7e  mov     rcx, [rcx+30h]; HeapHandle
0x18002df82  call    cs:__imp_RtlAllocateHeap
0x18002df88  mov     rsi, rax
0x18002df8b  test    rax, rax
0x18002df8e  jnz     short loc_18002DF9B
0x18002df90  mov     r8d, 529h
0x18002df96  jmp     loc_18002E0D2
0x18002df9b  mov     r8d, [rdi+0Ch]; Size
0x18002df9f  mov     rdx, r14; Src
0x18002dfa2  mov     rcx, rsi; void *
0x18002dfa5  call    memmove_0
0x18002dfaa  mov     ecx, [rdi+0Ch]
0x18002dfad  shr     rcx, 1
0x18002dfb0  mov     [rsi+rcx*2], r13w
0x18002dfb5  mov     rcx, rsi
0x18002dfb8  mov     eax, [rdi+0Ch]
0x18002dfbb  and     rax, 0FFFFFFFFFFFFFFFEh
0x18002dfbf  add     rax, rsi
0x18002dfc2  cmp     rsi, rax
0x18002dfc5  jnb     loc_18002E0FD
0x18002dfcb  lea     rax, [rcx+2]
0x18002dfcf  cmp     [rcx], r13w
0x18002dfd3  jnz     short loc_18002DFE4
0x18002dfd5  cmp     [rax], r13w
0x18002dfd9  jz      loc_18002E0FD
0x18002dfdf  mov     word ptr [rcx], 3Bh ; ';'
0x18002dfe4  mov     rcx, rax
0x18002dfe7  mov     eax, [rdi+0Ch]
0x18002dfea  and     rax, 0FFFFFFFFFFFFFFFEh
0x18002dfee  add     rax, rsi
0x18002dff1  cmp     rcx, rax
0x18002dff4  jb      short loc_18002DFCB
0x18002dff6  jmp     loc_18002E0FD
0x18002dffb  mov     eax, [r14]
0x18002dffe  cmp     [rbp+arg_20], eax
0x18002e001  jnz     loc_18002E117
0x18002e007  mov     rax, [rbp+arg_40]
0x18002e00e  mov     dword ptr [rax], 1
0x18002e014  mov     ebx, 1
0x18002e019  test    rdi, rdi
0x18002e01c  jz      short loc_18002E033
0x18002e01e  mov     rcx, gs:60h
0x18002e027  mov     rdx, rdi
0x18002e02a  mov     rcx, [rcx+30h]
0x18002e02e  call    AslFree
0x18002e033  test    rsi, rsi
0x18002e036  jz      short loc_18002E04D
0x18002e038  mov     rcx, gs:60h
0x18002e041  mov     rdx, rsi
0x18002e044  mov     rcx, [rcx+30h]
0x18002e048  call    AslFree
0x18002e04d  test    r15, r15
0x18002e050  jz      short loc_18002E067
0x18002e052  mov     rcx, gs:60h
0x18002e05b  mov     rdx, r15
0x18002e05e  mov     rcx, [rcx+30h]
0x18002e062  call    AslFree
0x18002e067  mov     eax, ebx
0x18002e069  mov     rbx, [rsp+50h+arg_0]
0x18002e071  add     rsp, 50h
0x18002e075  pop     r15
0x18002e077  pop     r14
0x18002e079  pop     r13
0x18002e07b  pop     r12
0x18002e07d  pop     rdi
0x18002e07e  pop     rsi
0x18002e07f  pop     rbp
0x18002e080  retn
0x18002e081  mov     eax, [rdi+0Ch]
0x18002e084  mov     r8, [rbp+Size]; Size
0x18002e088  cmp     r8, rax
0x18002e08b  jnz     loc_18002E117
0x18002e091  mov     rcx, [rbp+Buf1]; Buf1
0x18002e095  mov     rdx, r14; Buf2
0x18002e098  call    memcmp_0
0x18002e09d  test    eax, eax
0x18002e09f  jmp     loc_18002E001
0x18002e0a4  mov     rcx, gs:60h
0x18002e0ad  mov     edx, 8; Flags
0x18002e0b2  mov     r8d, [rdi+0Ch]
0x18002e0b6  add     r8, 2; Size
0x18002e0ba  mov     rcx, [rcx+30h]; HeapHandle
0x18002e0be  call    cs:__imp_RtlAllocateHeap
0x18002e0c4  mov     rsi, rax
0x18002e0c7  test    rax, rax
0x18002e0ca  jnz     short loc_18002E0E3
0x18002e0cc  mov     r8d, 511h
0x18002e0d2  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x18002e0d9  mov     ecx, 1
0x18002e0de  jmp     loc_18002DEE5
0x18002e0e3  mov     r8d, [rdi+0Ch]; Size
0x18002e0e7  mov     rdx, r14; Src
0x18002e0ea  mov     rcx, rsi; void *
0x18002e0ed  call    memmove_0
0x18002e0f2  mov     ecx, [rdi+0Ch]
0x18002e0f5  shr     rcx, 1
0x18002e0f8  mov     [rsi+rcx*2], r13w
0x18002e0fd  mov     rcx, [rbp+arg_18]
0x18002e101  xor     r9d, r9d
0x18002e104  xor     r8d, r8d
0x18002e107  mov     rdx, rsi
0x18002e10a  call    AslStringPatternMatchExW
0x18002e10f  test    eax, eax
0x18002e111  jnz     loc_18002E007
0x18002e117  mov     ebx, 1
0x18002e11c  jmp     loc_18002E01E
```
