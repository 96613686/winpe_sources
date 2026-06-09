# sqlite3GetToken

- ea: `0x18004f7c8`
- end: `0x18004ff8b`
- name: `sqlite3GetToken`
- size: `1987`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180021404`
- `0x18004f744`
- `0x18007eb3c`
- `0x18009bf50`

## callees

- `0x18004f7c8`
- `0x18004ffa0`

## pseudocode

```c
__int64 __fastcall sqlite3GetToken(unsigned __int8 *a1, int *a2)
{
  __int64 v2; // rdi
  int v3; // ebx
  unsigned int v6; // r8d
  unsigned int v7; // r8d
  int i; // r11d
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  unsigned int v20; // r8d
  bool v21; // zf
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  __int64 v24; // rcx
  unsigned __int8 v25; // cl
  int j; // edx
  unsigned __int8 v27; // al
  unsigned int v28; // r8d
  unsigned int v29; // r8d
  unsigned int v30; // ecx
  int v31; // edx
  __int64 v32; // r11
  unsigned int v33; // r8d
  unsigned int v34; // r8d
  __int64 v35; // rax
  int v36; // r9d
  __int64 v37; // rdx
  __int64 v38; // rax
  int v39; // edx
  unsigned __int8 v40; // cl
  unsigned __int8 v41; // al
  unsigned __int8 v42; // al
  int v43; // eax
  char v44; // al
  int v45; // edx
  int v46; // ecx
  int v47; // eax
  unsigned __int8 *v48; // rax
  unsigned int v49; // r8d
  unsigned int v50; // r8d
  unsigned int v51; // r8d
  unsigned int v52; // r8d
  unsigned int v53; // r8d
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rcx

  v2 = *a1;
  v3 = 0;
  v6 = *((unsigned __int8 *)qword_1800C1040 + v2);
  if ( v6 > 0xF )
  {
    if ( (_BYTE)v6 == 23 )
    {
      *a2 = 25;
      return 1;
    }
    if ( (unsigned __int8)v6 > 0x17u )
    {
      v49 = v6 - 24;
      if ( !v49 )
      {
        *a2 = 102;
        return 1;
      }
      v50 = v49 - 1;
      if ( !v50 )
      {
        *a2 = 114;
        return 1;
      }
      v51 = v50 - 1;
      if ( !v51 )
      {
        if ( (*((_BYTE *)&qword_1800B4FF0 + a1[1]) & 4) != 0 )
          goto LABEL_33;
        *a2 = 141;
        return 1;
      }
      v52 = v51 - 1;
      if ( !v52 )
        goto LABEL_160;
      v53 = v52 - 2;
      if ( !v53 )
      {
        v14 = 0;
        goto LABEL_159;
      }
      if ( v53 == 1 )
      {
        if ( a1[1] == 0xBB && a1[2] == 0xBF )
        {
          *a2 = 184;
          return 3;
        }
        goto LABEL_160;
      }
    }
    else
    {
      v10 = v6 - 16;
      if ( !v10 )
      {
        if ( a1[1] == 42 && a1[2] )
        {
          v47 = a1[2];
          for ( i = 3; ; ++i )
          {
            if ( v47 == 42 )
            {
              v48 = &a1[i];
              if ( *v48 == 47 )
              {
                ++i;
LABEL_143:
                *a2 = 184;
                return (unsigned int)i;
              }
            }
            else
            {
              v48 = &a1[i];
            }
            v47 = *v48;
            if ( !v47 )
              goto LABEL_143;
          }
        }
        *a2 = 109;
        return 1;
      }
      v11 = v10 - 1;
      if ( !v11 )
      {
        *a2 = 22;
        return 1;
      }
      v12 = v11 - 1;
      if ( !v12 )
      {
        *a2 = 23;
        return 1;
      }
      v13 = v12 - 1;
      if ( !v13 )
      {
        v14 = 1;
        *a2 = 1;
        return v14;
      }
      v33 = v13 - 1;
      if ( !v33 )
      {
        *a2 = 106;
        return 1;
      }
      v34 = v33 - 1;
      if ( !v34 )
      {
        *a2 = 108;
        return 1;
      }
      if ( v34 == 1 )
      {
        *a2 = 110;
        return 1;
      }
    }
    goto LABEL_157;
  }
  if ( v6 == 15 )
  {
    if ( a1[1] == 61 )
      goto LABEL_132;
LABEL_157:
    v14 = 1;
LABEL_159:
    *a2 = 185;
    return v14;
  }
  if ( v6 == 7 )
  {
    for ( i = 1; (*((_BYTE *)&qword_1800B4FF0 + a1[i]) & 1) != 0; ++i )
      ;
    *a2 = 184;
    return (unsigned int)i;
  }
  if ( v6 > 7 )
  {
    v15 = v6 - 8;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( !v16 )
      {
        v45 = *a1;
        i = 1;
        if ( (_DWORD)v2 != 93 )
        {
          do
          {
            v45 = a1[i];
            if ( !(_BYTE)v45 )
              break;
            ++i;
          }
          while ( v45 != 93 );
        }
        v46 = 59;
        if ( v45 != 93 )
          v46 = 185;
        *a2 = v46;
        return (unsigned int)i;
      }
      v17 = v16 - 1;
      if ( !v17 )
      {
        if ( a1[1] == 124 )
        {
          *a2 = 111;
          return 2;
        }
        *a2 = 103;
        return 1;
      }
      v18 = v17 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          v20 = v19 - 1;
          if ( v20 )
          {
            if ( v20 == 1 )
            {
              v21 = a1[1] == 61;
              *a2 = 53;
              LOBYTE(v3) = v21;
              return (unsigned int)(v3 + 1);
            }
            goto LABEL_157;
          }
          v27 = a1[1];
          if ( v27 == 61 )
          {
            *a2 = 57;
            return 2;
          }
          if ( v27 == 62 )
          {
            *a2 = 105;
            return 2;
          }
          *a2 = 54;
          return 1;
        }
        v41 = a1[1];
        if ( v41 == 61 )
        {
          *a2 = 55;
          return 2;
        }
        if ( v41 != 62 )
        {
          if ( v41 == 60 )
          {
            *a2 = 104;
            return 2;
          }
          *a2 = 56;
          return 1;
        }
LABEL_132:
        *a2 = 52;
        return 2;
      }
      v42 = a1[1];
      if ( v42 != 45 )
      {
        if ( v42 == 62 )
        {
          v44 = a1[2] - 62;
          *a2 = 112;
          return 3 - (unsigned int)(v44 != 0);
        }
        *a2 = 107;
        return 1;
      }
      v43 = a1[2];
      for ( j = 2; a1[j]; v43 = a1[++j] )
      {
        if ( v43 == 10 )
          break;
      }
      *a2 = 184;
      return (unsigned int)j;
    }
    v25 = a1[1];
    j = 1;
    while ( v25 )
    {
      if ( v25 == (_BYTE)v2 )
      {
        if ( a1[j + 1] != (_BYTE)v2 )
          break;
        ++j;
      }
      v25 = a1[++j];
    }
    if ( v25 == 39 )
    {
      *a2 = 117;
    }
    else
    {
      if ( !v25 )
      {
        *a2 = 185;
        return (unsigned int)j;
      }
      *a2 = 59;
    }
    return (unsigned int)(j + 1);
  }
  if ( !*((_BYTE *)qword_1800C1040 + v2) )
  {
    if ( a1[1] == 39 )
    {
      v38 = a1[2];
      *a2 = 154;
      v39 = 2;
      if ( (*((_BYTE *)&qword_1800B4FF0 + v38) & 8) != 0 )
      {
        do
          ++v39;
        while ( (*((_BYTE *)&qword_1800B4FF0 + a1[v39]) & 8) != 0 );
      }
      v40 = a1[v39];
      if ( v40 != 39 || (v39 & 1) != 0 )
      {
        *a2 = 185;
        if ( v40 )
        {
          do
          {
            if ( a1[v39] == 39 )
              break;
            ++v39;
          }
          while ( a1[v39] );
        }
      }
      v30 = v39 + 1;
      if ( !a1[v39] )
        return (unsigned int)v39;
      return v30;
    }
LABEL_160:
    i = 1;
    goto LABEL_55;
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    v22 = v7 - 1;
    if ( !v22 )
      goto LABEL_160;
    v23 = v22 - 1;
    if ( !v23 )
    {
LABEL_33:
      *a2 = 155;
      if ( (_BYTE)v2 == 48 && ((a1[1] - 88) & 0xDF) == 0 && (*((_BYTE *)&qword_1800B4FF0 + a1[2]) & 8) != 0 )
      {
        for ( i = 3; ; ++i )
        {
          v54 = a1[i];
          if ( (*((_BYTE *)&qword_1800B4FF0 + v54) & 8) == 0 )
          {
            if ( (_BYTE)v54 != 95 )
              goto LABEL_39;
            *a2 = 183;
          }
        }
      }
      for ( i = 0; ; ++i )
      {
        v24 = a1[i];
        if ( (*((_BYTE *)&qword_1800B4FF0 + v24) & 4) == 0 )
        {
          if ( (_BYTE)v24 != 95 )
          {
            if ( (_BYTE)v24 == 46 )
            {
              if ( *a2 == 155 )
                *a2 = 153;
              while ( 1 )
              {
                do
                  v55 = a1[++i];
                while ( (*((_BYTE *)&qword_1800B4FF0 + v55) & 4) != 0 );
                if ( (_BYTE)v55 != 95 )
                  break;
                *a2 = 183;
              }
            }
            if ( ((a1[i] - 69) & 0xDF) == 0 )
            {
              v56 = a1[i + 1];
              if ( (*((_BYTE *)&qword_1800B4FF0 + v56) & 4) != 0
                || (((_BYTE)v56 - 43) & 0xFD) == 0 && (*((_BYTE *)&qword_1800B4FF0 + a1[i + 2]) & 4) != 0 )
              {
                if ( *a2 == 155 )
                  *a2 = 153;
                for ( i += 2; ; ++i )
                {
                  v57 = a1[i];
                  if ( (*((_BYTE *)&qword_1800B4FF0 + v57) & 4) == 0 )
                  {
                    if ( (_BYTE)v57 != 95 )
                      break;
                    *a2 = 183;
                  }
                }
              }
            }
LABEL_39:
            if ( (*((_BYTE *)&qword_1800B4FF0 + a1[i]) & 0x46) != 0 )
            {
              *a2 = 185;
              do
                ++i;
              while ( (*((_BYTE *)&qword_1800B4FF0 + a1[i]) & 0x46) != 0 );
            }
            return (unsigned int)i;
          }
          *a2 = 183;
        }
      }
    }
    v28 = v23 - 1;
    if ( !v28 || (v29 = v28 - 1) == 0 )
    {
      *a2 = 156;
      v30 = 1;
      v31 = 0;
      while ( 1 )
      {
        v32 = a1[v30];
        if ( !(_BYTE)v32 )
          break;
        if ( (*((_BYTE *)&qword_1800B4FF0 + v32) & 0x46) != 0 )
        {
          ++v31;
        }
        else
        {
          if ( (_BYTE)v32 == 40 && v31 > 0 )
          {
            do
            {
              v37 = a1[++v30];
              if ( !(_BYTE)v37 )
                goto LABEL_73;
            }
            while ( (*((_BYTE *)&qword_1800B4FF0 + v37) & 1) == 0 && (_BYTE)v37 != 41 );
            if ( (_BYTE)v37 == 41 )
              return ++v30;
LABEL_73:
            *a2 = 185;
            return v30;
          }
          if ( (_BYTE)v32 != 58 || a1[v30 + 1] != 58 )
            break;
          ++v30;
        }
        ++v30;
      }
      if ( !v31 )
        goto LABEL_73;
      return v30;
    }
    if ( v29 == 1 )
    {
      v35 = a1[1];
      v36 = 1;
      *a2 = 156;
      if ( (*((_BYTE *)&qword_1800B4FF0 + v35) & 4) != 0 )
      {
        do
          ++v36;
        while ( (*((_BYTE *)&qword_1800B4FF0 + a1[v36]) & 4) != 0 );
      }
      return (unsigned int)v36;
    }
    goto LABEL_157;
  }
  if ( *((_BYTE *)qword_1800C1040 + a1[1]) > 2u )
    goto LABEL_160;
  for ( i = 2; *((_BYTE *)qword_1800C1040 + a1[i]) <= 2u; ++i )
    ;
  if ( (*((_BYTE *)&qword_1800B4FF0 + a1[i]) & 0x46) != 0 )
  {
    do
    {
      ++i;
LABEL_55:
      ;
    }
    while ( (*((_BYTE *)&qword_1800B4FF0 + a1[i]) & 0x46) != 0 );
    *a2 = 59;
    return (unsigned int)i;
  }
  *a2 = 59;
  return keywordCode(a1, (unsigned int)i, a2);
}

