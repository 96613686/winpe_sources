# NetSetup2::ObjectCreationTemplate::GetProperty(_NETSETUPPROPKEY const &)

- ea: `0x18002c89c`
- end: `0x18002c944`
- name: `?GetProperty@ObjectCreationTemplate@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z`
- size: `168`
- prototype: `struct Property __fastcall(NetSetup2::ObjectCreationTemplate *this, struct Property *)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800223a4`
- `0x180022800`
- `0x180024468`

## callees

- `0x18000d974`
- `0x18001d294`
- `0x18002b784`
- `0x18002c89c`
- `0x18002d90c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct Property __fastcall NetSetup2::ObjectCreationTemplate::GetProperty(
        NetSetup2::ObjectCreationTemplate *this,
        struct Property *a2)
{
  const struct _NETSETUPPROPKEY *v3; // r11
  const struct Property *v4; // rax
  char v5; // bl
  char v6; // bl
  struct Property *v8; // [rsp+28h] [rbp-80h] BYREF
  char v9; // [rsp+30h] [rbp-78h]
  _BYTE v10[24]; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v11[24]; // [rsp+50h] [rbp-58h] BYREF
  _BYTE v12[24]; // [rsp+68h] [rbp-40h] BYREF
  _BYTE v13[40]; // [rsp+80h] [rbp-28h] BYREF

  v8 = a2;
  NetSetup2::PropertyArray::TryGetProperty(this, &v8);
  if ( v9 )
  {
    v4 = (const struct Property *)NetSetup2::Property::Property((NetSetup2::Property *)v12, v8);
    v5 = 1;
  }
  else
  {
    v4 = (const struct Property *)NetSetup2::Property::Property((NetSetup2::Property *)v10, v3);
    v5 = 2;
  }
  NetSetup2::Property::Property((NetSetup2::Property *)a2, v4);
  v6 = v5 | 4;
  if ( (v6 & 2) != 0 )
  {
    v6 &= ~2u;
    std::vector<unsigned char>::_Tidy((__int64)v11);
  }
  if ( (v6 & 1) != 0 )
    std::vector<unsigned char>::_Tidy((__int64)v13);
  return (struct Property)a2;
}

```

## disassembly

```asm
0x18002c89c  mov     [rsp+arg_18], rbx
0x18002c8a1  push    rdi
0x18002c8a2  sub     rsp, 0A0h
0x18002c8a9  mov     r11, r8
0x18002c8ac  mov     rdi, rdx
0x18002c8af  mov     [rsp+0A8h+var_80], rdx
0x18002c8b4  mov     [rsp+0A8h+var_88], 0
0x18002c8bc  lea     rdx, [rsp+0A8h+var_80]
0x18002c8c1  call    ?TryGetProperty@PropertyArray@NetSetup2@@QEBA?AV?$Optional@AEBVProperty@NetSetup2@@@details@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::PropertyArray::TryGetProperty(_NETSETUPPROPKEY const &)
0x18002c8c6  nop
0x18002c8c7  cmp     [rsp+0A8h+var_78], 0
0x18002c8cc  jz      short loc_18002C8E5
0x18002c8ce  mov     rdx, [rsp+0A8h+var_80]; struct Property *
0x18002c8d3  lea     rcx, [rsp+0A8h+var_40]; this
0x18002c8d8  call    ??0Property@NetSetup2@@QEAA@AEBV01@@Z; NetSetup2::Property::Property(NetSetup2::Property const &)
0x18002c8dd  nop
0x18002c8de  mov     ebx, 1
0x18002c8e3  jmp     short loc_18002C8F8
0x18002c8e5  mov     rdx, r11; struct _NETSETUPPROPKEY *
0x18002c8e8  lea     rcx, [rsp+0A8h+var_70]; this
0x18002c8ed  call    ??0Property@NetSetup2@@QEAA@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::Property::Property(_NETSETUPPROPKEY const &)
0x18002c8f2  nop
0x18002c8f3  mov     ebx, 2
0x18002c8f8  mov     [rsp+0A8h+var_88], ebx
0x18002c8fc  mov     rdx, rax; struct Property *
0x18002c8ff  mov     rcx, rdi; this
0x18002c902  call    ??0Property@NetSetup2@@QEAA@AEBV01@@Z; NetSetup2::Property::Property(NetSetup2::Property const &)
0x18002c907  or      ebx, 4
0x18002c90a  test    bl, 2
0x18002c90d  jz      short loc_18002C91D
0x18002c90f  and     ebx, 0FFFFFFFDh
0x18002c912  lea     rcx, [rsp+0A8h+var_58]
0x18002c917  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002c91c  nop
0x18002c91d  test    bl, 1
0x18002c920  jz      short loc_18002C930
0x18002c922  lea     rcx, [rsp+0A8h+var_28]
0x18002c92a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002c92f  nop
0x18002c930  mov     rax, rdi
0x18002c933  mov     rbx, [rsp+0A8h+arg_18]
0x18002c93b  add     rsp, 0A0h
0x18002c942  pop     rdi
0x18002c943  retn
```
