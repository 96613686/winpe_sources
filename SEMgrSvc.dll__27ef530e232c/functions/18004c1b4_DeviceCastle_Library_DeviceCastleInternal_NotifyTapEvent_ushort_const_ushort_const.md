# DeviceCastle::Library::DeviceCastleInternal::NotifyTapEvent(ushort const *,ushort const *)

- ea: `0x18004c1b4`
- end: `0x18004c430`
- name: `?NotifyTapEvent@DeviceCastleInternal@Library@DeviceCastle@@QEAAJPEBG0@Z`
- size: `636`
- prototype: `int(DeviceCastle::Library::DeviceCastleInternal *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180042ea0`

## callees

- `0x180004e9c`
- `0x1800480dc`
- `0x18004989c`
- `0x18004bf9c`
- `0x18004c1b4`
- `0x18004d0c8`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c30c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c30c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004c2cb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004c2cb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004c389`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004c389`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004c2d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004c2d8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18004c2fa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18004c2fa`

## string_xrefs

- `0x18004c3ef`: `Tap event ignored due to %1!lu! events already active.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DeviceCastle::Library::DeviceCastleInternal::NotifyTapEvent(
        DeviceCastle::Library::DeviceCastleInternal *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  signed int v5; // ebx
  signed __int32 v6; // eax
  DeviceCastle::Library::CallerIdentity *v7; // rax
  DeviceCastle::Library::CallerIdentity *v8; // rsi
  struct _TP_WORK *v9; // rcx
  PTP_WORK ThreadpoolWork; // rax
  signed int LastError; // eax
  DeviceCastle::Library::CallerIdentity *v14; // [rsp+68h] [rbp+10h] BYREF

  if ( a2 && *a2 )
  {
    v5 = 1;
    v6 = _InterlockedIncrement((volatile signed __int32 *)this + 146);
    if ( v6 == 1 )
    {
      v7 = (DeviceCastle::Library::CallerIdentity *)operator new(0xC0u, (const struct std::nothrow_t *)std::nothrow);
      v14 = v7;
      if ( v7 )
        v8 = (DeviceCastle::Library::CallerIdentity *)DeviceCastle::Library::CallerIdentity::CallerIdentity(v7);
      else
        v8 = 0;
      v14 = v8;
      if ( v8 )
      {
        try
        {
          v5 = DeviceCastle::Library::SetCallerId(a2);
          if ( v5 >= 0 )
          {
            v9 = (struct _TP_WORK *)*((_QWORD *)this + 83);
            if ( v9 )
            {
              WaitForThreadpoolWorkCallbacks(v9, 0);
              CloseThreadpoolWork(*((PTP_WORK *)this + 83));
              *((_QWORD *)this + 83) = 0;
            }
            ThreadpoolWork = CreateThreadpoolWork(
                               DeviceCastle::Library::DeviceCastleInternal::HandleTapEvent,
                               v8,
                               (PTP_CALLBACK_ENVIRON)((char *)this + 592));
            *((_QWORD *)this + 83) = ThreadpoolWork;
            if ( ThreadpoolWork )
            {
              MEMORY[0xB0] = -2147483638;
              SubmitThreadpoolWork(*((PTP_WORK *)this + 83));
              v14 = 0;
              v5 = 0;
            }
            else
            {
              LastError = GetLastError();
              v5 = LastError;
              if ( LastError > 0 )
                v5 = (unsigned __int16)LastError | 0x80070000;
            }
          }
          std::unique_ptr<DeviceCastle::Library::CallerIdentity>::~unique_ptr<DeviceCastle::Library::CallerIdentity>(&v14);
        }
        catch ( ... )
        {
          _InterlockedDecrement((volatile signed __int32 *)this + 146);
          throw;
        }
      }
      else
      {
        v5 = -2147024882;
        std::unique_ptr<DeviceCastle::Library::CallerIdentity>::~unique_ptr<DeviceCastle::Library::CallerIdentity>(&v14);
      }
    }
    else
    {
      DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(
        this,
        4u,
        0,
        L"Tap event ignored due to %1!lu! events already active.",
        v6 - 1);
    }
  }
  else
  {
    v5 = -2147024809;
  }
  if ( *((_DWORD *)this + 146) )
    _InterlockedDecrement((volatile signed __int32 *)this + 146);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004c1b4  mov     [rsp+arg_10], rbx
0x18004c1b9  mov     [rsp+arg_18], rsi
0x18004c1be  mov     [rsp+arg_0], rcx
0x18004c1c3  push    rdi
0x18004c1c4  push    r14
0x18004c1c6  push    r15
0x18004c1c8  sub     rsp, 40h
0x18004c1cc  mov     r15, r8
0x18004c1cf  mov     r14, rdx
0x18004c1d2  mov     rdi, rcx
0x18004c1d5  test    rdx, rdx
0x18004c1d8  jz      loc_18004C404
0x18004c1de  xor     eax, eax
0x18004c1e0  cmp     ax, [rdx]
0x18004c1e3  jz      loc_18004C404
0x18004c1e9  lea     ebx, [rax+1]
0x18004c1ec  mov     eax, ebx
0x18004c1ee  lock xadd [rcx+248h], eax
0x18004c1f6  add     eax, ebx
0x18004c1f8  cmp     eax, ebx
0x18004c1fa  jnz     loc_18004C3E9
0x18004c200  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004c207  mov     ecx, 0C0h; unsigned __int64
0x18004c20c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004c211  mov     [rsp+58h+arg_8], rax
0x18004c216  test    rax, rax
0x18004c219  jz      short loc_18004C228
0x18004c21b  mov     rcx, rax; this
0x18004c21e  call    ??0CallerIdentity@Library@DeviceCastle@@QEAA@XZ; DeviceCastle::Library::CallerIdentity::CallerIdentity(void)
0x18004c223  mov     rsi, rax
0x18004c226  jmp     short loc_18004C22A
0x18004c228  xor     esi, esi
0x18004c22a  mov     [rsp+58h+arg_8], rsi
0x18004c22f  xorps   xmm0, xmm0
0x18004c232  movdqu  [rsp+58h+var_28], xmm0
0x18004c238  test    rsi, rsi
0x18004c23b  jnz     short loc_18004C252
0x18004c23d  mov     ebx, 8007000Eh
0x18004c242  lea     rcx, [rsp+58h+arg_8]
0x18004c247  call    ??1?$unique_ptr@VCallerIdentity@Library@DeviceCastle@@U?$default_delete@VCallerIdentity@Library@DeviceCastle@@@std@@@std@@QEAA@XZ; std::unique_ptr<DeviceCastle::Library::CallerIdentity>::~unique_ptr<DeviceCastle::Library::CallerIdentity>(void)
0x18004c24c  nop
0x18004c24d  jmp     loc_18004C409
0x18004c252  lea     r9, [rsp+58h+var_28]
0x18004c257  mov     r8, rsi
0x18004c25a  mov     rdx, r15
0x18004c25d  mov     rcx, r14; unsigned __int16 *
0x18004c260  call    DeviceCastle__Library__SetCallerId
0x18004c265  mov     ebx, eax
0x18004c267  test    eax, eax
0x18004c269  jns     short loc_18004C2BD
0x18004c26b  mov     rsi, qword ptr [rsp+58h+var_28+8]
0x18004c270  test    rsi, rsi
0x18004c273  jz      short loc_18004C2AD
0x18004c275  or      eax, 0FFFFFFFFh
0x18004c278  lock xadd [rsi+8], eax
0x18004c27d  cmp     eax, 1
0x18004c280  jnz     short loc_18004C2AD
0x18004c282  mov     rax, [rsi]
0x18004c285  mov     rcx, rsi
0x18004c288  mov     rax, [rax]
0x18004c28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c290  or      eax, 0FFFFFFFFh
0x18004c293  lock xadd [rsi+0Ch], eax
0x18004c298  cmp     eax, 1
0x18004c29b  jnz     short loc_18004C2AD
0x18004c29d  mov     rax, [rsi]
0x18004c2a0  mov     rcx, rsi
0x18004c2a3  mov     rax, [rax+8]
0x18004c2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2ac  nop
0x18004c2ad  lea     rcx, [rsp+58h+arg_8]
0x18004c2b2  call    ??1?$unique_ptr@VCallerIdentity@Library@DeviceCastle@@U?$default_delete@VCallerIdentity@Library@DeviceCastle@@@std@@@std@@QEAA@XZ; std::unique_ptr<DeviceCastle::Library::CallerIdentity>::~unique_ptr<DeviceCastle::Library::CallerIdentity>(void)
0x18004c2b7  nop
0x18004c2b8  jmp     loc_18004C409
0x18004c2bd  mov     rcx, [rdi+298h]; pwk
0x18004c2c4  test    rcx, rcx
0x18004c2c7  jz      short loc_18004C2E9
0x18004c2c9  xor     edx, edx; fCancelPendingCallbacks
0x18004c2cb  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18004c2d1  mov     rcx, [rdi+298h]; pwk
0x18004c2d8  call    cs:__imp_CloseThreadpoolWork
0x18004c2de  mov     qword ptr [rdi+298h], 0
0x18004c2e9  lea     r8, [rdi+250h]; pcbe
0x18004c2f0  mov     rdx, rsi; pv
0x18004c2f3  lea     rcx, ?HandleTapEvent@DeviceCastleInternal@Library@DeviceCastle@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18004c2fa  call    cs:__imp_CreateThreadpoolWork
0x18004c300  mov     [rdi+298h], rax
0x18004c307  test    rax, rax
0x18004c30a  jnz     short loc_18004C373
0x18004c30c  call    cs:__imp_GetLastError
0x18004c312  mov     ebx, eax
0x18004c314  test    eax, eax
0x18004c316  jle     short loc_18004C321
0x18004c318  movzx   ebx, ax
0x18004c31b  or      ebx, 80070000h
0x18004c321  mov     rsi, qword ptr [rsp+58h+var_28+8]
0x18004c326  test    rsi, rsi
0x18004c329  jz      short loc_18004C363
0x18004c32b  or      eax, 0FFFFFFFFh
0x18004c32e  lock xadd [rsi+8], eax
0x18004c333  cmp     eax, 1
0x18004c336  jnz     short loc_18004C363
0x18004c338  mov     rax, [rsi]
0x18004c33b  mov     rcx, rsi
0x18004c33e  mov     rax, [rax]
0x18004c341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c346  or      eax, 0FFFFFFFFh
0x18004c349  lock xadd [rsi+0Ch], eax
0x18004c34e  cmp     eax, 1
0x18004c351  jnz     short loc_18004C363
0x18004c353  mov     rax, [rsi]
0x18004c356  mov     rcx, rsi
0x18004c359  mov     rax, [rax+8]
0x18004c35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c362  nop
0x18004c363  lea     rcx, [rsp+58h+arg_8]
0x18004c368  call    ??1?$unique_ptr@VCallerIdentity@Library@DeviceCastle@@U?$default_delete@VCallerIdentity@Library@DeviceCastle@@@std@@@std@@QEAA@XZ; std::unique_ptr<DeviceCastle::Library::CallerIdentity>::~unique_ptr<DeviceCastle::Library::CallerIdentity>(void)
0x18004c36d  nop
0x18004c36e  jmp     loc_18004C409
0x18004c373  mov     rax, qword ptr [rsp+58h+var_28]
0x18004c378  mov     dword ptr [rax+0B0h], 8000000Ah
0x18004c382  mov     rcx, [rdi+298h]; pwk
0x18004c389  call    cs:__imp_SubmitThreadpoolWork
0x18004c38f  mov     [rsp+58h+arg_8], 0
0x18004c398  xor     ebx, ebx
0x18004c39a  mov     rsi, qword ptr [rsp+58h+var_28+8]
0x18004c39f  test    rsi, rsi
0x18004c3a2  jz      short loc_18004C3DC
0x18004c3a4  or      eax, 0FFFFFFFFh
0x18004c3a7  lock xadd [rsi+8], eax
0x18004c3ac  cmp     eax, 1
0x18004c3af  jnz     short loc_18004C3DC
0x18004c3b1  mov     rax, [rsi]
0x18004c3b4  mov     rcx, rsi
0x18004c3b7  mov     rax, [rax]
0x18004c3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c3bf  or      eax, 0FFFFFFFFh
0x18004c3c2  lock xadd [rsi+0Ch], eax
0x18004c3c7  cmp     eax, 1
0x18004c3ca  jnz     short loc_18004C3DC
0x18004c3cc  mov     rax, [rsi]
0x18004c3cf  mov     rcx, rsi
0x18004c3d2  mov     rax, [rax+8]
0x18004c3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c3db  nop
0x18004c3dc  lea     rcx, [rsp+58h+arg_8]
0x18004c3e1  call    ??1?$unique_ptr@VCallerIdentity@Library@DeviceCastle@@U?$default_delete@VCallerIdentity@Library@DeviceCastle@@@std@@@std@@QEAA@XZ; std::unique_ptr<DeviceCastle::Library::CallerIdentity>::~unique_ptr<DeviceCastle::Library::CallerIdentity>(void)
0x18004c3e6  nop
0x18004c3e7  jmp     short loc_18004C409
0x18004c3e9  dec     eax
0x18004c3eb  mov     [rsp+58h+var_38], eax
0x18004c3ef  lea     r9, aTapEventIgnore; "Tap event ignored due to %1!lu! events "...
0x18004c3f6  xor     r8d, r8d; struct DeviceCastle::Library::CallerIdentity *
0x18004c3f9  lea     edx, [r8+4]; unsigned int
0x18004c3fd  call    ?LogFormattedMessage@DeviceCastleInternal@Library@DeviceCastle@@QEBAXKPEAVCallerIdentity@23@PEBGZZ; DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(ulong,DeviceCastle::Library::CallerIdentity *,ushort const *,...)
0x18004c402  jmp     short loc_18004C409
0x18004c404  mov     ebx, 80070057h
0x18004c409  mov     ecx, [rdi+248h]
0x18004c40f  test    ecx, ecx
0x18004c411  jz      short loc_18004C41A
0x18004c413  lock dec dword ptr [rdi+248h]
0x18004c41a  mov     eax, ebx
0x18004c41c  mov     rbx, [rsp+58h+arg_10]
0x18004c421  mov     rsi, [rsp+58h+arg_18]
0x18004c426  add     rsp, 40h
0x18004c42a  pop     r15
0x18004c42c  pop     r14
0x18004c42e  pop     rdi
0x18004c42f  retn
```
