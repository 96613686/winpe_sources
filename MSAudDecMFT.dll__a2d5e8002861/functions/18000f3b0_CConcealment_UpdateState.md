# CConcealment_UpdateState

- ea: `0x18000f3b0`
- end: `0x18000f699`
- name: `CConcealment_UpdateState`
- size: `745`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000ef70`

## callees

- `0x18000f3b0`
- `0x180073038`
- `0x180073258`

## pseudocode

```c
void __fastcall CConcealment_UpdateState(_QWORD *a1, int a2, int a3, int a4, __int64 a5)
{
  _QWORD *v6; // r11
  _DWORD *v7; // rcx
  int v8; // edi
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax
  int v17; // eax
  int v18; // edx
  int v19; // edx
  int v20; // edx
  int v21; // edx
  __int64 v22; // rdx
  int EquiFadeFrame; // eax

  v6 = a1;
  v7 = (_DWORD *)*a1;
  v8 = a4;
  if ( v7[64] != 1 )
  {
    if ( (unsigned int)(v7[64] - 2) > 1 )
      return;
    v10 = *((_DWORD *)v6 + 20);
    if ( !v10 )
    {
      if ( !*((_DWORD *)v6 + 10) && (!*((_DWORD *)v6 + 9) || !a2) )
      {
        *((_DWORD *)v6 + 20) = (v7[65] > 0) + 3;
        *((_DWORD *)v6 + 14) = 0;
        *(_QWORD *)((char *)v6 + 44) = 0;
      }
      return;
    }
    v15 = 1;
    if ( *((_DWORD *)v6 + 10) || *((_DWORD *)v6 + 9) && a2 )
      ++*((_DWORD *)v6 + 11);
    else
      *((_DWORD *)v6 + 11) = 0;
    v11 = v10 - 1;
    if ( !v11 )
    {
LABEL_12:
      *((_DWORD *)v6 + 20) = 0;
      return;
    }
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        if ( v13 != 1 )
          return;
        v14 = *((unsigned int *)v6 + 12);
        *((_DWORD *)v6 + 12) = v14 + 1;
        if ( *((_DWORD *)v6 + 11) > v7[67] )
        {
          *((_DWORD *)v6 + 14) = 0;
          if ( (int)v7[66] <= 0 )
            goto LABEL_12;
          goto LABEL_18;
        }
        if ( (int)v14 + 1 < v7[65] )
          return;
        goto LABEL_21;
      }
      if ( *((_DWORD *)v6 + 11) <= v7[67] )
        return;
      *((_DWORD *)v6 + 14) = 0;
LABEL_24:
      if ( (int)v7[66] <= 0 )
        goto LABEL_12;
      *((_DWORD *)v6 + 20) = 2;
      v16 = v7[66] - 1;
LABEL_26:
      *((_DWORD *)v6 + 12) = v16;
      return;
    }
    v14 = *((unsigned int *)v6 + 12);
    v17 = v14 - 1;
    *((_DWORD *)v6 + 12) = v14 - 1;
    if ( !a2 && !*((_DWORD *)v6 + 10) )
    {
      if ( (int)v7[65] > 0 )
      {
        *((_DWORD *)v6 + 20) = 4;
        goto LABEL_19;
      }
      goto LABEL_21;
    }
