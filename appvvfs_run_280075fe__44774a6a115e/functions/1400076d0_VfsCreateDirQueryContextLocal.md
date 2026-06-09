# VfsCreateDirQueryContextLocal

- ea: `0x1400076d0`
- end: `0x140007833`
- name: `VfsCreateDirQueryContextLocal`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140006a60`

## callees

- `0x14000748c`
- `0x1400076d0`
- `0x14000783c`

## pseudocode

```c
__int64 __fastcall VfsCreateDirQueryContextLocal(
        struct _FLT_INSTANCE *a1,
        struct _FLT_INSTANCE *a2,
        struct _FLT_INSTANCE *a3,
        struct _FLT_INSTANCE *a4,
        unsigned int a5,
        __int64 a6,
        _OWORD *a7)
{
  int v9; // esi
  _OWORD *v10; // rdi
  char *v11; // rbx
  unsigned int v12; // r12d
  __int64 *v13; // rcx
  __int64 v14; // rax
  __int64 *v15; // rcx
  __int64 v16; // rax
  __int64 v18; // [rsp+80h] [rbp+8h] BYREF

  v18 = 0;
  if ( (!a1 || !a2) && (!a3 || !a4) )
    return 3221225485LL;
  v9 = 0;
  v10 = a7;
  *a7 = 0;
  v10[1] = 0;
  v10[2] = 0;
  *((_QWORD *)v10 + 6) = 0;
  v11 = (char *)v10 + 8;
  *((_QWORD *)v10 + 2) = (char *)v10 + 8;
  *((_QWORD *)v10 + 1) = (char *)v10 + 8;
  *(_DWORD *)v10 = 1;
  v12 = a5;
  *((_DWORD *)v10 + 6) = a5;
  *((_DWORD *)v10 + 8) = 2;
  if ( !a1 || !a2 )
    goto LABEL_11;
  v9 = VfsCreateDirQuerySubContext(a1, 0, a2, v12, 0, &v18);
  if ( v9 >= 0 )
  {
    v13 = (__int64 *)*((_QWORD *)v10 + 2);
    if ( (char *)*v13 != v11 )
      __fastfail(3u);
    v14 = v18;
    *(_QWORD *)v18 = v11;
    *(_QWORD *)(v14 + 8) = v13;
    *v13 = v14;
    *((_QWORD *)v10 + 2) = v14;
    ++*((_DWORD *)v10 + 7);
LABEL_11:
    if ( a3 )
    {
      if ( a4 )
      {
        v9 = VfsCreateDirQuerySubContext(a3, 0, a4, v12, 1, &v18);
        if ( v9 >= 0 )
        {
          v15 = (__int64 *)*((_QWORD *)v10 + 2);
          if ( (char *)*v15 != v11 )
            __fastfail(3u);
          v16 = v18;
          *(_QWORD *)v18 = v11;
          *(_QWORD *)(v16 + 8) = v15;
          *v15 = v16;
          *((_QWORD *)v10 + 2) = v16;
          ++*((_DWORD *)v10 + 7);
        }
      }
    }
  }
  if ( v9 < 0 )
    VfsCleanupDirQueryContext(v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400076d0  mov     rax, rsp
0x1400076d3  push    rbx
0x1400076d4  push    rsi
0x1400076d5  push    rdi
0x1400076d6  push    r12
0x1400076d8  push    r14
0x1400076da  push    r15
0x1400076dc  sub     rsp, 48h
0x1400076e0  mov     r14, r9
0x1400076e3  mov     r15, r8
0x1400076e6  mov     qword ptr [rax+8], 0
0x1400076ee  test    rcx, rcx
0x1400076f1  jz      short loc_1400076F8
0x1400076f3  test    rdx, rdx
0x1400076f6  jnz     short loc_14000770A
0x1400076f8  test    r15, r15
0x1400076fb  jz      loc_14000781F
0x140007701  test    r14, r14
0x140007704  jz      loc_14000781F
0x14000770a  xor     esi, esi
0x14000770c  mov     [rsp+78h+var_48], esi
0x140007710  xorps   xmm0, xmm0
0x140007713  xor     eax, eax
0x140007715  mov     rdi, [rsp+78h+arg_30]
0x14000771d  movups  xmmword ptr [rdi], xmm0
0x140007720  movups  xmmword ptr [rdi+10h], xmm0
0x140007724  movups  xmmword ptr [rdi+20h], xmm0
0x140007728  mov     [rdi+30h], rax
0x14000772c  lea     rbx, [rdi+8]
0x140007730  mov     [rbx+8], rbx
0x140007734  mov     [rbx], rbx
0x140007737  mov     dword ptr [rdi], 1
0x14000773d  mov     r12d, [rsp+78h+arg_20]
0x140007745  mov     [rdi+18h], r12d
0x140007749  mov     dword ptr [rdi+20h], 2
0x140007750  test    rcx, rcx
0x140007753  jz      short loc_1400077B0
0x140007755  test    rdx, rdx
0x140007758  jz      short loc_1400077B0
0x14000775a  lea     rax, [rsp+78h+arg_0]
0x140007762  mov     [rsp+78h+var_50], rax; __int64
0x140007767  mov     [rsp+78h+var_58], sil; char
0x14000776c  mov     r9d, r12d
0x14000776f  mov     r8, rdx
0x140007772  xor     edx, edx
0x140007774  call    VfsCreateDirQuerySubContext
0x140007779  mov     esi, eax
0x14000777b  mov     [rsp+78h+var_48], eax
0x14000777f  test    eax, eax
0x140007781  js      loc_14000780F
0x140007787  mov     rcx, [rbx+8]
0x14000778b  cmp     [rcx], rbx
0x14000778e  jz      short loc_140007797
0x140007790  mov     ecx, 3
0x140007795  int     29h; Win8: RtlFailFast(ecx)
0x140007797  mov     rax, [rsp+78h+arg_0]
0x14000779f  mov     [rax], rbx
0x1400077a2  mov     [rax+8], rcx
0x1400077a6  mov     [rcx], rax
0x1400077a9  mov     [rbx+8], rax
0x1400077ad  inc     dword ptr [rdi+1Ch]
0x1400077b0  test    r15, r15
0x1400077b3  jz      short loc_14000780F
0x1400077b5  test    r14, r14
0x1400077b8  jz      short loc_14000780F
0x1400077ba  lea     rax, [rsp+78h+arg_0]
0x1400077c2  mov     [rsp+78h+var_50], rax; __int64
0x1400077c7  mov     [rsp+78h+var_58], 1; char
0x1400077cc  mov     r9d, r12d
0x1400077cf  mov     r8, r14
0x1400077d2  xor     edx, edx
0x1400077d4  mov     rcx, r15; FltObject
0x1400077d7  call    VfsCreateDirQuerySubContext
0x1400077dc  mov     esi, eax
0x1400077de  mov     [rsp+78h+var_48], eax
0x1400077e2  test    eax, eax
0x1400077e4  js      short loc_14000780F
0x1400077e6  mov     rcx, [rbx+8]
0x1400077ea  cmp     [rcx], rbx
0x1400077ed  jz      short loc_1400077F6
0x1400077ef  mov     ecx, 3
0x1400077f4  int     29h; Win8: RtlFailFast(ecx)
0x1400077f6  mov     rax, [rsp+78h+arg_0]
0x1400077fe  mov     [rax], rbx
0x140007801  mov     [rax+8], rcx
0x140007805  mov     [rcx], rax
0x140007808  mov     [rbx+8], rax
0x14000780c  inc     dword ptr [rdi+1Ch]
0x14000780f  test    esi, esi
0x140007811  jns     short loc_14000781B
0x140007813  mov     rcx, rdi
0x140007816  call    VfsCleanupDirQueryContext
0x14000781b  mov     eax, esi
0x14000781d  jmp     short loc_140007824
0x14000781f  mov     eax, 0C000000Dh
0x140007824  add     rsp, 48h
0x140007828  pop     r15
0x14000782a  pop     r14
0x14000782c  pop     r12
0x14000782e  pop     rdi
0x14000782f  pop     rsi
0x140007830  pop     rbx
0x140007831  retn
0x140014bf4  push    rbp
0x140014bf6  sub     rsp, 30h
0x140014bfa  mov     rbp, rdx
0x140014bfd  cmp     dword ptr [rbp+30h], 0
0x140014c01  jge     short loc_140014C10
0x140014c03  mov     rcx, [rbp+0B0h]
0x140014c0a  call    VfsCleanupDirQueryContext
0x140014c0f  nop
0x140014c10  add     rsp, 30h
0x140014c14  pop     rbp
0x140014c15  retn
```
