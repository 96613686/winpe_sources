# CClipTaskSchedulerT<CEmptyType>::GetTaskStatus(ushort *,ushort *,int *)

- ea: `0x140007a34`
- end: `0x140007ad9`
- name: `?GetTaskStatus@?$CClipTaskSchedulerT@VCEmptyType@@@@SAJPEAG0PEAH@Z`
- size: `165`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140007dcc`

## callees

- `0x140003454`
- `0x140004780`
- `0x1400077fc`
- `0x140007a34`
- `0x140014010`

## pseudocode

```c
__int64 __fastcall CClipTaskSchedulerT<CEmptyType>::GetTaskStatus(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v3; // rdi
  unsigned int v5; // ebx
  __int64 v6; // rcx
  int SchedulerObjects; // eax
  int v8; // eax
  __int16 v10; // [rsp+40h] [rbp+18h] BYREF
  __int64 v11; // [rsp+48h] [rbp+20h] BYREF

  v3 = 0;
  v11 = 0;
  v10 = 0;
  if ( !a3 )
  {
    v5 = -2147024809;
    v6 = 2147942487LL;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_9;
  }
  SchedulerObjects = CClipTaskSchedulerT<CEmptyType>::GetSchedulerObjects(a1, a2, &v11);
  v3 = v11;
  if ( SchedulerObjects < 0 )
  {
    v5 = 1;
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v11 + 80LL))(v11, &v10);
    v5 = v8;
    if ( v8 < 0 )
    {
      v6 = (unsigned int)v8;
      goto LABEL_3;
    }
    *a3 = v10 == -1;
  }
LABEL_9:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  return v5;
}

```

## disassembly

```asm
0x140007a34  mov     [rsp+arg_0], rbx
0x140007a39  mov     [rsp+arg_8], rsi
0x140007a3e  push    rdi
0x140007a3f  sub     rsp, 20h
0x140007a43  xor     edi, edi
0x140007a45  xor     eax, eax
0x140007a47  mov     [rsp+28h+arg_18], rdi
0x140007a4c  mov     rsi, r8
0x140007a4f  mov     [rsp+28h+arg_10], ax
0x140007a54  test    r8, r8
0x140007a57  jnz     short loc_140007A67
0x140007a59  mov     ebx, 80070057h
0x140007a5e  mov     ecx, ebx
0x140007a60  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140007a65  jmp     short loc_140007AAC
0x140007a67  lea     r8, [rsp+28h+arg_18]
0x140007a6c  call    ?GetSchedulerObjects@?$CClipTaskSchedulerT@VCEmptyType@@@@CAJPEAG0PEAPEAUIRegisteredTask@@PEAPEAUITaskFolder@@@Z; CClipTaskSchedulerT<CEmptyType>::GetSchedulerObjects(ushort *,ushort *,IRegisteredTask * *,ITaskFolder * *)
0x140007a71  mov     rdi, [rsp+28h+arg_18]
0x140007a76  test    eax, eax
0x140007a78  js      short loc_140007AA7
0x140007a7a  mov     rax, [rdi]
0x140007a7d  lea     rdx, [rsp+28h+arg_10]
0x140007a82  mov     rcx, rdi
0x140007a85  mov     rax, [rax+50h]
0x140007a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a8e  mov     ebx, eax
0x140007a90  test    eax, eax
0x140007a92  jns     short loc_140007A98
0x140007a94  mov     ecx, eax
0x140007a96  jmp     short loc_140007A60
0x140007a98  xor     eax, eax
0x140007a9a  cmp     [rsp+28h+arg_10], 0FFFFh
0x140007aa0  setz    al
0x140007aa3  mov     [rsi], eax
0x140007aa5  jmp     short loc_140007AAC
0x140007aa7  mov     ebx, 1
0x140007aac  mov     ecx, ebx
0x140007aae  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140007ab3  test    rdi, rdi
0x140007ab6  jz      short loc_140007AC7
0x140007ab8  mov     rax, [rdi]
0x140007abb  mov     rcx, rdi
0x140007abe  mov     rax, [rax+10h]
0x140007ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ac7  mov     rsi, [rsp+28h+arg_8]
0x140007acc  mov     eax, ebx
0x140007ace  mov     rbx, [rsp+28h+arg_0]
0x140007ad3  add     rsp, 20h
0x140007ad7  pop     rdi
0x140007ad8  retn
```
