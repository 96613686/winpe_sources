# CommonUtil::CMpWppTraceBase::Close(void)

- ea: `0x1400f3860`
- end: `0x1400f395c`
- name: `?Close@CMpWppTraceBase@CommonUtil@@UEAAXXZ`
- size: `252`
- prototype: `void __fastcall(CommonUtil::CMpWppTraceBase *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400f3770`
- `0x1400f37e0`

## callees

- `0x14000c010`
- `0x14007d210`
- `0x1400f3860`
- `0x1400f395c`

## import_xrefs

- `KERNEL32!SwitchToThread` at `0x1400f38f3`
- `KERNEL32!SwitchToThread` at `0x1400f38f3`
- `KERNEL32!CloseHandle` at `0x1400f38b4`
- `KERNEL32!CloseHandle` at `0x1400f38b4`
- `ADVAPI32!ControlTraceW` at `0x1400f38d3`
- `ADVAPI32!ControlTraceW` at `0x1400f38d3`

## pseudocode

```c
void __fastcall CommonUtil::CMpWppTraceBase::Close(CommonUtil::CMpWppTraceBase *this)
{
  TRACEHANDLE v1; // rbp
  int v3; // eax
  __int64 v4; // r9
  __int64 v5; // r8
  void *v6; // rcx
  unsigned __int64 i; // rsi
  signed int v8; // eax
  unsigned int v9; // ebx

  v1 = *((_QWORD *)this + 3);
  if ( v1 )
  {
    v3 = *((_DWORD *)this + 13);
    v4 = *((_QWORD *)this + 5);
    v5 = *((unsigned int *)this + 12);
    *((_QWORD *)this + 3) = 0;
    CommonUtil::EnableModulesWpp(v1, 0, v5, v4, v3);
    v6 = (void *)*((_QWORD *)this + 4);
    if ( v6 && v6 != (void *)-1LL )
    {
      CloseHandle(v6);
      *((_QWORD *)this + 4) = 0;
    }
    for ( i = 0; i < 0xA; ++i )
    {
      v8 = ControlTraceW(v1, 0, *((PEVENT_TRACE_PROPERTIES *)this + 2), 1u);
      v9 = v8;
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      if ( !(unsigned int)IsOutOfMemoryError(v9) )
        break;
      SwitchToThread();
    }
    if ( (int)(v9 + 0x80000000) >= 0
      && v9 != -2147020695
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, &WPP_69ab96dea61b39c0c05cd0a3fd1238e8_Traceguids, v9);
    }
  }
}

```

## disassembly

```asm
0x1400f3860  mov     [rsp+arg_0], rbx
0x1400f3865  mov     [rsp+arg_8], rbp
0x1400f386a  mov     [rsp+arg_10], rsi
0x1400f386f  push    rdi
0x1400f3870  sub     rsp, 30h
0x1400f3874  mov     rbp, [rcx+18h]
0x1400f3878  mov     rdi, rcx
0x1400f387b  test    rbp, rbp
0x1400f387e  jz      loc_1400F3947
0x1400f3884  mov     eax, [rcx+34h]
0x1400f3887  xor     edx, edx
0x1400f3889  mov     r9, [rcx+28h]
0x1400f388d  mov     r8d, [rcx+30h]
0x1400f3891  mov     qword ptr [rcx+18h], 0
0x1400f3899  mov     rcx, rbp
0x1400f389c  mov     [rsp+38h+var_18], eax
0x1400f38a0  call    ?EnableModulesWpp@CommonUtil@@YAJ_K_NK0W4tagMP_FEATURE@@@Z; CommonUtil::EnableModulesWpp(unsigned __int64,bool,ulong,unsigned __int64,tagMP_FEATURE)
0x1400f38a5  mov     rcx, [rdi+20h]; hObject
0x1400f38a9  test    rcx, rcx
0x1400f38ac  jz      short loc_1400F38C2
0x1400f38ae  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400f38b2  jz      short loc_1400F38C2
0x1400f38b4  call    cs:__imp_CloseHandle
0x1400f38ba  mov     qword ptr [rdi+20h], 0
0x1400f38c2  xor     esi, esi
0x1400f38c4  mov     r8, [rdi+10h]; Properties
0x1400f38c8  mov     r9d, 1; ControlCode
0x1400f38ce  xor     edx, edx; InstanceName
0x1400f38d0  mov     rcx, rbp; TraceHandle
0x1400f38d3  call    cs:__imp_ControlTraceW
0x1400f38d9  mov     ebx, eax
0x1400f38db  test    eax, eax
0x1400f38dd  jle     short loc_1400F38E8
0x1400f38df  movzx   ebx, ax
0x1400f38e2  or      ebx, 80070000h
0x1400f38e8  mov     ecx, ebx
0x1400f38ea  call    IsOutOfMemoryError
0x1400f38ef  test    eax, eax
0x1400f38f1  jz      short loc_1400F3902
0x1400f38f3  call    cs:__imp_SwitchToThread
0x1400f38f9  inc     rsi
0x1400f38fc  cmp     rsi, 0Ah
0x1400f3900  jb      short loc_1400F38C4
0x1400f3902  mov     ecx, 80000000h
0x1400f3907  lea     eax, [rbx+rcx]
0x1400f390a  test    ecx, eax
0x1400f390c  jnz     short loc_1400F3947
0x1400f390e  cmp     ebx, 80071069h
0x1400f3914  jz      short loc_1400F3947
0x1400f3916  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f391d  lea     rax, WPP_GLOBAL_Control
0x1400f3924  cmp     rcx, rax
0x1400f3927  jz      short loc_1400F3947
0x1400f3929  test    byte ptr [rcx+1Ch], 1
0x1400f392d  jz      short loc_1400F3947
0x1400f392f  mov     rcx, [rcx+10h]
0x1400f3933  lea     r8, WPP_69ab96dea61b39c0c05cd0a3fd1238e8_Traceguids
0x1400f393a  mov     edx, 11h
0x1400f393f  mov     r9d, ebx
0x1400f3942  call    WPP_SF_d
0x1400f3947  mov     rbx, [rsp+38h+arg_0]
0x1400f394c  mov     rbp, [rsp+38h+arg_8]
0x1400f3951  mov     rsi, [rsp+38h+arg_10]
0x1400f3956  add     rsp, 30h
0x1400f395a  pop     rdi
0x1400f395b  retn
```
