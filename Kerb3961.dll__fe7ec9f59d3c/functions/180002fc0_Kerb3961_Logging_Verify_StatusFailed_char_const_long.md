# Kerb3961::Logging::Verify::StatusFailed(char const *,long)

- ea: `0x180002fc0`
- end: `0x180003090`
- name: `?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z`
- size: `208`
- prototype: `void __fastcall(Kerb3961::Logging::Verify *__hidden this, const char *, int)`
- caller_count: `83`
- callee_count: `3`
- tags: ``

## callers

- `0x1800050e0`
- `0x180005480`
- `0x180005ed0`
- `0x180006270`
- `0x180006ac0`
- `0x1800071e0`
- `0x180007500`
- `0x180007650`
- `0x180007a90`
- `0x180007d00`
- `0x1800082f0`
- `0x180008500`
- `0x1800085cc`
- `0x1800088c0`
- `0x1800090b0`
- `0x180009190`
- `0x1800092a4`
- `0x180009470`
- `0x1800095b0`
- `0x1800098c0`
- `0x1800099c0`
- `0x180009dc0`
- `0x18000a2a0`
- `0x18000aa04`
- `0x18000ae18`
- `0x18000b3d0`
- `0x18000ba20`
- `0x18000c400`
- `0x18000ca80`
- `0x18000cdb0`
- `0x18000cfd0`
- `0x18000d510`
- `0x18000d6e0`
- `0x18000d8b0`
- `0x18000d960`
- `0x18000db90`
- `0x18000e320`
- `0x18000e6c4`
- `0x18000ec30`
- `0x18000ed80`
- `0x18000eee8`
- `0x18000f030`
- `0x18000f2d0`
- `0x18000f438`
- `0x18000f580`
- `0x18000f754`
- `0x1800110c0`
- `0x1800112d0`
- `0x180011530`
- `0x18001190c`

## callees

- `0x18000120c`
- `0x180001d40`
- `0x180002fc0`

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

  if ( (unsigned int)dword_180029000 > 2 )
  {
    v2 = 1;
    if ( (qword_180029010 & 1) != 0 && (qword_180029018 & 1) == qword_180029018 )
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
        this = (Kerb3961::Logging::Verify *)&word_1800205DA;
      }
      v8 = 0;
      v6 = this;
      v7 = v2;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180029000, (unsigned __int8 *)byte_180025F41, 0, 0, 4u, &v5);
    }
  }
}

```

## disassembly

```asm
0x180002fc0  sub     rsp, 98h
0x180002fc7  mov     rax, cs:__security_cookie
0x180002fce  xor     rax, rsp
0x180002fd1  mov     [rsp+98h+var_18], rax
0x180002fd9  mov     eax, cs:dword_180029000
0x180002fdf  cmp     eax, 2
0x180002fe2  jbe     loc_180003078
0x180002fe8  mov     r9, cs:qword_180029018
0x180002fef  mov     r8d, 1
0x180002ff5  mov     rax, cs:qword_180029010
0x180002ffc  test    r8b, al
0x180002fff  jz      short loc_180003078
0x180003001  mov     rax, r9
0x180003004  and     rax, r8
0x180003007  cmp     rax, r9
0x18000300a  jnz     short loc_180003078
0x18000300c  lea     rax, [rsp+98h+var_68]
0x180003011  mov     [rsp+98h+var_68], edx
0x180003015  mov     [rsp+98h+var_28], rax
0x18000301a  lea     edx, [r8+3]
0x18000301e  xor     eax, eax
0x180003020  mov     [rsp+98h+var_20], rdx
0x180003025  test    rcx, rcx
0x180003028  jz      short loc_18000303C
0x18000302a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000302e  inc     r8
0x180003031  cmp     [rcx+r8], al
0x180003035  jnz     short loc_18000302E
0x180003037  inc     r8d
0x18000303a  jmp     short loc_180003043
0x18000303c  lea     rcx, word_1800205DA
0x180003043  mov     [rsp+98h+var_2C], eax
0x180003047  xor     r9d, r9d
0x18000304a  lea     rax, [rsp+98h+var_58]
0x18000304f  mov     [rsp+98h+var_38], rcx
0x180003054  mov     [rsp+98h+var_70], rax
0x180003059  lea     rcx, dword_180029000
0x180003060  mov     [rsp+98h+var_78], edx
0x180003064  lea     rdx, byte_180025F41
0x18000306b  mov     [rsp+98h+var_30], r8d
0x180003070  xor     r8d, r8d
0x180003073  call    _tlgWriteTransfer_EventWriteTransfer
0x180003078  mov     rcx, [rsp+98h+var_18]
0x180003080  xor     rcx, rsp; StackCookie
0x180003083  call    __security_check_cookie
0x180003088  add     rsp, 98h
0x18000308f  retn
```
