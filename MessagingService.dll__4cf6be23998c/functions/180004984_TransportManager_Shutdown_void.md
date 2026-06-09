# TransportManager::Shutdown(void)

- ea: `0x180004984`
- end: `0x180004ad1`
- name: `?Shutdown@TransportManager@@QEAAXXZ`
- size: `333`
- prototype: `void __fastcall(TransportManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x180003500`

## callees

- `0x18000108c`
- `0x18000266c`
- `0x1800044dc`
- `0x180004984`
- `0x180005364`
- `0x18000aa50`
- `0x18000c010`

## string_xrefs

- `0x180004a60`: `onecoreuap\net\messaging\desktoptransport\service\transportmanager.cpp`

## pseudocode

```c
void __fastcall TransportManager::Shutdown(TransportManager *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  int v6; // eax
  char *v7; // rdi
  __int64 *v8; // rbx
  __int64 *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-38h] BYREF

  if ( (unsigned int)dword_180013018 > 4 )
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, (int)&dword_1800101E4, 0, 0, 2u, &v12);
  v2 = *((_QWORD *)this + 5);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 48LL))(v2);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 40LL))(*((_QWORD *)this + 5));
    v3 = *((_QWORD *)this + 5);
    if ( v3 )
    {
      *((_QWORD *)this + 5) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    }
  }
  v4 = *((_QWORD *)this + 6);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 32LL))(v4);
    v5 = *((_QWORD *)this + 6);
    if ( v5 )
    {
      *((_QWORD *)this + 6) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
  v6 = TransportManager::_StopIdleTimer(this);
  if ( v6 < 0 )
    Log_HREvent_0((unsigned int)v6, 0, "onecoreuap\\net\\messaging\\desktoptransport\\service\\transportmanager.cpp");
  v7 = (char *)this + 56;
  while ( 1 )
  {
    v8 = *(__int64 **)v7;
    if ( *(char **)v7 == v7 )
      break;
    v9 = (__int64 *)v8[1];
    v10 = *v8;
    *v9 = *v8;
    *(_QWORD *)(v10 + 8) = v9;
    v11 = v8[2];
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    operator delete(v8, (const struct std::nothrow_t *)&std::nothrow);
  }
  *((_QWORD *)v7 + 2) = 0;
}

```

## disassembly

```asm
0x180004984  mov     [rsp+arg_8], rbx
0x180004989  push    rdi
0x18000498a  sub     rsp, 60h
0x18000498e  mov     rax, cs:__security_cookie
0x180004995  xor     rax, rsp
0x180004998  mov     [rsp+68h+var_18], rax
0x18000499d  mov     rbx, rcx
0x1800049a0  mov     eax, cs:dword_180013018
0x1800049a6  cmp     eax, 4
0x1800049a9  jbe     short loc_1800049D6
0x1800049ab  lea     rax, [rsp+68h+var_38]
0x1800049b0  mov     [rsp+68h+var_40], rax; PEVENT_DATA_DESCRIPTOR
0x1800049b5  mov     [rsp+68h+var_48], 2; ULONG
0x1800049bd  xor     r9d, r9d; int
0x1800049c0  xor     r8d, r8d; int
0x1800049c3  lea     rdx, dword_1800101E4; int
0x1800049ca  lea     rcx, dword_180013018; int
0x1800049d1  call    _tlgWriteTransfer_EventWriteTransfer
0x1800049d6  mov     rcx, [rbx+28h]
0x1800049da  test    rcx, rcx
0x1800049dd  jz      short loc_180004A1A
0x1800049df  mov     rax, [rcx]
0x1800049e2  mov     rax, [rax+30h]
0x1800049e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049eb  mov     rcx, [rbx+28h]
0x1800049ef  mov     rax, [rcx]
0x1800049f2  mov     rax, [rax+28h]
0x1800049f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049fb  nop
0x1800049fc  mov     rcx, [rbx+28h]
0x180004a00  test    rcx, rcx
0x180004a03  jz      short loc_180004A1A
0x180004a05  mov     qword ptr [rbx+28h], 0
0x180004a0d  mov     rax, [rcx]
0x180004a10  mov     rax, [rax+10h]
0x180004a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a19  nop
0x180004a1a  mov     rcx, [rbx+30h]
0x180004a1e  test    rcx, rcx
0x180004a21  jz      short loc_180004A4E
0x180004a23  mov     rax, [rcx]
0x180004a26  mov     rax, [rax+20h]
0x180004a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a2f  nop
0x180004a30  mov     rcx, [rbx+30h]
0x180004a34  test    rcx, rcx
0x180004a37  jz      short loc_180004A4E
0x180004a39  mov     qword ptr [rbx+30h], 0
0x180004a41  mov     rax, [rcx]
0x180004a44  mov     rax, [rax+10h]
0x180004a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a4d  nop
0x180004a4e  mov     rcx, rbx; this
0x180004a51  call    ?_StopIdleTimer@TransportManager@@AEAAJXZ; TransportManager::_StopIdleTimer(void)
0x180004a56  test    eax, eax
0x180004a58  jns     short loc_180004A70
0x180004a5a  mov     r9d, 6Ah ; 'j'
0x180004a60  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\messaging\\desktoptran"...
0x180004a67  xor     edx, edx
0x180004a69  mov     ecx, eax
0x180004a6b  call    Log_HREvent_0
0x180004a70  lea     rdi, [rbx+38h]
0x180004a74  mov     rbx, [rdi]
0x180004a77  cmp     rbx, rdi
0x180004a7a  jz      short loc_180004AB1
0x180004a7c  mov     rcx, [rbx+8]
0x180004a80  mov     rax, [rbx]
0x180004a83  mov     [rcx], rax
0x180004a86  mov     [rax+8], rcx
0x180004a8a  mov     rcx, [rbx+10h]
0x180004a8e  test    rcx, rcx
0x180004a91  jz      short loc_180004AA0
0x180004a93  mov     rax, [rcx]
0x180004a96  mov     rax, [rax+10h]
0x180004a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a9f  nop
0x180004aa0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004aa7  mov     rcx, rbx; void *
0x180004aaa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004aaf  jmp     short loc_180004A74
0x180004ab1  mov     qword ptr [rdi+10h], 0
0x180004ab9  mov     rcx, [rsp+68h+var_18]
0x180004abe  xor     rcx, rsp; StackCookie
0x180004ac1  call    __security_check_cookie
0x180004ac6  mov     rbx, [rsp+68h+arg_8]
0x180004acb  add     rsp, 60h
0x180004acf  pop     rdi
0x180004ad0  retn
```
