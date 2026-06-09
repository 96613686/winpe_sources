# CAacDecoderSetTransportStreamChannelConfig

- ea: `0x1800743e0`
- end: `0x180074552`
- name: `CAacDecoderSetTransportStreamChannelConfig`
- size: `370`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001a6b0`

## callees

- `0x180002122`
- `0x1800021a8`
- `0x1800743e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007450d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007450d`

## pseudocode

```c
__int64 __fastcall CAacDecoderSetTransportStreamChannelConfig(_DWORD *a1, _DWORD *a2, __int64 a3, __int64 a4)
{
  _DWORD *v5; // rcx

  if ( a2 && a3 || !a1 )
    return 1;
  if ( a2 )
  {
    if ( !a3 )
    {
      if ( *a2 > 7u )
        return 1;
      a1[55] = 1;
      a1[56] = *a2;
      memset_0(a1 + 57, 0, 0xB1u);
      return 0;
    }
LABEL_15:
    memset_0(a1 + 55, 0, 0xBCu);
    return 0;
  }
  if ( !a3 )
    goto LABEL_15;
  *(_QWORD *)(a1 + 55) = 2;
  v5 = a1 + 57;
  if ( v5 )
  {
    *(_OWORD *)v5 = *(_OWORD *)a3;
    *((_OWORD *)v5 + 1) = *(_OWORD *)(a3 + 16);
    *((_OWORD *)v5 + 2) = *(_OWORD *)(a3 + 32);
    *((_OWORD *)v5 + 3) = *(_OWORD *)(a3 + 48);
    *((_OWORD *)v5 + 4) = *(_OWORD *)(a3 + 64);
    *((_OWORD *)v5 + 5) = *(_OWORD *)(a3 + 80);
    *((_OWORD *)v5 + 6) = *(_OWORD *)(a3 + 96);
    *((_OWORD *)v5 + 7) = *(_OWORD *)(a3 + 112);
    *((_OWORD *)v5 + 8) = *(_OWORD *)(a3 + 128);
    *((_OWORD *)v5 + 9) = *(_OWORD *)(a3 + 144);
    *((_OWORD *)v5 + 10) = *(_OWORD *)(a3 + 160);
    *((_BYTE *)v5 + 176) = *(_BYTE *)(a3 + 176);
  }
  else
  {
    *(_DWORD *)_o__errno(0, 0, a3, a4) = 22;
    invalid_parameter_noinfo();
  }
  return 0;
}

```

## disassembly

```asm
0x1800743e0  sub     rsp, 28h
0x1800743e4  mov     rax, rcx
0x1800743e7  test    rdx, rdx
0x1800743ea  jz      short loc_1800743F1
0x1800743ec  test    r8, r8
0x1800743ef  jnz     short loc_1800743F6
0x1800743f1  test    rax, rax
0x1800743f4  jnz     short loc_180074401
0x1800743f6  mov     eax, 1
0x1800743fb  add     rsp, 28h
0x1800743ff  retn
0x180074401  mov     [rsp+28h+var_8], rbx
0x180074406  xor     ebx, ebx
0x180074408  test    rdx, rdx
0x18007440b  jz      short loc_18007445E
0x18007440d  test    r8, r8
0x180074410  jnz     loc_180074531
0x180074416  cmp     dword ptr [rdx], 7
0x180074419  jbe     short loc_18007442B
0x18007441b  mov     rbx, [rsp+28h+var_8]
0x180074420  mov     eax, 1
0x180074425  add     rsp, 28h
0x180074429  retn
0x18007442b  mov     dword ptr [rcx+0DCh], 1
0x180074435  mov     r8d, 0B1h; Size
0x18007443b  mov     ecx, [rdx]
0x18007443d  xor     edx, edx; Val
0x18007443f  mov     [rax+0E0h], ecx
0x180074445  lea     rcx, [rax+0E4h]; void *
0x18007444c  call    memset_0
0x180074451  mov     eax, ebx
0x180074453  mov     rbx, [rsp+28h+var_8]
0x180074458  add     rsp, 28h
0x18007445c  retn
0x18007445e  test    r8, r8
0x180074461  jz      loc_180074531
0x180074467  mov     qword ptr [rcx+0DCh], 2
0x180074472  add     rcx, 0E4h
0x180074479  jz      loc_18007450D
0x18007447f  movups  xmm0, xmmword ptr [r8]
0x180074483  movups  xmmword ptr [rcx], xmm0
0x180074486  movups  xmm1, xmmword ptr [r8+10h]
0x18007448b  movups  xmmword ptr [rcx+10h], xmm1
0x18007448f  movups  xmm0, xmmword ptr [r8+20h]
0x180074494  movups  xmmword ptr [rcx+20h], xmm0
0x180074498  movups  xmm1, xmmword ptr [r8+30h]
0x18007449d  movups  xmmword ptr [rcx+30h], xmm1
0x1800744a1  movups  xmm0, xmmword ptr [r8+40h]
0x1800744a6  movups  xmmword ptr [rcx+40h], xmm0
0x1800744aa  movups  xmm1, xmmword ptr [r8+50h]
0x1800744af  movups  xmmword ptr [rcx+50h], xmm1
0x1800744b3  movups  xmm0, xmmword ptr [r8+60h]
0x1800744b8  movups  xmmword ptr [rcx+60h], xmm0
0x1800744bc  movups  xmm1, xmmword ptr [r8+70h]
0x1800744c1  movups  xmmword ptr [rcx+70h], xmm1
0x1800744c5  movups  xmm0, xmmword ptr [r8+80h]
0x1800744cd  movups  xmmword ptr [rcx+80h], xmm0
0x1800744d4  movups  xmm1, xmmword ptr [r8+90h]
0x1800744dc  movups  xmmword ptr [rcx+90h], xmm1
0x1800744e3  movups  xmm0, xmmword ptr [r8+0A0h]
0x1800744eb  movups  xmmword ptr [rcx+0A0h], xmm0
0x1800744f2  movzx   eax, byte ptr [r8+0B0h]
0x1800744fa  mov     [rcx+0B0h], al
0x180074500  mov     eax, ebx
0x180074502  mov     rbx, [rsp+28h+var_8]
0x180074507  add     rsp, 28h
0x18007450b  retn
0x18007450d  call    cs:__imp__o__errno
0x180074514  nop     dword ptr [rax+rax+00h]
0x180074519  mov     dword ptr [rax], 16h
0x18007451f  call    _invalid_parameter_noinfo
0x180074524  mov     eax, ebx
0x180074526  mov     rbx, [rsp+28h+var_8]
0x18007452b  add     rsp, 28h
0x18007452f  retn
0x180074531  add     rcx, 0DCh; void *
0x180074538  mov     r8d, 0BCh; Size
0x18007453e  xor     edx, edx; Val
0x180074540  call    memset_0
0x180074545  mov     eax, ebx
0x180074547  mov     rbx, [rsp+28h+var_8]
0x18007454c  add     rsp, 28h
0x180074550  retn
```
