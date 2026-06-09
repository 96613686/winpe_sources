# ShieldProvider::Tracer::Close(void)

- ea: `0x140002a8c`
- end: `0x140002b56`
- name: `?Close@Tracer@ShieldProvider@@QEAAXXZ`
- size: `202`
- prototype: `void __fastcall(ShieldProvider::Tracer *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400029bc`

## callees

- `0x140002a8c`
- `0x140002b5c`
- `0x140003640`
- `0x14000e67c`

## import_xrefs

- `KERNEL32!SwitchToThread` at `0x140002af9`
- `KERNEL32!SwitchToThread` at `0x140002af9`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x140002ad7`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x140002ad7`

## pseudocode

```c
void __fastcall ShieldProvider::Tracer::Close(ShieldProvider::Tracer *this)
{
  TRACEHANDLE v1; // rbp
  unsigned int v3; // r9d
  unsigned __int64 v4; // rdx
  unsigned __int64 i; // rsi
  signed int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // [rsp+20h] [rbp-38h]

  v1 = *((_QWORD *)this + 4);
  if ( v1 )
  {
    v3 = *((_DWORD *)this + 10);
    v4 = *((_QWORD *)this + 4);
    v8 = *((_DWORD *)this + 11);
    *((_QWORD *)this + 4) = 0;
    ShieldProvider::Tracer::EnableModules(this, v4, 0, v3, v8);
    for ( i = 0; i < 0xA; ++i )
    {
      v6 = ControlTraceW(v1, 0, *((PEVENT_TRACE_PROPERTIES *)this + 342), 1u);
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      if ( !(unsigned int)IsOutOfMemoryError(v7) )
        break;
      SwitchToThread();
    }
    if ( (int)(v7 + 0x80000000) >= 0
      && v7 != -2147020695
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_2c725f389e6a321be0c37ed6ef950991_Traceguids, v7);
    }
  }
}

```

## disassembly

```asm
0x140002a8c  push    rbx
0x140002a8e  push    rbp
0x140002a8f  push    rsi
0x140002a90  push    rdi
0x140002a91  sub     rsp, 38h
0x140002a95  mov     rbp, [rcx+20h]
0x140002a99  mov     rdi, rcx
0x140002a9c  test    rbp, rbp
0x140002a9f  jz      loc_140002B4D
0x140002aa5  mov     eax, [rcx+2Ch]
0x140002aa8  xor     r8d, r8d; int
0x140002aab  mov     r9d, [rcx+28h]; unsigned int
0x140002aaf  mov     rdx, rbp; unsigned __int64
0x140002ab2  mov     [rsp+58h+var_38], eax; unsigned int
0x140002ab6  mov     qword ptr [rcx+20h], 0
0x140002abe  call    ?EnableModules@Tracer@ShieldProvider@@AEAAJ_KHKK@Z; ShieldProvider::Tracer::EnableModules(unsigned __int64,int,ulong,ulong)
0x140002ac3  xor     esi, esi
0x140002ac5  mov     r8, [rdi+0AB0h]; Properties
0x140002acc  mov     r9d, 1; ControlCode
0x140002ad2  xor     edx, edx; InstanceName
0x140002ad4  mov     rcx, rbp; TraceHandle
0x140002ad7  call    cs:__imp_ControlTraceW
0x140002add  mov     ebx, eax
0x140002adf  test    eax, eax
0x140002ae1  jz      short loc_140002AEE
0x140002ae3  jle     short loc_140002AEE
0x140002ae5  movzx   ebx, ax
0x140002ae8  or      ebx, 80070000h
0x140002aee  mov     ecx, ebx
0x140002af0  call    IsOutOfMemoryError
0x140002af5  test    eax, eax
0x140002af7  jz      short loc_140002B08
0x140002af9  call    cs:__imp_SwitchToThread
0x140002aff  inc     rsi
0x140002b02  cmp     rsi, 0Ah
0x140002b06  jb      short loc_140002AC5
0x140002b08  mov     ecx, 80000000h
0x140002b0d  lea     eax, [rbx+rcx]
0x140002b10  test    ecx, eax
0x140002b12  jnz     short loc_140002B4D
0x140002b14  cmp     ebx, 80071069h
0x140002b1a  jz      short loc_140002B4D
0x140002b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b23  lea     rax, WPP_GLOBAL_Control
0x140002b2a  cmp     rcx, rax
0x140002b2d  jz      short loc_140002B4D
0x140002b2f  test    byte ptr [rcx+1Ch], 1
0x140002b33  jz      short loc_140002B4D
0x140002b35  mov     rcx, [rcx+10h]
0x140002b39  lea     r8, WPP_2c725f389e6a321be0c37ed6ef950991_Traceguids
0x140002b40  mov     edx, 0Ah
0x140002b45  mov     r9d, ebx
0x140002b48  call    WPP_SF_d
0x140002b4d  add     rsp, 38h
0x140002b51  pop     rdi
0x140002b52  pop     rsi
0x140002b53  pop     rbp
0x140002b54  pop     rbx
0x140002b55  retn
```
