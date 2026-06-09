# _fclose_internal(_iobuf * const,__crt_cached_ptd_host &)

- ea: `0x14000c660`
- end: `0x14000c6da`
- name: `?_fclose_internal@@YAHQEAU_iobuf@@AEAV__crt_cached_ptd_host@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(FILE *Stream, struct __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000c784`

## callees

- `0x14000648c`
- `0x14000a3bc`
- `0x14000a3c8`
- `0x14000c660`
- `0x14000c6dc`
- `0x14000cb68`

## pseudocode

```c
__int64 __fastcall _fclose_internal(FILE *Stream, struct __crt_cached_ptd_host *a2)
{
  unsigned int v5; // edi

  if ( !Stream )
  {
    *((_BYTE *)a2 + 48) = 1;
    *((_DWORD *)a2 + 11) = 22;
    sub_14000648C(0, 0, 0, 0, 0, a2);
    return 0xFFFFFFFFLL;
  }
  if ( (HIDWORD(Stream->_base) & 0x1000) != 0 )
  {
    __acrt_stdio_free_stream(Stream);
    return 0xFFFFFFFFLL;
  }
  sub_14000A3BC();
  v5 = _fclose_nolock_internal(Stream, a2);
  sub_14000A3C8(Stream);
  return v5;
}

```

## disassembly

```asm
0x14000c660  mov     rax, rsp
0x14000c663  mov     [rax+10h], rbx
0x14000c667  mov     [rax+8], rcx
0x14000c66b  push    rdi
0x14000c66c  sub     rsp, 30h
0x14000c670  mov     rdi, rdx
0x14000c673  mov     rbx, rcx
0x14000c676  test    rcx, rcx
0x14000c679  jnz     short loc_14000C6A9
0x14000c67b  mov     byte ptr [rdx+30h], 1
0x14000c67f  mov     dword ptr [rdx+2Ch], 16h
0x14000c686  mov     [rax-10h], rdx
0x14000c68a  and     [rax-18h], rcx
0x14000c68e  xor     r9d, r9d; LineNo
0x14000c691  xor     r8d, r8d; FileName
0x14000c694  xor     edx, edx; FunctionName
0x14000c696  call    sub_14000648C
0x14000c69b  or      eax, 0FFFFFFFFh
0x14000c69e  mov     rbx, [rsp+38h+arg_8]
0x14000c6a3  add     rsp, 30h
0x14000c6a7  pop     rdi
0x14000c6a8  retn
0x14000c6a9  mov     eax, [rcx+14h]
0x14000c6ac  nop
0x14000c6ad  shr     eax, 0Ch
0x14000c6b0  and     al, 1
0x14000c6b2  jz      short loc_14000C6BB
0x14000c6b4  call    ?__acrt_stdio_free_stream@@YAXV__crt_stdio_stream@@@Z
0x14000c6b9  jmp     short loc_14000C69B
0x14000c6bb  call    sub_14000A3BC
0x14000c6c0  nop
0x14000c6c1  mov     rdx, rdi; struct __crt_cached_ptd_host *
0x14000c6c4  mov     rcx, rbx; Stream
0x14000c6c7  call    ?_fclose_nolock_internal@@YAHQEAU_iobuf@@AEAV__crt_cached_ptd_host@@@Z
0x14000c6cc  mov     edi, eax
0x14000c6ce  mov     rcx, rbx
0x14000c6d1  call    sub_14000A3C8
0x14000c6d6  mov     eax, edi
0x14000c6d8  jmp     short loc_14000C69E
0x14000e04f  push    rbp; Microsoft VisualC 64bit universal runtime
0x14000e051  sub     rsp, 30h
0x14000e055  mov     rbp, rdx
0x14000e058  mov     rcx, [rbp+40h]
0x14000e05c  add     rsp, 30h
0x14000e060  pop     rbp
0x14000e061  jmp     sub_14000A3C8
```
