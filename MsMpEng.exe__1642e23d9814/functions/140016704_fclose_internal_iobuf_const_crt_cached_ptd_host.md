# _fclose_internal(_iobuf * const,__crt_cached_ptd_host &)

- ea: `0x140016704`
- end: `0x14001677e`
- name: `?_fclose_internal@@YAHQEAU_iobuf@@AEAV__crt_cached_ptd_host@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(FILE *File, struct __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140016828`

## callees

- `0x140015fe4`
- `0x140016704`
- `0x140016780`
- `0x14001b1ec`
- `0x14001b1f8`
- `0x14001be10`

## pseudocode

```c
__int64 __fastcall _fclose_internal(FILE *File, struct __crt_cached_ptd_host *a2)
{
  unsigned int v5; // edi

  if ( !File )
  {
    *((_BYTE *)a2 + 48) = 1;
    *((_DWORD *)a2 + 11) = 22;
    sub_140015FE4(0, 0, 0, 0, 0, a2);
    return 0xFFFFFFFFLL;
  }
  if ( (HIDWORD(File->_base) & 0x1000) != 0 )
  {
    __acrt_stdio_free_stream(File);
    return 0xFFFFFFFFLL;
  }
  lock_file(File);
  v5 = _fclose_nolock_internal(File, a2);
  unlock_file(File);
  return v5;
}

```

## disassembly

```asm
0x140016704  mov     rax, rsp
0x140016707  mov     [rax+10h], rbx
0x14001670b  mov     [rax+8], rcx
0x14001670f  push    rdi
0x140016710  sub     rsp, 30h
0x140016714  mov     rdi, rdx
0x140016717  mov     rbx, rcx
0x14001671a  test    rcx, rcx
0x14001671d  jnz     short loc_14001674D
0x14001671f  mov     byte ptr [rdx+30h], 1
0x140016723  mov     dword ptr [rdx+2Ch], 16h
0x14001672a  mov     [rax-10h], rdx
0x14001672e  and     [rax-18h], rcx
0x140016732  xor     r9d, r9d; LineNo
0x140016735  xor     r8d, r8d; FileName
0x140016738  xor     edx, edx; FunctionName
0x14001673a  call    sub_140015FE4
0x14001673f  or      eax, 0FFFFFFFFh
0x140016742  mov     rbx, [rsp+38h+arg_8]
0x140016747  add     rsp, 30h
0x14001674b  pop     rdi
0x14001674c  retn
0x14001674d  mov     eax, [rcx+14h]
0x140016750  nop
0x140016751  shr     eax, 0Ch
0x140016754  and     al, 1
0x140016756  jz      short loc_14001675F
0x140016758  call    ?__acrt_stdio_free_stream@@YAXV__crt_stdio_stream@@@Z
0x14001675d  jmp     short loc_14001673F
0x14001675f  call    _lock_file
0x140016764  nop
0x140016765  mov     rdx, rdi; struct __crt_cached_ptd_host *
0x140016768  mov     rcx, rbx; File
0x14001676b  call    ?_fclose_nolock_internal@@YAHQEAU_iobuf@@AEAV__crt_cached_ptd_host@@@Z
0x140016770  mov     edi, eax
0x140016772  mov     rcx, rbx; File
0x140016775  call    _unlock_file
0x14001677a  mov     eax, edi
0x14001677c  jmp     short loc_140016742
0x14002b092  push    rbp; Microsoft VisualC 64bit universal runtime
0x14002b094  sub     rsp, 30h
0x14002b098  mov     rbp, rdx
0x14002b09b  mov     rcx, [rbp+40h]; File
0x14002b09f  add     rsp, 30h
0x14002b0a3  pop     rbp
0x14002b0a4  jmp     _unlock_file
```
