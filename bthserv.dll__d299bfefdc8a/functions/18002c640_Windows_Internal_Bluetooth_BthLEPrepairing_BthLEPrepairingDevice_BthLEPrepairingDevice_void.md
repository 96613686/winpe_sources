# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::~BthLEPrepairingDevice(void)

- ea: `0x18002c640`
- end: `0x18002c7f6`
- name: `??1BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAA@XZ`
- size: `438`
- prototype: `void __fastcall(PTP_TIMER *this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x180029920`
- `0x18002b4a4`

## callees

- `0x180001b60`
- `0x18001140c`
- `0x18002c640`
- `0x18002efa0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c777`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c777`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002c78e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002c78e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002c785`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002c785`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c70e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c725`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c75d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c70e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c725`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c75d`
- `deviceassociation!DafMemFree` at `0x18002c7a6`
- `deviceassociation!DafMemFree` at `0x18002c7a6`
- `deviceassociation!DafCloseAssociationContext` at `0x18002c737`
- `deviceassociation!DafCloseAssociationContext` at `0x18002c737`

## pseudocode

```c
void __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::~BthLEPrepairingDevice(
        PTP_TIMER *this)
{
  bool v2; // dl
  const struct std::nothrow_t *v3; // rdx
  __int64 v4; // r8
  PTP_TIMER v5; // rcx
  PTP_TIMER v6; // rcx
  PTP_TIMER v7; // rcx
  PTP_TIMER v8; // rcx
  PTP_TIMER v9; // rcx
  struct _TP_TIMER *v10; // rdi
  PTP_TIMER v11; // rcx
  volatile signed __int32 *v12; // rbx

  v2 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Stop((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)this);
  LOBYTE(v3) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_BYTE)v3,
      v4,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v5 = this[257];
  if ( (unsigned __int64)v5 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  v6 = this[256];
  if ( (unsigned __int64)v6 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  v7 = this[255];
  if ( v7 )
    DafCloseAssociationContext(v7, v3, v4);
  v8 = this[16];
  if ( v8 )
    operator delete(v8, v3);
  v9 = this[15];
  if ( (unsigned __int64)v9 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  v10 = this[9];
  if ( v10 )
  {
    SetThreadpoolTimer(this[9], 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v10, 1);
    CloseThreadpoolTimer(v10);
  }
  v11 = this[8];
  this[8] = 0;
  if ( v11 )
    DafMemFree(v11, v3, v4);
  v12 = (volatile signed __int32 *)this[1];
  if ( v12 && _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *, const struct std::nothrow_t *, __int64))v12)(v12, v3, v4);
    if ( !_InterlockedDecrement(v12 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
  }
}

```

## disassembly

