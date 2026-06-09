# AppActivation::~AppActivation(void)

- ea: `0x18002fa00`
- end: `0x18002fc25`
- name: `??1AppActivation@@MEAA@XZ`
- size: `549`
- prototype: `void __fastcall(AppActivation *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002f9c0`

## callees

- `0x18002fa00`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fc1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fc1a`
- `ntdll!RtlWakeAllConditionVariable` at `0x18002fa51`
- `ntdll!RtlWakeAllConditionVariable` at `0x18002fa51`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002fa47`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002fc04`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002fa47`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002fc04`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002fa2c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002fa2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fb73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fb87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fb9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fbaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fbc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fbd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fb73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fb87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fb9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fbaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fbc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fbd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fbe7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fbe7`
- `api-ms-win-core-com-private-l1-1-0!CoRevokeRacActivationToken` at `0x18002fc0f`
- `api-ms-win-core-com-private-l1-1-0!CoRevokeRacActivationToken` at `0x18002fc0f`
- `RMCLIENT!HamCloseActivity` at `0x18002fa5f`
- `RMCLIENT!HamCloseActivity` at `0x18002fa5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AppActivation::~AppActivation(AppActivation *this)
{
  __int64 v2; // rdi
  __int64 v3; // rcx
  char *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  void *v12; // rcx

  *(_QWORD *)this = &AppActivation::`vftable';
  v2 = *((_QWORD *)this + 26);
  if ( v2 )
  {
    RtlAcquireSRWLockExclusive(v2 + 8);
    v3 = v2 + 8;
    if ( *(_DWORD *)(v2 + 40) == 3 )
    {
      RtlReleaseSRWLockExclusive(v3);
    }
    else
    {
      *(_DWORD *)(v2 + 40) = 3;
      RtlReleaseSRWLockExclusive(v3);
      RtlWakeAllConditionVariable(v2 + 16);
      HamCloseActivity(*(_QWORD *)(v2 + 24), *(_QWORD *)(v2 + 32));
    }
  }
  if ( *((_QWORD *)this + 28) )
    CoRevokeRacActivationToken();
  v4 = (char *)*((_QWORD *)this + 32);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  v5 = *((_QWORD *)this + 27);
  if ( v5 )
  {
    *((_QWORD *)this + 27) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *((_QWORD *)this + 26);
  if ( v6 )
  {
    *((_QWORD *)this + 26) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v7 = *((_QWORD *)this + 25);
  if ( v7 )
  {
    *((_QWORD *)this + 25) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  v8 = *((_QWORD *)this + 24);
  if ( v8 )
  {
    *((_QWORD *)this + 24) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = *((_QWORD *)this + 23);
  if ( v9 )
  {
    *((_QWORD *)this + 23) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v10 = *((_QWORD *)this + 22);
  if ( v10 )
  {
    *((_QWORD *)this + 22) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = *((_QWORD *)this + 21);
  if ( v11 )
  {
    *((_QWORD *)this + 21) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  WindowsDeleteString(*((HSTRING *)this + 20));
  *((_QWORD *)this + 20) = 0;
  WindowsDeleteString(*((HSTRING *)this + 19));
  *((_QWORD *)this + 19) = 0;
  WindowsDeleteString(*((HSTRING *)this + 18));
  *((_QWORD *)this + 18) = 0;
  WindowsDeleteString(*((HSTRING *)this + 17));
  *((_QWORD *)this + 17) = 0;
  WindowsDeleteString(*((HSTRING *)this + 16));
  *((_QWORD *)this + 16) = 0;
  WindowsDeleteString(*((HSTRING *)this + 15));
  *((_QWORD *)this + 15) = 0;
  v12 = (void *)*((_QWORD *)this + 14);
  if ( v12 )
    LocalFree(v12);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18002fa00  mov     [rsp+arg_0], rbx
0x18002fa05  mov     [rsp+arg_8], rsi
0x18002fa0a  push    rdi
0x18002fa0b  sub     rsp, 20h
0x18002fa0f  mov     rbx, rcx
0x18002fa12  lea     rax, ??_7AppActivation@@6B@; const AppActivation::`vftable'
0x18002fa19  mov     [rcx], rax
0x18002fa1c  mov     rdi, [rcx+0D0h]
0x18002fa23  test    rdi, rdi
0x18002fa26  jz      short loc_18002FA65
0x18002fa28  lea     rcx, [rdi+8]
0x18002fa2c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002fa32  lea     rcx, [rdi+8]
0x18002fa36  cmp     dword ptr [rdi+28h], 3
0x18002fa3a  jz      loc_18002FC04
0x18002fa40  mov     dword ptr [rdi+28h], 3
0x18002fa47  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002fa4d  lea     rcx, [rdi+10h]
0x18002fa51  call    cs:__imp_RtlWakeAllConditionVariable
0x18002fa57  mov     rdx, [rdi+20h]
0x18002fa5b  mov     rcx, [rdi+18h]
0x18002fa5f  call    cs:__imp_HamCloseActivity
0x18002fa65  mov     rcx, [rbx+0E0h]
0x18002fa6c  test    rcx, rcx
0x18002fa6f  jnz     loc_18002FC0F
0x18002fa75  mov     rcx, [rbx+100h]; hObject
0x18002fa7c  lea     rax, [rcx-1]
0x18002fa80  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002fa84  jbe     loc_18002FC1A
0x18002fa8a  mov     rcx, [rbx+0D8h]
0x18002fa91  xor     edi, edi
0x18002fa93  test    rcx, rcx
0x18002fa96  jz      short loc_18002FAAC
0x18002fa98  mov     [rbx+0D8h], rdi
0x18002fa9f  mov     rax, [rcx]
0x18002faa2  mov     rax, [rax+10h]
0x18002faa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002faab  nop
0x18002faac  mov     rcx, [rbx+0D0h]
0x18002fab3  test    rcx, rcx
0x18002fab6  jz      short loc_18002FACC
0x18002fab8  mov     [rbx+0D0h], rdi
0x18002fabf  mov     rax, [rcx]
0x18002fac2  mov     rax, [rax+10h]
0x18002fac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002facb  nop
0x18002facc  mov     rcx, [rbx+0C8h]
0x18002fad3  test    rcx, rcx
0x18002fad6  jz      short loc_18002FAEC
0x18002fad8  mov     [rbx+0C8h], rdi
0x18002fadf  mov     rax, [rcx]
0x18002fae2  mov     rax, [rax+10h]
0x18002fae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002faeb  nop
0x18002faec  mov     rcx, [rbx+0C0h]
0x18002faf3  test    rcx, rcx
0x18002faf6  jz      short loc_18002FB0C
0x18002faf8  mov     [rbx+0C0h], rdi
0x18002faff  mov     rax, [rcx]
0x18002fb02  mov     rax, [rax+10h]
0x18002fb06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb0b  nop
0x18002fb0c  mov     rcx, [rbx+0B8h]
0x18002fb13  test    rcx, rcx
0x18002fb16  jz      short loc_18002FB2C
0x18002fb18  mov     [rbx+0B8h], rdi
0x18002fb1f  mov     rax, [rcx]
0x18002fb22  mov     rax, [rax+10h]
0x18002fb26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb2b  nop
0x18002fb2c  mov     rcx, [rbx+0B0h]
0x18002fb33  test    rcx, rcx
0x18002fb36  jz      short loc_18002FB4C
0x18002fb38  mov     [rbx+0B0h], rdi
0x18002fb3f  mov     rax, [rcx]
0x18002fb42  mov     rax, [rax+10h]
0x18002fb46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb4b  nop
0x18002fb4c  mov     rcx, [rbx+0A8h]
0x18002fb53  test    rcx, rcx
0x18002fb56  jz      short loc_18002FB6C
0x18002fb58  mov     [rbx+0A8h], rdi
0x18002fb5f  mov     rax, [rcx]
0x18002fb62  mov     rax, [rax+10h]
0x18002fb66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb6b  nop
0x18002fb6c  mov     rcx, [rbx+0A0h]; string
0x18002fb73  call    cs:__imp_WindowsDeleteString
0x18002fb79  mov     [rbx+0A0h], rdi
0x18002fb80  mov     rcx, [rbx+98h]; string
0x18002fb87  call    cs:__imp_WindowsDeleteString
0x18002fb8d  mov     [rbx+98h], rdi
0x18002fb94  mov     rcx, [rbx+90h]; string
0x18002fb9b  call    cs:__imp_WindowsDeleteString
0x18002fba1  mov     [rbx+90h], rdi
0x18002fba8  mov     rcx, [rbx+88h]; string
0x18002fbaf  call    cs:__imp_WindowsDeleteString
0x18002fbb5  mov     [rbx+88h], rdi
0x18002fbbc  mov     rcx, [rbx+80h]; string
0x18002fbc3  call    cs:__imp_WindowsDeleteString
0x18002fbc9  mov     [rbx+80h], rdi
0x18002fbd0  mov     rcx, [rbx+78h]; string
0x18002fbd4  call    cs:__imp_WindowsDeleteString
0x18002fbda  mov     [rbx+78h], rdi
0x18002fbde  mov     rcx, [rbx+70h]; hMem
0x18002fbe2  test    rcx, rcx
0x18002fbe5  jz      short loc_18002FBED
0x18002fbe7  call    cs:__imp_LocalFree
0x18002fbed  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18002fbf4  mov     rbx, [rsp+28h+arg_0]
0x18002fbf9  mov     rsi, [rsp+28h+arg_8]
0x18002fbfe  add     rsp, 20h
0x18002fc02  pop     rdi
0x18002fc03  retn
0x18002fc04  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002fc0a  jmp     loc_18002FA65
0x18002fc0f  call    cs:__imp_CoRevokeRacActivationToken
0x18002fc15  jmp     loc_18002FA75
0x18002fc1a  call    cs:__imp_CloseHandle
0x18002fc20  jmp     loc_18002FA8A
```
