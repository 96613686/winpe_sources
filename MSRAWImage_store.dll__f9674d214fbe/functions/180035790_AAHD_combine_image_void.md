# AAHD::combine_image(void)

- ea: `0x180035790`
- end: `0x1800359ef`
- name: `?combine_image@AAHD@@QEAAXXZ`
- size: `607`
- prototype: `void __fastcall(AAHD *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180035690`

## callees

- `0x18002b500`
- `0x180035790`

## pseudocode

```c
void __fastcall AAHD::combine_image(AAHD *this)
{
  __int64 v2; // rcx
  int v3; // esi
  __int64 v4; // rbp
  int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // r13
  char v8; // r8
  __int64 v9; // r14
  __int64 v10; // r15
  __int64 v11; // r12
  unsigned int v12; // eax
  int v13; // eax
  __int16 v14; // r9
  int v15; // edx
  char v16; // r8
  char v17; // cl
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rdx

  v2 = *((_QWORD *)this + 15);
  v3 = 0;
  if ( *(_WORD *)(v2 + 28) )
  {
    v4 = 0;
    do
    {
      v5 = 0;
      v6 = v2;
      if ( *(_WORD *)(v2 + 30) )
      {
        v7 = 8 * v4;
        v8 = 2 * (v3 & 7);
        v9 = *((_DWORD *)this + 1) * (v3 + 4) + 4;
        v10 = 6 * v9;
        v11 = 3 * v9;
        do
        {
          if ( (*(_BYTE *)(v9 + *((_QWORD *)this + 5)) & 8) != 0 )
          {
            v12 = *(_DWORD *)(v2 + 544);
            if ( v12 )
            {
              if ( v12 >= 0x3E8 )
              {
                if ( *(_WORD *)(v2 + 381350) )
                {
                  v14 = *(_WORD *)(v2 + 381350);
                  if ( *(_DWORD *)(v2 + 381504) )
                  {
                    v15 = v5 + ((v3 + 1) >> 1);
                    v16 = v14 + (v3 >> 1) - v5;
                  }
                  else
                  {
                    v15 = v3 + ((v5 + 1) >> 1);
                    v16 = v3 + v14 - (v5 >> 1);
                  }
                  v17 = (2 * (v15 & 1)) | (4 * v16 - 1) & 0x1C;
                }
                else
                {
                  v17 = 2 * (v8 | v5 & 1);
                }
                v13 = (v12 >> v17) & 3;
              }
              else
              {
                v13 = LibRaw::fcol((LibRaw *)v2, v3, v5);
              }
            }
            else
            {
              v13 = 6;
            }
            v18 = 2 * (v13 + v11);
            *(_WORD *)(v18 + *((_QWORD *)this + 1)) = *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 15) + 8LL)
                                                               + 2 * (v13 + 4 * v4));
            *(_WORD *)(v18 + *((_QWORD *)this + 2)) = *(_WORD *)(v18 + *((_QWORD *)this + 1));
            v2 = *((_QWORD *)this + 15);
            v8 = 2 * (v3 & 7);
          }
          v19 = *(_QWORD *)(v2 + 8);
          if ( (*(_BYTE *)(v9 + *((_QWORD *)this + 5)) & 4) != 0 )
          {
            *(_WORD *)(v19 + v7) = *(_WORD *)(v10 + *((_QWORD *)this + 2));
            *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 15) + 8LL) + 8 * v4 + 2) = *(_WORD *)(v10
                                                                                          + *((_QWORD *)this + 2)
                                                                                          + 2);
            *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 15) + 8LL) + 8 * v4 + 6) = *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 15) + 8LL)
                                                                                          + 8 * v4
                                                                                          + 2);
            v20 = *((_QWORD *)this + 2);
          }
          else
          {
            *(_WORD *)(v19 + 8 * v4) = *(_WORD *)(v10 + *((_QWORD *)this + 1));
            *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 15) + 8LL) + 8 * v4 + 2) = *(_WORD *)(*((_QWORD *)this + 1)
                                                                                          + v10
                                                                                          + 2);
            *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 15) + 8LL) + 8 * v4 + 6) = *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 15) + 8LL)
                                                                                          + 8 * v4
                                                                                          + 2);
            v20 = *((_QWORD *)this + 1);
          }
          *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 15) + 8LL) + 8 * v4 + 4) = *(_WORD *)(v10 + v20 + 4);
          ++v5;
          v6 = *((_QWORD *)this + 15);
          ++v9;
          v11 += 3;
          v10 += 6;
          ++v4;
          v7 += 8;
          v2 = v6;
        }
        while ( v5 < *(unsigned __int16 *)(v6 + 30) );
      }
      ++v3;
      v2 = v6;
    }
    while ( v3 < *(unsigned __int16 *)(v6 + 28) );
  }
}

```

