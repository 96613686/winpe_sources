# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18000de80`
- end: `0x18000df9a`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `282`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `9`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000aec0`
- `0x18000c820`
- `0x18000cbd0`
- `0x18000ccb0`
- `0x18000cd80`
- `0x18000d3b0`
- `0x18000d8d0`
- `0x18000dac0`
- `0x18000de10`

## callees

- `0x18000de80`
- `0x18001cf40`
- `0x18001d600`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000df38`
- `KERNEL32!GetLastError` at `0x18000df38`
- `KERNEL32!SetLastError` at `0x18000df4b`
- `KERNEL32!SetLastError` at `0x18000df4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dea8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dea8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df43`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000df2a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000df2a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000df0b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000df1e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000df0b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000df1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  size_t v3; // rbp
  char *v4; // rax
  char *v5; // r14
  const void *v6; // rbx
  size_t v7; // rsi
  void *v8; // r15
  DWORD LastError; // ebx
  bool result; // al

  if ( *((_QWORD *)this + 260) - *((_QWORD *)this + 258) > a2 )
    a2 = *((_QWORD *)this + 260) - *((_QWORD *)this + 258);
  v3 = 2 * a2;
  v4 = (char *)CoTaskMemAlloc(2 * a2);
  v5 = v4;
  if ( !v4 )
  {
    *((_BYTE *)this + 8) = 1;
    return 0;
  }
  v6 = (const void *)*((_QWORD *)this + 258);
  v7 = *((_QWORD *)this + 259) - (_QWORD)v6;
  if ( v7 )
  {
    if ( !v6 || v3 < v7 )
    {
      memset(v4, 0, v3);
      if ( v6 )
      {
        if ( v3 >= v7 )
          goto LABEL_13;
        *_errno() = 34;
      }
      else
      {
        *_errno() = 22;
      }
      _invalid_parameter_noinfo();
      goto LABEL_13;
    }
    _mm_lfence();
    memmove(v4, v6, v7);
  }
LABEL_13:
  v8 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    CoTaskMemFree(v8);
    SetLastError(LastError);
  }
  *(_QWORD *)this = v5;
  *((_QWORD *)this + 259) = &v5[v7];
  *((_QWORD *)this + 260) = &v5[v3];
  result = 1;
  *((_QWORD *)this + 258) = v5;
  return result;
}

```

## disassembly

```asm
0x18000de80  push    rbp
0x18000de82  push    rdi
0x18000de83  push    r14
0x18000de85  sub     rsp, 20h
0x18000de89  mov     rax, [rcx+820h]
0x18000de90  mov     rdi, rcx
0x18000de93  sub     rax, [rcx+810h]
0x18000de9a  cmp     rax, rdx
0x18000de9d  cmova   rdx, rax
0x18000dea1  lea     rbp, [rdx+rdx]
0x18000dea5  mov     rcx, rbp; cb
0x18000dea8  call    cs:__imp_CoTaskMemAlloc
0x18000deae  mov     r14, rax
0x18000deb1  test    rax, rax
0x18000deb4  jz      loc_18000DF8B
0x18000deba  mov     [rsp+38h+arg_0], rbx
0x18000debf  mov     rbx, [rdi+810h]
0x18000dec6  mov     [rsp+38h+arg_8], rsi
0x18000decb  mov     rsi, [rdi+818h]
0x18000ded2  mov     [rsp+38h+arg_10], r15
0x18000ded7  sub     rsi, rbx
0x18000deda  jz      short loc_18000DF30
0x18000dedc  test    rbx, rbx
0x18000dedf  jz      short loc_18000DEF9
0x18000dee1  cmp     rbp, rsi
0x18000dee4  jb      short loc_18000DEF9
0x18000dee6  lfence
0x18000dee9  mov     r8, rsi; Size
0x18000deec  mov     rdx, rbx; Src
0x18000deef  mov     rcx, rax; void *
0x18000def2  call    memmove
0x18000def7  jmp     short loc_18000DF30
0x18000def9  mov     r8, rbp; Size
0x18000defc  xor     edx, edx; Val
0x18000defe  mov     rcx, r14; void *
0x18000df01  call    memset
0x18000df06  test    rbx, rbx
0x18000df09  jnz     short loc_18000DF19
0x18000df0b  call    cs:__imp__errno
0x18000df11  mov     dword ptr [rax], 16h
0x18000df17  jmp     short loc_18000DF2A
0x18000df19  cmp     rbp, rsi
0x18000df1c  jnb     short loc_18000DF30
0x18000df1e  call    cs:__imp__errno
0x18000df24  mov     dword ptr [rax], 22h ; '"'
0x18000df2a  call    cs:__imp__invalid_parameter_noinfo
0x18000df30  mov     r15, [rdi]
0x18000df33  test    r15, r15
0x18000df36  jz      short loc_18000DF51
0x18000df38  call    cs:__imp_GetLastError
0x18000df3e  mov     rcx, r15; pv
0x18000df41  mov     ebx, eax
0x18000df43  call    cs:__imp_CoTaskMemFree
0x18000df49  mov     ecx, ebx; dwErrCode
0x18000df4b  call    cs:__imp_SetLastError
0x18000df51  mov     r15, [rsp+38h+arg_10]
0x18000df56  lea     rax, [rsi+r14]
0x18000df5a  mov     rsi, [rsp+38h+arg_8]
0x18000df5f  mov     rbx, [rsp+38h+arg_0]
0x18000df64  mov     [rdi], r14
0x18000df67  mov     [rdi+818h], rax
0x18000df6e  lea     rax, [r14+rbp]
0x18000df72  mov     [rdi+820h], rax
0x18000df79  mov     al, 1
0x18000df7b  mov     [rdi+810h], r14
0x18000df82  add     rsp, 20h
0x18000df86  pop     r14
0x18000df88  pop     rdi
0x18000df89  pop     rbp
0x18000df8a  retn
0x18000df8b  mov     byte ptr [rdi+8], 1
0x18000df8f  xor     al, al
0x18000df91  add     rsp, 20h
0x18000df95  pop     r14
0x18000df97  pop     rdi
0x18000df98  pop     rbp
0x18000df99  retn
```
