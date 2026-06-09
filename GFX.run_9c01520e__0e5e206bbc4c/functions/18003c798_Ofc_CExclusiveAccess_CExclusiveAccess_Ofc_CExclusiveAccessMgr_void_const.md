# Ofc::CExclusiveAccess::CExclusiveAccess(Ofc::CExclusiveAccessMgr &,void const *)

- ea: `0x18003c798`
- end: `0x18003c875`
- name: `??0CExclusiveAccess@Ofc@@QEAA@AEAVCExclusiveAccessMgr@1@PEBX@Z`
- size: `221`
- prototype: `__int64 __fastcall(Ofc::CExclusiveAccess *__hidden this, struct Ofc::CExclusiveAccessMgr *, const void *)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x18001bf60`
- `0x18003b9e0`
- `0x18003c750`
- `0x18004eec0`
- `0x1800acd08`
- `0x1800ae470`
- `0x1800afbdc`
- `0x1800b07c0`
- `0x1800b0ed0`
- `0x180112680`
- `0x1801b8010`
- `0x1801ba250`

## callees

- `0x18003c798`
- `0x180076df0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18003c7be`
- `KERNEL32!GetCurrentThreadId` at `0x18003c7be`
- `KERNEL32!WaitForSingleObjectEx` at `0x18003c84f`
- `KERNEL32!WaitForSingleObjectEx` at `0x18003c84f`
- `KERNEL32!ResetEvent` at `0x18003c831`
- `KERNEL32!ResetEvent` at `0x18003c831`
- `MSVCP140!_Mtx_unlock` at `0x18003c7f1`
- `MSVCP140!_Mtx_unlock` at `0x18003c83e`
- `MSVCP140!_Mtx_unlock` at `0x18003c7f1`
- `MSVCP140!_Mtx_unlock` at `0x18003c83e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18003c86c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18003c86c`

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
0x18003c798  mov     [rsp+arg_0], rbx
0x18003c79d  mov     [rsp+arg_8], rbp
0x18003c7a2  mov     [rsp+arg_10], rsi
0x18003c7a7  push    rdi
0x18003c7a8  sub     rsp, 20h
0x18003c7ac  mov     rdi, rcx
0x18003c7af  mov     [rcx], rdx
0x18003c7b2  mov     qword ptr [rcx+8], 0
0x18003c7ba  mov     [rcx+10h], r8
0x18003c7be  call    cs:__imp_GetCurrentThreadId
0x18003c7c4  mov     [rdi+18h], eax
0x18003c7c7  cmp     qword ptr [rdi+10h], 0
0x18003c7cc  jz      short loc_18003C7F7
0x18003c7ce  mov     rbx, [rdi]
0x18003c7d1  mov     rcx, rbx; this
0x18003c7d4  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18003c7d9  mov     rsi, [rbx+50h]
0x18003c7dd  test    rsi, rsi
0x18003c7e0  jnz     short loc_18003C80F
0x18003c7e2  mov     rax, [rbx+50h]
0x18003c7e6  mov     [rdi+8], rax
0x18003c7ea  mov     [rbx+50h], rdi
0x18003c7ee  mov     rcx, rbx; _Mtx_t
0x18003c7f1  call    cs:__imp__Mtx_unlock
0x18003c7f7  mov     rax, rdi
0x18003c7fa  mov     rbx, [rsp+28h+arg_0]
0x18003c7ff  mov     rbp, [rsp+28h+arg_8]
0x18003c804  mov     rsi, [rsp+28h+arg_10]
0x18003c809  add     rsp, 20h
0x18003c80d  pop     rdi
0x18003c80e  retn
0x18003c80f  cmp     rbx, [rsi]
0x18003c812  jnz     short loc_18003C867
0x18003c814  cmp     qword ptr [rsi+10h], 0
0x18003c819  jz      short loc_18003C867
0x18003c81b  mov     rax, [rdi+10h]
0x18003c81f  cmp     [rsi+10h], rax
0x18003c823  jnz     short loc_18003C85E
0x18003c825  mov     eax, [rdi+18h]
0x18003c828  cmp     [rsi+18h], eax
0x18003c82b  jz      short loc_18003C7EE
0x18003c82d  mov     rcx, [rbx+58h]; hEvent
0x18003c831  call    cs:__imp_ResetEvent
0x18003c837  lock inc dword ptr [rbx+60h]
0x18003c83b  mov     rcx, rbx; _Mtx_t
0x18003c83e  call    cs:__imp__Mtx_unlock
0x18003c844  xor     r8d, r8d; bAlertable
0x18003c847  lea     edx, [r8+32h]; dwMilliseconds
0x18003c84b  mov     rcx, [rbx+58h]; hHandle
0x18003c84f  call    cs:__imp_WaitForSingleObjectEx
0x18003c855  lock dec dword ptr [rbx+60h]
0x18003c859  jmp     loc_18003C7D1
0x18003c85e  mov     rsi, [rsi+8]
0x18003c862  jmp     loc_18003C7DD
0x18003c867  mov     ecx, 139049Bh
0x18003c86c  call    cs:__imp_MsoShipAssertTagProc
0x18003c872  jmp     short loc_18003C81B
```
