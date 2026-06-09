# CJobBase::QueueDeviceCommand(DeviceCommand *)

- ea: `0x140063a48`
- end: `0x140063bdd`
- name: `?QueueDeviceCommand@CJobBase@@IEAAHPEAVDeviceCommand@@@Z`
- size: `405`
- prototype: `__int64 __fastcall(CJobBase *__hidden this, struct DeviceCommand *)`
- caller_count: `20`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400123c0`
- `0x140012610`
- `0x14004f700`
- `0x140050318`
- `0x14006b040`
- `0x14006de00`
- `0x14006df5c`
- `0x140071820`
- `0x140071c10`
- `0x140075fb0`
- `0x14007b9a0`
- `0x14007f07c`
- `0x1400871a0`
- `0x140091710`
- `0x1400b1d28`
- `0x1400b5d00`
- `0x1400bad7c`
- `0x1400bbed4`
- `0x1400be3c0`
- `0x1400c1f50`

## callees

- `0x14001e2c0`
- `0x14001eed0`
- `0x140022db4`
- `0x140063a48`

## pseudocode

```c
__int64 __fastcall CJobBase::QueueDeviceCommand(CJobBase *this, struct DeviceCommand *a2, int a3)
{
  struct DeviceCommand *v3; // rsi
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
      49,
      (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  if ( v3 )
  {
    if ( *((_DWORD *)this + 16) == 1 )
    {
      started = DeviceCommandScheduler::StartCommand(*((DeviceCommandScheduler **)this + 9), v3, this, this);
      if ( started )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return started;
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          a3,
          52,
          (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
      else
      {
        *((_DWORD *)this + 16) = 2;
        *((_QWORD *)this + 14) = v3;
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
          51,
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
        50,
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
      53,
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
0x140063a48  push    rbx
0x140063a4a  push    rbp
0x140063a4b  push    rsi
0x140063a4c  push    rdi
0x140063a4d  push    r14
0x140063a4f  push    r15
0x140063a51  sub     rsp, 48h
0x140063a55  mov     rsi, rdx
0x140063a58  mov     rbx, rcx
0x140063a5b  lea     rbp, WPP_RECORDER_INITIALIZED
0x140063a62  xor     r14d, r14d
0x140063a65  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140063a6c  lea     r15, WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids
0x140063a73  jz      short loc_140063AAB
0x140063a75  mov     rcx, cs:WPP_GLOBAL_Control
0x140063a7c  cmp     byte ptr [rcx+29h], 5
0x140063a80  jnb     short loc_140063A89
0x140063a82  cmp     [rcx+48h], r14w
0x140063a87  jz      short loc_140063AAB
0x140063a89  mov     eax, [rbx+10h]
0x140063a8c  mov     r9d, 31h ; '1'
0x140063a92  mov     rcx, [rcx+40h]
0x140063a96  mov     dl, 5
0x140063a98  mov     [rsp+78h+var_48], eax
0x140063a9c  mov     [rsp+78h+var_50], rbx
0x140063aa1  mov     [rsp+78h+var_58], r15
0x140063aa6  call    WPP_RECORDER_SF_qD
0x140063aab  test    rsi, rsi
0x140063aae  jnz     short loc_140063AEA
0x140063ab0  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140063ab7  jz      short loc_140063AE0
0x140063ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x140063ac0  lea     r9d, [rsi+32h]
0x140063ac4  mov     eax, [rbx+10h]
0x140063ac7  mov     dl, 2
0x140063ac9  mov     [rsp+78h+var_48], eax
0x140063acd  mov     [rsp+78h+var_50], rbx
0x140063ad2  mov     rcx, [rcx+40h]
0x140063ad6  mov     [rsp+78h+var_58], r15
0x140063adb  call    WPP_RECORDER_SF_qD
0x140063ae0  mov     edi, 0C000000Dh
0x140063ae5  jmp     loc_140063B8A
0x140063aea  mov     eax, [rbx+40h]
0x140063aed  cmp     eax, 1
0x140063af0  jz      short loc_140063B2F
0x140063af2  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140063af9  jz      short loc_140063B28
0x140063afb  mov     rcx, cs:WPP_GLOBAL_Control
0x140063b02  mov     r9d, 33h ; '3'
0x140063b08  mov     dword ptr [rsp+78h+var_40], eax
0x140063b0c  mov     dl, 2
0x140063b0e  mov     eax, [rbx+10h]
0x140063b11  mov     [rsp+78h+var_48], eax
0x140063b15  mov     rcx, [rcx+40h]
0x140063b19  mov     [rsp+78h+var_50], rbx
0x140063b1e  mov     [rsp+78h+var_58], r15
0x140063b23  call    WPP_RECORDER_SF_qDD
0x140063b28  mov     edi, 0C0000184h
0x140063b2d  jmp     short loc_140063B8A
0x140063b2f  mov     rcx, [rbx+48h]; this
0x140063b33  mov     r9, rbx; struct CJobBase *
0x140063b36  mov     r8, rbx; struct IOperationCompletionCallback *
0x140063b39  mov     rdx, rsi; struct DeviceCommand *
0x140063b3c  call    ?StartCommand@DeviceCommandScheduler@@QEAAHPEAVDeviceCommand@@PEAVIOperationCompletionCallback@@PEAVCJobBase@@@Z; DeviceCommandScheduler::StartCommand(DeviceCommand *,IOperationCompletionCallback *,CJobBase *)
0x140063b41  mov     edi, eax
0x140063b43  test    eax, eax
0x140063b45  jz      short loc_140063B7B
0x140063b47  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140063b4e  jz      short loc_140063BCD
0x140063b50  mov     ecx, [rbx+10h]
0x140063b53  mov     r9d, 34h ; '4'
0x140063b59  mov     [rsp+78h+var_48], ecx
0x140063b5d  mov     dl, 2
0x140063b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140063b66  mov     [rsp+78h+var_50], rbx
0x140063b6b  mov     [rsp+78h+var_58], r15
0x140063b70  mov     rcx, [rcx+40h]
0x140063b74  call    WPP_RECORDER_SF_qD
0x140063b79  jmp     short loc_140063B8A
0x140063b7b  mov     dword ptr [rbx+40h], 2
0x140063b82  mov     [rbx+70h], rsi
0x140063b86  mov     byte ptr [rbx+78h], 1
0x140063b8a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140063b91  jz      short loc_140063BCD
0x140063b93  mov     rcx, cs:WPP_GLOBAL_Control
0x140063b9a  cmp     byte ptr [rcx+29h], 5
0x140063b9e  jnb     short loc_140063BA7
0x140063ba0  cmp     [rcx+48h], r14w
0x140063ba5  jz      short loc_140063BCD
0x140063ba7  mov     eax, [rbx+10h]
0x140063baa  mov     r9d, 35h ; '5'
0x140063bb0  mov     rcx, [rcx+40h]
0x140063bb4  mov     dl, 5
0x140063bb6  mov     dword ptr [rsp+78h+var_40], edi
0x140063bba  mov     [rsp+78h+var_48], eax
0x140063bbe  mov     [rsp+78h+var_50], rbx
0x140063bc3  mov     [rsp+78h+var_58], r15
0x140063bc8  call    WPP_RECORDER_SF_qDD
0x140063bcd  mov     eax, edi
0x140063bcf  add     rsp, 48h
0x140063bd3  pop     r15
0x140063bd5  pop     r14
0x140063bd7  pop     rdi
0x140063bd8  pop     rsi
0x140063bd9  pop     rbp
0x140063bda  pop     rbx
0x140063bdb  retn
```
