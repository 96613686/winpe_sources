# mutex_extensions::shared_recursive_mutex::lock_shared(void)

- ea: `0x14007a970`
- end: `0x14007ab16`
- name: `?lock_shared@shared_recursive_mutex@mutex_extensions@@QEAAXXZ`
- size: `422`
- prototype: `void __fastcall(_Mtx_t this)`
- caller_count: `66`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x14007d4b4`
- `0x140082030`
- `0x14008371c`
- `0x14008424c`
- `0x140089128`
- `0x140089474`
- `0x14008980c`
- `0x140089b24`
- `0x14008a974`
- `0x14008c060`
- `0x14008d440`
- `0x14008d974`
- `0x14008f540`
- `0x140091b28`
- `0x140093cdc`
- `0x1400973d8`
- `0x140097870`
- `0x140099860`
- `0x140099fa4`
- `0x14009b0f0`
- `0x14009baa0`
- `0x14009ccc8`
- `0x14009dc3c`
- `0x14009ebbc`
- `0x1401b0f34`
- `0x1401ba1b4`
- `0x1401ba5dc`
- `0x1401baa04`
- `0x1401bad50`
- `0x1401bb244`
- `0x1401bb548`
- `0x1401bb8e4`
- `0x1401bba8c`
- `0x1401bbc34`
- `0x1401bbe30`
- `0x1401bd7a4`
- `0x1401bdab4`
- `0x1401bdd70`
- `0x1401be5b8`
- `0x1401bebc4`
- `0x1401bf1ac`
- `0x1401bf604`
- `0x1401bf740`
- `0x1401bf8d0`
- `0x1401bfb44`
- `0x1401bfe10`
- `0x1401c05d8`
- `0x1401c1a28`
- `0x1401c29e0`
- `0x1401c2ce4`

## callees

- `0x140041df8`
- `0x1400421f8`
- `0x140045160`
- `0x14004519c`
- `0x14005745c`
- `0x14007a970`
- `0x1401a2e3c`
- `0x1401a2e84`
- `0x1401a2fd0`
- `0x140379070`
- `0x14037b4b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007a9d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007a9f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007aa18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007a9d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007a9f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007aa18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007aa75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007aa75`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14007aa7f`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14007aa7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall mutex_extensions::shared_recursive_mutex::lock_shared(char *this)
{
  DWORD CurrentThreadId; // ebp
  __int64 v3; // rsi
  __int64 v4; // rax
  __int64 *v5; // rcx
  const struct std::error_category *v7; // rax
  __int128 v8; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v9[16]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+40h] [rbp-48h] BYREF
  __int128 v11; // [rsp+68h] [rbp-20h]

  v11 = 0;
  *(_QWORD *)&v11 = this;
  BYTE8(v11) = 0;
  if ( (unsigned int)mtx_do_lock(this, 0) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)this + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  BYTE8(v11) = 1;
  while ( *((_DWORD *)this + 44) )
  {
    if ( *((_DWORD *)this + 45) == GetCurrentThreadId() )
    {
      if ( *((_DWORD *)this + 44) && *((_DWORD *)this + 45) != GetCurrentThreadId() )
      {
        v7 = std::system_category();
        v8 = *(_OWORD *)std::error_code::error_code((std::error_code *)v9, 5023, v7);
        std::system_error::system_error(pExceptionObject, &v8);
        throw (std::system_error *)pExceptionObject;
      }
      break;
    }
    Cnd_wait((_Cnd_t)(this + 80), (_Mtx_t)this);
  }
  ++*((_DWORD *)this + 38);
  CurrentThreadId = GetCurrentThreadId();
  v3 = *((_QWORD *)this + 20);
  if ( *((_QWORD *)this + 21) == 0xAAAAAAAAAAAAAAALL )
    std::_Xlength_error("list too long");
  v8 = (unsigned __int64)(this + 160);
  v4 = std::_Allocate<16,std::_Default_allocate_traits>(24);
  *(_DWORD *)(v4 + 16) = CurrentThreadId;
  ++*((_QWORD *)this + 21);
  v5 = *(__int64 **)(v3 + 8);
  *(_QWORD *)v4 = v3;
  *(_QWORD *)(v4 + 8) = v5;
  *(_QWORD *)(v3 + 8) = v4;
  *v5 = v4;
  if ( (*((_DWORD *)this + 19))-- == 1 )
  {
    *((_DWORD *)this + 18) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 2);
  }
  WakeAllConditionVariable((PCONDITION_VARIABLE)this + 11);
}

