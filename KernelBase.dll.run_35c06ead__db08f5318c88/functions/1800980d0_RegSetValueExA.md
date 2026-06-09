# RegSetValueExA

- ea: `0x1800980d0`
- end: `0x1800982c6`
- name: `RegSetValueExA`
- size: `502`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCSTR lpValueName, DWORD Reserved, DWORD dwType, const BYTE *lpData, DWORD cbData)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180097a88`
- `0x180097b10`
- `0x180097ca0`
- `0x180116420`
- `0x18013ef50`

## callees

- `0x18005bb80`
- `0x18005d0a0`
- `0x180094aa0`
- `0x1800980d0`
- `0x18012d578`
- `0x180188eb9`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18009822b`
- `ntdll!RtlFreeUnicodeString` at `0x18009822b`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1801914ae`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1801914ae`
- `ntdll!RtlNtStatusToDosError` at `0x180098164`
- `ntdll!RtlNtStatusToDosError` at `0x1801914ba`
- `ntdll!RtlNtStatusToDosError` at `0x180098164`
- `ntdll!RtlNtStatusToDosError` at `0x1801914ba`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180098155`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180098155`
- `ntdll!RtlFreeHeap` at `0x18009829e`
- `ntdll!RtlFreeHeap` at `0x1800982bb`
- `ntdll!RtlFreeHeap` at `0x18009829e`
- `ntdll!RtlFreeHeap` at `0x1800982bb`
- `ntdll!RtlAllocateHeap` at `0x18019143d`
- `ntdll!RtlAllocateHeap` at `0x180191482`
- `ntdll!RtlAllocateHeap` at `0x18019143d`
- `ntdll!RtlAllocateHeap` at `0x180191482`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegSetValue` at `0x1801914f3`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegSetValue` at `0x1801914f3`

## pseudocode

