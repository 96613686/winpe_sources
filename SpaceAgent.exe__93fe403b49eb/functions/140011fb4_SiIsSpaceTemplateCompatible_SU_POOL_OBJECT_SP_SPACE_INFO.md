# SiIsSpaceTemplateCompatible(_SU_POOL_OBJECT *,_SP_SPACE_INFO *)

- ea: `0x140011fb4`
- end: `0x1400120fd`
- name: `?SiIsSpaceTemplateCompatible@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@@Z`
- size: `329`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, struct _SP_SPACE_INFO *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400111c4`
- `0x1400135c4`

## callees

- `0x140011fb4`
- `0x140012474`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1400120e8`
- `KERNEL32!SetLastError` at `0x1400120e8`

## pseudocode

```c
__int64 __fastcall SiIsSpaceTemplateCompatible(struct _SU_POOL_OBJECT *a1, struct _SP_SPACE_INFO *a2, __int64 a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  _DWORD *v6; // rcx
  __int64 v7; // rax

  v4 = 1;
  v5 = *((unsigned int *)a1 + 661);
  v6 = (_DWORD *)((char *)a2 + 2748);
  if ( (unsigned int)v5 <= 1 )
  {
    a3 = 0x2000000;
    if ( *v6 != 3 )
      a3 = 0;
    v7 = *((_QWORD *)a2 + 347);
    if ( v7 == -1 )
    {
      *((_QWORD *)a2 + 347) = a3;
    }
    else if ( v7 != a3 )
    {
LABEL_41:
      SetLastError(0x32u);
      return 0;
    }
    goto LABEL_9;
  }
  if ( (unsigned int)v5 <= 2 )
  {
LABEL_9:
    if ( *v6 == 3 && *((_DWORD *)a2 + 688) != 1 )
      goto LABEL_41;
LABEL_13:
    if ( !*((_QWORD *)a2 + 333) )
      goto LABEL_41;
    goto LABEL_16;
  }
  if ( (unsigned int)v5 <= 3 )
    goto LABEL_13;
  if ( (unsigned int)v5 <= 4 )
  {
LABEL_16:
    if ( *((_DWORD *)a2 + 690) != 1 || *v6 == 3 && *((_DWORD *)a2 + 681) != 1 )
      goto LABEL_41;
LABEL_21:
    if ( *((_DWORD *)a2 + 679) != 1 || (unsigned int)(*((_DWORD *)a2 + 681) - 1) > 1 )
      goto LABEL_41;
LABEL_25:
    if ( *((_BYTE *)a2 + 2600) > 3u )
      goto LABEL_41;
    goto LABEL_28;
  }
  if ( (unsigned int)v5 <= 0xB )
    goto LABEL_21;
  if ( (unsigned int)v5 <= 0xE )
    goto LABEL_25;
  if ( (unsigned int)v5 <= 0x15 )
  {
LABEL_28:
    if ( *v6 == 2 )
    {
      if ( *((_DWORD *)a2 + 689) == 4 )
        goto LABEL_41;
    }
    else if ( *v6 == 3 && *((_DWORD *)a2 + 689) > 1u )
    {
      goto LABEL_41;
    }
    goto LABEL_35;
  }
  if ( (unsigned int)v5 > 0x19 )
    goto LABEL_36;
LABEL_35:
  if ( *((_BYTE *)a2 + 2600) > 8u )
    goto LABEL_41;
LABEL_36:
  if ( ((unsigned int)v5 <= 0x1B || !(unsigned int)SuAreCacheLinesSupported((unsigned int)v5, v5, a3, 3))
    && (*((_QWORD *)a2 + 348) || *((_DWORD *)a2 + 700) > 1u || (*((_BYTE *)a2 + 2868) & 0x20) != 0) )
  {
    goto LABEL_41;
  }
  return v4;
}

```

## disassembly

