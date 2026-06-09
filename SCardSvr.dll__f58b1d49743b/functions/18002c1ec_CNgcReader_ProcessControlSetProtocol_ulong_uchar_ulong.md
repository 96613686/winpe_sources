# CNgcReader::ProcessControlSetProtocol(ulong,uchar *,ulong *)

- ea: `0x18002c1ec`
- end: `0x18002c2d3`
- name: `?ProcessControlSetProtocol@CNgcReader@@IEAAKKPEAEPEAK@Z`
- size: `231`
- prototype: `__int64 __fastcall(CNgcReader *this, char, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013740`

## callees

- `0x180010bac`
- `0x18002b61c`
- `0x18002b8b4`
- `0x18002c1ec`
- `0x1800326d0`

## string_xrefs

- `0x18002c20e`: `CNgcReader::ProcessControlSetProtocol`

## pseudocode

```c
__int64 __fastcall CNgcReader::ProcessControlSetProtocol(
        CNgcReader *this,
        char a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  CNgcReader *v7; // rcx
  unsigned int v8; // ebx
  int v10; // [rsp+30h] [rbp-19h] BYREF
  int v11; // [rsp+34h] [rbp-15h] BYREF
  unsigned __int8 v12[8]; // [rsp+38h] [rbp-11h] BYREF
  _QWORD *v13; // [rsp+40h] [rbp-9h] BYREF
  _QWORD v14[3]; // [rsp+48h] [rbp-1h] BYREF
  char v15[40]; // [rsp+60h] [rbp+17h] BYREF

  v14[0] = v15;
  v10 = 0;
  v14[1] = &v11;
  strcpy(v15, "CNgcReader::ProcessControlSetProtocol");
  v14[2] = &v10;
  v11 = 0;
  lambda_2da6f19b2fad5b5e89493b22dd88fc7c_::operator()(v14);
  v11 = 1;
  v13 = v14;
  if ( (a2 & 2) != 0 )
  {
    *(_DWORD *)v12 = 2;
    v10 = CNgcReader::CopyControlResult(v7, v12, 4u, a3, a4);
    v8 = v10;
  }
  else
  {
    v8 = -2146435038;
    v10 = -2146435038;
  }
  WppTraceUnwinder__lambda_2da6f19b2fad5b5e89493b22dd88fc7c____::_WppTraceUnwinder__lambda_2da6f19b2fad5b5e89493b22dd88fc7c____(&v13);
  return v8;
}

```

## disassembly

```asm
0x18002c1ec  mov     [rsp-8+arg_0], rbx
0x18002c1f1  push    rbp
0x18002c1f2  push    rsi
0x18002c1f3  push    rdi
0x18002c1f4  lea     rbp, [rsp-47h]
0x18002c1f9  sub     rsp, 90h
0x18002c200  mov     rax, cs:__security_cookie
0x18002c207  xor     rax, rsp
0x18002c20a  mov     [rbp+57h+var_18], rax
0x18002c20e  movups  xmm0, xmmword ptr cs:aCngcreaderProc_0; "CNgcReader::ProcessControlSetProtocol"
0x18002c215  lea     rax, [rbp+57h+var_40]
0x18002c219  mov     rsi, r9
0x18002c21c  movups  xmm1, xmmword ptr cs:aCngcreaderProc_0+10h; "essControlSetProtocol"
0x18002c223  mov     [rbp+57h+var_58], rax
0x18002c227  lea     rcx, [rbp+57h+var_58]
0x18002c22b  lea     rax, [rbp+57h+var_6C]
0x18002c22f  mov     [rbp+57h+var_70], 0
0x18002c236  mov     [rbp+57h+var_50], rax
0x18002c23a  mov     rdi, r8
0x18002c23d  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x18002c241  lea     rax, [rbp+57h+var_70]
0x18002c245  mov     ebx, edx
0x18002c247  movsd   xmm0, qword ptr cs:aCngcreaderProc_0+1Eh; "rotocol"
0x18002c24f  movups  xmmword ptr [rbp+57h+var_40+10h], xmm1
0x18002c253  mov     [rbp+57h+var_48], rax
0x18002c257  mov     [rbp+57h+var_6C], 0
0x18002c25e  movsd   qword ptr [rbp+57h+var_40+1Eh], xmm0
0x18002c263  call    _lambda_2da6f19b2fad5b5e89493b22dd88fc7c___operator__
0x18002c268  mov     [rbp+57h+var_6C], 1
0x18002c26f  lea     rax, [rbp+57h+var_58]
0x18002c273  mov     [rbp+57h+var_60], rax
0x18002c277  test    bl, 2
0x18002c27a  jnz     short loc_18002C286
0x18002c27c  mov     ebx, 80100022h
0x18002c281  mov     [rbp+57h+var_70], ebx
0x18002c284  jmp     short loc_18002C2A9
0x18002c286  mov     r9, rdi; unsigned __int8 *
0x18002c289  mov     dword ptr [rbp+57h+var_68], 2
0x18002c290  mov     r8d, 4; unsigned int
0x18002c296  mov     [rsp+0A0h+var_80], rsi; unsigned int *
0x18002c29b  lea     rdx, [rbp+57h+var_68]; unsigned __int8 *
0x18002c29f  call    ?CopyControlResult@CNgcReader@@IEAAKPEBEKPEAEPEAK@Z; CNgcReader::CopyControlResult(uchar const *,ulong,uchar *,ulong *)
0x18002c2a4  mov     [rbp+57h+var_70], eax
0x18002c2a7  mov     ebx, eax
0x18002c2a9  lea     rcx, [rbp+57h+var_60]
0x18002c2ad  call    WppTraceUnwinder__lambda_2da6f19b2fad5b5e89493b22dd88fc7c_______WppTraceUnwinder__lambda_2da6f19b2fad5b5e89493b22dd88fc7c____
0x18002c2b2  mov     eax, ebx
0x18002c2b4  mov     rcx, [rbp+57h+var_18]
0x18002c2b8  xor     rcx, rsp; StackCookie
0x18002c2bb  call    __security_check_cookie
0x18002c2c0  mov     rbx, [rsp+0A0h+arg_0]
0x18002c2c8  add     rsp, 90h
0x18002c2cf  pop     rdi
0x18002c2d0  pop     rsi
0x18002c2d1  pop     rbp
0x18002c2d2  retn
```
