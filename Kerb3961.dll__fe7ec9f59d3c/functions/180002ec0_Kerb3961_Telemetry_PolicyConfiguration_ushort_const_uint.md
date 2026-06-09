# Kerb3961::Telemetry::PolicyConfiguration(ushort const *,uint)

- ea: `0x180002ec0`
- end: `0x180002fb8`
- name: `?PolicyConfiguration@Telemetry@Kerb3961@@YAXPEBGI@Z`
- size: `248`
- prototype: `void __fastcall(Kerb3961::Telemetry *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000c944`

## callees

- `0x18000120c`
- `0x180001d40`
- `0x180002ec0`

## pseudocode

```c
void __fastcall Kerb3961::Telemetry::PolicyConfiguration(Kerb3961::Telemetry *this, const unsigned __int16 *a2)
{
  __int64 v2; // rax
  int v3; // eax
  int v4; // [rsp+30h] [rbp-19h] BYREF
  __int64 v5; // [rsp+38h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+40h] [rbp-9h] BYREF
  Kerb3961::Telemetry *v7; // [rsp+60h] [rbp+17h]
  int v8; // [rsp+68h] [rbp+1Fh]
  int v9; // [rsp+6Ch] [rbp+23h]
  int *v10; // [rsp+70h] [rbp+27h]
  __int64 v11; // [rsp+78h] [rbp+2Fh]
  __int64 *v12; // [rsp+80h] [rbp+37h]
  __int64 v13; // [rsp+88h] [rbp+3Fh]

  if ( (unsigned int)dword_180029000 > 5
    && (qword_180029010 & 0x400000000000LL) != 0
    && (qword_180029018 & 0x400000000000LL) == qword_180029018 )
  {
    v4 = (int)a2;
    v12 = &v5;
    v5 = 0x1000000;
    v10 = &v4;
    v13 = 8;
    v11 = 4;
    if ( this )
    {
      v2 = -1;
      do
        ++v2;
      while ( *((_WORD *)this + v2) );
      v3 = 2 * v2 + 2;
    }
    else
    {
      this = (Kerb3961::Telemetry *)byte_1800205D8;
      v3 = 2;
    }
    v8 = v3;
    v7 = this;
    v9 = 0;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180029000, (unsigned __int8 *)word_180026112, 0, 0, 5u, &v6);
  }
}

```

## disassembly

```asm
0x180002ec0  push    rbp
0x180002ec2  lea     rbp, [rsp-57h]
0x180002ec7  sub     rsp, 0A0h
0x180002ece  mov     rax, cs:__security_cookie
0x180002ed5  xor     rax, rsp
0x180002ed8  mov     [rbp+57h+var_10], rax
0x180002edc  mov     eax, cs:dword_180029000
0x180002ee2  cmp     eax, 5
0x180002ee5  jbe     loc_180002FA3
0x180002eeb  mov     r8, cs:qword_180029018
0x180002ef2  mov     r9, 400000000000h
0x180002efc  mov     rax, cs:qword_180029010
0x180002f03  test    r9, rax
0x180002f06  jz      loc_180002FA3
0x180002f0c  mov     rax, r8
0x180002f0f  and     rax, r9
0x180002f12  cmp     rax, r8
0x180002f15  jnz     loc_180002FA3
0x180002f1b  lea     rax, [rbp+57h+var_68]
0x180002f1f  mov     [rbp+57h+var_70], edx
0x180002f22  mov     [rbp+57h+var_20], rax
0x180002f26  xor     edx, edx
0x180002f28  mov     [rbp+57h+var_68], 1000000h
0x180002f30  lea     rax, [rbp+57h+var_70]
0x180002f34  mov     [rbp+57h+var_30], rax
0x180002f38  mov     [rbp+57h+var_18], 8
0x180002f40  mov     [rbp+57h+var_28], 4
0x180002f48  test    rcx, rcx
0x180002f4b  jz      short loc_180002F63
0x180002f4d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002f51  inc     rax
0x180002f54  cmp     [rcx+rax*2], dx
0x180002f58  jnz     short loc_180002F51
0x180002f5a  lea     eax, ds:2[rax*2]
0x180002f61  jmp     short loc_180002F6F
0x180002f63  lea     rcx, byte_1800205D8
0x180002f6a  mov     eax, 2
0x180002f6f  mov     [rbp+57h+var_38], eax
0x180002f72  xor     r9d, r9d
0x180002f75  lea     rax, [rbp+57h+var_60]
0x180002f79  mov     [rbp+57h+var_40], rcx
0x180002f7d  mov     [rbp+57h+var_34], edx
0x180002f80  lea     rcx, dword_180029000
0x180002f87  mov     [rsp+0A0h+var_78], rax
0x180002f8c  lea     rdx, word_180026112
0x180002f93  xor     r8d, r8d
0x180002f96  mov     [rsp+0A0h+var_80], 5
0x180002f9e  call    _tlgWriteTransfer_EventWriteTransfer
0x180002fa3  mov     rcx, [rbp+57h+var_10]
0x180002fa7  xor     rcx, rsp; StackCookie
0x180002faa  call    __security_check_cookie
0x180002faf  add     rsp, 0A0h
0x180002fb6  pop     rbp
0x180002fb7  retn
```
