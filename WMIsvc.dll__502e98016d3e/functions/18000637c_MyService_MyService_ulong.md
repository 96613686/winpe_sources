# MyService::MyService(ulong)

- ea: `0x18000637c`
- end: `0x18000640c`
- name: `??0MyService@@QEAA@K@Z`
- size: `144`
- prototype: `MyService *__fastcall(MyService *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800062c8`

## callees

- `0x18000637c`
- `0x18000b648`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800063bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800063bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
MyService *__fastcall MyService::MyService(MyService *this)
{
  HANDLE EventW; // rax

  *(_QWORD *)this = &CNtService::`vftable';
  *((_DWORD *)this + 6) = 7;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &MyService::`vftable';
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 8) = EventW;
  if ( !EventW
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_2716f4bd31e130f967505b342dce5479_Traceguids);
  }
  return this;
}

```

## disassembly

```asm
0x18000637c  mov     [rsp+arg_0], rcx
0x180006381  push    rbx
0x180006382  sub     rsp, 20h
0x180006386  mov     rbx, rcx
0x180006389  lea     rax, ??_7CNtService@@6B@; const CNtService::`vftable'
0x180006390  mov     [rcx], rax
0x180006393  mov     dword ptr [rcx+18h], 7
0x18000639a  mov     dword ptr [rcx+8], 0
0x1800063a1  mov     qword ptr [rcx+10h], 0
0x1800063a9  lea     rax, ??_7MyService@@6B@; const MyService::`vftable'
0x1800063b0  mov     [rcx], rax
0x1800063b3  xor     r9d, r9d; lpName
0x1800063b6  xor     r8d, r8d; bInitialState
0x1800063b9  lea     edx, [r9+1]; bManualReset
0x1800063bd  xor     ecx, ecx; lpEventAttributes
0x1800063bf  call    cs:__imp_CreateEventW
0x1800063c5  mov     [rbx+40h], rax
0x1800063c9  test    rax, rax
0x1800063cc  jnz     short loc_180006403
0x1800063ce  lea     rax, WPP_GLOBAL_Control
0x1800063d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063dc  cmp     rcx, rax
0x1800063df  jz      short loc_180006403
0x1800063e1  test    byte ptr [rcx+1Ch], 1
0x1800063e5  jz      short loc_180006403
0x1800063e7  cmp     byte ptr [rcx+19h], 5
0x1800063eb  jb      short loc_180006403
0x1800063ed  mov     edx, 22h ; '"'
0x1800063f2  lea     r8, WPP_2716f4bd31e130f967505b342dce5479_Traceguids
0x1800063f9  mov     rcx, [rcx+10h]
0x1800063fd  call    WPP_SF_
0x180006402  nop
0x180006403  mov     rax, rbx
0x180006406  add     rsp, 20h
0x18000640a  pop     rbx
0x18000640b  retn
```
