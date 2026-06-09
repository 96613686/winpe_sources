# FastWppTraceMessage

- ea: `0x18000b794`
- end: `0x18000b91d`
- name: `FastWppTraceMessage`
- size: `393`
- prototype: `ULONG(__int16, USHORT, ULONGLONG, ...)`
- caller_count: `60`
- callee_count: `3`
- tags: ``

## callers

- `0x180015008`
- `0x180015040`
- `0x180015094`
- `0x1800150cc`
- `0x180015114`
- `0x180015128`
- `0x180015178`
- `0x1800151bc`
- `0x180015268`
- `0x1800152b0`
- `0x1800152f8`
- `0x180015398`
- `0x1800153dc`
- `0x18001541c`
- `0x180015478`
- `0x1800154c8`
- `0x18001553c`
- `0x180015618`
- `0x180015694`
- `0x180015720`
- `0x1800157fc`
- `0x180015864`
- `0x1800158bc`
- `0x180015978`
- `0x180015a18`
- `0x180015ad8`
- `0x180015b74`
- `0x180015c1c`
- `0x180015d00`
- `0x180015e84`
- `0x180015f14`
- `0x180015fd8`
- `0x1800160b8`
- `0x180016134`
- `0x1800161ac`
- `0x180016288`
- `0x1800162f4`
- `0x1800163e0`
- `0x180016544`
- `0x18001663c`
- `0x1800166c8`
- `0x180016750`
- `0x1800167ec`
- `0x180016858`
- `0x18001690c`
- `0x1800169dc`
- `0x180016a30`
- `0x180016aa8`
- `0x180016af0`
- `0x180016b38`

## callees

- `0x1800014b0`
- `0x18000b6ec`
- `0x18000b794`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18000b8df`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18000b8df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b877`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b877`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8fc`

## pseudocode

```c
ULONG FastWppTraceMessage(__int16 a1, USHORT a2, ULONGLONG a3, ...)
{
  ULONG result; // eax
  void *v4; // rbx
  LPVOID v5; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-A8h] BYREF
  SIZE_T dwBytes[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v9[256]; // [rsp+80h] [rbp-80h] BYREF
  va_list va; // [rsp+1C8h] [rbp+C8h] BYREF

  va_start(va, a3);
  result = FastWppInitState;
  EventDescriptor = 0;
  UserData = 0;
  *(_OWORD *)dwBytes = 0;
  if ( FastWppInitState == 2 )
  {
    EventDescriptor.Id = a2;
    EventDescriptor.Level = HIBYTE(a1);
    v4 = 0;
    UserData.Type = 4;
    UserData.Size = 16;
    BYTE4(dwBytes[1]) = 0;
    LODWORD(dwBytes[1]) = 256;
    EventDescriptor.Keyword = 1LL << a1;
    UserData.Ptr = a3;
    dwBytes[0] = (SIZE_T)v9;
    FastWppPackEvent((__int64 *)va, v9, 256, &dwBytes[1]);
    if ( LODWORD(dwBytes[1]) > 0x100 )
    {
      v5 = HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, LODWORD(dwBytes[1]));
      v4 = v5;
      if ( v5 )
      {
        dwBytes[0] = (SIZE_T)v5;
        FastWppPackEvent((__int64 *)va, v5, LODWORD(dwBytes[1]), &dwBytes[1]);
      }
      else
      {
        LODWORD(dwBytes[1]) = 256;
      }
    }
    result = EventWriteEx(FastWppRegHandle, &EventDescriptor, 0, 0, 0, 0, 2u, &UserData);
    if ( v4 )
      return HeapFree(NtCurrentPeb()->ProcessHeap, 0, v4);
  }
  return result;
}

```

## disassembly

