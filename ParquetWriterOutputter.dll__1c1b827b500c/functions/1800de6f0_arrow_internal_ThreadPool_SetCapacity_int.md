# arrow::internal::ThreadPool::SetCapacity(int)

- ea: `0x1800de6f0`
- end: `0x1800de87a`
- name: `?SetCapacity@ThreadPool@internal@arrow@@QEAA?AVStatus@3@H@Z`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800ddea0`

## callees

- `0x180086ed0`
- `0x1800997f0`
- `0x18009a010`
- `0x1800dd910`
- `0x1800ddbb0`
- `0x1800de6f0`
- `0x180307e68`
- `0x180307e8c`
- `0x180307f98`
- `0x18030a0a0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x1800de754`: `operation forbidden during or after shutdown`
- `0x1800de781`: `ThreadPool capacity must be > 0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall arrow::internal::ThreadPool::SetCapacity(arrow::internal::ThreadPool *a1, __int64 a2, int a3)
{
  struct _Mtx_internal_imp_t *v6; // rbp
  int v7; // eax
  int v8; // eax
  __int64 v9; // r8
  __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  _BYTE *v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  int v15; // edi
  int v16; // eax
  int v17; // eax
  _BYTE *v19; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int64 v20; // [rsp+50h] [rbp-28h]

  v6 = (struct _Mtx_internal_imp_t *)*((_QWORD *)a1 + 3);
  v7 = Mtx_lock(v6);
  if ( v7 )
    std::_Throw_C_error(v7);
  if ( *(_BYTE *)(*((_QWORD *)a1 + 3) + 308LL) )
  {
    arrow::Status::Invalid<char const (&)[65]>(a2, "operation forbidden during or after shutdown");
    v8 = Mtx_unlock(v6);
    if ( v8 )
      std::_Throw_C_error(v8);
  }
  else if ( a3 > 0 )
  {
    arrow::internal::ThreadPool::CollectFinishedWorkersUnlocked(a1);
    *(_DWORD *)(*((_QWORD *)a1 + 3) + 304LL) = a3;
    v14 = *((_QWORD *)a1 + 3);
    v15 = a3 - *(_DWORD *)(v14 + 232);
    if ( v15 <= 0 )
    {
      if ( v15 < 0 )
      {
        v16 = Cnd_broadcast((_Cnd_t)(v14 + 80));
        if ( v16 )
          std::_Throw_C_error(v16);
      }
    }
    else
    {
      arrow::internal::ThreadPool::LaunchWorkersUnlocked(a1, v15);
    }
    *(_QWORD *)(a2 + 8) = 0;
    v17 = Mtx_unlock(v6);
    if ( v17 )
      std::_Throw_C_error(v17);
  }
  else
  {
    v9 = arrow::util::StringBuilder<char const (&)[13]>(&v19, "ThreadPool capacity must be > 0");
    LOBYTE(v10) = 4;
    arrow::Status::Status(a2, v10, v9);
    if ( v20 >= 0x10 )
    {
      v11 = v20 + 1;
      v12 = v19;
      if ( v20 + 1 >= 0x1000 )
      {
        v11 = v20 + 40;
        v12 = (_BYTE *)*((_QWORD *)v19 - 1);
        if ( (unsigned __int64)(v19 - v12 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v12, v11);
    }
    v13 = Mtx_unlock(v6);
    if ( v13 )
      std::_Throw_C_error(v13);
  }
  return a2;
}

```

## disassembly

```asm
0x1800de6f0  push    rbp
0x1800de6f2  push    rsi
0x1800de6f3  push    rdi
0x1800de6f4  sub     rsp, 60h
0x1800de6f8  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x1800de701  mov     [rsp+78h+arg_10], rbx
0x1800de709  mov     rax, cs:__security_cookie
0x1800de710  xor     rax, rsp
0x1800de713  mov     [rsp+78h+var_20], rax
0x1800de718  mov     edi, r8d
0x1800de71b  mov     rbx, rdx
0x1800de71e  mov     rsi, rcx
0x1800de721  mov     [rsp+78h+var_58], rdx
0x1800de726  mov     rbp, [rcx+18h]
0x1800de72a  mov     [rsp+78h+var_58], rbp
0x1800de72f  mov     rcx, rbp; _Mtx_t
0x1800de732  call    _Mtx_lock
0x1800de737  test    eax, eax
0x1800de739  jz      short loc_1800DE742
0x1800de73b  mov     ecx, eax; int
0x1800de73d  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x1800de742  mov     [rsp+78h+var_50], 1
0x1800de747  mov     rax, [rsi+18h]
0x1800de74b  cmp     byte ptr [rax+134h], 0
0x1800de752  jz      short loc_1800DE77D
0x1800de754  lea     rdx, aOperationForbi_0; "operation forbidden during or after shu"...
0x1800de75b  mov     rcx, rbx
0x1800de75e  call    ??$Invalid@AEAY0EB@$$CBD@Status@arrow@@SA?AV01@AEAY0EB@$$CBD@Z; arrow::Status::Invalid<char const (&)[65]>(char const (&)[65])
0x1800de763  nop
0x1800de764  mov     rcx, rbp; _Mtx_t
0x1800de767  call    _Mtx_unlock
0x1800de76c  test    eax, eax
0x1800de76e  jz      short loc_1800DE778
0x1800de770  mov     ecx, eax; int
0x1800de772  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x1800de777  nop
0x1800de778  jmp     loc_1800DE854
0x1800de77d  test    edi, edi
0x1800de77f  jg      short loc_1800DE7F5
0x1800de781  lea     rdx, aThreadpoolCapa; "ThreadPool capacity must be > 0"
0x1800de788  lea     rcx, [rsp+78h+var_40]
0x1800de78d  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1800de792  nop
0x1800de793  mov     r8, rax
0x1800de796  mov     dl, 4
0x1800de798  mov     rcx, rbx
0x1800de79b  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800de7a0  nop
0x1800de7a1  mov     rdx, [rsp+78h+var_28]
0x1800de7a6  cmp     rdx, 10h
0x1800de7aa  jb      short loc_1800DE7DF
0x1800de7ac  inc     rdx
0x1800de7af  mov     rcx, [rsp+78h+var_40]
0x1800de7b4  mov     rax, rcx
0x1800de7b7  cmp     rdx, 1000h
0x1800de7be  jb      short loc_1800DE7D9
0x1800de7c0  add     rdx, 27h ; '''; unsigned __int64
0x1800de7c4  mov     rcx, [rcx-8]; void *
0x1800de7c8  sub     rax, rcx
0x1800de7cb  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800de7cf  cmp     rax, 1Fh
0x1800de7d3  ja      loc_1800DE874
0x1800de7d9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800de7de  nop
0x1800de7df  mov     rcx, rbp; _Mtx_t
0x1800de7e2  call    _Mtx_unlock
0x1800de7e7  test    eax, eax
0x1800de7e9  jz      short loc_1800DE7F3
0x1800de7eb  mov     ecx, eax; int
0x1800de7ed  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x1800de7f2  nop
0x1800de7f3  jmp     short loc_1800DE854
0x1800de7f5  mov     rcx, rsi; this
0x1800de7f8  call    ?CollectFinishedWorkersUnlocked@ThreadPool@internal@arrow@@IEAAXXZ; arrow::internal::ThreadPool::CollectFinishedWorkersUnlocked(void)
0x1800de7fd  mov     rax, [rsi+18h]
0x1800de801  mov     [rax+130h], edi
0x1800de807  mov     rcx, [rsi+18h]
0x1800de80b  sub     edi, [rcx+0E8h]
0x1800de811  test    edi, edi
0x1800de813  jle     short loc_1800DE821
0x1800de815  mov     edx, edi; int
0x1800de817  mov     rcx, rsi; this
0x1800de81a  call    ?LaunchWorkersUnlocked@ThreadPool@internal@arrow@@IEAAXH@Z; arrow::internal::ThreadPool::LaunchWorkersUnlocked(int)
0x1800de81f  jmp     short loc_1800DE838
0x1800de821  jns     short loc_1800DE838
0x1800de823  add     rcx, 50h ; 'P'; _Cnd_t
0x1800de827  call    _Cnd_broadcast
0x1800de82c  test    eax, eax
0x1800de82e  jz      short loc_1800DE838
0x1800de830  mov     ecx, eax; int
0x1800de832  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x1800de837  nop
0x1800de838  mov     qword ptr [rbx+8], 0
0x1800de840  mov     rcx, rbp; _Mtx_t
0x1800de843  call    _Mtx_unlock
0x1800de848  test    eax, eax
0x1800de84a  jz      short loc_1800DE854
0x1800de84c  mov     ecx, eax; int
0x1800de84e  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x1800de853  nop
0x1800de854  mov     rax, rbx
0x1800de857  mov     rcx, [rsp+78h+var_20]
0x1800de85c  xor     rcx, rsp; StackCookie
0x1800de85f  call    __security_check_cookie
0x1800de864  mov     rbx, [rsp+78h+arg_10]
0x1800de86c  add     rsp, 60h
0x1800de870  pop     rdi
0x1800de871  pop     rsi
0x1800de872  pop     rbp
0x1800de873  retn
0x1800de874  call    _invalid_parameter_noinfo_noreturn
```
