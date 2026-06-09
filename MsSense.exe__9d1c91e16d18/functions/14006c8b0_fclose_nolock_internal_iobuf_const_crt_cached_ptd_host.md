# _fclose_nolock_internal(_iobuf * const,__crt_cached_ptd_host &)

- ea: `0x14006c8b0`
- end: `0x14006c955`
- name: `?_fclose_nolock_internal@@YAHQEAU_iobuf@@AEAV__crt_cached_ptd_host@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(FILE *File, struct __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14006c834`

## callees

- `0x14006147c`
- `0x14006c8b0`
- `0x14006cbd0`
- `0x140072280`
- `0x1400739d4`
- `0x140076094`
- `0x140076228`
- `0x140076244`

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
      if ( (int)sub_140076094(v6, a2) >= 0 )
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
    sub_14006147C(0, 0, 0, 0, 0, a2);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x14006c8b0  mov     rax, rsp
0x14006c8b3  mov     [rax+8], rbx
0x14006c8b7  mov     [rax+10h], rsi
0x14006c8bb  push    rdi
0x14006c8bc  sub     rsp, 30h
0x14006c8c0  mov     rdi, rdx
0x14006c8c3  mov     rbx, rcx
0x14006c8c6  test    rcx, rcx
0x14006c8c9  jnz     short loc_14006C8F0
0x14006c8cb  mov     [rax-10h], rdx
0x14006c8cf  xor     r9d, r9d; LineNo
0x14006c8d2  and     [rax-18h], rcx
0x14006c8d6  xor     r8d, r8d; FileName
0x14006c8d9  mov     byte ptr [rdx+30h], 1
0x14006c8dd  mov     dword ptr [rdx+2Ch], 16h
0x14006c8e4  xor     edx, edx; FunctionName
0x14006c8e6  call    sub_14006147C
0x14006c8eb  or      eax, 0FFFFFFFFh
0x14006c8ee  jmp     short loc_14006C945
0x14006c8f0  mov     eax, [rcx+14h]
0x14006c8f3  or      esi, 0FFFFFFFFh
0x14006c8f6  shr     eax, 0Dh
0x14006c8f9  nop
0x14006c8fa  test    al, 1
0x14006c8fc  jz      short loc_14006C93B
0x14006c8fe  call    __acrt_stdio_flush_nolock
0x14006c903  mov     rcx, rbx
0x14006c906  mov     esi, eax
0x14006c908  call    __acrt_stdio_free_buffer_nolock
0x14006c90d  mov     rcx, rbx; File
0x14006c910  call    _fileno
0x14006c915  mov     ecx, eax
0x14006c917  mov     rdx, rdi
0x14006c91a  call    sub_140076094
0x14006c91f  test    eax, eax
0x14006c921  jns     short loc_14006C928
0x14006c923  or      esi, 0FFFFFFFFh
0x14006c926  jmp     short loc_14006C93B
0x14006c928  mov     rcx, [rbx+28h]; Block
0x14006c92c  test    rcx, rcx
0x14006c92f  jz      short loc_14006C93B
0x14006c931  call    _free_base
0x14006c936  and     qword ptr [rbx+28h], 0
0x14006c93b  mov     rcx, rbx
0x14006c93e  call    ?__acrt_stdio_free_stream@@YAXV__crt_stdio_stream@@@Z
0x14006c943  mov     eax, esi
0x14006c945  mov     rbx, [rsp+38h+arg_0]
0x14006c94a  mov     rsi, [rsp+38h+arg_8]
0x14006c94f  add     rsp, 30h
0x14006c953  pop     rdi
0x14006c954  retn
```
