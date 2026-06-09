# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180026fb0`
- end: `0x1800270a9`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `249`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `16`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d688`
- `0x18001d738`
- `0x18001e800`
- `0x18001e898`
- `0x18001e92c`
- `0x18001e9c0`
- `0x18001ea54`
- `0x18001eae4`
- `0x18001ffa0`
- `0x180026cb0`
- `0x180026f00`
- `0x1800270b0`
- `0x180027680`
- `0x180027c5c`
- `0x180028224`
- `0x180028438`

## callees

- `0x180006e3e`
- `0x180006ed4`
- `0x180007ecd`
- `0x180026fb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002702d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180027040`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002702d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180027040`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002706c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002706c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027064`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027064`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026fdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026fdc`

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
0x180026fb0  push    rbx
0x180026fb2  push    rbp
0x180026fb3  push    rsi
0x180026fb4  push    rdi
0x180026fb5  push    r14
0x180026fb7  push    r15
0x180026fb9  sub     rsp, 28h
0x180026fbd  mov     rax, [rcx+820h]
0x180026fc4  mov     rdi, rcx
0x180026fc7  sub     rax, [rcx+810h]
0x180026fce  cmp     rax, rdx
0x180026fd1  cmova   rdx, rax
0x180026fd5  lea     r14, [rdx+rdx]
0x180026fd9  mov     rcx, r14; cb
0x180026fdc  call    cs:__imp_CoTaskMemAlloc
0x180026fe2  mov     rbp, rax
0x180026fe5  test    rax, rax
0x180026fe8  jz      loc_180027096
0x180026fee  mov     rbx, [rdi+810h]
0x180026ff5  mov     rsi, [rdi+818h]
0x180026ffc  sub     rsi, rbx
0x180026fff  jz      short loc_180027051
0x180027001  test    rbx, rbx
0x180027004  jz      short loc_18002701B
0x180027006  cmp     r14, rsi
0x180027009  jb      short loc_18002701B
0x18002700b  mov     r8, rsi; Size
0x18002700e  mov     rdx, rbx; Src
0x180027011  mov     rcx, rax; void *
0x180027014  call    memcpy_0
0x180027019  jmp     short loc_180027051
0x18002701b  mov     r8, r14; Size
0x18002701e  xor     edx, edx; Val
0x180027020  mov     rcx, rbp; void *
0x180027023  call    memset_0
0x180027028  test    rbx, rbx
0x18002702b  jnz     short loc_18002703B
0x18002702d  call    cs:__imp__o__errno
0x180027033  mov     dword ptr [rax], 16h
0x180027039  jmp     short loc_18002704C
0x18002703b  cmp     r14, rsi
0x18002703e  jnb     short loc_180027051
0x180027040  call    cs:__imp__o__errno
0x180027046  mov     dword ptr [rax], 22h ; '"'
0x18002704c  call    _invalid_parameter_noinfo
0x180027051  mov     r15, [rdi]
0x180027054  test    r15, r15
0x180027057  jz      short loc_180027072
0x180027059  call    cs:__imp_GetLastError
0x18002705f  mov     rcx, r15; pv
0x180027062  mov     ebx, eax
0x180027064  call    cs:__imp_CoTaskMemFree
0x18002706a  mov     ecx, ebx; dwErrCode
0x18002706c  call    cs:__imp_SetLastError
0x180027072  mov     [rdi], rbp
0x180027075  lea     rax, [rsi+rbp]
0x180027079  mov     [rdi+818h], rax
0x180027080  lea     rax, [r14+rbp]
0x180027084  mov     [rdi+820h], rax
0x18002708b  mov     al, 1
0x18002708d  mov     [rdi+810h], rbp
0x180027094  jmp     short loc_18002709C
0x180027096  mov     byte ptr [rdi+8], 1
0x18002709a  xor     al, al
0x18002709c  add     rsp, 28h
0x1800270a0  pop     r15
0x1800270a2  pop     r14
0x1800270a4  pop     rdi
0x1800270a5  pop     rsi
0x1800270a6  pop     rbp
0x1800270a7  pop     rbx
0x1800270a8  retn
```
