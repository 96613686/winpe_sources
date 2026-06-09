# TraceSession::OpenTrace(ITraceConsumer *)

- ea: `0x180026b48`
- end: `0x180026bfb`
- name: `?OpenTrace@TraceSession@@QEAAXPEAUITraceConsumer@@@Z`
- size: `179`
- prototype: `void __fastcall(TraceSession *__hidden this, struct ITraceConsumer *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010070`

## callees

- `0x180021860`
- `0x1800261f4`
- `0x180026b48`

## import_xrefs

- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180026bbf`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180026bbf`

## string_xrefs

- `0x180026bd4`: `onecore\windows\directx\dxg\common\etwtracesession\tracesession.cpp`

## pseudocode

```c
void __fastcall TraceSession::OpenTrace(TraceSession *this, struct ITraceConsumer *a2)
{
  __int64 v3; // rdx
  TRACEHANDLE v4; // rax
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_BYTE *)this + 104) )
  {
    *(_QWORD *)(*((_QWORD *)this + 9) + 8LL) = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this);
    *(_DWORD *)(*((_QWORD *)this + 9) + 28LL) = 256;
  }
  else
  {
    **((_QWORD **)this + 9) = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
  }
  *(_DWORD *)(*((_QWORD *)this + 9) + 28LL) |= 0x10001000u;
  *(_QWORD *)(*((_QWORD *)this + 9) + 424LL) = EventRecordCallback;
  *(_QWORD *)(*((_QWORD *)this + 9) + 400LL) = BufferRecordCallback;
  *(_QWORD *)(*((_QWORD *)this + 9) + 440LL) = v3;
  v4 = OpenTraceW(*((PEVENT_TRACE_LOGFILEW *)this + 9));
  *((_QWORD *)this + 11) = v4;
  if ( v4 == -1 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xD4,
      (unsigned int)"onecore\\windows\\directx\\dxg\\common\\etwtracesession\\tracesession.cpp",
      v5);
  *((_QWORD *)this + 12) = *(_QWORD *)(*((_QWORD *)this + 9) + 376LL);
}

```

## disassembly

```asm
0x180026b48  push    rbx
0x180026b4a  sub     rsp, 20h
0x180026b4e  cmp     byte ptr [rcx+68h], 0
0x180026b52  mov     rbx, rcx
0x180026b55  jz      short loc_180026B71
0x180026b57  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026b5c  mov     r8, [rbx+48h]
0x180026b60  mov     [r8+8], rax
0x180026b64  mov     rax, [rbx+48h]
0x180026b68  mov     dword ptr [rax+1Ch], 100h
0x180026b6f  jmp     short loc_180026B81
0x180026b71  add     rcx, 20h ; ' '
0x180026b75  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026b7a  mov     rcx, [rbx+48h]
0x180026b7e  mov     [rcx], rax
0x180026b81  mov     rax, [rbx+48h]
0x180026b85  lea     rcx, EventRecordCallback
0x180026b8c  or      dword ptr [rax+1Ch], 10001000h
0x180026b93  mov     rax, [rbx+48h]
0x180026b97  mov     [rax+1A8h], rcx
0x180026b9e  lea     rcx, BufferRecordCallback
0x180026ba5  mov     rax, [rbx+48h]
0x180026ba9  mov     [rax+190h], rcx
0x180026bb0  mov     rax, [rbx+48h]
0x180026bb4  mov     [rax+1B8h], rdx
0x180026bbb  mov     rcx, [rbx+48h]; Logfile
0x180026bbf  call    cs:__imp_OpenTraceW
0x180026bc5  mov     [rbx+58h], rax
0x180026bc9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026bcd  jnz     short loc_180026BE6
0x180026bcf  mov     rcx, [rsp+28h]; this
0x180026bd4  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\dxg\\common"...
0x180026bdb  mov     edx, 0D4h; void *
0x180026be0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180026be6  mov     rax, [rbx+48h]
0x180026bea  mov     rcx, [rax+178h]
0x180026bf1  mov     [rbx+60h], rcx
0x180026bf5  add     rsp, 20h
0x180026bf9  pop     rbx
0x180026bfa  retn
```
