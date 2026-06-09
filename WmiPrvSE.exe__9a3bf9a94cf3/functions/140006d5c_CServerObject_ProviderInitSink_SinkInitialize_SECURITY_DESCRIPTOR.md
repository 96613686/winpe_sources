# CServerObject_ProviderInitSink::SinkInitialize(_SECURITY_DESCRIPTOR *)

- ea: `0x140006d5c`
- end: `0x140006e06`
- name: `?SinkInitialize@CServerObject_ProviderInitSink@@QEAAJPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `170`
- prototype: `int(CServerObject_ProviderInitSink *__hidden this, struct _SECURITY_DESCRIPTOR *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140005a14`
- `0x14001cbf4`
- `0x14001d55c`

## callees

- `0x140006d5c`
- `0x1400234b8`
- `0x140041c60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006d7b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006d7b`
- `wbemcomn!GetMemLogObject` at `0x140006d8f`
- `wbemcomn!GetMemLogObject` at `0x140006d8f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140006d9a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140006d9a`

## pseudocode

```c
__int64 __fastcall CServerObject_ProviderInitSink::SinkInitialize(
        CServerObject_ProviderInitSink *this,
        struct _SECURITY_DESCRIPTOR *a2)
{
  HANDLE EventW; // rax
  int v5; // ebx
  CMemoryLog *MemLogObject; // rax

  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 2) = EventW;
  if ( !EventW )
  {
    v5 = -2147217402;
LABEL_3:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v5);
    goto LABEL_6;
  }
  v5 = 0;
  if ( a2 )
  {
    v5 = ProviderSubSystem_Common_Globals::SinkAccessInitialize(a2, (struct _SECURITY_DESCRIPTOR **)this + 4);
    if ( v5 < 0 )
      goto LABEL_3;
  }
LABEL_6:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ac9f0bf1ae8b30a0c82e8edf46eb550d_Traceguids, (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140006d5c  mov     [rsp+arg_0], rbx
0x140006d61  mov     [rsp+arg_8], rsi
0x140006d66  push    rdi
0x140006d67  sub     rsp, 20h
0x140006d6b  mov     rdi, rdx
0x140006d6e  mov     rsi, rcx
0x140006d71  xor     edx, edx; bManualReset
0x140006d73  xor     ecx, ecx; lpEventAttributes
0x140006d75  xor     r9d, r9d; lpName
0x140006d78  xor     r8d, r8d; bInitialState
0x140006d7b  call    cs:__imp_CreateEventW
0x140006d81  mov     [rsi+10h], rax
0x140006d85  test    rax, rax
0x140006d88  jnz     short loc_140006DA2
0x140006d8a  mov     ebx, 80041006h
0x140006d8f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140006d95  mov     rcx, rax
0x140006d98  mov     edx, ebx
0x140006d9a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140006da0  jmp     short loc_140006DBB
0x140006da2  xor     ebx, ebx
0x140006da4  test    rdi, rdi
0x140006da7  jz      short loc_140006DBB
0x140006da9  lea     rdx, [rsi+20h]; struct _SECURITY_DESCRIPTOR **
0x140006dad  mov     rcx, rdi; struct _SECURITY_DESCRIPTOR *
0x140006db0  call    ?SinkAccessInitialize@ProviderSubSystem_Common_Globals@@SAJPEAU_SECURITY_DESCRIPTOR@@AEAPEAU2@@Z; ProviderSubSystem_Common_Globals::SinkAccessInitialize(_SECURITY_DESCRIPTOR *,_SECURITY_DESCRIPTOR * &)
0x140006db5  mov     ebx, eax
0x140006db7  test    eax, eax
0x140006db9  js      short loc_140006D8F
0x140006dbb  mov     rcx, cs:WPP_GLOBAL_Control
0x140006dc2  lea     rax, WPP_GLOBAL_Control
0x140006dc9  cmp     rcx, rax
0x140006dcc  jz      short loc_140006DD4
0x140006dce  test    byte ptr [rcx+1Ch], 4
0x140006dd2  jnz     short loc_140006DE6
0x140006dd4  mov     rsi, [rsp+28h+arg_8]
0x140006dd9  mov     eax, ebx
0x140006ddb  mov     rbx, [rsp+28h+arg_0]
0x140006de0  add     rsp, 20h
0x140006de4  pop     rdi
0x140006de5  retn
0x140006de6  cmp     byte ptr [rcx+19h], 2
0x140006dea  jb      short loc_140006DD4
0x140006dec  mov     rcx, [rcx+10h]
0x140006df0  lea     r8, WPP_ac9f0bf1ae8b30a0c82e8edf46eb550d_Traceguids
0x140006df7  mov     edx, 0Ah
0x140006dfc  mov     r9d, ebx
0x140006dff  call    WPP_SF_d
0x140006e04  jmp     short loc_140006DD4
```
