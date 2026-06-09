# Wd1dsListener::ShutdownUnSafe(bool)

- ea: `0x1400e5ef0`
- end: `0x1400e6070`
- name: `?ShutdownUnSafe@Wd1dsListener@@AEAAX_N@Z`
- size: `384`
- prototype: `void __fastcall(Wd1dsListener *__hidden this, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400e5e48`

## callees

- `0x1400144dc`
- `0x14003a5c0`
- `0x14007d210`
- `0x1400e5ef0`
- `0x140166990`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400e6041`
- `KERNEL32!CloseHandle` at `0x1400e6041`
- `ADVAPI32!CloseTrace` at `0x1400e5fe5`
- `ADVAPI32!CloseTrace` at `0x1400e5fe5`
- `ADVAPI32!ControlTraceW` at `0x1400e5f94`
- `ADVAPI32!ControlTraceW` at `0x1400e5f94`
- `RPCRT4!UuidCreate` at `0x1400e5f53`
- `RPCRT4!UuidCreate` at `0x1400e5f53`

## pseudocode

```c
void __fastcall Wd1dsListener::ShutdownUnSafe(Wd1dsListener *this, char a2, unsigned int a3)
{
  TRACEHANDLE v4; // rcx
  signed int v5; // eax
  bool v6; // zf
  ULONG v7; // eax
  CommonUtil *v8; // rcx
  void *v9; // rcx
  struct _EVENT_TRACE_PROPERTIES Properties; // [rsp+20h] [rbp-4A8h] BYREF

  if ( a2 )
  {
    if ( *((_QWORD *)this + 1) )
    {
      memset(&Properties, 0, 0x488u);
      Properties.Wnode.BufferSize = 1160;
      Properties.Wnode.Flags = 0x20000;
      UuidCreate(&Properties.Wnode.Guid);
      v4 = *((_QWORD *)this + 1);
      *(_QWORD *)&Properties.LogFileMode = 134218112;
      Properties.BufferSize = 64;
      Properties.MaximumBuffers = 64;
      Properties.LoggerNameOffset = 120;
      Properties.LogFileNameOffset = 640;
      v5 = ControlTraceW(v4, 0, &Properties, 1u);
      if ( v5 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          if ( v5 > 0 )
            v5 = (unsigned __int16)v5 | 0x80070000;
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            52,
            &WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids,
            (unsigned int)v5);
        }
      }
    }
  }
  v6 = *(_QWORD *)this == -1;
  *((_QWORD *)this + 1) = 0;
  if ( !v6 )
  {
    v7 = CloseTrace(*(_QWORD *)this);
    if ( v7
      && v7 != 7007
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 53, &WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids, v7);
    }
    *(_QWORD *)this = -1;
  }
  v8 = (CommonUtil *)*((_QWORD *)this + 2);
  if ( v8 )
  {
    CommonUtil::UtilWaitForSingleObject(v8, (void *)0xFFFFFFFFLL, a3);
    v9 = (void *)*((_QWORD *)this + 2);
    if ( v9 )
    {
      CloseHandle(v9);
      *((_QWORD *)this + 2) = 0;
    }
  }
}

