# web::json::details::_String::_String(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180004a40`
- end: `0x180004b4e`
- name: `??0_String@details@json@web@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180004ce0`
- `0x180006b10`

## callees

- `0x180002cc0`
- `0x180004a40`

## pseudocode

```c
__int64 __fastcall web::json::details::_String::_String(__int64 a1, __int64 *a2)
{
  __int64 v2; // r8
  __int16 *v5; // rcx
  __int64 v6; // rax
  __int16 v7; // dx
  char v8; // al
  unsigned __int64 v9; // rdx
  __int64 v10; // rax
  unsigned __int64 v11; // rdx
  void *v12; // rcx
  __int64 result; // rax

  v2 = a1 + 8;
  *(_QWORD *)a1 = &web::json::details::_String::`vftable';
  *(_OWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_OWORD *)(a1 + 8) = *(_OWORD *)a2;
  *(_OWORD *)(a1 + 24) = *((_OWORD *)a2 + 1);
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  if ( *(_QWORD *)(a1 + 32) <= 7u )
  {
    v5 = (__int16 *)(a1 + 8);
    v6 = v2 + 2LL * *(_QWORD *)(v2 + 16);
  }
  else
  {
    v5 = *(__int16 **)v2;
    v6 = *(_QWORD *)v2 + 2LL * *(_QWORD *)(v2 + 16);
  }
  if ( v5 == (__int16 *)v6 )
  {
LABEL_9:
    v8 = 0;
  }
  else
  {
    while ( 1 )
    {
      v7 = *v5;
      if ( (unsigned __int16)*v5 <= 0x1Fu || v7 == 34 || v7 == 92 )
        break;
      if ( ++v5 == (__int16 *)v6 )
        goto LABEL_9;
    }
    v8 = 1;
  }
  *(_BYTE *)(a1 + 40) = v8;
  v9 = a2[3];
  if ( v9 > 7 )
  {
    v10 = *a2;
    v11 = 2 * v9 + 2;
    if ( v11 < 0x1000 )
    {
      v12 = (void *)*a2;
    }
    else
    {
      v12 = *(void **)(v10 - 8);
      if ( (unsigned __int64)(v10 - (_QWORD)v12 - 8) > 0x1F )
        __fastfail(5u);
      v11 += 39LL;
    }
    operator delete(v12, v11);
  }
  a2[2] = 0;
  result = a1;
  *(_WORD *)a2 = 0;
  a2[3] = 7;
  return result;
}

```

## disassembly

```asm
0x180004a40  mov     [rsp+arg_10], rbx
0x180004a45  mov     [rsp+arg_18], rsi
0x180004a4a  push    rdi
0x180004a4b  sub     rsp, 30h
0x180004a4f  lea     r8, [rcx+8]
0x180004a53  mov     [rsp+38h+var_18], rcx
0x180004a58  xor     esi, esi
0x180004a5a  mov     [rsp+38h+var_18], rdx
0x180004a5f  xorps   xmm0, xmm0
0x180004a62  lea     rax, ??_7_String@details@json@web@@6B@; const web::json::details::_String::`vftable'
0x180004a69  mov     [rcx], rax
0x180004a6c  mov     rbx, rdx
0x180004a6f  movups  xmmword ptr [r8], xmm0
0x180004a73  mov     [r8+10h], rsi
0x180004a77  mov     rdi, rcx
0x180004a7a  mov     [r8+18h], rsi
0x180004a7e  movups  xmm0, xmmword ptr [rdx]
0x180004a81  movups  xmmword ptr [r8], xmm0
0x180004a85  movups  xmm1, xmmword ptr [rdx+10h]
0x180004a89  movups  xmmword ptr [r8+10h], xmm1
0x180004a8e  mov     [rdx+10h], rsi
0x180004a92  mov     qword ptr [rdx+18h], 7
0x180004a9a  mov     [rdx], si
0x180004a9d  cmp     qword ptr [r8+18h], 7
0x180004aa2  jbe     short loc_180004AB1
0x180004aa4  mov     rcx, [r8]
0x180004aa7  mov     rdx, [r8+10h]
0x180004aab  lea     rax, [rcx+rdx*2]
0x180004aaf  jmp     short loc_180004ABC
0x180004ab1  mov     rax, [r8+10h]
0x180004ab5  mov     rcx, r8
0x180004ab8  lea     rax, [r8+rax*2]
0x180004abc  cmp     rcx, rax
0x180004abf  jz      short loc_180004ADF
0x180004ac1  movzx   edx, word ptr [rcx]
0x180004ac4  cmp     dx, 1Fh
0x180004ac8  jbe     short loc_180004B19
0x180004aca  cmp     dx, 22h ; '"'
0x180004ace  jz      short loc_180004B19
0x180004ad0  cmp     dx, 5Ch ; '\'
0x180004ad4  jz      short loc_180004B19
0x180004ad6  add     rcx, 2
0x180004ada  cmp     rcx, rax
0x180004add  jnz     short loc_180004AC1
0x180004adf  xor     al, al
0x180004ae1  mov     [rdi+28h], al
0x180004ae4  mov     rdx, [rbx+18h]
0x180004ae8  cmp     rdx, 7
0x180004aec  jbe     short loc_180004B2C
0x180004aee  mov     rax, [rbx]
0x180004af1  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180004af9  cmp     rdx, 1000h
0x180004b00  jb      short loc_180004B24
0x180004b02  mov     rcx, [rax-8]
0x180004b06  sub     rax, rcx
0x180004b09  sub     rax, 8
0x180004b0d  cmp     rax, 1Fh
0x180004b11  ja      short loc_180004B1D
0x180004b13  add     rdx, 27h ; '''
0x180004b17  jmp     short loc_180004B27
0x180004b19  mov     al, 1
0x180004b1b  jmp     short loc_180004AE1
0x180004b1d  mov     ecx, 5
0x180004b22  int     29h; Win8: RtlFailFast(ecx)
0x180004b24  mov     rcx, rax; void *
0x180004b27  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004b2c  mov     [rbx+10h], rsi
0x180004b30  mov     rax, rdi
0x180004b33  mov     [rbx], si
0x180004b36  mov     rsi, [rsp+38h+arg_18]
0x180004b3b  mov     qword ptr [rbx+18h], 7
0x180004b43  mov     rbx, [rsp+38h+arg_10]
0x180004b48  add     rsp, 30h
0x180004b4c  pop     rdi
0x180004b4d  retn
```
