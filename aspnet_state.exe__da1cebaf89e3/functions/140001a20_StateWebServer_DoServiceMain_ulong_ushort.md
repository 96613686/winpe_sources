# StateWebServer::DoServiceMain(ulong,ushort * *)

- ea: `0x140001a20`
- end: `0x140001c90`
- name: `?DoServiceMain@StateWebServer@@AEAAXKPEAPEAG@Z`
- size: `624`
- prototype: `void __fastcall(StateWebServer *this, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task`

## callers

- `0x140001cf0`

## callees

- `0x140001a20`
- `0x140001d04`
- `0x14000210c`
- `0x1400021b8`
- `0x140002200`
- `0x1400022a0`
- `0x14000248c`
- `0x1400027ec`
- `0x140002840`
- `0x140004f2c`
- `0x140004fc8`
- `0x1400052d0`
- `0x140005374`

## import_xrefs

- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x140001a54`
- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x140001a54`
- `KERNEL32!WaitForSingleObject` at `0x140001add`
- `KERNEL32!WaitForSingleObject` at `0x140001add`

## pseudocode

```c
void __fastcall StateWebServer::DoServiceMain(StateWebServer *this, __int64 a2, unsigned __int16 **a3)
{
  int v4; // esi
  char v5; // r12
  SERVICE_STATUS_HANDLE v6; // rax
  unsigned int started; // edi
  _QWORD **v8; // r15
  int v9; // esi
  int v10; // esi
  int v11; // esi
  int v12; // esi
  unsigned int v13; // edx
  unsigned int v14; // r8d
  _DWORD *v15; // r14
  _QWORD *v16; // rax

  LOBYTE(v4) = 0;
  v5 = 1;
  v6 = RegisterServiceCtrlHandlerW(StateWebServer::s_serviceName, StateWebServer::ServiceCtrlHandler);
  *((_QWORD *)this + 10) = v6;
  if ( v6 )
  {
    StateWebServer::SetServiceStatus(this, 2u, 0, 0x64u);
    started = StateWebServer::PrepareToRun(this);
    if ( started
      || (started = StateWebServer::StartListening(this)) != 0
      || (started = StateWebServer::StartSocketTimer(this)) != 0 )
    {
LABEL_28:
      StateWebServer::SetServiceStatus(this, 1u, started, 0);
      goto LABEL_29;
    }
    StateWebServer::SetServiceStatus(this, 4u, 0, 0);
    v5 = 0;
    v8 = (_QWORD **)((char *)this + 96);
LABEL_7:
    WaitForSingleObject(*((HANDLE *)this + 8), 0xFFFFFFFF);
    while ( 1 )
    {
      while ( 1 )
      {
        CReadWriteSpinLock::AcquireWriterLock((StateWebServer *)((char *)this + 112));
        v15 = *v8;
        v16 = (_QWORD *)**v8;
        *v8 = v16;
        v16[1] = v8;
        CReadWriteSpinLock::ReleaseWriterLock((StateWebServer *)((char *)this + 112));
        if ( v15 == (_DWORD *)v8 )
          goto LABEL_7;
        v9 = v15[4];
        MemFree(v15);
        v10 = v9 - 1;
        if ( !v10 )
        {
          StateWebServer::SetServiceStatus(this, 3u, 0, 0x64u);
          StateWebServer::StopSocketTimer(this);
          StateWebServer::StopListening(this);
          StateWebServer::WaitForZeroTrackers(this);
          StateWebServer::CleanupAfterRunning(this);
          LOBYTE(v4) = 1;
          StateWebServer::SetServiceStatus(this, 1u, 0, 0);
          goto LABEL_26;
        }
        v11 = v10 - 1;
        if ( !v11 )
          break;
        v12 = v11 - 1;
        if ( v12 )
        {
          v4 = v12 - 1;
          if ( !v4 )
          {
            v13 = *((_DWORD *)this + 22);
LABEL_21:
            v14 = 0;
            goto LABEL_22;
          }
          if ( v4 == 1 )
          {
            StateWebServer::StopSocketTimer(this);
            StateWebServer::StopListening(this);
            StateWebServer::WaitForZeroTrackers(this);
            StateWebServer::CleanupAfterRunning(this);
            goto LABEL_26;
          }
        }
        else if ( *((_DWORD *)this + 22) == 7 )
        {
          StateWebServer::SetServiceStatus(this, 5u, 0, 0x64u);
          started = StateWebServer::StartListening(this);
          if ( !started )
            started = StateWebServer::StartSocketTimer(this);
          v14 = started;
          v13 = started != 0 ? 7 : 4;
LABEL_22:
          StateWebServer::SetServiceStatus(this, v13, v14, 0);
        }
      }
      if ( *((_DWORD *)this + 22) == 4 )
      {
        StateWebServer::SetServiceStatus(this, 6u, 0, 0x64u);
        StateWebServer::StopSocketTimer(this);
        StateWebServer::StopListening(this);
        StateWebServer::WaitForZeroTrackers(this);
        v13 = 7;
        goto LABEL_21;
      }
    }
  }
  started = GetLastWin32Error();
LABEL_26:
  if ( started && v5 )
    goto LABEL_28;
LABEL_29:
  if ( !(_BYTE)v4 )
    StateWebServer::CleanupAfterRunning(this);
}

```