## disassembly

```asm
0x180035790  push    rbx
0x180035792  push    rsi
0x180035793  sub     rsp, 38h
0x180035797  xor     eax, eax
0x180035799  mov     rbx, rcx
0x18003579c  mov     rcx, [rcx+78h]; this
0x1800357a0  mov     esi, eax
0x1800357a2  cmp     ax, [rcx+1Ch]
0x1800357a6  jnb     loc_1800359E8
0x1800357ac  mov     [rsp+48h+arg_8], rbp
0x1800357b1  mov     ebp, eax
0x1800357b3  mov     [rsp+48h+arg_10], rdi
0x1800357b8  mov     [rsp+48h+arg_18], r12
0x1800357bd  mov     [rsp+48h+var_18], r13
0x1800357c2  mov     [rsp+48h+var_20], r14
0x1800357c7  mov     [rsp+48h+var_28], r15
0x1800357cc  nop     dword ptr [rax+00h]
0x1800357d0  mov     edi, eax
0x1800357d2  mov     rdx, rcx
0x1800357d5  cmp     ax, [rcx+1Eh]
0x1800357d9  jnb     loc_1800359B4
0x1800357df  mov     eax, esi
0x1800357e1  lea     r13, ds:0[rbp*8]
0x1800357e9  and     eax, 7
0x1800357ec  lea     r8d, [rax+rax]
0x1800357f0  lea     eax, [rsi+4]
0x1800357f3  mov     [rsp+48h+arg_0], r8d
0x1800357f8  imul    eax, [rbx+4]
0x1800357fc  add     eax, 4
0x1800357ff  movsxd  r14, eax
0x180035802  lea     r15, [r14+r14*2]
0x180035806  add     r15, r15
0x180035809  lea     r12, [r14+r14*2]
0x18003580d  nop     dword ptr [rax]
0x180035810  mov     rax, [rbx+28h]
0x180035814  test    byte ptr [r14+rax], 8
0x180035819  jz      loc_1800358E6
0x18003581f  mov     eax, [rcx+220h]
0x180035825  test    eax, eax
0x180035827  jnz     short loc_180035830
0x180035829  mov     eax, 6
0x18003582e  jmp     short loc_1800358A7
0x180035830  cmp     eax, 3E8h
0x180035835  jnb     short loc_180035843
0x180035837  mov     r8d, edi; int
0x18003583a  mov     edx, esi; int
0x18003583c  call    ?fcol@LibRaw@@QEAAHHH@Z; LibRaw::fcol(int,int)
0x180035841  jmp     short loc_1800358A7
0x180035843  movzx   edx, word ptr [rcx+5D1A6h]
0x18003584a  test    dx, dx
0x18003584d  jz      short loc_180035898
0x18003584f  cmp     dword ptr [rcx+5D240h], 0
0x180035856  mov     r9d, edx
0x180035859  jz      short loc_180035870
0x18003585b  lea     edx, [rsi+1]
0x18003585e  mov     r8d, esi
0x180035861  sar     edx, 1
0x180035863  sar     r8d, 1
0x180035866  add     edx, edi
0x180035868  sub     r8d, edi
0x18003586b  add     r8d, r9d
0x18003586e  jmp     short loc_180035884
0x180035870  lea     edx, [rdi+1]
0x180035873  mov     ecx, edi
0x180035875  sar     edx, 1
0x180035877  mov     r8d, r9d
0x18003587a  sar     ecx, 1
0x18003587c  add     edx, esi
0x18003587e  sub     r8d, ecx
0x180035881  add     r8d, esi
0x180035884  and     edx, 1
0x180035887  lea     ecx, ds:0FFFFFFFFFFFFFFFFh[r8*4]
0x18003588f  and     ecx, 1Ch
0x180035892  add     edx, edx
0x180035894  or      ecx, edx
0x180035896  jmp     short loc_1800358A2
0x180035898  mov     ecx, edi
0x18003589a  and     ecx, 1
0x18003589d  or      ecx, r8d
0x1800358a0  add     ecx, ecx
0x1800358a2  shr     eax, cl
0x1800358a4  and     eax, 3
0x1800358a7  movsxd  rcx, eax
0x1800358aa  lea     rax, [rcx+r12]
0x1800358ae  lea     r8, [rax+rax]
0x1800358b2  mov     rax, [rbx+78h]
0x1800358b6  lea     rdx, [rcx+rbp*4]
0x1800358ba  mov     rcx, [rbx+8]
0x1800358be  mov     rax, [rax+8]
0x1800358c2  movzx   eax, word ptr [rax+rdx*2]
0x1800358c6  mov     [r8+rcx], ax
0x1800358cb  mov     rax, [rbx+8]
0x1800358cf  mov     rcx, [rbx+10h]
0x1800358d3  movzx   eax, word ptr [r8+rax]
0x1800358d8  mov     [r8+rcx], ax
0x1800358dd  mov     rcx, [rbx+78h]
0x1800358e1  mov     r8d, [rsp+48h+arg_0]
0x1800358e6  mov     rax, [rbx+28h]
0x1800358ea  mov     rcx, [rcx+8]
0x1800358ee  test    byte ptr [r14+rax], 4
0x1800358f3  jz      short loc_180035940
0x1800358f5  mov     rax, [rbx+10h]
0x1800358f9  movzx   eax, word ptr [r15+rax]
0x1800358fe  mov     [rcx+r13], ax
0x180035903  mov     rax, [rbx+78h]
0x180035907  mov     rdx, [rbx+10h]
0x18003590b  mov     rcx, [rax+8]
0x18003590f  movzx   eax, word ptr [r15+rdx+2]
0x180035915  mov     [rcx+rbp*8+2], ax
0x18003591a  mov     rax, [rbx+78h]
0x18003591e  mov     rcx, [rax+8]
0x180035922  movzx   eax, word ptr [rcx+rbp*8+2]
0x180035927  mov     [rcx+rbp*8+6], ax
0x18003592c  mov     rax, [rbx+78h]
0x180035930  mov     rdx, [rbx+10h]
0x180035934  mov     rcx, [rax+8]
0x180035938  movzx   eax, word ptr [r15+rdx+4]
0x18003593e  jmp     short loc_180035988
0x180035940  mov     rax, [rbx+8]
0x180035944  movzx   eax, word ptr [r15+rax]
0x180035949  mov     [rcx+rbp*8], ax
0x18003594d  mov     rax, [rbx+78h]
0x180035951  mov     rdx, [rbx+8]
0x180035955  mov     rcx, [rax+8]
0x180035959  movzx   eax, word ptr [rdx+r15+2]
0x18003595f  mov     [rcx+rbp*8+2], ax
0x180035964  mov     rax, [rbx+78h]
0x180035968  mov     rcx, [rax+8]
0x18003596c  movzx   eax, word ptr [rcx+rbp*8+2]
0x180035971  mov     [rcx+rbp*8+6], ax
0x180035976  mov     rax, [rbx+78h]
0x18003597a  mov     rdx, [rbx+8]
0x18003597e  mov     rcx, [rax+8]
0x180035982  movzx   eax, word ptr [rdx+r15+4]
0x180035988  mov     [rcx+rbp*8+4], ax
0x18003598d  inc     edi
0x18003598f  mov     rdx, [rbx+78h]
0x180035993  inc     r14
0x180035996  add     r12, 3
0x18003599a  add     r15, 6
0x18003599e  inc     rbp
0x1800359a1  add     r13, 8
0x1800359a5  mov     rcx, rdx
0x1800359a8  movzx   eax, word ptr [rdx+1Eh]
0x1800359ac  cmp     edi, eax
0x1800359ae  jl      loc_180035810
0x1800359b4  movzx   eax, word ptr [rdx+1Ch]
0x1800359b8  inc     esi
0x1800359ba  cmp     esi, eax
0x1800359bc  mov     rcx, rdx
0x1800359bf  mov     eax, 0
0x1800359c4  jl      loc_1800357D0
0x1800359ca  mov     r15, [rsp+48h+var_28]
0x1800359cf  mov     r14, [rsp+48h+var_20]
0x1800359d4  mov     r13, [rsp+48h+var_18]
0x1800359d9  mov     r12, [rsp+48h+arg_18]
0x1800359de  mov     rdi, [rsp+48h+arg_10]
0x1800359e3  mov     rbp, [rsp+48h+arg_8]
0x1800359e8  add     rsp, 38h
0x1800359ec  pop     rsi
0x1800359ed  pop     rbx
0x1800359ee  retn
```
