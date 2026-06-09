# TracePrintW(uchar,char const *,ulong,ushort const *,...)

- ea: `0x18000789c`
- end: `0x18000796f`
- name: `?TracePrintW@@YAXEPEBDKPEBGZZ`
- size: `211`
- prototype: `void(PPTraceStatus *, const char *, unsigned int, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180006304`
- `0x1800066d4`
- `0x180006a78`

## callees

- `0x180001cd4`
- `0x180001d04`
- `0x180002908`
- `0x180007600`
- `0x18000789c`
- `0x180007978`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180007934`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180007934`

## pseudocode

```c
void TracePrintW(PPTraceStatus *a1, const char *a2, unsigned int a3, const unsigned __int16 *a4, ...)
{
  const char *v5; // rdi
  char v6; // si
  __int64 v7; // r9
  wchar_t *v8; // rax
  wchar_t *v9; // rbx
  __int64 v10; // rdx
  char *v11; // rax
  va_list Args; // [rsp+90h] [rbp+28h] BYREF

  va_start(Args, a4);
  v5 = a2;
  v6 = (char)a1;
  if ( PPTraceStatus::TraceOnFlag(a1, (unsigned __int8)a2) )
  {
    if ( v7 )
    {
      v8 = (wchar_t *)operator new[](0x800u, (const struct std::nothrow_t *)&std::nothrow);
      v9 = v8;
      if ( v8 )
      {
        if ( (unsigned int)vsnwprintf(v8, 0x3FFu, a4, Args) > 0x3FE )
          v9[1023] = 0;
        if ( *v9 )
        {
          if ( v5 )
          {
            v11 = strrchr(v5, 92);
            if ( v11 )
              v5 = v11 + 1;
          }
          else
          {
            v5 = (const char *)&byte_18000DE48;
          }
          LOBYTE(v10) = v6;
          TraceStringW((unsigned int)dword_1800134CC, v10, v5, a3, v9);
        }
        operator delete(v9);
      }
    }
  }
}

```

## disassembly

```asm
0x18000789c  mov     [rsp+Format], r9
0x1800078a1  push    rbx
0x1800078a2  push    rbp
0x1800078a3  push    rsi
0x1800078a4  push    rdi
0x1800078a5  push    r14
0x1800078a7  sub     rsp, 40h
0x1800078ab  mov     ebp, r8d
0x1800078ae  mov     rdi, rdx
0x1800078b1  mov     sil, cl
0x1800078b4  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x1800078b9  xor     r14d, r14d
0x1800078bc  test    al, al
0x1800078be  jz      loc_180007964
0x1800078c4  test    r9, r9
0x1800078c7  jz      loc_180007964
0x1800078cd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800078d4  mov     ecx, 800h; unsigned __int64
0x1800078d9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800078de  mov     rbx, rax
0x1800078e1  test    rax, rax
0x1800078e4  jz      short loc_180007964
0x1800078e6  mov     r8, [rsp+68h+Format]; Format
0x1800078ee  lea     r9, [rsp+68h+Args]; Args
0x1800078f6  mov     edx, 3FFh; BufferCount
0x1800078fb  mov     rcx, rax; Buffer
0x1800078fe  call    _vsnwprintf
0x180007903  test    eax, eax
0x180007905  js      short loc_180007910
0x180007907  cmp     eax, 3FFh
0x18000790c  ja      short loc_180007910
0x18000790e  jnz     short loc_180007918
0x180007910  mov     [rbx+7FEh], r14w
0x180007918  cmp     [rbx], r14w
0x18000791c  jz      short loc_18000795C
0x18000791e  test    rdi, rdi
0x180007921  jnz     short loc_18000792C
0x180007923  lea     rdi, byte_18000DE48
0x18000792a  jmp     short loc_180007943
0x18000792c  mov     edx, 5Ch ; '\'; Ch
0x180007931  mov     rcx, rdi; Str
0x180007934  call    cs:__imp_strrchr
0x18000793a  test    rax, rax
0x18000793d  jz      short loc_180007943
0x18000793f  lea     rdi, [rax+1]
0x180007943  mov     ecx, cs:dword_1800134CC
0x180007949  mov     r9d, ebp
0x18000794c  mov     r8, rdi
0x18000794f  mov     [rsp+68h+var_48], rbx
0x180007954  mov     dl, sil
0x180007957  call    ?TraceStringW@@YAXW4MSATRACE_MODULE@@EPEBDKPEBG@Z; TraceStringW(MSATRACE_MODULE,uchar,char const *,ulong,ushort const *)
0x18000795c  mov     rcx, rbx; void *
0x18000795f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007964  add     rsp, 40h
0x180007968  pop     r14
0x18000796a  pop     rdi
0x18000796b  pop     rsi
0x18000796c  pop     rbp
0x18000796d  pop     rbx
0x18000796e  retn
```
