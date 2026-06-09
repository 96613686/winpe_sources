# CSerialWorkQueue::QueueWaitItemInternal(void *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long),std::function<void (void)>,std::unique_ptr<_WaitTask,std::default_delete<_WaitTask>> &)

- ea: `0x140058c50`
- end: `0x140058dc2`
- name: `?QueueWaitItemInternal@CSerialWorkQueue@@AEAAJPEAXP6AXPEAU_TP_CALLBACK_INSTANCE@@0PEAU_TP_WAIT@@J@ZV?$function@$$A6AXXZ@std@@AEAV?$unique_ptr@U_WaitTask@@U?$default_delete@U_WaitTask@@@std@@@5@@Z`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x140058bd8`

## callees

- `0x14000f1a4`
- `0x14000f3b8`
- `0x140058c50`
- `0x14005d148`
- `0x14008e074`
- `0x14008e25c`
- `0x14008fd6c`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058d2d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140058d59`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140058d59`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140058d1f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140058d1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 CSerialWorkQueue::QueueWaitItemInternal(__int64 a1, void *a2, ...)
{
  __int64 v2; // rbp
  void *v3; // r14
  int v5; // edi
  PTP_WAIT *v6; // rax
  PTP_WAIT *v7; // rbx
  __int64 v8; // rax
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *v10; // rsi
  signed int LastError; // eax
  PTP_WAIT *v12; // rdx
  __int64 v13; // rcx
  char v15[104]; // [rsp+20h] [rbp-68h] BYREF
  PTP_WAIT *v16; // [rsp+A0h] [rbp+18h] BYREF
  va_list va; // [rsp+A0h] [rbp+18h]
  __int64 v18; // [rsp+A8h] [rbp+20h]
  PTP_WAIT **v19; // [rsp+B0h] [rbp+28h]
  va_list va1; // [rsp+B8h] [rbp+30h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  v16 = va_arg(va1, PTP_WAIT *);
  v18 = va_arg(va1, _QWORD);
  v19 = va_arg(va1, PTP_WAIT **);
  v2 = v18;
  v3 = a2;
  v5 = 0;
  if ( !*(_BYTE *)(a1 + 80) )
  {
    v5 = CSerialWorkQueue::Initialize((PTP_POOL *)a1);
    if ( v5 >= 0 )
    {
      v6 = (PTP_WAIT *)operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
      v7 = v6;
      v16 = v6;
      if ( v6 )
      {
        *v6 = 0;
        v6[1] = 0;
        v6[2] = 0;
        v6[3] = 0;
        v6[4] = 0;
      }
      else
      {
        v7 = 0;
      }
      v16 = v7;
      if ( v7 )
      {
        v8 = std::function<void (void)>::function<void (void)>(v15, v2);
        v5 = _WaitTask::Initialize(v7, v3, v8, a1);
        if ( v5 >= 0 )
        {
          ThreadpoolWait = CreateThreadpoolWait(CSerialWorkQueue::WaitCallback, v7, (PTP_CALLBACK_ENVIRON)(a1 + 8));
          v10 = ThreadpoolWait;
          if ( ThreadpoolWait )
          {
            v5 = 0;
            *v7 = ThreadpoolWait;
          }
          else
          {
            LastError = GetLastError();
            v5 = LastError;
            if ( LastError > 0 )
              v5 = (unsigned __int16)LastError | 0x80070000;
            *v7 = 0;
            if ( v5 < 0 )
              goto LABEL_17;
          }
          SetThreadpoolWait(v10, v3, 0);
          v16 = 0;
          v12 = *v19;
          *v19 = v7;
          if ( v12 )
            std::default_delete<_WaitTask>::operator()();
        }
      }
      else
      {
        v5 = -2147024882;
      }
LABEL_17:
      std::unique_ptr<_WaitTask>::~unique_ptr<_WaitTask>((PTP_WAIT **)va);
    }
  }
  v13 = *(_QWORD *)(v2 + 56);
  if ( v13 )
  {
    LOBYTE(a2) = v13 != v2;
    (*(void (__fastcall **)(__int64, void *))(*(_QWORD *)v13 + 32LL))(v13, a2);
    *(_QWORD *)(v2 + 56) = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140058c50  mov     [rsp+arg_18], r9
0x140058c55  mov     [rsp+arg_10], r8
0x140058c5a  push    rbx
0x140058c5b  push    rbp
0x140058c5c  push    rsi
0x140058c5d  push    rdi
0x140058c5e  push    r14
0x140058c60  sub     rsp, 60h
0x140058c64  mov     rbp, r9
0x140058c67  mov     r14, rdx
0x140058c6a  mov     rsi, rcx
0x140058c6d  xor     edi, edi
0x140058c6f  mov     al, [rcx+50h]
0x140058c72  nop
0x140058c73  test    al, al
0x140058c75  jnz     loc_140058D92
0x140058c7b  call    ?Initialize@CSerialWorkQueue@@AEAAJXZ; CSerialWorkQueue::Initialize(void)
0x140058c80  mov     edi, eax
0x140058c82  test    eax, eax
0x140058c84  js      loc_140058D92
0x140058c8a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140058c91  mov     ecx, 28h ; '('; unsigned __int64
0x140058c96  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140058c9b  mov     rbx, rax
0x140058c9e  mov     [rsp+88h+arg_10], rax
0x140058ca6  test    rax, rax
0x140058ca9  jz      short loc_140058CD4
0x140058cab  mov     qword ptr [rax], 0
0x140058cb2  mov     qword ptr [rax+8], 0
0x140058cba  mov     qword ptr [rax+10h], 0
0x140058cc2  mov     qword ptr [rax+18h], 0
0x140058cca  mov     qword ptr [rax+20h], 0
0x140058cd2  jmp     short loc_140058CD6
0x140058cd4  xor     ebx, ebx
0x140058cd6  mov     [rsp+88h+arg_10], rbx
0x140058cde  test    rbx, rbx
0x140058ce1  jnz     short loc_140058CED
0x140058ce3  mov     edi, 8007000Eh
0x140058ce8  jmp     loc_140058D84
0x140058ced  mov     rdx, rbp
0x140058cf0  lea     rcx, [rsp+88h+var_68]
0x140058cf5  call    ??0?$function@$$A6AXXZ@std@@QEAA@AEBV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> const &)
0x140058cfa  mov     r9, rsi
0x140058cfd  mov     r8, rax
0x140058d00  mov     rdx, r14
0x140058d03  mov     rcx, rbx
0x140058d06  call    ?Initialize@_WaitTask@@QEAAJPEAXV?$function@$$A6AXXZ@std@@PEAVCSerialWorkQueue@@@Z; _WaitTask::Initialize(void *,std::function<void (void)>,CSerialWorkQueue *)
0x140058d0b  mov     edi, eax
0x140058d0d  test    eax, eax
0x140058d0f  js      short loc_140058D84
0x140058d11  lea     r8, [rsi+8]; pcbe
0x140058d15  mov     rdx, rbx; pv
0x140058d18  lea     rcx, ?WaitCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x140058d1f  call    cs:__imp_CreateThreadpoolWait
0x140058d25  mov     rsi, rax
0x140058d28  test    rax, rax
0x140058d2b  jnz     short loc_140058D4B
0x140058d2d  call    cs:__imp_GetLastError
0x140058d33  mov     edi, eax
0x140058d35  test    eax, eax
0x140058d37  jle     short loc_140058D42
0x140058d39  movzx   edi, ax
0x140058d3c  or      edi, 80070000h
0x140058d42  mov     [rbx], rsi
0x140058d45  test    edi, edi
0x140058d47  js      short loc_140058D84
0x140058d49  jmp     short loc_140058D50
0x140058d4b  xor     edi, edi
0x140058d4d  mov     [rbx], rsi
0x140058d50  xor     r8d, r8d; pftTimeout
0x140058d53  mov     rdx, r14; h
0x140058d56  mov     rcx, rsi; pwa
0x140058d59  call    cs:__imp_SetThreadpoolWait
0x140058d5f  mov     [rsp+88h+arg_10], 0
0x140058d6b  mov     rax, [rsp+88h+arg_20]
0x140058d73  mov     rdx, [rax]
0x140058d76  mov     [rax], rbx
0x140058d79  test    rdx, rdx
0x140058d7c  jz      short loc_140058D84
0x140058d7e  call    ??R?$default_delete@U_WaitTask@@@std@@QEBAXPEAU_WaitTask@@@Z; std::default_delete<_WaitTask>::operator()(_WaitTask *)
0x140058d83  nop
0x140058d84  lea     rcx, [rsp+88h+arg_10]
0x140058d8c  call    ??1?$unique_ptr@U_WaitTask@@U?$default_delete@U_WaitTask@@@std@@@std@@QEAA@XZ; std::unique_ptr<_WaitTask>::~unique_ptr<_WaitTask>(void)
0x140058d91  nop
0x140058d92  mov     rcx, [rbp+38h]
0x140058d96  test    rcx, rcx
0x140058d99  jz      short loc_140058DB5
0x140058d9b  mov     rax, [rcx]
0x140058d9e  cmp     rcx, rbp
0x140058da1  setnz   dl
0x140058da4  mov     rax, [rax+20h]
0x140058da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058dad  mov     qword ptr [rbp+38h], 0
0x140058db5  mov     eax, edi
0x140058db7  add     rsp, 60h
0x140058dbb  pop     r14
0x140058dbd  pop     rdi
0x140058dbe  pop     rsi
0x140058dbf  pop     rbp
0x140058dc0  pop     rbx
0x140058dc1  retn
```
