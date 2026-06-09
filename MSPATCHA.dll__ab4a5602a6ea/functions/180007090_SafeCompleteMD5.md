# SafeCompleteMD5

- ea: `0x180007090`
- end: `0x1800071d5`
- name: `SafeCompleteMD5`
- size: `325`
- prototype: `__int64 __fastcall(char *Src, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004180`

## callees

- `0x180001400`
- `0x180001cae`
- `0x180007090`
- `0x1800072b4`
- `0x180009061`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800071a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800071a1`

## pseudocode

```c
__int64 __fastcall SafeCompleteMD5(char *Src, unsigned int a2, _DWORD *a3)
{
  __int64 v5; // r12
  unsigned __int64 v6; // rdi
  char v7; // r15
  __int64 v9; // r15
  _OWORD v11[3]; // [rsp+40h] [rbp-78h] BYREF
  __int64 v12; // [rsp+70h] [rbp-48h]
  __int64 v13; // [rsp+78h] [rbp-40h]

  v5 = a2;
  v6 = (unsigned __int64)a2 >> 6;
  v7 = a2 & 0x3F;
  *a3 = 1732584193;
  a3[1] = -271733879;
  a3[2] = -1732584194;
  a3[3] = 271733878;
  while ( v6-- )
  {
    UpdateMD5_64ByteChunk(a3, Src);
    Src += 64;
  }
  v9 = v7 & 0x3F;
  memset_0(v11, 0, 0x40u);
  *((_BYTE *)v11 + v9) = 0x80;
  if ( (_DWORD)v9 )
  {
    memcpy_0(v11, Src, (unsigned int)v9);
    if ( (unsigned int)v9 >= 0x38 )
    {
      UpdateMD5_64ByteChunk(a3, v11);
      memset(v11, 0, sizeof(v11));
      v12 = 0;
    }
  }
  v13 = 8 * v5;
  UpdateMD5_64ByteChunk(a3, v11);
  return 1;
}

```

## disassembly

```asm
0x180007090  mov     [rsp+arg_18], rbx
0x180007095  push    rsi
0x180007096  push    rdi
0x180007097  push    r12
0x180007099  push    r14
0x18000709b  push    r15
0x18000709d  sub     rsp, 90h
0x1800070a4  mov     rax, cs:__security_cookie
0x1800070ab  xor     rax, rsp
0x1800070ae  mov     [rsp+0B8h+var_38], rax
0x1800070b6  mov     rbx, r8
0x1800070b9  mov     rsi, rcx
0x1800070bc  mov     r14d, 1
0x1800070c2  mov     r12d, edx
0x1800070c5  mov     [rsp+0B8h+var_88], r12
0x1800070ca  mov     [rsp+0B8h+var_90], rcx
0x1800070cf  mov     edi, edx
0x1800070d1  shr     rdi, 6
0x1800070d5  mov     [rsp+0B8h+var_98], rdi
0x1800070da  mov     r15d, edx
0x1800070dd  and     r15d, 3Fh
0x1800070e1  mov     dword ptr [r8], 67452301h
0x1800070e8  mov     dword ptr [r8+4], 0EFCDAB89h
0x1800070f0  mov     dword ptr [r8+8], 98BADCFEh
0x1800070f8  mov     dword ptr [r8+0Ch], 10325476h
0x180007100  mov     rax, rdi
0x180007103  sub     rdi, r14
0x180007106  mov     [rsp+0B8h+var_98], rdi
0x18000710b  test    rax, rax
0x18000710e  jz      short loc_180007126
0x180007110  mov     rdx, rsi
0x180007113  mov     rcx, rbx
0x180007116  call    UpdateMD5_64ByteChunk
0x18000711b  add     rsi, 40h ; '@'
0x18000711f  mov     [rsp+0B8h+var_90], rsi
0x180007124  jmp     short loc_180007100
0x180007126  and     r15d, 3Fh
0x18000712a  mov     edi, r15d
0x18000712d  xor     edx, edx; Val
0x18000712f  lea     r8d, [rdx+40h]; Size
0x180007133  lea     rcx, [rsp+0B8h+var_78]; void *
0x180007138  call    memset_0
0x18000713d  mov     byte ptr [rsp+r15+0B8h+var_78], 80h
0x180007143  test    r15d, r15d
0x180007146  jz      short loc_180007183
0x180007148  mov     r8d, edi; Size
0x18000714b  mov     rdx, rsi; Src
0x18000714e  lea     rcx, [rsp+0B8h+var_78]; void *
0x180007153  call    memcpy_0
0x180007158  cmp     edi, 38h ; '8'
0x18000715b  jb      short loc_180007183
0x18000715d  lea     rdx, [rsp+0B8h+var_78]
0x180007162  mov     rcx, rbx
0x180007165  call    UpdateMD5_64ByteChunk
0x18000716a  xorps   xmm0, xmm0
0x18000716d  xor     eax, eax
0x18000716f  movups  [rsp+0B8h+var_78], xmm0
0x180007174  movups  [rsp+0B8h+var_68], xmm0
0x180007179  movups  [rsp+0B8h+var_58], xmm0
0x18000717e  mov     [rsp+0B8h+var_48], rax
0x180007183  lea     rax, ds:0[r12*8]
0x18000718b  mov     [rsp+0B8h+var_40], rax
0x180007190  lea     rdx, [rsp+0B8h+var_78]
0x180007195  mov     rcx, rbx
0x180007198  call    UpdateMD5_64ByteChunk
0x18000719d  jmp     short loc_1800071AA
0x18000719f  mov     ecx, eax; dwErrCode
0x1800071a1  call    cs:__imp_SetLastError
0x1800071a7  xor     r14d, r14d
0x1800071aa  mov     eax, r14d
0x1800071ad  mov     rcx, [rsp+0B8h+var_38]
0x1800071b5  xor     rcx, rsp; StackCookie
0x1800071b8  call    __security_check_cookie
0x1800071bd  mov     rbx, [rsp+0B8h+arg_18]
0x1800071c5  add     rsp, 90h
0x1800071cc  pop     r15
0x1800071ce  pop     r14
0x1800071d0  pop     r12
0x1800071d2  pop     rdi
0x1800071d3  pop     rsi
0x1800071d4  retn
```
