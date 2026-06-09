# HGetFeatureAttribute

- ea: `0x18002ac28`
- end: `0x18002b07a`
- name: `HGetFeatureAttribute`
- size: `1106`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned __int8 *, _DWORD *, void *, unsigned int, _DWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180022890`
- `0x18002d9d0`

## callees

- `0x18002ac28`
- `0x18002be80`
- `0x18002bf24`
- `0x180031044`
- `0x18005e0c4`

## string_xrefs

- `0x18002af1f`: `OpenUIType`
- `0x18002af77`: `OpenGroupType`

## pseudocode

```c
__int64 __fastcall HGetFeatureAttribute(
        __int64 a1,
        __int64 a2,
        const char *a3,
        char *a4,
        _DWORD *a5,
        void *a6,
        int a7,
        unsigned int *a8)
{
  __int64 v10; // rbp
  __int64 v11; // rdi
  unsigned int *KeywordMatchFeature; // rdx
  unsigned int v13; // eax
  _DWORD *v14; // rcx
  unsigned int v15; // r8d
  unsigned int v16; // eax
  _BYTE *v17; // rsi
  char **v18; // r14
  int v19; // ebp
  int v20; // r13d
  int v21; // r15d
  char *v22; // rdx
  __int64 v23; // r12
  unsigned int v24; // r12d
  char *v25; // rdx
  __int64 v26; // r12
  unsigned int v27; // r12d
  char *v29; // rax
  int v30; // r9d
  int v31; // r8d
  __int64 v32; // rdi
  unsigned int v33; // r8d
  int v34; // edx
  signed __int64 v35; // r8
  int v36; // ecx
  int v37; // eax
  unsigned int v38; // eax
  _DWORD *v39; // r8
  __int64 v40; // rdi
  char *v41; // rax
  int v42; // r10d
  int v43; // r9d
  __int64 v44; // rax
  char *v45; // rax
  int v46; // r10d
  int v47; // r9d
  char *v48; // rax
  int v49; // r9d
  int v50; // r8d
  signed __int64 v51; // r8
  int v52; // edx
  int v53; // eax
  unsigned int v54; // [rsp+98h] [rbp+10h] BYREF

  v54 = 0;
  if ( *(_DWORD *)(a1 + 56) )
    v10 = a1 + *(unsigned int *)(a1 + 56);
  else
    v10 = 0;
  if ( *(_DWORD *)(a1 + 60) )
    v11 = a1 + *(unsigned int *)(a1 + 60);
  else
    v11 = 0;
  if ( !v10 || !v11 )
    return 2147500037LL;
  if ( !a3 )
    return 2147942487LL;
  KeywordMatchFeature = PInternalGetKeywordMatchFeature(v10, a3, 0, &v54);
  if ( !KeywordMatchFeature )
    return 2147942487LL;
  v13 = *(_DWORD *)(v11 + 200);
  if ( v13 && (v14 = (_DWORD *)(a1 + v13)) != 0 && (v15 = *(_DWORD *)(v11 + 196), v16 = 0, v15) )
  {
    while ( v14[1] == 8 || v14[3] != v54 || v14[4] != 255 )
    {
      ++v16;
      v14 += 6;
      if ( v16 >= v15 )
        goto LABEL_18;
    }
  }
  else
  {
LABEL_18:
    v14 = 0;
  }
  if ( a4 )
  {
    if ( *a4 == 68 )
    {
      v29 = a4;
      do
      {
        v30 = (unsigned __int8)v29["DisplayName" - a4];
        v31 = (unsigned __int8)*v29 - v30;
        if ( v31 )
          break;
        ++v29;
      }
      while ( v30 );
      if ( !v31 )
      {
        if ( KeywordMatchFeature[3] )
        {
          v14 = (_DWORD *)(a1 + KeywordMatchFeature[3]);
          if ( v14 )
          {
            v32 = -1;
            do
              ++v32;
            while ( *((_WORD *)v14 + v32) );
            v33 = 2 * v32 + 2;
            v34 = 6;
            return HGetSingleData(v14, v34, v33, a5, a6, a7, a8);
          }
        }
        return 2147500037LL;
      }
      v35 = "DefaultOption" - a4;
      do
      {
        v36 = (unsigned __int8)a4[v35];
        v37 = (unsigned __int8)*a4 - v36;
        if ( v37 )
          break;
        ++a4;
      }
      while ( v36 );
      if ( !v37 )
      {
        v38 = KeywordMatchFeature[5];
        if ( v38 >= KeywordMatchFeature[13]
          || (v39 = (_DWORD *)(*(_QWORD *)(v10 + 328) + KeywordMatchFeature[14] + KeywordMatchFeature[12] * v38)) == 0 )
        {
          if ( !KeywordMatchFeature[13] )
            return 2147500037LL;
          v39 = (_DWORD *)(*(_QWORD *)(v10 + 328) + KeywordMatchFeature[14]);
          if ( !v39 )
            return 2147500037LL;
        }
        if ( *v39 )
          v14 = (_DWORD *)(a1 + (unsigned int)*v39);
        else
          v14 = 0;
        v40 = -1;
        do
          ++v40;
        while ( *((_BYTE *)v14 + v40) );
        goto LABEL_68;
      }
      return 2147942487LL;
    }
    if ( *a4 != 79 )
      return 2147942487LL;
    v41 = a4;
    do
    {
      v42 = (unsigned __int8)v41["OpenUIType" - a4];
      v43 = (unsigned __int8)*v41 - v42;
      if ( v43 )
        break;
      ++v41;
    }
    while ( v42 );
    if ( v43 )
    {
      v45 = a4;
      do
      {
        v46 = (unsigned __int8)v45["OpenGroupType" - a4];
        v47 = (unsigned __int8)*v45 - v46;
        if ( v47 )
          break;
        ++v45;
      }
      while ( v46 );
      if ( v47 )
      {
        v48 = a4;
        do
        {
          v49 = (unsigned __int8)v48["OrderDependencyValue" - a4];
          v50 = (unsigned __int8)*v48 - v49;
          if ( v50 )
            break;
          ++v48;
        }
        while ( v49 );
        if ( v50 )
        {
          v51 = "OrderDependencySection" - a4;
          do
          {
            v52 = (unsigned __int8)a4[v51];
            v53 = (unsigned __int8)*a4 - v52;
            if ( v53 )
              break;
            ++a4;
          }
          while ( v52 );
          if ( !v53 && v14 )
            return HGetOrderDepSection((__int64)v14, (__int64)a5, a6, a7, (__int64)a8);
        }
        else if ( v14 )
        {
          v34 = 3;
          v33 = 4;
          return HGetSingleData(v14, v34, v33, a5, a6, a7, a8);
        }
        return 2147942487LL;
      }
      v14 = (_DWORD *)(0x180000000LL + (KeywordMatchFeature[11] != 2 ? 422998LL : 422968LL));
      v40 = -1;
      do
        ++v40;
      while ( *((_BYTE *)v14 + v40) );
    }
    else
    {
      v44 = 0;
      if ( KeywordMatchFeature[8] <= 2 )
        v44 = KeywordMatchFeature[8];
      v14 = (_DWORD *)(0x180000000LL + 10 * v44 + 423032);
      v40 = -1;
      do
        ++v40;
      while ( *((_BYTE *)v14 + v40) );
    }
LABEL_68:
    v33 = v40 + 1;
    v34 = 5;
    return HGetSingleData(v14, v34, v33, a5, a6, a7, a8);
  }
  if ( a5 )
    *a5 = 5;
  v17 = a6;
  v18 = &off_180061C90;
  v19 = a7;
  v20 = 0;
  v21 = 6;
  if ( v14 )
  {
    do
    {
      v25 = *v18;
      v26 = -1;
      do
        ++v26;
      while ( v25[v26] );
      v27 = v26 + 1;
      if ( v17 && v19 >= (int)v27 )
      {
        memcpy_0(v17, v25, v27);
        v17 += v27;
      }
      v19 -= v27;
      v20 += v27;
      v18 += 2;
      --v21;
    }
    while ( v21 );
  }
  else
  {
    do
    {
      if ( !*((_DWORD *)v18 + 2) )
      {
        v22 = *v18;
        v23 = -1;
        do
          ++v23;
        while ( v22[v23] );
        v24 = v23 + 1;
        if ( v17 && v19 >= (int)v24 )
        {
          memcpy_0(v17, v22, v24);
          v17 += v24;
        }
        v19 -= v24;
        v20 += v24;
      }
      v18 += 2;
      --v21;
    }
    while ( v21 );
  }
  if ( a8 )
    *a8 = v20 + 1;
  if ( !v17 || v19 - 1 < 0 )
    return 2147942414LL;
  *v17 = 0;
  return 0;
}

