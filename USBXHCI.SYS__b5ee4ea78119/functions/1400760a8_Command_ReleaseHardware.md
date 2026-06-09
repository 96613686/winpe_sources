# Command_ReleaseHardware

- ea: `0x1400760a8`
- end: `0x14007619f`
- name: `Command_ReleaseHardware`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14007ada0`

## callees

- `0x14001ac48`
- `0x14003f87c`
- `0x1400760a8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140076173`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076173`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140076151`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140076151`

## pseudocode

```c
void __fastcall Command_ReleaseHardware(__int64 a1)
{
  int v2; // edx
  __int64 v3; // rdx
  void *v4; // rcx

  if ( *(_DWORD *)(a1 + 32) == 1 )
  {
    XilCommand_FreeResources(a1);
    if ( *(_QWORD *)(a1 + 96) != a1 + 96 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v2) = 3;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
        v2,
        7,
        14,
        (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids);
    }
    if ( *(_QWORD *)(a1 + 80) != a1 + 80 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v2) = 3;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
        v2,
        7,
        15,
        (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids);
    }
    v3 = *(_QWORD *)(a1 + 16);
    if ( v3 && v3 != *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL) )
    {
      imp_WppRecorderLogDelete(WPP_GLOBAL_Control, v3);
      *(_QWORD *)(a1 + 16) = 0;
    }
    v4 = *(void **)(a1 + 72);
    if ( v4 )
    {
      ExFreePoolWithTag(v4, 0x49434858u);
      *(_QWORD *)(a1 + 72) = 0;
    }
  }
  *(_DWORD *)(a1 + 32) = 2;
}

```

## disassembly

```asm
0x1400760a8  mov     [rsp+arg_0], rbx
0x1400760ad  mov     [rsp+arg_8], rbp
0x1400760b2  push    rdi
0x1400760b3  sub     rsp, 30h
0x1400760b7  cmp     dword ptr [rcx+20h], 1
0x1400760bb  mov     rbx, rcx
0x1400760be  jnz     loc_140076187
0x1400760c4  call    XilCommand_FreeResources
0x1400760c9  lea     rax, [rbx+60h]
0x1400760cd  lea     rbp, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x1400760d4  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400760db  cmp     [rax], rax
0x1400760de  jz      short loc_140076107
0x1400760e0  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x1400760e7  jz      short loc_140076107
0x1400760e9  mov     rcx, [rbx+8]
0x1400760ed  mov     r9d, 0Eh
0x1400760f3  mov     dl, 3
0x1400760f5  mov     [rsp+38h+var_18], rbp
0x1400760fa  mov     rcx, [rcx+48h]
0x1400760fe  lea     r8d, [r9-7]
0x140076102  call    WPP_RECORDER_SF_
0x140076107  lea     rax, [rbx+50h]
0x14007610b  cmp     [rax], rax
0x14007610e  jz      short loc_140076137
0x140076110  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140076117  jz      short loc_140076137
0x140076119  mov     rcx, [rbx+8]
0x14007611d  mov     r9d, 0Fh
0x140076123  mov     dl, 3
0x140076125  mov     [rsp+38h+var_18], rbp
0x14007612a  mov     rcx, [rcx+48h]
0x14007612e  lea     r8d, [r9-8]
0x140076132  call    WPP_RECORDER_SF_
0x140076137  mov     rdx, [rbx+10h]
0x14007613b  test    rdx, rdx
0x14007613e  jz      short loc_140076165
0x140076140  mov     rax, [rbx+8]
0x140076144  cmp     rdx, [rax+48h]
0x140076148  jz      short loc_140076165
0x14007614a  mov     rcx, cs:WPP_GLOBAL_Control
0x140076151  call    cs:__imp_imp_WppRecorderLogDelete
0x140076158  nop     dword ptr [rax+rax+00h]
0x14007615d  mov     qword ptr [rbx+10h], 0
0x140076165  mov     rcx, [rbx+48h]; P
0x140076169  test    rcx, rcx
0x14007616c  jz      short loc_140076187
0x14007616e  mov     edx, 49434858h; Tag
0x140076173  call    cs:__imp_ExFreePoolWithTag
0x14007617a  nop     dword ptr [rax+rax+00h]
0x14007617f  mov     qword ptr [rbx+48h], 0
0x140076187  mov     dword ptr [rbx+20h], 2
0x14007618e  mov     rbx, [rsp+38h+arg_0]
0x140076193  mov     rbp, [rsp+38h+arg_8]
0x140076198  add     rsp, 30h
0x14007619c  pop     rdi
0x14007619d  retn
```
