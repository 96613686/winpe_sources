# ConvertToSniConfig

- ea: `0x180001710`
- end: `0x18000190e`
- name: `ConvertToSniConfig`
- size: `510`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180001490`
- `0x1800015d0`
- `0x180009280`

## callees

- `0x180001710`
- `0x180001920`
- `0x18000a4c8`

## pseudocode

```c
__int64 __fastcall ConvertToSniConfig(int a1, __int64 a2, unsigned int a3, _OWORD *a4)
{
  int v8; // esi
  int v9; // esi
  __int64 result; // rax
  __int128 v11; // xmm0

  memset_0(a4, 0, 0xD8u);
  if ( a1 != 1 )
  {
    v8 = a1 - 5;
    if ( !v8 )
    {
LABEL_8:
      if ( a3 < 0xD8 )
        return 87;
      *a4 = *(_OWORD *)a2;
      a4[1] = *(_OWORD *)(a2 + 16);
      a4[2] = *(_OWORD *)(a2 + 32);
      a4[3] = *(_OWORD *)(a2 + 48);
      a4[4] = *(_OWORD *)(a2 + 64);
      a4[5] = *(_OWORD *)(a2 + 80);
      a4[6] = *(_OWORD *)(a2 + 96);
      a4[7] = *(_OWORD *)(a2 + 112);
      a4[8] = *(_OWORD *)(a2 + 128);
      a4[9] = *(_OWORD *)(a2 + 144);
      a4[10] = *(_OWORD *)(a2 + 160);
      a4[11] = *(_OWORD *)(a2 + 176);
      a4[12] = *(_OWORD *)(a2 + 192);
      *((_QWORD *)a4 + 26) = *(_QWORD *)(a2 + 208);
      return 0;
    }
    v9 = v8 - 1;
    if ( v9 )
    {
      if ( v9 != 5 )
        return 87;
      goto LABEL_8;
    }
    if ( a3 < 0xD0 )
      return 87;
    *a4 = *(_OWORD *)a2;
    a4[1] = *(_OWORD *)(a2 + 16);
    a4[2] = *(_OWORD *)(a2 + 32);
    a4[3] = *(_OWORD *)(a2 + 48);
    a4[4] = *(_OWORD *)(a2 + 64);
    a4[5] = *(_OWORD *)(a2 + 80);
    a4[6] = *(_OWORD *)(a2 + 96);
    a4[7] = *(_OWORD *)(a2 + 112);
    *(_OWORD *)((char *)a4 + 136) = *(_OWORD *)(a2 + 128);
    *(_OWORD *)((char *)a4 + 152) = *(_OWORD *)(a2 + 144);
    *(_OWORD *)((char *)a4 + 168) = *(_OWORD *)(a2 + 160);
    *(_OWORD *)((char *)a4 + 184) = *(_OWORD *)(a2 + 176);
    v11 = *(_OWORD *)(a2 + 192);
LABEL_13:
    *(_OWORD *)((char *)a4 + 200) = v11;
    return 0;
  }
  if ( a3 < 0x58 )
    return 87;
  result = CopySockAddrToSockAddrStorage(*(_QWORD *)a2, a4);
  if ( !(_DWORD)result )
  {
    *(_OWORD *)((char *)a4 + 136) = *(_OWORD *)(a2 + 8);
    *(_OWORD *)((char *)a4 + 152) = *(_OWORD *)(a2 + 24);
    *(_OWORD *)((char *)a4 + 168) = *(_OWORD *)(a2 + 40);
    *(_OWORD *)((char *)a4 + 184) = *(_OWORD *)(a2 + 56);
    v11 = *(_OWORD *)(a2 + 72);
    goto LABEL_13;
  }
  return result;
}

