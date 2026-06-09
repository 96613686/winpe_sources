# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x1800272e4`
- end: `0x1800273de`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `250`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `13`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018aac`
- `0x180019360`
- `0x1800193f8`
- `0x18001948c`
- `0x18001951c`
- `0x180019f20`
- `0x180026964`
- `0x180026d00`
- `0x1800273e4`
- `0x180027a80`
- `0x180027e30`
- `0x180028374`
- `0x180028588`

## callees

- `0x180002db8`
- `0x180003345`
- `0x1800272e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180027380`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180027380`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180027361`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180027374`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180027361`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180027374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002738e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002738e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800273a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800273a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027310`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027310`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027399`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027399`

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
      _invalid_parameter_noinfo();
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
0x1800272e4  push    rbx
0x1800272e6  push    rbp
0x1800272e7  push    rsi
0x1800272e8  push    rdi
0x1800272e9  push    r14
0x1800272eb  push    r15
0x1800272ed  sub     rsp, 28h
0x1800272f1  mov     rax, [rcx+820h]
0x1800272f8  mov     rdi, rcx
0x1800272fb  sub     rax, [rcx+810h]
0x180027302  cmp     rax, rdx
0x180027305  cmova   rdx, rax
0x180027309  lea     r14, [rdx+rdx]
0x18002730d  mov     rcx, r14; cb
0x180027310  call    cs:__imp_CoTaskMemAlloc
0x180027316  mov     rbp, rax
0x180027319  test    rax, rax
0x18002731c  jz      loc_1800273CB
0x180027322  mov     rbx, [rdi+810h]
0x180027329  mov     rsi, [rdi+818h]
0x180027330  sub     rsi, rbx
0x180027333  jz      short loc_180027386
0x180027335  test    rbx, rbx
0x180027338  jz      short loc_18002734F
0x18002733a  cmp     r14, rsi
0x18002733d  jb      short loc_18002734F
0x18002733f  mov     r8, rsi; Size
0x180027342  mov     rdx, rbx; Src
0x180027345  mov     rcx, rax; void *
0x180027348  call    memcpy_0
0x18002734d  jmp     short loc_180027386
0x18002734f  mov     r8, r14; Size
0x180027352  xor     edx, edx; Val
0x180027354  mov     rcx, rbp; void *
0x180027357  call    memset_0
0x18002735c  test    rbx, rbx
0x18002735f  jnz     short loc_18002736F
0x180027361  call    cs:__imp__o__errno
0x180027367  mov     dword ptr [rax], 16h
0x18002736d  jmp     short loc_180027380
0x18002736f  cmp     r14, rsi
0x180027372  jnb     short loc_180027386
0x180027374  call    cs:__imp__o__errno
0x18002737a  mov     dword ptr [rax], 22h ; '"'
0x180027380  call    cs:__imp__invalid_parameter_noinfo
0x180027386  mov     r15, [rdi]
0x180027389  test    r15, r15
0x18002738c  jz      short loc_1800273A7
0x18002738e  call    cs:__imp_GetLastError
0x180027394  mov     rcx, r15; pv
0x180027397  mov     ebx, eax
0x180027399  call    cs:__imp_CoTaskMemFree
0x18002739f  mov     ecx, ebx; dwErrCode
0x1800273a1  call    cs:__imp_SetLastError
0x1800273a7  mov     [rdi], rbp
0x1800273aa  lea     rax, [rsi+rbp]
0x1800273ae  mov     [rdi+818h], rax
0x1800273b5  lea     rax, [r14+rbp]
0x1800273b9  mov     [rdi+820h], rax
0x1800273c0  mov     al, 1
0x1800273c2  mov     [rdi+810h], rbp
0x1800273c9  jmp     short loc_1800273D1
0x1800273cb  mov     byte ptr [rdi+8], 1
0x1800273cf  xor     al, al
0x1800273d1  add     rsp, 28h
0x1800273d5  pop     r15
0x1800273d7  pop     r14
0x1800273d9  pop     rdi
0x1800273da  pop     rsi
0x1800273db  pop     rbp
0x1800273dc  pop     rbx
0x1800273dd  retn
```
