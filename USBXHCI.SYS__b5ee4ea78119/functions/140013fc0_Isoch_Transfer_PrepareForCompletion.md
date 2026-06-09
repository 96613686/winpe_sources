# Isoch_Transfer_PrepareForCompletion

- ea: `0x140013fc0`
- end: `0x14001425b`
- name: `Isoch_Transfer_PrepareForCompletion`
- size: `667`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011760`
- `0x140038424`

## callees

- `0x140013fc0`
- `0x140014270`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x1400140cf`
- `ntoskrnl!IoFreeMdl` at `0x1400140cf`

## pseudocode

```c
void __fastcall Isoch_Transfer_PrepareForCompletion(__int64 a1, __int64 a2, int a3, int a4)
{
  __int64 v4; // rdi
  __int64 v8; // rcx
  int v9; // r8d
  unsigned int v10; // eax
  unsigned int i; // edx
  int v12; // eax
  int v13; // eax
  struct _MDL *v14; // rcx
  __int64 v15; // r8

  v4 = *(_QWORD *)(a2 + 48);
  if ( *(_WORD *)(v4 + 2) == 56 )
  {
LABEL_2:
    v8 = 36;
  }
  else
  {
    switch ( *(_WORD *)(v4 + 2) )
    {
      case '9':
      case ':':
        v8 = 52;
        break;
      default:
        goto LABEL_2;
    }
  }
  *(_DWORD *)(v4 + v8) = *(_DWORD *)(a2 + 84);
  v9 = 0;
  v10 = *(_DWORD *)(a2 + 96);
  for ( i = 0; i < v10; v10 = *(_DWORD *)(a2 + 96) )
  {
    if ( a3 == -1 )
    {
      v12 = *(_DWORD *)(v4 + 12LL * i + 148);
      if ( v12 == -1 )
      {
        *(_DWORD *)(v4 + 12LL * i + 148) = -1073610752;
LABEL_26:
        ++*(_DWORD *)(v4 + 136);
        ++*(_DWORD *)(a1 + 268);
        goto LABEL_8;
      }
    }
    else
    {
      *(_DWORD *)(v4 + 12LL * i + 148) = a3;
      v12 = a3;
    }
    if ( v12 )
      goto LABEL_26;
    ++v9;
LABEL_8:
    ++*(_DWORD *)(a1 + 264);
    ++i;
  }
  if ( a4 == -1 )
  {
    if ( *(_DWORD *)(v4 + 136) != v10 )
    {
      *(_DWORD *)(v4 + 4) = 0;
LABEL_13:
      v13 = 0;
      goto LABEL_15;
    }
    *(_DWORD *)(v4 + 4) = -1073739008;
    goto LABEL_14;
  }
  *(_DWORD *)(v4 + 4) = a4;
  if ( a4 == 1 )
    goto LABEL_13;
  if ( a4 <= -1073738240 )
  {
    if ( a4 == -1073738240 )
    {
      v13 = -1073741637;
    }
    else
    {
      if ( a4 != -1073739264 && a4 != -2147483136 && a4 != -2147482880 && a4 != -2147482112 )
        goto LABEL_14;
      v13 = -1073741811;
    }
  }
  else
  {
    if ( a4 == -1073676288 )
    {
      v13 = -1073741536;
      goto LABEL_15;
    }
    if ( a4 != -1073737728 )
    {
      if ( a4 == -1073713152 )
      {
        v13 = -1073741810;
        goto LABEL_15;
      }
      if ( !a4 )
        goto LABEL_13;
LABEL_14:
      v13 = -1073741823;
      goto LABEL_15;
    }
    v13 = -1073741670;
  }
LABEL_15:
  *(_DWORD *)(a2 + 68) = v13;
  ++*(_DWORD *)(a1 + 248);
  *(_QWORD *)(a1 + 256) += *(unsigned int *)(a2 + 84);
  if ( *(int *)(a2 + 68) < 0 )
    ++*(_DWORD *)(a1 + 252);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_DDqdDDDD(
      *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
      *(unsigned __int8 *)(*(_QWORD *)(a1 + 48) + 143LL),
      v9,
      a4);
  v14 = *(struct _MDL **)(a2 + 72);
  if ( v14 )
  {
    v15 = *(_QWORD *)(a2 + 48);
    if ( *(_WORD *)(v15 + 2) != 56 )
    {
      switch ( *(_WORD *)(v15 + 2) )
      {
        case '9':
        case ':':
          goto LABEL_22;
        default:
          break;
      }
    }
    if ( v14 != *(struct _MDL **)(v15 + 48) )
    {
LABEL_22:
      IoFreeMdl(v14);
      *(_QWORD *)(a2 + 72) = 0;
    }
  }
  *(_BYTE *)(a2 + 16) = 0;
}

```

