# CommunicationPortContext::ImpersonateClient(void)

- ea: `0x18000d710`
- end: `0x18000d7e3`
- name: `?ImpersonateClient@CommunicationPortContext@@QEAAXXZ`
- size: `211`
- prototype: `void __fastcall(CommunicationPortContext *__hidden this)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c20c`
- `0x18000f538`
- `0x18000ff74`
- `0x180095cac`
- `0x18009664c`
- `0x1800974a8`

## callees

- `0x18000d55c`
- `0x18000d710`
- `0x18000f7bc`
- `0x1800217ac`
- `0x18004d664`
- `0x1800ab1b0`

## import_xrefs

- `ntdll!NtAlpcImpersonateClientOfPort` at `0x18000d73d`
- `ntdll!NtAlpcImpersonateClientOfPort` at `0x18000d73d`

## pseudocode

```c
void __fastcall CommunicationPortContext::ImpersonateClient(CommunicationPortContext *this, const char *a2)
{
  int v3; // eax
  int v4; // ebx
  int pExceptionObject; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 3) == 0x6E6F737265706D69LL )
  {
    FailAssert(0x41u, a2);
    __debugbreak();
  }
  v3 = NtAlpcImpersonateClientOfPort(*((_QWORD *)this + 4), *((_QWORD *)this + 5), 0);
  if ( v3 )
  {
    Exception::Exception((Exception *)&pExceptionObject, v3 | 0x10000000, 0);
    v4 = pExceptionObject;
    EventLogger::LogEvent<long,EventTag,unsigned int>(
      (_DWORD)this + 16,
      1668312129,
      1869771365,
      pExceptionObject,
      1668312161,
      71);
    pExceptionObject = v4;
    throw (OSException *)&pExceptionObject;
  }
  *((_QWORD *)this + 3) = 0x6E6F737265706D69LL;
  EventLogger::LogEvent<EventTag>((unsigned int *)this + 4, 0x74726F5063706C41LL, 0x6574617473LL, 0x6E6F737265706D69LL);
}

```

## disassembly

```asm
0x18000d710  mov     [rsp+arg_8], rbx
0x18000d715  mov     [rsp+arg_10], rsi
0x18000d71a  push    rdi
0x18000d71b  sub     rsp, 30h
0x18000d71f  mov     rbx, 6E6F737265706D69h
0x18000d729  mov     rdi, rcx
0x18000d72c  cmp     [rcx+18h], rbx
0x18000d730  jz      short loc_18000D77A
0x18000d732  mov     rdx, [rcx+28h]
0x18000d736  xor     r8d, r8d
0x18000d739  mov     rcx, [rcx+20h]
0x18000d73d  call    cs:__imp_NtAlpcImpersonateClientOfPort
0x18000d743  test    eax, eax
0x18000d745  jnz     short loc_18000D785
0x18000d747  mov     rdx, 74726F5063706C41h; char *
0x18000d751  mov     [rdi+18h], rbx
0x18000d755  mov     r8, 6574617473h
0x18000d75f  lea     rcx, [rdi+10h]
0x18000d763  mov     r9, rbx
0x18000d766  mov     rbx, [rsp+38h+arg_8]
0x18000d76b  mov     rsi, [rsp+38h+arg_10]
0x18000d770  add     rsp, 30h
0x18000d774  pop     rdi
0x18000d775  jmp     ??$LogEvent@VEventTag@@@EventLogger@@QEBAXVEventTag@@00@Z; EventLogger::LogEvent<EventTag>(EventTag,EventTag,EventTag)
0x18000d77a  mov     ecx, 41h ; 'A'; unsigned int
0x18000d77f  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
0x18000d784  int     3; Trap to Debugger
0x18000d785  bts     eax, 1Ch
0x18000d789  lea     rcx, [rsp+38h+pExceptionObject]; this
0x18000d78e  mov     edx, eax; int
0x18000d790  xor     r8d, r8d; unsigned int
0x18000d793  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18000d798  mov     ebx, [rsp+38h+pExceptionObject]
0x18000d79c  lea     rcx, [rdi+10h]
0x18000d7a0  mov     rdx, 74726F5063706C41h
0x18000d7aa  mov     [rsp+38h+var_10], 47h ; 'G'
0x18000d7b2  mov     r8, 726F727265h
0x18000d7bc  mov     [rsp+38h+var_18], 63706C61h
0x18000d7c5  mov     r9d, ebx
0x18000d7c8  call    ??$LogEvent@JVEventTag@@I@EventLogger@@QEBAXVEventTag@@0J0I@Z; EventLogger::LogEvent<long,EventTag,uint>(EventTag,EventTag,long,EventTag,uint)
0x18000d7cd  lea     rdx, _TI2?AVOSException@@; pThrowInfo
0x18000d7d4  mov     [rsp+38h+pExceptionObject], ebx
0x18000d7d8  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000d7dd  call    _CxxThrowException_0
```