```

## disassembly

```asm
0x18002ac28  mov     [rsp+arg_8], edx
0x18002ac2c  mov     r11, rsp
0x18002ac2f  push    rbx
0x18002ac30  push    rbp
0x18002ac31  push    rsi
0x18002ac32  push    rdi
0x18002ac33  push    r12
0x18002ac35  push    r13
0x18002ac37  push    r14
0x18002ac39  push    r15
0x18002ac3b  sub     rsp, 48h
0x18002ac3f  xor     r12d, r12d
0x18002ac42  mov     rbx, r9
0x18002ac45  mov     rax, r8
0x18002ac48  mov     rsi, rcx
0x18002ac4b  mov     [r11+10h], r12d
0x18002ac4f  cmp     [rcx+38h], r12d
0x18002ac53  jz      short loc_18002AC5D
0x18002ac55  mov     ebp, [rcx+38h]
0x18002ac58  add     rbp, rcx
0x18002ac5b  jmp     short loc_18002AC60
0x18002ac5d  mov     rbp, r12
0x18002ac60  cmp     [rcx+3Ch], r12d
0x18002ac64  jz      short loc_18002AC6E
0x18002ac66  mov     edi, [rcx+3Ch]
0x18002ac69  add     rdi, rsi
0x18002ac6c  jmp     short loc_18002AC71
0x18002ac6e  mov     rdi, r12
0x18002ac71  test    rbp, rbp
0x18002ac74  jz      loc_18002B063
0x18002ac7a  test    rdi, rdi
0x18002ac7d  jz      loc_18002B063
0x18002ac83  test    rax, rax
0x18002ac86  jz      loc_18002B05C
0x18002ac8c  lea     r9, [rsp+88h+arg_8]
0x18002ac94  xor     r8d, r8d
0x18002ac97  mov     rdx, rax
0x18002ac9a  mov     rcx, rbp
0x18002ac9d  call    PInternalGetKeywordMatchFeature
0x18002aca2  mov     rdx, rax
0x18002aca5  test    rax, rax
0x18002aca8  jz      loc_18002B05C
0x18002acae  mov     eax, [rdi+0C8h]
0x18002acb4  test    eax, eax
0x18002acb6  jz      short loc_18002ACF6
0x18002acb8  mov     ecx, eax
0x18002acba  add     rcx, rsi
0x18002acbd  jz      short loc_18002ACF6
0x18002acbf  mov     r8d, [rdi+0C4h]
0x18002acc6  mov     eax, r12d
0x18002acc9  test    r8d, r8d
0x18002accc  jz      short loc_18002ACF6
0x18002acce  mov     r9d, [rsp+88h+arg_8]
0x18002acd6  cmp     dword ptr [rcx+4], 8
0x18002acda  jz      short loc_18002ACEB
0x18002acdc  cmp     [rcx+0Ch], r9d
0x18002ace0  jnz     short loc_18002ACEB
0x18002ace2  cmp     dword ptr [rcx+10h], 0FFh
0x18002ace9  jz      short loc_18002ACF9
0x18002aceb  inc     eax
0x18002aced  add     rcx, 18h
0x18002acf1  cmp     eax, r8d
0x18002acf4  jb      short loc_18002ACD6
0x18002acf6  mov     rcx, r12
0x18002acf9  test    rbx, rbx
0x18002acfc  jnz     loc_18002ADF7
0x18002ad02  mov     rax, [rsp+88h+arg_20]
0x18002ad0a  test    rax, rax
0x18002ad0d  jz      short loc_18002AD15
0x18002ad0f  mov     dword ptr [rax], 5
0x18002ad15  mov     rsi, [rsp+88h+arg_28]
0x18002ad1d  lea     r14, off_180061C90; "DisplayName"
0x18002ad24  mov     ebp, [rsp+88h+arg_30]
0x18002ad2b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002ad2f  mov     r13d, r12d
0x18002ad32  mov     r15d, 6
0x18002ad38  test    rcx, rcx
0x18002ad3b  jnz     short loc_18002AD86
0x18002ad3d  cmp     [r14+8], r12d
0x18002ad41  jnz     short loc_18002AD7A
0x18002ad43  mov     rdx, [r14]; Src
0x18002ad46  mov     r12, rdi
0x18002ad49  inc     r12
0x18002ad4c  cmp     byte ptr [rdx+r12], 0
0x18002ad51  jnz     short loc_18002AD49
0x18002ad53  inc     r12d
0x18002ad56  test    rsi, rsi
0x18002ad59  jz      short loc_18002AD71
0x18002ad5b  cmp     ebp, r12d
0x18002ad5e  jl      short loc_18002AD71
0x18002ad60  mov     r8d, r12d; Size
0x18002ad63  mov     rcx, rsi; void *
0x18002ad66  mov     ebx, r12d
0x18002ad69  call    memcpy_0
0x18002ad6e  add     rsi, rbx
0x18002ad71  sub     ebp, r12d
0x18002ad74  add     r13d, r12d
0x18002ad77  xor     r12d, r12d
0x18002ad7a  add     r14, 10h
0x18002ad7e  add     r15d, 0FFFFFFFFh
0x18002ad82  jnz     short loc_18002AD3D
0x18002ad84  jmp     short loc_18002ADC4
0x18002ad86  mov     rdx, [r14]; Src
0x18002ad89  mov     r12, rdi
0x18002ad8c  inc     r12
0x18002ad8f  cmp     byte ptr [rdx+r12], 0
0x18002ad94  jnz     short loc_18002AD8C
0x18002ad96  inc     r12d
0x18002ad99  test    rsi, rsi
0x18002ad9c  jz      short loc_18002ADB4
0x18002ad9e  cmp     ebp, r12d
0x18002ada1  jl      short loc_18002ADB4
0x18002ada3  mov     r8d, r12d; Size
0x18002ada6  mov     rcx, rsi; void *
0x18002ada9  mov     ebx, r12d
0x18002adac  call    memcpy_0
0x18002adb1  add     rsi, rbx
0x18002adb4  sub     ebp, r12d
0x18002adb7  add     r13d, r12d
0x18002adba  add     r14, 10h
0x18002adbe  add     r15d, 0FFFFFFFFh
0x18002adc2  jnz     short loc_18002AD86
0x18002adc4  mov     rcx, [rsp+88h+arg_38]
0x18002adcc  test    rcx, rcx
0x18002adcf  jz      short loc_18002ADD7
0x18002add1  lea     eax, [r13+1]
0x18002add5  mov     [rcx], eax
0x18002add7  test    rsi, rsi
0x18002adda  jz      short loc_18002ADED
0x18002addc  lea     eax, [rbp-1]
0x18002addf  test    eax, eax
0x18002ade1  js      short loc_18002ADED
0x18002ade3  mov     byte ptr [rsi], 0
0x18002ade6  xor     eax, eax
0x18002ade8  jmp     loc_18002B068
0x18002aded  mov     eax, 8007000Eh
0x18002adf2  jmp     loc_18002B068
0x18002adf7  cmp     byte ptr [rbx], 44h ; 'D'
0x18002adfa  jnz     loc_18002AF16
0x18002ae00  lea     rcx, kstrDisplayName; "DisplayName"
0x18002ae07  mov     rax, rbx
0x18002ae0a  sub     rcx, rbx
0x18002ae0d  movzx   r8d, byte ptr [rax]
0x18002ae11  movzx   r9d, byte ptr [rax+rcx]
0x18002ae16  sub     r8d, r9d
0x18002ae19  jnz     short loc_18002AE23
0x18002ae1b  inc     rax
0x18002ae1e  test    r9d, r9d
0x18002ae21  jnz     short loc_18002AE0D
0x18002ae23  test    r8d, r8d
0x18002ae26  jnz     short loc_18002AE90
0x18002ae28  cmp     [rdx+0Ch], r12d
0x18002ae2c  jz      loc_18002B063
0x18002ae32  mov     ecx, [rdx+0Ch]
0x18002ae35  add     rcx, rsi; Src
0x18002ae38  jz      loc_18002B063
0x18002ae3e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002ae42  inc     rdi
0x18002ae45  cmp     [rcx+rdi*2], r12w
0x18002ae4a  jnz     short loc_18002AE42
0x18002ae4c  lea     r8d, ds:2[rdi*2]
0x18002ae54  mov     edx, 6
0x18002ae59  mov     rax, [rsp+88h+arg_38]
0x18002ae61  mov     r9, [rsp+88h+arg_20]
0x18002ae69  mov     [rsp+88h+var_58], rax; __int64
0x18002ae6e  mov     eax, [rsp+88h+arg_30]
0x18002ae75  mov     [rsp+88h+var_60], eax; int
0x18002ae79  mov     rax, [rsp+88h+arg_28]
0x18002ae81  mov     [rsp+88h+var_68], rax; void *
0x18002ae86  call    HGetSingleData
0x18002ae8b  jmp     loc_18002B068
0x18002ae90  lea     r8, kstrDefOption; "DefaultOption"
0x18002ae97  sub     r8, rbx
0x18002ae9a  movzx   eax, byte ptr [rbx]
0x18002ae9d  movzx   ecx, byte ptr [rbx+r8]
0x18002aea2  sub     eax, ecx
0x18002aea4  jnz     short loc_18002AEAD
0x18002aea6  inc     rbx
0x18002aea9  test    ecx, ecx
0x18002aeab  jnz     short loc_18002AE9A
0x18002aead  test    eax, eax
0x18002aeaf  jnz     loc_18002B05C
0x18002aeb5  mov     eax, [rdx+14h]
0x18002aeb8  cmp     eax, [rdx+34h]
0x18002aebb  jnb     short loc_18002AED0
0x18002aebd  imul    eax, [rdx+30h]
0x18002aec1  add     eax, [rdx+38h]
0x18002aec4  mov     r8d, eax
0x18002aec7  add     r8, [rbp+148h]
0x18002aece  jnz     short loc_18002AEEB
0x18002aed0  cmp     [rdx+34h], r12d
0x18002aed4  jbe     loc_18002B063
0x18002aeda  mov     r8d, [rdx+38h]
0x18002aede  add     r8, [rbp+148h]
0x18002aee5  jz      loc_18002B063
0x18002aeeb  cmp     [r8], r12d
0x18002aeee  jz      short loc_18002AEF8
0x18002aef0  mov     ecx, [r8]
0x18002aef3  add     rcx, rsi
0x18002aef6  jmp     short loc_18002AEFB
0x18002aef8  mov     rcx, r12
0x18002aefb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002aeff  inc     rdi
0x18002af02  cmp     [rcx+rdi], r12b
0x18002af06  jnz     short loc_18002AEFF
0x18002af08  lea     r8d, [rdi+1]
0x18002af0c  mov     edx, 5
0x18002af11  jmp     loc_18002AE59
0x18002af16  cmp     byte ptr [rbx], 4Fh ; 'O'
0x18002af19  jnz     loc_18002B05C
0x18002af1f  lea     r8, kstrOpenUIType; "OpenUIType"
0x18002af26  mov     rax, rbx
0x18002af29  sub     r8, rbx
0x18002af2c  movzx   r9d, byte ptr [rax]
0x18002af30  movzx   r10d, byte ptr [rax+r8]
0x18002af35  sub     r9d, r10d
0x18002af38  jnz     short loc_18002AF42
0x18002af3a  inc     rax
0x18002af3d  test    r10d, r10d
0x18002af40  jnz     short loc_18002AF2C
0x18002af42  test    r9d, r9d
0x18002af45  jnz     short loc_18002AF77
0x18002af47  cmp     dword ptr [rdx+20h], 2
0x18002af4b  mov     eax, r12d
0x18002af4e  cmovbe  eax, [rdx+20h]
0x18002af52  lea     rcx, [rax+rax*4]
0x18002af56  lea     rcx, ds:67478h[rcx*2]
0x18002af5e  lea     rax, cs:180000000h
0x18002af65  add     rcx, rax
0x18002af68  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002af6c  inc     rdi
0x18002af6f  cmp     [rcx+rdi], r12b
0x18002af73  jnz     short loc_18002AF6C
0x18002af75  jmp     short loc_18002AF08
0x18002af77  lea     r8, kstrOpenGroupType; "OpenGroupType"
0x18002af7e  mov     rax, rbx
0x18002af81  sub     r8, rbx
0x18002af84  movzx   r9d, byte ptr [rax]
0x18002af88  movzx   r10d, byte ptr [rax+r8]
0x18002af8d  sub     r9d, r10d
0x18002af90  jnz     short loc_18002AF9A
0x18002af92  inc     rax
0x18002af95  test    r10d, r10d
0x18002af98  jnz     short loc_18002AF84
0x18002af9a  test    r9d, r9d
0x18002af9d  jnz     short loc_18002AFD0
0x18002af9f  mov     eax, [rdx+2Ch]
0x18002afa2  sub     eax, 2
0x18002afa5  neg     eax
0x18002afa7  lea     rax, cs:180000000h
0x18002afae  sbb     rcx, rcx
0x18002afb1  and     ecx, 1Eh
0x18002afb4  lea     rcx, [rcx+67438h]
0x18002afbb  add     rcx, rax
0x18002afbe  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002afc2  inc     rdi
0x18002afc5  cmp     [rcx+rdi], r12b
0x18002afc9  jnz     short loc_18002AFC2
0x18002afcb  jmp     loc_18002AF08
0x18002afd0  lea     rdx, kstrOrderDepValue; "OrderDependencyValue"
0x18002afd7  mov     rax, rbx
0x18002afda  sub     rdx, rbx
0x18002afdd  movzx   r8d, byte ptr [rax]
0x18002afe1  movzx   r9d, byte ptr [rax+rdx]
0x18002afe6  sub     r8d, r9d
0x18002afe9  jnz     short loc_18002AFF3
0x18002afeb  inc     rax
0x18002afee  test    r9d, r9d
0x18002aff1  jnz     short loc_18002AFDD
0x18002aff3  test    r8d, r8d
0x18002aff6  jnz     short loc_18002B00A
0x18002aff8  test    rcx, rcx
0x18002affb  jz      short loc_18002B05C
0x18002affd  lea     edx, [r8+3]
0x18002b001  lea     r8d, [rdx+1]
0x18002b005  jmp     loc_18002AE59
0x18002b00a  lea     r8, kstrOrderDepSect; "OrderDependencySection"
0x18002b011  sub     r8, rbx
0x18002b014  movzx   eax, byte ptr [rbx]
0x18002b017  movzx   edx, byte ptr [rbx+r8]
0x18002b01c  sub     eax, edx
0x18002b01e  jnz     short loc_18002B027
0x18002b020  inc     rbx
0x18002b023  test    edx, edx
0x18002b025  jnz     short loc_18002B014
0x18002b027  test    eax, eax
0x18002b029  jnz     short loc_18002B05C
0x18002b02b  test    rcx, rcx
0x18002b02e  jz      short loc_18002B05C
0x18002b030  mov     rax, [rsp+88h+arg_38]
0x18002b038  mov     r9d, [rsp+88h+arg_30]
0x18002b040  mov     r8, [rsp+88h+arg_28]
0x18002b048  mov     rdx, [rsp+88h+arg_20]
0x18002b050  mov     [rsp+88h+var_68], rax
0x18002b055  call    HGetOrderDepSection
0x18002b05a  jmp     short loc_18002B068
0x18002b05c  mov     eax, 80070057h
0x18002b061  jmp     short loc_18002B068
0x18002b063  mov     eax, 80004005h
0x18002b068  add     rsp, 48h
  ... truncated ...
```