LABEL_55:
    if ( v17 >= 0 )
      return;
    goto LABEL_12;
  }
  v18 = *((_DWORD *)v6 + 20);
  if ( !v18 )
  {
    if ( a2 )
      return;
    *(_QWORD *)((char *)v6 + 44) = 0;
    *(_QWORD *)((char *)v6 + 60) = 0;
    *(_QWORD *)((char *)v6 + 52) = 0;
    if ( (int)v7[65] <= 0 )
      goto LABEL_21;
    *((_DWORD *)v6 + 20) = 1;
    goto LABEL_63;
  }
  if ( a2 )
    ++*((_DWORD *)v6 + 11);
  else
    *((_DWORD *)v6 + 11) = 0;
  v19 = v18 - 1;
  if ( !v19 )
  {
    if ( a2 )
      goto LABEL_12;
    if ( *((_DWORD *)v6 + 12) >= v7[65] )
      goto LABEL_21;
    *((_DWORD *)v6 + 20) = 4;
    goto LABEL_63;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
    v22 = *((unsigned int *)v6 + 12);
    v17 = v22 - 1;
    *((_DWORD *)v6 + 12) = v22 - 1;
    if ( a2 )
      goto LABEL_55;
    if ( (int)v7[65] <= 0 )
      goto LABEL_21;
    *((_DWORD *)v6 + 20) = 4;
    EquiFadeFrame = findEquiFadeFrame(v7, v22, 1);
    *(_QWORD *)((char *)v6 + 52) = 0;
    *(_QWORD *)((char *)v6 + 60) = 0;
    a4 = v8;
    *((_DWORD *)v6 + 12) = EquiFadeFrame - 1;
LABEL_63:
    CConcealment_ApplyFadeOut(0, (_DWORD)v6, a3, a4, a5);
    return;
  }
  v21 = v20 - 1;
  if ( v21 )
  {
    if ( v21 != 1 )
      return;
    if ( *((_DWORD *)v6 + 11) > v7[67] )
    {
      if ( (int)v7[66] <= 0 )
        goto LABEL_12;
      v14 = *((unsigned int *)v6 + 12);
LABEL_18:
      v15 = 0;
      *((_DWORD *)v6 + 20) = 2;
LABEL_19:
      v16 = findEquiFadeFrame(v7, v14, v15);
      goto LABEL_26;
    }
    if ( a2 )
    {
      *(_QWORD *)((char *)v6 + 52) = 0;
      *(_QWORD *)((char *)v6 + 60) = 0;
    }
    if ( *((_DWORD *)v6 + 12) >= v7[65] )
    {
LABEL_21:
      *((_DWORD *)v6 + 20) = 3;
      return;
    }
    goto LABEL_63;
  }
  if ( *((_DWORD *)v6 + 11) > v7[67] )
    goto LABEL_24;
  if ( a2 )
  {
    *(_QWORD *)((char *)v6 + 52) = 0;
    *(_QWORD *)((char *)v6 + 60) = 0;
  }
}

