# PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::Evaluate(TimeValue const &,void *,_CBROKERED_EVENT_ID,void * const,ulong)

- ea: `0x18000dca0`
- end: `0x18000de2f`
- name: `?Evaluate@TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@EEAAHAEBVTimeValue@@PEAXU_CBROKERED_EVENT_ID@@QEAXK@Z`
- size: `399`
- prototype: `__int64 __fastcall(__int64, _OWORD *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001260`
- `0x18000dca0`
- `0x18001dca4`
- `0x18001dd08`
- `0x18001fbac`
- `0x180020c30`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::Evaluate(__int64 a1, _OWORD *a2, __int64 a3)
{
  SYSTEMTIME v5; // xmm0
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // edx
  __int128 v12; // xmm0
  SYSTEMTIME SystemTime; // [rsp+30h] [rbp-68h] BYREF
  __int64 v15; // [rsp+40h] [rbp-58h]
  __int64 v16; // [rsp+48h] [rbp-50h]
  int v17; // [rsp+50h] [rbp-48h]
  int v18; // [rsp+54h] [rbp-44h]
  int v19; // [rsp+58h] [rbp-40h]
  SYSTEMTIME v20; // [rsp+60h] [rbp-38h] BYREF
  __int128 v21; // [rsp+70h] [rbp-28h] BYREF

  if ( !*(_DWORD *)(a1 + 184) && *(_QWORD *)(a1 + 432) == a3 )
  {
    v5 = *(SYSTEMTIME *)(a1 + 216);
    v6 = *(_QWORD *)(a1 + 200);
    v15 = *(_QWORD *)(a1 + 232);
    v16 = *(_QWORD *)(a1 + 240);
    v17 = *(_DWORD *)(a1 + 248);
    v7 = *(_DWORD *)(a1 + 252);
    SystemTime = v5;
    v18 = v7;
    v19 = 1;
    TimeValue::AdvanceNs100(&SystemTime, -v6, 0);
    if ( !*(_QWORD *)(a1 + 200) || *(_DWORD *)(a1 + 212) )
    {
      v10 = -10000000;
      if ( *(_DWORD *)(a1 + 208) )
        v10 = -5000000;
      TimeValue::AdvanceNs100(&SystemTime, v10, 0);
    }
    if ( (unsigned int)operator>=((__int64)a2, (__int64)&SystemTime, v8, v9) )
    {
      *(_OWORD *)(a1 + 448) = *a2;
      *(_OWORD *)(a1 + 464) = a2[1];
      v12 = a2[2];
      *(_DWORD *)(a1 + 184) = 1;
      *(_OWORD *)(a1 + 480) = v12;
    }
    else
    {
      v21 = *a2;
      v20 = SystemTime;
      if ( (byte_180030D07 & 1) != 0 )
        McTemplateU0jyy_EventWriteTransfer(a1, v11, *(_QWORD *)(a1 + 176) + 16, (unsigned int)&v21, (__int64)&v20);
    }
  }
  if ( (byte_180030D05 & 1) != 0 )
    McTemplateU0jt_EventWriteTransfer(
      a1,
      PeriodicTriggerEvaluate,
      *(_QWORD *)(a1 + 176) + 16LL,
      *(unsigned int *)(a1 + 184));
  return *(unsigned int *)(a1 + 184);
}

