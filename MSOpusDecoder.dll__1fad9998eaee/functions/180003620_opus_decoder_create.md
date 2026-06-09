# opus_decoder_create

- ea: `0x180003620`
- end: `0x18000383a`
- name: `opus_decoder_create`
- size: `538`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001d860`

## callees

- `0x18000227c`
- `0x180003620`
- `0x1800072f0`
- `0x180007330`
- `0x180008120`
- `0x180009360`
- `0x180009fc0`
- `0x180009fd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000381c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000381c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800036b9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800036b9`

## pseudocode

```c
_DWORD *__fastcall opus_decoder_create(int a1, unsigned int a2, int *a3)
{
  unsigned int v7; // r14d
  int v8; // eax
  _DWORD *v9; // rbx
  int v10; // eax
  int v11; // eax
  unsigned int v12; // eax
  int v13; // eax
  int v14; // r14d
  char *v15; // r14
  unsigned int v16; // [rsp+40h] [rbp+8h] BYREF
  int v17; // [rsp+58h] [rbp+20h] BYREF

  if ( a1 != 48000 && a1 != 24000 && a1 != 16000 && a1 != 12000 && a1 != 8000 || a2 - 1 > 1 )
  {
    if ( a3 )
    {
      *a3 = -1;
      return 0;
    }
    return 0;
  }
  v7 = a2 - 1;
  if ( (unsigned int)silk_Get_Decoder_Size(&v16) )
  {
    v8 = 0;
  }
  else
  {
    v16 = (v16 + 7) & 0xFFFFFFF8;
    v8 = v16 + 96 + celt_decoder_get_size(a2);
  }
  v9 = malloc(v8);
  if ( !v9 )
  {
    if ( a3 )
      *a3 = -7;
    return 0;
  }
  if ( (a1 == 48000 || a1 == 24000 || a1 == 16000 || a1 == 12000 || a1 == 8000) && a2 - 1 <= 1 )
  {
    if ( v7 > 1 || (unsigned int)silk_Get_Decoder_Size(&v16) )
    {
      v11 = 0;
    }
    else
    {
      v16 = (v16 + 7) & 0xFFFFFFF8;
      v11 = v16 + 96 + celt_decoder_get_size(a2);
    }
    memset_0(v9, 0, v11);
    if ( (unsigned int)silk_Get_Decoder_Size(&v17) )
    {
      v10 = -3;
    }
    else
    {
      v12 = v17 + 7;
      v9[1] = 96;
      v9[2] = a2;
      v9[14] = a2;
      v9[12] = 0;
      v13 = 8 * (v12 >> 3);
      v9[3] = a1;
      v14 = v13 + 96;
      v17 = v13;
      *v9 = v13 + 96;
      v9[6] = a1;
      v9[4] = a2;
      if ( (unsigned int)silk_ResetDecoder(v9 + 24) )
      {
        v10 = -3;
      }
      else
      {
        v15 = (char *)v9 + v14;
        if ( (unsigned int)celt_decoder_init(v15) )
        {
          v10 = -3;
        }
        else
        {
          opus_custom_decoder_ctl(v15, 10016, 0);
          v9[17] = 0;
          v9[18] = a1 / 400;
          v9[13] = opus_select_arch();
          v10 = 0;
        }
      }
    }
  }
  else
  {
    v10 = -1;
  }
  if ( a3 )
    *a3 = v10;
  if ( v10 )
  {
    free(v9);
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180003620  mov     [rsp+arg_8], rbx
0x180003625  mov     [rsp+arg_10], rbp
0x18000362a  push    rsi
0x18000362b  push    rdi
0x18000362c  push    r14
0x18000362e  sub     rsp, 20h
0x180003632  mov     rsi, r8
0x180003635  mov     ebp, edx
0x180003637  mov     edi, ecx
0x180003639  cmp     ecx, 0BB80h
0x18000363f  jz      short loc_180003661
0x180003641  cmp     ecx, 5DC0h
0x180003647  jz      short loc_180003661
0x180003649  cmp     ecx, 3E80h
0x18000364f  jz      short loc_180003661
0x180003651  cmp     ecx, 2EE0h
0x180003657  jz      short loc_180003661
0x180003659  cmp     ecx, 1F40h
0x18000365f  jnz     short loc_180003669
0x180003661  lea     eax, [rdx-1]
0x180003664  cmp     eax, 1
0x180003667  jbe     short loc_18000367C
0x180003669  test    rsi, rsi
0x18000366c  jz      short loc_1800036D2
0x18000366e  mov     dword ptr [r8], 0FFFFFFFFh
0x180003675  xor     eax, eax
0x180003677  jmp     loc_180003827
0x18000367c  lea     r14d, [rdx-1]
0x180003680  cmp     r14d, 1
0x180003684  ja      short loc_1800036B4
0x180003686  lea     rcx, [rsp+38h+arg_0]
0x18000368b  call    silk_Get_Decoder_Size
0x180003690  test    eax, eax
0x180003692  jnz     short loc_1800036B4
0x180003694  mov     eax, [rsp+38h+arg_0]
0x180003698  mov     ecx, ebp
0x18000369a  add     eax, 7
0x18000369d  and     eax, 0FFFFFFF8h
0x1800036a0  mov     [rsp+38h+arg_0], eax
0x1800036a4  call    celt_decoder_get_size
0x1800036a9  mov     ecx, [rsp+38h+arg_0]
0x1800036ad  add     ecx, 60h ; '`'
0x1800036b0  add     eax, ecx
0x1800036b2  jmp     short loc_1800036B6
0x1800036b4  xor     eax, eax
0x1800036b6  movsxd  rcx, eax; Size
0x1800036b9  call    cs:__imp_malloc
0x1800036bf  mov     rbx, rax
0x1800036c2  test    rax, rax
0x1800036c5  jnz     short loc_1800036D9
0x1800036c7  test    rsi, rsi
0x1800036ca  jz      short loc_1800036D2
0x1800036cc  mov     dword ptr [rsi], 0FFFFFFF9h
0x1800036d2  xor     eax, eax
0x1800036d4  jmp     loc_180003827
0x1800036d9  cmp     edi, 0BB80h
0x1800036df  jz      short loc_180003701
0x1800036e1  cmp     edi, 5DC0h
0x1800036e7  jz      short loc_180003701
0x1800036e9  cmp     edi, 3E80h
0x1800036ef  jz      short loc_180003701
0x1800036f1  cmp     edi, 2EE0h
0x1800036f7  jz      short loc_180003701
0x1800036f9  cmp     edi, 1F40h
0x1800036ff  jnz     short loc_180003709
0x180003701  lea     eax, [rbp-1]
0x180003704  cmp     eax, 1
0x180003707  jbe     short loc_180003713
0x180003709  mov     eax, 0FFFFFFFFh
0x18000370e  jmp     loc_18000380E
0x180003713  cmp     r14d, 1
0x180003717  ja      short loc_180003747
0x180003719  lea     rcx, [rsp+38h+arg_0]
0x18000371e  call    silk_Get_Decoder_Size
0x180003723  test    eax, eax
0x180003725  jnz     short loc_180003747
0x180003727  mov     eax, [rsp+38h+arg_0]
0x18000372b  mov     ecx, ebp
0x18000372d  add     eax, 7
0x180003730  and     eax, 0FFFFFFF8h
0x180003733  mov     [rsp+38h+arg_0], eax
0x180003737  call    celt_decoder_get_size
0x18000373c  mov     ecx, [rsp+38h+arg_0]
0x180003740  add     ecx, 60h ; '`'
0x180003743  add     eax, ecx
0x180003745  jmp     short loc_180003749
0x180003747  xor     eax, eax
0x180003749  movsxd  r8, eax; Size
0x18000374c  xor     edx, edx; Val
0x18000374e  mov     rcx, rbx; void *
0x180003751  call    memset_0
0x180003756  lea     rcx, [rsp+38h+arg_18]
0x18000375b  call    silk_Get_Decoder_Size
0x180003760  test    eax, eax
0x180003762  jz      short loc_18000376E
0x180003764  mov     eax, 0FFFFFFFDh
0x180003769  jmp     loc_18000380E
0x18000376e  mov     eax, [rsp+38h+arg_18]
0x180003772  lea     rcx, [rbx+60h]
0x180003776  add     eax, 7
0x180003779  mov     dword ptr [rbx+4], 60h ; '`'
0x180003780  shr     eax, 3
0x180003783  mov     [rbx+8], ebp
0x180003786  mov     [rbx+38h], ebp
0x180003789  mov     dword ptr [rbx+30h], 0
0x180003790  lea     eax, ds:0[rax*8]
0x180003797  mov     [rbx+0Ch], edi
0x18000379a  lea     r14d, [rax+60h]
0x18000379e  mov     [rsp+38h+arg_18], eax
0x1800037a2  mov     [rbx], r14d
0x1800037a5  mov     [rbx+18h], edi
0x1800037a8  mov     [rbx+10h], ebp
0x1800037ab  call    silk_ResetDecoder
0x1800037b0  test    eax, eax
0x1800037b2  jz      short loc_1800037BB
0x1800037b4  mov     eax, 0FFFFFFFDh
0x1800037b9  jmp     short loc_18000380E
0x1800037bb  movsxd  r14, r14d
0x1800037be  mov     r8d, ebp
0x1800037c1  add     r14, rbx
0x1800037c4  mov     edx, edi
0x1800037c6  mov     rcx, r14; void *
0x1800037c9  call    celt_decoder_init
0x1800037ce  test    eax, eax
0x1800037d0  jz      short loc_1800037D9
0x1800037d2  mov     eax, 0FFFFFFFDh
0x1800037d7  jmp     short loc_18000380E
0x1800037d9  xor     r8d, r8d
0x1800037dc  mov     edx, 2720h
0x1800037e1  mov     rcx, r14
0x1800037e4  call    opus_custom_decoder_ctl
0x1800037e9  mov     eax, 51EB851Fh
0x1800037ee  mov     dword ptr [rbx+44h], 0
0x1800037f5  imul    edi
0x1800037f7  sar     edx, 7
0x1800037fa  mov     eax, edx
0x1800037fc  shr     eax, 1Fh
0x1800037ff  add     edx, eax
0x180003801  mov     [rbx+48h], edx
0x180003804  call    opus_select_arch
0x180003809  mov     [rbx+34h], eax
0x18000380c  xor     eax, eax
0x18000380e  test    rsi, rsi
0x180003811  jz      short loc_180003815
0x180003813  mov     [rsi], eax
0x180003815  test    eax, eax
0x180003817  jz      short loc_180003824
0x180003819  mov     rcx, rbx; Block
0x18000381c  call    cs:__imp_free
0x180003822  xor     ebx, ebx
0x180003824  mov     rax, rbx
0x180003827  mov     rbx, [rsp+38h+arg_8]
0x18000382c  mov     rbp, [rsp+38h+arg_10]
0x180003831  add     rsp, 20h
0x180003835  pop     r14
0x180003837  pop     rdi
0x180003838  pop     rsi
0x180003839  retn
```
