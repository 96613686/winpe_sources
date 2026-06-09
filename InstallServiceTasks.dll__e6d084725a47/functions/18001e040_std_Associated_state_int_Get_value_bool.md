# std::_Associated_state<int>::_Get_value(bool)

- ea: `0x18001e040`
- end: `0x18001e126`
- name: `?_Get_value@?$_Associated_state@H@std@@UEAAAEAH_N@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001e130`

## callees

- `0x18001ab74`
- `0x18001b630`
- `0x18001e040`
- `0x18001e3f4`
- `0x18001ebc0`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x18001e0cc`
- `msvcp_win!_Cnd_wait` at `0x18001e0cc`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18001e0ac`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18001e109`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18001e0ac`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18001e109`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001e09a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001e0f7`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001e09a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001e0f7`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18001e081`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18001e0de`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18001e081`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18001e0de`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Associated_state<int>::_Get_value(__int64 a1, char a2)
{
  _BYTE *v4; // rsi
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  _Mtx_t v7[3]; // [rsp+30h] [rbp-18h] BYREF

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v7, a1 + 32);
  v4 = (_BYTE *)(a1 + 184);
  if ( a2 && *v4 )
    std::_Throw_future_error2(2);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 16));
    __ExceptionPtrRethrow(&v6);
  }
  *v4 = 1;
  std::_Associated_state<int>::_Maybe_run_deferred_function(a1, v7);
  while ( !*(_DWORD *)(a1 + 188) )
    _Cnd_wait((_Cnd_t)(a1 + 112), v7[0]);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 16));
    __ExceptionPtrRethrow(&v6);
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v7);
  return a1 + 12;
}

```

## disassembly

```asm
0x18001e040  push    rbp
0x18001e042  push    rbx
0x18001e043  push    rsi
0x18001e044  push    rdi
0x18001e045  mov     rbp, rsp
0x18001e048  sub     rsp, 48h
0x18001e04c  mov     bl, dl
0x18001e04e  mov     rdi, rcx
0x18001e051  lea     rdx, [rcx+20h]
0x18001e055  lea     rcx, [rbp+var_18]
0x18001e059  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001e05e  nop
0x18001e05f  lea     rsi, [rdi+0B8h]
0x18001e066  test    bl, bl
0x18001e068  jz      short loc_18001E07A
0x18001e06a  cmp     byte ptr [rsi], 0
0x18001e06d  jz      short loc_18001E07A
0x18001e06f  mov     ecx, 2
0x18001e074  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18001e07a  lea     rbx, [rdi+10h]
0x18001e07e  mov     rcx, rbx
0x18001e081  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18001e087  test    al, al
0x18001e089  jz      short loc_18001E0B3
0x18001e08b  xorps   xmm0, xmm0
0x18001e08e  movdqu  [rbp+var_28], xmm0
0x18001e093  mov     rdx, rbx
0x18001e096  lea     rcx, [rbp+var_28]
0x18001e09a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001e0a0  lea     rax, [rbp+var_28]
0x18001e0a4  mov     [rbp+arg_0], rax
0x18001e0a8  lea     rcx, [rbp+var_28]
0x18001e0ac  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18001e0b2  nop
0x18001e0b3  mov     byte ptr [rsi], 1
0x18001e0b6  lea     rdx, [rbp+var_18]
0x18001e0ba  mov     rcx, rdi
0x18001e0bd  call    ?_Maybe_run_deferred_function@?$_Associated_state@H@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<int>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x18001e0c2  jmp     short loc_18001E0D2
0x18001e0c4  mov     rdx, [rbp+var_18]; _Mtx_t
0x18001e0c8  lea     rcx, [rdi+70h]; _Cnd_t
0x18001e0cc  call    cs:__imp__Cnd_wait
0x18001e0d2  cmp     dword ptr [rdi+0BCh], 0
0x18001e0d9  jz      short loc_18001E0C4
0x18001e0db  mov     rcx, rbx
0x18001e0de  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18001e0e4  test    al, al
0x18001e0e6  jz      short loc_18001E110
0x18001e0e8  xorps   xmm0, xmm0
0x18001e0eb  movdqu  [rbp+var_28], xmm0
0x18001e0f0  mov     rdx, rbx
0x18001e0f3  lea     rcx, [rbp+var_28]
0x18001e0f7  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001e0fd  lea     rax, [rbp+var_28]
0x18001e101  mov     [rbp+arg_0], rax
0x18001e105  lea     rcx, [rbp+var_28]
0x18001e109  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18001e10f  nop
0x18001e110  lea     rcx, [rbp+var_18]
0x18001e114  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18001e119  lea     rax, [rdi+0Ch]
0x18001e11d  add     rsp, 48h
0x18001e121  pop     rdi
0x18001e122  pop     rsi
0x18001e123  pop     rbx
0x18001e124  pop     rbp
0x18001e125  retn
```
