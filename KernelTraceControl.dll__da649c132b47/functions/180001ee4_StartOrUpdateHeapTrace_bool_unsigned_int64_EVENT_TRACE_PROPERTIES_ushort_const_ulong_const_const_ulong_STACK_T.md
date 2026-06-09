# StartOrUpdateHeapTrace(bool,unsigned __int64 *,_EVENT_TRACE_PROPERTIES *,ushort const *,ulong const * const,ulong,_STACK_TRACING_EVENT_ID const * const,ulong)

- ea: `0x180001ee4`
- end: `0x18000204f`
- name: `?StartOrUpdateHeapTrace@@YAK_NPEA_KPEAU_EVENT_TRACE_PROPERTIES@@PEBGQEBKKQEBU_STACK_TRACING_EVENT_ID@@K@Z`
- size: `363`
- prototype: `__int64 __fastcall(char, unsigned __int64 *, struct _EVENT_TRACE_PROPERTIES *, const unsigned __int16 *, unsigned int *, unsigned int, const struct _STACK_TRACING_EVENT_ID *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180002110`
- `0x180002160`

## callees

- `0x18000183c`
- `0x180001a10`
- `0x180001ee4`

## import_xrefs

- `msvcrt!free` at `0x180002027`
- `msvcrt!free` at `0x180002027`
- `ADVAPI32!StartTraceW` at `0x180001fd8`
- `ADVAPI32!StartTraceW` at `0x180001fd8`
- `ADVAPI32!ControlTraceW` at `0x180001fec`
- `ADVAPI32!ControlTraceW` at `0x180001fec`

## pseudocode

```c
__int64 __fastcall StartOrUpdateHeapTrace(
        char a1,
        unsigned __int64 *a2,
        struct _EVENT_TRACE_PROPERTIES *a3,
        const unsigned __int16 *a4,
        unsigned int *a5,
        unsigned int a6,
        const struct _STACK_TRACING_EVENT_ID *a7,
        unsigned int a8)
{
  char v12; // bl
  unsigned int v14; // esi
  PEVENT_TRACE_PROPERTIES v15; // rbx
  ULONG started; // eax
  PEVENT_TRACE_PROPERTIES Properties[2]; // [rsp+40h] [rbp-28h] BYREF

  Properties[1] = (PEVENT_TRACE_PROPERTIES)-2LL;
  v12 = 1;
  if ( GetOSVersionInfo()->dwMajorVersion >= 6
    && (GetOSVersionInfo()->dwMajorVersion != 6 || GetOSVersionInfo()->dwMinorVersion) )
  {
    v12 = 0;
  }
  if ( a8 > (v12 != 0 ? 16 : 256) || !a4 )
    return 87;
  if ( (a3->EnableFlags & 0x80000000) != 0 )
    return 1004;
  if ( !a2 && a1 )
    return 87;
  Properties[0] = 0;
  v14 = TranslateTraceProperties((void **)Properties, &a3->Wnode.BufferSize, a7, a8, a5, a6, 0);
  v15 = Properties[0];
  if ( !v14 )
  {
    Properties[0]->Wnode.Guid = (GUID)HeapGuid;
    if ( a1 )
    {
      started = StartTraceW(a2, a4, v15);
    }
    else
    {
      v15->LogFileNameOffset = 0;
      started = ControlTraceW(0, a4, v15, 2u);
    }
    v14 = started;
    if ( !started )
    {
      a3->NumberOfBuffers = v15->NumberOfBuffers;
      a3->FreeBuffers = v15->FreeBuffers;
      a3->EventsLost = v15->EventsLost;
      a3->BuffersWritten = v15->BuffersWritten;
      a3->LogBuffersLost = v15->LogBuffersLost;
      a3->RealTimeBuffersLost = v15->RealTimeBuffersLost;
      a3->LoggerThreadId = v15->LoggerThreadId;
    }
  }
  free(v15);
  return v14;
}

```

## disassembly

