# _lambda_026b74bcb782224f7565c8bc6310a4ff_::operator()

- ea: `0x18005bc6c`
- end: `0x18005bd23`
- name: `_lambda_026b74bcb782224f7565c8bc6310a4ff_::operator()`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18005b81c`
- `0x180060c24`

## callees

- `0x180003908`
- `0x18000e9a4`
- `0x180020fa8`
- `0x18005bc6c`
- `0x18005c2a4`
- `0x18007dc20`

## import_xrefs

- `SAMSRV!SamIFree_UserInternal6Information` at `0x18005bc99`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18005bc99`
- `SAMSRV!SamrCloseHandle` at `0x18005bca9`
- `SAMSRV!SamrCloseHandle` at `0x18005bca9`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18005bcb3`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18005bcb3`

## pseudocode

```c
void __fastcall lambda_026b74bcb782224f7565c8bc6310a4ff_::operator()(__int64 a1)
{
  _QWORD *v2; // rcx
  __int64 v3; // rcx
  _BYTE v4[60]; // [rsp+20h] [rbp-59h] BYREF
  int v5; // [rsp+5Ch] [rbp-1Dh]
  int v6; // [rsp+71h] [rbp-8h]
  __int16 v7; // [rsp+75h] [rbp-4h]
  char v8; // [rsp+77h] [rbp-2h]
  __int16 v9; // [rsp+89h] [rbp+10h]
  char v10; // [rsp+8Bh] [rbp+12h]
  int v11; // [rsp+94h] [rbp+1Bh]
  __int128 v12; // [rsp+B8h] [rbp+3Fh] BYREF
  __int64 v13; // [rsp+C8h] [rbp+4Fh]

  KerbFreeString(*(_QWORD *)a1);
  KerbFreeString(*(_QWORD *)(a1 + 8));
  SamIFree_UserInternal6Information(**(_QWORD **)(a1 + 16));
  v2 = *(_QWORD **)(a1 + 24);
  if ( *v2 )
    SamrCloseHandle(v2);
  SamIFreeSidAndAttributesList(*(_QWORD *)(a1 + 32));
  FreeTicketInfo(*(struct _KDC_TICKET_INFO **)(a1 + 40));
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  memset_0(v4, 0, 0x98u);
  v3 = *(_QWORD *)(a1 + 40);
  v13 = 0;
  v12 = 0;
  _KDC_TICKET_INFO::operator=(v3, v4);
  std::vector<unsigned int>::_Tidy((__int64)&v12);
}

```

## disassembly

```asm
0x18005bc6c  mov     [rsp-8+arg_0], rbx
0x18005bc71  push    rbp
0x18005bc72  lea     rbp, [rsp-57h]
0x18005bc77  sub     rsp, 0D0h
0x18005bc7e  mov     rbx, rcx
0x18005bc81  mov     rcx, [rcx]
0x18005bc84  call    KerbFreeString
0x18005bc89  mov     rcx, [rbx+8]
0x18005bc8d  call    KerbFreeString
0x18005bc92  mov     rcx, [rbx+10h]
0x18005bc96  mov     rcx, [rcx]
0x18005bc99  call    cs:__imp_SamIFree_UserInternal6Information
0x18005bc9f  mov     rcx, [rbx+18h]
0x18005bca3  cmp     qword ptr [rcx], 0
0x18005bca7  jz      short loc_18005BCAF
0x18005bca9  call    cs:__imp_SamrCloseHandle
0x18005bcaf  mov     rcx, [rbx+20h]
0x18005bcb3  call    cs:__imp_SamIFreeSidAndAttributesList
0x18005bcb9  mov     rcx, [rbx+28h]; struct _KDC_TICKET_INFO *
0x18005bcbd  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x18005bcc2  xor     eax, eax
0x18005bcc4  lea     rcx, [rbp+57h+var_B0]; void *
0x18005bcc8  xor     edx, edx; Val
0x18005bcca  mov     [rbp+57h+var_74], eax
0x18005bccd  mov     r8d, 98h; Size
0x18005bcd3  mov     [rbp+57h+var_5F], eax
0x18005bcd6  mov     [rbp+57h+var_5B], ax
0x18005bcda  mov     [rbp+57h+var_59], al
0x18005bcdd  mov     [rbp+57h+var_47], ax
0x18005bce1  mov     [rbp+57h+var_45], al
0x18005bce4  mov     [rbp+57h+var_3C], eax
0x18005bce7  call    memset_0
0x18005bcec  mov     rcx, [rbx+28h]
0x18005bcf0  lea     rdx, [rbp+57h+var_B0]
0x18005bcf4  xorps   xmm0, xmm0
0x18005bcf7  mov     [rbp+57h+var_8], 0
0x18005bcff  movdqu  [rbp+57h+var_18], xmm0
0x18005bd04  call    ??4_KDC_TICKET_INFO@@QEAAAEAU0@$$QEAU0@@Z; _KDC_TICKET_INFO::operator=(_KDC_TICKET_INFO &&)
0x18005bd09  lea     rcx, [rbp+57h+var_18]
0x18005bd0d  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18005bd12  mov     rbx, [rsp+0D0h+arg_0]
0x18005bd1a  add     rsp, 0D0h
0x18005bd21  pop     rbp
0x18005bd22  retn
```
