# CNgcReader::CopyControlResult(uchar const *,ulong,uchar *,ulong *)

- ea: `0x180010bac`
- end: `0x180010c7e`
- name: `?CopyControlResult@CNgcReader@@IEAAKPEBEKPEAEPEAK@Z`
- size: `210`
- prototype: `__int64 __fastcall(CNgcReader *this, const unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180013740`
- `0x180019c1c`
- `0x180019dd8`
- `0x18002c1ec`

## callees

- `0x180010bac`
- `0x180010c84`
- `0x180010ca0`
- `0x180023276`
- `0x1800326d0`

## string_xrefs

- `0x180010bc8`: `CNgcReader::CopyControlResult`

## pseudocode

```c
__int64 __fastcall CNgcReader::CopyControlResult(
        CNgcReader *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  size_t v5; // rdi
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-50h] BYREF
  int v11; // [rsp+24h] [rbp-4Ch] BYREF
  _QWORD *v12; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v13[3]; // [rsp+30h] [rbp-40h] BYREF
  char v14[32]; // [rsp+48h] [rbp-28h] BYREF

  v13[0] = v14;
  v5 = a3;
  v13[1] = &v11;
  v10 = 0;
  strcpy(v14, "CNgcReader::CopyControlResult");
  v13[2] = &v10;
  v11 = 0;
  lambda_a873074d1d2ad5b4d41a4e725fc6dd42_::operator()(v13);
  v11 = 1;
  v12 = v13;
  if ( (_DWORD)v5 )
  {
    if ( !a5 || (unsigned int)v5 > *a5 )
    {
      v8 = -2146435064;
      v10 = -2146435064;
      goto LABEL_9;
    }
    memcpy_0(a4, a2, v5);
    *a5 = v5;
  }
  else if ( a5 )
  {
    *a5 = 0;
  }
  v8 = v10;
LABEL_9:
  WppTraceUnwinder__lambda_a873074d1d2ad5b4d41a4e725fc6dd42____::_WppTraceUnwinder__lambda_a873074d1d2ad5b4d41a4e725fc6dd42____(&v12);
  return v8;
}

```

## disassembly

```asm
0x180010bac  push    rbp
0x180010bae  push    rbx
0x180010baf  push    rsi
0x180010bb0  push    rdi
0x180010bb1  push    r14
0x180010bb3  mov     rbp, rsp
0x180010bb6  sub     rsp, 70h
0x180010bba  mov     rax, cs:__security_cookie
0x180010bc1  xor     rax, rsp
0x180010bc4  mov     [rbp+var_8], rax
0x180010bc8  movups  xmm0, xmmword ptr cs:aCngcreaderCopy; "CNgcReader::CopyControlResult"
0x180010bcf  mov     rbx, [rbp+arg_20]
0x180010bd3  lea     rax, [rbp+var_28]
0x180010bd7  movups  xmm1, xmmword ptr cs:aCngcreaderCopy+0Eh; "pyControlResult"
0x180010bde  mov     [rbp+var_40], rax
0x180010be2  lea     rcx, [rbp+var_40]
0x180010be6  lea     rax, [rbp+var_4C]
0x180010bea  mov     edi, r8d
0x180010bed  mov     [rbp+var_38], rax
0x180010bf1  mov     r14, r9
0x180010bf4  lea     rax, [rbp+var_50]
0x180010bf8  mov     [rbp+var_50], 0
0x180010bff  movups  xmmword ptr [rbp+var_28], xmm0
0x180010c03  mov     [rbp+var_30], rax
0x180010c07  mov     rsi, rdx
0x180010c0a  mov     [rbp+var_4C], 0
0x180010c11  movups  xmmword ptr [rbp+var_28+0Eh], xmm1
0x180010c15  call    _lambda_a873074d1d2ad5b4d41a4e725fc6dd42___operator__
0x180010c1a  mov     [rbp+var_4C], 1
0x180010c21  lea     rax, [rbp+var_40]
0x180010c25  mov     [rbp+var_48], rax
0x180010c29  test    edi, edi
0x180010c2b  jnz     short loc_180010C39
0x180010c2d  test    rbx, rbx
0x180010c30  jz      short loc_180010C34
0x180010c32  mov     [rbx], edi
0x180010c34  mov     ebx, [rbp+var_50]
0x180010c37  jmp     short loc_180010C5C
0x180010c39  test    rbx, rbx
0x180010c3c  jz      short loc_180010C54
0x180010c3e  cmp     edi, [rbx]
0x180010c40  ja      short loc_180010C54
0x180010c42  mov     r8, rdi; Size
0x180010c45  mov     rdx, rsi; Src
0x180010c48  mov     rcx, r14; void *
0x180010c4b  call    memcpy_0
0x180010c50  mov     [rbx], edi
0x180010c52  jmp     short loc_180010C34
0x180010c54  mov     ebx, 80100008h
0x180010c59  mov     [rbp+var_50], ebx
0x180010c5c  lea     rcx, [rbp+var_48]
0x180010c60  call    WppTraceUnwinder__lambda_a873074d1d2ad5b4d41a4e725fc6dd42_______WppTraceUnwinder__lambda_a873074d1d2ad5b4d41a4e725fc6dd42____
0x180010c65  mov     eax, ebx
0x180010c67  mov     rcx, [rbp+var_8]
0x180010c6b  xor     rcx, rsp; StackCookie
0x180010c6e  call    __security_check_cookie
0x180010c73  add     rsp, 70h
0x180010c77  pop     r14
0x180010c79  pop     rdi
0x180010c7a  pop     rsi
0x180010c7b  pop     rbx
0x180010c7c  pop     rbp
0x180010c7d  retn
```
