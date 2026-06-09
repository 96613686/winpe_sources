# CopyStringToOutputParameter(ushort const *,ushort * *)

- ea: `0x14003cdec`
- end: `0x14003ce7e`
- name: `?CopyStringToOutputParameter@@YAJPEBGPEAPEAG@Z`
- size: `146`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14003cfe0`
- `0x14003dde0`

## callees

- `0x1400058d0`
- `0x14000a6b4`
- `0x14003cdec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14003ce68`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14003ce68`

## string_xrefs

- `0x14003ce0f`: `avcore\midi2\service\exe\midisrvrpc.cpp`

## pseudocode

```c
__int64 __fastcall CopyStringToOutputParameter(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v7; // rax
  __int64 v8; // rsi
  unsigned __int16 *v9; // rax
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 36;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
      (const char *)v4,
      v10);
    return v4;
  }
  if ( a1 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a1[v7] );
    v8 = v7 + 1;
    if ( v7 != -1 )
    {
      v9 = (unsigned __int16 *)operator new[](2 * v8, (const struct std::nothrow_t *)&std::nothrow);
      *a2 = v9;
      if ( !v9 )
      {
        v4 = -2147024882;
        v5 = 48;
        goto LABEL_3;
      }
      _o_wcscpy_s(v9, v8, a1);
    }
  }
  else
  {
    *a2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14003cdec  push    rbx
0x14003cdee  push    rbp
0x14003cdef  push    rsi
0x14003cdf0  push    rdi
0x14003cdf1  sub     rsp, 28h
0x14003cdf5  xor     ebp, ebp
0x14003cdf7  mov     rbx, rdx
0x14003cdfa  mov     rdi, rcx
0x14003cdfd  test    rdx, rdx
0x14003ce00  jnz     short loc_14003CE22
0x14003ce02  mov     ebx, 80070057h
0x14003ce07  lea     edx, [rbp+24h]; void *
0x14003ce0a  mov     rcx, [rsp+48h]; this
0x14003ce0f  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003ce16  mov     r9d, ebx; char *
0x14003ce19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003ce1e  mov     eax, ebx
0x14003ce20  jmp     short loc_14003CE75
0x14003ce22  test    rdi, rdi
0x14003ce25  jz      short loc_14003CE70
0x14003ce27  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003ce2b  inc     rax
0x14003ce2e  cmp     [rcx+rax*2], bp
0x14003ce32  jnz     short loc_14003CE2B
0x14003ce34  lea     rsi, [rax+1]
0x14003ce38  test    rsi, rsi
0x14003ce3b  jz      short loc_14003CE73
0x14003ce3d  lea     rcx, [rsi+rsi]; unsigned __int64
0x14003ce41  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003ce48  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14003ce4d  mov     [rbx], rax
0x14003ce50  test    rax, rax
0x14003ce53  jnz     short loc_14003CE5F
0x14003ce55  mov     ebx, 8007000Eh
0x14003ce5a  lea     edx, [rax+30h]
0x14003ce5d  jmp     short loc_14003CE0A
0x14003ce5f  mov     r8, rdi
0x14003ce62  mov     rdx, rsi
0x14003ce65  mov     rcx, rax
0x14003ce68  call    cs:__imp__o_wcscpy_s
0x14003ce6e  jmp     short loc_14003CE73
0x14003ce70  mov     [rdx], rbp
0x14003ce73  xor     eax, eax
0x14003ce75  add     rsp, 28h
0x14003ce79  pop     rdi
0x14003ce7a  pop     rsi
0x14003ce7b  pop     rbp
0x14003ce7c  pop     rbx
0x14003ce7d  retn
```
