# TraceSession::Start(TraceSession::Properties)

- ea: `0x180026c04`
- end: `0x180026eb5`
- name: `?Start@TraceSession@@QEAAXUProperties@1@@Z`
- size: `689`
- prototype: `void __fastcall(TraceSession *__hidden this, struct Properties)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180010070`

## callees

- `0x1800047f0`
- `0x180004b41`
- `0x180016ef0`
- `0x18001b044`
- `0x180021860`
- `0x180026908`
- `0x180026c04`
- `0x180026f90`
- `0x180026fbc`
- `0x18002708c`

## import_xrefs

- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180026d72`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180026e52`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180026d72`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180026e52`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180026dde`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180026dde`

## string_xrefs

- `0x180026d84`: `Trace start failed -> attempting to stop`
- `0x180026e71`: `onecore\windows\directx\dxg\common\etwtracesession\tracesession.cpp`

## pseudocode

```c
void __fastcall TraceSession::Start(TraceSession *this, struct Properties a2)
{
  __int64 v4; // rax
  __int64 v5; // r15
  __int64 v6; // rax
  __int64 v7; // rax
  _DWORD **v8; // rsi
  __int64 v9; // r14
  __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rbp
  __int64 v13; // rax
  unsigned __int64 v14; // rbx
  _DWORD *v15; // rax
  __int64 v16; // rcx
  const void *v17; // rax
  __int64 v18; // rdx
  const WCHAR *v19; // rax
  ULONG started; // eax
  unsigned int v21; // r8d
  const WCHAR *v22; // rax
  ULONG v23; // eax
  ULONG v24; // ebx
  __int64 v25; // rdx
  int v26; // ecx
  const char *v27; // rcx
  const WCHAR *v28; // rax
  int v29; // [rsp+20h] [rbp-78h]
  const char *v30; // [rsp+28h] [rbp-70h]
  _BYTE v31[104]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v4 = std::wstring::wstring(v31, this);
  v5 = StringBytesRequired(v4);
  v6 = std::wstring::wstring(v31, (char *)this + 32);
  v7 = StringBytesRequired(v6);
  if ( !*((_QWORD *)this + 8) )
  {
    v8 = (_DWORD **)((char *)this + 112);
    v9 = *((_QWORD *)this + 15);
    v10 = *((_QWORD *)this + 14);
    v11 = v9 - v10;
    v12 = v7 + v5 + 120;
    if ( v12 >= v9 - v10 )
    {
      if ( v12 <= v11 )
        goto LABEL_9;
      if ( v12 > *((_QWORD *)this + 16) - v10 )
      {
        std::vector<char>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 112, v12);
        goto LABEL_9;
      }
      v14 = v12 - v11;
      memset_0(*((void **)this + 15), 0, v12 - v11);
      v13 = v14 + v9;
    }
    else
    {
      v13 = v10 + v12;
    }
    *((_QWORD *)this + 15) = v13;
LABEL_9:
    v15 = *v8;
    *((_QWORD *)this + 8) = *v8;
    *v15 = v12;
    *(_DWORD *)(*((_QWORD *)this + 8) + 40LL) = 1;
    *(_DWORD *)(*((_QWORD *)this + 8) + 44LL) = 0x20000;
    *(_DWORD *)(*((_QWORD *)this + 8) + 64LL) = 256;
    *(_DWORD *)(*((_QWORD *)this + 8) + 116LL) = 120;
    *(_DWORD *)(*((_QWORD *)this + 8) + 48LL) = a2.lpVtbl->QueryInterface;
    *(_DWORD *)(*((_QWORD *)this + 8) + 52LL) = HIDWORD(a2.lpVtbl->QueryInterface);
    *(_DWORD *)(*((_QWORD *)this + 8) + 56LL) = a2.lpVtbl->AddRef;
    *(_DWORD *)(*((_QWORD *)this + 8) + 68LL) = HIDWORD(a2.lpVtbl->AddRef);
    v16 = *((_QWORD *)this + 8);
    if ( *((_QWORD *)this + 6) )
    {
      *(_DWORD *)(v16 + 112) = v5 + *(_DWORD *)(v16 + 116);
      v17 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
      memmove_0((char *)*v8 + v18, v17, 2LL * *((_QWORD *)this + 6));
    }
    else
    {
      *(_DWORD *)(v16 + 112) = 0;
    }
  }
  LogTraceStart("Starting trace", 0, *((const struct _EVENT_TRACE_PROPERTIES **)this + 8));
  v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this);
  started = StartTraceW((PTRACEHANDLE)this + 10, v19, *((PEVENT_TRACE_PROPERTIES *)this + 8));
  if ( started )
  {
    LogTraceStart(
      "Trace start failed -> attempting to stop",
      started,
      *((const struct _EVENT_TRACE_PROPERTIES **)this + 8));
    memset_0(*((void **)this + 8), 0, *((_QWORD *)this + 15) - *((_QWORD *)this + 14));
    **((_DWORD **)this + 8) = *((_DWORD *)this + 30) - *((_DWORD *)this + 28);
    *(_DWORD *)(*((_QWORD *)this + 8) + 44LL) = 0x20000;
    *(_DWORD *)(*((_QWORD *)this + 8) + 116LL) = 120;
    v22 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this);
    v23 = ControlTraceW(0, v22, *((PEVENT_TRACE_PROPERTIES *)this + 8), 1u);
    v24 = v23;
    if ( !v23 || v23 == 4201 )
    {
      v25 = *((_QWORD *)this + 8);
      if ( *((_QWORD *)this + 6) )
        v26 = v5 + *(_DWORD *)(v25 + 116);
      else
        v26 = 0;
      *(_DWORD *)(v25 + 112) = v26;
      v27 = "Stop resulted in ERROR_WMI_INSTANCE_NOT_FOUND - > Retrying start";
      if ( v23 != 4201 )
        v27 = "Stop succeeded - > Retrying start";
      LogTraceStart(v27, 0, *((const struct _EVENT_TRACE_PROPERTIES **)this + 8));
      v28 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this);
      v24 = StartTraceW((PTRACEHANDLE)this + 10, v28, *((PEVENT_TRACE_PROPERTIES *)this + 8));
    }
    else
    {
      LogTraceStart("Stop failed -> aborting", v23, *((const struct _EVENT_TRACE_PROPERTIES **)this + 8));
    }
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\windows\\directx\\dxg\\common\\etwtracesession\\tracesession.cpp",
      (const char *)v24,
      (unsigned int)"Error occured while starting trace session.",
      v30);
  }
  if ( !*((_QWORD *)this + 10) )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x8A, v21, (const char *)0x8000FFFFLL, v29);
  *((_BYTE *)this + 104) = 1;
}

```

