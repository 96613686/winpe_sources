# Kerb3961::Logging::Cipher::UsageEnabled(ushort const *,bool,Kerb3961::KeyPolicyOperation,uint)

- ea: `0x180003098`
- end: `0x180003196`
- name: `?UsageEnabled@Cipher@Logging@Kerb3961@@YAXPEBG_NW4KeyPolicyOperation@3@I@Z`
- size: `254`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004990`
- `0x180004a20`
- `0x180004a70`
- `0x180004b00`
- `0x180010e50`
- `0x180010ef0`
- `0x180012fe0`
- `0x180018c80`
- `0x180018e30`
- `0x180018eb0`
- `0x180019060`

## callees

- `0x18000120c`
- `0x180001d40`
- `0x180003098`

## pseudocode

```c
int __fastcall Kerb3961::Logging::Cipher::UsageEnabled(char *a1, unsigned __int8 a2, char a3, int a4)
{
  __int64 v4; // rax
  __int64 v5; // rax
  int v6; // eax
  char v8; // [rsp+30h] [rbp-29h] BYREF
  int v9; // [rsp+34h] [rbp-25h] BYREF
  int v10; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-19h] BYREF
  char *v12; // [rsp+60h] [rbp+7h]
  int v13; // [rsp+68h] [rbp+Fh]
  int v14; // [rsp+6Ch] [rbp+13h]
  int *v15; // [rsp+70h] [rbp+17h]
  __int64 v16; // [rsp+78h] [rbp+1Fh]
  char *v17; // [rsp+80h] [rbp+27h]
  __int64 v18; // [rsp+88h] [rbp+2Fh]
  int *v19; // [rsp+90h] [rbp+37h]
  __int64 v20; // [rsp+98h] [rbp+3Fh]

  LODWORD(v4) = dword_180029000;
  if ( (unsigned int)dword_180029000 > 4 )
  {
    LODWORD(v4) = qword_180029010;
    if ( (qword_180029010 & 3) != 0 )
    {
      v4 = qword_180029018 & 3;
      if ( v4 == qword_180029018 )
      {
        v10 = a2;
        v19 = &v9;
        v17 = &v8;
        v15 = &v10;
        v9 = a4;
        v8 = a3;
        v20 = 4;
        v18 = 1;
        v16 = 4;
        if ( a1 )
        {
          v5 = -1;
          do
            ++v5;
          while ( *(_WORD *)&a1[2 * v5] );
          v6 = 2 * v5 + 2;
        }
        else
        {
          a1 = byte_1800205D8;
          v6 = 2;
        }
        v13 = v6;
        v12 = a1;
        v14 = 0;
        LODWORD(v4) = tlgWriteTransfer_EventWriteTransfer(
                        (__int64)&dword_180029000,
                        (unsigned __int8 *)byte_180025FC5,
                        0,
                        0,
                        6u,
                        &v11);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180003098  push    rbp
0x18000309a  lea     rbp, [rsp-57h]
0x18000309f  sub     rsp, 0B0h
0x1800030a6  mov     rax, cs:__security_cookie
0x1800030ad  xor     rax, rsp
0x1800030b0  mov     [rbp+57h+var_10], rax
0x1800030b4  mov     eax, cs:dword_180029000
0x1800030ba  mov     r11d, 4
0x1800030c0  cmp     eax, r11d
0x1800030c3  jbe     loc_180003181
0x1800030c9  mov     r10, cs:qword_180029018
0x1800030d0  mov     rax, cs:qword_180029010
0x1800030d7  test    al, 3
0x1800030d9  jz      loc_180003181
0x1800030df  mov     rax, r10
0x1800030e2  and     eax, 3
0x1800030e5  cmp     rax, r10
0x1800030e8  jnz     loc_180003181
0x1800030ee  movzx   eax, dl
0x1800030f1  xor     edx, edx
0x1800030f3  mov     [rbp+57h+var_78], eax
0x1800030f6  lea     rax, [rbp+57h+var_7C]
0x1800030fa  mov     [rbp+57h+var_20], rax
0x1800030fe  lea     rax, [rbp+57h+var_80]
0x180003102  mov     [rbp+57h+var_30], rax
0x180003106  lea     rax, [rbp+57h+var_78]
0x18000310a  mov     [rbp+57h+var_40], rax
0x18000310e  mov     [rbp+57h+var_7C], r9d
0x180003112  mov     [rbp+57h+var_80], r8b
0x180003116  mov     [rbp+57h+var_18], r11
0x18000311a  mov     [rbp+57h+var_28], 1
0x180003122  mov     [rbp+57h+var_38], r11
0x180003126  test    rcx, rcx
0x180003129  jz      short loc_180003141
0x18000312b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000312f  inc     rax
0x180003132  cmp     [rcx+rax*2], dx
0x180003136  jnz     short loc_18000312F
0x180003138  lea     eax, ds:2[rax*2]
0x18000313f  jmp     short loc_18000314D
0x180003141  lea     rcx, byte_1800205D8
0x180003148  mov     eax, 2
0x18000314d  mov     [rbp+57h+var_48], eax
0x180003150  xor     r9d, r9d
0x180003153  lea     rax, [rbp+57h+var_70]
0x180003157  mov     [rbp+57h+var_50], rcx
0x18000315b  mov     [rbp+57h+var_44], edx
0x18000315e  lea     rcx, dword_180029000
0x180003165  mov     [rsp+0B0h+var_88], rax
0x18000316a  lea     rdx, byte_180025FC5
0x180003171  xor     r8d, r8d
0x180003174  mov     [rsp+0B0h+var_90], 6
0x18000317c  call    _tlgWriteTransfer_EventWriteTransfer
0x180003181  mov     rcx, [rbp+57h+var_10]
0x180003185  xor     rcx, rsp; StackCookie
0x180003188  call    __security_check_cookie
0x18000318d  add     rsp, 0B0h
0x180003194  pop     rbp
0x180003195  retn
```
