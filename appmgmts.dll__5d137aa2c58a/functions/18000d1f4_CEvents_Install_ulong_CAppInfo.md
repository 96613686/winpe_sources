# CEvents::Install(ulong,CAppInfo *)

- ea: `0x18000d1f4`
- end: `0x18000d2d0`
- name: `?Install@CEvents@@QEAAXKPEAVCAppInfo@@@Z`
- size: `220`
- prototype: `void __fastcall(CEvents *this, unsigned int, struct CAppInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180003370`
- `0x180007110`

## callees

- `0x1800016d0`
- `0x180008e8c`
- `0x180008f58`
- `0x18000d1f4`
- `0x18001b4e0`

## pseudocode

```c
void __fastcall CEvents::Install(CEvents *this, unsigned int a2, struct CAppInfo *a3)
{
  __int64 v3; // rbp
  __int64 v5; // r14
  unsigned __int16 v8[12]; // [rsp+40h] [rbp-48h] BYREF

  v3 = *((_QWORD *)a3 + 9);
  v5 = *((_QWORD *)a3 + 5);
  if ( a2 )
  {
    StringCchPrintfW(v8, 0xCu, L"%u", a2);
    CEventsBase::Report(this, 0x66u, a2 == 1274, 3u, v5, v3, v8);
  }
  else
  {
    CEventsBase::Report(this, 0x12Eu, 0, 2u, v5, *((_QWORD *)a3 + 9));
  }
  if ( *(_DWORD *)(*((_QWORD *)a3 + 2) + 396LL) == 2 )
    CAppInfo::SetRsopFailureStatus(a3, a2, 0x66u);
}

```

## disassembly

```asm
0x18000d1f4  mov     [rsp+arg_18], rbx
0x18000d1f9  push    rbp
0x18000d1fa  push    rsi
0x18000d1fb  push    rdi
0x18000d1fc  push    r14
0x18000d1fe  push    r15
0x18000d200  sub     rsp, 60h
0x18000d204  mov     rax, cs:__security_cookie
0x18000d20b  xor     rax, rsp
0x18000d20e  mov     [rsp+88h+var_30], rax
0x18000d213  mov     rbp, [r8+48h]
0x18000d217  mov     rbx, r8
0x18000d21a  mov     r14, [r8+28h]
0x18000d21e  mov     edi, edx
0x18000d220  mov     rsi, rcx
0x18000d223  mov     r15d, 2
0x18000d229  test    edx, edx
0x18000d22b  jz      short loc_18000D278
0x18000d22d  mov     r9d, edx
0x18000d230  lea     r8, aU; "%u"
0x18000d237  lea     edx, [r15+0Ah]; unsigned __int64
0x18000d23b  lea     rcx, [rsp+88h+var_48]; unsigned __int16 *
0x18000d240  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d245  xor     r8d, r8d
0x18000d248  lea     rax, [rsp+88h+var_48]
0x18000d24d  mov     [rsp+88h+var_58], rax
0x18000d252  lea     r9d, [r15+1]; unsigned __int16
0x18000d256  cmp     edi, 4FAh
0x18000d25c  mov     [rsp+88h+var_60], rbp
0x18000d261  lea     edx, [r15+64h]; unsigned int
0x18000d265  mov     [rsp+88h+var_68], r14
0x18000d26a  setz    r8b; int
0x18000d26e  mov     rcx, rsi; this
0x18000d271  call    ?Report@CEventsBase@@QEAAXKHGZZ; CEventsBase::Report(ulong,int,ushort,...)
0x18000d276  jmp     short loc_18000D292
0x18000d278  mov     [rsp+88h+var_60], rbp
0x18000d27d  mov     r9d, r15d; unsigned __int16
0x18000d280  xor     r8d, r8d; int
0x18000d283  mov     [rsp+88h+var_68], r14
0x18000d288  mov     edx, 12Eh; unsigned int
0x18000d28d  call    ?Report@CEventsBase@@QEAAXKHGZZ; CEventsBase::Report(ulong,int,ushort,...)
0x18000d292  mov     rax, [rbx+10h]
0x18000d296  cmp     [rax+18Ch], r15d
0x18000d29d  jnz     short loc_18000D2AF
0x18000d29f  mov     r8d, 66h ; 'f'; unsigned int
0x18000d2a5  mov     edx, edi; unsigned int
0x18000d2a7  mov     rcx, rbx; this
0x18000d2aa  call    ?SetRsopFailureStatus@CAppInfo@@QEAAXKK@Z; CAppInfo::SetRsopFailureStatus(ulong,ulong)
0x18000d2af  mov     rcx, [rsp+88h+var_30]
0x18000d2b4  xor     rcx, rsp; StackCookie
0x18000d2b7  call    __security_check_cookie
0x18000d2bc  mov     rbx, [rsp+88h+arg_18]
0x18000d2c4  add     rsp, 60h
0x18000d2c8  pop     r15
0x18000d2ca  pop     r14
0x18000d2cc  pop     rdi
0x18000d2cd  pop     rsi
0x18000d2ce  pop     rbp
0x18000d2cf  retn
```
