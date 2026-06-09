# RateLimiter::New(wistd::unique_ptr<RateLimiterStrategy,wistd::default_delete<RateLimiterStrategy>>)

- ea: `0x1800199e4`
- end: `0x180019b6c`
- name: `?New@RateLimiter@@SA?AV?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@V?$unique_ptr@VRateLimiterStrategy@@U?$default_delete@VRateLimiterStrategy@@@wistd@@@3@@Z`
- size: `392`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800443a4`

## callees

- `0x1800199e4`
- `0x18001a1ac`
- `0x18001c8f4`
- `0x18001ca30`
- `0x18001ef98`
- `0x180028838`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180019aa3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180019aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ab1`

## pseudocode

```c
_QWORD *__fastcall RateLimiter::New(_QWORD *a1, __int64 *a2)
{
  _QWORD *v4; // rbx
  __int64 *v5; // rax
  void (__fastcall ****v6)(_QWORD, __int64); // r8
  void (__fastcall ***v7)(_QWORD, __int64); // rcx
  HANDLE Mutex; // rbp
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  void (__fastcall ***v11)(_QWORD, __int64); // rcx
  _QWORD *v13; // [rsp+48h] [rbp+10h] BYREF

  if ( *a2 )
  {
    v4 = operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
    if ( v4 )
    {
      v5 = (__int64 *)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                        &v13,
                        a2);
      wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v4, v5);
      v4[1] = 0;
      v7 = *v6;
      *v6 = 0;
      if ( v7 )
        (**v7)(v7, 1);
      v13 = v4;
      Mutex = CreateMutexExW(0, 0, 0, 0x1F0001u);
      if ( Mutex )
      {
        GetLastError();
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
          v4 + 1,
          Mutex);
        if ( v4[1] )
        {
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
            a1,
            (__int64 *)&v13);
LABEL_20:
          wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(&v13, 0);
          goto LABEL_21;
        }
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_19:
        *a1 = 0;
        goto LABEL_20;
      }
      v10 = 20;
    }
    else
    {
      v13 = 0;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      v10 = 19;
    }
    WPP_SF_(v9[2], v10, WPP_93abf9d0a22735fdb0b3a31cca08f13b_Traceguids);
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_93abf9d0a22735fdb0b3a31cca08f13b_Traceguids);
  *a1 = 0;
LABEL_21:
  v11 = (void (__fastcall ***)(_QWORD, __int64))*a2;
  *a2 = 0;
  if ( v11 )
    (**v11)(v11, 1);
  return a1;
}

```

## disassembly

```asm
0x1800199e4  mov     [rsp+arg_0], rbx
0x1800199e9  mov     [rsp+arg_10], rbp
0x1800199ee  push    rdi
0x1800199ef  push    r14
0x1800199f1  push    r15
0x1800199f3  sub     rsp, 20h
0x1800199f7  xor     r15d, r15d
0x1800199fa  mov     rdi, rdx
0x1800199fd  mov     r14, rcx
0x180019a00  cmp     [rdx], r15
0x180019a03  jnz     short loc_180019A3A
0x180019a05  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a0c  lea     rax, WPP_GLOBAL_Control
0x180019a13  cmp     rcx, rax
0x180019a16  jz      short loc_180019A32
0x180019a18  test    byte ptr [rcx+1Ch], 1
0x180019a1c  jz      short loc_180019A32
0x180019a1e  mov     rcx, [rcx+10h]
0x180019a22  lea     edx, [r15+12h]
0x180019a26  lea     r8, WPP_93abf9d0a22735fdb0b3a31cca08f13b_Traceguids
0x180019a2d  call    WPP_SF_
0x180019a32  mov     [r14], r15
0x180019a35  jmp     loc_180019B3A
0x180019a3a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019a41  mov     ecx, 10h; unsigned __int64
0x180019a46  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180019a4b  mov     rbx, rax
0x180019a4e  test    rax, rax
0x180019a51  jz      loc_180019AF8
0x180019a57  mov     rdx, rdi
0x180019a5a  lea     rcx, [rsp+38h+arg_8]
0x180019a5f  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x180019a64  mov     rdx, rax
0x180019a67  mov     rcx, rbx
0x180019a6a  mov     r8, rax
0x180019a6d  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x180019a72  mov     [rbx+8], r15
0x180019a76  mov     rcx, [r8]
0x180019a79  mov     [r8], r15
0x180019a7c  test    rcx, rcx
0x180019a7f  jz      short loc_180019A91
0x180019a81  mov     rax, [rcx]
0x180019a84  mov     edx, 1
0x180019a89  mov     rax, [rax]
0x180019a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a91  mov     r9d, 1F0001h; dwDesiredAccess
0x180019a97  mov     [rsp+38h+arg_8], rbx
0x180019a9c  xor     r8d, r8d; dwFlags
0x180019a9f  xor     edx, edx; lpName
0x180019aa1  xor     ecx, ecx; lpMutexAttributes
0x180019aa3  call    cs:__imp_CreateMutexExW
0x180019aa9  mov     rbp, rax
0x180019aac  test    rax, rax
0x180019aaf  jz      short loc_180019AD8
0x180019ab1  call    cs:__imp_GetLastError
0x180019ab7  mov     rdx, rbp
0x180019aba  lea     rcx, [rbx+8]
0x180019abe  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180019ac3  cmp     [rbx+8], r15
0x180019ac7  jz      short loc_180019AD8
0x180019ac9  lea     rdx, [rsp+38h+arg_8]
0x180019ace  mov     rcx, r14
0x180019ad1  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x180019ad6  jmp     short loc_180019B2E
0x180019ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x180019adf  lea     rax, WPP_GLOBAL_Control
0x180019ae6  cmp     rcx, rax
0x180019ae9  jz      short loc_180019B2B
0x180019aeb  test    byte ptr [rcx+1Ch], 1
0x180019aef  jz      short loc_180019B2B
0x180019af1  mov     edx, 14h
0x180019af6  jmp     short loc_180019B1B
0x180019af8  mov     [rsp+38h+arg_8], r15
0x180019afd  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b04  lea     rax, WPP_GLOBAL_Control
0x180019b0b  cmp     rcx, rax
0x180019b0e  jz      short loc_180019B2B
0x180019b10  test    byte ptr [rcx+1Ch], 1
0x180019b14  jz      short loc_180019B2B
0x180019b16  mov     edx, 13h
0x180019b1b  mov     rcx, [rcx+10h]
0x180019b1f  lea     r8, WPP_93abf9d0a22735fdb0b3a31cca08f13b_Traceguids
0x180019b26  call    WPP_SF_
0x180019b2b  mov     [r14], r15
0x180019b2e  xor     edx, edx
0x180019b30  lea     rcx, [rsp+38h+arg_8]
0x180019b35  call    ?reset@?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@QEAAXPEAVRateLimiter@@@Z; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(RateLimiter *)
0x180019b3a  mov     rcx, [rdi]
0x180019b3d  mov     [rdi], r15
0x180019b40  test    rcx, rcx
0x180019b43  jz      short loc_180019B55
0x180019b45  mov     rax, [rcx]
0x180019b48  mov     edx, 1
0x180019b4d  mov     rax, [rax]
0x180019b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b55  mov     rbx, [rsp+38h+arg_0]
0x180019b5a  mov     rax, r14
0x180019b5d  mov     rbp, [rsp+38h+arg_10]
0x180019b62  add     rsp, 20h
0x180019b66  pop     r15
0x180019b68  pop     r14
0x180019b6a  pop     rdi
0x180019b6b  retn
```
