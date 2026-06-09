# NetSetup2::ObjectCreationTemplate::WritePropertiesToExistingObject(NetSetup2::ActiveObject &)

- ea: `0x18002da68`
- end: `0x18002daf2`
- name: `?WritePropertiesToExistingObject@ObjectCreationTemplate@NetSetup2@@QEBAXAEAVActiveObject@2@@Z`
- size: `138`
- prototype: `void(NetSetup2::ObjectCreationTemplate *__hidden this, struct NetSetup2::ActiveObject *)`
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001a9e4`
- `0x18001dce8`
- `0x18001ddac`
- `0x180020384`

## callees

- `0x1800027c0`
- `0x18000d974`
- `0x18002a334`
- `0x18002ba08`
- `0x18002c728`
- `0x18002da68`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NetSetup2::ObjectCreationTemplate::WritePropertiesToExistingObject(
        NetSetup2::ObjectCreationTemplate *this,
        struct NetSetup2::ActiveObject *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rdi
  _BYTE v5[24]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v6[24]; // [rsp+38h] [rbp-30h] BYREF

  v3 = *(_QWORD *)this;
  v4 = *((_QWORD *)this + 1);
  while ( v3 != v4 )
  {
    NetSetup2::ActiveObject::GetProperty(a2, (const struct _NETSETUPPROPKEY *)v5, v3);
    if ( !(unsigned __int8)NetSetup2::Property::operator==(v5, v3) )
      NetSetup2::ActiveObject::SetPropertyUniversal<NetSetup2::Property const &>(a2, v3);
    std::vector<unsigned char>::_Tidy((__int64)v6);
    v3 += 48;
  }
}

```

## disassembly

```asm
0x18002da68  mov     [rsp+arg_0], rbx
0x18002da6d  mov     [rsp+arg_10], rsi
0x18002da72  push    rdi
0x18002da73  sub     rsp, 60h
0x18002da77  mov     rax, cs:__security_cookie
0x18002da7e  xor     rax, rsp
0x18002da81  mov     [rsp+68h+var_18], rax
0x18002da86  mov     rsi, rdx
0x18002da89  mov     rbx, [rcx]
0x18002da8c  mov     rdi, [rcx+8]
0x18002da90  cmp     rbx, rdi
0x18002da93  jz      short loc_18002DAD3
0x18002da95  mov     r8, rbx
0x18002da98  lea     rdx, [rsp+68h+var_48]; struct _NETSETUPPROPKEY *
0x18002da9d  mov     rcx, rsi; this
0x18002daa0  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x18002daa5  nop
0x18002daa6  mov     rdx, rbx
0x18002daa9  lea     rcx, [rsp+68h+var_48]
0x18002daae  call    ??8Property@NetSetup2@@QEBA_NAEBV01@@Z; NetSetup2::Property::operator==(NetSetup2::Property const &)
0x18002dab3  test    al, al
0x18002dab5  jnz     short loc_18002DAC3
0x18002dab7  mov     rdx, rbx
0x18002daba  mov     rcx, rsi
0x18002dabd  call    ??$SetPropertyUniversal@AEBVProperty@NetSetup2@@@ActiveObject@NetSetup2@@AEAAXAEBVProperty@1@@Z; NetSetup2::ActiveObject::SetPropertyUniversal<NetSetup2::Property const &>(NetSetup2::Property const &)
0x18002dac2  nop
0x18002dac3  lea     rcx, [rsp+68h+var_30]
0x18002dac8  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002dacd  add     rbx, 30h ; '0'
0x18002dad1  jmp     short loc_18002DA90
0x18002dad3  mov     rcx, [rsp+68h+var_18]
0x18002dad8  xor     rcx, rsp; StackCookie
0x18002dadb  call    __security_check_cookie
0x18002dae0  lea     r11, [rsp+68h+var_8]
0x18002dae5  mov     rbx, [r11+10h]
0x18002dae9  mov     rsi, [r11+20h]
0x18002daed  mov     rsp, r11
0x18002daf0  pop     rdi
0x18002daf1  retn
```
