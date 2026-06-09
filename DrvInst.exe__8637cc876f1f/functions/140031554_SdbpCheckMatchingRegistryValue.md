# SdbpCheckMatchingRegistryValue

- ea: `0x140031554`
- end: `0x1400318d3`
- name: `SdbpCheckMatchingRegistryValue`
- size: `895`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, wchar_t *String1@<rdx>, int, __int64, void *Buf1, size_t Size, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x14003136c`
- `0x14003234c`

## callees

- `0x140001b64`
- `0x140031554`
- `0x14003bf18`
- `0x14003c368`
- `0x140041140`
- `0x1400413fc`
- `0x140045ec6`
- `0x140045ede`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1400315da`
- `ntdll!RtlInitUnicodeString` at `0x1400315da`
- `ntdll!ZwQueryValueKey` at `0x1400315fe`
- `ntdll!ZwQueryValueKey` at `0x140031680`
- `ntdll!ZwQueryValueKey` at `0x1400315fe`
- `ntdll!ZwQueryValueKey` at `0x140031680`
- `ntdll!RtlAllocateHeap` at `0x140031634`
- `ntdll!RtlAllocateHeap` at `0x14003173a`
- `ntdll!RtlAllocateHeap` at `0x140031876`
- `ntdll!RtlAllocateHeap` at `0x140031634`
- `ntdll!RtlAllocateHeap` at `0x14003173a`
- `ntdll!RtlAllocateHeap` at `0x140031876`

## string_xrefs

