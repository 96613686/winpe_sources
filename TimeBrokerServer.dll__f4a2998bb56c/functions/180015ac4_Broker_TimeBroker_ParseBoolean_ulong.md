# Broker::TimeBroker::ParseBoolean(ulong)

- ea: `0x180015ac4`
- end: `0x180015b0a`
- name: `?ParseBoolean@TimeBroker@Broker@@CAEK@Z`
- size: `70`
- prototype: `unsigned __int8 __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d388`

## callees

- `0x180013978`
- `0x180015ac4`

## pseudocode

```c
unsigned __int8 __fastcall Broker::TimeBroker::ParseBoolean(int a1)
{
  void **pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  __int128 v3; // [rsp+28h] [rbp-20h]
  int v4; // [rsp+38h] [rbp-10h]

  if ( !a1 )
    return 0;
  if ( a1 != 1 )
  {
    v4 = 4;
    pExceptionObject = &Broker::InvalidParameter::`vftable';
    v3 = 0;
    throw (Broker::InvalidParameter *)&pExceptionObject;
  }
  return 1;
}

```

## disassembly

```asm
0x180015ac4  sub     rsp, 48h
0x180015ac8  test    ecx, ecx
0x180015aca  jz      short loc_180015B03
0x180015acc  cmp     ecx, 1
0x180015acf  jz      short loc_180015AFF
0x180015ad1  xorps   xmm0, xmm0
0x180015ad4  mov     [rsp+48h+var_10], 4
0x180015adc  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180015ae3  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180015aea  mov     [rsp+48h+pExceptionObject], rax
0x180015aef  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180015af4  movups  [rsp+48h+var_20], xmm0
0x180015af9  call    _CxxThrowException_0
0x180015aff  mov     al, 1
0x180015b01  jmp     short loc_180015B05
0x180015b03  xor     al, al
0x180015b05  add     rsp, 48h
0x180015b09  retn
```
