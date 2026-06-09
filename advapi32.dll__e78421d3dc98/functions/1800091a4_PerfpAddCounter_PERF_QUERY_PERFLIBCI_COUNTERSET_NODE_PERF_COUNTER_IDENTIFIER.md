# PerfpAddCounter(_PERF_QUERY *,PERFLIBCI_COUNTERSET_NODE *,_PERF_COUNTER_IDENTIFIER *)

- ea: `0x1800091a4`
- end: `0x180009304`
- name: `?PerfpAddCounter@@YAKPEAU_PERF_QUERY@@PEAUPERFLIBCI_COUNTERSET_NODE@@PEAU_PERF_COUNTER_IDENTIFIER@@@Z`
- size: `352`
- prototype: `unsigned int __fastcall(struct _PERF_QUERY *, struct PERFLIBCI_COUNTERSET_NODE *, struct _PERF_COUNTER_IDENTIFIER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c0d4`

## callees

- `0x180009034`
- `0x1800091a4`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180009211`
- `ntdll!RtlInitUnicodeStringEx` at `0x180009211`
- `ntdll!RtlNtStatusToDosError` at `0x1800092b5`
- `ntdll!RtlNtStatusToDosError` at `0x1800092b5`
- `ntdll!RtlInitUnicodeString` at `0x1800092c9`
- `ntdll!RtlInitUnicodeString` at `0x1800092c9`
- `KERNEL32!CompareStringOrdinal` at `0x1800092f4`
- `KERNEL32!CompareStringOrdinal` at `0x1800092f4`
- `api-ms-win-core-pcw-l1-1-0!PcwCreateQuery` at `0x1800092a5`
- `api-ms-win-core-pcw-l1-1-0!PcwCreateQuery` at `0x1800092a5`
- `api-ms-win-core-pcw-l1-1-0!PcwAddQueryItem` at `0x180009254`
- `api-ms-win-core-pcw-l1-1-0!PcwAddQueryItem` at `0x180009254`

## pseudocode

```c
ULONG __fastcall PerfpAddCounter(
        struct _PERF_QUERY *a1,
        struct PERFLIBCI_COUNTERSET_NODE *a2,
        struct _PERF_COUNTER_IDENTIFIER *a3)
{
  _QWORD *v3; // r14
  bool v4; // zf
  ULONG CounterId; // ecx
  __int64 v8; // rbx
  int Query; // eax
  unsigned __int8 v10; // al
  __int64 v11; // r8
  unsigned int v13; // r8d
  unsigned int i; // edx
  __int64 v15; // rax
  int v16; // [rsp+28h] [rbp-60h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF

  v3 = (_QWORD *)((char *)a1 + 72);
  v4 = *((_QWORD *)a1 + 9) == 0;
  DestinationString = 0;
  if ( v4 )
  {
    Query = PcwCreateQuery((char *)a1 + 72, 0);
    if ( Query < 0 )
      return RtlNtStatusToDosError(Query);
  }
  CounterId = a3->CounterId;
  if ( CounterId == -1 )
  {
    v13 = *((_DWORD *)a2 + 32);
    v8 = 0;
    if ( v13 )
    {
      for ( i = 0; i < v13; ++i )
      {
        v15 = i;
        v8 |= 1LL << *(_DWORD *)(56 * v15 + *((_QWORD *)a2 + 15));
      }
    }
LABEL_5:
    if ( a3->Size == 40 || *((_DWORD *)a2 + 22) == 6 && CompareStringOrdinal((LPCWCH)&a3[1], -1, L"_Total", -1, 1) == 2 )
    {
      RtlInitUnicodeString(&DestinationString, L"*");
    }
    else
    {
      Query = RtlInitUnicodeStringEx(&DestinationString, (PCWSTR)&a3[1]);
      if ( Query < 0 )
        return RtlNtStatusToDosError(Query);
    }
    v10 = PerflibciWildcardInstance(DestinationString.Buffer);
    v16 = v11;
    LOBYTE(v11) = v10;
    Query = ((__int64 (__fastcall *)(ULONG *, _QWORD, __int64, char *, struct _UNICODE_STRING *, int, __int64, __int64))PcwAddQueryItem)(
              &a3->Reserved,
              *v3,
              v11,
              (char *)a2 + 104,
              &DestinationString,
              v16,
              v8,
              0xFFFFFFFFLL);
    if ( Query >= 0 )
      return 0;
    return RtlNtStatusToDosError(Query);
  }
  if ( CounterId < 0x40 )
  {
    v8 = 1LL << CounterId;
    goto LABEL_5;
  }
  return 87;
}

