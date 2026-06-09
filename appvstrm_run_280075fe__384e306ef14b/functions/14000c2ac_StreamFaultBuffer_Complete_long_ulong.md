# StreamFaultBuffer::Complete(long,ulong)

- ea: `0x14000c2ac`
- end: `0x14000c4a6`
- name: `?Complete@StreamFaultBuffer@@QEAAXJK@Z`
- size: `506`
- prototype: `void __fastcall(StreamFaultBuffer *__hidden this, int, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000c4ac`
- `0x14000d690`

## callees

- `0x14000c2ac`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `FLTMGR!FltCompletePendedPreOperation` at `0x14000c487`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14000c487`

## string_xrefs

- `0x14000c314`: `StreamFaultBuffer::Complete() - Stream fault failed. File name: %s, Offset: %lld , Length %ld, Status 0x%08X.`
- `0x14000c3de`: `StreamFaultBuffer::Complete() - Stream Succeeded. File name: %s, Offset: %lld, Length %ld, Status 0x%08X.`

## pseudocode

```c
void __fastcall StreamFaultBuffer::Complete(StreamFaultBuffer *this, int a2, unsigned int a3)
{
  __int64 v4; // r9
  _QWORD *v5; // rcx
  __int64 v7; // r8
  int v8; // edi
  __int64 v9; // rsi
  __int64 v10; // rbx
  __int64 *v11; // rax
  volatile signed __int32 *v12; // rdi
  volatile signed __int32 *v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // r8
  _QWORD *v16; // rcx
  __int64 v17; // rcx
  int v18; // edi
  __int64 v19; // rsi
  __int64 v20; // rbx
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *v22; // rdi
  int v23; // [rsp+28h] [rbp-60h]
  int v24; // [rsp+28h] [rbp-60h]
  int v25; // [rsp+30h] [rbp-58h]
  int v26; // [rsp+30h] [rbp-58h]
  _BYTE v27[8]; // [rsp+40h] [rbp-48h] BYREF
  volatile signed __int32 *v28; // [rsp+48h] [rbp-40h]
  _BYTE v29[8]; // [rsp+50h] [rbp-38h] BYREF
  volatile signed __int32 *v30; // [rsp+58h] [rbp-30h]

  v4 = a3;
  v5 = *(_QWORD **)this;
  if ( v5 )
  {
    if ( a2 >= 0 )
    {
      v14 = **((_QWORD **)this + 4);
      if ( (*(_DWORD *)(v14 + 80) & 2) != 0 )
      {
        v15 = v5[2];
        if ( (*(_DWORD *)v15 & 2) == 0 )
          *(_QWORD *)(v14 + 104) = *(_QWORD *)(v15 + 40) + v4;
      }
      v16 = *(_QWORD **)this;
      *((_DWORD *)v16 + 6) = a2;
      v16[4] = v4;
      v17 = *(_QWORD *)(*(_QWORD *)this + 16LL);
      v18 = *(_DWORD *)(v17 + 24);
      v19 = *(_QWORD *)(v17 + 40);
      v20 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v27, *((_QWORD *)this + 5) + 16LL);
      CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(v29);
      v26 = a2;
      v24 = v18;
      LogWrite(
        3,
        *CurrentActivityID,
        L"StreamFaultBuffer::Complete() - Stream Succeeded. File name: %s, Offset: %lld, Length %ld, Status 0x%08X.",
        v20,
        v19,
        v24,
        v26);
      v22 = v30;
      if ( v30 )
      {
        if ( _InterlockedExchangeAdd(v30 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
          if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 16LL))(v22);
        }
      }
      v13 = v28;
    }
    else
    {
      *((_DWORD *)v5 + 6) = -1073741818;
      v5[4] = 0;
      v7 = *(_QWORD *)(*(_QWORD *)this + 16LL);
      v8 = *(_DWORD *)(v7 + 24);
      v9 = *(_QWORD *)(v7 + 40);
      v10 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v29, *((_QWORD *)this + 5) + 16LL);
      v11 = (__int64 *)Streaming::Utils::GetCurrentActivityID(v27);
      v25 = a2;
      v23 = v8;
      LogWrite(
        1,
        *v11,
        L"StreamFaultBuffer::Complete() - Stream fault failed. File name: %s, Offset: %lld , Length %ld, Status 0x%08X.",
        v10,
        v9,
        v23,
        v25);
      v12 = v28;
      if ( v28 )
      {
        if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
      v13 = v30;
    }
    if ( v13 && _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    FltCompletePendedPreOperation(*(PFLT_CALLBACK_DATA *)this, FLT_PREOP_COMPLETE, 0);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x14000c2ac  push    rbx
0x14000c2ae  push    rbp
0x14000c2af  push    rsi
0x14000c2b0  push    rdi
0x14000c2b1  push    r14
0x14000c2b3  sub     rsp, 60h
0x14000c2b7  mov     r14, rcx
0x14000c2ba  mov     r9d, r8d
0x14000c2bd  mov     rcx, [rcx]
0x14000c2c0  mov     ebp, edx
0x14000c2c2  test    rcx, rcx
0x14000c2c5  jz      loc_14000C49A
0x14000c2cb  test    edx, edx
0x14000c2cd  jns     loc_14000C37F
0x14000c2d3  mov     dword ptr [rcx+18h], 0C0000006h
0x14000c2da  mov     qword ptr [rcx+20h], 0
0x14000c2e2  lea     rcx, [rsp+88h+var_38]
0x14000c2e7  mov     rax, [r14]
0x14000c2ea  mov     rdx, [r14+28h]
0x14000c2ee  add     rdx, 10h
0x14000c2f2  mov     r8, [rax+10h]
0x14000c2f6  mov     edi, [r8+18h]
0x14000c2fa  mov     rsi, [r8+28h]
0x14000c2fe  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000c303  lea     rcx, [rsp+88h+var_48]
0x14000c308  mov     rbx, [rax]
0x14000c30b  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000c310  mov     [rsp+88h+var_58], ebp
0x14000c314  lea     r8, aStreamfaultbuf_3; "StreamFaultBuffer::Complete() - Stream "...
0x14000c31b  mov     [rsp+88h+var_60], edi
0x14000c31f  mov     r9, rbx
0x14000c322  mov     ecx, 1
0x14000c327  mov     [rsp+88h+var_68], rsi
0x14000c32c  mov     rdx, [rax]
0x14000c32f  call    LogWrite
0x14000c334  mov     rdi, [rsp+88h+var_40]
0x14000c339  or      ebx, 0FFFFFFFFh
0x14000c33c  test    rdi, rdi
0x14000c33f  jz      short loc_14000C375
0x14000c341  mov     eax, ebx
0x14000c343  lock xadd [rdi+8], eax
0x14000c348  add     eax, ebx
0x14000c34a  jnz     short loc_14000C375
0x14000c34c  mov     rax, [rdi]
0x14000c34f  mov     rcx, rdi
0x14000c352  mov     rax, [rax+8]
0x14000c356  call    _guard_dispatch_icall
0x14000c35b  mov     eax, ebx
0x14000c35d  lock xadd [rdi+0Ch], eax
0x14000c362  add     eax, ebx
0x14000c364  jnz     short loc_14000C375
0x14000c366  mov     rax, [rdi]
0x14000c369  mov     rcx, rdi
0x14000c36c  mov     rax, [rax+10h]
0x14000c370  call    _guard_dispatch_icall
0x14000c375  mov     rdi, [rsp+88h+var_30]
0x14000c37a  jmp     loc_14000C444
0x14000c37f  mov     rax, [r14+20h]
0x14000c383  mov     rdx, [rax]
0x14000c386  mov     eax, [rdx+50h]
0x14000c389  test    al, 2
0x14000c38b  jz      short loc_14000C3A3
0x14000c38d  mov     r8, [rcx+10h]
0x14000c391  mov     eax, [r8]
0x14000c394  test    al, 2
0x14000c396  jnz     short loc_14000C3A3
0x14000c398  mov     rax, r9
0x14000c39b  add     rax, [r8+28h]
0x14000c39f  mov     [rdx+68h], rax
0x14000c3a3  mov     rcx, [r14]
0x14000c3a6  mov     [rcx+18h], ebp
0x14000c3a9  mov     [rcx+20h], r9
0x14000c3ad  mov     rax, [r14]
0x14000c3b0  mov     rdx, [r14+28h]
0x14000c3b4  add     rdx, 10h
0x14000c3b8  mov     rcx, [rax+10h]
0x14000c3bc  mov     edi, [rcx+18h]
0x14000c3bf  mov     rsi, [rcx+28h]
0x14000c3c3  lea     rcx, [rsp+88h+var_48]
0x14000c3c8  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000c3cd  lea     rcx, [rsp+88h+var_38]
0x14000c3d2  mov     rbx, [rax]
0x14000c3d5  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000c3da  mov     [rsp+88h+var_58], ebp
0x14000c3de  lea     r8, aStreamfaultbuf_1; "StreamFaultBuffer::Complete() - Stream "...
0x14000c3e5  mov     [rsp+88h+var_60], edi
0x14000c3e9  mov     r9, rbx
0x14000c3ec  mov     ecx, 3
0x14000c3f1  mov     [rsp+88h+var_68], rsi
0x14000c3f6  mov     rdx, [rax]
0x14000c3f9  call    LogWrite
0x14000c3fe  mov     rdi, [rsp+88h+var_30]
0x14000c403  or      ebx, 0FFFFFFFFh
0x14000c406  test    rdi, rdi
0x14000c409  jz      short loc_14000C43F
0x14000c40b  mov     eax, ebx
0x14000c40d  lock xadd [rdi+8], eax
0x14000c412  add     eax, ebx
0x14000c414  jnz     short loc_14000C43F
0x14000c416  mov     rax, [rdi]
0x14000c419  mov     rcx, rdi
0x14000c41c  mov     rax, [rax+8]
0x14000c420  call    _guard_dispatch_icall
0x14000c425  mov     eax, ebx
0x14000c427  lock xadd [rdi+0Ch], eax
0x14000c42c  add     eax, ebx
0x14000c42e  jnz     short loc_14000C43F
0x14000c430  mov     rax, [rdi]
0x14000c433  mov     rcx, rdi
0x14000c436  mov     rax, [rax+10h]
0x14000c43a  call    _guard_dispatch_icall
0x14000c43f  mov     rdi, [rsp+88h+var_40]
0x14000c444  test    rdi, rdi
0x14000c447  jz      short loc_14000C47D
0x14000c449  mov     eax, ebx
0x14000c44b  lock xadd [rdi+8], eax
0x14000c450  add     eax, ebx
0x14000c452  jnz     short loc_14000C47D
0x14000c454  mov     rax, [rdi]
0x14000c457  mov     rcx, rdi
0x14000c45a  mov     rax, [rax+8]
0x14000c45e  call    _guard_dispatch_icall
0x14000c463  mov     eax, ebx
0x14000c465  lock xadd [rdi+0Ch], eax
0x14000c46a  add     eax, ebx
0x14000c46c  jnz     short loc_14000C47D
0x14000c46e  mov     rax, [rdi]
0x14000c471  mov     rcx, rdi
0x14000c474  mov     rax, [rax+10h]
0x14000c478  call    _guard_dispatch_icall
0x14000c47d  mov     rcx, [r14]; CallbackData
0x14000c480  xor     r8d, r8d; Context
0x14000c483  lea     edx, [r8+4]; CallbackStatus
0x14000c487  call    cs:__imp_FltCompletePendedPreOperation
0x14000c48e  nop     dword ptr [rax+rax+00h]
0x14000c493  mov     qword ptr [r14], 0
0x14000c49a  add     rsp, 60h
0x14000c49e  pop     r14
0x14000c4a0  pop     rdi
0x14000c4a1  pop     rsi
0x14000c4a2  pop     rbp
0x14000c4a3  pop     rbx
0x14000c4a4  retn
```