- `0x14003164f`: `SdbpCheckMatchingRegistryValue`
- `0x14003169d`: `SdbpCheckMatchingRegistryValue`
- `0x1400315a2`: `dbRegistryDefaultName`
- `0x14003168d`: `Failed to read value`
- `0x140031702`: `Unknown registry value data type`

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
  WCHAR *v12; // r15
  char *v13; // rsi
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
  char *v30; // rax
  char *i; // rcx
  char *v33; // rax
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
    v12 = (WCHAR *)SourceString;
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
      v30 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v14[3] + 2LL);
      v13 = v30;
      if ( !v30 )
      {
        v21 = 1321;
LABEL_49:
        v20 = "Failed to allocate memory";
        goto LABEL_15;
      }
      memmove_0(v30, v23, (unsigned int)v14[3]);
      *(_WORD *)&v13[2 * ((unsigned __int64)(unsigned int)v14[3] >> 1)] = 0;
      for ( i = v13; i < &v13[v14[3] & 0xFFFFFFFE]; i += 2 )
      {
        if ( !*(_WORD *)i )
        {
          if ( !*((_WORD *)i + 1) )
            break;
          *(_WORD *)i = 59;
        }
      }
    }
    else
    {
      v33 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v14[3] + 2LL);
      v13 = v33;
      if ( !v33 )
      {
        v21 = 1297;
        goto LABEL_49;
      }
      memmove_0(v33, v23, (unsigned int)v14[3]);
      *(_WORD *)&v13[2 * ((unsigned __int64)(unsigned int)v14[3] >> 1)] = 0;
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
0x140031554  mov     [rsp-38h+arg_0], rbx
0x140031559  mov     [rsp-38h+arg_18], r9
0x14003155e  push    rbp
0x14003155f  push    rsi
0x140031560  push    rdi
0x140031561  push    r12
0x140031563  push    r13
0x140031565  push    r14
0x140031567  push    r15
0x140031569  mov     rbp, rsp
0x14003156c  sub     rsp, 50h
0x140031570  xor     eax, eax
0x140031572  xorps   xmm0, xmm0
0x140031575  mov     [rbp+SourceString], rax
0x140031579  mov     r12d, r8d
0x14003157c  mov     [rbp+arg_8], eax
0x14003157f  mov     r14, rdx
0x140031582  mov     r13, rcx
0x140031585  mov     r15d, eax
0x140031588  mov     esi, eax
0x14003158a  mov     edi, eax
0x14003158c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140031590  test    rdx, rdx
0x140031593  jz      loc_1400317BF
0x140031599  cmp     [rdx], ax
0x14003159c  jz      loc_1400317BF
0x1400315a2  lea     rdx, aDbregistrydefa; "dbRegistryDefaultName"
0x1400315a9  mov     rcx, r14; String1
0x1400315ac  mov     ebx, eax
0x1400315ae  call    _wcsicmp_0
0x1400315b3  test    eax, eax
0x1400315b5  jnz     short loc_1400315BB
0x1400315b7  xor     edx, edx
0x1400315b9  jmp     short loc_1400315D6
0x1400315bb  mov     rdx, r14
0x1400315be  lea     rcx, [rbp+SourceString]
0x1400315c2  call    AslStringDuplicate
0x1400315c7  mov     r15, [rbp+SourceString]
0x1400315cb  test    eax, eax
0x1400315cd  js      loc_140031805
0x1400315d3  mov     rdx, r15; SourceString
0x1400315d6  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400315da  call    cs:__imp_RtlInitUnicodeString
0x1400315e0  xor     r9d, r9d; KeyValueInformation
0x1400315e3  lea     rax, [rbp+arg_8]
0x1400315e7  mov     [rsp+50h+ResultLength], rax; ResultLength
0x1400315ec  lea     rdx, [rbp+DestinationString]; ValueName
0x1400315f0  mov     rcx, r13; KeyHandle
0x1400315f3  mov     [rsp+50h+Length], ebx; Length
0x1400315f7  lea     r14d, [r9+1]
0x1400315fb  mov     r8d, r14d; KeyValueInformationClass
0x1400315fe  call    cs:__imp_ZwQueryValueKey
0x140031604  test    eax, eax
0x140031606  jns     short loc_14003161E
0x140031608  cmp     eax, 80000005h
0x14003160d  jz      short loc_14003161E
0x14003160f  cmp     eax, 0C0000023h
0x140031614  jz      short loc_14003161E
0x140031616  mov     ebx, r14d
0x140031619  jmp     loc_140031805
0x14003161e  mov     rcx, gs:60h
0x140031627  mov     edx, 8; Flags
0x14003162c  mov     r8d, [rbp+arg_8]; Size
0x140031630  mov     rcx, [rcx+30h]; HeapHandle
0x140031634  call    cs:__imp_RtlAllocateHeap
0x14003163a  mov     rdi, rax
0x14003163d  test    rax, rax
0x140031640  jnz     short loc_140031663
0x140031642  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x140031649  mov     r8d, 4E1h
0x14003164f  lea     rdx, aSdbpcheckmatch_7; "SdbpCheckMatchingRegistryValue"
0x140031656  mov     ecx, r14d
0x140031659  call    AslLogCallPrintf
0x14003165e  jmp     loc_140031805
0x140031663  lea     rax, [rbp+arg_8]
0x140031667  mov     r9, rdi; KeyValueInformation
0x14003166a  mov     [rsp+50h+ResultLength], rax; ResultLength
0x14003166f  lea     rdx, [rbp+DestinationString]; ValueName
0x140031673  mov     eax, [rbp+arg_8]
0x140031676  mov     r8d, r14d; KeyValueInformationClass
0x140031679  mov     rcx, r13; KeyHandle
0x14003167c  mov     [rsp+50h+Length], eax; Length
0x140031680  call    cs:__imp_ZwQueryValueKey
0x140031686  xor     r13d, r13d
0x140031689  test    eax, eax
0x14003168b  jns     short loc_1400316AE
0x14003168d  lea     r9, aFailedToReadVa_0; "Failed to read value"
0x140031694  mov     r8d, 4ECh
0x14003169a  mov     ecx, r14d
0x14003169d  lea     rdx, aSdbpcheckmatch_7; "SdbpCheckMatchingRegistryValue"
0x1400316a4  call    AslLogCallPrintf
0x1400316a9  jmp     loc_1400317D6
0x1400316ae  test    r12d, r12d
0x1400316b1  jnz     short loc_1400316C5
0x1400316b3  mov     rax, [rbp+arg_40]
0x1400316ba  mov     [rax], r14d
0x1400316bd  mov     ebx, r14d
0x1400316c0  jmp     loc_1400317D6
0x1400316c5  mov     ecx, [rdi+4]
0x1400316c8  cmp     ecx, r12d
0x1400316cb  jnz     short loc_1400316BD
0x1400316cd  mov     r14d, [rdi+8]
0x1400316d1  add     r14, rdi
0x1400316d4  sub     ecx, 1
0x1400316d7  jz      loc_14003185C
0x1400316dd  sub     ecx, 1
0x1400316e0  jz      loc_14003185C
0x1400316e6  sub     ecx, 1
0x1400316e9  jz      loc_140031839
0x1400316ef  sub     ecx, 1
0x1400316f2  jz      loc_1400317B3
0x1400316f8  sub     ecx, 3
0x1400316fb  jz      short loc_140031720
0x1400316fd  cmp     ecx, 4
0x140031700  jz      short loc_140031714
0x140031702  lea     r9, aUnknownRegistr; "Unknown registry value data type"
0x140031709  mov     r8d, 574h
0x14003170f  jmp     loc_140031891
0x140031714  mov     rax, [r14]
0x140031717  cmp     [rbp+arg_28], rax
0x14003171b  jmp     loc_1400317B9
0x140031720  mov     rcx, gs:60h
0x140031729  mov     edx, 8; Flags
0x14003172e  mov     r8d, [rdi+0Ch]
0x140031732  add     r8, 2; Size
0x140031736  mov     rcx, [rcx+30h]; HeapHandle
0x14003173a  call    cs:__imp_RtlAllocateHeap
0x140031740  mov     rsi, rax
0x140031743  test    rax, rax
0x140031746  jnz     short loc_140031753
0x140031748  mov     r8d, 529h
0x14003174e  jmp     loc_14003188A
0x140031753  mov     r8d, [rdi+0Ch]; Size
0x140031757  mov     rdx, r14; Src
0x14003175a  mov     rcx, rsi; void *
0x14003175d  call    memmove_0
0x140031762  mov     ecx, [rdi+0Ch]
0x140031765  shr     rcx, 1
0x140031768  mov     [rsi+rcx*2], r13w
0x14003176d  mov     rcx, rsi
0x140031770  mov     eax, [rdi+0Ch]
0x140031773  and     rax, 0FFFFFFFFFFFFFFFEh
0x140031777  add     rax, rsi
0x14003177a  cmp     rsi, rax
0x14003177d  jnb     loc_1400318B5
0x140031783  lea     rax, [rcx+2]
0x140031787  cmp     [rcx], r13w
0x14003178b  jnz     short loc_14003179C
0x14003178d  cmp     [rax], r13w
0x140031791  jz      loc_1400318B5
0x140031797  mov     word ptr [rcx], 3Bh ; ';'
0x14003179c  mov     rcx, rax
0x14003179f  mov     eax, [rdi+0Ch]
0x1400317a2  and     rax, 0FFFFFFFFFFFFFFFEh
0x1400317a6  add     rax, rsi
0x1400317a9  cmp     rcx, rax
0x1400317ac  jb      short loc_140031783
0x1400317ae  jmp     loc_1400318B5
0x1400317b3  mov     eax, [r14]
0x1400317b6  cmp     [rbp+arg_20], eax
0x1400317b9  jnz     loc_1400318C9
0x1400317bf  mov     rax, [rbp+arg_40]
0x1400317c6  mov     dword ptr [rax], 1
0x1400317cc  mov     ebx, 1
0x1400317d1  test    rdi, rdi
0x1400317d4  jz      short loc_1400317EB
0x1400317d6  mov     rcx, gs:60h
0x1400317df  mov     rdx, rdi
0x1400317e2  mov     rcx, [rcx+30h]
0x1400317e6  call    AslFree
0x1400317eb  test    rsi, rsi
0x1400317ee  jz      short loc_140031805
0x1400317f0  mov     rcx, gs:60h
0x1400317f9  mov     rdx, rsi
0x1400317fc  mov     rcx, [rcx+30h]
0x140031800  call    AslFree
0x140031805  test    r15, r15
0x140031808  jz      short loc_14003181F
0x14003180a  mov     rcx, gs:60h
0x140031813  mov     rdx, r15
0x140031816  mov     rcx, [rcx+30h]
0x14003181a  call    AslFree
0x14003181f  mov     eax, ebx
0x140031821  mov     rbx, [rsp+50h+arg_0]
0x140031829  add     rsp, 50h
0x14003182d  pop     r15
0x14003182f  pop     r14
0x140031831  pop     r13
0x140031833  pop     r12
0x140031835  pop     rdi
0x140031836  pop     rsi
0x140031837  pop     rbp
0x140031838  retn
0x140031839  mov     eax, [rdi+0Ch]
0x14003183c  mov     r8, [rbp+Size]; Size
0x140031840  cmp     r8, rax
0x140031843  jnz     loc_1400318C9
0x140031849  mov     rcx, [rbp+Buf1]; Buf1
0x14003184d  mov     rdx, r14; Buf2
0x140031850  call    memcmp_0
0x140031855  test    eax, eax
0x140031857  jmp     loc_1400317B9
0x14003185c  mov     rcx, gs:60h
0x140031865  mov     edx, 8; Flags
0x14003186a  mov     r8d, [rdi+0Ch]
0x14003186e  add     r8, 2; Size
0x140031872  mov     rcx, [rcx+30h]; HeapHandle
0x140031876  call    cs:__imp_RtlAllocateHeap
0x14003187c  mov     rsi, rax
0x14003187f  test    rax, rax
0x140031882  jnz     short loc_14003189B
0x140031884  mov     r8d, 511h
0x14003188a  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x140031891  mov     ecx, 1
0x140031896  jmp     loc_14003169D
0x14003189b  mov     r8d, [rdi+0Ch]; Size
0x14003189f  mov     rdx, r14; Src
0x1400318a2  mov     rcx, rsi; void *
0x1400318a5  call    memmove_0
0x1400318aa  mov     ecx, [rdi+0Ch]
0x1400318ad  shr     rcx, 1
0x1400318b0  mov     [rsi+rcx*2], r13w
0x1400318b5  mov     rcx, [rbp+arg_18]
0x1400318b9  mov     rdx, rsi
0x1400318bc  call    AslStringPatternMatchExW
0x1400318c1  test    eax, eax
0x1400318c3  jnz     loc_1400317BF
0x1400318c9  mov     ebx, 1
0x1400318ce  jmp     loc_1400317D6
```
