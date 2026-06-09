# CJobBase::CancelActivePendingCommand(void)

- ea: `0x140063458`
- end: `0x1400635b1`
- name: `?CancelActivePendingCommand@CJobBase@@IEAAHXZ`
- size: `345`
- prototype: `__int64 __fastcall(CJobBase *__hidden this)`
- caller_count: `10`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14005d7f0`
- `0x14005d8c0`
- `0x140060720`
- `0x14007b200`
- `0x14009f1d0`
- `0x1400ac9d0`
- `0x1400acaf0`
- `0x1400bb060`
- `0x1400bf7e0`
- `0x1400c17c0`

## callees

- `0x14001e2c0`
- `0x14001eed0`
- `0x1400623b8`
- `0x140063458`
- `0x1400dfd40`

## pseudocode

```c
__int64 __fastcall CJobBase::CancelActivePendingCommand(CJobBase *this, __int64 a2, int a3)
{
  unsigned int v4; // edi
  __int64 v5; // rcx
  Task *v6; // rcx
  __int64 v8; // [rsp+38h] [rbp-30h]
  int v9; // [rsp+38h] [rbp-30h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      57,
      (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  if ( *((_DWORD *)this + 16) == 2 )
  {
    if ( *((_BYTE *)this + 120) )
    {
      v5 = *((_QWORD *)this + 12);
      v4 = 0;
      if ( v5 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
      }
      else
      {
        v6 = (Task *)*((_QWORD *)this + 13);
        if ( v6 )
          Task::CancelTask(v6, a2, a3);
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          a3,
          59,
          (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
      v4 = -1073741637;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = *((_DWORD *)this + 16);
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        58,
        (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v9);
    }
    v4 = -1073741436;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    LODWORD(v8) = v4;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      *((_DWORD *)this + 4),
      60,
      (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v8);
  }
  return v4;
}

```

## disassembly

```asm
0x140063458  push    rbx
0x14006345a  push    rbp
0x14006345b  push    rsi
0x14006345c  push    rdi
0x14006345d  push    r14
0x14006345f  sub     rsp, 40h
0x140063463  mov     rbx, rcx
0x140063466  lea     rbp, WPP_RECORDER_INITIALIZED
0x14006346d  xor     esi, esi
0x14006346f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140063476  lea     r14, WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids
0x14006347d  jz      short loc_1400634B4
0x14006347f  mov     rcx, cs:WPP_GLOBAL_Control
0x140063486  cmp     byte ptr [rcx+29h], 5
0x14006348a  jnb     short loc_140063492
0x14006348c  cmp     [rcx+48h], si
0x140063490  jz      short loc_1400634B4
0x140063492  mov     eax, [rbx+10h]
0x140063495  mov     r9d, 39h ; '9'
0x14006349b  mov     rcx, [rcx+40h]
0x14006349f  mov     dl, 5
0x1400634a1  mov     [rsp+68h+var_38], eax
0x1400634a5  mov     [rsp+68h+var_40], rbx
0x1400634aa  mov     [rsp+68h+var_48], r14
0x1400634af  call    WPP_RECORDER_SF_qD
0x1400634b4  mov     eax, [rbx+40h]
0x1400634b7  cmp     eax, 2
0x1400634ba  jz      short loc_1400634F9
0x1400634bc  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400634c3  jz      short loc_1400634F2
0x1400634c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400634cc  mov     r9d, 3Ah ; ':'
0x1400634d2  mov     dword ptr [rsp+68h+var_30], eax
0x1400634d6  mov     dl, 2
0x1400634d8  mov     eax, [rbx+10h]
0x1400634db  mov     [rsp+68h+var_38], eax
0x1400634df  mov     rcx, [rcx+40h]
0x1400634e3  mov     [rsp+68h+var_40], rbx
0x1400634e8  mov     [rsp+68h+var_48], r14
0x1400634ed  call    WPP_RECORDER_SF_qDD
0x1400634f2  mov     edi, 0C0000184h
0x1400634f7  jmp     short loc_14006355F
0x1400634f9  cmp     [rbx+78h], sil
0x1400634fd  jnz     short loc_140063538
0x1400634ff  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140063506  jz      short loc_140063531
0x140063508  mov     rcx, cs:WPP_GLOBAL_Control
0x14006350f  mov     r9d, 3Bh ; ';'
0x140063515  mov     eax, [rbx+10h]
0x140063518  mov     dl, 2
0x14006351a  mov     [rsp+68h+var_38], eax
0x14006351e  mov     [rsp+68h+var_40], rbx
0x140063523  mov     rcx, [rcx+40h]
0x140063527  mov     [rsp+68h+var_48], r14
0x14006352c  call    WPP_RECORDER_SF_qD
0x140063531  mov     edi, 0C00000BBh
0x140063536  jmp     short loc_14006355F
0x140063538  mov     rcx, [rbx+60h]
0x14006353c  mov     edi, esi
0x14006353e  test    rcx, rcx
0x140063541  jz      short loc_140063551
0x140063543  mov     rax, [rcx]
0x140063546  mov     rax, [rax+18h]
0x14006354a  call    _guard_dispatch_icall
0x14006354f  jmp     short loc_14006355F
0x140063551  mov     rcx, [rbx+68h]; this
0x140063555  test    rcx, rcx
0x140063558  jz      short loc_14006355F
0x14006355a  call    ?CancelTask@Task@@QEAAXXZ; Task::CancelTask(void)
0x14006355f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140063566  jz      short loc_1400635A3
0x140063568  mov     rcx, cs:WPP_GLOBAL_Control
0x14006356f  cmp     byte ptr [rcx+29h], 5
0x140063573  jnb     short loc_14006357B
0x140063575  cmp     [rcx+48h], si
0x140063579  jz      short loc_1400635A3
0x14006357b  mov     r8d, [rbx+10h]
0x14006357f  mov     r9d, 3Ch ; '<'
0x140063585  mov     rcx, [rcx+40h]
0x140063589  mov     dl, 5
0x14006358b  mov     dword ptr [rsp+68h+var_30], edi
0x14006358f  mov     [rsp+68h+var_38], r8d
0x140063594  mov     [rsp+68h+var_40], rbx
0x140063599  mov     [rsp+68h+var_48], r14
0x14006359e  call    WPP_RECORDER_SF_qDD
0x1400635a3  mov     eax, edi
0x1400635a5  add     rsp, 40h
0x1400635a9  pop     r14
0x1400635ab  pop     rdi
0x1400635ac  pop     rsi
0x1400635ad  pop     rbp
0x1400635ae  pop     rbx
0x1400635af  retn
```