## disassembly

```asm
0x140013fc0  push    rbx
0x140013fc2  push    rbp
0x140013fc3  push    rsi
0x140013fc4  push    rdi
0x140013fc5  sub     rsp, 78h
0x140013fc9  mov     rdi, [rdx+30h]
0x140013fcd  lea     rbp, cs:140000000h
0x140013fd4  mov     r11d, r8d
0x140013fd7  mov     rbx, rdx
0x140013fda  mov     r10, rcx
0x140013fdd  movzx   eax, word ptr [rdi+2]
0x140013fe1  cmp     eax, 38h ; '8'
0x140013fe4  jz      short def_1400141F7; jumptable 00000001400141F7 default case, cases 8-56
0x140013fe6  add     eax, 0FFFFFFF8h; switch 51 cases
0x140013fe9  cmp     eax, 32h
0x140013fec  jbe     loc_1400141E3
0x140013ff2  mov     ecx, 24h ; '$'; jumptable 00000001400141F7 default case, cases 8-56
0x140013ff7  mov     eax, [rdx+54h]
0x140013ffa  xor     esi, esi
0x140013ffc  mov     [rdi+rcx], eax
0x140013fff  mov     r8d, esi
0x140014002  mov     eax, [rbx+60h]
0x140014005  mov     edx, esi
0x140014007  test    eax, eax
0x140014009  jz      short loc_14001404B
0x14001400b  nop     dword ptr [rax+rax+00h]
0x140014010  mov     eax, edx
0x140014012  lea     rcx, [rax+rax*2]
0x140014016  cmp     r11d, 0FFFFFFFFh
0x14001401a  jnz     loc_1400140ED
0x140014020  mov     eax, [rdi+rcx*4+94h]
0x140014027  cmp     eax, r11d
0x14001402a  jz      loc_1400140FD
0x140014030  test    eax, eax
0x140014032  jnz     loc_140014108
0x140014038  inc     r8d
0x14001403b  inc     dword ptr [r10+108h]
0x140014042  inc     edx
0x140014044  mov     eax, [rbx+60h]
0x140014047  cmp     edx, eax
0x140014049  jb      short loc_140014010
0x14001404b  cmp     r9d, 0FFFFFFFFh
0x14001404f  jnz     short loc_140014062
0x140014051  cmp     [rdi+88h], eax
0x140014057  jz      loc_14001424F
0x14001405d  mov     [rdi+4], esi
0x140014060  jmp     short loc_140014070
0x140014062  mov     [rdi+4], r9d
0x140014066  cmp     r9d, 1
0x14001406a  jnz     loc_14001417E
0x140014070  mov     eax, esi
0x140014072  jmp     short loc_140014079
0x140014074  mov     eax, 0C0000001h
0x140014079  mov     [rbx+44h], eax
0x14001407c  inc     dword ptr [r10+0F8h]
0x140014083  mov     eax, [rbx+54h]
0x140014086  add     [r10+100h], rax
0x14001408d  cmp     [rbx+44h], esi
0x140014090  jl      loc_140014172
0x140014096  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001409d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400140a4  jnz     short loc_14001411A
0x1400140a6  mov     rcx, [rbx+48h]; Mdl
0x1400140aa  test    rcx, rcx
0x1400140ad  jz      short loc_1400140DF
0x1400140af  mov     r8, [rbx+30h]
0x1400140b3  movzx   eax, word ptr [r8+2]
0x1400140b8  cmp     eax, 38h ; '8'
0x1400140bb  jz      short def_14001421B; jumptable 000000014001421B default case, cases 8-56
0x1400140bd  add     eax, 0FFFFFFF8h; switch 51 cases
0x1400140c0  cmp     eax, 32h
0x1400140c3  jbe     loc_140014207
0x1400140c9  cmp     rcx, [r8+30h]; jumptable 000000014001421B default case, cases 8-56
0x1400140cd  jz      short loc_1400140DF
0x1400140cf  call    cs:__imp_IoFreeMdl; jumptable 000000014001421B cases 57,58
0x1400140d6  nop     dword ptr [rax+rax+00h]
0x1400140db  mov     [rbx+48h], rsi
0x1400140df  mov     [rbx+10h], sil
0x1400140e3  add     rsp, 78h
0x1400140e7  pop     rdi
0x1400140e8  pop     rsi
0x1400140e9  pop     rbp
0x1400140ea  pop     rbx
0x1400140eb  retn
0x1400140ed  mov     [rdi+rcx*4+94h], r11d
0x1400140f5  mov     eax, r11d
0x1400140f8  jmp     loc_140014030
0x1400140fd  mov     dword ptr [rdi+rcx*4+94h], 0C0020000h
0x140014108  inc     dword ptr [rdi+88h]
0x14001410e  inc     dword ptr [r10+10Ch]
0x140014115  jmp     loc_14001403B
0x14001411a  mov     rax, [r10+30h]
0x14001411e  mov     rcx, [r10+38h]
0x140014122  movzx   edx, byte ptr [rax+8Fh]
0x140014129  mov     eax, [rbx+54h]
0x14001412c  mov     [rsp+98h+var_38], eax
0x140014130  mov     eax, [rbx+60h]
0x140014133  mov     [rsp+98h+var_40], eax
0x140014137  mov     eax, [rdi+80h]
0x14001413d  mov     [rsp+98h+var_48], r8d
0x140014142  mov     [rsp+98h+var_50], eax
0x140014146  mov     eax, [rbx+44h]
0x140014149  mov     [rsp+98h+var_58], eax
0x14001414d  mov     rax, [rbx+18h]
0x140014151  mov     [rsp+98h+var_60], rax
0x140014156  mov     eax, [rcx+98h]
0x14001415c  mov     rcx, [rcx+50h]
0x140014160  mov     [rsp+98h+var_68], eax
0x140014164  mov     [rsp+98h+var_70], edx
0x140014168  call    WPP_RECORDER_SF_DDqdDDDD
0x14001416d  jmp     loc_1400140A6
0x140014172  inc     dword ptr [r10+0FCh]
0x140014179  jmp     loc_140014096
0x14001417e  cmp     r9d, 0C0000E00h
0x140014185  jle     short loc_1400141BA
0x140014187  cmp     r9d, 0C0010000h
0x14001418e  jnz     short loc_14001419A
0x140014190  mov     eax, 0C0000120h
0x140014195  jmp     loc_140014079
0x14001419a  cmp     r9d, 0C0001000h
0x1400141a1  jz      short loc_1400141C6
0x1400141a3  cmp     r9d, 0C0007000h
0x1400141aa  jnz     loc_140014241
0x1400141b0  mov     eax, 0C000000Eh
0x1400141b5  jmp     loc_140014079
0x1400141ba  jnz     short loc_1400141D0
0x1400141bc  mov     eax, 0C00000BBh
0x1400141c1  jmp     loc_140014079
0x1400141c6  mov     eax, 0C000009Ah
0x1400141cb  jmp     loc_140014079
0x1400141d0  cmp     r9d, 0C0000A00h
0x1400141d7  jnz     short loc_140014221
0x1400141d9  mov     eax, 0C000000Dh
0x1400141de  jmp     loc_140014079
0x1400141e3  cdqe
0x1400141e5  movzx   eax, ds:(byte_140064B51 - 140000000h)[rax+rbp]
0x1400141ed  mov     ecx, ss:(jpt_1400141F7 - 140000000h)[rbp+rax*4]
0x1400141f4  add     rcx, rbp
0x1400141f7  jmp     rcx; switch jump
0x1400141fd  mov     ecx, 34h ; '4'; jumptable 00000001400141F7 cases 57,58
0x140014202  jmp     loc_140013FF7
0x140014207  cdqe
0x140014209  movzx   eax, ds:(byte_140064B90 - 140000000h)[rax+rbp]
0x140014211  mov     edx, ss:(jpt_14001421B - 140000000h)[rbp+rax*4]
0x140014218  add     rdx, rbp
0x14001421b  jmp     rdx; switch jump
0x140014221  cmp     r9d, 80000200h
0x140014228  jz      short loc_1400141D9
0x14001422a  cmp     r9d, 80000300h
0x140014231  jz      short loc_1400141D9
0x140014233  cmp     r9d, 80000600h
0x14001423a  jz      short loc_1400141D9
0x14001423c  jmp     loc_140014074
0x140014241  test    r9d, r9d
0x140014244  jz      loc_140014070
0x14001424a  jmp     loc_140014074
0x14001424f  mov     dword ptr [rdi+4], 0C0000B00h
0x140014256  jmp     loc_140014074
```