```

## disassembly

```asm
0x18004f7c8  mov     [rsp+arg_0], rbx
0x18004f7cd  mov     [rsp+arg_8], rbp
0x18004f7d2  push    rdi
0x18004f7d3  sub     rsp, 20h
0x18004f7d7  movzx   edi, byte ptr [rcx]
0x18004f7da  lea     rbp, __ImageBase
0x18004f7e1  xor     ebx, ebx
0x18004f7e3  mov     r9, rdx
0x18004f7e6  mov     r10, rcx
0x18004f7e9  movzx   r8d, byte ptr [rdi+rbp+0C1040h]
0x18004f7f2  cmp     r8d, 0Fh
0x18004f7f6  ja      loc_18004F8C3
0x18004f7fc  jz      loc_18004FD77
0x18004f802  cmp     r8d, 7
0x18004f806  jz      loc_18004F89C
0x18004f80c  ja      loc_18004F909
0x18004f812  test    r8d, r8d
0x18004f815  jz      loc_18004FBC5
0x18004f81b  sub     r8d, 1
0x18004f81f  jnz     loc_18004F966
0x18004f825  movzx   eax, byte ptr [rcx+1]
0x18004f829  lea     edx, [rbx+2]
0x18004f82c  lea     r8d, [rbx+1]
0x18004f830  cmp     [rax+rbp+0C1040h], dl
0x18004f837  ja      loc_18004FE6D
0x18004f83d  movzx   eax, byte ptr [rcx+2]
0x18004f841  mov     r11d, edx
0x18004f844  cmp     [rax+rbp+0C1040h], dl
0x18004f84b  ja      short loc_18004F861
0x18004f84d  add     r11d, r8d
0x18004f850  movsxd  rax, r11d
0x18004f853  movzx   ecx, byte ptr [rax+r10]
0x18004f858  cmp     [rcx+rbp+0C1040h], dl
0x18004f85f  jbe     short loc_18004F84D
0x18004f861  movsxd  rax, r11d
0x18004f864  movzx   ecx, byte ptr [rax+r10]
0x18004f869  test    byte ptr [rcx+rbp+0B4FF0h], 46h
0x18004f871  jnz     loc_18004FA6C
0x18004f877  mov     r8, r9
0x18004f87a  mov     dword ptr [r9], 3Bh ; ';'
0x18004f881  mov     edx, r11d
0x18004f884  mov     rcx, r10
0x18004f887  call    keywordCode
0x18004f88c  mov     rbx, [rsp+28h+arg_0]
0x18004f891  mov     rbp, [rsp+28h+arg_8]
0x18004f896  add     rsp, 20h
0x18004f89a  pop     rdi
0x18004f89b  retn
0x18004f89c  movzx   eax, byte ptr [rcx+1]
0x18004f8a0  mov     r8d, 1
0x18004f8a6  mov     r11d, r8d
0x18004f8a9  test    [rax+rbp+0B4FF0h], r8b
0x18004f8b1  jnz     loc_18004FC45
0x18004f8b7  mov     dword ptr [r9], 0B8h
0x18004f8be  mov     eax, r11d
0x18004f8c1  jmp     short loc_18004F88C
0x18004f8c3  cmp     r8b, 17h
0x18004f8c7  jz      loc_18004FA64
0x18004f8cd  ja      loc_18004FE0A
0x18004f8d3  sub     r8d, 10h
0x18004f8d7  jz      loc_18004FDB7
0x18004f8dd  sub     r8d, 1
0x18004f8e1  jz      loc_18004FA54
0x18004f8e7  sub     r8d, 1
0x18004f8eb  jz      loc_18004FDAC
0x18004f8f1  sub     r8d, 1
0x18004f8f5  jnz     loc_18004FAE6
0x18004f8fb  mov     r8d, 1
0x18004f901  mov     [rdx], r8d
0x18004f904  mov     eax, r8d
0x18004f907  jmp     short loc_18004F88C
0x18004f909  sub     r8d, 8
0x18004f90d  jz      loc_18004FA0F
0x18004f913  sub     r8d, 1
0x18004f917  jz      loc_18004FD32
0x18004f91d  sub     r8d, 1
0x18004f921  jz      loc_18004FD16
0x18004f927  sub     r8d, 1
0x18004f92b  jz      loc_18004FCAD
0x18004f931  sub     r8d, 1
0x18004f935  jz      loc_18004FC79
0x18004f93b  sub     r8d, 1
0x18004f93f  jz      loc_18004FA8D
0x18004f945  cmp     r8d, 1
0x18004f949  jnz     loc_18004FE51
0x18004f94f  cmp     byte ptr [rcx+1], 3Dh ; '='
0x18004f953  mov     eax, r8d
0x18004f956  mov     dword ptr [rdx], 35h ; '5'
0x18004f95c  setz    bl
0x18004f95f  add     eax, ebx
0x18004f961  jmp     loc_18004F88C
0x18004f966  sub     r8d, 1
0x18004f96a  jz      loc_18004FE67
0x18004f970  sub     r8d, 1
0x18004f974  jnz     loc_18004FAA8
0x18004f97a  mov     edx, 9Bh
0x18004f97f  mov     [r9], edx
0x18004f982  cmp     dil, 30h ; '0'
0x18004f986  jz      loc_18004FE92
0x18004f98c  mov     r11d, ebx
0x18004f98f  mov     r8d, 1
0x18004f995  mov     ebx, 0B7h
0x18004f99a  movsxd  rax, r11d
0x18004f99d  movzx   ecx, byte ptr [rax+r10]
0x18004f9a2  test    byte ptr [rcx+rbp+0B4FF0h], 4
0x18004f9aa  jnz     loc_18004FEE5
0x18004f9b0  cmp     cl, 5Fh ; '_'
0x18004f9b3  jz      loc_18004FEE2
0x18004f9b9  mov     edi, 99h
0x18004f9be  cmp     cl, 2Eh ; '.'
0x18004f9c1  jz      loc_18004FEED
0x18004f9c7  movsxd  rcx, r11d
0x18004f9ca  mov     al, [rcx+r10]
0x18004f9ce  sub     al, 45h ; 'E'
0x18004f9d0  test    al, 0DFh
0x18004f9d2  jz      loc_18004FF18
0x18004f9d8  movsxd  rax, r11d
0x18004f9db  movzx   ecx, byte ptr [rax+r10]
0x18004f9e0  test    byte ptr [rcx+rbp+0B4FF0h], 46h
0x18004f9e8  jz      loc_18004F8BE
0x18004f9ee  mov     dword ptr [r9], 0B9h
0x18004f9f5  add     r11d, r8d
0x18004f9f8  movsxd  rcx, r11d
0x18004f9fb  movzx   edx, byte ptr [rcx+r10]
0x18004fa00  test    byte ptr [rdx+rbp+0B4FF0h], 46h
0x18004fa08  jnz     short loc_18004F9F5
0x18004fa0a  jmp     loc_18004F8BE
0x18004fa0f  mov     cl, [rcx+1]
0x18004fa12  mov     r8d, 1
0x18004fa18  mov     edx, r8d
0x18004fa1b  jmp     short loc_18004FA30
0x18004fa1d  cmp     cl, dil
0x18004fa20  jz      loc_18004FB65
0x18004fa26  add     edx, r8d
0x18004fa29  movsxd  rax, edx
0x18004fa2c  mov     cl, [rax+r10]
0x18004fa30  test    cl, cl
0x18004fa32  jnz     short loc_18004FA1D
0x18004fa34  cmp     cl, 27h ; '''
0x18004fa37  jz      loc_18004FD6B
0x18004fa3d  test    cl, cl
0x18004fa3f  jz      loc_18004FCE2
0x18004fa45  mov     dword ptr [r9], 3Bh ; ';'
0x18004fa4c  lea     eax, [rdx+1]
0x18004fa4f  jmp     loc_18004F88C
0x18004fa54  mov     dword ptr [rdx], 16h
0x18004fa5a  mov     eax, 1
0x18004fa5f  jmp     loc_18004F88C
0x18004fa64  mov     dword ptr [rdx], 19h
0x18004fa6a  jmp     short loc_18004FA5A
0x18004fa6c  add     r11d, r8d
0x18004fa6f  movsxd  rax, r11d
0x18004fa72  movzx   ecx, byte ptr [rax+r10]
0x18004fa77  test    byte ptr [rcx+rbp+0B4FF0h], 46h
0x18004fa7f  jnz     short loc_18004FA6C
0x18004fa81  mov     dword ptr [r9], 3Bh ; ';'
0x18004fa88  jmp     loc_18004F8BE
0x18004fa8d  mov     al, [rcx+1]
0x18004fa90  cmp     al, 3Dh ; '='
0x18004fa92  jnz     loc_18004FC5F
0x18004fa98  mov     dword ptr [rdx], 39h ; '9'
0x18004fa9e  mov     eax, 2
0x18004faa3  jmp     loc_18004F88C
0x18004faa8  sub     r8d, 1
0x18004faac  jz      short loc_18004FAB4
0x18004faae  sub     r8d, 1
0x18004fab2  jnz     short loc_18004FB27
0x18004fab4  mov     r8d, 1
0x18004faba  mov     dword ptr [r9], 9Ch
0x18004fac1  mov     ecx, r8d
0x18004fac4  mov     edx, ebx
0x18004fac6  movsxd  rax, ecx
0x18004fac9  movzx   r11d, byte ptr [rax+r10]
0x18004face  test    r11b, r11b
0x18004fad1  jz      short loc_18004FB15
0x18004fad3  test    byte ptr [r11+rbp+0B4FF0h], 46h
0x18004fadc  jz      short loc_18004FB05
0x18004fade  add     edx, r8d
0x18004fae1  add     ecx, r8d
0x18004fae4  jmp     short loc_18004FAC6
0x18004fae6  sub     r8d, 1
0x18004faea  jz      loc_18004FDA1
0x18004faf0  sub     r8d, 1
0x18004faf4  jnz     loc_18004FD8C
0x18004fafa  mov     dword ptr [rdx], 6Ch ; 'l'
0x18004fb00  jmp     loc_18004FA5A
0x18004fb05  cmp     r11b, 28h ; '('
0x18004fb09  jz      short loc_18004FB7B
0x18004fb0b  cmp     r11b, 3Ah ; ':'
0x18004fb0f  jz      loc_18004FBAE
0x18004fb15  test    edx, edx
0x18004fb17  jnz     short loc_18004FB20
0x18004fb19  mov     dword ptr [r9], 0B9h
0x18004fb20  mov     eax, ecx
0x18004fb22  jmp     loc_18004F88C
0x18004fb27  cmp     r8d, 1
0x18004fb2b  jnz     loc_18004FE51
0x18004fb31  movzx   eax, byte ptr [rcx+1]
0x18004fb35  mov     r9d, r8d
0x18004fb38  mov     dword ptr [rdx], 9Ch
0x18004fb3e  test    byte ptr [rax+rbp+0B4FF0h], 4
0x18004fb46  jz      short loc_18004FB5D
0x18004fb48  add     r9d, r8d
0x18004fb4b  movsxd  rcx, r9d
0x18004fb4e  movzx   edx, byte ptr [rcx+r10]
0x18004fb53  test    byte ptr [rdx+rbp+0B4FF0h], 4
0x18004fb5b  jnz     short loc_18004FB48
0x18004fb5d  mov     eax, r9d
0x18004fb60  jmp     loc_18004F88C
0x18004fb65  movsxd  rax, edx
0x18004fb68  cmp     [rax+r10+1], dil
0x18004fb6d  jnz     loc_18004FA34
0x18004fb73  add     edx, r8d
0x18004fb76  jmp     loc_18004FA26
0x18004fb7b  test    edx, edx
0x18004fb7d  jle     short loc_18004FB0B
0x18004fb7f  add     ecx, r8d
0x18004fb82  movsxd  rax, ecx
0x18004fb85  movzx   edx, byte ptr [rax+r10]
0x18004fb8a  test    dl, dl
0x18004fb8c  jz      short loc_18004FB19
0x18004fb8e  test    [rdx+rbp+0B4FF0h], r8b
0x18004fb96  jnz     short loc_18004FB9D
0x18004fb98  cmp     dl, 29h ; ')'
0x18004fb9b  jnz     short loc_18004FB7F
0x18004fb9d  cmp     dl, 29h ; ')'
0x18004fba0  jnz     loc_18004FB19
0x18004fba6  add     ecx, r8d
0x18004fba9  jmp     loc_18004FB20
0x18004fbae  movsxd  rax, ecx
0x18004fbb1  cmp     byte ptr [rax+r10+1], 3Ah ; ':'
0x18004fbb7  jnz     loc_18004FB15
0x18004fbbd  add     ecx, r8d
0x18004fbc0  jmp     loc_18004FAE1
0x18004fbc5  cmp     byte ptr [rcx+1], 27h ; '''
0x18004fbc9  jnz     loc_18004FE67
0x18004fbcf  movzx   eax, byte ptr [rcx+2]
0x18004fbd3  mov     dword ptr [rdx], 9Ah
0x18004fbd9  mov     edx, 2
0x18004fbde  test    byte ptr [rax+rbp+0B4FF0h], 8
0x18004fbe6  lea     r8d, [rdx-1]
0x18004fbea  jz      short loc_18004FC01
0x18004fbec  add     edx, r8d
0x18004fbef  movsxd  rax, edx
0x18004fbf2  movzx   ecx, byte ptr [rax+r10]
0x18004fbf7  test    byte ptr [rcx+rbp+0B4FF0h], 8
0x18004fbff  jnz     short loc_18004FBEC
0x18004fc01  movsxd  rax, edx
0x18004fc04  mov     cl, [rax+r10]
0x18004fc08  cmp     cl, 27h ; '''
0x18004fc0b  jnz     short loc_18004FC12
0x18004fc0d  test    r8b, dl
0x18004fc10  jz      short loc_18004FC33
0x18004fc12  mov     dword ptr [r9], 0B9h
0x18004fc19  test    cl, cl
0x18004fc1b  jz      short loc_18004FC33
0x18004fc1d  movsxd  rax, edx
0x18004fc20  cmp     byte ptr [rax+r10], 27h ; '''
0x18004fc25  jz      short loc_18004FC33
0x18004fc27  add     edx, r8d
0x18004fc2a  movsxd  rax, edx
0x18004fc2d  cmp     [rax+r10], bl
0x18004fc31  jnz     short loc_18004FC1D
0x18004fc33  movsxd  rax, edx
0x18004fc36  lea     ecx, [rdx+1]
0x18004fc39  cmp     [rax+r10], bl
0x18004fc3d  cmovz   ecx, edx
0x18004fc40  jmp     loc_18004FB20
0x18004fc45  add     r11d, r8d
0x18004fc48  movsxd  rcx, r11d
0x18004fc4b  movzx   edx, byte ptr [rcx+r10]
0x18004fc50  test    [rdx+rbp+0B4FF0h], r8b
0x18004fc58  jnz     short loc_18004FC45
0x18004fc5a  jmp     loc_18004F8B7
0x18004fc5f  cmp     al, 3Eh ; '>'
0x18004fc61  jnz     short loc_18004FC6E
0x18004fc63  mov     dword ptr [rdx], 69h ; 'i'
0x18004fc69  jmp     loc_18004FA9E
0x18004fc6e  mov     dword ptr [rdx], 36h ; '6'
0x18004fc74  jmp     loc_18004FA5A
0x18004fc79  mov     al, [rcx+1]
0x18004fc7c  cmp     al, 3Dh ; '='
0x18004fc7e  jnz     short loc_18004FC8B
0x18004fc80  mov     dword ptr [rdx], 37h ; '7'
0x18004fc86  jmp     loc_18004FA9E
0x18004fc8b  cmp     al, 3Eh ; '>'
0x18004fc8d  jz      loc_18004FD81
0x18004fc93  cmp     al, 3Ch ; '<'
0x18004fc95  jnz     short loc_18004FCA2
0x18004fc97  mov     dword ptr [rdx], 68h ; 'h'
0x18004fc9d  jmp     loc_18004FA9E
0x18004fca2  mov     dword ptr [rdx], 38h ; '8'
0x18004fca8  jmp     loc_18004FA5A
0x18004fcad  mov     al, [rcx+1]
0x18004fcb0  cmp     al, 2Dh ; '-'
0x18004fcb2  jnz     short loc_18004FCF0
0x18004fcb4  movzx   eax, byte ptr [rcx+2]
0x18004fcb8  mov     edx, 2
0x18004fcbd  test    eax, eax
0x18004fcbf  jz      short loc_18004FCD9
  ... truncated ...
```
