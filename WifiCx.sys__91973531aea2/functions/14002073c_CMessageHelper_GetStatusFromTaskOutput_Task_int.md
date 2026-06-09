# CMessageHelper::GetStatusFromTaskOutput(Task *,int *)

- ea: `0x14002073c`
- end: `0x140020857`
- name: `?GetStatusFromTaskOutput@CMessageHelper@@SAHPEAVTask@@PEAH@Z`
- size: `283`
- prototype: `__int64 __fastcall(struct Task *, int *)`
- caller_count: `13`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x14005e1b0`
- `0x140072050`
- `0x140077118`
- `0x1400802f8`
- `0x140090054`
- `0x14009f9c0`
- `0x1400a42c8`
- `0x1400aebb0`
- `0x1400ba210`
- `0x1400bb200`
- `0x1400bf894`
- `0x1400c20b0`
- `0x1400c5d90`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x14002073c`
- `0x140020860`
- `0x140024a20`

## pseudocode

```c
__int64 __fastcall CMessageHelper::GetStatusFromTaskOutput(struct Task *a1, unsigned int *a2)
{
  int v3; // edx
  unsigned int OutputBuffer; // ebx
  int v5; // r8d
  unsigned int v7; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int8 *v8; // [rsp+60h] [rbp+18h] BYREF

  v7 = 0;
  v8 = 0;
  OutputBuffer = Task::get_OutputBuffer(a1, &v7, &v8);
  if ( OutputBuffer )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v3,
        1,
        10,
        (__int64)WPP_52dff22801773d96f6ef5b670d2cd017_Traceguids,
        OutputBuffer);
    }
  }
  else if ( v7 >= 0x30 )
  {
    OutputBuffer = *((_DWORD *)v8 + 9);
    if ( OutputBuffer && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_Ld(
        WPP_GLOBAL_Control->DeviceExtension,
        v3,
        v5,
        12,
        (__int64)WPP_52dff22801773d96f6ef5b670d2cd017_Traceguids,
        *(_DWORD *)v8,
        *((_DWORD *)v8 + 9));
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v3,
        1,
        11,
        (__int64)WPP_52dff22801773d96f6ef5b670d2cd017_Traceguids);
    }
    OutputBuffer = -1073676268;
  }
  if ( a2 )
    *a2 = OutputBuffer;
  return OutputBuffer;
}

```

## disassembly

```asm
0x14002073c  mov     rax, rsp
0x14002073f  mov     [rax+8], rbx
0x140020743  push    rdi
0x140020744  sub     rsp, 40h
0x140020748  mov     rdi, rdx
0x14002074b  mov     dword ptr [rax+10h], 0
0x140020752  lea     rdx, [rax+10h]; unsigned int *
0x140020756  mov     qword ptr [rax+18h], 0
0x14002075e  lea     r8, [rax+18h]; unsigned __int8 **
0x140020762  call    ?get_OutputBuffer@Task@@QEAAHPEAKPEAPEAE@Z; Task::get_OutputBuffer(ulong *,uchar * *)
0x140020767  mov     ebx, eax
0x140020769  test    eax, eax
0x14002076b  jz      short loc_1400207B2
0x14002076d  lea     rax, WPP_RECORDER_INITIALIZED
0x140020774  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002077b  jz      loc_140020842
0x140020781  mov     rcx, cs:WPP_GLOBAL_Control
0x140020788  lea     rax, WPP_52dff22801773d96f6ef5b670d2cd017_Traceguids
0x14002078f  mov     r9d, 0Ah
0x140020795  mov     [rsp+48h+var_20], ebx
0x140020799  mov     dl, 2
0x14002079b  mov     [rsp+48h+var_28], rax
0x1400207a0  mov     rcx, [rcx+40h]
0x1400207a4  lea     r8d, [r9-9]
0x1400207a8  call    WPP_RECORDER_SF_d
0x1400207ad  jmp     loc_140020842
0x1400207b2  cmp     [rsp+48h+arg_8], 30h ; '0'
0x1400207b7  jnb     short loc_1400207F8
0x1400207b9  lea     rax, WPP_RECORDER_INITIALIZED
0x1400207c0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400207c7  jz      short loc_1400207F1
0x1400207c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400207d0  lea     rax, WPP_52dff22801773d96f6ef5b670d2cd017_Traceguids
0x1400207d7  mov     r9d, 0Bh
0x1400207dd  mov     [rsp+48h+var_28], rax
0x1400207e2  mov     dl, 2
0x1400207e4  mov     rcx, [rcx+40h]
0x1400207e8  lea     r8d, [r9-0Ah]
0x1400207ec  call    WPP_RECORDER_SF_
0x1400207f1  mov     ebx, 0C0010014h
0x1400207f6  jmp     short loc_140020842
0x1400207f8  mov     rcx, [rsp+48h+arg_10]
0x1400207fd  mov     ebx, [rcx+24h]
0x140020800  test    ebx, ebx
0x140020802  jz      short loc_140020842
0x140020804  lea     rax, WPP_RECORDER_INITIALIZED
0x14002080b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020812  jz      short loc_140020842
0x140020814  mov     eax, [rcx]
0x140020816  mov     r9d, 0Ch
0x14002081c  mov     rcx, cs:WPP_GLOBAL_Control
0x140020823  mov     dl, 2
0x140020825  mov     [rsp+48h+var_18], ebx
0x140020829  mov     [rsp+48h+var_20], eax
0x14002082d  lea     rax, WPP_52dff22801773d96f6ef5b670d2cd017_Traceguids
0x140020834  mov     [rsp+48h+var_28], rax
0x140020839  mov     rcx, [rcx+40h]
0x14002083d  call    WPP_RECORDER_SF_Ld
0x140020842  test    rdi, rdi
0x140020845  jz      short loc_140020849
0x140020847  mov     [rdi], ebx
0x140020849  mov     eax, ebx
0x14002084b  mov     rbx, [rsp+48h+arg_0]
0x140020850  add     rsp, 40h
0x140020854  pop     rdi
0x140020855  retn
```