```

## disassembly

```asm
0x18000f3b0  mov     [rsp+arg_0], rbx
0x18000f3b5  mov     [rsp+arg_8], rsi
0x18000f3ba  push    rdi
0x18000f3bb  sub     rsp, 30h
0x18000f3bf  mov     r10d, edx
0x18000f3c2  mov     r11, rcx
0x18000f3c5  mov     rcx, [rcx]
0x18000f3c8  mov     edi, r9d
0x18000f3cb  mov     rsi, r8
0x18000f3ce  mov     edx, [rcx+100h]
0x18000f3d4  sub     edx, 1
0x18000f3d7  jz      loc_18000F542
0x18000f3dd  sub     edx, 1
0x18000f3e0  jz      short loc_18000F3E7
0x18000f3e2  cmp     edx, 1
0x18000f3e5  jnz     short loc_18000F3FB
0x18000f3e7  mov     edx, [r11+50h]
0x18000f3eb  xor     ebx, ebx
0x18000f3ed  test    edx, edx
0x18000f3ef  jnz     short loc_18000F456
0x18000f3f1  cmp     [r11+28h], ebx
0x18000f3f5  jz      loc_18000F514
0x18000f3fb  mov     rbx, [rsp+38h+arg_0]
0x18000f400  mov     rsi, [rsp+38h+arg_8]
0x18000f405  add     rsp, 30h
0x18000f409  pop     rdi
0x18000f40a  retn
0x18000f40c  test    edx, edx
0x18000f40e  jz      short loc_18000F3F1
0x18000f410  sub     edx, r8d
0x18000f413  jz      short loc_18000F450
0x18000f415  sub     edx, r8d
0x18000f418  jz      loc_18000F4E9
0x18000f41e  sub     edx, r8d
0x18000f421  jz      loc_18000F4B3
0x18000f427  cmp     edx, r8d
0x18000f42a  jnz     short loc_18000F3FB
0x18000f42c  mov     edx, [r11+30h]
0x18000f430  lea     r8d, [rdx+1]
0x18000f434  mov     [r11+30h], r8d
0x18000f438  mov     eax, [rcx+10Ch]
0x18000f43e  cmp     [r11+2Ch], eax
0x18000f442  jle     short loc_18000F499
0x18000f444  mov     [r11+38h], ebx
0x18000f448  cmp     [rcx+108h], ebx
0x18000f44e  jg      short loc_18000F47D
0x18000f450  mov     [r11+50h], ebx
0x18000f454  jmp     short loc_18000F3FB
0x18000f456  mov     r8d, 1
0x18000f45c  cmp     [r11+28h], ebx
0x18000f460  jnz     short loc_18000F473
0x18000f462  cmp     [r11+24h], ebx
0x18000f466  jz      short loc_18000F46D
0x18000f468  test    r10d, r10d
0x18000f46b  jnz     short loc_18000F473
0x18000f46d  mov     [r11+2Ch], ebx
0x18000f471  jmp     short loc_18000F40C
0x18000f473  add     [r11+2Ch], r8d
0x18000f477  jmp     short loc_18000F40C
0x18000f479  mov     edx, [r11+30h]
0x18000f47d  xor     r8d, r8d
0x18000f480  mov     dword ptr [r11+50h], 2
0x18000f488  jmp     short loc_18000F492
0x18000f48a  mov     dword ptr [r11+50h], 4
0x18000f492  call    findEquiFadeFrame
0x18000f497  jmp     short loc_18000F4E0
0x18000f499  cmp     r8d, [rcx+104h]
0x18000f4a0  jl      loc_18000F3FB
0x18000f4a6  mov     dword ptr [r11+50h], 3
0x18000f4ae  jmp     loc_18000F3FB
0x18000f4b3  mov     eax, [rcx+10Ch]
0x18000f4b9  cmp     [r11+2Ch], eax
0x18000f4bd  jle     loc_18000F3FB
0x18000f4c3  mov     [r11+38h], ebx
0x18000f4c7  cmp     [rcx+108h], ebx
0x18000f4cd  jle     short loc_18000F450
0x18000f4cf  mov     dword ptr [r11+50h], 2
0x18000f4d7  mov     eax, [rcx+108h]
0x18000f4dd  sub     eax, r8d
0x18000f4e0  mov     [r11+30h], eax
0x18000f4e4  jmp     loc_18000F3FB
0x18000f4e9  mov     edx, [r11+30h]
0x18000f4ed  lea     eax, [rdx-1]
0x18000f4f0  mov     [r11+30h], eax
0x18000f4f4  test    r10d, r10d
0x18000f4f7  jnz     loc_18000F628
0x18000f4fd  cmp     [r11+28h], ebx
0x18000f501  jnz     loc_18000F628
0x18000f507  cmp     [rcx+104h], ebx
0x18000f50d  jle     short loc_18000F4A6
0x18000f50f  jmp     loc_18000F48A
0x18000f514  cmp     [r11+24h], ebx
0x18000f518  jz      short loc_18000F523
0x18000f51a  test    r10d, r10d
0x18000f51d  jnz     loc_18000F3FB
0x18000f523  cmp     [rcx+104h], ebx
0x18000f529  mov     eax, ebx
0x18000f52b  setnle  al
0x18000f52e  add     eax, 3
0x18000f531  mov     [r11+50h], eax
0x18000f535  mov     [r11+38h], ebx
0x18000f539  mov     [r11+2Ch], rbx
0x18000f53d  jmp     loc_18000F3FB
0x18000f542  mov     edx, [r11+50h]
0x18000f546  xor     ebx, ebx
0x18000f548  lea     r8d, [rbx+1]
0x18000f54c  test    edx, edx
0x18000f54e  jz      loc_18000F658
0x18000f554  test    r10d, r10d
0x18000f557  jz      short loc_18000F55F
0x18000f559  add     [r11+2Ch], r8d
0x18000f55d  jmp     short loc_18000F563
0x18000f55f  mov     [r11+2Ch], ebx
0x18000f563  test    edx, edx
0x18000f565  jz      loc_18000F658
0x18000f56b  sub     edx, r8d
0x18000f56e  jz      loc_18000F635
0x18000f574  sub     edx, r8d
0x18000f577  jz      short loc_18000F5EC
0x18000f579  sub     edx, r8d
0x18000f57c  jz      short loc_18000F5C6
0x18000f57e  cmp     edx, r8d
0x18000f581  jnz     loc_18000F3FB
0x18000f587  mov     eax, [rcx+10Ch]
0x18000f58d  cmp     [r11+2Ch], eax
0x18000f591  jle     short loc_18000F5A4
0x18000f593  cmp     [rcx+108h], ebx
0x18000f599  jle     loc_18000F450
0x18000f59f  jmp     loc_18000F479
0x18000f5a4  test    r10d, r10d
0x18000f5a7  jz      short loc_18000F5B1
0x18000f5a9  mov     [r11+34h], rbx
0x18000f5ad  mov     [r11+3Ch], rbx
0x18000f5b1  mov     eax, [rcx+104h]
0x18000f5b7  cmp     [r11+30h], eax
0x18000f5bb  jl      loc_18000F67D
0x18000f5c1  jmp     loc_18000F4A6
0x18000f5c6  mov     eax, [rcx+10Ch]
0x18000f5cc  cmp     [r11+2Ch], eax
0x18000f5d0  jg      loc_18000F4C7
0x18000f5d6  test    r10d, r10d
0x18000f5d9  jz      loc_18000F3FB
0x18000f5df  mov     [r11+34h], rbx
0x18000f5e3  mov     [r11+3Ch], rbx
0x18000f5e7  jmp     loc_18000F3FB
0x18000f5ec  mov     edx, [r11+30h]
0x18000f5f0  lea     eax, [rdx-1]
0x18000f5f3  mov     [r11+30h], eax
0x18000f5f7  test    r10d, r10d
0x18000f5fa  jnz     short loc_18000F628
0x18000f5fc  cmp     [rcx+104h], ebx
0x18000f602  jle     loc_18000F4A6
0x18000f608  mov     dword ptr [r11+50h], 4
0x18000f610  call    findEquiFadeFrame
0x18000f615  dec     eax
0x18000f617  mov     [r11+34h], rbx
0x18000f61b  mov     [r11+3Ch], rbx
0x18000f61f  mov     r9d, edi
0x18000f622  mov     [r11+30h], eax
0x18000f626  jmp     short loc_18000F67D
0x18000f628  test    eax, eax
0x18000f62a  js      loc_18000F450
0x18000f630  jmp     loc_18000F3FB
0x18000f635  test    r10d, r10d
0x18000f638  jnz     loc_18000F450
0x18000f63e  mov     eax, [rcx+104h]
0x18000f644  cmp     [r11+30h], eax
0x18000f648  jge     loc_18000F4A6
0x18000f64e  mov     dword ptr [r11+50h], 4
0x18000f656  jmp     short loc_18000F67D
0x18000f658  test    r10d, r10d
0x18000f65b  jnz     loc_18000F3FB
0x18000f661  mov     [r11+2Ch], rbx
0x18000f665  mov     [r11+3Ch], rbx
0x18000f669  mov     [r11+34h], rbx
0x18000f66d  cmp     [rcx+104h], ebx
0x18000f673  jle     loc_18000F4A6
0x18000f679  mov     [r11+50h], r8d
0x18000f67d  mov     rax, [rsp+38h+arg_20]
0x18000f682  mov     r8, rsi
0x18000f685  mov     rdx, r11
0x18000f688  mov     [rsp+38h+var_18], rax
0x18000f68d  xor     ecx, ecx
0x18000f68f  call    CConcealment_ApplyFadeOut
0x18000f694  jmp     loc_18000F3FB
```
