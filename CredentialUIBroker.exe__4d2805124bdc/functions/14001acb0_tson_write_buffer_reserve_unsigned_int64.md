# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x14001acb0`
- end: `0x14001ad70`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140004858`
- `0x1400049d4`
- `0x14000796c`
- `0x14001a990`

## callees

- `0x1400085ac`
- `0x1400097ec`
- `0x14001acb0`
- `0x14001c2b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001ace1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001ace1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001ad23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001ad23`

## pseudocode

```c
bool __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  rsize_t v3; // r14
  char *v4; // rax
  char *v5; // rdi
  const void *v6; // r8
  rsize_t v7; // rsi
  void *v8; // rbp
  bool result; // al
  char v10; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 260) - *((_QWORD *)this + 258) > a2 )
    a2 = *((_QWORD *)this + 260) - *((_QWORD *)this + 258);
  v3 = 2 * a2;
  v4 = (char *)CoTaskMemAlloc(2 * a2);
  v5 = v4;
  if ( v4 )
  {
    v6 = (const void *)*((_QWORD *)this + 258);
    v7 = *((_QWORD *)this + 259) - (_QWORD)v6;
    memcpy_s_0(v4, v3, v6, v7);
    v8 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
      CoTaskMemFree(v8);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
    }
    *(_QWORD *)this = v5;
    *((_QWORD *)this + 259) = &v5[v7];
    *((_QWORD *)this + 260) = &v5[v3];
    result = 1;
    *((_QWORD *)this + 258) = v5;
  }
  else
  {
    *((_BYTE *)this + 8) = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14001acb0  mov     [rsp+arg_8], rbx
0x14001acb5  mov     [rsp+arg_10], rbp
0x14001acba  push    rsi
0x14001acbb  push    rdi
0x14001acbc  push    r14
0x14001acbe  sub     rsp, 20h
0x14001acc2  mov     rax, [rcx+820h]
0x14001acc9  mov     rbx, rcx
0x14001accc  sub     rax, [rcx+810h]
0x14001acd3  cmp     rax, rdx
0x14001acd6  cmova   rdx, rax
0x14001acda  lea     r14, [rdx+rdx]
0x14001acde  mov     rcx, r14; cb
0x14001ace1  call    cs:__imp_CoTaskMemAlloc
0x14001ace7  mov     rdi, rax
0x14001acea  test    rax, rax
0x14001aced  jz      short loc_14001AD57
0x14001acef  mov     r8, [rbx+810h]; Source
0x14001acf6  mov     rdx, r14; DestinationSize
0x14001acf9  mov     rsi, [rbx+818h]
0x14001ad00  mov     rcx, rax; Destination
0x14001ad03  sub     rsi, r8
0x14001ad06  mov     r9, rsi; SourceSize
0x14001ad09  call    memcpy_s_0
0x14001ad0e  mov     rbp, [rbx]
0x14001ad11  test    rbp, rbp
0x14001ad14  jz      short loc_14001AD33
0x14001ad16  lea     rcx, [rsp+38h+arg_0]; this
0x14001ad1b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001ad20  mov     rcx, rbp; pv
0x14001ad23  call    cs:__imp_CoTaskMemFree
0x14001ad29  lea     rcx, [rsp+38h+arg_0]; this
0x14001ad2e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001ad33  mov     [rbx], rdi
0x14001ad36  lea     rax, [rsi+rdi]
0x14001ad3a  mov     [rbx+818h], rax
0x14001ad41  lea     rax, [r14+rdi]
0x14001ad45  mov     [rbx+820h], rax
0x14001ad4c  mov     al, 1
0x14001ad4e  mov     [rbx+810h], rdi
0x14001ad55  jmp     short loc_14001AD5D
0x14001ad57  mov     byte ptr [rbx+8], 1
0x14001ad5b  xor     al, al
0x14001ad5d  mov     rbx, [rsp+38h+arg_8]
0x14001ad62  mov     rbp, [rsp+38h+arg_10]
0x14001ad67  add     rsp, 20h
0x14001ad6b  pop     r14
0x14001ad6d  pop     rdi
0x14001ad6e  pop     rsi
0x14001ad6f  retn
```
