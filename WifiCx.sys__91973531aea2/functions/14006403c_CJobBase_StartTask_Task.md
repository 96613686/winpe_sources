# CJobBase::StartTask(Task *)

- ea: `0x14006403c`
- end: `0x1400641cd`
- name: `?StartTask@CJobBase@@IEAAHPEAVTask@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(CJobBase *__hidden this, struct Task *)`
- caller_count: `12`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x140063764`
- `0x14006b410`
- `0x140071c10`
- `0x14007bbd0`
- `0x14007f3bc`
- `0x140081588`
- `0x14009292c`
- `0x1400ad300`
- `0x1400b511c`
- `0x1400ba93c`
- `0x1400bad7c`
- `0x1400c5aa0`

## callees

- `0x14001ccd0`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14006403c`

## pseudocode

```c
__int64 __fastcall CJobBase::StartTask(CJobBase *this, struct Task *a2, int a3)
{
  Task *v3; // rsi
  unsigned int started; // edi
  __int64 v7; // [rsp+38h] [rbp-40h]

  v3 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      40,
      (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  if ( v3 )
  {
    if ( *((_DWORD *)this + 16) == 1 )
    {
      started = Task::StartTask(v3, this, this);
      if ( started )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return started;
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          a3,
          43,
          (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
      else
      {
        *((_DWORD *)this + 16) = 2;
        *((_QWORD *)this + 13) = v3;
        *((_BYTE *)this + 120) = 1;
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          a3,
          42,
          (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          *((_DWORD *)this + 16));
      }
      started = -1073741436;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        a3,
        41,
        (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    started = -1073741811;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    LODWORD(v7) = started;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      44,
      (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v7);
  }
  return started;
}

```

## disassembly

```asm
0x14006403c  push    rbx
0x14006403e  push    rbp
0x14006403f  push    rsi
0x140064040  push    rdi
0x140064041  push    r14
0x140064043  push    r15
0x140064045  sub     rsp, 48h
0x140064049  mov     rsi, rdx
0x14006404c  mov     rbx, rcx
0x14006404f  lea     rbp, WPP_RECORDER_INITIALIZED
0x140064056  xor     r14d, r14d
0x140064059  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140064060  lea     r15, WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids
0x140064067  jz      short loc_14006409F
0x140064069  mov     rcx, cs:WPP_GLOBAL_Control
0x140064070  cmp     byte ptr [rcx+29h], 5
0x140064074  jnb     short loc_14006407D
0x140064076  cmp     [rcx+48h], r14w
0x14006407b  jz      short loc_14006409F
0x14006407d  mov     eax, [rbx+10h]
0x140064080  mov     r9d, 28h ; '('
0x140064086  mov     rcx, [rcx+40h]
0x14006408a  mov     dl, 5
0x14006408c  mov     [rsp+78h+var_48], eax
0x140064090  mov     [rsp+78h+var_50], rbx
0x140064095  mov     [rsp+78h+var_58], r15
0x14006409a  call    WPP_RECORDER_SF_qD
0x14006409f  test    rsi, rsi
0x1400640a2  jnz     short loc_1400640DE
0x1400640a4  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400640ab  jz      short loc_1400640D4
0x1400640ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400640b4  lea     r9d, [rsi+29h]
0x1400640b8  mov     eax, [rbx+10h]
0x1400640bb  mov     dl, 2
0x1400640bd  mov     [rsp+78h+var_48], eax
0x1400640c1  mov     [rsp+78h+var_50], rbx
0x1400640c6  mov     rcx, [rcx+40h]
0x1400640ca  mov     [rsp+78h+var_58], r15
0x1400640cf  call    WPP_RECORDER_SF_qD
0x1400640d4  mov     edi, 0C000000Dh
0x1400640d9  jmp     loc_14006417A
0x1400640de  mov     eax, [rbx+40h]
0x1400640e1  cmp     eax, 1
0x1400640e4  jz      short loc_140064123
0x1400640e6  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400640ed  jz      short loc_14006411C
0x1400640ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400640f6  mov     r9d, 2Ah ; '*'
0x1400640fc  mov     dword ptr [rsp+78h+var_40], eax
0x140064100  mov     dl, 2
0x140064102  mov     eax, [rbx+10h]
0x140064105  mov     [rsp+78h+var_48], eax
0x140064109  mov     rcx, [rcx+40h]
0x14006410d  mov     [rsp+78h+var_50], rbx
0x140064112  mov     [rsp+78h+var_58], r15
0x140064117  call    WPP_RECORDER_SF_qDD
0x14006411c  mov     edi, 0C0000184h
0x140064121  jmp     short loc_14006417A
0x140064123  mov     r8, rbx; struct CJobBase *
0x140064126  mov     rdx, rbx; struct IOperationCompletionCallback *
0x140064129  mov     rcx, rsi; this
0x14006412c  call    ?StartTask@Task@@QEAAHPEAVIOperationCompletionCallback@@PEAVCJobBase@@@Z; Task::StartTask(IOperationCompletionCallback *,CJobBase *)
0x140064131  mov     edi, eax
0x140064133  test    eax, eax
0x140064135  jz      short loc_14006416B
0x140064137  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14006413e  jz      short loc_1400641BD
0x140064140  mov     ecx, [rbx+10h]
0x140064143  mov     r9d, 2Bh ; '+'
0x140064149  mov     [rsp+78h+var_48], ecx
0x14006414d  mov     dl, 2
0x14006414f  mov     rcx, cs:WPP_GLOBAL_Control
0x140064156  mov     [rsp+78h+var_50], rbx
0x14006415b  mov     [rsp+78h+var_58], r15
0x140064160  mov     rcx, [rcx+40h]
0x140064164  call    WPP_RECORDER_SF_qD
0x140064169  jmp     short loc_14006417A
0x14006416b  mov     dword ptr [rbx+40h], 2
0x140064172  mov     [rbx+68h], rsi
0x140064176  mov     byte ptr [rbx+78h], 1
0x14006417a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140064181  jz      short loc_1400641BD
0x140064183  mov     rcx, cs:WPP_GLOBAL_Control
0x14006418a  cmp     byte ptr [rcx+29h], 5
0x14006418e  jnb     short loc_140064197
0x140064190  cmp     [rcx+48h], r14w
0x140064195  jz      short loc_1400641BD
0x140064197  mov     eax, [rbx+10h]
0x14006419a  mov     r9d, 2Ch ; ','
0x1400641a0  mov     rcx, [rcx+40h]
0x1400641a4  mov     dl, 5
0x1400641a6  mov     dword ptr [rsp+78h+var_40], edi
0x1400641aa  mov     [rsp+78h+var_48], eax
0x1400641ae  mov     [rsp+78h+var_50], rbx
0x1400641b3  mov     [rsp+78h+var_58], r15
0x1400641b8  call    WPP_RECORDER_SF_qDD
0x1400641bd  mov     eax, edi
0x1400641bf  add     rsp, 48h
0x1400641c3  pop     r15
0x1400641c5  pop     r14
0x1400641c7  pop     rdi
0x1400641c8  pop     rsi
0x1400641c9  pop     rbp
0x1400641ca  pop     rbx
0x1400641cb  retn
```
