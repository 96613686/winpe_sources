# Apx::ApfIpcIoLink::EndOperation(void)

- ea: `0x18002812c`
- end: `0x1800281b6`
- name: `?EndOperation@ApfIpcIoLink@Apx@@AEAAXXZ`
- size: `138`
- prototype: `void __fastcall(Apx::ApfIpcIoLink *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180027990`
- `0x1800281bc`
- `0x180028b10`

## callees

- `0x18000a12c`
- `0x18002812c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800281af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002813d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002813d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002815f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002815f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18002819b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18002819b`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLink::EndOperation(Apx::ApfIpcIoLink *this)
{
  int v2; // eax
  int v3; // eax

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v2 = *((_DWORD *)this + 109);
  if ( v2 <= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
    }
    DebugBreak();
  }
  else
  {
    v3 = v2 - 1;
    *((_DWORD *)this + 109) = v3;
    if ( !v3 )
      SetEvent(*((HANDLE *)this + 53));
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x18002812c  mov     [rsp+arg_0], rbx
0x180028131  push    rdi
0x180028132  sub     rsp, 20h
0x180028136  mov     rbx, rcx
0x180028139  add     rcx, 10h; lpCriticalSection
0x18002813d  call    cs:__imp_EnterCriticalSection
0x180028143  mov     eax, [rbx+1B4h]
0x180028149  test    eax, eax
0x18002814b  jle     short loc_180028167
0x18002814d  sub     eax, 1
0x180028150  mov     [rbx+1B4h], eax
0x180028156  jnz     short loc_1800281A1
0x180028158  mov     rcx, [rbx+1A8h]; hEvent
0x18002815f  call    cs:__imp_SetEvent
0x180028165  jmp     short loc_1800281A1
0x180028167  mov     rcx, cs:WPP_GLOBAL_Control
0x18002816e  lea     rax, WPP_GLOBAL_Control
0x180028175  cmp     rcx, rax
0x180028178  jz      short loc_18002819B
0x18002817a  test    byte ptr [rcx+1Ch], 80h
0x18002817e  jz      short loc_18002819B
0x180028180  cmp     byte ptr [rcx+19h], 2
0x180028184  jb      short loc_18002819B
0x180028186  mov     rcx, [rcx+10h]
0x18002818a  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180028191  mov     edx, 21h ; '!'
0x180028196  call    WPP_SF_
0x18002819b  call    cs:__imp_DebugBreak
0x1800281a1  lea     rcx, [rbx+10h]
0x1800281a5  mov     rbx, [rsp+28h+arg_0]
0x1800281aa  add     rsp, 20h
0x1800281ae  pop     rdi
0x1800281af  jmp     cs:__imp_LeaveCriticalSection
```
