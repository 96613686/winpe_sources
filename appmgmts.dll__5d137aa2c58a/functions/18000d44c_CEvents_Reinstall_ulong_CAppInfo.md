# CEvents::Reinstall(ulong,CAppInfo *)

- ea: `0x18000d44c`
- end: `0x18000d51e`
- name: `?Reinstall@CEvents@@QEAAXKPEAVCAppInfo@@@Z`
- size: `210`
- prototype: `void __fastcall(CEvents *this, unsigned int, struct CAppInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180007410`
- `0x180007b58`

## callees

- `0x1800016d0`
- `0x180008e8c`
- `0x180008f58`
- `0x18000d44c`
- `0x18001b4e0`

## pseudocode

```c
void __fastcall CEvents::Reinstall(CEvents *this, unsigned int a2, struct CAppInfo *a3)
{
  unsigned __int16 v6[12]; // [rsp+40h] [rbp-38h] BYREF

  if ( a2 )
  {
    StringCchPrintfW(v6, 0xCu, L"%u", a2);
    CEventsBase::Report(this, 0x69u, a2 == 1274, 3u, *((_QWORD *)a3 + 5), *((_QWORD *)a3 + 9), v6);
    if ( *(_DWORD *)(*((_QWORD *)a3 + 2) + 396LL) == 2 )
      CAppInfo::SetRsopFailureStatus(a3, a2, 0x69u);
  }
  else
  {
    CEventsBase::Report(this, 0x131u, 0, 2u, *((_QWORD *)a3 + 5), *((_QWORD *)a3 + 9));
  }
}

```

## disassembly

```asm
0x18000d44c  push    rbx
0x18000d44e  push    rsi
0x18000d44f  push    rdi
0x18000d450  sub     rsp, 60h
0x18000d454  mov     rax, cs:__security_cookie
0x18000d45b  xor     rax, rsp
0x18000d45e  mov     [rsp+78h+var_20], rax
0x18000d463  mov     rbx, r8
0x18000d466  mov     edi, edx
0x18000d468  mov     rsi, rcx
0x18000d46b  test    edx, edx
0x18000d46d  jz      short loc_18000D4E4
0x18000d46f  mov     r9d, edx
0x18000d472  lea     r8, aU; "%u"
0x18000d479  mov     edx, 0Ch; unsigned __int64
0x18000d47e  lea     rcx, [rsp+78h+var_38]; unsigned __int16 *
0x18000d483  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d488  xor     r8d, r8d
0x18000d48b  lea     rax, [rsp+78h+var_38]
0x18000d490  mov     [rsp+78h+var_48], rax
0x18000d495  mov     r9d, 3; unsigned __int16
0x18000d49b  mov     rax, [rbx+48h]
0x18000d49f  cmp     edi, 4FAh
0x18000d4a5  mov     [rsp+78h+var_50], rax
0x18000d4aa  mov     rcx, rsi; this
0x18000d4ad  mov     rax, [rbx+28h]
0x18000d4b1  setz    r8b; int
0x18000d4b5  lea     edx, [r9+66h]; unsigned int
0x18000d4b9  mov     [rsp+78h+var_58], rax
0x18000d4be  call    ?Report@CEventsBase@@QEAAXKHGZZ; CEventsBase::Report(ulong,int,ushort,...)
0x18000d4c3  mov     rax, [rbx+10h]
0x18000d4c7  mov     ecx, 2
0x18000d4cc  cmp     [rax+18Ch], ecx
0x18000d4d2  jnz     short loc_18000D509
0x18000d4d4  lea     r8d, [rcx+67h]; unsigned int
0x18000d4d8  mov     edx, edi; unsigned int
0x18000d4da  mov     rcx, rbx; this
0x18000d4dd  call    ?SetRsopFailureStatus@CAppInfo@@QEAAXKK@Z; CAppInfo::SetRsopFailureStatus(ulong,ulong)
0x18000d4e2  jmp     short loc_18000D509
0x18000d4e4  mov     rax, [r8+48h]
0x18000d4e8  mov     r9d, 2; unsigned __int16
0x18000d4ee  mov     [rsp+78h+var_50], rax
0x18000d4f3  mov     edx, 131h; unsigned int
0x18000d4f8  mov     rax, [r8+28h]
0x18000d4fc  xor     r8d, r8d; int
0x18000d4ff  mov     [rsp+78h+var_58], rax
0x18000d504  call    ?Report@CEventsBase@@QEAAXKHGZZ; CEventsBase::Report(ulong,int,ushort,...)
0x18000d509  mov     rcx, [rsp+78h+var_20]
0x18000d50e  xor     rcx, rsp; StackCookie
0x18000d511  call    __security_check_cookie
0x18000d516  add     rsp, 60h
0x18000d51a  pop     rdi
0x18000d51b  pop     rsi
0x18000d51c  pop     rbx
0x18000d51d  retn
```
