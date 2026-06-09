# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000c970`
- end: `0x18000ca59`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, unsigned __int8 **bufferParam, unsigned __int8 *bufferEnd)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180006840`
- `0x18000ad50`
- `0x18000bd4c`
- `0x18000c180`
- `0x18000d770`

## callees

- `0x18000c970`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c9bf`
- `msvcrt!memcpy_s` at `0x18000c9f4`
- `msvcrt!memcpy_s` at `0x18000ca1f`
- `msvcrt!memcpy_s` at `0x18000c9bf`
- `msvcrt!memcpy_s` at `0x18000c9f4`
- `msvcrt!memcpy_s` at `0x18000ca1f`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **bufferParam,
        unsigned __int8 *bufferEnd)
{
  char *v5; // r8
  char *v7; // rbx
  unsigned __int16 c_size; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al
  unsigned __int16 tempValue; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*bufferParam;
  if ( this->c_countSize == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)bufferEnd )
      return 0;
    this->countBuffer = v5;
    tempValue = 0;
    memcpy_s(&tempValue, 2u, v5, 2u);
    this->count = tempValue;
  }
  else
  {
    v7 = (char *)*bufferParam;
    if ( this->c_countSize == 2 )
    {
      v7 = v5 + 4;
      if ( v5 + 4 > (char *)bufferEnd )
        return 0;
      this->countBuffer = v5;
      memcpy_s(&this->count, 4u, v5, 4u);
    }
  }
  c_size = this->c_size;
  this->size = this->c_size;
  if ( c_size )
    goto LABEL_10;
  if ( v7 + 2 > (char *)bufferEnd )
    return 0;
  memcpy_s(&this->size, 2u, v7, 2u);
  v7 += 2;
LABEL_10:
  v9 = (unsigned __int8 *)&v7[this->size];
  if ( v9 > bufferEnd )
    return 0;
  this->value = v7;
  result = 1;
  *bufferParam = v9;
  return result;
}

```

## disassembly

```asm
0x18000c970  mov     rax, rsp
0x18000c973  mov     [rax+10h], rbx
0x18000c977  mov     [rax+18h], rbp
0x18000c97b  push    rsi
0x18000c97c  push    rdi
0x18000c97d  push    r12
0x18000c97f  push    r14
0x18000c981  push    r15
0x18000c983  sub     rsp, 20h
0x18000c987  xor     r15d, r15d
0x18000c98a  mov     rsi, bufferEnd
0x18000c98d  cmp     byte ptr [this+2], 1
0x18000c991  mov     r12, bufferParam
0x18000c994  mov     bufferEnd, [bufferParam]; Source
0x18000c997  mov     rdi, this
0x18000c99a  jnz     short loc_18000C9CF
0x18000c99c  lea     rbx, [bufferEnd+2]
0x18000c9a0  cmp     rbx, rsi
0x18000c9a3  ja      loc_18000CA34
0x18000c9a9  lea     ebp, [r15+2]
0x18000c9ad  mov     [this+10h], bufferEnd
0x18000c9b1  mov     r9d, ebp; SourceSize
0x18000c9b4  mov     [rax+8], r15w
0x18000c9b9  mov     edx, ebp; DestinationSize
0x18000c9bb  lea     this, [rax+8]; Destination
0x18000c9bf  call    cs:__imp_memcpy_s
0x18000c9c5  movzx   eax, [rsp+48h+tempValue]
0x18000c9ca  mov     [rdi+4], eax
0x18000c9cd  jmp     short loc_18000C9FA
0x18000c9cf  mov     ebp, 2
0x18000c9d4  mov     rbx, bufferEnd
0x18000c9d7  cmp     [this+2], bpl
0x18000c9db  jnz     short loc_18000C9FA
0x18000c9dd  lea     rbx, [bufferEnd+4]
0x18000c9e1  cmp     rbx, rsi
0x18000c9e4  ja      short loc_18000CA34
0x18000c9e6  lea     edx, [rbp+2]; DestinationSize
0x18000c9e9  mov     [this+10h], bufferEnd
0x18000c9ed  mov     r9d, edx; SourceSize
0x18000c9f0  add     this, 4; Destination
0x18000c9f4  call    cs:__imp_memcpy_s
0x18000c9fa  movzx   eax, word ptr [rdi]
0x18000c9fd  lea     r14, [rdi+8]
0x18000ca01  mov     [r14], ax
0x18000ca05  test    ax, ax
0x18000ca08  jnz     short loc_18000CA28
0x18000ca0a  lea     r15, [rbx+2]
0x18000ca0e  cmp     r15, rsi
0x18000ca11  ja      short loc_18000CA34
0x18000ca13  mov     r9, rbp; SourceSize
0x18000ca16  mov     bufferEnd, rbx; Source
0x18000ca19  mov     bufferParam, rbp; DestinationSize
0x18000ca1c  mov     this, r14; Destination
0x18000ca1f  call    cs:__imp_memcpy_s
0x18000ca25  mov     rbx, r15
0x18000ca28  movzx   ecx, word ptr [r14]
0x18000ca2c  add     this, rbx
0x18000ca2f  cmp     this, rsi
0x18000ca32  jbe     short loc_18000CA38
0x18000ca34  xor     al, al
0x18000ca36  jmp     short loc_18000CA42
0x18000ca38  mov     [rdi+18h], rbx
0x18000ca3c  mov     al, 1
0x18000ca3e  mov     [r12], this
0x18000ca42  mov     rbx, [rsp+48h+arg_8]
0x18000ca47  mov     rbp, [rsp+48h+arg_10]
0x18000ca4c  add     rsp, 20h
0x18000ca50  pop     r15
0x18000ca52  pop     r14
0x18000ca54  pop     r12
0x18000ca56  pop     rdi
0x18000ca57  pop     rsi
0x18000ca58  retn
```
