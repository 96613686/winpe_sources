# pplx::details::_CancellationTokenState::~_CancellationTokenState(void)

- ea: `0x140015a3c`
- end: `0x140015b6f`
- name: `??1_CancellationTokenState@details@pplx@@UEAA@XZ`
- size: `307`
- prototype: `void __fastcall(pplx::details::_CancellationTokenState *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140017070`

## callees

- `0x140015a3c`
- `0x14001a340`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015b3e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015b3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140015a9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140015a9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140015a73`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140015a73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015b48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015b48`
- `msvcrt!??3@YAXPEAX@Z` at `0x140015ae6`
- `msvcrt!??3@YAXPEAX@Z` at `0x140015af7`
- `msvcrt!??3@YAXPEAX@Z` at `0x140015b23`
- `msvcrt!??3@YAXPEAX@Z` at `0x140015b34`
- `msvcrt!??3@YAXPEAX@Z` at `0x140015ae6`
- `msvcrt!??3@YAXPEAX@Z` at `0x140015af7`
- `msvcrt!??3@YAXPEAX@Z` at `0x140015b23`
- `msvcrt!??3@YAXPEAX@Z` at `0x140015b34`

## pseudocode

```c
void __fastcall pplx::details::_CancellationTokenState::~_CancellationTokenState(
        pplx::details::_CancellationTokenState *this)
{
  _QWORD *v2; // rbx
  _QWORD ***v3; // rsi
  _QWORD **v4; // rax
  _QWORD *i; // rdi
  volatile signed __int32 *v6; // rcx
  _QWORD *v7; // rcx
  _QWORD *v8; // rdi
  _QWORD *v9; // rdx
  _QWORD *v10; // rcx
  _QWORD *v11; // rbx
  char v12; // [rsp+20h] [rbp-48h] BYREF

  *(_QWORD *)this = &pplx::details::_CancellationTokenState::`vftable';
  v2 = (_QWORD *)std::_List_alloc<0,std::_List_base_types<pplx::details::_CancellationTokenRegistration *>>::_Buynode0(
                   this,
                   0,
                   0);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v3 = (_QWORD ***)((char *)this + 96);
  if ( (char *)this + 96 != &v12 )
  {
    v4 = *v3;
    *v3 = (_QWORD **)v2;
    v2 = v4;
    *((_QWORD *)this + 13) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  for ( i = (_QWORD *)*v2; i != v2; i = (_QWORD *)*i )
  {
    v6 = (volatile signed __int32 *)i[2];
    _InterlockedExchange(v6 + 4, 2);
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
  }
  v7 = (_QWORD *)*v2;
  *v2 = v2;
  v2[1] = v2;
  if ( v7 != v2 )
  {
    do
    {
      v8 = (_QWORD *)*v7;
      operator delete(v7);
      v7 = v8;
    }
    while ( v8 != v2 );
  }
  operator delete(v2);
  v9 = **v3;
  **v3 = *v3;
  (*v3)[1] = *v3;
  *((_QWORD *)this + 13) = 0;
  v10 = *v3;
  if ( v9 != *v3 )
  {
    do
    {
      v11 = (_QWORD *)*v9;
      operator delete(v9);
      v9 = v11;
      v10 = *v3;
    }
    while ( v11 != *v3 );
  }
  operator delete(v10);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  CloseHandle(*((HANDLE *)this + 3));
  *(_QWORD *)this = &pplx::details::_RefCounterBase::`vftable';
}

```

## disassembly

```asm
0x140015a3c  push    rbx
0x140015a3e  push    rsi
0x140015a3f  push    rdi
0x140015a40  push    r14
0x140015a42  sub     rsp, 48h
0x140015a46  mov     rax, cs:__security_cookie
0x140015a4d  xor     rax, rsp
0x140015a50  mov     [rsp+68h+var_38], rax
0x140015a55  mov     r14, rcx
0x140015a58  lea     rax, ??_7_CancellationTokenState@details@pplx@@6B@; const pplx::details::_CancellationTokenState::`vftable'
0x140015a5f  mov     [rcx], rax
0x140015a62  xor     r8d, r8d
0x140015a65  xor     edx, edx
0x140015a67  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@PEAV_CancellationTokenRegistration@details@pplx@@V?$allocator@PEAV_CancellationTokenRegistration@details@pplx@@@std@@@std@@@std@@QEAAPEAU?$_List_node@PEAV_CancellationTokenRegistration@details@pplx@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<pplx::details::_CancellationTokenRegistration *>>::_Buynode0(std::_List_node<pplx::details::_CancellationTokenRegistration *,void *> *,std::_List_node<pplx::details::_CancellationTokenRegistration *,void *> *)
0x140015a6c  mov     rbx, rax
0x140015a6f  lea     rcx, [r14+20h]; lpCriticalSection
0x140015a73  call    cs:__imp_EnterCriticalSection
0x140015a79  lea     rsi, [r14+60h]
0x140015a7d  lea     rax, [rsp+68h+var_48]
0x140015a82  cmp     rsi, rax
0x140015a85  jz      short loc_140015A98
0x140015a87  mov     rax, [rsi]
0x140015a8a  mov     [rsi], rbx
0x140015a8d  mov     rbx, rax
0x140015a90  mov     qword ptr [rsi+8], 0
0x140015a98  lea     rcx, [r14+20h]; lpCriticalSection
0x140015a9c  call    cs:__imp_LeaveCriticalSection
0x140015aa2  mov     rdi, [rbx]
0x140015aa5  cmp     rdi, rbx
0x140015aa8  jz      short loc_140015AD4
0x140015aaa  mov     rcx, [rdi+10h]
0x140015aae  mov     eax, 2
0x140015ab3  xchg    eax, [rcx+10h]
0x140015ab6  or      eax, 0FFFFFFFFh
0x140015ab9  lock xadd [rcx+8], eax
0x140015abe  cmp     eax, 1
0x140015ac1  jnz     short loc_140015ACF
0x140015ac3  mov     rax, [rcx]
0x140015ac6  mov     rax, [rax+8]
0x140015aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015acf  mov     rdi, [rdi]
0x140015ad2  jmp     short loc_140015AA5
0x140015ad4  mov     rcx, [rbx]
0x140015ad7  mov     [rbx], rbx
0x140015ada  mov     [rbx+8], rbx
0x140015ade  cmp     rcx, rbx
0x140015ae1  jz      short loc_140015AF4
0x140015ae3  mov     rdi, [rcx]
0x140015ae6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140015aec  mov     rcx, rdi
0x140015aef  cmp     rdi, rbx
0x140015af2  jnz     short loc_140015AE3
0x140015af4  mov     rcx, rbx
0x140015af7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140015afd  mov     rax, [rsi]
0x140015b00  mov     rdx, [rax]
0x140015b03  mov     [rax], rax
0x140015b06  mov     rax, [rsi]
0x140015b09  mov     [rax+8], rax
0x140015b0d  mov     qword ptr [rsi+8], 0
0x140015b15  mov     rcx, [rsi]
0x140015b18  cmp     rdx, rcx
0x140015b1b  jz      short loc_140015B34
0x140015b1d  mov     rbx, [rdx]
0x140015b20  mov     rcx, rdx
0x140015b23  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140015b29  mov     rdx, rbx
0x140015b2c  mov     rcx, [rsi]
0x140015b2f  cmp     rbx, rcx
0x140015b32  jnz     short loc_140015B1D
0x140015b34  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140015b3a  lea     rcx, [r14+20h]; lpCriticalSection
0x140015b3e  call    cs:__imp_DeleteCriticalSection
0x140015b44  mov     rcx, [r14+18h]; hObject
0x140015b48  call    cs:__imp_CloseHandle
0x140015b4e  lea     rax, ??_7_RefCounterBase@details@pplx@@6B@; const pplx::details::_RefCounterBase::`vftable'
0x140015b55  mov     [r14], rax
0x140015b58  mov     rcx, [rsp+68h+var_38]
0x140015b5d  xor     rcx, rsp; StackCookie
0x140015b60  call    __security_check_cookie
0x140015b65  add     rsp, 48h
0x140015b69  pop     r14
0x140015b6b  pop     rdi
0x140015b6c  pop     rsi
0x140015b6d  pop     rbx
0x140015b6e  retn
```
