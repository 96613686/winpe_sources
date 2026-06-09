# Kerb3961::Logging::Cipher::UsageEnabled(ushort const *,bool,Kerb3961::KeyPolicyOperation,uint)

- ea: `0x1800119a4`
- end: `0x180011aa3`
- name: `?UsageEnabled@Cipher@Logging@Kerb3961@@YAXPEBG_NW4KeyPolicyOperation@3@I@Z`
- size: `255`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180001a00`
- `0x180001bb0`
- `0x180001c40`
- `0x180001df0`
- `0x180006e70`
- `0x180006f10`
- `0x180008308`
- `0x18000d210`
- `0x18000d2a0`
- `0x18000d2f0`
- `0x18000d380`

## callees

- `0x180001008`
- `0x1800119a4`
- `0x180012200`

## pseudocode

```c
int __fastcall Kerb3961::Logging::Cipher::UsageEnabled(_WORD *a1, unsigned __int8 a2, char a3, int a4)
{
  __int64 v4; // rax
  __int64 v5; // rax
  int v6; // eax
  char v8; // [rsp+30h] [rbp-29h] BYREF
  int v9; // [rsp+34h] [rbp-25h] BYREF
  int v10; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-19h] BYREF
  _WORD *v12; // [rsp+60h] [rbp+7h]
  int v13; // [rsp+68h] [rbp+Fh]
  int v14; // [rsp+6Ch] [rbp+13h]
  int *v15; // [rsp+70h] [rbp+17h]
  __int64 v16; // [rsp+78h] [rbp+1Fh]
  char *v17; // [rsp+80h] [rbp+27h]
  __int64 v18; // [rsp+88h] [rbp+2Fh]
  int *v19; // [rsp+90h] [rbp+37h]
  __int64 v20; // [rsp+98h] [rbp+3Fh]

  LODWORD(v4) = dword_18001A000;
  if ( (unsigned int)dword_18001A000 > 4 )
  {
    LODWORD(v4) = qword_18001A010;
    if ( (qword_18001A010 & 3) != 0 )
    {
      v4 = qword_18001A018 & 3;
      if ( v4 == qword_18001A018 )
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
          while ( a1[v5] );
          v6 = 2 * v5 + 2;
        }
        else
        {
          a1 = &unk_1800187AC;
          v6 = 2;
        }
        v13 = v6;
        v12 = a1;
        v14 = 0;
        LODWORD(v4) = tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_18001A000, byte_180018915, 0, 0, 6u, &v11);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800119a4  push    rbp
0x1800119a6  lea     rbp, [rsp-57h]
0x1800119ab  sub     rsp, 0B0h
0x1800119b2  mov     rax, cs:__security_cookie
0x1800119b9  xor     rax, rsp
0x1800119bc  mov     [rbp+57h+var_10], rax
0x1800119c0  mov     eax, cs:dword_18001A000
0x1800119c6  mov     r11d, 4
0x1800119cc  cmp     eax, r11d
0x1800119cf  jbe     loc_180011A8D
0x1800119d5  mov     r10, cs:qword_18001A018
0x1800119dc  mov     rax, cs:qword_18001A010
0x1800119e3  test    al, 3
0x1800119e5  jz      loc_180011A8D
0x1800119eb  mov     rax, r10
0x1800119ee  and     eax, 3
0x1800119f1  cmp     rax, r10
0x1800119f4  jnz     loc_180011A8D
0x1800119fa  movzx   eax, dl
0x1800119fd  xor     edx, edx
0x1800119ff  mov     [rbp+57h+var_78], eax
0x180011a02  lea     rax, [rbp+57h+var_7C]
0x180011a06  mov     [rbp+57h+var_20], rax
0x180011a0a  lea     rax, [rbp+57h+var_80]
0x180011a0e  mov     [rbp+57h+var_30], rax
0x180011a12  lea     rax, [rbp+57h+var_78]
0x180011a16  mov     [rbp+57h+var_40], rax
0x180011a1a  mov     [rbp+57h+var_7C], r9d
0x180011a1e  mov     [rbp+57h+var_80], r8b
0x180011a22  mov     [rbp+57h+var_18], r11
0x180011a26  mov     [rbp+57h+var_28], 1
0x180011a2e  mov     [rbp+57h+var_38], r11
0x180011a32  test    rcx, rcx
0x180011a35  jz      short loc_180011A4D
0x180011a37  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011a3b  inc     rax
0x180011a3e  cmp     [rcx+rax*2], dx
0x180011a42  jnz     short loc_180011A3B
0x180011a44  lea     eax, ds:2[rax*2]
0x180011a4b  jmp     short loc_180011A59
0x180011a4d  lea     rcx, unk_1800187AC
0x180011a54  mov     eax, 2
0x180011a59  mov     [rbp+57h+var_48], eax
0x180011a5c  xor     r9d, r9d
0x180011a5f  lea     rax, [rbp+57h+var_70]
0x180011a63  mov     [rbp+57h+var_50], rcx
0x180011a67  mov     [rbp+57h+var_44], edx
0x180011a6a  lea     rcx, dword_18001A000
0x180011a71  mov     [rsp+0B0h+var_88], rax
0x180011a76  lea     rdx, byte_180018915
0x180011a7d  xor     r8d, r8d
0x180011a80  mov     [rsp+0B0h+var_90], 6
0x180011a88  call    _tlgWriteTransfer_EtwWriteTransfer
0x180011a8d  mov     rcx, [rbp+57h+var_10]
0x180011a91  xor     rcx, rsp; StackCookie
0x180011a94  call    __security_check_cookie
0x180011a99  add     rsp, 0B0h
0x180011aa0  pop     rbp
0x180011aa1  retn
```
