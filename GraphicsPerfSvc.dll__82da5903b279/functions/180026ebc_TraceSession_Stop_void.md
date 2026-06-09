# TraceSession::Stop(void)

- ea: `0x180026ebc`
- end: `0x180026f87`
- name: `?Stop@TraceSession@@QEAAXXZ`
- size: `203`
- prototype: `void __fastcall(TraceSession *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001a850`

## callees

- `0x1800047f0`
- `0x18001b044`
- `0x180026ebc`
- `0x180026fbc`

## import_xrefs

- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180026f22`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180026f22`

## string_xrefs

- `0x180026f2d`: `onecore\windows\directx\dxg\common\etwtracesession\tracesession.cpp`

## pseudocode

```c
void __fastcall TraceSession::Stop(TraceSession *this)
{
  void *v2; // rcx
  unsigned int v3; // r8d
  TRACEHANDLE v4; // rcx
  struct _EVENT_TRACE_PROPERTIES *v5; // r8
  ULONG v6; // eax
  int v7; // [rsp+20h] [rbp-18h]
  const char *v8; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 )
  {
    memset_0(v2, 0, *((_QWORD *)this + 15) - *((_QWORD *)this + 14));
    **((_DWORD **)this + 8) = *((_DWORD *)this + 30) - *((_DWORD *)this + 28);
    *(_DWORD *)(*((_QWORD *)this + 8) + 44LL) = 0x20000;
    *(_DWORD *)(*((_QWORD *)this + 8) + 116LL) = 120;
    if ( !*((_BYTE *)this + 104) )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0xF2, v3, (const char *)0x8000FFFFLL, v7);
    v4 = *((_QWORD *)this + 10);
    if ( !v4 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0xF3, v3, (const char *)0x8000FFFFLL, v7);
    v5 = (struct _EVENT_TRACE_PROPERTIES *)*((_QWORD *)this + 8);
    *((_BYTE *)this + 104) = 0;
    v6 = ControlTraceW(v4, 0, v5, 1u);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecore\\windows\\directx\\dxg\\common\\etwtracesession\\tracesession.cpp",
      (const char *)v6,
      (unsigned int)"Error occured while stopping trace.",
      v8);
    *((_QWORD *)this + 10) = 0;
  }
}

```

## disassembly

```asm
0x180026ebc  push    rbx
0x180026ebe  sub     rsp, 30h
0x180026ec2  mov     rbx, rcx
0x180026ec5  mov     rcx, [rcx+40h]; void *
0x180026ec9  test    rcx, rcx
0x180026ecc  jz      loc_180026F55
0x180026ed2  mov     r8, [rbx+78h]
0x180026ed6  xor     edx, edx; Val
0x180026ed8  sub     r8, [rbx+70h]; Size
0x180026edc  call    memset_0
0x180026ee1  mov     rax, [rbx+40h]
0x180026ee5  mov     ecx, [rbx+78h]
0x180026ee8  sub     ecx, [rbx+70h]
0x180026eeb  mov     [rax], ecx
0x180026eed  mov     rax, [rbx+40h]
0x180026ef1  mov     dword ptr [rax+2Ch], 20000h
0x180026ef8  mov     rax, [rbx+40h]
0x180026efc  mov     dword ptr [rax+74h], 78h ; 'x'
0x180026f03  cmp     byte ptr [rbx+68h], 0
0x180026f07  jz      short loc_180026F71
0x180026f09  mov     rcx, [rbx+50h]; TraceHandle
0x180026f0d  test    rcx, rcx
0x180026f10  jz      short loc_180026F5B
0x180026f12  mov     r8, [rbx+40h]; Properties
0x180026f16  mov     r9d, 1; ControlCode
0x180026f1c  xor     edx, edx; InstanceName
0x180026f1e  mov     byte ptr [rbx+68h], 0
0x180026f22  call    cs:__imp_ControlTraceW
0x180026f28  mov     rcx, [rsp+38h]; this
0x180026f2d  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\dxg\\common"...
0x180026f34  mov     r9d, eax; char *
0x180026f37  mov     edx, 0F8h; void *
0x180026f3c  lea     rax, aErrorOccuredWh_1; "Error occured while stopping trace."
0x180026f43  mov     qword ptr [rsp+38h+var_18], rax; unsigned int
0x180026f48  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180026f4d  mov     qword ptr [rbx+50h], 0
0x180026f55  add     rsp, 30h
0x180026f59  pop     rbx
0x180026f5a  retn
0x180026f5b  mov     rcx, [rsp+38h]; this
0x180026f60  mov     edx, 0F3h; void *
0x180026f65  mov     r9d, 8000FFFFh; char *
0x180026f6b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180026f71  mov     rcx, [rsp+38h]; this
0x180026f76  mov     edx, 0F2h; void *
0x180026f7b  mov     r9d, 8000FFFFh; char *
0x180026f81  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
