# WPP_RECORDER_SF_d

- ea: `0x140001db8`
- end: `0x140001e9d`
- name: `WPP_RECORDER_SF_d`
- size: `229`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, __int64, char)`
- caller_count: `144`
- callee_count: `2`
- tags: ``

## callers

- `0x140001b34`
- `0x140003ab0`
- `0x140003d30`
- `0x140004004`
- `0x140005028`
- `0x140005c24`
- `0x140005df4`
- `0x140006b60`
- `0x1400092e0`
- `0x140009720`
- `0x14000a0a8`
- `0x14000a330`
- `0x14000abe0`
- `0x14000ace0`
- `0x14000b030`
- `0x14000b2b0`
- `0x14000b3fc`
- `0x14000b670`
- `0x14000bb48`
- `0x14000c37c`
- `0x14000c6c8`
- `0x14000cc8c`
- `0x14000e900`
- `0x14000ece0`
- `0x14000f0c0`
- `0x14000f6c0`
- `0x14000fa30`
- `0x14000fca8`
- `0x14000fe90`
- `0x14000ff80`
- `0x140010b00`
- `0x140010f40`
- `0x1400115c0`
- `0x140011680`
- `0x140011e94`
- `0x1400124a0`
- `0x140013220`
- `0x140013c08`
- `0x140013ef0`
- `0x140014730`
- `0x140014d50`
- `0x140014ea0`
- `0x140015290`
- `0x140015710`
- `0x140015a40`
- `0x140015f00`
- `0x140015fc0`
- `0x140016200`
- `0x140016560`
- `0x140017230`

## callees

- `0x140001db8`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001e85`
- `WppRecorder!WppAutoLogTrace` at `0x140001e85`

## pseudocode

```c
__int64 WPP_RECORDER_SF_d(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rbx
  unsigned int v9; // edi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-48h]
  __int64 v13; // [rsp+40h] [rbp-28h]
  __int64 v14; // [rsp+48h] [rbp-20h]
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, a3 - 1) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      va,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v12, va, 4, 0, v13, v14);
}

```

## disassembly

```asm
0x140001db8  push    rbx
0x140001dba  push    rbp
0x140001dbb  push    rsi
0x140001dbc  push    rdi
0x140001dbd  push    r14
0x140001dbf  sub     rsp, 40h
0x140001dc3  mov     ebp, r8d
0x140001dc6  mov     r14, rcx
0x140001dc9  mov     ebx, r8d
0x140001dcc  shr     rbx, 10h
0x140001dd0  movzx   esi, r9w
0x140001dd4  lea     r11d, [rbp-1]
0x140001dd8  movzx   edi, dl
0x140001ddb  mov     r10d, r11d
0x140001dde  shr     r10, 5
0x140001de2  lea     rax, [rbx+rbx*4]
0x140001de6  and     r10d, 7FFh
0x140001ded  lea     rax, [r10+rax*4]
0x140001df1  mov     r10, cs:WPP_GLOBAL_Control
0x140001df8  mov     eax, [r10+rax*4+2Ch]
0x140001dfd  bt      eax, r11d
0x140001e01  jnb     short loc_140001E51
0x140001e03  lea     rcx, [rbx+rbx*4]
0x140001e07  add     rcx, rcx
0x140001e0a  cmp     [r10+rcx*8+29h], dil
0x140001e0f  jb      short loc_140001E51
0x140001e11  mov     rax, cs:pfnWppTraceMessage
0x140001e18  lea     rdx, [rsp+68h+arg_28]
0x140001e20  mov     r8, [rsp+68h+arg_20]
0x140001e28  mov     r9d, esi
0x140001e2b  mov     rcx, [r10+rcx*8+18h]
0x140001e30  mov     [rsp+68h+var_38], 0
0x140001e39  mov     [rsp+68h+var_40], 4
0x140001e42  mov     [rsp+68h+var_48], rdx
0x140001e47  mov     edx, 2Bh ; '+'
0x140001e4c  call    _guard_dispatch_icall
0x140001e51  mov     r9, [rsp+68h+arg_20]
0x140001e59  lea     rax, [rsp+68h+arg_28]
0x140001e61  mov     [rsp+68h+var_30], 0
0x140001e6a  mov     r8d, ebp
0x140001e6d  mov     [rsp+68h+var_38], 4
0x140001e76  mov     edx, edi
0x140001e78  mov     [rsp+68h+var_40], rax
0x140001e7d  mov     rcx, r14
0x140001e80  mov     word ptr [rsp+68h+var_48], si
0x140001e85  call    cs:__imp_WppAutoLogTrace
0x140001e8c  nop     dword ptr [rax+rax+00h]
0x140001e91  add     rsp, 40h
0x140001e95  pop     r14
0x140001e97  pop     rdi
0x140001e98  pop     rsi
0x140001e99  pop     rbp
0x140001e9a  pop     rbx
0x140001e9b  retn
```
