# Apx::ApfIpcIoLink::StartOperation(void)

- ea: `0x180029118`
- end: `0x1800291bf`
- name: `?StartOperation@ApfIpcIoLink@Apx@@AEAA_NXZ`
- size: `167`
- prototype: `char __fastcall(Apx::ApfIpcIoLink *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180027990`
- `0x1800281bc`
- `0x180028b10`

## callees

- `0x18000a1b4`
- `0x180029118`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800291a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800291a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029131`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029131`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002915d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002915d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18002919c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18002919c`

## pseudocode

```c
char __fastcall Apx::ApfIpcIoLink::StartOperation(Apx::ApfIpcIoLink *this)
{
  char v2; // si
  int v3; // r9d
  void *v4; // rcx

  v2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !*((_BYTE *)this + 432) )
  {
    v3 = *((_DWORD *)this + 109);
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
      }
      DebugBreak();
    }
    else
    {
      v4 = (void *)*((_QWORD *)this + 53);
      *((_DWORD *)this + 109) = v3 + 1;
      ResetEvent(v4);
      v2 = 1;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v2;
}

```

## disassembly

```asm
0x180029118  mov     [rsp+arg_0], rbx
0x18002911d  mov     [rsp+arg_8], rsi
0x180029122  push    rdi
0x180029123  sub     rsp, 20h
0x180029127  mov     rbx, rcx
0x18002912a  xor     sil, sil
0x18002912d  add     rcx, 10h; lpCriticalSection
0x180029131  call    cs:__imp_EnterCriticalSection
0x180029137  cmp     [rbx+1B0h], sil
0x18002913e  jnz     short loc_1800291A2
0x180029140  mov     r9d, [rbx+1B4h]
0x180029147  test    r9d, r9d
0x18002914a  js      short loc_180029168
0x18002914c  mov     rcx, [rbx+1A8h]; hEvent
0x180029153  lea     eax, [r9+1]
0x180029157  mov     [rbx+1B4h], eax
0x18002915d  call    cs:__imp_ResetEvent
0x180029163  mov     sil, 1
0x180029166  jmp     short loc_1800291A2
0x180029168  mov     rcx, cs:WPP_GLOBAL_Control
0x18002916f  lea     rax, WPP_GLOBAL_Control
0x180029176  cmp     rcx, rax
0x180029179  jz      short loc_18002919C
0x18002917b  test    byte ptr [rcx+1Ch], 80h
0x18002917f  jz      short loc_18002919C
0x180029181  cmp     byte ptr [rcx+19h], 2
0x180029185  jb      short loc_18002919C
0x180029187  mov     rcx, [rcx+10h]
0x18002918b  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180029192  mov     edx, 20h ; ' '
0x180029197  call    WPP_SF_d
0x18002919c  call    cs:__imp_DebugBreak
0x1800291a2  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800291a6  call    cs:__imp_LeaveCriticalSection
0x1800291ac  mov     rbx, [rsp+28h+arg_0]
0x1800291b1  mov     al, sil
0x1800291b4  mov     rsi, [rsp+28h+arg_8]
0x1800291b9  add     rsp, 20h
0x1800291bd  pop     rdi
0x1800291be  retn
```