```c
LSTATUS __stdcall RegSetValueExA(
        HKEY hKey,
        LPCSTR lpValueName,
        DWORD Reserved,
        DWORD dwType,
        const BYTE *lpData,
        DWORD cbData)
{
  ULONG v8; // edi
  struct _UNICODE_STRING *p_Destination; // rax
  BYTE *v11; // r12
  BYTE *v12; // r14
  WCHAR *v13; // r15
  ULONG BytesInMultiByteString; // esi
  BYTE *v15; // rax
  size_t v16; // rdi
  BYTE *Heap; // rax
  WCHAR *v18; // rax
  int v19; // eax
  char v20; // [rsp+30h] [rbp-98h] BYREF
  ULONG BytesInUnicodeString[3]; // [rsp+34h] [rbp-94h] BYREF
  PUNICODE_STRING ValueName; // [rsp+40h] [rbp-88h]
  BYTE *v23; // [rsp+48h] [rbp-80h]
  WCHAR *v24; // [rsp+50h] [rbp-78h]
  __int64 v25; // [rsp+58h] [rbp-70h] BYREF
  __int64 v26; // [rsp+60h] [rbp-68h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+68h] [rbp-60h] BYREF
  __int128 v28; // [rsp+78h] [rbp-50h] BYREF
  HANDLE KeyHandle; // [rsp+D0h] [rbp+8h] BYREF
  LPCSTR v30; // [rsp+D8h] [rbp+10h]
  ULONG Type; // [rsp+E8h] [rbp+20h]

  Type = dwType;
  v30 = lpValueName;
  KeyHandle = hKey;
  Destination = 0;
  v28 = 0;
  BytesInUnicodeString[0] = 0;
  v26 = 0;
  v25 = 0;
  v20 = 0;
  if ( hKey == HKEY_PERFORMANCE_DATA )
    return 6;
  if ( !Reserved )
  {
    v8 = MapPredefinedHandleInternal(hKey, &KeyHandle, &v26, &v25);
    if ( v8 )
    {
LABEL_7:
      CLOSE_LOCAL_HANDLE_INTERNAL(v26, v25);
      return v8;
    }
    if ( lpValueName )
    {
      if ( !RtlCreateUnicodeStringFromAsciiz(&Destination, lpValueName) )
      {
        v8 = RtlNtStatusToDosError(-1073741801);
        goto LABEL_7;
      }
      Destination.Length += 2;
      if ( !Destination.Length )
      {
        v8 = 87;
        goto LABEL_22;
      }
      p_Destination = &Destination;
    }
    else
    {
      p_Destination = (struct _UNICODE_STRING *)&v28;
      LODWORD(v28) = 0;
      *((_QWORD *)&v28 + 1) = 0;
    }
    ValueName = p_Destination;
    v11 = 0;
    v23 = 0;
    v12 = (BYTE *)lpData;
    if ( !lpData || dwType - 1 > 1 && dwType != 7 )
    {
      v13 = 0;
      v24 = 0;
      BytesInMultiByteString = cbData;
      goto LABEL_14;
    }
    BytesInMultiByteString = cbData;
    if ( cbData )
    {
      if ( lpData[cbData - 1] )
      {
        v16 = cbData;
        if ( (((unsigned __int64)&lpData[cbData] ^ (unsigned __int64)&lpData[cbData - 1]) & 0xFFFFFFFFFFFFF000uLL) == 0
          && !lpData[cbData] )
        {
          BytesInMultiByteString = cbData + 1;
          Heap = (BYTE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, cbData + 1);
          v11 = Heap;
          v23 = Heap;
          if ( !Heap )
          {
            v8 = 8;
LABEL_22:
            if ( lpValueName )
              RtlFreeUnicodeString(&Destination);
            goto LABEL_7;
          }
          memcpy_0(Heap, v12, v16);
          v11[v16] = 0;
          v12 = v11;
        }
      }
    }
    v18 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * BytesInMultiByteString);
    v13 = v18;
    v24 = v18;
    if ( !v18 )
    {
      v8 = 8;
LABEL_18:
      if ( v11 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
      if ( v13 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
      goto LABEL_22;
    }
    v19 = RtlMultiByteToUnicodeN(
            v18,
            2 * BytesInMultiByteString,
            BytesInUnicodeString,
            (const CHAR *)v12,
            BytesInMultiByteString);
    if ( v19 < 0 )
    {
      v8 = RtlNtStatusToDosError(v19);
LABEL_15:
      if ( !v8 )
      {
        if ( ((unsigned __int8)KeyHandle & 1) != 0 )
        {
          if ( (unsigned __int8)IsBaseRegCloseKeyPresent() )
          {
            if ( !v12 )
            {
              v15 = (BYTE *)&v20;
              if ( BytesInMultiByteString )
                v15 = 0;
              v12 = v15;
            }
            v8 = BaseRegSetValue(
                   (unsigned __int64)KeyHandle & 0xFFFFFFFFFFFFFFFEuLL,
                   ValueName,
                   Type,
                   v12,
                   BytesInMultiByteString);
            BytesInUnicodeString[2] = v8;
          }
        }
        else
        {
          v8 = BaseRegSetValueInternal(KeyHandle, ValueName, Type, v12, BytesInMultiByteString);
        }
      }
      goto LABEL_18;
    }
    v12 = (BYTE *)v13;
    BytesInMultiByteString = BytesInUnicodeString[0];
LABEL_14:
    v8 = 0;
    goto LABEL_15;
  }
  return 87;
}

```

## disassembly

