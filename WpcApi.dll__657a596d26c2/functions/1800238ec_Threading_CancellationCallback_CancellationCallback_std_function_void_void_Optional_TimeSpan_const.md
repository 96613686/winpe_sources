# Threading::CancellationCallback::CancellationCallback(std::function<void (void)>,Optional<TimeSpan> const &)

- ea: `0x1800238ec`
- end: `0x180023aeb`
- name: `??0CancellationCallback@Threading@@QEAA@V?$function@$$A6AXXZ@std@@AEBV?$Optional@VTimeSpan@@@@@Z`
- size: `511`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180023b80`

## callees

- `0x180003d20`
- `0x1800195c4`
- `0x180021304`
- `0x18002162c`
- `0x1800216cc`
- `0x1800238ec`
- `0x18002c010`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x180023978`
- `KERNEL32!TlsGetValue` at `0x18002398c`
- `KERNEL32!TlsGetValue` at `0x1800239ce`
- `KERNEL32!TlsGetValue` at `0x180023978`
- `KERNEL32!TlsGetValue` at `0x18002398c`
- `KERNEL32!TlsGetValue` at `0x1800239ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Threading::CancellationCallback::CancellationCallback(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rax
  Threading *v9; // rcx
  char *v10; // rdi
  char *v11; // rcx
  _BYTE *v12; // rdx
  _BYTE *v13; // rdx
  __int64 v14; // rcx
  __int64 v16; // [rsp+28h] [rbp-39h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+38h] [rbp-29h] BYREF
  _BYTE v18[56]; // [rsp+60h] [rbp-1h] BYREF
  _BYTE *v19; // [rsp+98h] [rbp+37h]

  v19 = 0;
  v4 = *(_QWORD *)(a2 + 56);
  if ( v4 )
  {
    if ( v4 == a2 )
    {
      v19 = (_BYTE *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v4 + 8LL))(v4, v18);
      v6 = *(_QWORD *)(a2 + 56);
      if ( v6 )
      {
        LOBYTE(v5) = v6 != a2;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 32LL))(v6, v5);
        *(_QWORD *)(a2 + 56) = 0;
      }
    }
    else
    {
      v19 = *(_BYTE **)(a2 + 56);
      *(_QWORD *)(a2 + 56) = 0;
    }
  }
  if ( (int)TlsGetValue(dwTlsIndex) <= 0 )
  {
    if ( !TlsGetValue(dword_18004A6D8) )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
      throw (ErrorCodeException *)pExceptionObject;
    }
    anonymous_namespace_::TestWaitable(qword_18004A720);
    v8 = Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->();
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 48LL))(v8, &v16);
    Threading::TestThreadCancelled(v9);
    v10 = (char *)TlsGetValue(dword_18004A6D8) + 16;
    if ( v10 == v18 )
      goto LABEL_17;
    v11 = (char *)*((_QWORD *)v10 + 7);
    if ( v11 )
    {
      LOBYTE(v7) = v11 != v10;
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v11 + 32LL))(v11, v7);
      *((_QWORD *)v10 + 7) = 0;
    }
    if ( !v19 )
      goto LABEL_17;
    if ( v19 == v18 )
    {
      *((_QWORD *)v10 + 7) = (*(__int64 (__fastcall **)(_BYTE *, char *))(*(_QWORD *)v19 + 8LL))(v19, v10);
      if ( !v19 )
        goto LABEL_17;
      v12 = v18;
      LOBYTE(v12) = v19 != v18;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v19 + 32LL))(v19, v12);
    }
    else
    {
      *((_QWORD *)v10 + 7) = v19;
    }
    v19 = 0;
LABEL_17:
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
      v16 = 0;
    }
  }
  if ( v19 )
  {
    v13 = v18;
    LOBYTE(v13) = v19 != v18;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v19 + 32LL))(v19, v13);
  }
  v14 = *(_QWORD *)(a2 + 56);
  if ( v14 )
  {
    LOBYTE(v7) = v14 != a2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 32LL))(v14, v7);
    *(_QWORD *)(a2 + 56) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1800238ec  mov     rax, rsp
0x1800238ef  mov     [rax+8], rbx
0x1800238f3  mov     [rax+18h], r8
0x1800238f7  mov     [rax+10h], rdx
0x1800238fb  push    rbp
0x1800238fc  push    rsi
0x1800238fd  push    rdi
0x1800238fe  lea     rbp, [rax-5Fh]
0x180023902  sub     rsp, 0A0h
0x180023909  mov     rbx, rdx
0x18002390c  mov     rsi, rcx
0x18002390f  mov     [rbp+57h+var_20], 0
0x180023917  mov     rcx, [rdx+38h]
0x18002391b  test    rcx, rcx
0x18002391e  jz      short loc_18002396A
0x180023920  cmp     rcx, rdx
0x180023923  jnz     short loc_18002395E
0x180023925  mov     rax, [rcx]
0x180023928  lea     rdx, [rbp+57h+var_58]
0x18002392c  mov     rax, [rax+8]
0x180023930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023935  mov     [rbp+57h+var_20], rax
0x180023939  mov     rcx, [rbx+38h]
0x18002393d  test    rcx, rcx
0x180023940  jz      short loc_18002396A
0x180023942  mov     rax, [rcx]
0x180023945  cmp     rcx, rbx
0x180023948  setnz   dl
0x18002394b  mov     rax, [rax+20h]
0x18002394f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023954  mov     qword ptr [rbx+38h], 0
0x18002395c  jmp     short loc_18002396A
0x18002395e  mov     [rbp+57h+var_20], rcx
0x180023962  mov     qword ptr [rdx+38h], 0
0x18002396a  lea     rax, [rbp+57h+var_58]
0x18002396e  mov     [rbp+57h+arg_10], rax
0x180023972  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180023978  call    cs:__imp_TlsGetValue
0x18002397e  test    eax, eax
0x180023980  jg      loc_180023A73
0x180023986  mov     ecx, cs:dword_18004A6D8; dwTlsIndex
0x18002398c  call    cs:__imp_TlsGetValue
0x180023992  test    rax, rax
0x180023995  jz      loc_180023ACC
0x18002399b  lea     rcx, qword_18004A720
0x1800239a2  call    _anonymous_namespace___TestWaitable
0x1800239a7  call    ??C?$Global@V?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@@@QEAAPEAV?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@XZ; Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->(void)
0x1800239ac  mov     r8, rax
0x1800239af  mov     rcx, [rax]
0x1800239b2  mov     rax, [rcx+30h]
0x1800239b6  lea     rdx, [rbp+57h+var_90]
0x1800239ba  mov     rcx, r8
0x1800239bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239c2  nop
0x1800239c3  call    ?TestThreadCancelled@Threading@@YAXXZ; Threading::TestThreadCancelled(void)
0x1800239c8  mov     ecx, cs:dword_18004A6D8; dwTlsIndex
0x1800239ce  call    cs:__imp_TlsGetValue
0x1800239d4  lea     rdi, [rax+10h]
0x1800239d8  lea     rax, [rbp+57h+var_58]
0x1800239dc  cmp     rdi, rax
0x1800239df  jz      short loc_180023A56
0x1800239e1  mov     rcx, [rdi+38h]
0x1800239e5  test    rcx, rcx
0x1800239e8  jz      short loc_180023A04
0x1800239ea  mov     rax, [rcx]
0x1800239ed  cmp     rcx, rdi
0x1800239f0  setnz   dl
0x1800239f3  mov     rax, [rax+20h]
0x1800239f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239fc  mov     qword ptr [rdi+38h], 0
0x180023a04  mov     rcx, [rbp+57h+var_20]
0x180023a08  test    rcx, rcx
0x180023a0b  jz      short loc_180023A56
0x180023a0d  lea     rax, [rbp+57h+var_58]
0x180023a11  cmp     rcx, rax
0x180023a14  jnz     short loc_180023A4A
0x180023a16  mov     rax, [rcx]
0x180023a19  mov     rdx, rdi
0x180023a1c  mov     rax, [rax+8]
0x180023a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a25  mov     [rdi+38h], rax
0x180023a29  mov     rcx, [rbp+57h+var_20]
0x180023a2d  test    rcx, rcx
0x180023a30  jz      short loc_180023A56
0x180023a32  mov     rax, [rcx]
0x180023a35  lea     rdx, [rbp+57h+var_58]
0x180023a39  cmp     rcx, rdx
0x180023a3c  setnz   dl
0x180023a3f  mov     rax, [rax+20h]
0x180023a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a48  jmp     short loc_180023A4E
0x180023a4a  mov     [rdi+38h], rcx
0x180023a4e  mov     [rbp+57h+var_20], 0
0x180023a56  mov     rcx, [rbp+57h+var_90]
0x180023a5a  test    rcx, rcx
0x180023a5d  jz      short loc_180023A73
0x180023a5f  mov     rax, [rcx]
0x180023a62  mov     rax, [rax+18h]
0x180023a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a6b  mov     [rbp+57h+var_90], 0
0x180023a73  mov     rcx, [rbp+57h+var_20]
0x180023a77  test    rcx, rcx
0x180023a7a  jz      short loc_180023A93
0x180023a7c  lea     rdx, [rbp+57h+var_58]
0x180023a80  cmp     rcx, rdx
0x180023a83  mov     rax, [rcx]
0x180023a86  setnz   dl
0x180023a89  mov     rax, [rax+20h]
0x180023a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a92  nop
0x180023a93  mov     rcx, [rbx+38h]
0x180023a97  test    rcx, rcx
0x180023a9a  jz      short loc_180023AB6
0x180023a9c  mov     rax, [rcx]
0x180023a9f  cmp     rcx, rbx
0x180023aa2  setnz   dl
0x180023aa5  mov     rax, [rax+20h]
0x180023aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023aae  mov     qword ptr [rbx+38h], 0
0x180023ab6  mov     rax, rsi
0x180023ab9  mov     rbx, [rsp+0B0h+arg_0]
0x180023ac1  add     rsp, 0A0h
0x180023ac8  pop     rdi
0x180023ac9  pop     rsi
0x180023aca  pop     rbp
0x180023acb  retn
0x180023acc  mov     edx, 8000FFFFh; int
0x180023ad1  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180023ad5  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180023ada  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180023ae1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180023ae5  call    _CxxThrowException_0
```
