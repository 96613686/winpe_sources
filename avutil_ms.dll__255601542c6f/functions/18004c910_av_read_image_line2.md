# av_read_image_line2

- ea: `0x18004c910`
- end: `0x18004cb8f`
- name: `av_read_image_line2`
- size: `639`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004c8c0`

## callees

- `0x18004c910`
- `0x180078c32`

## pseudocode

```c
unsigned __int64 __fastcall av_read_image_line2(
        _WORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10)
{
  _WORD *v10; // r14
  int v12; // r12d
  int *v13; // r15
  int v14; // ebp
  unsigned __int64 v15; // rdx
  unsigned __int64 result; // rax
  int v17; // r13d
  unsigned __int64 v18; // r10
  unsigned int *v19; // rsi
  int i; // ebx
  int v21; // r9d
  int v22; // ecx
  unsigned __int8 *v23; // r8
  int v24; // ebx
  int v25; // edx
  int v26; // ebx
  __int64 v27; // rax
  int v28; // ebp
  unsigned int *v29; // rdi
  int v30; // esi
  __int64 v31; // r13
  unsigned int v32; // eax
  __int128 v33; // [rsp+20h] [rbp-58h]
  unsigned __int64 v34; // [rsp+80h] [rbp+8h]
  int v36; // [rsp+98h] [rbp+20h]

  v10 = a1;
  v12 = *(_DWORD *)(a4 + 16);
  v13 = (int *)a1;
  v14 = *(_DWORD *)(a4 + 20LL * a7 + 40);
  v15 = *(_QWORD *)(a4 + 20LL * a7 + 32);
  result = *(_QWORD *)(a4 + 20LL * a7 + 24);
  v17 = (1LL << v14) - 1;
  v18 = HIDWORD(result);
  v36 = v17;
  v34 = HIDWORD(v15);
  v33 = *(_OWORD *)(a4 + 20LL * a7 + 24);
  if ( v14 )
  {
    result = (int)result;
    v19 = (unsigned int *)(*(_QWORD *)(a2 + 8LL * (int)result) + *(_DWORD *)(a3 + 4LL * (int)result) * a6);
    if ( (v12 & 4) != 0 )
    {
      if ( (int)v18 <= 8 )
      {
        v21 = a8;
        v22 = v15 + a5 * v18;
        v23 = (unsigned __int8 *)v19 + ((__int64)v22 >> 3);
        v24 = 8 - (v22 & 7) - v14;
        while ( v21 )
        {
          --v21;
          v25 = v17 & (*v23 >> v24);
          if ( a9 )
            v25 = *(unsigned __int8 *)(a7 + 4 * v25 + *(_QWORD *)(a2 + 8));
          v26 = v24 - v18;
          v27 = v26;
          v24 = v26 & 7;
          result = v27 >> 3;
          v23 -= result;
          if ( a10 == 4 )
            *v13++ = v25;
          else
            *v10++ = v25;
        }
      }
      else
      {
        for ( i = a8; i; ++v19 )
        {
          --i;
          result = v17 & (unsigned int)((int)byteswap_ulong(*v19) >> SBYTE8(v33));
          if ( a9 )
            result = *(unsigned __int8 *)(a7 + 4 * (int)result + *(_QWORD *)(a2 + 8));
          if ( a10 == 4 )
            *v13++ = result;
          else
            *v10++ = result;
        }
      }
    }
    else
    {
      v28 = HIDWORD(v15) + v14;
      result = (unsigned __int64)v19 + a5 * (int)v18;
      v29 = (unsigned int *)(result + (int)v15);
      if ( v28 <= 8 )
      {
        result = v12 & 1;
        v29 = (unsigned int *)((char *)v29 + result);
      }
      v30 = a8;
      if ( a8 )
      {
        v31 = (int)v18;
        do
        {
          --v30;
          if ( v28 > 8 )
          {
            if ( v28 > 16 )
            {
              v32 = *v29;
              if ( (v12 & 1) != 0 )
                v32 = byteswap_ulong(v32);
            }
            else
            {
              LOWORD(v32) = *(_WORD *)v29;
              if ( (v12 & 1) != 0 )
                LOWORD(v32) = __ROR2__(v32, 8);
              v32 = (unsigned __int16)v32;
            }
          }
          else
          {
            v32 = *(unsigned __int8 *)v29;
          }
          result = v36 & (v32 >> v34);
          if ( a9 )
            result = *(unsigned __int8 *)((unsigned int)(a7 + 4 * result) + *(_QWORD *)(a2 + 8));
          v29 = (unsigned int *)((char *)v29 + v31);
          if ( a10 == 4 )
            *v13++ = result;
          else
            *v10++ = result;
        }
        while ( v30 );
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004c910  mov     [rsp+arg_10], rbx
0x18004c915  mov     [rsp+arg_8], rdx
0x18004c91a  push    rbp
0x18004c91b  push    rsi
0x18004c91c  push    rdi
0x18004c91d  push    r12
0x18004c91f  push    r13
0x18004c921  push    r14
0x18004c923  push    r15
0x18004c925  sub     rsp, 40h
0x18004c929  movsxd  rax, [rsp+78h+arg_30]
0x18004c931  mov     r14, rcx
0x18004c934  mov     r11d, [rsp+78h+arg_28]
0x18004c93c  mov     rdi, rdx
0x18004c93f  mov     r12d, [r9+10h]
0x18004c943  mov     r13d, 1
0x18004c949  mov     r15, r14
0x18004c94c  lea     r10, [rax+rax*4]
0x18004c950  movups  xmm1, xmmword ptr [r9+r10*4+18h]
0x18004c956  mov     ebp, [r9+r10*4+28h]
0x18004c95b  mov     ecx, ebp
0x18004c95d  mov     rdx, [r9+r10*4+20h]
0x18004c962  shl     r13, cl
0x18004c965  movq    rax, xmm1
0x18004c96a  dec     r13d
0x18004c96d  mov     r10, rax
0x18004c970  mov     rbx, rdx
0x18004c973  shr     r10, 20h
0x18004c977  shr     rbx, 20h
0x18004c97b  mov     [rsp+78h+arg_18], r13
0x18004c983  mov     [rsp+78h+arg_0], rbx
0x18004c98b  movups  [rsp+78h+var_58], xmm1
0x18004c990  test    ebp, ebp
0x18004c992  jz      loc_18004CB77
0x18004c998  cdqe
0x18004c99a  imul    r11d, [r8+rax*4]
0x18004c99f  movsxd  rsi, r11d
0x18004c9a2  add     rsi, [rdi+rax*8]
0x18004c9a6  test    r12b, 4
0x18004c9aa  jz      loc_18004CAAE
0x18004c9b0  mov     ebx, 8
0x18004c9b5  cmp     r10d, ebx
0x18004c9b8  jle     short loc_18004CA24
0x18004c9ba  mov     ebx, [rsp+78h+arg_38]
0x18004c9c1  test    ebx, ebx
0x18004c9c3  jz      loc_18004CB77
0x18004c9c9  mov     r12d, [rsp+78h+arg_30]
0x18004c9d1  mov     ecx, [rsi]; Number
0x18004c9d3  dec     ebx
0x18004c9d5  call    _byteswap_ulong
0x18004c9da  mov     ecx, dword ptr [rsp+78h+var_58+8]
0x18004c9de  sar     eax, cl
0x18004c9e0  and     eax, r13d
0x18004c9e3  cmp     [rsp+78h+arg_40], 0
0x18004c9eb  jz      short loc_18004C9FC
0x18004c9ed  lea     eax, [r12+rax*4]
0x18004c9f1  movsxd  rcx, eax
0x18004c9f4  mov     rax, [rdi+8]
0x18004c9f8  movzx   eax, byte ptr [rcx+rax]
0x18004c9fc  cmp     [rsp+78h+arg_48], 4
0x18004ca04  jnz     short loc_18004CA0F
0x18004ca06  mov     [r15], eax
0x18004ca09  add     r15, 4
0x18004ca0d  jmp     short loc_18004CA17
0x18004ca0f  mov     [r14], ax
0x18004ca13  add     r14, 2
0x18004ca17  add     rsi, 4
0x18004ca1b  test    ebx, ebx
0x18004ca1d  jnz     short loc_18004C9D1
0x18004ca1f  jmp     loc_18004CB77
0x18004ca24  mov     r9d, [rsp+78h+arg_38]
0x18004ca2c  mov     ecx, r10d
0x18004ca2f  imul    ecx, [rsp+78h+arg_20]
0x18004ca37  add     ecx, edx
0x18004ca39  movsxd  r8, ecx
0x18004ca3c  and     ecx, 7
0x18004ca3f  sar     r8, 3
0x18004ca43  sub     ebx, ecx
0x18004ca45  add     r8, rsi
0x18004ca48  sub     ebx, ebp
0x18004ca4a  jmp     short loc_18004CAA4
0x18004ca4c  movzx   edx, byte ptr [r8]
0x18004ca50  mov     cl, bl
0x18004ca52  shr     edx, cl
0x18004ca54  dec     r9d
0x18004ca57  and     edx, r13d
0x18004ca5a  cmp     [rsp+78h+arg_40], 0
0x18004ca62  jz      short loc_18004CA79
0x18004ca64  mov     eax, [rsp+78h+arg_30]
0x18004ca6b  lea     eax, [rax+rdx*4]
0x18004ca6e  movsxd  rcx, eax
0x18004ca71  mov     rax, [rdi+8]
0x18004ca75  movzx   edx, byte ptr [rcx+rax]
0x18004ca79  sub     ebx, r10d
0x18004ca7c  movsxd  rax, ebx
0x18004ca7f  and     ebx, 7
0x18004ca82  sar     rax, 3
0x18004ca86  sub     r8, rax
0x18004ca89  cmp     [rsp+78h+arg_48], 4
0x18004ca91  jnz     short loc_18004CA9C
0x18004ca93  mov     [r15], edx
0x18004ca96  add     r15, 4
0x18004ca9a  jmp     short loc_18004CAA4
0x18004ca9c  mov     [r14], dx
0x18004caa0  add     r14, 2
0x18004caa4  test    r9d, r9d
0x18004caa7  jnz     short loc_18004CA4C
0x18004caa9  jmp     loc_18004CB77
0x18004caae  mov     eax, r10d
0x18004cab1  movsxd  rdi, edx
0x18004cab4  imul    eax, [rsp+78h+arg_20]
0x18004cabc  add     ebp, ebx
0x18004cabe  mov     ebx, 8
0x18004cac3  cdqe
0x18004cac5  add     rax, rsi
0x18004cac8  add     rdi, rax
0x18004cacb  cmp     ebp, ebx
0x18004cacd  jg      short loc_18004CAD8
0x18004cacf  mov     eax, r12d
0x18004cad2  and     eax, 1
0x18004cad5  add     rdi, rax
0x18004cad8  mov     esi, [rsp+78h+arg_38]
0x18004cadf  test    esi, esi
0x18004cae1  jz      loc_18004CB77
0x18004cae7  movsxd  r13, r10d
0x18004caea  dec     esi
0x18004caec  cmp     ebp, ebx
0x18004caee  jg      short loc_18004CAF5
0x18004caf0  movzx   eax, byte ptr [rdi]
0x18004caf3  jmp     short loc_18004CB1D
0x18004caf5  mov     ecx, r12d
0x18004caf8  and     ecx, 1
0x18004cafb  cmp     ebp, 10h
0x18004cafe  jg      short loc_18004CB10
0x18004cb00  movzx   eax, word ptr [rdi]
0x18004cb03  test    ecx, ecx
0x18004cb05  jz      short loc_18004CB0B
0x18004cb07  ror     ax, 8
0x18004cb0b  movzx   eax, ax
0x18004cb0e  jmp     short loc_18004CB1D
0x18004cb10  mov     eax, [rdi]
0x18004cb12  test    ecx, ecx
0x18004cb14  jz      short loc_18004CB1D
0x18004cb16  mov     ecx, eax; Number
0x18004cb18  call    _byteswap_ulong
0x18004cb1d  mov     ecx, dword ptr [rsp+78h+arg_0]
0x18004cb24  shr     eax, cl
0x18004cb26  and     eax, dword ptr [rsp+78h+arg_18]
0x18004cb2d  cmp     [rsp+78h+arg_40], 0
0x18004cb35  jz      short loc_18004CB51
0x18004cb37  mov     ecx, [rsp+78h+arg_30]
0x18004cb3e  lea     ecx, [rcx+rax*4]
0x18004cb41  mov     rax, [rsp+78h+arg_8]
0x18004cb49  mov     rax, [rax+8]
0x18004cb4d  movzx   eax, byte ptr [rcx+rax]
0x18004cb51  add     rdi, r13
0x18004cb54  cmp     [rsp+78h+arg_48], 4
0x18004cb5c  jnz     short loc_18004CB67
0x18004cb5e  mov     [r15], eax
0x18004cb61  add     r15, 4
0x18004cb65  jmp     short loc_18004CB6F
0x18004cb67  mov     [r14], ax
0x18004cb6b  add     r14, 2
0x18004cb6f  test    esi, esi
0x18004cb71  jnz     loc_18004CAEA
0x18004cb77  mov     rbx, [rsp+78h+arg_10]
0x18004cb7f  add     rsp, 40h
0x18004cb83  pop     r15
0x18004cb85  pop     r14
0x18004cb87  pop     r13
0x18004cb89  pop     r12
0x18004cb8b  pop     rdi
0x18004cb8c  pop     rsi
0x18004cb8d  pop     rbp
0x18004cb8e  retn
```
