# Kerb3961::Logging::Verify::StatusFailed(char const *,long)

- ea: `0x1800118cc`
- end: `0x18001199d`
- name: `?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z`
- size: `209`
- prototype: `void __fastcall(Kerb3961::Logging::Verify *__hidden this, const char *, int)`
- caller_count: `75`
- callee_count: `3`
- tags: ``

## callers

- `0x1800023e0`
- `0x1800025e0`
- `0x1800028d4`
- `0x180002cc4`
- `0x180003020`
- `0x180003240`
- `0x180003590`
- `0x180003b10`
- `0x180003dc0`
- `0x1800041a0`
- `0x180004390`
- `0x180004700`
- `0x180004a00`
- `0x180004f80`
- `0x1800051e0`
- `0x1800056f0`
- `0x180005780`
- `0x180005c30`
- `0x180005e34`
- `0x180005fb0`
- `0x1800060f0`
- `0x1800063f0`
- `0x1800064e0`
- `0x180006750`
- `0x180006900`
- `0x1800070e0`
- `0x180007338`
- `0x180007710`
- `0x180007ad0`
- `0x180007e9c`
- `0x180008020`
- `0x1800083f0`
- `0x180008840`
- `0x180008b40`
- `0x180008ce0`
- `0x180008e10`
- `0x180008ea0`
- `0x180009040`
- `0x180009300`
- `0x180009570`
- `0x1800097c0`
- `0x180009ad0`
- `0x180009c48`
- `0x180009da0`
- `0x18000a050`
- `0x18000a1c8`
- `0x18000a320`
- `0x18000a500`
- `0x18000acb4`
- `0x18000b0c8`

## callees

- `0x180001008`
- `0x1800118cc`
- `0x180012200`

## pseudocode

```c
void __fastcall Kerb3961::Logging::Verify::StatusFailed(Kerb3961::Logging::Verify *this, const char *a2)
{
  int v2; // r8d
  __int64 v3; // r8
  int v4; // [rsp+30h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+40h] [rbp-58h] BYREF
  Kerb3961::Logging::Verify *v6; // [rsp+60h] [rbp-38h]
  int v7; // [rsp+68h] [rbp-30h]
  int v8; // [rsp+6Ch] [rbp-2Ch]
  int *v9; // [rsp+70h] [rbp-28h]
  __int64 v10; // [rsp+78h] [rbp-20h]

  if ( (unsigned int)dword_18001A000 > 2 )
  {
    v2 = 1;
    if ( (qword_18001A010 & 1) != 0 && (qword_18001A018 & 1) == qword_18001A018 )
    {
      v4 = (int)a2;
      v9 = &v4;
      v10 = 4;
      if ( this )
      {
        v3 = -1;
        do
          ++v3;
        while ( *((_BYTE *)this + v3) );
        v2 = v3 + 1;
      }
      else
      {
        this = (Kerb3961::Logging::Verify *)&unk_1800187AE;
      }
      v8 = 0;
      v6 = this;
      v7 = v2;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_18001A000, byte_180018891, 0, 0, 4u, &v5);
    }
  }
}

```

## disassembly

```asm
0x1800118cc  sub     rsp, 98h
0x1800118d3  mov     rax, cs:__security_cookie
0x1800118da  xor     rax, rsp
0x1800118dd  mov     [rsp+98h+var_18], rax
0x1800118e5  mov     eax, cs:dword_18001A000
0x1800118eb  cmp     eax, 2
0x1800118ee  jbe     loc_180011984
0x1800118f4  mov     r9, cs:qword_18001A018
0x1800118fb  mov     r8d, 1
0x180011901  mov     rax, cs:qword_18001A010
0x180011908  test    r8b, al
0x18001190b  jz      short loc_180011984
0x18001190d  mov     rax, r9
0x180011910  and     rax, r8
0x180011913  cmp     rax, r9
0x180011916  jnz     short loc_180011984
0x180011918  lea     rax, [rsp+98h+var_68]
0x18001191d  mov     [rsp+98h+var_68], edx
0x180011921  mov     [rsp+98h+var_28], rax
0x180011926  lea     edx, [r8+3]
0x18001192a  xor     eax, eax
0x18001192c  mov     [rsp+98h+var_20], rdx
0x180011931  test    rcx, rcx
0x180011934  jz      short loc_180011948
0x180011936  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001193a  inc     r8
0x18001193d  cmp     [rcx+r8], al
0x180011941  jnz     short loc_18001193A
0x180011943  inc     r8d
0x180011946  jmp     short loc_18001194F
0x180011948  lea     rcx, unk_1800187AE
0x18001194f  mov     [rsp+98h+var_2C], eax
0x180011953  xor     r9d, r9d
0x180011956  lea     rax, [rsp+98h+var_58]
0x18001195b  mov     [rsp+98h+var_38], rcx
0x180011960  mov     [rsp+98h+var_70], rax
0x180011965  lea     rcx, dword_18001A000
0x18001196c  mov     [rsp+98h+var_78], edx
0x180011970  lea     rdx, byte_180018891
0x180011977  mov     [rsp+98h+var_30], r8d
0x18001197c  xor     r8d, r8d
0x18001197f  call    _tlgWriteTransfer_EtwWriteTransfer
0x180011984  mov     rcx, [rsp+98h+var_18]
0x18001198c  xor     rcx, rsp; StackCookie
0x18001198f  call    __security_check_cookie
0x180011994  add     rsp, 98h
0x18001199b  retn
```
