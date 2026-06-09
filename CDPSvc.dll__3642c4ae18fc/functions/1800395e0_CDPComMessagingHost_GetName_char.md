# CDPComMessagingHost::GetName(char * *)

- ea: `0x1800395e0`
- end: `0x1800396dc`
- name: `?GetName@CDPComMessagingHost@@UEAAJPEAPEAD@Z`
- size: `252`
- prototype: `__int64 __fastcall(CDPComMessagingHost *__hidden this, char **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006668`
- `0x18000c2e8`
- `0x18000c914`
- `0x18000cb8c`
- `0x1800225a0`
- `0x1800395e0`
- `0x18006a010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180039635`
- `msvcp_win!_Mtx_unlock` at `0x18003966c`
- `msvcp_win!_Mtx_unlock` at `0x180039635`
- `msvcp_win!_Mtx_unlock` at `0x18003966c`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800396ab`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800396ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003967a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003967a`

## pseudocode

```c
__int64 __fastcall CDPComMessagingHost::GetName(CDPComMessagingHost *this, char **a2)
{
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // r8
  char *v9; // rax
  const char *v10; // r8
  char *Source[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v12; // [rsp+30h] [rbp-28h]
  unsigned __int64 v13; // [rsp+38h] [rbp-20h]

  if ( !a2 )
    return 2147500035LL;
  std::string::string(Source);
  std::_Mutex_base::lock((CDPComMessagingHost *)((char *)this + 40));
  v5 = *((_QWORD *)this + 3);
  if ( v5 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
    v8 = -1;
    do
      ++v8;
    while ( *(_BYTE *)(v7 + v8) );
    std::string::_Assign<char>(Source);
    _Mtx_unlock((CDPComMessagingHost *)((char *)this + 40));
    v9 = (char *)CoTaskMemAlloc(v12 + 1);
    *a2 = v9;
    if ( v9 )
    {
      v10 = (const char *)Source;
      if ( v13 > 0xF )
        v10 = Source[0];
      strcpy_s(v9, v12 + 1, v10);
      v6 = 0;
    }
    else
    {
      v6 = -2147024882;
    }
  }
  else
  {
    _Mtx_unlock((CDPComMessagingHost *)((char *)this + 40));
    v6 = -2147418113;
  }
  std::string::~string(Source);
  return v6;
}

```

## disassembly

```asm
0x1800395e0  mov     [rsp+arg_10], rbx
0x1800395e5  mov     [rsp+arg_18], rsi
0x1800395ea  push    rdi
0x1800395eb  sub     rsp, 50h
0x1800395ef  mov     rax, cs:__security_cookie
0x1800395f6  xor     rax, rsp
0x1800395f9  mov     [rsp+58h+var_18], rax
0x1800395fe  mov     rsi, rdx
0x180039601  mov     rdi, rcx
0x180039604  test    rdx, rdx
0x180039607  jnz     short loc_180039613
0x180039609  mov     eax, 80004003h
0x18003960e  jmp     loc_1800396BF
0x180039613  lea     rcx, [rsp+58h+Source]
0x180039618  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18003961d  lea     rbx, [rdi+28h]
0x180039621  mov     rcx, rbx; this
0x180039624  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180039629  mov     rcx, [rdi+18h]
0x18003962d  test    rcx, rcx
0x180039630  jnz     short loc_180039642
0x180039632  mov     rcx, rbx; _Mtx_t
0x180039635  call    cs:__imp__Mtx_unlock
0x18003963b  mov     ebx, 8000FFFFh
0x180039640  jmp     short loc_1800396B3
0x180039642  mov     rax, [rcx]
0x180039645  mov     rax, [rax+18h]
0x180039649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003964e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039652  inc     r8
0x180039655  cmp     byte ptr [rax+r8], 0
0x18003965a  jnz     short loc_180039652
0x18003965c  mov     rdx, rax
0x18003965f  lea     rcx, [rsp+58h+Source]
0x180039664  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x180039669  mov     rcx, rbx; _Mtx_t
0x18003966c  call    cs:__imp__Mtx_unlock
0x180039672  mov     rcx, [rsp+58h+var_28]
0x180039677  inc     rcx; cb
0x18003967a  call    cs:__imp_CoTaskMemAlloc
0x180039680  mov     [rsi], rax
0x180039683  test    rax, rax
0x180039686  jnz     short loc_18003968F
0x180039688  mov     ebx, 8007000Eh
0x18003968d  jmp     short loc_1800396B3
0x18003968f  lea     r8, [rsp+58h+Source]
0x180039694  cmp     [rsp+58h+var_20], 0Fh
0x18003969a  cmova   r8, [rsp+58h+Source]; Source
0x1800396a0  mov     rdx, [rsp+58h+var_28]
0x1800396a5  inc     rdx; SizeInBytes
0x1800396a8  mov     rcx, rax; Destination
0x1800396ab  call    cs:__imp_strcpy_s
0x1800396b1  xor     ebx, ebx
0x1800396b3  lea     rcx, [rsp+58h+Source]
0x1800396b8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800396bd  mov     eax, ebx
0x1800396bf  mov     rcx, [rsp+58h+var_18]
0x1800396c4  xor     rcx, rsp; StackCookie
0x1800396c7  call    __security_check_cookie
0x1800396cc  mov     rbx, [rsp+58h+arg_10]
0x1800396d1  mov     rsi, [rsp+58h+arg_18]
0x1800396d6  add     rsp, 50h
0x1800396da  pop     rdi
0x1800396db  retn
```
