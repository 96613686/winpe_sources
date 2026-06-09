# Register_WaitForControllerReady

- ea: `0x14001b790`
- end: `0x14001b8a6`
- name: `Register_WaitForControllerReady`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001b3b8`

## callees

- `0x14001ac48`
- `0x14001ad0c`
- `0x14001b790`
- `0x14001f830`
- `0x14001fb30`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14001b822`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001b822`

## pseudocode

```c
__int64 __fastcall Register_WaitForControllerReady(__int64 a1)
{
  __int64 v2; // rsi
  int v3; // ebx
  char v4; // bp
  int v5; // edx
  union _LARGE_INTEGER Interval; // [rsp+70h] [rbp+8h] BYREF

  Interval.QuadPart = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
      4,
      6,
      71,
      (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids);
  if ( (unsigned __int8)Controller_IsControllerAccessible(*(_QWORD *)(a1 + 8)) )
  {
    v2 = *(_QWORD *)(a1 + 32);
    v3 = 100;
    v4 = 0;
    while ( (XilRegister_ReadUlong(a1, v2 + 4) & 0x800) != 0 )
    {
      if ( !v3 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v5) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
            v5,
            6,
            73,
            (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids,
            16);
        }
        return 3221225473LL;
      }
      Interval.QuadPart = -1000000;
      KeDelayExecutionThread(0, 0, &Interval);
      --v3;
      v4 += 100;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 4;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
        v5,
        6,
        72,
        (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids,
        v4);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001b790  push    rbx
0x14001b792  push    rbp
0x14001b793  push    rsi
0x14001b794  push    rdi
0x14001b795  push    r12
0x14001b797  push    r14
0x14001b799  sub     rsp, 38h
0x14001b79d  mov     rdi, rcx
0x14001b7a0  mov     qword ptr [rsp+68h+Interval], 0
0x14001b7a9  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001b7b0  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001b7b7  lea     r12, WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids
0x14001b7be  jz      short loc_14001B7DE
0x14001b7c0  mov     rcx, [rcx+8]
0x14001b7c4  mov     r9d, 47h ; 'G'
0x14001b7ca  mov     dl, 4
0x14001b7cc  mov     [rsp+68h+var_48], r12
0x14001b7d1  mov     rcx, [rcx+48h]
0x14001b7d5  lea     r8d, [r9-41h]
0x14001b7d9  call    WPP_RECORDER_SF_
0x14001b7de  mov     rcx, [rdi+8]
0x14001b7e2  call    Controller_IsControllerAccessible
0x14001b7e7  test    al, al
0x14001b7e9  jz      loc_14001B896
0x14001b7ef  mov     rsi, [rdi+20h]
0x14001b7f3  mov     ebx, 64h ; 'd'
0x14001b7f8  xor     ebp, ebp
0x14001b7fa  lea     rdx, [rsi+4]
0x14001b7fe  mov     rcx, rdi
0x14001b801  call    XilRegister_ReadUlong
0x14001b806  bt      eax, 0Bh
0x14001b80a  jnb     short loc_14001B86B
0x14001b80c  test    ebx, ebx
0x14001b80e  jz      short loc_14001B835
0x14001b810  lea     r8, [rsp+68h+Interval]; Interval
0x14001b815  mov     qword ptr [rsp+68h+Interval], 0FFFFFFFFFFF0BDC0h
0x14001b81e  xor     edx, edx; Alertable
0x14001b820  xor     ecx, ecx; WaitMode
0x14001b822  call    cs:__imp_KeDelayExecutionThread
0x14001b829  nop     dword ptr [rax+rax+00h]
0x14001b82e  dec     ebx
0x14001b830  add     ebp, 64h ; 'd'
0x14001b833  jmp     short loc_14001B7FA
0x14001b835  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14001b83c  jz      short loc_14001B864
0x14001b83e  mov     rcx, [rdi+8]
0x14001b842  mov     r9d, 49h ; 'I'
0x14001b848  mov     [rsp+68h+var_40], 2710h
0x14001b850  mov     dl, 2
0x14001b852  mov     [rsp+68h+var_48], r12
0x14001b857  mov     rcx, [rcx+48h]
0x14001b85b  lea     r8d, [r9-43h]
0x14001b85f  call    WPP_RECORDER_SF_d
0x14001b864  mov     eax, 0C0000001h
0x14001b869  jmp     short loc_14001B898
0x14001b86b  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14001b872  jz      short loc_14001B896
0x14001b874  mov     rcx, [rdi+8]
0x14001b878  mov     r9d, 48h ; 'H'
0x14001b87e  mov     [rsp+68h+var_40], ebp
0x14001b882  mov     dl, 4
0x14001b884  mov     [rsp+68h+var_48], r12
0x14001b889  mov     rcx, [rcx+48h]
0x14001b88d  lea     r8d, [r9-42h]
0x14001b891  call    WPP_RECORDER_SF_d
0x14001b896  xor     eax, eax
0x14001b898  add     rsp, 38h
0x14001b89c  pop     r14
0x14001b89e  pop     r12
0x14001b8a0  pop     rdi
0x14001b8a1  pop     rsi
0x14001b8a2  pop     rbp
0x14001b8a3  pop     rbx
0x14001b8a4  retn
```
