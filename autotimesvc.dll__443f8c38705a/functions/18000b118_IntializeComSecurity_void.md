# IntializeComSecurity(void)

- ea: `0x18000b118`
- end: `0x18000b233`
- name: `?IntializeComSecurity@@YAJXZ`
- size: `283`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b264`

## callees

- `0x180001010`
- `0x180001218`
- `0x1800012f0`
- `0x18000b118`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18000b150`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18000b150`

## pseudocode

```c
__int64 IntializeComSecurity(void)
{
  HRESULT v0; // ebx

  v0 = CoInitializeSecurity(0, -1, 0, 0, 6u, 3u, 0, 0, 0);
  if ( v0 >= 0 )
  {
    if ( (unsigned int)dword_18001C010 > 3 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          (__int64)&dword_18001C010,
          (__int64)word_18001689A,
          0,
          0);
    }
    return (unsigned int)v0;
  }
  if ( v0 != -2147417831 )
  {
    if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18001C010,
        (__int64)word_1800168CA,
        0,
        0);
    return (unsigned int)v0;
  }
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18001C010,
      (__int64)&byte_180016997,
      0,
      0);
  return 1;
}

```

## disassembly

```asm
0x18000b118  mov     rax, rsp
0x18000b11b  push    rbx
0x18000b11c  sub     rsp, 50h
0x18000b120  mov     qword ptr [rax-18h], 0
0x18000b128  xor     r9d, r9d; pReserved1
0x18000b12b  mov     dword ptr [rax-20h], 0
0x18000b132  xor     r8d, r8d; asAuthSvc
0x18000b135  mov     qword ptr [rax-28h], 0
0x18000b13d  or      edx, 0FFFFFFFFh; cAuthSvc
0x18000b140  mov     dword ptr [rax-30h], 3
0x18000b147  xor     ecx, ecx; pSecDesc
0x18000b149  mov     dword ptr [rax-38h], 6
0x18000b150  call    cs:__imp_CoInitializeSecurity
0x18000b156  mov     ebx, eax
0x18000b158  test    eax, eax
0x18000b15a  js      short loc_18000B1A2
0x18000b15c  mov     ecx, cs:dword_18001C010
0x18000b162  cmp     ecx, 3
0x18000b165  jbe     loc_18000B22B
0x18000b16b  mov     edx, 1
0x18000b170  lea     rcx, dword_18001C010
0x18000b177  call    _tlgKeywordOn
0x18000b17c  test    al, al
0x18000b17e  jz      loc_18000B22B
0x18000b184  xor     r9d, r9d
0x18000b187  lea     rdx, word_18001689A
0x18000b18e  xor     r8d, r8d
0x18000b191  lea     rcx, dword_18001C010
0x18000b198  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000b19d  jmp     loc_18000B22B
0x18000b1a2  mov     eax, cs:dword_18001C010
0x18000b1a8  cmp     ebx, 80010119h
0x18000b1ae  jnz     short loc_18000B1EA
0x18000b1b0  cmp     eax, 4
0x18000b1b3  jbe     short loc_18000B1E3
0x18000b1b5  mov     edx, 1
0x18000b1ba  lea     rcx, dword_18001C010
0x18000b1c1  call    _tlgKeywordOn
0x18000b1c6  test    al, al
0x18000b1c8  jz      short loc_18000B1E3
0x18000b1ca  xor     r9d, r9d
0x18000b1cd  lea     rdx, byte_180016997
0x18000b1d4  xor     r8d, r8d
0x18000b1d7  lea     rcx, dword_18001C010
0x18000b1de  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000b1e3  mov     eax, 1
0x18000b1e8  jmp     short loc_18000B22D
0x18000b1ea  cmp     eax, 4
0x18000b1ed  jbe     short loc_18000B22B
0x18000b1ef  mov     edx, 1
0x18000b1f4  lea     rcx, dword_18001C010
0x18000b1fb  call    _tlgKeywordOn
0x18000b200  test    al, al
0x18000b202  jz      short loc_18000B22B
0x18000b204  lea     rax, [rsp+58h+arg_0]
0x18000b209  mov     [rsp+58h+arg_0], ebx
0x18000b20d  xor     r9d, r9d
0x18000b210  mov     [rsp+58h+var_38], rax
0x18000b215  xor     r8d, r8d
0x18000b218  lea     rdx, word_1800168CA
0x18000b21f  lea     rcx, dword_18001C010
0x18000b226  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000b22b  mov     eax, ebx
0x18000b22d  add     rsp, 50h
0x18000b231  pop     rbx
0x18000b232  retn
```
