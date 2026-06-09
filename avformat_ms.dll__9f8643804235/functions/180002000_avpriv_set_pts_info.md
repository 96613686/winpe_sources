# avpriv_set_pts_info

- ea: `0x180002000`
- end: `0x1800020e2`
- name: `avpriv_set_pts_info`
- size: `226`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013478`
- `0x180015324`
- `0x180016180`
- `0x180016310`
- `0x1800164c0`
- `0x180016590`
- `0x1800167b0`
- `0x1800168f0`
- `0x180016d90`
- `0x180017390`
- `0x1800174d0`
- `0x1800176a0`
- `0x1800179a0`
- `0x180018a74`
- `0x180018c60`
- `0x180019330`

## callees

- `0x180002000`
- `0x18001bb58`
- `0x18001bb64`

## string_xrefs

- `0x18000204b`: `st:%d removing common factor %d from timebase\n`
- `0x1800020b2`: `Ignoring attempt to set invalid timebase %d/%d for st:%d\n`

## pseudocode

```c
__int64 __fastcall avpriv_set_pts_info(__int64 a1, int a2, unsigned int a3, unsigned int a4)
{
  _DWORD *v5; // rbx
  __int64 v8; // r9
  __int64 result; // rax
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF

  v5 = (_DWORD *)(a1 + 8);
  if ( !(unsigned int)av_reduce(&v10, (char *)&v10 + 4, a3, a4, 0x7FFFFFFF) )
  {
    av_log(0, 24, "st:%d has too large timebase, reducing\n", *v5);
    goto LABEL_5;
  }
  v8 = v10;
  if ( (_DWORD)v10 != a3 )
  {
    av_log(0, 48, "st:%d removing common factor %d from timebase\n", *v5, a3 / (unsigned int)v10);
LABEL_5:
    v8 = v10;
  }
  if ( (int)v8 <= 0 || SHIDWORD(v10) <= 0 )
    return av_log(0, 16, "Ignoring attempt to set invalid timebase %d/%d for st:%d\n", v8, HIDWORD(v10), *v5);
  result = *(_QWORD *)(a1 + 248);
  *(_QWORD *)(a1 + 32) = v8;
  if ( result )
    *(_QWORD *)(result + 92) = v8;
  *(_DWORD *)(a1 + 212) = a2;
  return result;
}

```

## disassembly

```asm
0x180002000  mov     rax, rsp
0x180002003  mov     [rax+10h], rbx
0x180002007  mov     [rax+18h], rbp
0x18000200b  mov     [rax+20h], rsi
0x18000200f  push    rdi
0x180002010  sub     rsp, 30h
0x180002014  mov     esi, r8d
0x180002017  lea     rbx, [rcx+8]
0x18000201b  mov     ebp, edx
0x18000201d  mov     r8d, r8d
0x180002020  mov     rdi, rcx
0x180002023  mov     r9d, r9d
0x180002026  lea     rdx, [rax+0Ch]
0x18000202a  mov     qword ptr [rax-18h], 7FFFFFFFh
0x180002032  lea     rcx, [rax+8]
0x180002036  call    av_reduce
0x18000203b  test    eax, eax
0x18000203d  jz      short loc_18000206C
0x18000203f  mov     r9, [rsp+38h+arg_0]
0x180002044  cmp     r9d, esi
0x180002047  jz      short loc_180002087
0x180002049  xor     edx, edx
0x18000204b  lea     r8, aStDRemovingCom; "st:%d removing common factor %d from ti"...
0x180002052  mov     eax, esi
0x180002054  xor     ecx, ecx
0x180002056  div     r9d
0x180002059  mov     r9d, [rbx]
0x18000205c  mov     edx, 30h ; '0'
0x180002061  mov     [rsp+38h+var_18], eax
0x180002065  call    av_log
0x18000206a  jmp     short loc_180002082
0x18000206c  mov     r9d, [rbx]
0x18000206f  lea     r8, aStDHasTooLarge; "st:%d has too large timebase, reducing"...
0x180002076  mov     edx, 18h
0x18000207b  xor     ecx, ecx
0x18000207d  call    av_log
0x180002082  mov     r9, [rsp+38h+arg_0]
0x180002087  mov     ecx, dword ptr [rsp+38h+arg_0+4]
0x18000208b  test    r9d, r9d
0x18000208e  jle     short loc_1800020B0
0x180002090  test    ecx, ecx
0x180002092  jle     short loc_1800020B0
0x180002094  mov     rax, [rdi+0F8h]
0x18000209b  mov     [rdi+20h], r9
0x18000209f  test    rax, rax
0x1800020a2  jz      short loc_1800020A8
0x1800020a4  mov     [rax+5Ch], r9
0x1800020a8  mov     [rdi+0D4h], ebp
0x1800020ae  jmp     short loc_1800020CD
0x1800020b0  mov     eax, [rbx]
0x1800020b2  lea     r8, aIgnoringAttemp; "Ignoring attempt to set invalid timebas"...
0x1800020b9  mov     [rsp+38h+var_10], eax
0x1800020bd  mov     edx, 10h
0x1800020c2  mov     [rsp+38h+var_18], ecx
0x1800020c6  xor     ecx, ecx
0x1800020c8  call    av_log
0x1800020cd  mov     rbx, [rsp+38h+arg_8]
0x1800020d2  mov     rbp, [rsp+38h+arg_10]
0x1800020d7  mov     rsi, [rsp+38h+arg_18]
0x1800020dc  add     rsp, 30h
0x1800020e0  pop     rdi
0x1800020e1  retn
```
