# UaspAllocatePool

- ea: `0x1400052b8`
- end: `0x14000534f`
- name: `UaspAllocatePool`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140001154`
- `0x1400015cc`
- `0x140001b64`
- `0x140002070`
- `0x140003b90`
- `0x140004120`
- `0x140004f40`
- `0x140005040`
- `0x140005744`
- `0x140006dc8`

## callees

- `0x14000492c`
- `0x1400052b8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400052d5`
- `ntoskrnl!ExAllocatePool2` at `0x1400052d5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000530b`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000530b`

## pseudocode

```c
__int64 __fastcall UaspAllocatePool(__int64 a1, __int64 a2)
{
  char v2; // di
  __int64 Pool2; // rbx
  int Default; // eax
  int v5; // edx
  int v6; // r8d

  v2 = a2;
  Pool2 = ExAllocatePool2(64, a2, 1969320816);
  if ( !Pool2 && gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    WPP_RECORDER_SF_dD(Default, v5, v6, 10, (__int64)WPP_36185c522d943f8d0ee1935152861c3e_Traceguids, v2, 112);
  }
  return Pool2;
}

```

## disassembly

```asm
0x1400052b8  mov     [rsp+arg_0], rbx
0x1400052bd  mov     [rsp+arg_8], rsi
0x1400052c2  push    rdi
0x1400052c3  sub     rsp, 40h
0x1400052c7  mov     ecx, 40h ; '@'
0x1400052cc  mov     r8d, 75617370h
0x1400052d2  mov     rdi, rdx
0x1400052d5  call    cs:__imp_ExAllocatePool2
0x1400052dc  nop     dword ptr [rax+rax+00h]
0x1400052e1  mov     rbx, rax
0x1400052e4  test    rax, rax
0x1400052e7  jnz     short loc_14000533B
0x1400052e9  cmp     cs:gTracingEnabled, al
0x1400052ef  jz      short loc_14000533B
0x1400052f1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400052f8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400052ff  jz      short loc_14000533B
0x140005301  mov     rcx, cs:WPP_GLOBAL_Control
0x140005308  lea     esi, [rbx+0Ah]
0x14000530b  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140005312  nop     dword ptr [rax+rax+00h]
0x140005317  mov     [rsp+48h+var_18], 75617370h
0x14000531f  movzx   r9d, si
0x140005323  mov     rcx, rax
0x140005326  mov     [rsp+48h+var_20], edi
0x14000532a  lea     rax, WPP_36185c522d943f8d0ee1935152861c3e_Traceguids
0x140005331  mov     [rsp+48h+var_28], rax
0x140005336  call    WPP_RECORDER_SF_dD
0x14000533b  mov     rsi, [rsp+48h+arg_8]
0x140005340  mov     rax, rbx
0x140005343  mov     rbx, [rsp+48h+arg_0]
0x140005348  add     rsp, 40h
0x14000534c  pop     rdi
0x14000534d  retn
```