```asm
0x180001ee4  mov     rax, rsp
0x180001ee7  push    rdi
0x180001ee8  push    r14
0x180001eea  push    r15
0x180001eec  sub     rsp, 50h
0x180001ef0  mov     qword ptr [rax-20h], 0FFFFFFFFFFFFFFFEh
0x180001ef8  mov     [rax+8], rbx
0x180001efc  mov     [rax+10h], rbp
0x180001f00  mov     [rax+18h], rsi
0x180001f04  mov     rbp, r9
0x180001f07  mov     rdi, r8
0x180001f0a  mov     r15, rdx
0x180001f0d  mov     r14b, cl
0x180001f10  call    ?GetOSVersionInfo@@YAAEBU_OSVERSIONINFOEXW@@XZ; GetOSVersionInfo(void)
0x180001f15  mov     ebx, 1
0x180001f1a  cmp     dword ptr [rax+4], 6
0x180001f1e  jb      short loc_180001F37
0x180001f20  call    ?GetOSVersionInfo@@YAAEBU_OSVERSIONINFOEXW@@XZ; GetOSVersionInfo(void)
0x180001f25  cmp     dword ptr [rax+4], 6
0x180001f29  jnz     short loc_180001F35
0x180001f2b  call    ?GetOSVersionInfo@@YAAEBU_OSVERSIONINFOEXW@@XZ; GetOSVersionInfo(void)
0x180001f30  cmp     [rax+8], ebx
0x180001f33  jb      short loc_180001F37
0x180001f35  xor     bl, bl
0x180001f37  neg     bl
0x180001f39  sbb     eax, eax
0x180001f3b  and     eax, 0FFFFFF10h
0x180001f40  add     eax, 100h
0x180001f45  mov     r9d, [rsp+68h+arg_38]
0x180001f4d  cmp     r9d, eax
0x180001f50  jbe     short loc_180001F5C
0x180001f52  mov     eax, 57h ; 'W'
0x180001f57  jmp     loc_180002035
0x180001f5c  test    rbp, rbp
0x180001f5f  jz      short loc_180001F52
0x180001f61  cmp     dword ptr [rdi+48h], 0
0x180001f65  jge     short loc_180001F71
0x180001f67  mov     eax, 3ECh
0x180001f6c  jmp     loc_180002035
0x180001f71  test    r15, r15
0x180001f74  jnz     short loc_180001F7B
0x180001f76  test    r14b, r14b
0x180001f79  jnz     short loc_180001F52
0x180001f7b  and     [rsp+68h+Properties], 0
0x180001f81  mov     [rsp+68h+var_38], 0
0x180001f86  mov     eax, [rsp+68h+arg_28]
0x180001f8d  mov     [rsp+68h+var_40], eax
0x180001f91  mov     rax, [rsp+68h+arg_20]
0x180001f99  mov     [rsp+68h+var_48], rax
0x180001f9e  mov     r8, [rsp+68h+arg_30]
0x180001fa6  mov     rdx, rdi
0x180001fa9  lea     rcx, [rsp+68h+Properties]
0x180001fae  call    ?TranslateTraceProperties@@YAKAEAV?$CHeapPtr@U_EVENT_TRACE_PROPERTIES@@VCCRTAllocator@ATL@@@ATL@@QEAU_EVENT_TRACE_PROPERTIES@@QEBU_STACK_TRACING_EVENT_ID@@KQEBKK_N@Z; TranslateTraceProperties(ATL::CHeapPtr<_EVENT_TRACE_PROPERTIES,ATL::CCRTAllocator> &,_EVENT_TRACE_PROPERTIES * const,_STACK_TRACING_EVENT_ID const * const,ulong,ulong const * const,ulong,bool)
0x180001fb3  mov     esi, eax
0x180001fb5  mov     rbx, [rsp+68h+Properties]
0x180001fba  test    eax, eax
0x180001fbc  jnz     short loc_180002024
0x180001fbe  movups  xmm0, cs:HeapGuid
0x180001fc5  movdqu  xmmword ptr [rbx+18h], xmm0
0x180001fca  mov     r8, rbx; Properties
0x180001fcd  mov     rdx, rbp; InstanceName
0x180001fd0  test    r14b, r14b
0x180001fd3  jz      short loc_180001FE0
0x180001fd5  mov     rcx, r15; TraceHandle
0x180001fd8  call    cs:__imp_StartTraceW
0x180001fde  jmp     short loc_180001FF2
0x180001fe0  and     dword ptr [rbx+70h], 0
0x180001fe4  mov     r9d, 2; ControlCode
0x180001fea  xor     ecx, ecx; TraceHandle
0x180001fec  call    cs:__imp_ControlTraceW
0x180001ff2  mov     esi, eax
0x180001ff4  test    eax, eax
0x180001ff6  jnz     short loc_180002024
0x180001ff8  mov     eax, [rbx+50h]
0x180001ffb  mov     [rdi+50h], eax
0x180001ffe  mov     eax, [rbx+54h]
0x180002001  mov     [rdi+54h], eax
0x180002004  mov     eax, [rbx+58h]
0x180002007  mov     [rdi+58h], eax
0x18000200a  mov     eax, [rbx+5Ch]
0x18000200d  mov     [rdi+5Ch], eax
0x180002010  mov     eax, [rbx+60h]
0x180002013  mov     [rdi+60h], eax
0x180002016  mov     eax, [rbx+64h]
0x180002019  mov     [rdi+64h], eax
0x18000201c  mov     rax, [rbx+68h]
0x180002020  mov     [rdi+68h], rax
0x180002024  mov     rcx, rbx; Block
0x180002027  call    cs:__imp_free
0x18000202d  and     [rsp+68h+Properties], 0
0x180002033  mov     eax, esi
0x180002035  lea     r11, [rsp+68h+var_18]
0x18000203a  mov     rbx, [r11+20h]
0x18000203e  mov     rbp, [r11+28h]
0x180002042  mov     rsi, [r11+30h]
0x180002046  mov     rsp, r11
0x180002049  pop     r15
0x18000204b  pop     r14
0x18000204d  pop     rdi
0x18000204e  retn
```