## disassembly

```asm
0x140001a20  mov     rax, rsp
0x140001a23  mov     [rax+8], rbx
0x140001a27  mov     [rax+10h], rbp
0x140001a2b  mov     [rax+18h], rsi
0x140001a2f  mov     [rax+20h], rdi
0x140001a33  push    r12
0x140001a35  push    r14
0x140001a37  push    r15
0x140001a39  sub     rsp, 20h
0x140001a3d  mov     rbx, rcx
0x140001a40  lea     rdx, ?ServiceCtrlHandler@StateWebServer@@CAXK@Z; lpHandlerProc
0x140001a47  lea     rcx, ?s_serviceName@StateWebServer@@0PAGA; "aspnet_state"
0x140001a4e  xor     sil, sil
0x140001a51  mov     r12b, 1
0x140001a54  call    cs:__imp_RegisterServiceCtrlHandlerW
0x140001a5a  mov     [rbx+50h], rax
0x140001a5e  test    rax, rax
0x140001a61  jnz     short loc_140001A6F
0x140001a63  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x140001a68  mov     edi, eax
0x140001a6a  jmp     loc_140001C49
0x140001a6f  mov     r9d, 64h ; 'd'; unsigned int
0x140001a75  xor     r8d, r8d; unsigned int
0x140001a78  mov     rcx, rbx; this
0x140001a7b  lea     edx, [r9-62h]; unsigned int
0x140001a7f  call    ?SetServiceStatus@StateWebServer@@AEAAXKKK@Z; StateWebServer::SetServiceStatus(ulong,ulong,ulong)
0x140001a84  mov     rcx, rbx; this
0x140001a87  call    ?PrepareToRun@StateWebServer@@AEAAJXZ; StateWebServer::PrepareToRun(void)
0x140001a8c  mov     edi, eax
0x140001a8e  test    eax, eax
0x140001a90  jnz     loc_140001C52
0x140001a96  mov     rcx, rbx; this
0x140001a99  call    ?StartListening@StateWebServer@@AEAAJXZ; StateWebServer::StartListening(void)
0x140001a9e  mov     edi, eax
0x140001aa0  test    eax, eax
0x140001aa2  jnz     loc_140001C52
0x140001aa8  mov     rcx, rbx; this
0x140001aab  call    ?StartSocketTimer@StateWebServer@@AEAAJXZ; StateWebServer::StartSocketTimer(void)
0x140001ab0  mov     edi, eax
0x140001ab2  test    eax, eax
0x140001ab4  jnz     loc_140001C52
0x140001aba  xor     r9d, r9d; unsigned int
0x140001abd  lea     edx, [rax+4]; unsigned int
0x140001ac0  xor     r8d, r8d; unsigned int
0x140001ac3  mov     rcx, rbx; this
0x140001ac6  call    ?SetServiceStatus@StateWebServer@@AEAAXKKK@Z; StateWebServer::SetServiceStatus(ulong,ulong,ulong)
0x140001acb  xor     r12b, r12b
0x140001ace  lea     rbp, [rbx+70h]
0x140001ad2  lea     r15, [rbx+60h]
0x140001ad6  mov     rcx, [rbx+40h]; hHandle
0x140001ada  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140001add  call    cs:__imp_WaitForSingleObject
0x140001ae3  jmp     loc_140001BD4
0x140001ae8  mov     esi, [r14+10h]
0x140001aec  mov     rcx, r14; lpMem
0x140001aef  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x140001af4  sub     esi, 1
0x140001af7  jz      loc_140001BFF
0x140001afd  sub     esi, 1
0x140001b00  jz      loc_140001B8E
0x140001b06  sub     esi, 1
0x140001b09  jz      short loc_140001B46
0x140001b0b  sub     esi, 1
0x140001b0e  jz      short loc_140001B3E
0x140001b10  cmp     esi, 1
0x140001b13  jnz     loc_140001BD4
0x140001b19  mov     rcx, rbx; this
0x140001b1c  call    ?StopSocketTimer@StateWebServer@@AEAAJXZ; StateWebServer::StopSocketTimer(void)
0x140001b21  mov     rcx, rbx; this
0x140001b24  call    ?StopListening@StateWebServer@@AEAAXXZ; StateWebServer::StopListening(void)
0x140001b29  mov     rcx, rbx; this
0x140001b2c  call    ?WaitForZeroTrackers@StateWebServer@@AEAAJXZ; StateWebServer::WaitForZeroTrackers(void)
0x140001b31  mov     rcx, rbx; this
0x140001b34  call    ?CleanupAfterRunning@StateWebServer@@AEAAXXZ; StateWebServer::CleanupAfterRunning(void)
0x140001b39  jmp     loc_140001C49
0x140001b3e  mov     edx, [rbx+58h]
0x140001b41  jmp     loc_140001BC6
0x140001b46  cmp     dword ptr [rbx+58h], 7
0x140001b4a  jnz     loc_140001BD4
0x140001b50  mov     r9d, 64h ; 'd'; unsigned int
0x140001b56  xor     r8d, r8d; unsigned int
0x140001b59  mov     rcx, rbx; this
0x140001b5c  lea     edx, [r9-5Fh]; unsigned int
0x140001b60  call    ?SetServiceStatus@StateWebServer@@AEAAXKKK@Z; StateWebServer::SetServiceStatus(ulong,ulong,ulong)
0x140001b65  mov     rcx, rbx; this
0x140001b68  call    ?StartListening@StateWebServer@@AEAAJXZ; StateWebServer::StartListening(void)
0x140001b6d  mov     edi, eax
0x140001b6f  test    eax, eax
0x140001b71  jnz     short loc_140001B7D
0x140001b73  mov     rcx, rbx; this
0x140001b76  call    ?StartSocketTimer@StateWebServer@@AEAAJXZ; StateWebServer::StartSocketTimer(void)
0x140001b7b  mov     edi, eax
0x140001b7d  mov     eax, edi
0x140001b7f  mov     r8d, edi
0x140001b82  neg     eax
0x140001b84  sbb     edx, edx
0x140001b86  and     edx, 3
0x140001b89  add     edx, 4
0x140001b8c  jmp     short loc_140001BC9
0x140001b8e  cmp     dword ptr [rbx+58h], 4
0x140001b92  jnz     short loc_140001BD4
0x140001b94  mov     r9d, 64h ; 'd'; unsigned int
0x140001b9a  xor     r8d, r8d; unsigned int
0x140001b9d  mov     rcx, rbx; this
0x140001ba0  lea     edx, [r9-5Eh]; unsigned int
0x140001ba4  call    ?SetServiceStatus@StateWebServer@@AEAAXKKK@Z; StateWebServer::SetServiceStatus(ulong,ulong,ulong)
0x140001ba9  mov     rcx, rbx; this
0x140001bac  call    ?StopSocketTimer@StateWebServer@@AEAAJXZ; StateWebServer::StopSocketTimer(void)
0x140001bb1  mov     rcx, rbx; this
0x140001bb4  call    ?StopListening@StateWebServer@@AEAAXXZ; StateWebServer::StopListening(void)
0x140001bb9  mov     rcx, rbx; this
0x140001bbc  call    ?WaitForZeroTrackers@StateWebServer@@AEAAJXZ; StateWebServer::WaitForZeroTrackers(void)
0x140001bc1  mov     edx, 7; unsigned int
0x140001bc6  xor     r8d, r8d; unsigned int
0x140001bc9  xor     r9d, r9d; unsigned int
0x140001bcc  mov     rcx, rbx; this
0x140001bcf  call    ?SetServiceStatus@StateWebServer@@AEAAXKKK@Z; StateWebServer::SetServiceStatus(ulong,ulong,ulong)
0x140001bd4  mov     rcx, rbp; this
0x140001bd7  call    ?AcquireWriterLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::AcquireWriterLock(void)
0x140001bdc  mov     r14, [r15]
0x140001bdf  mov     rcx, rbp; this
0x140001be2  mov     rax, [r14]
0x140001be5  mov     [r15], rax
0x140001be8  mov     [rax+8], r15
0x140001bec  call    ?ReleaseWriterLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::ReleaseWriterLock(void)
0x140001bf1  cmp     r14, r15
0x140001bf4  jnz     loc_140001AE8
0x140001bfa  jmp     loc_140001AD6
0x140001bff  mov     r9d, 64h ; 'd'; unsigned int
0x140001c05  xor     r8d, r8d; unsigned int
0x140001c08  mov     rcx, rbx; this
0x140001c0b  lea     edx, [r9-61h]; unsigned int
0x140001c0f  call    ?SetServiceStatus@StateWebServer@@AEAAXKKK@Z; StateWebServer::SetServiceStatus(ulong,ulong,ulong)
0x140001c14  mov     rcx, rbx; this
0x140001c17  call    ?StopSocketTimer@StateWebServer@@AEAAJXZ; StateWebServer::StopSocketTimer(void)
0x140001c1c  mov     rcx, rbx; this
0x140001c1f  call    ?StopListening@StateWebServer@@AEAAXXZ; StateWebServer::StopListening(void)
0x140001c24  mov     rcx, rbx; this
0x140001c27  call    ?WaitForZeroTrackers@StateWebServer@@AEAAJXZ; StateWebServer::WaitForZeroTrackers(void)
0x140001c2c  mov     rcx, rbx; this
0x140001c2f  call    ?CleanupAfterRunning@StateWebServer@@AEAAXXZ; StateWebServer::CleanupAfterRunning(void)
0x140001c34  xor     r9d, r9d; unsigned int
0x140001c37  xor     r8d, r8d; unsigned int
0x140001c3a  mov     rcx, rbx; this
0x140001c3d  mov     sil, 1
0x140001c40  lea     edx, [r9+1]; unsigned int
0x140001c44  call    ?SetServiceStatus@StateWebServer@@AEAAXKKK@Z; StateWebServer::SetServiceStatus(ulong,ulong,ulong)
0x140001c49  test    edi, edi
0x140001c4b  jz      short loc_140001C64
0x140001c4d  test    r12b, r12b
0x140001c50  jz      short loc_140001C64
0x140001c52  xor     r9d, r9d; unsigned int
0x140001c55  mov     r8d, edi; unsigned int
0x140001c58  mov     rcx, rbx; this
0x140001c5b  lea     edx, [r9+1]; unsigned int
0x140001c5f  call    ?SetServiceStatus@StateWebServer@@AEAAXKKK@Z; StateWebServer::SetServiceStatus(ulong,ulong,ulong)
0x140001c64  test    sil, sil
0x140001c67  jnz     short loc_140001C71
0x140001c69  mov     rcx, rbx; this
0x140001c6c  call    ?CleanupAfterRunning@StateWebServer@@AEAAXXZ; StateWebServer::CleanupAfterRunning(void)
0x140001c71  mov     rbx, [rsp+38h+arg_0]
0x140001c76  mov     rbp, [rsp+38h+arg_8]
0x140001c7b  mov     rsi, [rsp+38h+arg_10]
0x140001c80  mov     rdi, [rsp+38h+arg_18]
0x140001c85  add     rsp, 20h
0x140001c89  pop     r15
0x140001c8b  pop     r14
0x140001c8d  pop     r12
0x140001c8f  retn
```
