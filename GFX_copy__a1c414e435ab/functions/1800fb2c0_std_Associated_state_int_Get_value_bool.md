# std::_Associated_state<int>::_Get_value(bool)

- ea: `0x1800fb2c0`
- end: `0x1800fb3e4`
- name: `?_Get_value@?$_Associated_state@H@std@@UEAAAEAH_N@Z`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800fb140`

## callees

- `0x1800573f0`
- `0x1800795a0`
- `0x1800fb2c0`
- `0x1801ae074`

## import_xrefs

- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800fb3a2`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800fb3dd`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800fb3a2`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800fb3dd`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800fb303`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800fb33f`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800fb303`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800fb33f`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800fb390`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800fb3cb`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800fb390`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800fb3cb`
- `MSVCP140!_Cnd_wait` at `0x1800fb3b1`
- `MSVCP140!_Cnd_wait` at `0x1800fb3b1`
- `MSVCP140!_Mtx_unlock` at `0x1800fb352`
- `MSVCP140!_Mtx_unlock` at `0x1800fb352`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Associated_state<int>::_Get_value(__int64 a1, char a2)
{
  _BYTE *v4; // rsi
  _Mtx_t v6; // [rsp+20h] [rbp-20h] BYREF
  char v7; // [rsp+28h] [rbp-18h]
  __int128 v8; // [rsp+30h] [rbp-10h] BYREF

  v6 = (_Mtx_t)(a1 + 32);
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 32));
  v7 = 1;
  v4 = (_BYTE *)(a1 + 184);
  if ( a2 && *v4 )
    std::_Throw_future_error2(2);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v8 = 0;
    __ExceptionPtrCopy(&v8, (const void *)(a1 + 16));
    __ExceptionPtrRethrow(&v8);
    goto LABEL_13;
  }
  *v4 = 1;
  if ( !*(_BYTE *)(a1 + 194) )
  {
    *(_BYTE *)(a1 + 194) = 1;
    (*(void (__fastcall **)(__int64, _Mtx_t *))(*(_QWORD *)a1 + 32LL))(a1, &v6);
  }
  while ( !*(_DWORD *)(a1 + 188) )
LABEL_13:
    _Cnd_wait((_Cnd_t)(a1 + 112), v6);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v8 = 0;
    __ExceptionPtrCopy(&v8, (const void *)(a1 + 16));
    __ExceptionPtrRethrow(&v8);
    JUMPOUT(0x1800FB3E3LL);
  }
  if ( v7 )
    _Mtx_unlock(v6);
  return a1 + 12;
}

```

## disassembly

```asm
0x1800fb2c0  mov     [rsp-8+arg_8], rbx
0x1800fb2c5  mov     [rsp-8+arg_10], rsi
0x1800fb2ca  mov     [rsp-8+arg_18], rdi
0x1800fb2cf  push    rbp
0x1800fb2d0  mov     rbp, rsp
0x1800fb2d3  sub     rsp, 40h
0x1800fb2d7  mov     bl, dl
0x1800fb2d9  mov     rdi, rcx
0x1800fb2dc  add     rcx, 20h ; ' '; this
0x1800fb2e0  mov     [rbp+var_20], rcx
0x1800fb2e4  mov     [rbp+var_18], 0
0x1800fb2e8  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800fb2ed  mov     [rbp+var_18], 1
0x1800fb2f1  lea     rsi, [rdi+0B8h]
0x1800fb2f8  test    bl, bl
0x1800fb2fa  jnz     short loc_1800FB371
0x1800fb2fc  lea     rbx, [rdi+10h]
0x1800fb300  mov     rcx, rbx
0x1800fb303  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800fb309  test    al, al
0x1800fb30b  jnz     short loc_1800FB381
0x1800fb30d  mov     byte ptr [rsi], 1
0x1800fb310  cmp     [rdi+0C2h], al
0x1800fb316  jnz     short loc_1800FB333
0x1800fb318  mov     byte ptr [rdi+0C2h], 1
0x1800fb31f  mov     rax, [rdi]
0x1800fb322  lea     rdx, [rbp+var_20]
0x1800fb326  mov     rcx, rdi
0x1800fb329  mov     rax, [rax+20h]
0x1800fb32d  call    cs:__guard_dispatch_icall_fptr
0x1800fb333  cmp     dword ptr [rdi+0BCh], 0
0x1800fb33a  jz      short loc_1800FB3A9
0x1800fb33c  mov     rcx, rbx
0x1800fb33f  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800fb345  test    al, al
0x1800fb347  jnz     short loc_1800FB3BC
0x1800fb349  cmp     [rbp+var_18], al
0x1800fb34c  jz      short loc_1800FB358
0x1800fb34e  mov     rcx, [rbp+var_20]; _Mtx_t
0x1800fb352  call    cs:__imp__Mtx_unlock
0x1800fb358  lea     rax, [rdi+0Ch]
0x1800fb35c  mov     rbx, [rsp+40h+arg_8]
0x1800fb361  mov     rsi, [rsp+40h+arg_10]
0x1800fb366  mov     rdi, [rsp+40h+arg_18]
0x1800fb36b  add     rsp, 40h
0x1800fb36f  pop     rbp
0x1800fb370  retn
0x1800fb371  cmp     byte ptr [rsi], 0
0x1800fb374  jz      short loc_1800FB2FC
0x1800fb376  mov     ecx, 2
0x1800fb37b  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x1800fb381  xorps   xmm0, xmm0
0x1800fb384  movdqu  [rbp+var_10], xmm0
0x1800fb389  mov     rdx, rbx
0x1800fb38c  lea     rcx, [rbp+var_10]
0x1800fb390  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800fb396  lea     rax, [rbp+var_10]
0x1800fb39a  mov     [rbp+arg_0], rax
0x1800fb39e  lea     rcx, [rbp+var_10]
0x1800fb3a2  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1800fb3a8  nop
0x1800fb3a9  mov     rdx, [rbp+var_20]; _Mtx_t
0x1800fb3ad  lea     rcx, [rdi+70h]; _Cnd_t
0x1800fb3b1  call    cs:__imp__Cnd_wait
0x1800fb3b7  jmp     loc_1800FB333
0x1800fb3bc  xorps   xmm0, xmm0
0x1800fb3bf  movdqu  [rbp+var_10], xmm0
0x1800fb3c4  mov     rdx, rbx
0x1800fb3c7  lea     rcx, [rbp+var_10]
0x1800fb3cb  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800fb3d1  lea     rax, [rbp+var_10]
0x1800fb3d5  mov     [rbp+arg_0], rax
0x1800fb3d9  lea     rcx, [rbp+var_10]
0x1800fb3dd  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