```asm
0x18000b794  mov     [rsp-8+arg_10], r8
0x18000b799  mov     [rsp-8+arg_18], r9
0x18000b79e  push    rbp
0x18000b79f  push    rbx
0x18000b7a0  push    r14
0x18000b7a2  lea     rbp, [rsp-90h]
0x18000b7aa  sub     rsp, 190h
0x18000b7b1  mov     rax, cs:__security_cookie
0x18000b7b8  xor     rax, rsp
0x18000b7bb  mov     [rbp+0A0h+var_20], rax
0x18000b7c2  mov     eax, cs:FastWppInitState
0x18000b7c8  xorps   xmm1, xmm1
0x18000b7cb  mov     [rsp+1A0h+var_160], 0
0x18000b7d4  xorps   xmm0, xmm0
0x18000b7d7  movups  xmmword ptr [rsp+1A0h+EventDescriptor.Id], xmm0
0x18000b7dc  movups  xmmword ptr [rsp+1A0h+var_148.Ptr], xmm1
0x18000b7e1  movups  xmmword ptr [rsp+1A0h+dwBytes], xmm1
0x18000b7e6  cmp     eax, 2
0x18000b7e9  jnz     loc_18000B902
0x18000b7ef  movzx   eax, cx
0x18000b7f2  mov     [rsp+1A0h+EventDescriptor.Id], dx
0x18000b7f7  shr     ax, 8
0x18000b7fb  lea     r14, [rbp+0A0h+arg_18]
0x18000b802  mov     [rsp+1A0h+EventDescriptor.Level], al
0x18000b806  lea     r9, [rsp+1A0h+dwBytes+8]
0x18000b80b  xor     ebx, ebx
0x18000b80d  mov     byte ptr [rsp+1A0h+var_148.0Ch], 4
0x18000b812  mov     r8d, 100h
0x18000b818  mov     [rsp+1A0h+var_148.Size], 10h
0x18000b820  lea     rdx, [rbp+0A0h+var_120]
0x18000b824  mov     byte ptr [rsp+1A0h+dwBytes+0Ch], bl
0x18000b828  mov     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18000b830  lea     eax, [rbx+1]
0x18000b833  shl     rax, cl
0x18000b836  mov     rcx, r14
0x18000b839  mov     [rsp+1A0h+EventDescriptor.Keyword], rax
0x18000b83e  mov     rax, [rbp+0A0h+arg_10]
0x18000b845  mov     [rsp+1A0h+var_148.Ptr], rax
0x18000b84a  lea     rax, [rbp+0A0h+var_120]
0x18000b84e  mov     [rsp+1A0h+dwBytes], rax
0x18000b853  call    FastWppPackEvent
0x18000b858  cmp     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18000b860  jbe     short loc_18000B8A9
0x18000b862  mov     rcx, gs:60h
0x18000b86b  lea     edx, [rbx+8]; dwFlags
0x18000b86e  mov     r8d, dword ptr [rsp+1A0h+dwBytes+8]; dwBytes
0x18000b873  mov     rcx, [rcx+30h]; hHeap
0x18000b877  call    cs:__imp_HeapAlloc
0x18000b87d  mov     rbx, rax
0x18000b880  test    rax, rax
0x18000b883  jz      short loc_18000B8A1
0x18000b885  mov     r8d, dword ptr [rsp+1A0h+dwBytes+8]
0x18000b88a  lea     r9, [rsp+1A0h+dwBytes+8]
0x18000b88f  mov     rdx, rax
0x18000b892  mov     [rsp+1A0h+dwBytes], rax
0x18000b897  mov     rcx, r14
0x18000b89a  call    FastWppPackEvent
0x18000b89f  jmp     short loc_18000B8A9
0x18000b8a1  mov     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18000b8a9  mov     rcx, cs:FastWppRegHandle; RegHandle
0x18000b8b0  lea     rax, [rsp+1A0h+var_148]
0x18000b8b5  mov     [rsp+1A0h+UserData], rax; UserData
0x18000b8ba  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x18000b8bf  mov     [rsp+1A0h+UserDataCount], 2; UserDataCount
0x18000b8c7  xor     r9d, r9d; Flags
0x18000b8ca  mov     [rsp+1A0h+RelatedActivityId], 0; RelatedActivityId
0x18000b8d3  xor     r8d, r8d; Filter
0x18000b8d6  mov     [rsp+1A0h+ActivityId], 0; ActivityId
0x18000b8df  call    cs:__imp_EventWriteEx
0x18000b8e5  test    rbx, rbx
0x18000b8e8  jz      short loc_18000B902
0x18000b8ea  mov     rcx, gs:60h
0x18000b8f3  mov     r8, rbx; lpMem
0x18000b8f6  xor     edx, edx; dwFlags
0x18000b8f8  mov     rcx, [rcx+30h]; hHeap
0x18000b8fc  call    cs:__imp_HeapFree
0x18000b902  mov     rcx, [rbp+0A0h+var_20]
0x18000b909  xor     rcx, rsp; StackCookie
0x18000b90c  call    __security_check_cookie
0x18000b911  add     rsp, 190h
0x18000b918  pop     r14
0x18000b91a  pop     rbx
0x18000b91b  pop     rbp
0x18000b91c  retn
```
