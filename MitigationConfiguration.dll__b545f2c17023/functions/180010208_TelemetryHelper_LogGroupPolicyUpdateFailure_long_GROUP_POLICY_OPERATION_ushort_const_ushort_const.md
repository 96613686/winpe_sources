# TelemetryHelper::LogGroupPolicyUpdateFailure(long,_GROUP_POLICY_OPERATION,ushort const *,ushort const *)

- ea: `0x180010208`
- end: `0x180010382`
- name: `?LogGroupPolicyUpdateFailure@TelemetryHelper@@CAXJW4_GROUP_POLICY_OPERATION@@PEBG1@Z`
- size: `378`
- prototype: `__int64 __fastcall(int, int, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000467c`

## callees

- `0x18000113c`
- `0x180001c00`
- `0x180010208`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x180010249`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180010249`

## pseudocode

```c
__int64 __fastcall TelemetryHelper::LogGroupPolicyUpdateFailure(int a1, int a2, __int64 *a3, __int64 *a4)
{
  __int64 v5; // rsi
  __int64 result; // rax
  __int64 v9; // rax
  __int64 *v10; // rdx
  int v11; // r8d
  __int64 v12; // rcx
  int v13; // ecx
  __int64 v14; // rcx
  int v15; // ecx
  int v16; // [rsp+30h] [rbp-49h] BYREF
  int *v17; // [rsp+60h] [rbp-19h]
  __int64 v18; // [rsp+68h] [rbp-11h]
  __int64 *v19; // [rsp+70h] [rbp-9h]
  int v20; // [rsp+78h] [rbp-1h]
  int v21; // [rsp+7Ch] [rbp+3h]
  __int64 *v22; // [rsp+80h] [rbp+7h]
  int v23; // [rsp+88h] [rbp+Fh]
  int v24; // [rsp+8Ch] [rbp+13h]
  __int64 *v25; // [rsp+90h] [rbp+17h]
  int v26; // [rsp+98h] [rbp+1Fh]
  int v27; // [rsp+9Ch] [rbp+23h]

  v5 = a2;
  RtlRunOnceExecuteOnce(&ExploitProtectionTelemetryInitRunOnce, ExploitProtectionTelemetryInitOnce, 0, 0);
  result = (unsigned int)dword_18001C000;
  if ( (unsigned int)dword_18001C000 > 5 )
  {
    result = qword_18001C010;
    if ( (qword_18001C010 & 0x400000000000LL) != 0 )
    {
      result = qword_18001C018 & 0x400000000000LL;
      if ( (qword_18001C018 & 0x400000000000LL) == qword_18001C018 )
      {
        v9 = -1;
        v16 = a1;
        v10 = (__int64 *)(&TelemetryHelper::s_groupPolicyOperations)[v5];
        v11 = 2;
        if ( a4 )
        {
          v12 = -1;
          do
            ++v12;
          while ( *((_WORD *)a4 + v12) );
          v13 = 2 * v12 + 2;
        }
        else
        {
          a4 = &qword_180018390;
          v13 = 2;
        }
        v25 = a4;
        v26 = v13;
        v27 = 0;
        if ( a3 )
        {
          v14 = -1;
          do
            ++v14;
          while ( *((_WORD *)a3 + v14) );
          v15 = 2 * v14 + 2;
        }
        else
        {
          a3 = &qword_180018390;
          v15 = 2;
        }
        v22 = a3;
        v23 = v15;
        v24 = 0;
        if ( v10 )
        {
          do
            ++v9;
          while ( *((_WORD *)v10 + v9) );
          v11 = 2 * v9 + 2;
        }
        else
        {
          v10 = &qword_180018390;
        }
        v19 = v10;
        v17 = &v16;
        v20 = v11;
        v21 = 0;
        v18 = 4;
        return tlgWriteTransfer_EventWriteTransfer(&dword_18001C000, byte_180018B19, 0);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010208  push    rbp
0x18001020a  push    rbx
0x18001020b  push    rsi
0x18001020c  push    rdi
0x18001020d  push    r14
0x18001020f  lea     rbp, [rsp-37h]
0x180010214  sub     rsp, 0B0h
0x18001021b  mov     rax, cs:__security_cookie
0x180010222  xor     rax, rsp
0x180010225  mov     [rbp+57h+var_30], rax
0x180010229  mov     rbx, r9
0x18001022c  movsxd  rsi, edx
0x18001022f  mov     rdi, r8
0x180010232  lea     rdx, ?ExploitProtectionTelemetryInitOnce@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; ExploitProtectionTelemetryInitOnce(_RTL_RUN_ONCE *,void *,void * *)
0x180010239  mov     r14d, ecx
0x18001023c  xor     r9d, r9d
0x18001023f  xor     r8d, r8d
0x180010242  lea     rcx, ?ExploitProtectionTelemetryInitRunOnce@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE ExploitProtectionTelemetryInitRunOnce
0x180010249  call    cs:__imp_RtlRunOnceExecuteOnce
0x18001024f  mov     eax, cs:dword_18001C000
0x180010255  cmp     eax, 5
0x180010258  jbe     loc_180010368
0x18001025e  mov     r9, cs:qword_18001C018
0x180010265  mov     rcx, 400000000000h
0x18001026f  mov     rax, cs:qword_18001C010
0x180010276  test    rcx, rax
0x180010279  jz      loc_180010368
0x18001027f  mov     rax, r9
0x180010282  and     rax, rcx
0x180010285  cmp     rax, r9
0x180010288  jnz     loc_180010368
0x18001028e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010292  mov     [rbp+57h+var_A0], r14d
0x180010296  xor     r9d, r9d
0x180010299  lea     rdx, ?s_groupPolicyOperations@TelemetryHelper@@0PAPEBGA; ushort const * near * TelemetryHelper::s_groupPolicyOperations
0x1800102a0  mov     rdx, [rdx+rsi*8]
0x1800102a4  lea     r10, qword_180018390
0x1800102ab  mov     r8d, 2
0x1800102b1  test    rbx, rbx
0x1800102b4  jz      short loc_1800102CC
0x1800102b6  mov     rcx, rax
0x1800102b9  inc     rcx
0x1800102bc  cmp     [rbx+rcx*2], r9w
0x1800102c1  jnz     short loc_1800102B9
0x1800102c3  lea     ecx, ds:2[rcx*2]
0x1800102ca  jmp     short loc_1800102D2
0x1800102cc  mov     rbx, r10
0x1800102cf  mov     ecx, r8d
0x1800102d2  mov     [rbp+57h+var_40], rbx
0x1800102d6  mov     [rbp+57h+var_38], ecx
0x1800102d9  mov     [rbp+57h+var_34], r9d
0x1800102dd  test    rdi, rdi
0x1800102e0  jz      short loc_1800102F8
0x1800102e2  mov     rcx, rax
0x1800102e5  inc     rcx
0x1800102e8  cmp     [rdi+rcx*2], r9w
0x1800102ed  jnz     short loc_1800102E5
0x1800102ef  lea     ecx, ds:2[rcx*2]
0x1800102f6  jmp     short loc_1800102FE
0x1800102f8  mov     rdi, r10
0x1800102fb  mov     ecx, r8d
0x1800102fe  mov     [rbp+57h+var_50], rdi
0x180010302  mov     [rbp+57h+var_48], ecx
0x180010305  mov     [rbp+57h+var_44], r9d
0x180010309  test    rdx, rdx
0x18001030c  jz      short loc_180010322
0x18001030e  inc     rax
0x180010311  cmp     [rdx+rax*2], r9w
0x180010316  jnz     short loc_18001030E
0x180010318  lea     r8d, ds:2[rax*2]
0x180010320  jmp     short loc_180010325
0x180010322  mov     rdx, r10
0x180010325  lea     rax, [rbp+57h+var_A0]
0x180010329  mov     [rbp+57h+var_60], rdx
0x18001032d  mov     [rbp+57h+var_70], rax
0x180010331  lea     rdx, byte_180018B19
0x180010338  lea     rax, [rbp+57h+var_90]
0x18001033c  mov     [rbp+57h+var_58], r8d
0x180010340  mov     [rsp+0D0h+var_A8], rax
0x180010345  lea     rcx, dword_18001C000
0x18001034c  xor     r8d, r8d
0x18001034f  mov     [rsp+0D0h+var_B0], 6
0x180010357  mov     [rbp+57h+var_54], r9d
0x18001035b  mov     [rbp+57h+var_68], 4
0x180010363  call    _tlgWriteTransfer_EventWriteTransfer
0x180010368  mov     rcx, [rbp+57h+var_30]
0x18001036c  xor     rcx, rsp; StackCookie
0x18001036f  call    __security_check_cookie
0x180010374  add     rsp, 0B0h
0x18001037b  pop     r14
0x18001037d  pop     rdi
0x18001037e  pop     rsi
0x18001037f  pop     rbx
0x180010380  pop     rbp
0x180010381  retn
```