```asm
0x140011fb4  mov     [rsp+arg_0], rbx
0x140011fb9  push    rdi
0x140011fba  sub     rsp, 20h
0x140011fbe  mov     rdi, rdx
0x140011fc1  mov     ebx, 1
0x140011fc6  mov     edx, [rcx+0A54h]
0x140011fcc  lea     rcx, [rdi+0ABCh]
0x140011fd3  lea     r9d, [rbx+2]
0x140011fd7  cmp     edx, ebx
0x140011fd9  ja      short loc_14001200B
0x140011fdb  xor     eax, eax
0x140011fdd  mov     r8d, 2000000h
0x140011fe3  cmp     [rcx], r9d
0x140011fe6  cmovnz  r8d, eax
0x140011fea  mov     rax, [rdi+0AD8h]
0x140011ff1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140011ff5  jnz     short loc_140012000
0x140011ff7  mov     [rdi+0AD8h], r8
0x140011ffe  jmp     short loc_140012010
0x140012000  cmp     rax, r8
0x140012003  jnz     loc_1400120E3
0x140012009  jmp     short loc_140012010
0x14001200b  cmp     edx, 2
0x14001200e  ja      short loc_140012022
0x140012010  cmp     [rcx], r9d
0x140012013  jnz     short loc_140012027
0x140012015  cmp     [rdi+0AC0h], ebx
0x14001201b  jz      short loc_140012027
0x14001201d  jmp     loc_1400120E3
0x140012022  cmp     edx, r9d
0x140012025  ja      short loc_140012036
0x140012027  cmp     qword ptr [rdi+0A68h], 0
0x14001202f  jnz     short loc_14001203B
0x140012031  jmp     loc_1400120E3
0x140012036  cmp     edx, 4
0x140012039  ja      short loc_140012059
0x14001203b  cmp     [rdi+0AC8h], ebx
0x140012041  jnz     loc_1400120E3
0x140012047  cmp     [rcx], r9d
0x14001204a  jnz     short loc_14001205E
0x14001204c  cmp     [rdi+0AA4h], ebx
0x140012052  jz      short loc_14001205E
0x140012054  jmp     loc_1400120E3
0x140012059  cmp     edx, 0Bh
0x14001205c  ja      short loc_140012074
0x14001205e  cmp     [rdi+0A9Ch], ebx
0x140012064  jnz     short loc_1400120E3
0x140012066  mov     eax, [rdi+0AA4h]
0x14001206c  sub     eax, ebx
0x14001206e  cmp     eax, ebx
0x140012070  jbe     short loc_140012079
0x140012072  jmp     short loc_1400120E3
0x140012074  cmp     edx, 0Eh
0x140012077  ja      short loc_140012084
0x140012079  cmp     [rdi+0A28h], r9b
0x140012080  jbe     short loc_140012089
0x140012082  jmp     short loc_1400120E3
0x140012084  cmp     edx, 15h
0x140012087  ja      short loc_1400120AA
0x140012089  mov     eax, [rcx]
0x14001208b  cmp     eax, 2
0x14001208e  jnz     short loc_14001209B
0x140012090  cmp     dword ptr [rdi+0AC4h], 4
0x140012097  jnz     short loc_1400120AF
0x140012099  jmp     short loc_1400120E3
0x14001209b  cmp     eax, r9d
0x14001209e  jnz     short loc_1400120AF
0x1400120a0  cmp     [rdi+0AC4h], ebx
0x1400120a6  jbe     short loc_1400120AF
0x1400120a8  jmp     short loc_1400120E3
0x1400120aa  cmp     edx, 19h
0x1400120ad  ja      short loc_1400120B8
0x1400120af  cmp     byte ptr [rdi+0A28h], 8
0x1400120b6  ja      short loc_1400120E3
0x1400120b8  cmp     edx, 1Bh
0x1400120bb  jbe     short loc_1400120C8
0x1400120bd  mov     ecx, edx
0x1400120bf  call    ?SuAreCacheLinesSupported@@YAHW4_SC_VERSION@@@Z; SuAreCacheLinesSupported(_SC_VERSION)
0x1400120c4  test    eax, eax
0x1400120c6  jnz     short loc_1400120F0
0x1400120c8  cmp     qword ptr [rdi+0AE0h], 0
0x1400120d0  ja      short loc_1400120E3
0x1400120d2  cmp     [rdi+0AF0h], ebx
0x1400120d8  ja      short loc_1400120E3
0x1400120da  test    byte ptr [rdi+0B34h], 20h
0x1400120e1  jz      short loc_1400120F0
0x1400120e3  mov     ecx, 32h ; '2'; dwErrCode
0x1400120e8  call    cs:__imp_SetLastError
0x1400120ee  xor     ebx, ebx
0x1400120f0  mov     eax, ebx
0x1400120f2  mov     rbx, [rsp+28h+arg_0]
0x1400120f7  add     rsp, 20h
0x1400120fb  pop     rdi
0x1400120fc  retn
```
