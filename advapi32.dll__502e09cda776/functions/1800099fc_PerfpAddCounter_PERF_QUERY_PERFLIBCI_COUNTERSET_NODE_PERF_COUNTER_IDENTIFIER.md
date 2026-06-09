# PerfpAddCounter(_PERF_QUERY *,PERFLIBCI_COUNTERSET_NODE *,_PERF_COUNTER_IDENTIFIER *)

- ea: `0x1800099fc`
- end: `0x180009b84`
- name: `?PerfpAddCounter@@YAKPEAU_PERF_QUERY@@PEAUPERFLIBCI_COUNTERSET_NODE@@PEAU_PERF_COUNTER_IDENTIFIER@@@Z`
- size: `392`
- prototype: `unsigned int __fastcall(struct _PERF_QUERY *, struct PERFLIBCI_COUNTERSET_NODE *, struct _PERF_COUNTER_IDENTIFIER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002ef8`

## callees

- `0x180009884`
- `0x1800099fc`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180009a69`
- `ntdll!RtlInitUnicodeStringEx` at `0x180009a69`
- `ntdll!RtlNtStatusToDosError` at `0x180009b20`
- `ntdll!RtlNtStatusToDosError` at `0x180009b20`
- `ntdll!RtlInitUnicodeString` at `0x180009b3a`
- `ntdll!RtlInitUnicodeString` at `0x180009b3a`
- `KERNEL32!CompareStringOrdinal` at `0x180009b6e`
- `KERNEL32!CompareStringOrdinal` at `0x180009b6e`
- `api-ms-win-core-pcw-l1-1-0!PcwCreateQuery` at `0x180009b0a`
- `api-ms-win-core-pcw-l1-1-0!PcwCreateQuery` at `0x180009b0a`
- `api-ms-win-core-pcw-l1-1-0!PcwAddQueryItem` at `0x180009ab2`
- `api-ms-win-core-pcw-l1-1-0!PcwAddQueryItem` at `0x180009ab2`

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
0x1800099fc  push    rbx
0x1800099fe  push    rbp
0x1800099ff  push    rsi
0x180009a00  push    rdi
0x180009a01  push    r14
0x180009a03  push    r15
0x180009a05  sub     rsp, 58h
0x180009a09  lea     r14, [rcx+48h]
0x180009a0d  xorps   xmm0, xmm0
0x180009a10  cmp     qword ptr [r14], 0
0x180009a14  mov     rdi, r8
0x180009a17  mov     rsi, rdx
0x180009a1a  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x180009a1f  jz      loc_180009B05
0x180009a25  mov     ecx, [rdi+18h]
0x180009a28  mov     r15d, 0FFFFFFFFh
0x180009a2e  mov     r10d, 1
0x180009a34  cmp     ecx, r15d
0x180009a37  jz      loc_180009AD2
0x180009a3d  cmp     ecx, 40h ; '@'
0x180009a40  jnb     loc_180009B4E
0x180009a46  mov     ebx, r10d
0x180009a49  shl     rbx, cl
0x180009a4c  cmp     dword ptr [rdi+14h], 28h ; '('
0x180009a50  jz      loc_180009B2E
0x180009a56  cmp     dword ptr [rsi+58h], 6
0x180009a5a  jz      loc_180009B58
0x180009a60  lea     rdx, [rdi+28h]; SourceString
0x180009a64  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x180009a69  call    cs:__imp_RtlInitUnicodeStringEx
0x180009a70  nop     dword ptr [rax+rax+00h]
0x180009a75  test    eax, eax
0x180009a77  js      loc_180009B1E
0x180009a7d  mov     r8d, [rdi+1Ch]
0x180009a81  mov     rcx, [rsp+88h+DestinationString.Buffer]; unsigned __int16 *
0x180009a86  call    ?PerflibciWildcardInstance@@YAEPEBG@Z; PerflibciWildcardInstance(ushort const *)
0x180009a8b  mov     [rsp+88h+var_50], r15
0x180009a90  lea     rdx, [rsp+88h+DestinationString]
0x180009a95  mov     [rsp+88h+var_58], rbx
0x180009a9a  lea     r9, [rsi+68h]
0x180009a9e  mov     [rsp+88h+var_60], r8d
0x180009aa3  lea     rcx, [rdi+24h]
0x180009aa7  mov     qword ptr [rsp+88h+bIgnoreCase], rdx
0x180009aac  mov     r8b, al
0x180009aaf  mov     rdx, [r14]
0x180009ab2  call    cs:__imp_PcwAddQueryItem
0x180009ab9  nop     dword ptr [rax+rax+00h]
0x180009abe  test    eax, eax
0x180009ac0  js      short loc_180009B1E
0x180009ac2  xor     eax, eax
0x180009ac4  add     rsp, 58h
0x180009ac8  pop     r15
0x180009aca  pop     r14
0x180009acc  pop     rdi
0x180009acd  pop     rsi
0x180009ace  pop     rbp
0x180009acf  pop     rbx
0x180009ad0  retn
0x180009ad2  mov     r8d, [rsi+80h]
0x180009ad9  xor     ebx, ebx
0x180009adb  test    r8d, r8d
0x180009ade  jz      loc_180009A4C
0x180009ae4  mov     r9, [rsi+78h]
0x180009ae8  xor     edx, edx
0x180009aea  mov     eax, edx
0x180009aec  add     edx, r10d
0x180009aef  imul    rcx, rax, 38h ; '8'
0x180009af3  mov     eax, [rcx+r9]
0x180009af7  bts     rbx, rax
0x180009afb  cmp     edx, r8d
0x180009afe  jb      short loc_180009AEA
0x180009b00  jmp     loc_180009A4C
0x180009b05  xor     edx, edx
0x180009b07  mov     rcx, r14
0x180009b0a  call    cs:__imp_PcwCreateQuery
0x180009b11  nop     dword ptr [rax+rax+00h]
0x180009b16  test    eax, eax
0x180009b18  jns     loc_180009A25
0x180009b1e  mov     ecx, eax; Status
0x180009b20  call    cs:__imp_RtlNtStatusToDosError
0x180009b27  nop     dword ptr [rax+rax+00h]
0x180009b2c  jmp     short loc_180009AC4
0x180009b2e  lea     rdx, asc_1800884A8; "*"
0x180009b35  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x180009b3a  call    cs:__imp_RtlInitUnicodeString
0x180009b41  nop     dword ptr [rax+rax+00h]
0x180009b46  mov     r8d, r15d
0x180009b49  jmp     loc_180009A81
0x180009b4e  mov     eax, 57h ; 'W'
0x180009b53  jmp     loc_180009AC4
0x180009b58  or      edx, 0FFFFFFFFh; cchCount1
0x180009b5b  mov     [rsp+88h+bIgnoreCase], r10d; bIgnoreCase
0x180009b60  mov     r9d, edx; cchCount2
0x180009b63  lea     r8, String2; "_Total"
0x180009b6a  lea     rcx, [rdi+28h]; lpString1
0x180009b6e  call    cs:__imp_CompareStringOrdinal
0x180009b75  nop     dword ptr [rax+rax+00h]
0x180009b7a  cmp     eax, 2
0x180009b7d  jz      short loc_180009B2E
0x180009b7f  jmp     loc_180009A60
```