```

## disassembly

```asm
0x1800091a4  push    rbx
0x1800091a6  push    rbp
0x1800091a7  push    rsi
0x1800091a8  push    rdi
0x1800091a9  push    r14
0x1800091ab  push    r15
0x1800091ad  sub     rsp, 58h
0x1800091b1  lea     r14, [rcx+48h]
0x1800091b5  xorps   xmm0, xmm0
0x1800091b8  cmp     qword ptr [r14], 0
0x1800091bc  mov     rdi, r8
0x1800091bf  mov     rsi, rdx
0x1800091c2  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x1800091c7  jz      loc_1800092A0
0x1800091cd  mov     ecx, [rdi+18h]
0x1800091d0  mov     r15d, 0FFFFFFFFh
0x1800091d6  mov     r10d, 1
0x1800091dc  cmp     ecx, r15d
0x1800091df  jz      loc_18000926D
0x1800091e5  cmp     ecx, 40h ; '@'
0x1800091e8  jnb     loc_1800092D7
0x1800091ee  mov     ebx, r10d
0x1800091f1  shl     rbx, cl
0x1800091f4  cmp     dword ptr [rdi+14h], 28h ; '('
0x1800091f8  jz      loc_1800092BD
0x1800091fe  cmp     dword ptr [rsi+58h], 6
0x180009202  jz      loc_1800092DE
0x180009208  lea     rdx, [rdi+28h]; SourceString
0x18000920c  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x180009211  call    cs:__imp_RtlInitUnicodeStringEx
0x180009217  test    eax, eax
0x180009219  js      loc_1800092B3
0x18000921f  mov     r8d, [rdi+1Ch]
0x180009223  mov     rcx, [rsp+88h+DestinationString.Buffer]; unsigned __int16 *
0x180009228  call    ?PerflibciWildcardInstance@@YAEPEBG@Z; PerflibciWildcardInstance(ushort const *)
0x18000922d  mov     [rsp+88h+var_50], r15
0x180009232  lea     rdx, [rsp+88h+DestinationString]
0x180009237  mov     [rsp+88h+var_58], rbx
0x18000923c  lea     r9, [rsi+68h]
0x180009240  mov     [rsp+88h+var_60], r8d
0x180009245  lea     rcx, [rdi+24h]
0x180009249  mov     qword ptr [rsp+88h+bIgnoreCase], rdx
0x18000924e  mov     r8b, al
0x180009251  mov     rdx, [r14]
0x180009254  call    cs:__imp_PcwAddQueryItem
0x18000925a  test    eax, eax
0x18000925c  js      short loc_1800092B3
0x18000925e  xor     eax, eax
0x180009260  add     rsp, 58h
0x180009264  pop     r15
0x180009266  pop     r14
0x180009268  pop     rdi
0x180009269  pop     rsi
0x18000926a  pop     rbp
0x18000926b  pop     rbx
0x18000926c  retn
0x18000926d  mov     r8d, [rsi+80h]
0x180009274  xor     ebx, ebx
0x180009276  test    r8d, r8d
0x180009279  jz      loc_1800091F4
0x18000927f  mov     r9, [rsi+78h]
0x180009283  xor     edx, edx
0x180009285  mov     eax, edx
0x180009287  add     edx, r10d
0x18000928a  imul    rcx, rax, 38h ; '8'
0x18000928e  mov     eax, [rcx+r9]
0x180009292  bts     rbx, rax
0x180009296  cmp     edx, r8d
0x180009299  jb      short loc_180009285
0x18000929b  jmp     loc_1800091F4
0x1800092a0  xor     edx, edx
0x1800092a2  mov     rcx, r14
0x1800092a5  call    cs:__imp_PcwCreateQuery
0x1800092ab  test    eax, eax
0x1800092ad  jns     loc_1800091CD
0x1800092b3  mov     ecx, eax; Status
0x1800092b5  call    cs:__imp_RtlNtStatusToDosError
0x1800092bb  jmp     short loc_180009260
0x1800092bd  lea     rdx, asc_18007AE24; "*"
0x1800092c4  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x1800092c9  call    cs:__imp_RtlInitUnicodeString
0x1800092cf  mov     r8d, r15d
0x1800092d2  jmp     loc_180009223
0x1800092d7  mov     eax, 57h ; 'W'
0x1800092dc  jmp     short loc_180009260
0x1800092de  or      edx, 0FFFFFFFFh; cchCount1
0x1800092e1  mov     [rsp+88h+bIgnoreCase], r10d; bIgnoreCase
0x1800092e6  mov     r9d, edx; cchCount2
0x1800092e9  lea     r8, String2; "_Total"
0x1800092f0  lea     rcx, [rdi+28h]; lpString1
0x1800092f4  call    cs:__imp_CompareStringOrdinal
0x1800092fa  cmp     eax, 2
0x1800092fd  jz      short loc_1800092BD
0x1800092ff  jmp     loc_180009208
```