```

## disassembly

```asm
0x180001710  push    rbx
0x180001712  push    rsi
0x180001713  push    rdi
0x180001714  push    r14
0x180001716  sub     rsp, 28h
0x18000171a  mov     ebx, r8d
0x18000171d  mov     r14, rdx
0x180001720  mov     esi, ecx
0x180001722  xor     edx, edx; Val
0x180001724  mov     r8d, 0D8h; Size
0x18000172a  mov     rcx, r9; void *
0x18000172d  mov     rdi, r9
0x180001730  call    memset_0
0x180001735  cmp     esi, 1
0x180001738  jz      loc_1800018AC
0x18000173e  sub     esi, 5
0x180001741  jz      loc_1800017FD
0x180001747  sub     esi, 1
0x18000174a  jz      short loc_180001764
0x18000174c  cmp     esi, 5
0x18000174f  jz      loc_1800017FD
0x180001755  mov     eax, 57h ; 'W'
0x18000175a  add     rsp, 28h
0x18000175e  pop     r14
0x180001760  pop     rdi
0x180001761  pop     rsi
0x180001762  pop     rbx
0x180001763  retn
0x180001764  cmp     ebx, 0D0h
0x18000176a  jb      short loc_180001755
0x18000176c  movups  xmm0, xmmword ptr [r14]
0x180001770  xor     ecx, ecx
0x180001772  movaps  xmmword ptr [rdi], xmm0
0x180001775  movups  xmm1, xmmword ptr [r14+10h]
0x18000177a  movaps  xmmword ptr [rdi+10h], xmm1
0x18000177e  movups  xmm0, xmmword ptr [r14+20h]
0x180001783  movaps  xmmword ptr [rdi+20h], xmm0
0x180001787  movups  xmm1, xmmword ptr [r14+30h]
0x18000178c  movaps  xmmword ptr [rdi+30h], xmm1
0x180001790  movups  xmm0, xmmword ptr [r14+40h]
0x180001795  movaps  xmmword ptr [rdi+40h], xmm0
0x180001799  movups  xmm1, xmmword ptr [r14+50h]
0x18000179e  movaps  xmmword ptr [rdi+50h], xmm1
0x1800017a2  movups  xmm0, xmmword ptr [r14+60h]
0x1800017a7  movaps  xmmword ptr [rdi+60h], xmm0
0x1800017ab  movups  xmm1, xmmword ptr [r14+70h]
0x1800017b0  movaps  xmmword ptr [rdi+70h], xmm1
0x1800017b4  movups  xmm0, xmmword ptr [r14+80h]
0x1800017bc  movups  xmmword ptr [rdi+88h], xmm0
0x1800017c3  movups  xmm1, xmmword ptr [r14+90h]
0x1800017cb  movups  xmmword ptr [rdi+98h], xmm1
0x1800017d2  movups  xmm0, xmmword ptr [r14+0A0h]
0x1800017da  movups  xmmword ptr [rdi+0A8h], xmm0
0x1800017e1  movups  xmm1, xmmword ptr [r14+0B0h]
0x1800017e9  movups  xmmword ptr [rdi+0B8h], xmm1
0x1800017f0  movups  xmm0, xmmword ptr [r14+0C0h]
0x1800017f8  jmp     loc_1800018FB
0x1800017fd  cmp     ebx, 0D8h
0x180001803  jb      loc_180001755
0x180001809  movups  xmm0, xmmword ptr [r14]
0x18000180d  xor     ecx, ecx
0x18000180f  movups  xmmword ptr [rdi], xmm0
0x180001812  movups  xmm1, xmmword ptr [r14+10h]
0x180001817  movups  xmmword ptr [rdi+10h], xmm1
0x18000181b  movups  xmm0, xmmword ptr [r14+20h]
0x180001820  movups  xmmword ptr [rdi+20h], xmm0
0x180001824  movups  xmm1, xmmword ptr [r14+30h]
0x180001829  movups  xmmword ptr [rdi+30h], xmm1
0x18000182d  movups  xmm0, xmmword ptr [r14+40h]
0x180001832  movups  xmmword ptr [rdi+40h], xmm0
0x180001836  movups  xmm1, xmmword ptr [r14+50h]
0x18000183b  movups  xmmword ptr [rdi+50h], xmm1
0x18000183f  movups  xmm0, xmmword ptr [r14+60h]
0x180001844  movups  xmmword ptr [rdi+60h], xmm0
0x180001848  movups  xmm1, xmmword ptr [r14+70h]
0x18000184d  movups  xmmword ptr [rdi+70h], xmm1
0x180001851  movups  xmm0, xmmword ptr [r14+80h]
0x180001859  movups  xmmword ptr [rdi+80h], xmm0
0x180001860  movups  xmm1, xmmword ptr [r14+90h]
0x180001868  movups  xmmword ptr [rdi+90h], xmm1
0x18000186f  movups  xmm0, xmmword ptr [r14+0A0h]
0x180001877  movups  xmmword ptr [rdi+0A0h], xmm0
0x18000187e  movups  xmm1, xmmword ptr [r14+0B0h]
0x180001886  movups  xmmword ptr [rdi+0B0h], xmm1
0x18000188d  movups  xmm0, xmmword ptr [r14+0C0h]
0x180001895  movups  xmmword ptr [rdi+0C0h], xmm0
0x18000189c  mov     rax, [r14+0D0h]
0x1800018a3  mov     [rdi+0D0h], rax
0x1800018aa  jmp     short loc_180001902
0x1800018ac  cmp     ebx, 58h ; 'X'
0x1800018af  jb      loc_180001755
0x1800018b5  mov     rcx, [r14]
0x1800018b8  mov     rdx, rdi
0x1800018bb  call    CopySockAddrToSockAddrStorage
0x1800018c0  mov     ecx, eax
0x1800018c2  test    eax, eax
0x1800018c4  jnz     short loc_180001904
0x1800018c6  movups  xmm0, xmmword ptr [r14+8]
0x1800018cb  movups  xmmword ptr [rdi+88h], xmm0
0x1800018d2  movups  xmm1, xmmword ptr [r14+18h]
0x1800018d7  movups  xmmword ptr [rdi+98h], xmm1
0x1800018de  movups  xmm0, xmmword ptr [r14+28h]
0x1800018e3  movups  xmmword ptr [rdi+0A8h], xmm0
0x1800018ea  movups  xmm1, xmmword ptr [r14+38h]
0x1800018ef  movups  xmmword ptr [rdi+0B8h], xmm1
0x1800018f6  movups  xmm0, xmmword ptr [r14+48h]
0x1800018fb  movups  xmmword ptr [rdi+0C8h], xmm0
0x180001902  mov     eax, ecx
0x180001904  add     rsp, 28h
0x180001908  pop     r14
0x18000190a  pop     rdi
0x18000190b  pop     rsi
0x18000190c  pop     rbx
0x18000190d  retn
```