```asm
0x18002c640  push    rbx
0x18002c642  push    rbp
0x18002c643  push    rsi
0x18002c644  push    rdi
0x18002c645  sub     rsp, 58h
0x18002c649  mov     rbx, rcx
0x18002c64c  lea     rdi, WPP_GLOBAL_Control
0x18002c653  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c65a  cmp     rcx, rdi
0x18002c65d  jz      short loc_18002C669
0x18002c65f  cmp     byte ptr [rcx+19h], 5
0x18002c663  jb      short loc_18002C669
0x18002c665  mov     dl, 1
0x18002c667  jmp     short loc_18002C66B
0x18002c669  xor     dl, dl
0x18002c66b  lea     rsi, WPP_RECORDER_INITIALIZED
0x18002c672  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18002c679  setnz   r8b
0x18002c67d  lea     rbp, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002c684  test    dl, dl
0x18002c686  jnz     short loc_18002C68D
0x18002c688  test    r8b, r8b
0x18002c68b  jz      short loc_18002C6AB
0x18002c68d  mov     [rsp+78h+var_30], rbx
0x18002c692  mov     [rsp+78h+var_40], rbp
0x18002c697  mov     [rsp+78h+var_48], 0Ah
0x18002c69e  mov     r9, [rcx+28h]
0x18002c6a2  mov     rcx, [rcx+10h]
0x18002c6a6  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002c6ab  mov     rcx, rbx; this
0x18002c6ae  call    ?Stop@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Stop(void)
0x18002c6b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c6ba  cmp     rcx, rdi
0x18002c6bd  jz      short loc_18002C6C9
0x18002c6bf  cmp     byte ptr [rcx+19h], 5
0x18002c6c3  jb      short loc_18002C6C9
0x18002c6c5  mov     dl, 1
0x18002c6c7  jmp     short loc_18002C6CB
0x18002c6c9  xor     dl, dl
0x18002c6cb  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18002c6d2  setnz   r8b
0x18002c6d6  test    dl, dl
0x18002c6d8  jnz     short loc_18002C6DF
0x18002c6da  test    r8b, r8b
0x18002c6dd  jz      short loc_18002C6FD
0x18002c6df  mov     [rsp+78h+var_30], rbx
0x18002c6e4  mov     [rsp+78h+var_40], rbp
0x18002c6e9  mov     [rsp+78h+var_48], 0Bh
0x18002c6f0  mov     r9, [rcx+28h]
0x18002c6f4  mov     rcx, [rcx+10h]
0x18002c6f8  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002c6fd  mov     rcx, [rbx+808h]; hObject
0x18002c704  lea     rax, [rcx-1]
0x18002c708  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c70c  ja      short loc_18002C714
0x18002c70e  call    cs:__imp_CloseHandle
0x18002c714  mov     rcx, [rbx+800h]; hObject
0x18002c71b  lea     rax, [rcx-1]
0x18002c71f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c723  ja      short loc_18002C72B
0x18002c725  call    cs:__imp_CloseHandle
0x18002c72b  mov     rcx, [rbx+7F8h]
0x18002c732  test    rcx, rcx
0x18002c735  jz      short loc_18002C73E
0x18002c737  call    cs:__imp_DafCloseAssociationContext
0x18002c73d  nop
0x18002c73e  mov     rcx, [rbx+80h]; void *
0x18002c745  test    rcx, rcx
0x18002c748  jz      short loc_18002C74F
0x18002c74a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c74f  mov     rcx, [rbx+78h]; hObject
0x18002c753  lea     rax, [rcx-1]
0x18002c757  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c75b  ja      short loc_18002C763
0x18002c75d  call    cs:__imp_CloseHandle
0x18002c763  mov     rdi, [rbx+48h]
0x18002c767  test    rdi, rdi
0x18002c76a  jz      short loc_18002C795
0x18002c76c  xor     r9d, r9d; msWindowLength
0x18002c76f  xor     r8d, r8d; msPeriod
0x18002c772  xor     edx, edx; pftDueTime
0x18002c774  mov     rcx, rdi; pti
0x18002c777  call    cs:__imp_SetThreadpoolTimer
0x18002c77d  mov     edx, 1; fCancelPendingCallbacks
0x18002c782  mov     rcx, rdi; pti
0x18002c785  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002c78b  mov     rcx, rdi; pti
0x18002c78e  call    cs:__imp_CloseThreadpoolTimer
0x18002c794  nop
0x18002c795  mov     rcx, [rbx+40h]
0x18002c799  mov     qword ptr [rbx+40h], 0
0x18002c7a1  test    rcx, rcx
0x18002c7a4  jz      short loc_18002C7AD
0x18002c7a6  call    cs:__imp_DafMemFree
0x18002c7ac  nop
0x18002c7ad  mov     rbx, [rbx+8]
0x18002c7b1  test    rbx, rbx
0x18002c7b4  jz      short loc_18002C7ED
0x18002c7b6  or      edi, 0FFFFFFFFh
0x18002c7b9  mov     eax, edi
0x18002c7bb  lock xadd [rbx+8], eax
0x18002c7c0  add     eax, edi
0x18002c7c2  jnz     short loc_18002C7ED
0x18002c7c4  mov     rax, [rbx]
0x18002c7c7  mov     rcx, rbx
0x18002c7ca  mov     rax, [rax]
0x18002c7cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7d2  mov     eax, edi
0x18002c7d4  lock xadd [rbx+0Ch], eax
0x18002c7d9  add     eax, edi
0x18002c7db  jnz     short loc_18002C7ED
0x18002c7dd  mov     rax, [rbx]
0x18002c7e0  mov     rcx, rbx
0x18002c7e3  mov     rax, [rax+8]
0x18002c7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7ec  nop
0x18002c7ed  add     rsp, 58h
0x18002c7f1  pop     rdi
0x18002c7f2  pop     rsi
0x18002c7f3  pop     rbp
0x18002c7f4  pop     rbx
0x18002c7f5  retn
```
