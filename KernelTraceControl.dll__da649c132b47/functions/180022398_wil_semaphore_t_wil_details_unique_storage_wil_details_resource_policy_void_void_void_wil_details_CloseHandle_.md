# wil::semaphore_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,0,std::nullptr_t>>,wil::err_returncode_policy>::create(long,long,ushort const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180022398`
- end: `0x18002243f`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024418`

## callees

- `0x1800201c4`
- `0x1800201dc`
- `0x180022398`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x1800223c2`
- `KERNEL32!CreateSemaphoreExW` at `0x1800223c2`
- `KERNEL32!SetLastError` at `0x1800223ef`
- `KERNEL32!SetLastError` at `0x1800223ef`
- `KERNEL32!GetLastError` at `0x1800223d8`
- `KERNEL32!GetLastError` at `0x1800223d8`
- `KERNEL32!CloseHandle` at `0x1800223e3`
- `KERNEL32!CloseHandle` at `0x1800223e3`

## pseudocode

```c
__int64 __fastcall wil::semaphore_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,0,std::nullptr_t>>,wil::err_returncode_policy>::create(
        void **a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  unsigned int v5; // ebx
  const char *v6; // r9
  HANDLE Semaphore; // r14
  void *v8; // rdi
  DWORD LastError; // ebp
  unsigned int v10; // r8d
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = 0;
  Semaphore = CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( Semaphore )
  {
    v8 = *a1;
    if ( *a1 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v8) )
      {
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x875, v10, v11);
        JUMPOUT(0x18002243ELL);
      }
      SetLastError(LastError);
    }
    *a1 = Semaphore;
  }
  else
  {
    return (unsigned int)wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0x15B0,
                           (unsigned int)"internal\\sdk\\inc\\wil\\resultmacros.h",
                           v6);
  }
  return v5;
}

```

## disassembly

```asm
0x180022398  mov     rax, rsp
0x18002239b  mov     [rax+8], rbx
0x18002239f  mov     [rax+10h], rbp
0x1800223a3  mov     [rax+18h], rsi
0x1800223a7  mov     [rax+20h], rdi
0x1800223ab  push    r14
0x1800223ad  sub     rsp, 30h
0x1800223b1  mov     rsi, rcx
0x1800223b4  mov     dword ptr [rax-10h], 1F0003h
0x1800223bb  xor     ebx, ebx
0x1800223bd  xor     ecx, ecx; lpSemaphoreAttributes
0x1800223bf  mov     [rax-18h], ebx
0x1800223c2  call    cs:__imp_CreateSemaphoreExW
0x1800223c8  mov     r14, rax
0x1800223cb  test    rax, rax
0x1800223ce  jz      short loc_1800223FA
0x1800223d0  mov     rdi, [rsi]
0x1800223d3  test    rdi, rdi
0x1800223d6  jz      short loc_1800223F5
0x1800223d8  call    cs:__imp_GetLastError
0x1800223de  mov     rcx, rdi; hObject
0x1800223e1  mov     ebp, eax
0x1800223e3  call    cs:__imp_CloseHandle
0x1800223e9  test    eax, eax
0x1800223eb  jz      short loc_18002242F
0x1800223ed  mov     ecx, ebp; dwErrCode
0x1800223ef  call    cs:__imp_SetLastError
0x1800223f5  mov     [rsi], r14
0x1800223f8  jmp     short loc_180022412
0x1800223fa  mov     rcx, [rsp+38h]; this
0x1800223ff  lea     r8, aInternalSdkInc_0; "internal\\sdk\\inc\\wil\\resultmacros.h"
0x180022406  mov     edx, 15B0h; void *
0x18002240b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180022410  mov     ebx, eax
0x180022412  mov     rbp, [rsp+38h+arg_8]
0x180022417  mov     eax, ebx
0x180022419  mov     rbx, [rsp+38h+arg_0]
0x18002241e  mov     rsi, [rsp+38h+arg_10]
0x180022423  mov     rdi, [rsp+38h+arg_18]
0x180022428  add     rsp, 30h
0x18002242c  pop     r14
0x18002242e  retn
0x18002242f  mov     rcx, [rsp+38h]; this
0x180022434  mov     edx, 875h; void *
0x180022439  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
