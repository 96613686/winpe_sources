# avcodec_default_get_buffer2

- ea: `0x18000c5c0`
- end: `0x18000c6ed`
- name: `avcodec_default_get_buffer2`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x18000c3e8`
- `0x18000c5c0`
- `0x18000c720`
- `0x18000ca24`
- `0x18002269e`
- `0x180022704`
- `0x1800228c4`

## string_xrefs

- `0x18000c659`: `Consider setting extra_hw_frames to a larger value (currently set to %d, giving a pool size of %d).\n`

## pseudocode

```c
__int64 __fastcall avcodec_default_get_buffer2(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  unsigned int buffer; // r14d
  _DWORD *v6; // r15
  unsigned int v7; // ebx
  const char *pix_fmt_name; // rdi
  const char *v9; // rax
  __int64 result; // rax
  int v11; // ecx

  v4 = *(_QWORD *)(a1 + 552);
  if ( v4 )
  {
    buffer = av_hwframe_get_buffer(v4, a2, 0);
    if ( buffer == -12 )
    {
      v6 = *(_DWORD **)(*(_QWORD *)(a1 + 552) + 8LL);
      if ( (int)v6[14] > 0 && !*(_DWORD *)(*(_QWORD *)(a1 + 40) + 148LL) )
      {
        v7 = v6[15];
        pix_fmt_name = (const char *)av_get_pix_fmt_name((unsigned int)v6[16]);
        v9 = (const char *)av_get_pix_fmt_name(v7);
        av_log(
          a1,
          buffer + 36,
          "Failed to allocate a %s/%s frame from a fixed pool of hardware frames.\n",
          v9,
          pix_fmt_name);
        av_log(
          a1,
          buffer + 36,
          "Consider setting extra_hw_frames to a larger value (currently set to %d, giving a pool size of %d).\n",
          *(_DWORD *)(a1 + 572),
          v6[14]);
        *(_DWORD *)(*(_QWORD *)(a1 + 40) + 148LL) = 1;
      }
    }
    *(_DWORD *)(a2 + 104) = *(_DWORD *)(a1 + 120);
    *(_DWORD *)(a2 + 108) = *(_DWORD *)(a1 + 124);
    return buffer;
  }
  else
  {
    result = sub_18000C720(a1);
    if ( (int)result >= 0 )
    {
      v11 = *(_DWORD *)(a1 + 12);
      if ( v11 )
      {
        if ( v11 == 1 )
        {
          _mm_lfence();
          return sub_18000C3E8(a1, a2);
        }
        else
        {
          return 0xFFFFFFFFLL;
        }
      }
      else
      {
        _mm_lfence();
        return sub_18000CA24(a1, a2);
      }
    }
    else
    {
      _mm_lfence();
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c5c0  mov     [rsp+arg_0], rbx
0x18000c5c5  mov     [rsp+arg_8], rbp
0x18000c5ca  mov     [rsp+arg_10], rsi
0x18000c5cf  push    rdi
0x18000c5d0  push    r14
0x18000c5d2  push    r15
0x18000c5d4  sub     rsp, 30h
0x18000c5d8  mov     rsi, rcx
0x18000c5db  mov     rbp, rdx
0x18000c5de  mov     rcx, [rcx+228h]
0x18000c5e5  test    rcx, rcx
0x18000c5e8  jz      loc_18000C694
0x18000c5ee  xor     r8d, r8d
0x18000c5f1  call    av_hwframe_get_buffer
0x18000c5f6  mov     r14d, eax
0x18000c5f9  cmp     eax, 0FFFFFFF4h
0x18000c5fc  jnz     loc_18000C683
0x18000c602  mov     rcx, [rsi+228h]
0x18000c609  mov     r15, [rcx+8]
0x18000c60d  cmp     dword ptr [r15+38h], 0
0x18000c612  jle     short loc_18000C683
0x18000c614  mov     rcx, [rsi+28h]
0x18000c618  cmp     dword ptr [rcx+94h], 0
0x18000c61f  jnz     short loc_18000C683
0x18000c621  mov     ecx, [r15+40h]
0x18000c625  mov     ebx, [r15+3Ch]
0x18000c629  call    av_get_pix_fmt_name
0x18000c62e  mov     ecx, ebx
0x18000c630  mov     rdi, rax
0x18000c633  call    av_get_pix_fmt_name
0x18000c638  lea     ebx, [r14+24h]
0x18000c63c  mov     [rsp+48h+var_28], rdi
0x18000c641  mov     edx, ebx
0x18000c643  lea     r8, aFailedToAlloca_0; "Failed to allocate a %s/%s frame from a"...
0x18000c64a  mov     r9, rax
0x18000c64d  mov     rcx, rsi
0x18000c650  call    av_log
0x18000c655  mov     eax, [r15+38h]
0x18000c659  lea     r8, aConsiderSettin; "Consider setting extra_hw_frames to a l"...
0x18000c660  mov     r9d, [rsi+23Ch]
0x18000c667  mov     edx, ebx
0x18000c669  mov     rcx, rsi
0x18000c66c  mov     dword ptr [rsp+48h+var_28], eax
0x18000c670  call    av_log
0x18000c675  mov     rax, [rsi+28h]
0x18000c679  mov     dword ptr [rax+94h], 1
0x18000c683  mov     eax, [rsi+78h]
0x18000c686  mov     [rbp+68h], eax
0x18000c689  mov     eax, [rsi+7Ch]
0x18000c68c  mov     [rbp+6Ch], eax
0x18000c68f  mov     eax, r14d
0x18000c692  jmp     short loc_18000C6D4
0x18000c694  mov     rcx, rsi
0x18000c697  call    sub_18000C720
0x18000c69c  test    eax, eax
0x18000c69e  jns     short loc_18000C6A5
0x18000c6a0  lfence
0x18000c6a3  jmp     short loc_18000C6D4
0x18000c6a5  mov     ecx, [rsi+0Ch]
0x18000c6a8  test    ecx, ecx
0x18000c6aa  jz      short loc_18000C6C6
0x18000c6ac  cmp     ecx, 1
0x18000c6af  jz      short loc_18000C6B6
0x18000c6b1  or      eax, 0FFFFFFFFh
0x18000c6b4  jmp     short loc_18000C6D4
0x18000c6b6  lfence
0x18000c6b9  mov     rdx, rbp
0x18000c6bc  mov     rcx, rsi
0x18000c6bf  call    sub_18000C3E8
0x18000c6c4  jmp     short loc_18000C6D4
0x18000c6c6  lfence
0x18000c6c9  mov     rdx, rbp
0x18000c6cc  mov     rcx, rsi
0x18000c6cf  call    sub_18000CA24
0x18000c6d4  mov     rbx, [rsp+48h+arg_0]
0x18000c6d9  mov     rbp, [rsp+48h+arg_8]
0x18000c6de  mov     rsi, [rsp+48h+arg_10]
0x18000c6e3  add     rsp, 30h
0x18000c6e7  pop     r15
0x18000c6e9  pop     r14
0x18000c6eb  pop     rdi
0x18000c6ec  retn
```
