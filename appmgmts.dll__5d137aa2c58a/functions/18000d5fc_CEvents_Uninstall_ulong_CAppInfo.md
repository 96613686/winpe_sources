# CEvents::Uninstall(ulong,CAppInfo *)

- ea: `0x18000d5fc`
- end: `0x18000d6d8`
- name: `?Uninstall@CEvents@@QEAAXKPEAVCAppInfo@@@Z`
- size: `220`
- prototype: `void __fastcall(void **this, unsigned int, struct CAppInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000239c`
- `0x1800079b0`
- `0x1800093ac`

## callees

- `0x1800016d0`
- `0x180008e8c`
- `0x180008f58`
- `0x18000d5fc`
- `0x18001b4e0`

## pseudocode

```c
void __fastcall CEvents::Uninstall(void **this, unsigned int a2, struct CAppInfo *a3)
{
  __int64 v3; // rbp
  __int64 v5; // r14
  unsigned __int16 v8[12]; // [rsp+40h] [rbp-48h] BYREF

  v3 = *((_QWORD *)a3 + 9);
  v5 = *((_QWORD *)a3 + 5);
  if ( a2 )
  {
    StringCchPrintfW(v8, 0xCu, L"%u", a2);
    CEventsBase::Report(this, 0x68u, a2 == 1274, 3u, v5, v3, v8);
  }
  else
  {
    CEventsBase::Report(this, 0x130u, 0, 2u, v5, *((_QWORD *)a3 + 9));
  }
  if ( *(_DWORD *)(*((_QWORD *)a3 + 2) + 396LL) == 2 )
    CAppInfo::SetRsopFailureStatus(a3, a2, 104);
}

```

## disassembly

```asm
0x18000d5fc  mov     [rsp+arg_18], rbx
0x18000d601  push    rbp
0x18000d602  push    rsi
0x18000d603  push    rdi
0x18000d604  push    r14
0x18000d606  push    r15
0x18000d608  sub     rsp, 60h
0x18000d60c  mov     rax, cs:__security_cookie
0x18000d613  xor     rax, rsp
0x18000d616  mov     [rsp+88h+var_30], rax
0x18000d61b  mov     rbp, [r8+48h]
0x18000d61f  mov     rbx, r8
0x18000d622  mov     r14, [r8+28h]
0x18000d626  mov     edi, edx
0x18000d628  mov     rsi, rcx
0x18000d62b  mov     r15d, 2
0x18000d631  test    edx, edx
0x18000d633  jz      short loc_18000D680
0x18000d635  mov     r9d, edx
0x18000d638  lea     r8, aU; "%u"
0x18000d63f  lea     edx, [r15+0Ah]; unsigned __int64
0x18000d643  lea     rcx, [rsp+88h+var_48]; unsigned __int16 *
0x18000d648  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d64d  xor     r8d, r8d
0x18000d650  lea     rax, [rsp+88h+var_48]
0x18000d655  mov     [rsp+88h+var_58], rax
0x18000d65a  lea     r9d, [r15+1]; unsigned __int16
0x18000d65e  cmp     edi, 4FAh
0x18000d664  mov     [rsp+88h+var_60], rbp
0x18000d669  lea     edx, [r15+66h]; unsigned int
0x18000d66d  mov     [rsp+88h+var_68], r14
0x18000d672  setz    r8b; int
0x18000d676  mov     rcx, rsi; this
0x18000d679  call    ?Report@CEventsBase@@QEAAXKHGZZ; CEventsBase::Report(ulong,int,ushort,...)
0x18000d67e  jmp     short loc_18000D69A
0x18000d680  mov     [rsp+88h+var_60], rbp
0x18000d685  mov     r9d, r15d; unsigned __int16
0x18000d688  xor     r8d, r8d; int
0x18000d68b  mov     [rsp+88h+var_68], r14
0x18000d690  mov     edx, 130h; unsigned int
0x18000d695  call    ?Report@CEventsBase@@QEAAXKHGZZ; CEventsBase::Report(ulong,int,ushort,...)
0x18000d69a  mov     rax, [rbx+10h]
0x18000d69e  cmp     [rax+18Ch], r15d
0x18000d6a5  jnz     short loc_18000D6B7
0x18000d6a7  mov     r8d, 68h ; 'h'; unsigned int
0x18000d6ad  mov     edx, edi; unsigned int
0x18000d6af  mov     rcx, rbx; this
0x18000d6b2  call    ?SetRsopFailureStatus@CAppInfo@@QEAAXKK@Z; CAppInfo::SetRsopFailureStatus(ulong,ulong)
0x18000d6b7  mov     rcx, [rsp+88h+var_30]
0x18000d6bc  xor     rcx, rsp; StackCookie
0x18000d6bf  call    __security_check_cookie
0x18000d6c4  mov     rbx, [rsp+88h+arg_18]
0x18000d6cc  add     rsp, 60h
0x18000d6d0  pop     r15
0x18000d6d2  pop     r14
0x18000d6d4  pop     rdi
0x18000d6d5  pop     rsi
0x18000d6d6  pop     rbp
0x18000d6d7  retn
```
