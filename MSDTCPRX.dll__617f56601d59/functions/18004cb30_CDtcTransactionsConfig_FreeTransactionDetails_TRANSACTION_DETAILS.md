# CDtcTransactionsConfig::FreeTransactionDetails(_TRANSACTION_DETAILS *)

- ea: `0x18004cb30`
- end: `0x18004cbe8`
- name: `?FreeTransactionDetails@CDtcTransactionsConfig@@AEAAXPEAU_TRANSACTION_DETAILS@@@Z`
- size: `184`
- prototype: `void __fastcall(CDtcTransactionsConfig *__hidden this, struct _TRANSACTION_DETAILS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004cbf0`

## callees

- `0x18000d5f4`
- `0x18004cb30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cb69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cb85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cba8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cbc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cb69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cb85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cba8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cbc4`

## string_xrefs

- `0x18004cb47`: `CDtcTransactionsConfig::FreeTransactionDetails (com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp@646): pTransactionDetails shouldn't be NULL`

## pseudocode

```c
void __fastcall CDtcTransactionsConfig::FreeTransactionDetails(
        CDtcTransactionsConfig *this,
        struct _TRANSACTION_DETAILS *a2)
{
  __int64 i; // rsi
  __int64 j; // rsi

  if ( !a2 )
    DtcInternalErrorW(
      L"CDtcTransactionsConfig::FreeTransactionDetails (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp@646): pTran"
       "sactionDetails shouldn't be NULL");
  if ( *((_QWORD *)a2 + 1) )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)a2; i = (unsigned int)(i + 1) )
    {
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)a2 + 1) + 8 * i));
      *(_QWORD *)(*((_QWORD *)a2 + 1) + 8 * i) = 0;
    }
    CoTaskMemFree(*((LPVOID *)a2 + 1));
    *((_QWORD *)a2 + 1) = 0;
  }
  if ( *((_QWORD *)a2 + 2) )
  {
    for ( j = 0; (unsigned int)j < *(_DWORD *)a2; j = (unsigned int)(j + 1) )
    {
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)a2 + 2) + 8 * j));
      *(_QWORD *)(*((_QWORD *)a2 + 2) + 8 * j) = 0;
    }
    CoTaskMemFree(*((LPVOID *)a2 + 2));
    *((_QWORD *)a2 + 2) = 0;
  }
  *(_DWORD *)a2 = 0;
}

```

## disassembly

```asm
0x18004cb30  mov     [rsp+arg_0], rbx
0x18004cb35  mov     [rsp+arg_8], rsi
0x18004cb3a  push    rdi
0x18004cb3b  sub     rsp, 20h
0x18004cb3f  mov     rdi, rdx
0x18004cb42  test    rdx, rdx
0x18004cb45  jnz     short loc_18004CB54
0x18004cb47  lea     rcx, aCdtctransactio_0; "CDtcTransactionsConfig::FreeTransaction"...
0x18004cb4e  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18004cb54  cmp     qword ptr [rdx+8], 0
0x18004cb59  jz      short loc_18004CB93
0x18004cb5b  xor     esi, esi
0x18004cb5d  cmp     [rdx], esi
0x18004cb5f  jbe     short loc_18004CB81
0x18004cb61  mov     rcx, [rdi+8]
0x18004cb65  mov     rcx, [rcx+rsi*8]; pv
0x18004cb69  call    cs:__imp_CoTaskMemFree
0x18004cb6f  mov     rax, [rdi+8]
0x18004cb73  mov     qword ptr [rax+rsi*8], 0
0x18004cb7b  inc     esi
0x18004cb7d  cmp     esi, [rdi]
0x18004cb7f  jb      short loc_18004CB61
0x18004cb81  mov     rcx, [rdi+8]; pv
0x18004cb85  call    cs:__imp_CoTaskMemFree
0x18004cb8b  mov     qword ptr [rdi+8], 0
0x18004cb93  cmp     qword ptr [rdi+10h], 0
0x18004cb98  jz      short loc_18004CBD2
0x18004cb9a  xor     esi, esi
0x18004cb9c  cmp     [rdi], esi
0x18004cb9e  jbe     short loc_18004CBC0
0x18004cba0  mov     rcx, [rdi+10h]
0x18004cba4  mov     rcx, [rcx+rsi*8]; pv
0x18004cba8  call    cs:__imp_CoTaskMemFree
0x18004cbae  mov     rax, [rdi+10h]
0x18004cbb2  mov     qword ptr [rax+rsi*8], 0
0x18004cbba  inc     esi
0x18004cbbc  cmp     esi, [rdi]
0x18004cbbe  jb      short loc_18004CBA0
0x18004cbc0  mov     rcx, [rdi+10h]; pv
0x18004cbc4  call    cs:__imp_CoTaskMemFree
0x18004cbca  mov     qword ptr [rdi+10h], 0
0x18004cbd2  mov     rbx, [rsp+28h+arg_0]
0x18004cbd7  mov     rsi, [rsp+28h+arg_8]
0x18004cbdc  mov     dword ptr [rdi], 0
0x18004cbe2  add     rsp, 20h
0x18004cbe6  pop     rdi
0x18004cbe7  retn
```
