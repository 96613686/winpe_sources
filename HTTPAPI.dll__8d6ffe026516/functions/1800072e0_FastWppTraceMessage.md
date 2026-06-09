# FastWppTraceMessage

- ea: `0x1800072e0`
- end: `0x18000747e`
- name: `FastWppTraceMessage`
- size: `414`
- prototype: ``
- caller_count: `49`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b010`
- `0x18000b080`
- `0x18000b0b8`
- `0x18000b0f0`
- `0x18000b138`
- `0x18000b198`
- `0x18000b214`
- `0x18000b30c`
- `0x18000b3d4`
- `0x18000b424`
- `0x18000b46c`
- `0x18000b4f0`
- `0x18000b584`
- `0x18000b5e8`
- `0x18000b644`
- `0x18000b6bc`
- `0x18000b718`
- `0x18000b80c`
- `0x18000b85c`
- `0x18000b8ac`
- `0x18000b924`
- `0x18000b9e4`
- `0x18000ba5c`
- `0x18000bbe0`
- `0x18000bc68`
- `0x18000bce0`
- `0x18000bdb8`
- `0x18000bdd0`
- `0x18000be2c`
- `0x18000be64`
- `0x18000beb4`
- `0x18000bf60`
- `0x18000c0ac`
- `0x18000c16c`
- `0x18000c1bc`
- `0x18000c250`
- `0x18000c2ac`
- `0x18000c2fc`
- `0x18000c370`
- `0x18000c42c`
- `0x18000c4cc`
- `0x18000c550`
- `0x18000c5fc`
- `0x18000c63c`
- `0x18000c674`
- `0x18000c6c8`
- `0x18000c74c`
- `0x18000c7e8`
- `0x18000c87c`

## callees

- `0x180007250`
- `0x1800072e0`
- `0x18000a5f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007458`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007458`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800073cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800073cb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180007433`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180007433`

## pseudocode

```c
ULONG FastWppTraceMessage(__int16 a1, USHORT a2, ULONGLONG a3, ...)
{
  ULONG result; // eax
  void *v4; // rbx
  LPVOID v5; // rax
  EVENT_DESCRIPTOR EventDescriptor_8; // [rsp+50h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v8; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v9[256]; // [rsp+88h] [rbp-80h] BYREF
  va_list va; // [rsp+1D0h] [rbp+C8h] BYREF

  va_start(va, a3);
  result = FastWppInitState;
  EventDescriptor_8 = 0;
  UserData = 0;
  v8 = 0;
  if ( FastWppInitState == 2 )
  {
    EventDescriptor_8.Level = HIBYTE(a1);
    v4 = 0;
    EventDescriptor_8.Keyword = 1LL << a1;
    UserData.Ptr = a3;
    EventDescriptor_8.Id = a2;
    *(_QWORD *)&v8 = v9;
    UserData.Type = 4;
    UserData.Size = 16;
    BYTE12(v8) = 0;
    DWORD2(v8) = 256;
    FastWppPackEvent(va, v9, 256, (char *)&v8 + 8);
    if ( DWORD2(v8) > 0x100 )
    {
      v5 = HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, DWORD2(v8));
      v4 = v5;
      if ( v5 )
      {
        *(_QWORD *)&v8 = v5;
        FastWppPackEvent(va, v5, DWORD2(v8), (char *)&v8 + 8);
      }
      else
      {
        DWORD2(v8) = 256;
      }
    }
    result = EventWriteEx(FastWppRegHandle, &EventDescriptor_8, 0, 0, 0, 0, 2u, &UserData);
    if ( v4 )
      return HeapFree(NtCurrentPeb()->ProcessHeap, 0, v4);
  }
  return result;
}

```

## disassembly