## disassembly

```asm
0x180026c04  push    rbx
0x180026c06  push    rbp
0x180026c07  push    rsi
0x180026c08  push    rdi
0x180026c09  push    r12
0x180026c0b  push    r13
0x180026c0d  push    r14
0x180026c0f  push    r15
0x180026c11  sub     rsp, 58h
0x180026c15  mov     r12, rdx
0x180026c18  mov     rdi, rcx
0x180026c1b  mov     rdx, rcx
0x180026c1e  lea     rcx, [rsp+98h+var_68]
0x180026c23  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180026c28  mov     rcx, rax
0x180026c2b  call    ?StringBytesRequired@@YA_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringBytesRequired(std::wstring)
0x180026c30  lea     rdx, [rdi+20h]
0x180026c34  mov     r15, rax
0x180026c37  lea     rcx, [rsp+98h+var_68]
0x180026c3c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180026c41  mov     rcx, rax
0x180026c44  call    ?StringBytesRequired@@YA_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringBytesRequired(std::wstring)
0x180026c49  xor     ebp, ebp
0x180026c4b  cmp     [rdi+40h], rbp
0x180026c4f  jnz     loc_180026D4A
0x180026c55  lea     rsi, [rdi+70h]
0x180026c59  mov     r14, [rsi+8]
0x180026c5d  lea     rbp, [r15+78h]
0x180026c61  mov     rdx, [rsi]
0x180026c64  mov     rcx, r14
0x180026c67  sub     rcx, rdx
0x180026c6a  add     rbp, rax
0x180026c6d  cmp     rbp, rcx
0x180026c70  jnb     short loc_180026C78
0x180026c72  lea     rax, [rdx+rbp]
0x180026c76  jmp     short loc_180026CAA
0x180026c78  jbe     short loc_180026CAE
0x180026c7a  mov     rax, [rsi+10h]
0x180026c7e  sub     rax, rdx
0x180026c81  cmp     rbp, rax
0x180026c84  jbe     short loc_180026C93
0x180026c86  mov     rdx, rbp
0x180026c89  mov     rcx, rsi
0x180026c8c  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@DV?$allocator@D@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180026c91  jmp     short loc_180026CAE
0x180026c93  mov     rbx, rbp
0x180026c96  xor     edx, edx; Val
0x180026c98  sub     rbx, rcx
0x180026c9b  mov     rcx, r14; void *
0x180026c9e  mov     r8, rbx; Size
0x180026ca1  call    memset_0
0x180026ca6  lea     rax, [rbx+r14]
0x180026caa  mov     [rsi+8], rax
0x180026cae  mov     rax, [rsi]
0x180026cb1  mov     [rdi+40h], rax
0x180026cb5  mov     [rax], ebp
0x180026cb7  xor     ebp, ebp
0x180026cb9  mov     rax, [rdi+40h]
0x180026cbd  mov     dword ptr [rax+28h], 1
0x180026cc4  mov     rax, [rdi+40h]
0x180026cc8  mov     dword ptr [rax+2Ch], 20000h
0x180026ccf  mov     rax, [rdi+40h]
0x180026cd3  mov     dword ptr [rax+40h], 100h
0x180026cda  mov     rax, [rdi+40h]
0x180026cde  mov     dword ptr [rax+74h], 78h ; 'x'
0x180026ce5  mov     rcx, [rdi+40h]
0x180026ce9  mov     eax, [r12]
0x180026ced  mov     [rcx+30h], eax
0x180026cf0  mov     rcx, [rdi+40h]
0x180026cf4  mov     eax, [r12+4]
0x180026cf9  mov     [rcx+34h], eax
0x180026cfc  mov     rcx, [rdi+40h]
0x180026d00  mov     eax, [r12+8]
0x180026d05  mov     [rcx+38h], eax
0x180026d08  mov     rcx, [rdi+40h]
0x180026d0c  mov     eax, [r12+0Ch]
0x180026d11  mov     [rcx+44h], eax
0x180026d14  mov     rcx, [rdi+40h]
0x180026d18  cmp     [rdi+30h], rbp
0x180026d1c  jz      short loc_180026D47
0x180026d1e  mov     edx, [rcx+74h]
0x180026d21  add     rdx, r15
0x180026d24  mov     [rcx+70h], edx
0x180026d27  lea     rcx, [rdi+20h]
0x180026d2b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026d30  mov     rcx, [rsi]
0x180026d33  mov     r8, [rdi+30h]
0x180026d37  add     rcx, rdx; void *
0x180026d3a  mov     rdx, rax; Src
0x180026d3d  add     r8, r8; Size
0x180026d40  call    memmove_0
0x180026d45  jmp     short loc_180026D4A
0x180026d47  mov     [rcx+70h], ebp
0x180026d4a  mov     r8, [rdi+40h]; struct _EVENT_TRACE_PROPERTIES *
0x180026d4e  lea     rcx, aStartingTrace; "Starting trace"
0x180026d55  xor     edx, edx; unsigned int
0x180026d57  call    ?LogTraceStart@@YAXPEBDKPEBU_EVENT_TRACE_PROPERTIES@@@Z; LogTraceStart(char const *,ulong,_EVENT_TRACE_PROPERTIES const *)
0x180026d5c  mov     rcx, rdi
0x180026d5f  lea     rsi, [rdi+50h]
0x180026d63  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026d68  mov     r8, [rdi+40h]; Properties
0x180026d6c  mov     rdx, rax; InstanceName
0x180026d6f  mov     rcx, rsi; TraceHandle
0x180026d72  call    cs:__imp_StartTraceW
0x180026d78  test    eax, eax
0x180026d7a  jz      loc_180026E82
0x180026d80  mov     r8, [rdi+40h]; struct _EVENT_TRACE_PROPERTIES *
0x180026d84  lea     rcx, aTraceStartFail; "Trace start failed -> attempting to sto"...
0x180026d8b  mov     edx, eax; unsigned int
0x180026d8d  call    ?LogTraceStart@@YAXPEBDKPEBU_EVENT_TRACE_PROPERTIES@@@Z; LogTraceStart(char const *,ulong,_EVENT_TRACE_PROPERTIES const *)
0x180026d92  mov     r8, [rdi+78h]
0x180026d96  xor     edx, edx; Val
0x180026d98  sub     r8, [rdi+70h]; Size
0x180026d9c  mov     rcx, [rdi+40h]; void *
0x180026da0  call    memset_0
0x180026da5  mov     ecx, [rdi+78h]
0x180026da8  sub     ecx, [rdi+70h]
0x180026dab  mov     rax, [rdi+40h]
0x180026daf  mov     [rax], ecx
0x180026db1  mov     rcx, rdi
0x180026db4  mov     rax, [rdi+40h]
0x180026db8  mov     dword ptr [rax+2Ch], 20000h
0x180026dbf  mov     rax, [rdi+40h]
0x180026dc3  mov     dword ptr [rax+74h], 78h ; 'x'
0x180026dca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026dcf  mov     r8, [rdi+40h]; Properties
0x180026dd3  mov     rdx, rax; InstanceName
0x180026dd6  xor     ecx, ecx; TraceHandle
0x180026dd8  mov     r9d, 1; ControlCode
0x180026dde  call    cs:__imp_ControlTraceW
0x180026de4  mov     ebx, eax
0x180026de6  mov     r8d, 1069h
0x180026dec  test    eax, eax
0x180026dee  jz      short loc_180026E09
0x180026df0  cmp     eax, r8d
0x180026df3  jz      short loc_180026E09
0x180026df5  mov     r8, [rdi+40h]; struct _EVENT_TRACE_PROPERTIES *
0x180026df9  lea     rcx, aStopFailedAbor; "Stop failed -> aborting"
0x180026e00  mov     edx, eax; unsigned int
0x180026e02  call    ?LogTraceStart@@YAXPEBDKPEBU_EVENT_TRACE_PROPERTIES@@@Z; LogTraceStart(char const *,ulong,_EVENT_TRACE_PROPERTIES const *)
0x180026e07  jmp     short loc_180026E5A
0x180026e09  mov     rdx, [rdi+40h]
0x180026e0d  cmp     [rdi+30h], rbp
0x180026e11  jz      short loc_180026E1B
0x180026e13  mov     ecx, [rdx+74h]
0x180026e16  add     ecx, r15d
0x180026e19  jmp     short loc_180026E1D
0x180026e1b  mov     ecx, ebp
0x180026e1d  mov     [rdx+70h], ecx
0x180026e20  lea     rax, aStopSucceededR; "Stop succeeded - > Retrying start"
0x180026e27  cmp     ebx, r8d
0x180026e2a  lea     rcx, aStopResultedIn; "Stop resulted in ERROR_WMI_INSTANCE_NOT"...
0x180026e31  mov     r8, [rdi+40h]; struct _EVENT_TRACE_PROPERTIES *
0x180026e35  cmovnz  rcx, rax; char *
0x180026e39  xor     edx, edx; unsigned int
0x180026e3b  call    ?LogTraceStart@@YAXPEBDKPEBU_EVENT_TRACE_PROPERTIES@@@Z; LogTraceStart(char const *,ulong,_EVENT_TRACE_PROPERTIES const *)
0x180026e40  mov     rcx, rdi
0x180026e43  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026e48  mov     r8, [rdi+40h]; Properties
0x180026e4c  mov     rdx, rax; InstanceName
0x180026e4f  mov     rcx, rsi; TraceHandle
0x180026e52  call    cs:__imp_StartTraceW
0x180026e58  mov     ebx, eax
0x180026e5a  mov     rcx, [rsp+98h]; this
0x180026e62  lea     rax, aErrorOccuredWh; "Error occured while starting trace sess"...
0x180026e69  mov     r9d, ebx; char *
0x180026e6c  mov     qword ptr [rsp+98h+var_78], rax; int
0x180026e71  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\dxg\\common"...
0x180026e78  mov     edx, 86h; void *
0x180026e7d  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180026e82  cmp     [rsi], rbp
0x180026e85  jz      short loc_180026E9C
0x180026e87  mov     byte ptr [rdi+68h], 1
0x180026e8b  add     rsp, 58h
0x180026e8f  pop     r15
0x180026e91  pop     r14
0x180026e93  pop     r13
0x180026e95  pop     r12
0x180026e97  pop     rdi
0x180026e98  pop     rsi
0x180026e99  pop     rbp
0x180026e9a  pop     rbx
0x180026e9b  retn
0x180026e9c  mov     rcx, [rsp+98h]; this
0x180026ea4  mov     edx, 8Ah; void *
0x180026ea9  mov     r9d, 8000FFFFh; char *
0x180026eaf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
