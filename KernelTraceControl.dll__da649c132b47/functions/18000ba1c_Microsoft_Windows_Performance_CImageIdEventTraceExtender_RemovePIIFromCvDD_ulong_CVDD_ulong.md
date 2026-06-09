# Microsoft::Windows::Performance::CImageIdEventTraceExtender::RemovePIIFromCvDD(ulong,_CVDD *,ulong *)

- ea: `0x18000ba1c`
- end: `0x18000bbb2`
- name: `?RemovePIIFromCvDD@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJKPEAT_CVDD@@PEAK@Z`
- size: `406`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this, unsigned int, union _CVDD *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a30c`

## callees

- `0x18000ba1c`

## import_xrefs

- `msvcrt!memmove` at `0x18000bb7a`
- `msvcrt!memmove` at `0x18000bb7a`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::RemovePIIFromCvDD(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this,
        unsigned int a2,
        union _CVDD *a3,
        unsigned int *a4)
{
  unsigned int v7; // esi
  char *v8; // rcx
  void *v9; // r9
  char *v10; // rdx
  char *v11; // rax
  int v12; // r8d
  int v13; // ebx
  char *v14; // rax
  size_t v15; // r8
  const void *v16; // rdx
  char *v17; // rdx
  char *v18; // rax

  v7 = 0;
  if ( !a2 )
    return 0;
  while ( 1 )
  {
    v8 = (char *)a3 + 1576 * v7;
    if ( *a4 < 4 )
      goto LABEL_32;
    if ( *a4 > 0x628 )
      return 2147549183LL;
    if ( *(_DWORD *)v8 )
    {
      if ( *(_DWORD *)v8 <= 2u )
      {
        v9 = v8 + 16;
        v17 = 0;
        v18 = v8 + 16;
        if ( v8 + 16 >= v8 + 1576 )
          goto LABEL_32;
        do
        {
          if ( !*(_WORD *)v18 )
            break;
          if ( *(_WORD *)v18 == 92 )
            v17 = v18;
          v18 += 2;
        }
        while ( v18 < v8 + 1576 );
        if ( !v17 )
          goto LABEL_32;
        v13 = 2 * ((v17 - v8 - 16) >> 1) + 2;
        v15 = (unsigned int)(1560 - v13);
        v16 = v17 + 2;
        goto LABEL_31;
      }
      switch ( *(_DWORD *)v8 )
      {
        case 3:
          goto LABEL_9;
        case 0x3031424E:
          v9 = v8 + 16;
          v10 = 0;
          v14 = v8 + 16;
          if ( v8 + 16 >= v8 + 276 )
            break;
          do
          {
            if ( !*v14 )
              break;
            if ( *v14 == 92 )
              v10 = v14;
            ++v14;
          }
          while ( v14 < v8 + 276 );
          if ( !v10 )
            break;
          v12 = 260;
          v13 = (_DWORD)v10 - (_DWORD)v8 - 15;
          goto LABEL_23;
        case 0x53445352:
LABEL_9:
          v9 = v8 + 24;
          v10 = 0;
          v11 = v8 + 24;
          if ( v8 + 24 >= v8 + 804 )
            break;
          do
          {
            if ( !*v11 )
              break;
            if ( *v11 == 92 )
              v10 = v11;
            ++v11;
          }
          while ( v11 < v8 + 804 );
          if ( !v10 )
            break;
          v12 = 780;
          v13 = (_DWORD)v10 - (_DWORD)v8 - 23;
LABEL_23:
          v15 = (unsigned int)(v12 - v13);
          v16 = v10 + 1;
LABEL_31:
          memmove(v9, v16, v15);
          *a4 -= v13;
          break;
      }
    }
LABEL_32:
    ++v7;
    ++a4;
    if ( v7 >= a2 )
      return 0;
  }
}

```

## disassembly

