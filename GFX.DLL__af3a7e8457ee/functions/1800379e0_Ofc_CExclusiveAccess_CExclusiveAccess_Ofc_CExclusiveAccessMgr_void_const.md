# Ofc::CExclusiveAccess::CExclusiveAccess(Ofc::CExclusiveAccessMgr &,void const *)

- ea: `0x1800379e0`
- end: `0x180037abd`
- name: `??0CExclusiveAccess@Ofc@@QEAA@AEAVCExclusiveAccessMgr@1@PEBX@Z`
- size: `221`
- prototype: `__int64 __fastcall(Ofc::CExclusiveAccess *__hidden this, struct Ofc::CExclusiveAccessMgr *, const void *)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d7d0`
- `0x18003746c`
- `0x180037998`
- `0x180052290`
- `0x1800995c0`
- `0x1800b7820`
- `0x180117560`
- `0x180138b80`
- `0x18013a6e0`
- `0x1801786b0`
- `0x1801b44c0`
- `0x1801b6730`

## callees

- `0x1800379e0`
- `0x1800795a0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180037a06`
- `KERNEL32!GetCurrentThreadId` at `0x180037a06`
- `KERNEL32!WaitForSingleObjectEx` at `0x180037a97`
- `KERNEL32!WaitForSingleObjectEx` at `0x180037a97`
- `KERNEL32!ResetEvent` at `0x180037a79`
- `KERNEL32!ResetEvent` at `0x180037a79`
- `MSVCP140!_Mtx_unlock` at `0x180037a39`
- `MSVCP140!_Mtx_unlock` at `0x180037a86`
- `MSVCP140!_Mtx_unlock` at `0x180037a39`
- `MSVCP140!_Mtx_unlock` at `0x180037a86`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180037ab4`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180037ab4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Ofc::CExclusiveAccess *__fastcall Ofc::CExclusiveAccess::CExclusiveAccess(
        Ofc::CExclusiveAccess *this,
        struct Ofc::CExclusiveAccessMgr *a2,
        const void *a3)
{
  __int64 i; // rbx
  __int64 j; // rsi

  *(_QWORD *)this = a2;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = a3;
  *((_DWORD *)this + 6) = GetCurrentThreadId();
  if ( *((_QWORD *)this + 2) )
  {
    for ( i = *(_QWORD *)this; ; _InterlockedDecrement((volatile signed __int32 *)(i + 96)) )
    {
      std::_Mutex_base::lock((std::_Mutex_base *)i);
      for ( j = *(_QWORD *)(i + 80); ; j = *(_QWORD *)(j + 8) )
      {
        if ( !j )
        {
          *((_QWORD *)this + 1) = *(_QWORD *)(i + 80);
          *(_QWORD *)(i + 80) = this;
          goto LABEL_6;
        }
        if ( i != *(_QWORD *)j || !*(_QWORD *)(j + 16) )
          MsoShipAssertTagProc(20513947);
        if ( *(_QWORD *)(j + 16) == *((_QWORD *)this + 2) )
          break;
      }
      if ( *(_DWORD *)(j + 24) == *((_DWORD *)this + 6) )
        break;
      ResetEvent(*(HANDLE *)(i + 88));
      _InterlockedIncrement((volatile signed __int32 *)(i + 96));
      _Mtx_unlock((_Mtx_t)i);
      WaitForSingleObjectEx(*(HANDLE *)(i + 88), 0x32u, 0);
    }
LABEL_6:
    _Mtx_unlock((_Mtx_t)i);
  }
  return this;
}

```

## disassembly

```asm
0x1800379e0  mov     [rsp+arg_0], rbx
0x1800379e5  mov     [rsp+arg_8], rbp
0x1800379ea  mov     [rsp+arg_10], rsi
0x1800379ef  push    rdi
0x1800379f0  sub     rsp, 20h
0x1800379f4  mov     rdi, rcx
0x1800379f7  mov     [rcx], rdx
0x1800379fa  mov     qword ptr [rcx+8], 0
0x180037a02  mov     [rcx+10h], r8
0x180037a06  call    cs:__imp_GetCurrentThreadId
0x180037a0c  mov     [rdi+18h], eax
0x180037a0f  cmp     qword ptr [rdi+10h], 0
0x180037a14  jz      short loc_180037A3F
0x180037a16  mov     rbx, [rdi]
0x180037a19  mov     rcx, rbx; this
0x180037a1c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180037a21  mov     rsi, [rbx+50h]
0x180037a25  test    rsi, rsi
0x180037a28  jnz     short loc_180037A57
0x180037a2a  mov     rax, [rbx+50h]
0x180037a2e  mov     [rdi+8], rax
0x180037a32  mov     [rbx+50h], rdi
0x180037a36  mov     rcx, rbx; _Mtx_t
0x180037a39  call    cs:__imp__Mtx_unlock
0x180037a3f  mov     rax, rdi
0x180037a42  mov     rbx, [rsp+28h+arg_0]
0x180037a47  mov     rbp, [rsp+28h+arg_8]
0x180037a4c  mov     rsi, [rsp+28h+arg_10]
0x180037a51  add     rsp, 20h
0x180037a55  pop     rdi
0x180037a56  retn
0x180037a57  cmp     rbx, [rsi]
0x180037a5a  jnz     short loc_180037AAF
0x180037a5c  cmp     qword ptr [rsi+10h], 0
0x180037a61  jz      short loc_180037AAF
0x180037a63  mov     rax, [rdi+10h]
0x180037a67  cmp     [rsi+10h], rax
0x180037a6b  jnz     short loc_180037AA6
0x180037a6d  mov     eax, [rdi+18h]
0x180037a70  cmp     [rsi+18h], eax
0x180037a73  jz      short loc_180037A36
0x180037a75  mov     rcx, [rbx+58h]; hEvent
0x180037a79  call    cs:__imp_ResetEvent
0x180037a7f  lock inc dword ptr [rbx+60h]
0x180037a83  mov     rcx, rbx; _Mtx_t
0x180037a86  call    cs:__imp__Mtx_unlock
0x180037a8c  xor     r8d, r8d; bAlertable
0x180037a8f  lea     edx, [r8+32h]; dwMilliseconds
0x180037a93  mov     rcx, [rbx+58h]; hHandle
0x180037a97  call    cs:__imp_WaitForSingleObjectEx
0x180037a9d  lock dec dword ptr [rbx+60h]
0x180037aa1  jmp     loc_180037A19
0x180037aa6  mov     rsi, [rsi+8]
0x180037aaa  jmp     loc_180037A25
0x180037aaf  mov     ecx, 139049Bh
0x180037ab4  call    cs:__imp_MsoShipAssertTagProc
0x180037aba  jmp     short loc_180037A63
```
