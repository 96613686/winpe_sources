# SerializedJobList::QueueSerializedJob(CJobBase *,IOperationCompletionCallback *)

- ea: `0x14002b1f4`
- end: `0x14002b34b`
- name: `?QueueSerializedJob@SerializedJobList@@QEAAHPEAVCJobBase@@PEAVIOperationCompletionCallback@@@Z`
- size: `343`
- prototype: `int(SerializedJobList *__hidden this, struct CJobBase *, struct IOperationCompletionCallback *)`
- caller_count: `18`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005d40`
- `0x140026010`
- `0x14002c7dc`
- `0x14002cb2c`
- `0x14002ce2c`
- `0x14002d0e0`
- `0x14002d660`
- `0x14002d934`
- `0x14002ea0c`
- `0x140055628`
- `0x140063be4`
- `0x140087340`
- `0x140087744`
- `0x140088afc`
- `0x14008a5a4`
- `0x14008b73c`
- `0x1400c996c`
- `0x1400ca1cc`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x140013bd0`
- `0x140018c14`
- `0x1400233e0`
- `0x14002b1f4`
- `0x140064210`

## pseudocode

```c
__int64 __fastcall SerializedJobList::QueueSerializedJob(
        EventQueue **this,
        struct CJobBase *a2,
        struct IOperationCompletionCallback *a3)
{
  CJobBase *v4; // rdi
  unsigned int FailsafeCompletionEvent; // ebx
  __int64 v8; // [rsp+28h] [rbp-40h]
  struct Event *v9; // [rsp+78h] [rbp+10h] BYREF

  v9 = 0;
  v4 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      12,
      (__int64)WPP_0f77f759e52d32c311e0fc29986c8506_Traceguids);
  }
  if ( v4 )
  {
    if ( *((_BYTE *)this + 72) )
    {
      FailsafeCompletionEvent = CJobBase::set_SerializedJobCompletionCallback(v4, a3);
      if ( !FailsafeCompletionEvent )
      {
        FailsafeCompletionEvent = CJobBase::get_FailsafeCompletionEvent(v4, &v9);
        if ( !FailsafeCompletionEvent )
        {
          FailsafeCompletionEvent = Event::PopulateEvent(
                                      v9,
                                      3,
                                      (unsigned __int64)(this + 1) & -(__int64)(this != 0),
                                      v4,
                                      0,
                                      0);
          if ( !FailsafeCompletionEvent )
            FailsafeCompletionEvent = EventQueue::QueueEvent(this[4], v9, 0);
        }
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          1,
          13,
          (__int64)WPP_0f77f759e52d32c311e0fc29986c8506_Traceguids);
      }
      FailsafeCompletionEvent = -1073741436;
    }
  }
  else
  {
    FailsafeCompletionEvent = -1073741811;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v8) = FailsafeCompletionEvent;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      14,
      (__int64)WPP_0f77f759e52d32c311e0fc29986c8506_Traceguids,
      v8);
  }
  return FailsafeCompletionEvent;
}

```

## disassembly

