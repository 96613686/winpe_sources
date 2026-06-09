# _fclose_nolock_internal(_iobuf * const,__crt_cached_ptd_host &)

- ea: `0x140016780`
- end: `0x140016825`
- name: `?_fclose_nolock_internal@@YAHQEAU_iobuf@@AEAV__crt_cached_ptd_host@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(FILE *File, struct __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140016704`

## callees

- `0x140015fe4`
- `0x140016780`
- `0x140019930`
- `0x14001b044`
- `0x14001bb8c`
- `0x14001be10`
- `0x14001bf18`
- `0x14001c13c`

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
      if ( (int)sub_14001BB8C(v6, a2) >= 0 )
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
    sub_140015FE4(0, 0, 0, 0, 0, a2);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x140016780  mov     rax, rsp
0x140016783  mov     [rax+8], rbx
0x140016787  mov     [rax+10h], rsi
0x14001678b  push    rdi
0x14001678c  sub     rsp, 30h
0x140016790  mov     rdi, rdx
0x140016793  mov     rbx, rcx
0x140016796  test    rcx, rcx
0x140016799  jnz     short loc_1400167C0
0x14001679b  mov     [rax-10h], rdx
0x14001679f  xor     r9d, r9d; LineNo
0x1400167a2  and     [rax-18h], rcx
0x1400167a6  xor     r8d, r8d; FileName
0x1400167a9  mov     byte ptr [rdx+30h], 1
0x1400167ad  mov     dword ptr [rdx+2Ch], 16h
0x1400167b4  xor     edx, edx; FunctionName
0x1400167b6  call    sub_140015FE4
0x1400167bb  or      eax, 0FFFFFFFFh
0x1400167be  jmp     short loc_140016815
0x1400167c0  mov     eax, [rcx+14h]
0x1400167c3  or      esi, 0FFFFFFFFh
0x1400167c6  shr     eax, 0Dh
0x1400167c9  nop
0x1400167ca  test    al, 1
0x1400167cc  jz      short loc_14001680B
0x1400167ce  call    __acrt_stdio_flush_nolock
0x1400167d3  mov     rcx, rbx
0x1400167d6  mov     esi, eax
0x1400167d8  call    __acrt_stdio_free_buffer_nolock
0x1400167dd  mov     rcx, rbx; File
0x1400167e0  call    _fileno
0x1400167e5  mov     ecx, eax
0x1400167e7  mov     rdx, rdi
0x1400167ea  call    sub_14001BB8C
0x1400167ef  test    eax, eax
0x1400167f1  jns     short loc_1400167F8
0x1400167f3  or      esi, 0FFFFFFFFh
0x1400167f6  jmp     short loc_14001680B
0x1400167f8  mov     rcx, [rbx+28h]; Block
0x1400167fc  test    rcx, rcx
0x1400167ff  jz      short loc_14001680B
0x140016801  call    _free_base
0x140016806  and     qword ptr [rbx+28h], 0
0x14001680b  mov     rcx, rbx
0x14001680e  call    ?__acrt_stdio_free_stream@@YAXV__crt_stdio_stream@@@Z
0x140016813  mov     eax, esi
0x140016815  mov     rbx, [rsp+38h+arg_0]
0x14001681a  mov     rsi, [rsp+38h+arg_8]
0x14001681f  add     rsp, 30h
0x140016823  pop     rdi
0x140016824  retn
```
