# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18007db9c`
- end: `0x18007dcb5`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `281`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `13`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180071fd0`
- `0x1800732dc`
- `0x18007360c`
- `0x180073818`
- `0x180073c08`
- `0x180073f08`
- `0x1800741bc`
- `0x18007c8e0`
- `0x18007d984`
- `0x18007dcbc`
- `0x18007e2d0`
- `0x18007ed50`
- `0x18007ef64`

## callees

- `0x180003b2a`
- `0x180003b66`
- `0x180003c64`
- `0x18000693e`
- `0x18007db9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dc52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dc52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007dc71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007dc71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007dc63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007dc63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007dbd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007dbd1`

## pseudocode

```c
char __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  size_t v3; // r14
  char *v4; // rax
  char *v5; // rbp
  __int64 v6; // rbx
  size_t v7; // rsi
  __int64 v8; // rcx
  void *v9; // r15
  DWORD LastError; // ebx

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
        *(_DWORD *)o__errno_0(v8) = 34;
      }
      else
      {
        *(_DWORD *)o__errno_0(v8) = 22;
      }
      invalid_parameter_noinfo();
      goto LABEL_13;
    }
    memcpy_0(v4, *((const void **)this + 258), v7);
  }
LABEL_13:
  v9 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    CoTaskMemFree(v9);
    SetLastError(LastError);
  }
  *(_QWORD *)this = v5;
  *((_QWORD *)this + 258) = v5;
  *((_QWORD *)this + 259) = &v5[v7];
  *((_QWORD *)this + 260) = &v5[v3];
  return 1;
}

```

## disassembly

```asm
0x18007db9c  push    rbx
0x18007db9e  push    rbp
0x18007db9f  push    rsi
0x18007dba0  push    rdi
0x18007dba1  push    r14
0x18007dba3  push    r15
0x18007dba5  sub     rsp, 38h
0x18007dba9  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x18007dbb2  mov     rdi, rcx
0x18007dbb5  mov     rax, [rcx+820h]
0x18007dbbc  sub     rax, [rcx+810h]
0x18007dbc3  cmp     rax, rdx
0x18007dbc6  cmova   rdx, rax
0x18007dbca  lea     r14, [rdx+rdx]
0x18007dbce  mov     rcx, r14; cb
0x18007dbd1  call    cs:__imp_CoTaskMemAlloc
0x18007dbd8  nop     dword ptr [rax+rax+00h]
0x18007dbdd  mov     rbp, rax
0x18007dbe0  test    rax, rax
0x18007dbe3  jz      loc_18007DCA1
0x18007dbe9  mov     rbx, [rdi+810h]
0x18007dbf0  mov     rsi, [rdi+818h]
0x18007dbf7  sub     rsi, rbx
0x18007dbfa  jz      short loc_18007DC4A
0x18007dbfc  test    rbx, rbx
0x18007dbff  jz      short loc_18007DC16
0x18007dc01  cmp     r14, rsi
0x18007dc04  jb      short loc_18007DC16
0x18007dc06  mov     r8, rsi; Size
0x18007dc09  mov     rdx, rbx; Src
0x18007dc0c  mov     rcx, rax; void *
0x18007dc0f  call    memcpy_0
0x18007dc14  jmp     short loc_18007DC4A
0x18007dc16  mov     r8, r14; Size
0x18007dc19  xor     edx, edx; Val
0x18007dc1b  mov     rcx, rbp; void *
0x18007dc1e  call    memset_0
0x18007dc23  test    rbx, rbx
0x18007dc26  jnz     short loc_18007DC35
0x18007dc28  call    _o__errno_0
0x18007dc2d  mov     dword ptr [rax], 16h
0x18007dc33  jmp     short loc_18007DC45
0x18007dc35  cmp     r14, rsi
0x18007dc38  jnb     short loc_18007DC4A
0x18007dc3a  call    _o__errno_0
0x18007dc3f  mov     dword ptr [rax], 22h ; '"'
0x18007dc45  call    _invalid_parameter_noinfo
0x18007dc4a  mov     r15, [rdi]
0x18007dc4d  test    r15, r15
0x18007dc50  jz      short loc_18007DC7D
0x18007dc52  call    cs:__imp_GetLastError
0x18007dc59  nop     dword ptr [rax+rax+00h]
0x18007dc5e  mov     ebx, eax
0x18007dc60  mov     rcx, r15; pv
0x18007dc63  call    cs:__imp_CoTaskMemFree
0x18007dc6a  nop     dword ptr [rax+rax+00h]
0x18007dc6f  mov     ecx, ebx; dwErrCode
0x18007dc71  call    cs:__imp_SetLastError
0x18007dc78  nop     dword ptr [rax+rax+00h]
0x18007dc7d  mov     [rdi], rbp
0x18007dc80  mov     [rdi+810h], rbp
0x18007dc87  lea     rax, [rsi+rbp]
0x18007dc8b  mov     [rdi+818h], rax
0x18007dc92  lea     rax, [r14+rbp]
0x18007dc96  mov     [rdi+820h], rax
0x18007dc9d  mov     al, 1
0x18007dc9f  jmp     short loc_18007DCA7
0x18007dca1  mov     byte ptr [rdi+8], 1
0x18007dca5  xor     al, al
0x18007dca7  add     rsp, 38h
0x18007dcab  pop     r15
0x18007dcad  pop     r14
0x18007dcaf  pop     rdi
0x18007dcb0  pop     rsi
0x18007dcb1  pop     rbp
0x18007dcb2  pop     rbx
0x18007dcb3  retn
```
