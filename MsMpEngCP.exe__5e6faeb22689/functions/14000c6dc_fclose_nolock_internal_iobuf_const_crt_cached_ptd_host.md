# _fclose_nolock_internal(_iobuf * const,__crt_cached_ptd_host &)

- ea: `0x14000c6dc`
- end: `0x14000c781`
- name: `?_fclose_nolock_internal@@YAHQEAU_iobuf@@AEAV__crt_cached_ptd_host@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(FILE *Stream, struct __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000c660`

## callees

- `0x14000648c`
- `0x140006940`
- `0x14000a0d0`
- `0x14000aa1c`
- `0x14000c3ac`
- `0x14000c6dc`
- `0x14000c9d4`
- `0x14000cb68`

## pseudocode

```c
__int64 __fastcall _fclose_nolock_internal(FILE *Stream, struct __crt_cached_ptd_host *a2)
{
  unsigned int v5; // esi
  unsigned int v6; // eax
  char *tmpfname; // rcx

  if ( Stream )
  {
    v5 = -1;
    if ( (HIDWORD(Stream->_base) & 0x2000) != 0 )
    {
      v5 = _acrt_stdio_flush_nolock(Stream);
      _acrt_stdio_free_buffer_nolock(Stream);
      v6 = fileno(Stream);
      if ( (int)sub_14000C9D4(v6, a2) >= 0 )
      {
        tmpfname = Stream->_tmpfname;
        if ( tmpfname )
        {
          free_base(tmpfname);
          Stream->_tmpfname = 0;
        }
      }
      else
      {
        v5 = -1;
      }
    }
    __acrt_stdio_free_stream(Stream);
    return v5;
  }
  else
  {
    *((_BYTE *)a2 + 48) = 1;
    *((_DWORD *)a2 + 11) = 22;
    sub_14000648C(0, 0, 0, 0, 0, a2);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x14000c6dc  mov     rax, rsp
0x14000c6df  mov     [rax+8], rbx
0x14000c6e3  mov     [rax+10h], rsi
0x14000c6e7  push    rdi
0x14000c6e8  sub     rsp, 30h
0x14000c6ec  mov     rdi, rdx
0x14000c6ef  mov     rbx, rcx
0x14000c6f2  test    rcx, rcx
0x14000c6f5  jnz     short loc_14000C71C
0x14000c6f7  mov     [rax-10h], rdx
0x14000c6fb  xor     r9d, r9d; LineNo
0x14000c6fe  and     [rax-18h], rcx
0x14000c702  xor     r8d, r8d; FileName
0x14000c705  mov     byte ptr [rdx+30h], 1
0x14000c709  mov     dword ptr [rdx+2Ch], 16h
0x14000c710  xor     edx, edx; FunctionName
0x14000c712  call    sub_14000648C
0x14000c717  or      eax, 0FFFFFFFFh
0x14000c71a  jmp     short loc_14000C771
0x14000c71c  mov     eax, [rcx+14h]
0x14000c71f  or      esi, 0FFFFFFFFh
0x14000c722  shr     eax, 0Dh
0x14000c725  nop
0x14000c726  test    al, 1
0x14000c728  jz      short loc_14000C767
0x14000c72a  call    __acrt_stdio_flush_nolock
0x14000c72f  mov     rcx, rbx
0x14000c732  mov     esi, eax
0x14000c734  call    __acrt_stdio_free_buffer_nolock
0x14000c739  mov     rcx, rbx; Stream
0x14000c73c  call    _fileno
0x14000c741  mov     ecx, eax
0x14000c743  mov     rdx, rdi
0x14000c746  call    sub_14000C9D4
0x14000c74b  test    eax, eax
0x14000c74d  jns     short loc_14000C754
0x14000c74f  or      esi, 0FFFFFFFFh
0x14000c752  jmp     short loc_14000C767
0x14000c754  mov     rcx, [rbx+28h]; Block
0x14000c758  test    rcx, rcx
0x14000c75b  jz      short loc_14000C767
0x14000c75d  call    _free_base
0x14000c762  and     qword ptr [rbx+28h], 0
0x14000c767  mov     rcx, rbx
0x14000c76a  call    ?__acrt_stdio_free_stream@@YAXV__crt_stdio_stream@@@Z
0x14000c76f  mov     eax, esi
0x14000c771  mov     rbx, [rsp+38h+arg_0]
0x14000c776  mov     rsi, [rsp+38h+arg_8]
0x14000c77b  add     rsp, 30h
0x14000c77f  pop     rdi
0x14000c780  retn
```
