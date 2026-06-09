# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::RunCacheWorkAsync$_ResumeCoro$1

- ea: `0x18001cca0`
- end: `0x18001cddc`
- name: `winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::RunCacheWorkAsync$_ResumeCoro$1`
- size: `316`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800053f0`

## callees

- `0x180005550`
- `0x18000ac20`
- `0x1800128a0`
- `0x1800181b0`
- `0x180018238`
- `0x18001cca0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::RunCacheWorkAsync__ResumeCoro_1(
        signed __int64 a1)
{
  signed __int64 v1; // rbx
  __int64 v2; // rdx
  signed __int64 v3; // rax
  signed __int64 v4; // rtt

  v1 = a1;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 3:
      goto LABEL_13;
    case 2:
      v2 = *(_QWORD *)(a1 + 40);
      *(_QWORD *)(a1 + 16) = 0;
      if ( !v2 )
        goto LABEL_7;
      *(_QWORD *)(a1 + 16) = v2;
      v3 = *(_QWORD *)(v2 + 8);
      if ( v3 < 0 )
        goto LABEL_6;
      break;
    case 4:
      winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::RunCacheWork(*(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager **)(a1 + 16));
      if ( *(_QWORD *)(v1 + 16) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::unconditional_release_ref((_QWORD **)(v1 + 16));
      goto LABEL_13;
    case 5:
      if ( *(_QWORD *)(a1 + 16) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::unconditional_release_ref((_QWORD **)(a1 + 16));
LABEL_13:
      if ( *(_WORD *)(v1 + 10) )
        operator delete((void *)v1);
      return;
    default:
      __debugbreak();
      return;
  }
  while ( 1 )
  {
    a1 = v3 + 1;
    v4 = v3;
    v3 = _InterlockedCompareExchange64((volatile signed __int64 *)(v2 + 8), v3 + 1, v3);
    if ( v4 == v3 )
      break;
    if ( v3 < 0 )
    {
LABEL_6:
      _InterlockedIncrement((volatile signed __int32 *)(2 * v3 + 24));
      break;
    }
  }
LABEL_7:
  *(_BYTE *)(v1 + 24) = 0;
  *(_WORD *)(v1 + 8) = 4;
  `winrt::resume_background'::`2'::awaitable::await_suspend(a1, v1);
}

```

## disassembly

```asm
0x18001cca0  mov     [rsp+arg_8], rbx
0x18001cca5  mov     [rsp+arg_0], rcx
0x18001ccaa  push    rdi
0x18001ccab  sub     rsp, 50h
0x18001ccaf  mov     rax, cs:__security_cookie
0x18001ccb6  xor     rax, rsp
0x18001ccb9  mov     [rsp+58h+var_18], rax
0x18001ccbe  mov     rbx, [rsp+58h+arg_0]
0x18001ccc3  mov     [rsp+58h+var_30], rbx
0x18001ccc8  movzx   eax, word ptr [rbx+8]
0x18001cccc  mov     [rsp+58h+var_38], ax
0x18001ccd1  inc     ax; switch 7 cases
0x18001ccd4  cmp     ax, 6
0x18001ccd8  ja      def_18001CCF3; jumptable 000000018001CCF3 default case, cases 0,1
0x18001ccde  movsx   rax, ax
0x18001cce2  lea     rdx, cs:180000000h
0x18001cce9  mov     ecx, ds:(jpt_18001CCF3 - 180000000h)[rdx+rax*4]
0x18001ccf0  add     rcx, rdx
0x18001ccf3  jmp     rcx; switch jump
0x18001ccf5  jmp     loc_18001CD90; jumptable 000000018001CCF3 case 3
0x18001ccfa  mov     rdx, [rbx+28h]; jumptable 000000018001CCF3 case 2
0x18001ccfe  mov     qword ptr [rbx+10h], 0
0x18001cd06  test    rdx, rdx
0x18001cd09  jz      short loc_18001CD36
0x18001cd0b  mov     [rbx+10h], rdx
0x18001cd0f  mov     rax, [rdx+8]
0x18001cd13  test    rax, rax
0x18001cd16  js      short loc_18001CD31
0x18001cd18  nop     dword ptr [rax+rax+00000000h]
0x18001cd20  lea     rcx, [rax+1]
0x18001cd24  lock cmpxchg [rdx+8], rcx
0x18001cd2a  jz      short loc_18001CD36
0x18001cd2c  test    rax, rax
0x18001cd2f  jns     short loc_18001CD20
0x18001cd31  lock inc dword ptr [rax+rax+18h]
0x18001cd36  mov     byte ptr [rbx+18h], 0
0x18001cd3a  mov     eax, 4
0x18001cd3f  mov     [rbx+8], ax
0x18001cd43  mov     rdx, rbx
0x18001cd46  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x18001cd4b  jmp     short loc_18001CDA7
0x18001cd4d  lea     rcx, [rbx+10h]; jumptable 000000018001CCF3 case 5
0x18001cd51  mov     rax, [rcx]
0x18001cd54  mov     [rsp+58h+var_28], rax
0x18001cd59  test    rax, rax
0x18001cd5c  jz      short loc_18001CD64
0x18001cd5e  call    ?unconditional_release_ref@?$com_ptr@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::unconditional_release_ref(void)
0x18001cd63  nop
0x18001cd64  jmp     short loc_18001CD90; jumptable 000000018001CCF3 case -1
0x18001cd66  mov     rcx, [rbx+10h]; jumptable 000000018001CCF3 case 4
0x18001cd6a  mov     [rsp+58h+var_28], rcx
0x18001cd6f  call    ?RunCacheWork@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAAXXZ; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::RunCacheWork(void)
0x18001cd74  nop
0x18001cd75  mov     rax, [rbx+10h]
0x18001cd79  mov     [rsp+58h+var_28], rax
0x18001cd7e  test    rax, rax
0x18001cd81  jz      short loc_18001CD8D
0x18001cd83  lea     rcx, [rbx+10h]
0x18001cd87  call    ?unconditional_release_ref@?$com_ptr@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::unconditional_release_ref(void)
0x18001cd8c  nop
0x18001cd8d  nop     dword ptr [rax]
0x18001cd90  cmp     word ptr [rbx+0Ah], 0; jumptable 000000018001CCF3 case -1
0x18001cd95  jz      short loc_18001CDA7
0x18001cd97  mov     edx, 30h ; '0'; unsigned __int64
0x18001cd9c  mov     rcx, rbx; void *
0x18001cd9f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cda4  jmp     short loc_18001CDA7
0x18001cda6  int     3; Trap to Debugger
0x18001cda7  mov     rcx, [rsp+58h+var_18]
0x18001cdac  xor     rcx, rsp; StackCookie
0x18001cdaf  call    __security_check_cookie
0x18001cdb4  mov     rbx, [rsp+58h+arg_8]
0x18001cdb9  add     rsp, 50h
0x18001cdbd  pop     rdi
0x18001cdbe  retn
```
