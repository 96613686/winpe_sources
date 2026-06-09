# A2dpRole::SetPinLink(_KSPIN *)

- ea: `0x140011538`
- end: `0x140011652`
- name: `?SetPinLink@A2dpRole@@QEAAJPEAU_KSPIN@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(A2dpRole *__hidden this, struct _KSPIN *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140083430`
- `0x140083540`

## callees

- `0x140003530`
- `0x140011538`
- `0x14002bd64`
- `0x14002bd9c`
- `0x14002c124`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x14001162a`
- `ntoskrnl!KeResetEvent` at `0x14001162a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400115f7`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400115f7`

## pseudocode

```c
__int64 __fastcall A2dpRole::SetPinLink(A2dpRole *this, struct _KSPIN *a2)
{
  struct _KSPIN *v2; // rbp
  volatile int *v4; // rcx
  unsigned int v5; // edi

  v2 = a2;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      24,
      (__int64)WPP_7c0da6a8da193713e093ba9e03de3d02_Traceguids,
      (char)this);
  if ( (int)InterlockedIncrementFloor((volatile int *)this + 10, (int)a2) > 0 )
  {
    InterlockedDecrementWithZeroEvent(v4, (struct _KEVENT *)this + 2);
    InterlockedDecrementWithZeroEvent((volatile int *)this + 10, (struct _KEVENT *)this + 2);
    KeWaitForSingleObject((char *)this + 48, Executive, 0, 0, 0);
  }
  if ( *((_QWORD *)this + 4) && v2 )
  {
    return (unsigned int)-1073741670;
  }
  else
  {
    v5 = 0;
    if ( v2 )
    {
      *((_QWORD *)this + 4) = v2;
      *((_DWORD *)this + 10) = 1;
      KeResetEvent((PRKEVENT)this + 2);
      A2dpRole::LogPinCreate(this);
    }
    else
    {
      *((_QWORD *)this + 4) = 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140011538  push    rbx
0x14001153a  push    rbp
0x14001153b  push    rsi
0x14001153c  push    rdi
0x14001153d  push    r14
0x14001153f  sub     rsp, 50h
0x140011543  mov     rbp, rdx
0x140011546  mov     rbx, rcx
0x140011549  mov     rcx, cs:WPP_GLOBAL_Control
0x140011550  lea     rax, WPP_GLOBAL_Control
0x140011557  cmp     rcx, rax
0x14001155a  jz      short loc_14001156D
0x14001155c  mov     eax, [rcx+2Ch]
0x14001155f  test    al, 10h
0x140011561  jz      short loc_14001156D
0x140011563  cmp     byte ptr [rcx+29h], 4
0x140011567  jb      short loc_14001156D
0x140011569  mov     dl, 1
0x14001156b  jmp     short loc_14001156F
0x14001156d  xor     dl, dl
0x14001156f  lea     rax, WPP_RECORDER_INITIALIZED
0x140011576  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001157d  setnz   r8b
0x140011581  test    dl, dl
0x140011583  jnz     short loc_14001158A
0x140011585  test    r8b, r8b
0x140011588  jz      short loc_1400115BC
0x14001158a  mov     r9, [rcx+40h]
0x14001158e  lea     rax, WPP_7c0da6a8da193713e093ba9e03de3d02_Traceguids
0x140011595  mov     rcx, [rcx+18h]
0x140011599  mov     [rsp+78h+var_38], rbx
0x14001159e  mov     [rsp+78h+var_40], rax
0x1400115a3  mov     [rsp+78h+var_48], 18h
0x1400115aa  mov     [rsp+78h+var_50], 5
0x1400115b2  mov     byte ptr [rsp+78h+Timeout], 4
0x1400115b7  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400115bc  lea     rsi, [rbx+28h]
0x1400115c0  mov     rcx, rsi; volatile int *
0x1400115c3  lea     r14, [rbx+30h]
0x1400115c7  call    ?InterlockedIncrementFloor@@YAJPECJJ@Z; InterlockedIncrementFloor(long volatile *,long)
0x1400115cc  test    eax, eax
0x1400115ce  jle     short loc_140011603
0x1400115d0  mov     rdx, r14; struct _KEVENT *
0x1400115d3  call    ?InterlockedDecrementWithZeroEvent@@YAJPECJPEAU_KEVENT@@@Z; InterlockedDecrementWithZeroEvent(long volatile *,_KEVENT *)
0x1400115d8  mov     rdx, r14; struct _KEVENT *
0x1400115db  mov     rcx, rsi; volatile int *
0x1400115de  call    ?InterlockedDecrementWithZeroEvent@@YAJPECJPEAU_KEVENT@@@Z; InterlockedDecrementWithZeroEvent(long volatile *,_KEVENT *)
0x1400115e3  xor     r9d, r9d; Alertable
0x1400115e6  mov     [rsp+78h+Timeout], 0; Timeout
0x1400115ef  xor     r8d, r8d; WaitMode
0x1400115f2  xor     edx, edx; WaitReason
0x1400115f4  mov     rcx, r14; Object
0x1400115f7  call    cs:__imp_KeWaitForSingleObject
0x1400115fe  nop     dword ptr [rax+rax+00h]
0x140011603  cmp     qword ptr [rbx+20h], 0
0x140011608  jz      short loc_140011616
0x14001160a  test    rbp, rbp
0x14001160d  jz      short loc_140011616
0x14001160f  mov     edi, 0C000009Ah
0x140011614  jmp     short loc_140011644
0x140011616  xor     edi, edi
0x140011618  test    rbp, rbp
0x14001161b  jz      short loc_140011640
0x14001161d  mov     rcx, r14; Event
0x140011620  mov     [rbx+20h], rbp
0x140011624  mov     dword ptr [rsi], 1
0x14001162a  call    cs:__imp_KeResetEvent
0x140011631  nop     dword ptr [rax+rax+00h]
0x140011636  mov     rcx, rbx; this
0x140011639  call    ?LogPinCreate@A2dpRole@@AEAAXXZ; A2dpRole::LogPinCreate(void)
0x14001163e  jmp     short loc_140011644
0x140011640  mov     [rbx+20h], rdi
0x140011644  mov     eax, edi
0x140011646  add     rsp, 50h
0x14001164a  pop     r14
0x14001164c  pop     rdi
0x14001164d  pop     rsi
0x14001164e  pop     rbp
0x14001164f  pop     rbx
0x140011650  retn
```