```

## disassembly

```asm
0x18000dca0  mov     [rsp+arg_10], rbx
0x18000dca5  push    rdi
0x18000dca6  sub     rsp, 90h
0x18000dcad  mov     rax, cs:__security_cookie
0x18000dcb4  xor     rax, rsp
0x18000dcb7  mov     [rsp+98h+var_18], rax
0x18000dcbf  cmp     dword ptr [rcx+0B8h], 0
0x18000dcc6  mov     rdi, rdx
0x18000dcc9  mov     rbx, rcx
0x18000dccc  jnz     loc_18000DDE1
0x18000dcd2  cmp     [rcx+1B0h], r8
0x18000dcd9  jnz     loc_18000DDE1
0x18000dcdf  mov     rax, [rcx+0E8h]
0x18000dce6  xor     r8d, r8d; int
0x18000dce9  movups  xmm0, xmmword ptr [rcx+0D8h]
0x18000dcf0  mov     rdx, [rcx+0C8h]
0x18000dcf7  mov     [rsp+98h+var_58], rax
0x18000dcfc  neg     rdx; __int64
0x18000dcff  mov     rax, [rcx+0F0h]
0x18000dd06  mov     [rsp+98h+var_50], rax
0x18000dd0b  mov     eax, [rcx+0F8h]
0x18000dd11  mov     [rsp+98h+var_48], eax
0x18000dd15  mov     eax, [rcx+0FCh]
0x18000dd1b  lea     rcx, [rsp+98h+SystemTime]; lpSystemTime
0x18000dd20  movups  xmmword ptr [rsp+98h+SystemTime.wYear], xmm0
0x18000dd25  mov     [rsp+98h+var_44], eax
0x18000dd29  mov     [rsp+98h+var_40], 1
0x18000dd31  call    ?AdvanceNs100@TimeValue@@QEAAX_JH@Z; TimeValue::AdvanceNs100(__int64,int)
0x18000dd36  cmp     qword ptr [rbx+0C8h], 0
0x18000dd3e  jz      short loc_18000DD49
0x18000dd40  cmp     dword ptr [rbx+0D4h], 0
0x18000dd47  jz      short loc_18000DD6D
0x18000dd49  xor     r8d, r8d; int
0x18000dd4c  lea     rcx, [rsp+98h+SystemTime]; lpSystemTime
0x18000dd51  mov     rdx, 0FFFFFFFFFF676980h
0x18000dd58  cmp     [rbx+0D0h], r8d
0x18000dd5f  jz      short loc_18000DD68
0x18000dd61  mov     rdx, 0FFFFFFFFFFB3B4C0h; __int64
0x18000dd68  call    ?AdvanceNs100@TimeValue@@QEAAX_JH@Z; TimeValue::AdvanceNs100(__int64,int)
0x18000dd6d  lea     rdx, [rsp+98h+SystemTime]
0x18000dd72  mov     rcx, rdi
0x18000dd75  call    ??P@YAHAEBVTimeValue@@0@Z; operator>=(TimeValue const &,TimeValue const &)
0x18000dd7a  movups  xmm0, xmmword ptr [rdi]
0x18000dd7d  test    eax, eax
0x18000dd7f  jz      short loc_18000DDAA
0x18000dd81  movups  xmmword ptr [rbx+1C0h], xmm0
0x18000dd88  movups  xmm1, xmmword ptr [rdi+10h]
0x18000dd8c  movups  xmmword ptr [rbx+1D0h], xmm1
0x18000dd93  movups  xmm0, xmmword ptr [rdi+20h]
0x18000dd97  mov     dword ptr [rbx+0B8h], 1
0x18000dda1  movups  xmmword ptr [rbx+1E0h], xmm0
0x18000dda8  jmp     short loc_18000DDE1
0x18000ddaa  test    cs:byte_180030D07, 1
0x18000ddb1  movups  xmm1, xmmword ptr [rsp+98h+SystemTime.wYear]
0x18000ddb6  movups  [rsp+98h+var_28], xmm0
0x18000ddbb  movups  [rsp+98h+var_38], xmm1
0x18000ddc0  jz      short loc_18000DDE1
0x18000ddc2  mov     r8, [rbx+0B0h]
0x18000ddc9  lea     rax, [rsp+98h+var_38]
0x18000ddce  add     r8, 10h
0x18000ddd2  mov     [rsp+98h+var_78], rax
0x18000ddd7  lea     r9, [rsp+98h+var_28]
0x18000dddc  call    McTemplateU0jyy_EventWriteTransfer
0x18000dde1  test    cs:byte_180030D05, 1
0x18000dde8  jz      short loc_18000DE08
0x18000ddea  mov     r8, [rbx+0B0h]
0x18000ddf1  lea     rdx, PeriodicTriggerEvaluate
0x18000ddf8  mov     r9d, [rbx+0B8h]
0x18000ddff  add     r8, 10h
0x18000de03  call    McTemplateU0jt_EventWriteTransfer
0x18000de08  mov     eax, [rbx+0B8h]
0x18000de0e  mov     rcx, [rsp+98h+var_18]
0x18000de16  xor     rcx, rsp; StackCookie
0x18000de19  call    __security_check_cookie
0x18000de1e  mov     rbx, [rsp+98h+arg_10]
0x18000de26  add     rsp, 90h
0x18000de2d  pop     rdi
0x18000de2e  retn
```