```asm
0x1800980d0  mov     rax, rsp
0x1800980d3  mov     [rax+20h], r9d
0x1800980d7  mov     [rax+10h], rdx
0x1800980db  mov     [rax+8], rcx
0x1800980df  push    rbx
0x1800980e0  push    rsi
0x1800980e1  push    rdi
0x1800980e2  push    r12
0x1800980e4  push    r13
0x1800980e6  push    r14
0x1800980e8  push    r15
0x1800980ea  sub     rsp, 90h
0x1800980f1  mov     esi, r9d
0x1800980f4  mov     r13, rdx
0x1800980f7  xorps   xmm0, xmm0
0x1800980fa  movups  xmmword ptr [rax-60h], xmm0
0x1800980fe  xorps   xmm1, xmm1
0x180098101  movups  xmmword ptr [rax-50h], xmm1
0x180098105  xor     ebx, ebx
0x180098107  mov     [rsp+0C8h+BytesInUnicodeString], ebx
0x18009810b  mov     [rax-68h], rbx
0x18009810f  mov     [rax-70h], rbx
0x180098113  mov     [rsp+0C8h+var_98], bl
0x180098117  cmp     rcx, 0FFFFFFFF80000004h
0x18009811e  jz      loc_180098253
0x180098124  test    r8d, r8d
0x180098127  jnz     loc_18009825D
0x18009812d  lea     r9, [rax-70h]
0x180098131  lea     r8, [rax-68h]
0x180098135  lea     rdx, [rax+8]
0x180098139  call    MapPredefinedHandleInternal
0x18009813e  mov     edi, eax
0x180098140  test    eax, eax
0x180098142  jnz     short loc_18009816C
0x180098144  test    r13, r13
0x180098147  jz      loc_180098236
0x18009814d  mov     rdx, r13; Source
0x180098150  lea     rcx, [rsp+0C8h+Destination]; Destination
0x180098155  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18009815b  test    al, al
0x18009815d  jnz     short loc_180098190
0x18009815f  mov     ecx, 0C0000017h; Status
0x180098164  call    cs:__imp_RtlNtStatusToDosError
0x18009816a  mov     edi, eax
0x18009816c  mov     rdx, [rsp+0C8h+var_70]
0x180098171  mov     rcx, [rsp+0C8h+var_68]
0x180098176  call    CLOSE_LOCAL_HANDLE_INTERNAL
0x18009817b  mov     eax, edi
0x18009817d  add     rsp, 90h
0x180098184  pop     r15
0x180098186  pop     r14
0x180098188  pop     r13
0x18009818a  pop     r12
0x18009818c  pop     rdi
0x18009818d  pop     rsi
0x18009818e  pop     rbx
0x18009818f  retn
0x180098190  add     [rsp+0C8h+Destination.Length], 2
0x180098196  jz      loc_18009824C
0x18009819c  lea     rax, [rsp+0C8h+Destination]
0x1800981a1  mov     [rsp+0C8h+ValueName], rax
0x1800981a6  mov     r12, rbx
0x1800981a9  mov     [rsp+0C8h+var_80], rbx
0x1800981ae  mov     r14, [rsp+0C8h+lpData]
0x1800981b6  test    r14, r14
0x1800981b9  jz      short loc_1800981D0
0x1800981bb  lea     eax, [rsi-1]
0x1800981be  cmp     eax, 1
0x1800981c1  jbe     loc_1801913FC
0x1800981c7  cmp     esi, 7
0x1800981ca  jz      loc_1801913FC
0x1800981d0  mov     r15, rbx
0x1800981d3  mov     [rsp+0C8h+var_78], rbx
0x1800981d8  mov     esi, [rsp+0C8h+cbData]
0x1800981df  mov     edi, ebx
0x1800981e1  test    edi, edi
0x1800981e3  jnz     short loc_18009820F
0x1800981e5  mov     rax, [rsp+0C8h+KeyHandle]
0x1800981ed  test    al, 1
0x1800981ef  jnz     short loc_180098267
0x1800981f1  mov     [rsp+0C8h+BytesInMultiByteString], esi; ULONG
0x1800981f5  mov     r9, r14; Data
0x1800981f8  mov     r8d, [rsp+0C8h+Type]; Type
0x180098200  mov     rdx, [rsp+0C8h+ValueName]; ValueName
0x180098205  mov     rcx, rax; KeyHandle
0x180098208  call    BaseRegSetValueInternal
0x18009820d  mov     edi, eax
0x18009820f  test    r12, r12
0x180098212  jnz     short loc_18009828C
0x180098214  test    r15, r15
0x180098217  jnz     loc_1800982A9
0x18009821d  test    r13, r13
0x180098220  jz      loc_18009816C
0x180098226  lea     rcx, [rsp+0C8h+Destination]; UnicodeString
0x18009822b  call    cs:__imp_RtlFreeUnicodeString
0x180098231  jmp     loc_18009816C
0x180098236  lea     rax, [rsp+0C8h+var_50]
0x18009823b  mov     [rsp+0C8h+var_50], ebx
0x18009823f  mov     [rsp+0C8h+var_48], rbx
0x180098247  jmp     loc_1800981A1
0x18009824c  mov     edi, 57h ; 'W'
0x180098251  jmp     short loc_18009821D
0x180098253  mov     eax, 6
0x180098258  jmp     loc_18009817D
0x18009825d  mov     eax, 57h ; 'W'
0x180098262  jmp     loc_18009817D
0x180098267  call    IsBaseRegCloseKeyPresent
0x18009826c  test    al, al
0x18009826e  jz      short loc_18009820F
0x180098270  test    r14, r14
0x180098273  jnz     loc_1801914D3
0x180098279  lea     rax, [rsp+0C8h+var_98]
0x18009827e  test    esi, esi
0x180098280  cmovnz  rax, r14
0x180098284  mov     r14, rax
0x180098287  jmp     loc_1801914D3
0x18009828c  mov     rcx, gs:60h
0x180098295  mov     r8, r12; P
0x180098298  xor     edx, edx; Flags
0x18009829a  mov     rcx, [rcx+30h]; HeapHandle
0x18009829e  call    cs:__imp_RtlFreeHeap
0x1800982a4  jmp     loc_180098214
0x1800982a9  mov     rcx, gs:60h
0x1800982b2  mov     r8, r15; P
0x1800982b5  xor     edx, edx; Flags
0x1800982b7  mov     rcx, [rcx+30h]; HeapHandle
0x1800982bb  call    cs:__imp_RtlFreeHeap
0x1800982c1  jmp     loc_18009821D
0x1801913fc  mov     esi, [rsp+0C8h+cbData]
0x180191403  test    esi, esi
0x180191405  jz      short loc_18019146D
0x180191407  lea     eax, [rsi-1]
0x18019140a  cmp     [rax+r14], bl
0x18019140e  jz      short loc_18019146D
0x180191410  mov     edi, esi
0x180191412  lea     rcx, [rsi+r14]
0x180191416  lea     rax, [rcx-1]
0x18019141a  xor     rax, rcx
0x18019141d  test    rax, 0FFFFFFFFFFFFF000h
0x180191423  jnz     short loc_18019146D
0x180191425  cmp     [rcx], bl
0x180191427  jnz     short loc_18019146D
0x180191429  inc     esi
0x18019142b  mov     r8d, esi; Size
0x18019142e  mov     rcx, gs:60h
0x180191437  xor     edx, edx; Flags
0x180191439  mov     rcx, [rcx+30h]; HeapHandle
0x18019143d  call    cs:__imp_RtlAllocateHeap
0x180191443  mov     r12, rax
0x180191446  mov     [rsp+0C8h+var_80], rax
0x18019144b  test    rax, rax
0x18019144e  jnz     short loc_180191458
0x180191450  lea     edi, [rax+8]
0x180191453  jmp     loc_18009821D
0x180191458  mov     r8, rdi; Size
0x18019145b  mov     rdx, r14; Src
0x18019145e  mov     rcx, r12; void *
0x180191461  call    memcpy_0
0x180191466  mov     [rdi+r12], bl
0x18019146a  mov     r14, r12
0x18019146d  lea     edi, [rsi+rsi]
0x180191470  mov     r8d, edi; Size
0x180191473  mov     rcx, gs:60h
0x18019147c  xor     edx, edx; Flags
0x18019147e  mov     rcx, [rcx+30h]; HeapHandle
0x180191482  call    cs:__imp_RtlAllocateHeap
0x180191488  mov     r15, rax
0x18019148b  mov     [rsp+0C8h+var_78], rax
0x180191490  test    rax, rax
0x180191493  jnz     short loc_18019149D
0x180191495  lea     edi, [rax+8]
0x180191498  jmp     loc_18009820F
0x18019149d  mov     [rsp+0C8h+BytesInMultiByteString], esi; BytesInMultiByteString
0x1801914a1  mov     r9, r14; MultiByteString
0x1801914a4  lea     r8, [rsp+0C8h+BytesInUnicodeString]; BytesInUnicodeString
0x1801914a9  mov     edx, edi; MaxBytesInUnicodeString
0x1801914ab  mov     rcx, r15; UnicodeString
0x1801914ae  call    cs:__imp_RtlMultiByteToUnicodeN
0x1801914b4  test    eax, eax
0x1801914b6  jns     short loc_1801914C7
0x1801914b8  mov     ecx, eax; Status
0x1801914ba  call    cs:__imp_RtlNtStatusToDosError
0x1801914c0  mov     edi, eax
0x1801914c2  jmp     loc_1800981E1
0x1801914c7  mov     r14, r15
0x1801914ca  mov     esi, [rsp+0C8h+BytesInUnicodeString]
0x1801914ce  jmp     loc_1800981DF
0x1801914d3  mov     rcx, [rsp+0C8h+KeyHandle]
0x1801914db  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1801914df  mov     [rsp+0C8h+BytesInMultiByteString], esi
0x1801914e3  mov     r9, r14
0x1801914e6  mov     r8d, [rsp+0C8h+Type]
0x1801914ee  mov     rdx, [rsp+0C8h+ValueName]
0x1801914f3  call    cs:__imp_BaseRegSetValue
0x1801914f9  mov     edi, eax
0x1801914fb  mov     [rsp+0C8h+var_8C], eax
0x1801914ff  jmp     loc_18009820F
0x180191504  mov     edi, eax
0x180191506  mov     [rsp+0C8h+var_8C], eax
0x18019150a  mov     r13, [rsp+0C8h+arg_8]
0x180191512  mov     r12, [rsp+0C8h+var_80]
0x180191517  mov     r15, [rsp+0C8h+var_78]
0x18019151c  jmp     loc_18009820F
```
