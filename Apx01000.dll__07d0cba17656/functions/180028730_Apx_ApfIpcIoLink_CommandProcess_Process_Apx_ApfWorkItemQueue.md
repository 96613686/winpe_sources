# Apx::ApfIpcIoLink_CommandProcess::Process(Apx::ApfWorkItemQueue *)

- ea: `0x180028730`
- end: `0x1800287b2`
- name: `?Process@ApfIpcIoLink_CommandProcess@Apx@@UEAAXPEAVApfWorkItemQueue@2@@Z`
- size: `130`
- prototype: `void __fastcall(Apx::ApfIpcIoLink_CommandProcess *__hidden this, struct Apx::ApfWorkItemQueue *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000a12c`
- `0x180027990`
- `0x180028730`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLink_CommandProcess::Process(
        Apx::ApfIpcIoLink_CommandProcess *this,
        struct Apx::ApfWorkItemQueue *a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
  }
  Apx::ApfIpcIoLink::CommandProcess(*((_QWORD *)this + 1));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
  }
}

```

## disassembly

```asm
0x180028730  mov     [rsp+arg_0], rbx
0x180028735  push    rdi
0x180028736  sub     rsp, 20h
0x18002873a  mov     rbx, rcx
0x18002873d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028744  lea     rdi, WPP_GLOBAL_Control
0x18002874b  cmp     rcx, rdi
0x18002874e  jz      short loc_180028771
0x180028750  test    byte ptr [rcx+1Ch], 1
0x180028754  jz      short loc_180028771
0x180028756  cmp     byte ptr [rcx+19h], 5
0x18002875a  jb      short loc_180028771
0x18002875c  mov     rcx, [rcx+10h]
0x180028760  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180028767  mov     edx, 32h ; '2'
0x18002876c  call    WPP_SF_
0x180028771  mov     rcx, [rbx+8]; this
0x180028775  call    ?CommandProcess@ApfIpcIoLink@Apx@@QEAAXXZ; Apx::ApfIpcIoLink::CommandProcess(void)
0x18002877a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028781  cmp     rcx, rdi
0x180028784  jz      short loc_1800287A7
0x180028786  test    byte ptr [rcx+1Ch], 1
0x18002878a  jz      short loc_1800287A7
0x18002878c  cmp     byte ptr [rcx+19h], 5
0x180028790  jb      short loc_1800287A7
0x180028792  mov     rcx, [rcx+10h]
0x180028796  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x18002879d  mov     edx, 33h ; '3'
0x1800287a2  call    WPP_SF_
0x1800287a7  mov     rbx, [rsp+28h+arg_0]
0x1800287ac  add     rsp, 20h
0x1800287b0  pop     rdi
0x1800287b1  retn
```