```asm
0x18000ba1c  mov     [rsp+arg_0], rbx
0x18000ba21  mov     [rsp+arg_8], rbp
0x18000ba26  mov     [rsp+arg_10], rsi
0x18000ba2b  push    rdi
0x18000ba2c  push    r14
0x18000ba2e  push    r15
0x18000ba30  sub     rsp, 20h
0x18000ba34  xor     r15d, r15d
0x18000ba37  mov     rdi, r9
0x18000ba3a  mov     r14, r8
0x18000ba3d  mov     ebp, edx
0x18000ba3f  mov     esi, r15d
0x18000ba42  test    edx, edx
0x18000ba44  jz      loc_18000BB90
0x18000ba4a  mov     eax, esi
0x18000ba4c  imul    rcx, rax, 628h
0x18000ba53  add     rcx, r14
0x18000ba56  cmp     dword ptr [rdi], 4
0x18000ba59  jb      loc_18000BB82
0x18000ba5f  cmp     dword ptr [rdi], 628h
0x18000ba65  ja      loc_18000BBAB
0x18000ba6b  cmp     [rcx], r15d
0x18000ba6e  jbe     loc_18000BB82
0x18000ba74  cmp     dword ptr [rcx], 2
0x18000ba77  jbe     loc_18000BB24
0x18000ba7d  cmp     dword ptr [rcx], 3
0x18000ba80  jz      short loc_18000BA96
0x18000ba82  cmp     dword ptr [rcx], 3031424Eh
0x18000ba88  jz      short loc_18000BADC
0x18000ba8a  cmp     dword ptr [rcx], 53445352h
0x18000ba90  jnz     loc_18000BB82
0x18000ba96  lea     r9, [rcx+18h]
0x18000ba9a  mov     rdx, r15
0x18000ba9d  lea     r8, [r9+30Ch]
0x18000baa4  mov     rax, r9
0x18000baa7  cmp     r9, r8
0x18000baaa  jnb     loc_18000BB82
0x18000bab0  cmp     [rax], r15b
0x18000bab3  jz      short loc_18000BAC4
0x18000bab5  cmp     byte ptr [rax], 5Ch ; '\'
0x18000bab8  cmovz   rdx, rax
0x18000babc  inc     rax
0x18000babf  cmp     rax, r8
0x18000bac2  jb      short loc_18000BAB0
0x18000bac4  test    rdx, rdx
0x18000bac7  jz      loc_18000BB82
0x18000bacd  mov     ebx, edx
0x18000bacf  mov     r8d, 30Ch
0x18000bad5  sub     ebx, ecx
0x18000bad7  sub     ebx, 17h
0x18000bada  jmp     short loc_18000BB1C
0x18000badc  lea     r9, [rcx+10h]
0x18000bae0  mov     rdx, r15
0x18000bae3  lea     r8, [r9+104h]
0x18000baea  mov     rax, r9
0x18000baed  cmp     r9, r8
0x18000baf0  jnb     loc_18000BB82
0x18000baf6  cmp     [rax], r15b
0x18000baf9  jz      short loc_18000BB0A
0x18000bafb  cmp     byte ptr [rax], 5Ch ; '\'
0x18000bafe  cmovz   rdx, rax
0x18000bb02  inc     rax
0x18000bb05  cmp     rax, r8
0x18000bb08  jb      short loc_18000BAF6
0x18000bb0a  test    rdx, rdx
0x18000bb0d  jz      short loc_18000BB82
0x18000bb0f  mov     ebx, edx
0x18000bb11  mov     r8d, 104h
0x18000bb17  sub     ebx, ecx
0x18000bb19  sub     ebx, 0Fh
0x18000bb1c  sub     r8d, ebx
0x18000bb1f  inc     rdx
0x18000bb22  jmp     short loc_18000BB77
0x18000bb24  lea     r9, [rcx+10h]
0x18000bb28  mov     rdx, r15
0x18000bb2b  lea     r8, [r9+618h]
0x18000bb32  mov     rax, r9
0x18000bb35  cmp     r9, r8
0x18000bb38  jnb     short loc_18000BB82
0x18000bb3a  cmp     [rax], r15w
0x18000bb3e  jz      short loc_18000BB51
0x18000bb40  cmp     word ptr [rax], 5Ch ; '\'
0x18000bb44  cmovz   rdx, rax
0x18000bb48  add     rax, 2
0x18000bb4c  cmp     rax, r8
0x18000bb4f  jb      short loc_18000BB3A
0x18000bb51  test    rdx, rdx
0x18000bb54  jz      short loc_18000BB82
0x18000bb56  mov     rax, rdx
0x18000bb59  mov     r8d, 618h
0x18000bb5f  sub     rax, rcx
0x18000bb62  sub     rax, 10h
0x18000bb66  sar     rax, 1
0x18000bb69  lea     ebx, ds:2[rax*2]
0x18000bb70  sub     r8d, ebx; Size
0x18000bb73  add     rdx, 2; Src
0x18000bb77  mov     rcx, r9; void *
0x18000bb7a  call    cs:__imp_memmove
0x18000bb80  sub     [rdi], ebx
0x18000bb82  inc     esi
0x18000bb84  add     rdi, 4
0x18000bb88  cmp     esi, ebp
0x18000bb8a  jb      loc_18000BA4A
0x18000bb90  xor     eax, eax
0x18000bb92  mov     rbx, [rsp+38h+arg_0]
0x18000bb97  mov     rbp, [rsp+38h+arg_8]
0x18000bb9c  mov     rsi, [rsp+38h+arg_10]
0x18000bba1  add     rsp, 20h
0x18000bba5  pop     r15
0x18000bba7  pop     r14
0x18000bba9  pop     rdi
0x18000bbaa  retn
0x18000bbab  mov     eax, 8000FFFFh
0x18000bbb0  jmp     short loc_18000BB92
```