```

## disassembly

```asm
0x14007a970  mov     r11, rsp
0x14007a973  mov     [r11+10h], rbx
0x14007a977  mov     [r11+18h], rbp
0x14007a97b  mov     [r11+20h], rsi
0x14007a97f  push    rdi
0x14007a980  sub     rsp, 80h
0x14007a987  mov     rax, cs:__security_cookie
0x14007a98e  xor     rax, rsp
0x14007a991  mov     [rsp+88h+var_10], rax
0x14007a996  mov     rbx, rcx
0x14007a999  xorps   xmm0, xmm0
0x14007a99c  movups  [rsp+88h+var_20], xmm0
0x14007a9a1  mov     [r11-20h], rcx
0x14007a9a5  mov     byte ptr [rsp+88h+var_20+8], 0
0x14007a9aa  xor     edx, edx
0x14007a9ac  call    mtx_do_lock
0x14007a9b1  test    eax, eax
0x14007a9b3  jnz     loc_14007AAB8
0x14007a9b9  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x14007a9c0  jz      loc_14007AAC3
0x14007a9c6  mov     byte ptr [rsp+88h+var_20+8], 1
0x14007a9cb  cmp     dword ptr [rbx+0B0h], 0
0x14007a9d2  jz      short loc_14007AA0B
0x14007a9d4  call    cs:__imp_GetCurrentThreadId
0x14007a9da  cmp     [rbx+0B4h], eax
0x14007a9e0  jz      short loc_14007A9F0
0x14007a9e2  mov     rdx, rbx; _Mtx_t
0x14007a9e5  lea     rcx, [rbx+50h]; _Cnd_t
0x14007a9e9  call    _Cnd_wait
0x14007a9ee  jmp     short loc_14007A9CB
0x14007a9f0  cmp     dword ptr [rbx+0B0h], 0
0x14007a9f7  jz      short loc_14007AA0B
0x14007a9f9  call    cs:__imp_GetCurrentThreadId
0x14007a9ff  cmp     [rbx+0B4h], eax
0x14007aa05  jnz     loc_14007AAD5
0x14007aa0b  inc     dword ptr [rbx+98h]
0x14007aa11  lea     rdi, [rbx+0A0h]
0x14007aa18  call    cs:__imp_GetCurrentThreadId
0x14007aa1e  mov     ebp, eax
0x14007aa20  mov     rsi, [rdi]
0x14007aa23  mov     rax, 0AAAAAAAAAAAAAAAh
0x14007aa2d  cmp     [rdi+8], rax
0x14007aa31  jz      short loc_14007AAAB
0x14007aa33  mov     qword ptr [rsp+88h+var_68], rdi
0x14007aa38  mov     qword ptr [rsp+88h+var_68+8], 0
0x14007aa41  mov     ecx, 18h
0x14007aa46  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14007aa4b  mov     [rax+10h], ebp
0x14007aa4e  inc     qword ptr [rdi+8]
0x14007aa52  mov     rcx, [rsi+8]
0x14007aa56  mov     [rax], rsi
0x14007aa59  mov     [rax+8], rcx
0x14007aa5d  mov     [rsi+8], rax
0x14007aa61  mov     [rcx], rax
0x14007aa64  sub     dword ptr [rbx+4Ch], 1
0x14007aa68  jnz     short loc_14007AA7B
0x14007aa6a  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x14007aa71  lea     rcx, [rbx+10h]; SRWLock
0x14007aa75  call    cs:__imp_ReleaseSRWLockExclusive
0x14007aa7b  lea     rcx, [rbx+58h]; ConditionVariable
0x14007aa7f  call    cs:__imp_WakeAllConditionVariable
0x14007aa85  mov     rcx, [rsp+88h+var_10]
0x14007aa8a  xor     rcx, rsp; StackCookie
0x14007aa8d  call    __security_check_cookie
0x14007aa92  lea     r11, [rsp+88h+var_8]
0x14007aa9a  mov     rbx, [r11+18h]
0x14007aa9e  mov     rbp, [r11+20h]
0x14007aaa2  mov     rsi, [r11+28h]
0x14007aaa6  mov     rsp, r11
0x14007aaa9  pop     rdi
0x14007aaaa  retn
0x14007aaab  lea     rcx, aListTooLong; "list too long"
0x14007aab2  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x14007aab8  mov     ecx, 5; int
0x14007aabd  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14007aac3  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x14007aaca  mov     ecx, 6; int
0x14007aacf  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14007aad5  call    ?system_category@std@@YAAEBVerror_category@1@XZ; std::system_category(void)
0x14007aada  mov     r8, rax; struct std::error_category *
0x14007aadd  mov     edx, 139Fh; int
0x14007aae2  lea     rcx, [rsp+88h+var_58]; this
0x14007aae7  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x14007aaec  movups  xmm0, xmmword ptr [rax]
0x14007aaef  movdqu  [rsp+88h+var_68], xmm0
0x14007aaf5  lea     rdx, [rsp+88h+var_68]
0x14007aafa  lea     rcx, [rsp+88h+pExceptionObject]
0x14007aaff  call    ??0system_error@std@@QEAA@Verror_code@1@@Z; std::system_error::system_error(std::error_code)
0x14007ab04  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x14007ab0b  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x14007ab10  call    _CxxThrowException
```
