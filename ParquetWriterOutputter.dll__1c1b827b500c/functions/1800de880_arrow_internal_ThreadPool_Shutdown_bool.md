# arrow::internal::ThreadPool::Shutdown(bool)

- ea: `0x1800de880`
- end: `0x1800dea23`
- name: `?Shutdown@ThreadPool@internal@arrow@@QEAA?AVStatus@3@_N@Z`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x1800dd790`

## callees

- `0x180086ed0`
- `0x18009a010`
- `0x1800dd910`
- `0x1800de880`
- `0x1800df330`
- `0x180307e68`
- `0x180307e8c`
- `0x180307f98`
- `0x18030a0a0`
- `0x18030a154`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x1800de8e5`: `Shutdown() already called`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall arrow::internal::ThreadPool::Shutdown(arrow::internal::ThreadPool *a1, __int64 a2, char a3)
{
  struct _Mtx_internal_imp_t *v6; // rdi
  int v7; // eax
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  _BYTE *v12; // rcx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  struct _Cnd_internal_imp_t *i; // rbp
  int v17; // eax
  int v18; // eax
  _BYTE *v20; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int64 v21; // [rsp+50h] [rbp-28h]

  v6 = (struct _Mtx_internal_imp_t *)*((_QWORD *)a1 + 3);
  v7 = Mtx_lock(v6);
  if ( v7 )
    std::_Throw_C_error(v7);
  v8 = *((_QWORD *)a1 + 3);
  if ( *(_BYTE *)(v8 + 308) )
  {
    v9 = arrow::util::StringBuilder<char const (&)[13]>(&v20, "Shutdown() already called");
    LOBYTE(v10) = 4;
    arrow::Status::Status(a2, v10, v9);
    if ( v21 >= 0x10 )
    {
      v11 = v21 + 1;
      v12 = v20;
      if ( v21 + 1 >= 0x1000 )
      {
        v11 = v21 + 40;
        v12 = (_BYTE *)*((_QWORD *)v20 - 1);
        if ( (unsigned __int64)(v20 - v12 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v12, v11);
    }
    v13 = Mtx_unlock(v6);
    if ( v13 )
      std::_Throw_C_error(v13);
  }
  else
  {
    *(_BYTE *)(v8 + 308) = 1;
    *(_BYTE *)(*((_QWORD *)a1 + 3) + 309LL) = a3 ^ 1;
    v14 = Cnd_broadcast((_Cnd_t)(*((_QWORD *)a1 + 3) + 80LL));
    if ( v14 )
      std::_Throw_C_error(v14);
    v15 = *((_QWORD *)a1 + 3);
    for ( i = (struct _Cnd_internal_imp_t *)(v15 + 152); *(_QWORD *)(v15 + 232); v15 = *((_QWORD *)a1 + 3) )
    {
      v17 = Cnd_wait(i, v6);
      if ( v17 )
        std::_Throw_C_error(v17);
    }
    if ( *(_BYTE *)(v15 + 309) )
      std::deque<std::function<void (void)>>::_Tidy(v15 + 264);
    arrow::internal::ThreadPool::CollectFinishedWorkersUnlocked(a1);
    *(_QWORD *)(a2 + 8) = 0;
    v18 = Mtx_unlock(v6);
    if ( v18 )
      std::_Throw_C_error(v18);
  }
  return a2;
}

```

## disassembly

```asm
0x1800de880  push    rbp
0x1800de882  push    rsi
0x1800de883  push    rdi
0x1800de884  sub     rsp, 60h
0x1800de888  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x1800de891  mov     [rsp+78h+arg_10], rbx
0x1800de899  mov     rax, cs:__security_cookie
0x1800de8a0  xor     rax, rsp
0x1800de8a3  mov     [rsp+78h+var_20], rax
0x1800de8a8  movzx   ebp, r8b
0x1800de8ac  mov     rsi, rdx
0x1800de8af  mov     rbx, rcx
0x1800de8b2  mov     [rsp+78h+var_58], rdx
0x1800de8b7  mov     rdi, [rcx+18h]
0x1800de8bb  mov     [rsp+78h+var_58], rdi
0x1800de8c0  mov     rcx, rdi; _Mtx_t
0x1800de8c3  call    _Mtx_lock
0x1800de8c8  test    eax, eax
0x1800de8ca  jz      short loc_1800DE8D3
0x1800de8cc  mov     ecx, eax; int
0x1800de8ce  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x1800de8d3  mov     [rsp+78h+var_50], 1
0x1800de8d8  mov     rax, [rbx+18h]
0x1800de8dc  cmp     byte ptr [rax+134h], 0
0x1800de8e3  jz      short loc_1800DE95C
0x1800de8e5  lea     rdx, aShutdownAlread; "Shutdown() already called"
0x1800de8ec  lea     rcx, [rsp+78h+var_40]
0x1800de8f1  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1800de8f6  nop
0x1800de8f7  mov     r8, rax
0x1800de8fa  mov     dl, 4
0x1800de8fc  mov     rcx, rsi
0x1800de8ff  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800de904  nop
0x1800de905  mov     rdx, [rsp+78h+var_28]
0x1800de90a  cmp     rdx, 10h
0x1800de90e  jb      short loc_1800DE943
0x1800de910  inc     rdx
0x1800de913  mov     rcx, [rsp+78h+var_40]
0x1800de918  mov     rax, rcx
0x1800de91b  cmp     rdx, 1000h
0x1800de922  jb      short loc_1800DE93D
0x1800de924  add     rdx, 27h ; '''; unsigned __int64
0x1800de928  mov     rcx, [rcx-8]; void *
0x1800de92c  sub     rax, rcx
0x1800de92f  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800de933  cmp     rax, 1Fh
0x1800de937  ja      loc_1800DEA1D
0x1800de93d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800de942  nop
0x1800de943  mov     rcx, rdi; _Mtx_t
0x1800de946  call    _Mtx_unlock
0x1800de94b  test    eax, eax
0x1800de94d  jz      short loc_1800DE957
0x1800de94f  mov     ecx, eax; int
0x1800de951  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x1800de956  nop
0x1800de957  jmp     loc_1800DE9FD
0x1800de95c  mov     byte ptr [rax+134h], 1
0x1800de963  xor     bpl, 1
0x1800de967  mov     rax, [rbx+18h]
0x1800de96b  mov     [rax+135h], bpl
0x1800de972  mov     rcx, [rbx+18h]
0x1800de976  add     rcx, 50h ; 'P'; _Cnd_t
0x1800de97a  call    _Cnd_broadcast
0x1800de97f  test    eax, eax
0x1800de981  jz      short loc_1800DE98B
0x1800de983  mov     ecx, eax; int
0x1800de985  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x1800de98a  nop
0x1800de98b  mov     rcx, [rbx+18h]
0x1800de98f  lea     rbp, [rcx+98h]
0x1800de996  cmp     qword ptr [rcx+0E8h], 0
0x1800de99e  jz      short loc_1800DE9C4
0x1800de9a0  mov     rdx, rdi; _Mtx_t
0x1800de9a3  mov     rcx, rbp; _Cnd_t
0x1800de9a6  call    _Cnd_wait
0x1800de9ab  test    eax, eax
0x1800de9ad  jz      short loc_1800DE9B6
0x1800de9af  mov     ecx, eax; int
0x1800de9b1  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x1800de9b6  mov     rcx, [rbx+18h]
0x1800de9ba  cmp     qword ptr [rcx+0E8h], 0
0x1800de9c2  jnz     short loc_1800DE9A0
0x1800de9c4  cmp     byte ptr [rcx+135h], 0
0x1800de9cb  jz      short loc_1800DE9D9
0x1800de9cd  add     rcx, 108h
0x1800de9d4  call    ?_Tidy@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@IEAAXXZ; std::deque<std::function<void (void)>>::_Tidy(void)
0x1800de9d9  mov     rcx, rbx; this
0x1800de9dc  call    ?CollectFinishedWorkersUnlocked@ThreadPool@internal@arrow@@IEAAXXZ; arrow::internal::ThreadPool::CollectFinishedWorkersUnlocked(void)
0x1800de9e1  mov     qword ptr [rsi+8], 0
0x1800de9e9  mov     rcx, rdi; _Mtx_t
0x1800de9ec  call    _Mtx_unlock
0x1800de9f1  test    eax, eax
0x1800de9f3  jz      short loc_1800DE9FD
0x1800de9f5  mov     ecx, eax; int
0x1800de9f7  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x1800de9fc  nop
0x1800de9fd  mov     rax, rsi
0x1800dea00  mov     rcx, [rsp+78h+var_20]
0x1800dea05  xor     rcx, rsp; StackCookie
0x1800dea08  call    __security_check_cookie
0x1800dea0d  mov     rbx, [rsp+78h+arg_10]
0x1800dea15  add     rsp, 60h
0x1800dea19  pop     rdi
0x1800dea1a  pop     rsi
0x1800dea1b  pop     rbp
0x1800dea1c  retn
0x1800dea1d  call    _invalid_parameter_noinfo_noreturn
```
