# COMMAND_PROCESSOR::SetConfigPropertyValue(INativeConfigurationElement *,ushort const *,ushort const *)

- ea: `0x18000bff0`
- end: `0x18000c147`
- name: `?SetConfigPropertyValue@COMMAND_PROCESSOR@@UEAAJPEAVINativeConfigurationElement@@PEBG1@Z`
- size: `343`
- prototype: `int(COMMAND_PROCESSOR *__hidden this, struct INativeConfigurationElement *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001fb0`
- `0x180002e90`
- `0x180009aac`
- `0x18000bff0`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::SetConfigPropertyValue(
        COMMAND_PROCESSOR *this,
        struct INativeConfigurationElement *a2,
        wchar_t *a3,
        const unsigned __int8 *a4)
{
  int SetConfigPropertyInternal; // edi
  unsigned int v9; // edx
  __int64 v10; // rax
  wchar_t *v12; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[32]; // [rsp+48h] [rbp-B8h] BYREF
  __int16 *v14; // [rsp+68h] [rbp-98h]
  int v15; // [rsp+70h] [rbp-90h]
  __int16 v16; // [rsp+74h] [rbp-8Ch]
  int v17; // [rsp+78h] [rbp-88h]
  __int16 v18; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v19[510]; // [rsp+82h] [rbp-7Eh] BYREF

  memset_0(v19, 0, sizeof(v19));
  v15 = 512;
  v14 = &v18;
  v16 = 256;
  v17 = 0;
  v18 = 0;
  v12 = 0;
  if ( a2 && a3 && a4 )
  {
    SetConfigPropertyInternal = STRU::Copy((STRU *)v13, a4);
    if ( SetConfigPropertyInternal >= 0 )
    {
      if ( *a3 == 45 )
      {
        ++a3;
        v9 = 4;
      }
      else if ( *a3 == 43 )
      {
        v9 = 2;
        ++a3;
      }
      else
      {
        v9 = 1;
      }
      SetConfigPropertyInternal = COMMAND_PROCESSOR::GetSetConfigPropertyInternal(
                                    (COMMAND_PROCESSOR *)((char *)this - 8),
                                    v9,
                                    a2,
                                    (unsigned __int16 *)&Str,
                                    a3,
                                    (STRU *)v13,
                                    0);
      if ( SetConfigPropertyInternal == -2147023483 )
      {
        v10 = *(_QWORD *)this;
        v12 = a3;
        (*(void (__fastcall **)(COMMAND_PROCESSOR *, __int64, __int64, wchar_t **, _DWORD))(v10 + 144))(
          this,
          2147943813LL,
          3221226523LL,
          &v12,
          0);
      }
    }
  }
  else
  {
    SetConfigPropertyInternal = -2147024809;
  }
  BUFFER::~BUFFER((BUFFER *)v13);
  return (unsigned int)SetConfigPropertyInternal;
}

```

## disassembly

```asm
0x18000bff0  push    rbp
0x18000bff2  push    rbx
0x18000bff3  push    rsi
0x18000bff4  push    rdi
0x18000bff5  push    r14
0x18000bff7  lea     rbp, [rsp-190h]
0x18000bfff  sub     rsp, 290h
0x18000c006  mov     rax, cs:__security_cookie
0x18000c00d  xor     rax, rsp
0x18000c010  mov     [rbp+1B0h+var_30], rax
0x18000c017  mov     rbx, r8
0x18000c01a  mov     r14, rdx
0x18000c01d  mov     rsi, rcx
0x18000c020  xor     edx, edx; Val
0x18000c022  mov     r8d, 1FEh; Size
0x18000c028  lea     rcx, [rbp+1B0h+var_22E]; void *
0x18000c02c  mov     rdi, r9
0x18000c02f  call    memset_0
0x18000c034  lea     rax, [rbp+1B0h+var_230]
0x18000c038  mov     [rsp+2B0h+var_240], 200h
0x18000c040  mov     [rsp+2B0h+var_248], rax
0x18000c045  xor     eax, eax
0x18000c047  mov     [rsp+2B0h+var_23C], 100h
0x18000c04e  mov     [rsp+2B0h+var_238], 0
0x18000c056  mov     [rbp+1B0h+var_230], ax
0x18000c05a  mov     [rsp+2B0h+var_270], rax
0x18000c05f  test    r14, r14
0x18000c062  jz      loc_18000C119
0x18000c068  test    rbx, rbx
0x18000c06b  jz      loc_18000C119
0x18000c071  test    rdi, rdi
0x18000c074  jz      loc_18000C119
0x18000c07a  mov     rdx, rdi; unsigned __int16 *
0x18000c07d  lea     rcx, [rsp+2B0h+var_268]; this
0x18000c082  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000c087  mov     edi, eax
0x18000c089  test    eax, eax
0x18000c08b  js      loc_18000C11E
0x18000c091  cmp     word ptr [rbx], 2Dh ; '-'
0x18000c095  jnz     short loc_18000C0A2
0x18000c097  add     rbx, 2
0x18000c09b  mov     edx, 4
0x18000c0a0  jmp     short loc_18000C0B7
0x18000c0a2  cmp     word ptr [rbx], 2Bh ; '+'
0x18000c0a6  jnz     short loc_18000C0B2
0x18000c0a8  mov     edx, 2
0x18000c0ad  add     rbx, rdx
0x18000c0b0  jmp     short loc_18000C0B7
0x18000c0b2  mov     edx, 1
0x18000c0b7  lea     rax, [rsp+2B0h+var_268]
0x18000c0bc  mov     [rsp+2B0h+var_280], 0
0x18000c0c5  mov     [rsp+2B0h+var_288], rax
0x18000c0ca  lea     rcx, [rsi-8]
0x18000c0ce  lea     r9, Str
0x18000c0d5  mov     [rsp+2B0h+var_290], rbx
0x18000c0da  mov     r8, r14
0x18000c0dd  call    ?GetSetConfigPropertyInternal@COMMAND_PROCESSOR@@AEAAJW4CONFIG_OPERATION_TYPE@@PEAVINativeConfigurationElement@@PEBG2PEAVSTRU@@PEAH@Z; COMMAND_PROCESSOR::GetSetConfigPropertyInternal(CONFIG_OPERATION_TYPE,INativeConfigurationElement *,ushort const *,ushort const *,STRU *,int *)
0x18000c0e2  mov     edx, 80070585h
0x18000c0e7  mov     edi, eax
0x18000c0e9  cmp     eax, edx
0x18000c0eb  jnz     short loc_18000C11E
0x18000c0ed  mov     rax, [rsi]
0x18000c0f0  lea     r9, [rsp+2B0h+var_270]
0x18000c0f5  mov     r8d, 0C000041Bh
0x18000c0fb  mov     [rsp+2B0h+var_270], rbx
0x18000c100  mov     rcx, rsi
0x18000c103  mov     dword ptr [rsp+2B0h+var_290], 0
0x18000c10b  mov     rax, [rax+90h]
0x18000c112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c117  jmp     short loc_18000C11E
0x18000c119  mov     edi, 80070057h
0x18000c11e  lea     rcx, [rsp+2B0h+var_268]; this
0x18000c123  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000c128  mov     eax, edi
0x18000c12a  mov     rcx, [rbp+1B0h+var_30]
0x18000c131  xor     rcx, rsp; StackCookie
0x18000c134  call    __security_check_cookie
0x18000c139  add     rsp, 290h
0x18000c140  pop     r14
0x18000c142  pop     rdi
0x18000c143  pop     rsi
0x18000c144  pop     rbx
0x18000c145  pop     rbp
0x18000c146  retn
```
