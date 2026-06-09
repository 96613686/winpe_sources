# CLogETWBlock::~CLogETWBlock(void)

- ea: `0x180003dc0`
- end: `0x180003e52`
- name: `??1CLogETWBlock@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(CLogETWBlock *this, __int64)`
- caller_count: `36`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005a90`
- `0x1800066f0`
- `0x18000bee0`
- `0x18000caa0`
- `0x18000d51c`
- `0x180013620`
- `0x1800136b0`
- `0x1800137d0`
- `0x180013860`
- `0x180013940`
- `0x180013a30`
- `0x180013ac0`
- `0x180013b50`
- `0x180013ec8`
- `0x180014088`
- `0x180014510`
- `0x180014750`
- `0x1800148fc`
- `0x180014c2c`
- `0x1800157d4`
- `0x180015c94`
- `0x18001640c`
- `0x1800167c8`
- `0x180016b9c`
- `0x18001a4c0`
- `0x18001a500`
- `0x18001a540`
- `0x18001a580`
- `0x18001a5a0`
- `0x18001a600`
- `0x18001a664`
- `0x18001a676`
- `0x18001aa50`
- `0x18001aa62`
- `0x18001aa86`
- `0x18001aae0`

## callees

- `0x180003dc0`
- `0x180003e60`
- `0x180007d20`
- `0x18000c344`

## pseudocode

```c
void __fastcall CLogETWBlock::~CLogETWBlock(CLogETWBlock *this, __int64 a2)
{
  unsigned int *v2; // r9
  __int64 v4; // r9
  unsigned int *v5; // r9
  unsigned int *v6; // r9
  int v7; // [rsp+30h] [rbp+8h] BYREF

  v2 = (unsigned int *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    v4 = *v2;
  }
  else
  {
    v5 = (unsigned int *)*((_QWORD *)this + 2);
    if ( v5 )
    {
      v4 = *v5;
      LODWORD(v4) = v4 | 0x10000000;
    }
    else
    {
      v6 = (unsigned int *)*((_QWORD *)this + 3);
      if ( !v6 )
        goto LABEL_4;
      v4 = *v6;
      if ( (int)v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
    }
  }
  v7 = v4;
  if ( (int)v4 < 0 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(this, a2, *(_QWORD *)this, v4);
    CertPolEngProvider::GenericMethodFailure<char const * &,long &>((const unsigned __int16 **)this, &v7);
  }
LABEL_4:
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(this, Func_Exit, *(_QWORD *)this);
}

```

## disassembly

```asm
0x180003dc0  push    rbx
0x180003dc2  sub     rsp, 20h
0x180003dc6  mov     r9, [rcx+8]
0x180003dca  mov     rbx, rcx
0x180003dcd  test    r9, r9
0x180003dd0  jz      short loc_180003DEE
0x180003dd2  mov     r9d, [r9]
0x180003dd5  mov     [rsp+28h+arg_0], r9d
0x180003dda  test    r9d, r9d
0x180003ddd  js      short loc_180003E01
0x180003ddf  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x180003de6  jnz     short loc_180003E41
0x180003de8  add     rsp, 20h
0x180003dec  pop     rbx
0x180003ded  retn
0x180003dee  mov     r9, [rcx+10h]
0x180003df2  test    r9, r9
0x180003df5  jz      short loc_180003E19
0x180003df7  mov     r9d, [r9]
0x180003dfa  bts     r9d, 1Ch
0x180003dff  jmp     short loc_180003DD5
0x180003e01  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180003e08  jnz     short loc_180003E37
0x180003e0a  lea     rdx, [rsp+28h+arg_0]
0x180003e0f  mov     rcx, rbx
0x180003e12  call    ??$GenericMethodFailure@AEAPEBDAEAJ@CertPolEngProvider@@SAXAEAPEBDAEAJ@Z; CertPolEngProvider::GenericMethodFailure<char const * &,long &>(char const * &,long &)
0x180003e17  jmp     short loc_180003DDF
0x180003e19  mov     r9, [rcx+18h]
0x180003e1d  test    r9, r9
0x180003e20  jz      short loc_180003DDF
0x180003e22  mov     r9d, [r9]
0x180003e25  test    r9d, r9d
0x180003e28  jle     short loc_180003DD5
0x180003e2a  movzx   r9d, r9w
0x180003e2e  or      r9d, 80070000h
0x180003e35  jmp     short loc_180003DD5
0x180003e37  mov     r8, [rcx]
0x180003e3a  call    McTemplateU0sq_EtwEventWriteTransfer
0x180003e3f  jmp     short loc_180003E0A
0x180003e41  mov     r8, [rbx]
0x180003e44  lea     rdx, Func_Exit
0x180003e4b  call    McTemplateU0s_EtwEventWriteTransfer
0x180003e50  jmp     short loc_180003DE8
```
