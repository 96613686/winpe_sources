# std::_Associated_state<int>::_Get_value(bool)

- ea: `0x180059d90`
- end: `0x180059eb4`
- name: `?_Get_value@?$_Associated_state@H@std@@UEAAAEAH_N@Z`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180059c10`

## callees

- `0x180057e70`
- `0x180059d90`
- `0x180076df0`
- `0x1801b1c94`

## import_xrefs

- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180059e72`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180059ead`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180059e72`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180059ead`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180059dd3`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180059e0f`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180059dd3`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180059e0f`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180059e60`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180059e9b`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180059e60`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180059e9b`
- `MSVCP140!_Cnd_wait` at `0x180059e81`
- `MSVCP140!_Cnd_wait` at `0x180059e81`
- `MSVCP140!_Mtx_unlock` at `0x180059e22`
- `MSVCP140!_Mtx_unlock` at `0x180059e22`

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
    JUMPOUT(0x180059EB3LL);
  }
  if ( v7 )
    _Mtx_unlock(v6);
  return a1 + 12;
}

```

## disassembly

```asm
0x180059d90  mov     [rsp-8+arg_8], rbx
0x180059d95  mov     [rsp-8+arg_10], rsi
0x180059d9a  mov     [rsp-8+arg_18], rdi
0x180059d9f  push    rbp
0x180059da0  mov     rbp, rsp
0x180059da3  sub     rsp, 40h
0x180059da7  mov     bl, dl
0x180059da9  mov     rdi, rcx
0x180059dac  add     rcx, 20h ; ' '; this
0x180059db0  mov     [rbp+var_20], rcx
0x180059db4  mov     [rbp+var_18], 0
0x180059db8  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180059dbd  mov     [rbp+var_18], 1
0x180059dc1  lea     rsi, [rdi+0B8h]
0x180059dc8  test    bl, bl
0x180059dca  jnz     short loc_180059E41
0x180059dcc  lea     rbx, [rdi+10h]
0x180059dd0  mov     rcx, rbx
0x180059dd3  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180059dd9  test    al, al
0x180059ddb  jnz     short loc_180059E51
0x180059ddd  mov     byte ptr [rsi], 1
0x180059de0  cmp     [rdi+0C2h], al
0x180059de6  jnz     short loc_180059E03
0x180059de8  mov     byte ptr [rdi+0C2h], 1
0x180059def  mov     rax, [rdi]
0x180059df2  lea     rdx, [rbp+var_20]
0x180059df6  mov     rcx, rdi
0x180059df9  mov     rax, [rax+20h]
0x180059dfd  call    cs:__guard_dispatch_icall_fptr
0x180059e03  cmp     dword ptr [rdi+0BCh], 0
0x180059e0a  jz      short loc_180059E79
0x180059e0c  mov     rcx, rbx
0x180059e0f  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180059e15  test    al, al
0x180059e17  jnz     short loc_180059E8C
0x180059e19  cmp     [rbp+var_18], al
0x180059e1c  jz      short loc_180059E28
0x180059e1e  mov     rcx, [rbp+var_20]; _Mtx_t
0x180059e22  call    cs:__imp__Mtx_unlock
0x180059e28  lea     rax, [rdi+0Ch]
0x180059e2c  mov     rbx, [rsp+40h+arg_8]
0x180059e31  mov     rsi, [rsp+40h+arg_10]
0x180059e36  mov     rdi, [rsp+40h+arg_18]
0x180059e3b  add     rsp, 40h
0x180059e3f  pop     rbp
0x180059e40  retn
0x180059e41  cmp     byte ptr [rsi], 0
0x180059e44  jz      short loc_180059DCC
0x180059e46  mov     ecx, 2
0x180059e4b  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180059e51  xorps   xmm0, xmm0
0x180059e54  movdqu  [rbp+var_10], xmm0
0x180059e59  mov     rdx, rbx
0x180059e5c  lea     rcx, [rbp+var_10]
0x180059e60  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180059e66  lea     rax, [rbp+var_10]
0x180059e6a  mov     [rbp+arg_0], rax
0x180059e6e  lea     rcx, [rbp+var_10]
0x180059e72  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180059e78  nop
0x180059e79  mov     rdx, [rbp+var_20]; _Mtx_t
0x180059e7d  lea     rcx, [rdi+70h]; _Cnd_t
0x180059e81  call    cs:__imp__Cnd_wait
0x180059e87  jmp     loc_180059E03
0x180059e8c  xorps   xmm0, xmm0
0x180059e8f  movdqu  [rbp+var_10], xmm0
0x180059e94  mov     rdx, rbx
0x180059e97  lea     rcx, [rbp+var_10]
0x180059e9b  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180059ea1  lea     rax, [rbp+var_10]
0x180059ea5  mov     [rbp+arg_0], rax
0x180059ea9  lea     rcx, [rbp+var_10]
0x180059ead  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
