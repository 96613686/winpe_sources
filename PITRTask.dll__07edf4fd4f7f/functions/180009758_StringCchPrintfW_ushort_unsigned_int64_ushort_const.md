# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180009758`
- end: `0x1800097f8`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `160`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003eb0`
- `0x180004254`
- `0x180004bd4`
- `0x18000c750`

## callees

- `0x180009758`
- `0x1800107c0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800097a6`
- `msvcrt!_vsnwprintf` at `0x1800097a6`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned int v4; // edx
  unsigned __int64 v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v5 = a2 - 1;
      v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
      if ( v6 < 0 || v6 > v5 )
      {
        v4 = -2147024774;
        a1[v5] = 0;
      }
      else
      {
        v4 = 0;
        if ( v6 == v5 )
          a1[v5] = 0;
      }
    }
    else
    {
      v4 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x180009758  mov     [rsp+arg_10], r8
0x18000975d  mov     qword ptr [rsp+Args], r9
0x180009762  push    rbx
0x180009763  push    rdi
0x180009764  sub     rsp, 38h
0x180009768  mov     rax, cs:__security_cookie
0x18000976f  xor     rax, rsp
0x180009772  mov     [rsp+48h+var_20], rax
0x180009777  mov     rax, rdx
0x18000977a  mov     rdi, rcx
0x18000977d  test    rdx, rdx
0x180009780  jz      short loc_1800097D3
0x180009782  cmp     rax, 7FFFFFFFh
0x180009788  jbe     short loc_180009791
0x18000978a  mov     edx, 80070057h
0x18000978f  jmp     short loc_1800097DD
0x180009791  lea     rbx, [rdx-1]
0x180009795  mov     [rsp+48h+var_28], 0
0x18000979e  mov     rdx, rbx; BufferCount
0x1800097a1  lea     r9, [rsp+48h+Args]; Args
0x1800097a6  call    cs:__imp__vsnwprintf
0x1800097ac  test    eax, eax
0x1800097ae  js      short loc_1800097C6
0x1800097b0  cdqe
0x1800097b2  cmp     rax, rbx
0x1800097b5  ja      short loc_1800097C6
0x1800097b7  xor     edx, edx
0x1800097b9  cmp     rax, rbx
0x1800097bc  jnz     short loc_1800097E2
0x1800097be  xor     eax, eax
0x1800097c0  mov     [rdi+rbx*2], ax
0x1800097c4  jmp     short loc_1800097E2
0x1800097c6  xor     eax, eax
0x1800097c8  mov     edx, 8007007Ah
0x1800097cd  mov     [rdi+rbx*2], ax
0x1800097d1  jmp     short loc_1800097E2
0x1800097d3  mov     edx, 80070057h
0x1800097d8  test    rax, rax
0x1800097db  jz      short loc_1800097E2
0x1800097dd  xor     ecx, ecx
0x1800097df  mov     [rdi], cx
0x1800097e2  mov     eax, edx
0x1800097e4  mov     rcx, [rsp+48h+var_20]
0x1800097e9  xor     rcx, rsp; StackCookie
0x1800097ec  call    __security_check_cookie
0x1800097f1  add     rsp, 38h
0x1800097f5  pop     rdi
0x1800097f6  pop     rbx
0x1800097f7  retn
```
