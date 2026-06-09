# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180017ed0`
- end: `0x180017fc9`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `249`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `14`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800117dc`
- `0x18001188c`
- `0x180012490`
- `0x180012528`
- `0x1800125bc`
- `0x18001264c`
- `0x1800133c4`
- `0x180017840`
- `0x180017cd0`
- `0x180017fd0`
- `0x1800185f0`
- `0x180018ba0`
- `0x180019120`
- `0x180019334`

## callees

- `0x180003f02`
- `0x180003fa0`
- `0x180003fb8`
- `0x180017ed0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017f4d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017f60`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017f4d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017f60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017f8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017f8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017efc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017efc`

## pseudocode

```c
bool __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  size_t v3; // r14
  char *v4; // rax
  char *v5; // rbp
  __int64 v6; // rbx
  size_t v7; // rsi
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  void *v11; // r15
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
  v6 = *((_QWORD *)this + 258);
  v7 = *((_QWORD *)this + 259) - v6;
  if ( v7 )
  {
    if ( !v6 || v3 < v7 )
    {
      memset_0(v4, 0, v3);
      if ( v6 )
      {
        if ( v3 >= v7 )
          goto LABEL_13;
        *(_DWORD *)_o__errno(v9, v8, v10) = 34;
      }
      else
      {
        *(_DWORD *)_o__errno(v9, v8, v10) = 22;
      }
      invalid_parameter_noinfo();
      goto LABEL_13;
    }
    memcpy_0(v4, *((const void **)this + 258), v7);
  }
LABEL_13:
  v11 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    CoTaskMemFree(v11);
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
0x180017ed0  push    rbx
0x180017ed2  push    rbp
0x180017ed3  push    rsi
0x180017ed4  push    rdi
0x180017ed5  push    r14
0x180017ed7  push    r15
0x180017ed9  sub     rsp, 28h
0x180017edd  mov     rax, [rcx+820h]
0x180017ee4  mov     rdi, rcx
0x180017ee7  sub     rax, [rcx+810h]
0x180017eee  cmp     rax, rdx
0x180017ef1  cmova   rdx, rax
0x180017ef5  lea     r14, [rdx+rdx]
0x180017ef9  mov     rcx, r14; cb
0x180017efc  call    cs:__imp_CoTaskMemAlloc
0x180017f02  mov     rbp, rax
0x180017f05  test    rax, rax
0x180017f08  jz      loc_180017FB6
0x180017f0e  mov     rbx, [rdi+810h]
0x180017f15  mov     rsi, [rdi+818h]
0x180017f1c  sub     rsi, rbx
0x180017f1f  jz      short loc_180017F71
0x180017f21  test    rbx, rbx
0x180017f24  jz      short loc_180017F3B
0x180017f26  cmp     r14, rsi
0x180017f29  jb      short loc_180017F3B
0x180017f2b  mov     r8, rsi; Size
0x180017f2e  mov     rdx, rbx; Src
0x180017f31  mov     rcx, rax; void *
0x180017f34  call    memcpy_0
0x180017f39  jmp     short loc_180017F71
0x180017f3b  mov     r8, r14; Size
0x180017f3e  xor     edx, edx; Val
0x180017f40  mov     rcx, rbp; void *
0x180017f43  call    memset_0
0x180017f48  test    rbx, rbx
0x180017f4b  jnz     short loc_180017F5B
0x180017f4d  call    cs:__imp__o__errno
0x180017f53  mov     dword ptr [rax], 16h
0x180017f59  jmp     short loc_180017F6C
0x180017f5b  cmp     r14, rsi
0x180017f5e  jnb     short loc_180017F71
0x180017f60  call    cs:__imp__o__errno
0x180017f66  mov     dword ptr [rax], 22h ; '"'
0x180017f6c  call    _invalid_parameter_noinfo
0x180017f71  mov     r15, [rdi]
0x180017f74  test    r15, r15
0x180017f77  jz      short loc_180017F92
0x180017f79  call    cs:__imp_GetLastError
0x180017f7f  mov     rcx, r15; pv
0x180017f82  mov     ebx, eax
0x180017f84  call    cs:__imp_CoTaskMemFree
0x180017f8a  mov     ecx, ebx; dwErrCode
0x180017f8c  call    cs:__imp_SetLastError
0x180017f92  mov     [rdi], rbp
0x180017f95  lea     rax, [rsi+rbp]
0x180017f99  mov     [rdi+818h], rax
0x180017fa0  lea     rax, [r14+rbp]
0x180017fa4  mov     [rdi+820h], rax
0x180017fab  mov     al, 1
0x180017fad  mov     [rdi+810h], rbp
0x180017fb4  jmp     short loc_180017FBC
0x180017fb6  mov     byte ptr [rdi+8], 1
0x180017fba  xor     al, al
0x180017fbc  add     rsp, 28h
0x180017fc0  pop     r15
0x180017fc2  pop     r14
0x180017fc4  pop     rdi
0x180017fc5  pop     rsi
0x180017fc6  pop     rbp
0x180017fc7  pop     rbx
0x180017fc8  retn
```
