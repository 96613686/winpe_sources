# _fclose_nolock_internal(_iobuf * const,__crt_cached_ptd_host &)

- ea: `0x140018f98`
- end: `0x14001903d`
- name: `?_fclose_nolock_internal@@YAHQEAU_iobuf@@AEAV__crt_cached_ptd_host@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(FILE *File, struct __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140018f1c`

## callees

- `0x140004614`
- `0x1400107c4`
- `0x140011a0c`
- `0x140015aac`
- `0x140015c14`
- `0x140018f98`
- `0x14001a9e8`
- `0x14001ac6c`

## pseudocode

```c
__int64 __fastcall _fclose_nolock_internal(FILE *File, struct __crt_cached_ptd_host *a2)
{
  unsigned int v5; // esi
  unsigned int v6; // eax
  char *tmpfname; // rcx

  if ( File )
  {
    v5 = -1;
    if ( (HIDWORD(File->_base) & 0x2000) != 0 )
    {
      v5 = _acrt_stdio_flush_nolock(File);
      _acrt_stdio_free_buffer_nolock(File);
      v6 = fileno(File);
      if ( (int)sub_14001A9E8(v6, a2) >= 0 )
      {
        tmpfname = File->_tmpfname;
        if ( tmpfname )
        {
          free_base(tmpfname);
          File->_tmpfname = 0;
        }
      }
      else
      {
        v5 = -1;
      }
    }
    __acrt_stdio_free_stream(File);
    return v5;
  }
  else
  {
    *((_BYTE *)a2 + 48) = 1;
    *((_DWORD *)a2 + 11) = 22;
    sub_140004614(0, 0, 0, 0, 0, a2);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x140018f98  mov     rax, rsp
0x140018f9b  mov     [rax+8], rbx
0x140018f9f  mov     [rax+10h], rsi
0x140018fa3  push    rdi
0x140018fa4  sub     rsp, 30h
0x140018fa8  mov     rdi, rdx
0x140018fab  mov     rbx, rcx
0x140018fae  test    rcx, rcx
0x140018fb1  jnz     short loc_140018FD8
0x140018fb3  mov     [rax-10h], rdx
0x140018fb7  xor     r9d, r9d; LineNo
0x140018fba  and     [rax-18h], rcx
0x140018fbe  xor     r8d, r8d; FileName
0x140018fc1  mov     byte ptr [rdx+30h], 1
0x140018fc5  mov     dword ptr [rdx+2Ch], 16h
0x140018fcc  xor     edx, edx; FunctionName
0x140018fce  call    sub_140004614
0x140018fd3  or      eax, 0FFFFFFFFh
0x140018fd6  jmp     short loc_14001902D
0x140018fd8  mov     eax, [rcx+14h]
0x140018fdb  or      esi, 0FFFFFFFFh
0x140018fde  shr     eax, 0Dh
0x140018fe1  nop
0x140018fe2  test    al, 1
0x140018fe4  jz      short loc_140019023
0x140018fe6  call    __acrt_stdio_flush_nolock
0x140018feb  mov     rcx, rbx
0x140018fee  mov     esi, eax
0x140018ff0  call    __acrt_stdio_free_buffer_nolock
0x140018ff5  mov     rcx, rbx; File
0x140018ff8  call    _fileno
0x140018ffd  mov     ecx, eax
0x140018fff  mov     rdx, rdi
0x140019002  call    sub_14001A9E8
0x140019007  test    eax, eax
0x140019009  jns     short loc_140019010
0x14001900b  or      esi, 0FFFFFFFFh
0x14001900e  jmp     short loc_140019023
0x140019010  mov     rcx, [rbx+28h]; Block
0x140019014  test    rcx, rcx
0x140019017  jz      short loc_140019023
0x140019019  call    _free_base
0x14001901e  and     qword ptr [rbx+28h], 0
0x140019023  mov     rcx, rbx
0x140019026  call    ?__acrt_stdio_free_stream@@YAXV__crt_stdio_stream@@@Z
0x14001902b  mov     eax, esi
0x14001902d  mov     rbx, [rsp+38h+arg_0]
0x140019032  mov     rsi, [rsp+38h+arg_8]
0x140019037  add     rsp, 30h
0x14001903b  pop     rdi
0x14001903c  retn
```