```asm
0x1800072e0  mov     r11, rsp
0x1800072e3  mov     [r11+18h], r8
0x1800072e7  mov     [r11+20h], r9
0x1800072eb  push    rbp
0x1800072ec  lea     rbp, [r11-0A8h]
0x1800072f3  sub     rsp, 1A0h
0x1800072fa  mov     rax, cs:__security_cookie
0x180007301  xor     rax, rsp
0x180007304  mov     [rbp+0A0h+var_20], rax
0x18000730b  mov     eax, cs:FastWppInitState
0x180007311  xorps   xmm1, xmm1
0x180007314  mov     qword ptr [rsp+1A0h+EventDescriptor.Id], 0
0x18000731d  xorps   xmm0, xmm0
0x180007320  movups  xmmword ptr [rsp+1A0h+EventDescriptor.Keyword], xmm0
0x180007325  movups  xmmword ptr [rsp+1A0h+var_150.Size], xmm1
0x18000732a  movups  [rsp+1A0h+var_140+8], xmm1
0x18000732f  cmp     eax, 2
0x180007332  jnz     loc_180007466
0x180007338  movzx   eax, cx
0x18000733b  mov     [r11-10h], rbx
0x18000733f  shr     ax, 8
0x180007343  lea     r9, [rsp+70h]
0x180007348  mov     byte ptr [rsp+1A0h+EventDescriptor.Keyword+4], al
0x18000734c  xor     ebx, ebx
0x18000734e  mov     [r11-18h], rsi
0x180007352  mov     eax, 1
0x180007357  shl     rax, cl
0x18000735a  lea     rsi, [rbp+0A0h+arg_18]
0x180007361  mov     [rsp+1A0h+var_150.Ptr], rax
0x180007366  mov     r8d, 100h
0x18000736c  mov     rax, [rbp+0A0h+arg_10]
0x180007373  mov     rcx, rsi
0x180007376  mov     qword ptr [rsp+1A0h+var_150.Size], rax
0x18000737b  lea     rax, [rbp+0A0h+var_120]
0x18000737f  mov     word ptr [rsp+1A0h+EventDescriptor.Keyword], dx
0x180007384  lea     rdx, [rbp+0A0h+var_120]
0x180007388  mov     qword ptr [rsp+1A0h+var_140+8], rax
0x18000738d  mov     byte ptr [rsp+1A0h+var_140+4], 4
0x180007392  mov     dword ptr [rsp+1A0h+var_140], 10h
0x18000739a  mov     [rsp+74h], bl
0x18000739e  mov     dword ptr [rsp+70h], 100h
0x1800073a6  call    FastWppPackEvent
0x1800073ab  mov     eax, [rsp+70h]
0x1800073af  cmp     eax, 100h
0x1800073b4  jbe     short loc_1800073FD
0x1800073b6  mov     rcx, gs:60h
0x1800073bf  mov     r8d, eax; dwBytes
0x1800073c2  mov     edx, 8; dwFlags
0x1800073c7  mov     rcx, [rcx+30h]; hHeap
0x1800073cb  call    cs:__imp_HeapAlloc
0x1800073d1  mov     rbx, rax
0x1800073d4  test    rax, rax
0x1800073d7  jz      short loc_1800073F5
0x1800073d9  mov     r8d, [rsp+70h]
0x1800073de  lea     r9, [rsp+70h]
0x1800073e3  mov     rdx, rax
0x1800073e6  mov     qword ptr [rsp+1A0h+var_140+8], rax
0x1800073eb  mov     rcx, rsi
0x1800073ee  call    FastWppPackEvent
0x1800073f3  jmp     short loc_1800073FD
0x1800073f5  mov     dword ptr [rsp+70h], 100h
0x1800073fd  mov     rcx, cs:FastWppRegHandle; RegHandle
0x180007404  lea     rax, [rsp+1A0h+var_150.Size]
0x180007409  mov     [rsp+1A0h+UserData], rax; UserData
0x18000740e  lea     rdx, [rsp+1A0h+EventDescriptor.Keyword]; EventDescriptor
0x180007413  mov     [rsp+1A0h+UserDataCount], 2; UserDataCount
0x18000741b  xor     r9d, r9d; Flags
0x18000741e  mov     [rsp+1A0h+RelatedActivityId], 0; RelatedActivityId
0x180007427  xor     r8d, r8d; Filter
0x18000742a  mov     [rsp+1A0h+ActivityId], 0; ActivityId
0x180007433  call    cs:__imp_EventWriteEx
0x180007439  mov     rsi, [rsp+1A0h+var_10]
0x180007441  test    rbx, rbx
0x180007444  jz      short loc_18000745E
0x180007446  mov     rcx, gs:60h
0x18000744f  mov     r8, rbx; lpMem
0x180007452  xor     edx, edx; dwFlags
0x180007454  mov     rcx, [rcx+30h]; hHeap
0x180007458  call    cs:__imp_HeapFree
0x18000745e  mov     rbx, [rsp+198h]
0x180007466  mov     rcx, [rbp+0A0h+var_20]
0x18000746d  xor     rcx, rsp; StackCookie
0x180007470  call    __security_check_cookie
0x180007475  add     rsp, 1A0h
0x18000747c  pop     rbp
0x18000747d  retn
```
