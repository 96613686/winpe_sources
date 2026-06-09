# ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)

- ea: `0x180007274`
- end: `0x1800072f9`
- name: `?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z`
- size: `133`
- prototype: `void(ATL::Checked *__hidden this, void *, unsigned __int64, const void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000428c`
- `0x180004c3c`

## callees

- `0x180001e62`
- `0x180001eac`
- `0x180004e40`
- `0x180007274`
- `0x180009f88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007296`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800072dd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007296`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800072dd`

## pseudocode

```c
void __fastcall ATL::Checked::memcpy_s(ATL::Checked *this, void *a2, const void *a3, void *a4)
{
  if ( a4 )
  {
    if ( !this )
      goto LABEL_3;
    if ( !a3 || a2 < a4 )
    {
      memset_0(this, 0, (size_t)a2);
      if ( a3 )
      {
        if ( a2 >= a4 )
          goto LABEL_12;
        *(_DWORD *)_o__errno(this, a2, a3, a4) = 34;
LABEL_11:
        invalid_parameter_noinfo();
LABEL_12:
        ATL::AtlThrowImpl(-2147024809);
      }
LABEL_3:
      *(_DWORD *)_o__errno(this, a2, a3, a4) = 22;
      goto LABEL_11;
    }
    memcpy_0(this, a3, (size_t)a4);
  }
}

```

## disassembly

```asm
0x180007274  test    r9, r9
0x180007277  jz      short locret_1800072C8
0x180007279  mov     [rsp+arg_0], rbx
0x18000727e  mov     [rsp+arg_8], rsi
0x180007283  push    rdi
0x180007284  sub     rsp, 20h
0x180007288  mov     rbx, r9
0x18000728b  mov     rsi, r8
0x18000728e  mov     rdi, rdx
0x180007291  test    rcx, rcx
0x180007294  jnz     short loc_1800072A4
0x180007296  call    cs:__imp__o__errno
0x18000729c  mov     dword ptr [rax], 16h
0x1800072a2  jmp     short loc_1800072E9
0x1800072a4  test    rsi, rsi
0x1800072a7  jz      short loc_1800072C9
0x1800072a9  cmp     rdi, rbx
0x1800072ac  jb      short loc_1800072C9
0x1800072ae  mov     r8, rbx; Size
0x1800072b1  mov     rdx, rsi; Src
0x1800072b4  call    memcpy_0
0x1800072b9  mov     rbx, [rsp+28h+arg_0]
0x1800072be  mov     rsi, [rsp+28h+arg_8]
0x1800072c3  add     rsp, 20h
0x1800072c7  pop     rdi
0x1800072c8  retn
0x1800072c9  mov     r8, rdi; Size
0x1800072cc  xor     edx, edx; Val
0x1800072ce  call    memset_0
0x1800072d3  test    rsi, rsi
0x1800072d6  jz      short loc_180007296
0x1800072d8  cmp     rdi, rbx
0x1800072db  jnb     short loc_1800072EE
0x1800072dd  call    cs:__imp__o__errno
0x1800072e3  mov     dword ptr [rax], 22h ; '"'
0x1800072e9  call    _invalid_parameter_noinfo
0x1800072ee  mov     ecx, 80070057h; int
0x1800072f3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