```asm
0x14002b1f4  push    rbx
0x14002b1f6  push    rbp
0x14002b1f7  push    rsi
0x14002b1f8  push    rdi
0x14002b1f9  push    r12
0x14002b1fb  push    r14
0x14002b1fd  sub     rsp, 38h
0x14002b201  xor     ebp, ebp
0x14002b203  mov     rbx, r8
0x14002b206  mov     [rsp+68h+arg_8], rbp
0x14002b20b  mov     rdi, rdx
0x14002b20e  mov     rsi, rcx
0x14002b211  lea     r14, WPP_RECORDER_INITIALIZED
0x14002b218  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14002b21f  lea     r12, WPP_0f77f759e52d32c311e0fc29986c8506_Traceguids
0x14002b226  jz      short loc_14002B255
0x14002b228  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b22f  cmp     byte ptr [rcx+29h], 5
0x14002b233  jnb     short loc_14002B23B
0x14002b235  cmp     [rcx+48h], bp
0x14002b239  jz      short loc_14002B255
0x14002b23b  mov     rcx, [rcx+40h]
0x14002b23f  mov     r9d, 0Ch
0x14002b245  mov     dl, 5
0x14002b247  mov     [rsp+68h+var_48], r12
0x14002b24c  lea     r8d, [r9-0Bh]
0x14002b250  call    WPP_RECORDER_SF_
0x14002b255  test    rdi, rdi
0x14002b258  jnz     short loc_14002B264
0x14002b25a  mov     ebx, 0C000000Dh
0x14002b25f  jmp     loc_14002B301
0x14002b264  cmp     [rsi+48h], bpl
0x14002b268  jnz     short loc_14002B29B
0x14002b26a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14002b271  jz      short loc_14002B294
0x14002b273  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b27a  mov     r9d, 0Dh
0x14002b280  mov     dl, 2
0x14002b282  mov     [rsp+68h+var_48], r12
0x14002b287  mov     rcx, [rcx+40h]
0x14002b28b  lea     r8d, [r9-0Ch]
0x14002b28f  call    WPP_RECORDER_SF_
0x14002b294  mov     ebx, 0C0000184h
0x14002b299  jmp     short loc_14002B301
0x14002b29b  mov     rdx, rbx; struct IOperationCompletionCallback *
0x14002b29e  mov     rcx, rdi; this
0x14002b2a1  call    ?set_SerializedJobCompletionCallback@CJobBase@@QEAAHPEAVIOperationCompletionCallback@@@Z; CJobBase::set_SerializedJobCompletionCallback(IOperationCompletionCallback *)
0x14002b2a6  mov     ebx, eax
0x14002b2a8  test    eax, eax
0x14002b2aa  jnz     short loc_14002B301
0x14002b2ac  lea     rdx, [rsp+68h+arg_8]; struct Event **
0x14002b2b1  mov     rcx, rdi; this
0x14002b2b4  call    ?get_FailsafeCompletionEvent@CJobBase@@QEAAHPEAPEAVEvent@@@Z; CJobBase::get_FailsafeCompletionEvent(Event * *)
0x14002b2b9  mov     ebx, eax
0x14002b2bb  test    eax, eax
0x14002b2bd  jnz     short loc_14002B301
0x14002b2bf  lea     rcx, [rsi+8]
0x14002b2c3  mov     dword ptr [rsp+68h+var_40], ebp
0x14002b2c7  mov     rax, rsi
0x14002b2ca  mov     [rsp+68h+var_48], rbp
0x14002b2cf  neg     rax
0x14002b2d2  lea     edx, [rbx+3]
0x14002b2d5  mov     r9, rdi
0x14002b2d8  sbb     r8, r8
0x14002b2db  and     r8, rcx
0x14002b2de  mov     rcx, [rsp+68h+arg_8]
0x14002b2e3  call    ?PopulateEvent@Event@@QEAAHW4_WFC_EVENT_TYPE@@PEAVIEventQueueCallback@@PEAX2H@Z; Event::PopulateEvent(_WFC_EVENT_TYPE,IEventQueueCallback *,void *,void *,int)
0x14002b2e8  mov     ebx, eax
0x14002b2ea  test    eax, eax
0x14002b2ec  jnz     short loc_14002B301
0x14002b2ee  mov     rdx, [rsp+68h+arg_8]; struct Event *
0x14002b2f3  xor     r8d, r8d; bool
0x14002b2f6  mov     rcx, [rsi+20h]; this
0x14002b2fa  call    ?QueueEvent@EventQueue@@QEAAHPEAVEvent@@_N@Z; EventQueue::QueueEvent(Event *,bool)
0x14002b2ff  mov     ebx, eax
0x14002b301  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14002b308  jz      short loc_14002B33B
0x14002b30a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b311  cmp     byte ptr [rcx+29h], 5
0x14002b315  jnb     short loc_14002B31D
0x14002b317  cmp     [rcx+48h], bp
0x14002b31b  jz      short loc_14002B33B
0x14002b31d  mov     rcx, [rcx+40h]
0x14002b321  mov     r9d, 0Eh
0x14002b327  mov     dword ptr [rsp+68h+var_40], ebx
0x14002b32b  mov     dl, 5
0x14002b32d  mov     [rsp+68h+var_48], r12
0x14002b332  lea     r8d, [r9-0Dh]
0x14002b336  call    WPP_RECORDER_SF_d
0x14002b33b  mov     eax, ebx
0x14002b33d  add     rsp, 38h
0x14002b341  pop     r14
0x14002b343  pop     r12
0x14002b345  pop     rdi
0x14002b346  pop     rsi
0x14002b347  pop     rbp
0x14002b348  pop     rbx
0x14002b349  retn
```
