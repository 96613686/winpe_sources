# CRemoteTextAppIntegration::SendKeyToHost(uint,uint,uchar const *)

- ea: `0x180025380`
- end: `0x18002543f`
- name: `?SendKeyToHost@CRemoteTextAppIntegration@@UEAAJIIPEBE@Z`
- size: `191`
- prototype: `__int64 __fastcall(CRemoteTextAppIntegration *__hidden this, unsigned int, unsigned int, const unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800132f0`
- `0x180014b90`
- `0x180025380`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800253c5`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800253c5`
- `CoreMessaging!MsgBlobCreateShared` at `0x1800253b0`
- `CoreMessaging!MsgBlobCreateShared` at `0x1800253b0`
- `CoreMessaging!MsgRelease` at `0x180025427`
- `CoreMessaging!MsgRelease` at `0x180025427`

## pseudocode

```c
__int64 __fastcall CRemoteTextAppIntegration::SendKeyToHost(
        CRemoteTextAppIntegration *this,
        unsigned int a2,
        unsigned int a3,
        const unsigned __int8 *a4)
{
  unsigned int v4; // ebx
  int v7; // eax
  int v8; // eax
  int v9; // edx
  int v10; // ecx
  unsigned __int64 retaddr; // [rsp+38h] [rbp+0h]
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF

  v4 = 0;
  v13 = 0;
  if ( *((_QWORD *)this + 16) )
  {
    v7 = MsgBlobCreateShared(a4, a3, &v13);
    v4 = v7;
    if ( v7 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(*((_QWORD *)this + 16) + 8LL) + 32LL))(
             *((_QWORD *)this + 16) + 8LL,
             a2,
             v13);
      v4 = v8;
      if ( v8 < 0 && (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
        McTemplateU0sqq_EventWriteTransfer(v10, v9, (unsigned int)"CRemoteTextAppIntegration::SendKeyToHost", 967, v8);
    }
    else
    {
      if ( v7 == -2147024882 )
        TerminateProcessOnMemoryExhaustion(0);
      FailFastWithHR(v4, retaddr, 0x3C6u);
    }
  }
  MsgRelease(v13);
  return v4;
}

```

## disassembly

```asm
0x180025380  mov     r11, rsp
0x180025383  mov     [r11+10h], rbx
0x180025387  mov     [r11+18h], rsi
0x18002538b  push    rdi
0x18002538c  sub     rsp, 30h
0x180025390  xor     ebx, ebx
0x180025392  mov     eax, r8d
0x180025395  mov     esi, edx
0x180025397  mov     rdi, rcx
0x18002539a  mov     [r11+8], rbx
0x18002539e  cmp     [rcx+80h], rbx
0x1800253a5  jz      short loc_180025422
0x1800253a7  lea     r8, [r11+8]
0x1800253ab  mov     edx, eax
0x1800253ad  mov     rcx, r9
0x1800253b0  call    cs:__imp_MsgBlobCreateShared
0x1800253b6  mov     ebx, eax
0x1800253b8  test    eax, eax
0x1800253ba  jns     short loc_1800253DF
0x1800253bc  cmp     eax, 8007000Eh
0x1800253c1  jnz     short loc_1800253CB
0x1800253c3  xor     ecx, ecx; FailedAllocationSize
0x1800253c5  call    cs:__imp_TerminateProcessOnMemoryExhaustion
0x1800253cb  mov     rdx, [rsp+38h]; unsigned __int64
0x1800253d0  mov     r8d, 3C6h; unsigned __int64
0x1800253d6  mov     ecx, ebx; int
0x1800253d8  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x1800253dd  jmp     short loc_180025422
0x1800253df  mov     rcx, [rdi+80h]
0x1800253e6  mov     edx, esi
0x1800253e8  mov     r8, [rsp+38h+arg_0]
0x1800253ed  add     rcx, 8
0x1800253f1  mov     rax, [rcx]
0x1800253f4  mov     rax, [rax+20h]
0x1800253f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253fd  mov     ebx, eax
0x1800253ff  test    eax, eax
0x180025401  jns     short loc_180025422
0x180025403  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18002540a  jz      short loc_180025422
0x18002540c  mov     r9d, 3C7h
0x180025412  mov     [rsp+38h+var_18], eax
0x180025416  lea     r8, aCremotetextapp_0; "CRemoteTextAppIntegration::SendKeyToHos"...
0x18002541d  call    McTemplateU0sqq_EventWriteTransfer
0x180025422  mov     rcx, [rsp+38h+arg_0]
0x180025427  call    cs:__imp_MsgRelease
0x18002542d  mov     rsi, [rsp+38h+arg_10]
0x180025432  mov     eax, ebx
0x180025434  mov     rbx, [rsp+38h+arg_8]
0x180025439  add     rsp, 30h
0x18002543d  pop     rdi
0x18002543e  retn
```