```

## disassembly

```asm
0x1400e5ef0  mov     [rsp+arg_8], rbx
0x1400e5ef5  push    rbp
0x1400e5ef6  sub     rsp, 4C0h
0x1400e5efd  mov     rax, cs:__security_cookie
0x1400e5f04  xor     rax, rsp
0x1400e5f07  mov     [rsp+4C8h+var_18], rax
0x1400e5f0f  lea     rbp, WPP_GLOBAL_Control
0x1400e5f16  mov     rbx, rcx
0x1400e5f19  test    dl, dl
0x1400e5f1b  jz      loc_1400E5FD4
0x1400e5f21  cmp     qword ptr [rcx+8], 0
0x1400e5f26  jz      loc_1400E5FD4
0x1400e5f2c  xor     edx, edx; Val
0x1400e5f2e  lea     rcx, [rsp+4C8h+Properties]; void *
0x1400e5f33  mov     r8d, 488h; Size
0x1400e5f39  call    memset
0x1400e5f3e  lea     rcx, [rsp+4C8h+Properties.Wnode.Guid]; Uuid
0x1400e5f43  mov     [rsp+4C8h+Properties.Wnode.BufferSize], 488h
0x1400e5f4b  mov     [rsp+4C8h+Properties.Wnode.Flags], 20000h
0x1400e5f53  call    cs:__imp_UuidCreate
0x1400e5f59  mov     rcx, [rbx+8]; TraceHandle
0x1400e5f5d  lea     r8, [rsp+4C8h+Properties]; Properties
0x1400e5f62  mov     eax, 40h ; '@'
0x1400e5f67  mov     qword ptr [rsp+4C8h+Properties.LogFileMode], 8000180h
0x1400e5f70  xor     edx, edx; InstanceName
0x1400e5f72  mov     [rsp+4C8h+Properties.BufferSize], eax
0x1400e5f76  mov     [rsp+4C8h+Properties.MaximumBuffers], eax
0x1400e5f7a  mov     [rsp+4C8h+Properties.LoggerNameOffset], 78h ; 'x'
0x1400e5f85  lea     r9d, [rax-3Fh]; ControlCode
0x1400e5f89  mov     [rsp+4C8h+Properties.LogFileNameOffset], 280h
0x1400e5f94  call    cs:__imp_ControlTraceW
0x1400e5f9a  test    eax, eax
0x1400e5f9c  jz      short loc_1400E5FD4
0x1400e5f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e5fa5  cmp     rcx, rbp
0x1400e5fa8  jz      short loc_1400E5FD4
0x1400e5faa  test    byte ptr [rcx+1Ch], 2
0x1400e5fae  jz      short loc_1400E5FD4
0x1400e5fb0  test    eax, eax
0x1400e5fb2  jle     short loc_1400E5FBC
0x1400e5fb4  movzx   eax, ax
0x1400e5fb7  or      eax, 80070000h
0x1400e5fbc  mov     rcx, [rcx+10h]
0x1400e5fc0  lea     r8, WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids
0x1400e5fc7  mov     edx, 34h ; '4'
0x1400e5fcc  mov     r9d, eax
0x1400e5fcf  call    WPP_SF_d
0x1400e5fd4  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1400e5fd8  mov     qword ptr [rbx+8], 0
0x1400e5fe0  jz      short loc_1400E6027
0x1400e5fe2  mov     rcx, [rbx]; TraceHandle
0x1400e5fe5  call    cs:__imp_CloseTrace
0x1400e5feb  test    eax, eax
0x1400e5fed  jz      short loc_1400E6020
0x1400e5fef  cmp     eax, 1B5Fh
0x1400e5ff4  jz      short loc_1400E6020
0x1400e5ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e5ffd  cmp     rcx, rbp
0x1400e6000  jz      short loc_1400E6020
0x1400e6002  test    byte ptr [rcx+1Ch], 1
0x1400e6006  jz      short loc_1400E6020
0x1400e6008  mov     rcx, [rcx+10h]
0x1400e600c  lea     r8, WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids
0x1400e6013  mov     edx, 35h ; '5'
0x1400e6018  mov     r9d, eax
0x1400e601b  call    WPP_SF_d
0x1400e6020  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1400e6027  mov     rcx, [rbx+10h]; this
0x1400e602b  test    rcx, rcx
0x1400e602e  jz      short loc_1400E604F
0x1400e6030  or      edx, 0FFFFFFFFh; void *
0x1400e6033  call    ?UtilWaitForSingleObject@CommonUtil@@YA_NPEAXK@Z; CommonUtil::UtilWaitForSingleObject(void *,ulong)
0x1400e6038  mov     rcx, [rbx+10h]; hObject
0x1400e603c  test    rcx, rcx
0x1400e603f  jz      short loc_1400E604F
0x1400e6041  call    cs:__imp_CloseHandle
0x1400e6047  mov     qword ptr [rbx+10h], 0
0x1400e604f  mov     rcx, [rsp+4C8h+var_18]
0x1400e6057  xor     rcx, rsp; StackCookie
0x1400e605a  call    __security_check_cookie
0x1400e605f  mov     rbx, [rsp+4C8h+arg_8]
0x1400e6067  add     rsp, 4C0h
0x1400e606e  pop     rbp
0x1400e606f  retn
```
