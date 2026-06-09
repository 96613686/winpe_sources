# CAudioPump::EventHandlerBufferComplete(unsigned __int64 *)

- ea: `0x140040050`
- end: `0x140040255`
- name: `?EventHandlerBufferComplete@CAudioPump@@AEAAXPEA_K@Z`
- size: `517`
- prototype: `void __fastcall(CAudioPump *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140035d80`

## callees

- `0x140005ac0`
- `0x1400122f0`
- `0x140040050`
- `0x14005d0e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x140040150`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x140040150`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14004015b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14004015b`
- `ntdll!EtwEventWriteTransfer` at `0x140040234`
- `ntdll!EtwEventWriteTransfer` at `0x140040234`

## pseudocode

```c
void __fastcall CAudioPump::EventHandlerBufferComplete(CAudioPump *this, unsigned __int64 *a2)
{
  _QWORD *v3; // rdx
  __int64 (__fastcall *v4)(CAudioPump *); // rax
  void *v5; // rdi
  bool v6; // zf
  __int64 v7; // rcx
  _DWORD v8[2]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v9; // [rsp+40h] [rbp-38h]
  unsigned __int16 *v10; // [rsp+48h] [rbp-30h] BYREF
  int v11; // [rsp+50h] [rbp-28h]
  int v12; // [rsp+54h] [rbp-24h]
  __int16 *v13; // [rsp+58h] [rbp-20h]
  int v14; // [rsp+60h] [rbp-18h]
  int v15; // [rsp+64h] [rbp-14h]

  if ( *((_QWORD *)this + 39) )
  {
    if ( *((_BYTE *)this + 4752) )
    {
      ++*((_QWORD *)this + 593);
      *((_BYTE *)this + 4752) = 0;
    }
    *((_QWORD *)this + 47) = *((_QWORD *)this + 583);
    v3 = (_QWORD *)((char *)this + 408);
    v4 = (__int64 (__fastcall *)(CAudioPump *))*((_QWORD *)this + 27);
    if ( CAudioPump::OutputPumpWorkRoutine != v4 || !*v3 )
      *((_BYTE *)this + 272) = 0;
    if ( CAudioPump::OutputPumpWorkRoutine == v4 )
    {
      v3 = (_QWORD *)((char *)this + 408);
      if ( *((_QWORD *)this + 51) )
        *((_BYTE *)this + 4681) = 1;
    }
    if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 84, 0, 0) )
    {
      if ( CAudioPump::OutputPumpWorkRoutine == *((__int64 (__fastcall **)(CAudioPump *))this + 27) )
      {
        if ( *v3 )
        {
          *((_BYTE *)this + 272) = 0;
          *((_BYTE *)this + 4681) = 1;
        }
      }
      CAudioPump::SetTimer(
        this,
        *((void **)this + 37),
        (unsigned int)(int)((double)(int)*((_QWORD *)this + 13) * 1.5),
        0);
    }
    else
    {
      v5 = (void *)*((_QWORD *)this + 37);
      if ( v5 )
      {
        CancelWaitableTimer(*((HANDLE *)this + 37));
        WaitForSingleObject(v5, 0);
      }
      CAudioPump::CancelDeadline(this);
      v6 = *((_BYTE *)this + 4680) == 0;
      *((_BYTE *)this + 4681) = 0;
      if ( !v6 && CAudioPump::OutputPumpWorkRoutine == *((__int64 (__fastcall **)(CAudioPump *))this + 27) )
      {
        v7 = *((_QWORD *)this + 596);
        *((_BYTE *)this + 4682) = 1;
        if ( *(_DWORD *)v7 > 5u )
        {
          v8[1] = 5;
          v10 = *(unsigned __int16 **)(v7 + 8);
          v8[0] = 184549376;
          v9 = 0;
          v11 = *v10;
          v13 = &word_1400D20FE;
          v12 = 2;
          v14 = 43;
          v15 = 1;
          EtwEventWriteTransfer(*(_QWORD *)(v7 + 32), v8, 0, 0, 2, &v10);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140040050  push    rbx
0x140040052  sub     rsp, 70h
0x140040056  mov     rax, cs:__security_cookie
0x14004005d  xor     rax, rsp
0x140040060  mov     [rsp+78h+var_10], rax
0x140040065  cmp     qword ptr [rcx+138h], 0
0x14004006d  mov     rbx, rcx
0x140040070  jz      loc_140040242
0x140040076  cmp     byte ptr [rcx+1290h], 0
0x14004007d  mov     [rsp+78h+arg_8], rsi
0x140040085  jz      short loc_140040095
0x140040087  inc     qword ptr [rcx+1288h]
0x14004008e  mov     byte ptr [rcx+1290h], 0
0x140040095  mov     rax, [rcx+1238h]
0x14004009c  lea     rsi, ?OutputPumpWorkRoutine@CAudioPump@@CAKPEAX@Z; CAudioPump::OutputPumpWorkRoutine(void *)
0x1400400a3  mov     [rcx+178h], rax
0x1400400aa  lea     rdx, [rcx+198h]
0x1400400b1  mov     rax, [rcx+0D8h]
0x1400400b8  cmp     rsi, rax
0x1400400bb  jnz     short loc_1400400C3
0x1400400bd  cmp     qword ptr [rdx], 0
0x1400400c1  jnz     short loc_1400400CA
0x1400400c3  mov     byte ptr [rcx+110h], 0
0x1400400ca  cmp     rsi, rax
0x1400400cd  jnz     short loc_1400400E3
0x1400400cf  lea     rdx, [rcx+198h]
0x1400400d6  cmp     qword ptr [rdx], 0
0x1400400da  jz      short loc_1400400E3
0x1400400dc  mov     byte ptr [rcx+1249h], 1
0x1400400e3  xor     ecx, ecx
0x1400400e5  xor     eax, eax
0x1400400e7  lock cmpxchg [rbx+150h], ecx
0x1400400ef  jz      short loc_140040139
0x1400400f1  cmp     rsi, [rbx+0D8h]
0x1400400f8  jnz     short loc_14004010C
0x1400400fa  cmp     [rdx], rcx
0x1400400fd  jz      short loc_14004010C
0x1400400ff  mov     [rbx+110h], cl
0x140040105  mov     byte ptr [rbx+1249h], 1
0x14004010c  mov     rdx, [rbx+128h]; void *
0x140040113  xorps   xmm0, xmm0
0x140040116  cvtsi2sd xmm0, qword ptr [rbx+68h]
0x14004011c  xor     r9d, r9d; bool
0x14004011f  mov     rcx, rbx; this
0x140040122  mulsd   xmm0, cs:__real@3ff8000000000000
0x14004012a  cvttsd2si r8, xmm0; __int64
0x14004012f  call    ?SetTimer@CAudioPump@@AEAAJPEAX_J_N@Z; CAudioPump::SetTimer(void *,__int64,bool)
0x140040134  jmp     loc_14004023A
0x140040139  mov     [rsp+78h+arg_10], rdi
0x140040141  mov     rdi, [rbx+128h]
0x140040148  test    rdi, rdi
0x14004014b  jz      short loc_140040161
0x14004014d  mov     rcx, rdi; hTimer
0x140040150  call    cs:__imp_CancelWaitableTimer
0x140040156  xor     edx, edx; dwMilliseconds
0x140040158  mov     rcx, rdi; hHandle
0x14004015b  call    cs:__imp_WaitForSingleObject
0x140040161  mov     rcx, rbx; this
0x140040164  call    ?CancelDeadline@CAudioPump@@AEAAXXZ; CAudioPump::CancelDeadline(void)
0x140040169  cmp     byte ptr [rbx+1248h], 0
0x140040170  mov     rdi, [rsp+78h+arg_10]
0x140040178  mov     byte ptr [rbx+1249h], 0
0x14004017f  jz      loc_14004023A
0x140040185  cmp     rsi, [rbx+0D8h]
0x14004018c  jnz     loc_14004023A
0x140040192  mov     rcx, [rbx+12A0h]
0x140040199  mov     byte ptr [rbx+124Ah], 1
0x1400401a0  mov     eax, [rcx]
0x1400401a2  cmp     eax, 5
0x1400401a5  jbe     loc_14004023A
0x1400401ab  movzx   eax, cs:word_1400D20F4
0x1400401b2  lea     rdx, _TraceLoggingMetadata
0x1400401b9  mov     [rsp+78h+var_3C], eax
0x1400401bd  xor     r9d, r9d
0x1400401c0  mov     rax, [rcx+8]
0x1400401c4  xor     r8d, r8d
0x1400401c7  mov     [rsp+78h+var_30], rax
0x1400401cc  mov     [rsp+78h+var_40], 0B000000h
0x1400401d4  mov     [rsp+78h+var_38], 0
0x1400401dd  movzx   eax, word ptr [rax]
0x1400401e0  mov     [rsp+78h+var_28], eax
0x1400401e4  lea     rax, word_1400D20FE
0x1400401eb  mov     [rsp+78h+var_20], rax
0x1400401f0  lea     rax, _TraceLoggingMetadataEnd
0x1400401f7  sub     eax, edx
0x1400401f9  mov     [rsp+78h+var_24], 2
0x140040201  mov     [rsp+78h+var_18], 2Bh ; '+'
0x140040209  lea     rdx, [rsp+78h+var_40]
0x14004020e  mov     [rsp+78h+var_14], 1
0x140040216  mov     [rsp+78h+var_48], eax
0x14004021a  mov     eax, [rsp+78h+var_48]
0x14004021e  mov     rcx, [rcx+20h]
0x140040222  lea     rax, [rsp+78h+var_30]
0x140040227  mov     [rsp+78h+var_50], rax
0x14004022c  mov     [rsp+78h+var_58], 2
0x140040234  call    cs:__imp_EtwEventWriteTransfer
0x14004023a  mov     rsi, [rsp+78h+arg_8]
0x140040242  mov     rcx, [rsp+78h+var_10]
0x140040247  xor     rcx, rsp; StackCookie
0x14004024a  call    __security_check_cookie
0x14004024f  add     rsp, 70h
0x140040253  pop     rbx
0x140040254  retn
```
