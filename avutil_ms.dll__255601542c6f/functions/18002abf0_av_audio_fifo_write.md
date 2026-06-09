# av_audio_fifo_write

- ea: `0x18002abf0`
- end: `0x18002acbe`
- name: `av_audio_fifo_write`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002aad0`
- `0x18002abf0`
- `0x180039e20`

## pseudocode

```c
__int64 __fastcall av_audio_fifo_write(__int64 a1, __int64 a2, signed int a3)
{
  _DWORD *v4; // r14
  int v5; // ecx
  __int64 result; // rax
  int v9; // ebp
  _DWORD *v10; // rdx
  __int64 v11; // r15
  __int64 v12; // rsi

  v4 = (_DWORD *)(a1 + 12);
  v5 = *(_DWORD *)(a1 + 12);
  if ( *(_DWORD *)(a1 + 16) - v5 >= a3 )
    goto LABEL_6;
  if ( 0x3FFFFFFF - v5 < a3 )
    return 4294967274LL;
  _mm_lfence();
  result = av_audio_fifo_realloc(a1, (unsigned int)(2 * (v5 + a3)));
  if ( (int)result >= 0 )
  {
LABEL_6:
    v9 = 0;
    v10 = v4;
    if ( *(int *)(a1 + 8) <= 0 )
    {
LABEL_11:
      result = (unsigned int)a3;
      *v10 = a3 + *v4;
    }
    else
    {
      v11 = *(_DWORD *)(a1 + 28) * a3;
      v12 = 0;
      while ( (int)av_fifo_write(*(_QWORD *)(*(_QWORD *)a1 + v12), *(_QWORD *)(v12 + a2), v11) >= 0 )
      {
        ++v9;
        v12 += 8;
        if ( v9 >= *(_DWORD *)(a1 + 8) )
        {
          v10 = (_DWORD *)(a1 + 12);
          goto LABEL_11;
        }
      }
      return 3736644286LL;
    }
  }
  else
  {
    _mm_lfence();
  }
  return result;
}

```

## disassembly

```asm
0x18002abf0  mov     rax, rsp
0x18002abf3  mov     [rax+8], rbx
0x18002abf7  mov     [rax+10h], rbp
0x18002abfb  mov     [rax+18h], rsi
0x18002abff  mov     [rax+20h], rdi
0x18002ac03  push    r12
0x18002ac05  push    r14
0x18002ac07  push    r15
0x18002ac09  sub     rsp, 20h
0x18002ac0d  mov     rbx, rcx
0x18002ac10  lea     r14, [rcx+0Ch]
0x18002ac14  mov     ecx, [r14]
0x18002ac17  mov     edi, r8d
0x18002ac1a  mov     r12, rdx
0x18002ac1d  mov     eax, [rbx+10h]
0x18002ac20  sub     eax, ecx
0x18002ac22  cmp     eax, r8d
0x18002ac25  jge     short loc_18002AC54
0x18002ac27  mov     eax, 3FFFFFFFh
0x18002ac2c  sub     eax, ecx
0x18002ac2e  cmp     eax, r8d
0x18002ac31  jge     short loc_18002AC3A
0x18002ac33  mov     eax, 0FFFFFFEAh
0x18002ac38  jmp     short loc_18002AC98
0x18002ac3a  lfence
0x18002ac3d  lea     edx, [rcx+r8]
0x18002ac41  mov     rcx, rbx
0x18002ac44  add     edx, edx
0x18002ac46  call    av_audio_fifo_realloc
0x18002ac4b  test    eax, eax
0x18002ac4d  jns     short loc_18002AC54
0x18002ac4f  lfence
0x18002ac52  jmp     short loc_18002AC98
0x18002ac54  mov     eax, edi
0x18002ac56  xor     ebp, ebp
0x18002ac58  imul    eax, [rbx+1Ch]
0x18002ac5c  mov     rdx, r14
0x18002ac5f  cmp     [rbx+8], ebp
0x18002ac62  jle     short loc_18002AC8F
0x18002ac64  movsxd  r15, eax
0x18002ac67  xor     esi, esi
0x18002ac69  mov     rcx, [rbx]
0x18002ac6c  mov     r8, r15
0x18002ac6f  mov     rdx, [rsi+r12]
0x18002ac73  mov     rcx, [rcx+rsi]
0x18002ac77  call    av_fifo_write
0x18002ac7c  test    eax, eax
0x18002ac7e  js      short loc_18002ACB7
0x18002ac80  inc     ebp
0x18002ac82  add     rsi, 8
0x18002ac86  cmp     ebp, [rbx+8]
0x18002ac89  jl      short loc_18002AC69
0x18002ac8b  lea     rdx, [rbx+0Ch]
0x18002ac8f  mov     ecx, [r14]
0x18002ac92  mov     eax, edi
0x18002ac94  add     ecx, edi
0x18002ac96  mov     [rdx], ecx
0x18002ac98  mov     rbx, [rsp+38h+arg_0]
0x18002ac9d  mov     rbp, [rsp+38h+arg_8]
0x18002aca2  mov     rsi, [rsp+38h+arg_10]
0x18002aca7  mov     rdi, [rsp+38h+arg_18]
0x18002acac  add     rsp, 20h
0x18002acb0  pop     r15
0x18002acb2  pop     r14
0x18002acb4  pop     r12
0x18002acb6  retn
0x18002acb7  mov     eax, 0DEB8AABEh
0x18002acbc  jmp     short loc_18002AC98
```
