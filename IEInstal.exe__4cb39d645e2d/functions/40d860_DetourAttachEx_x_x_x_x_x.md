# DetourAttachEx(x,x,x,x,x)

- ea: `0x40d860`
- end: `0x40db9a`
- name: `_DetourAttachEx@20`
- size: `826`
- prototype: `DWORD __stdcall(LPCVOID *, LPCVOID lpAddress, unsigned int *, unsigned __int8 **, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x40d840`

## callees

- `0x4026e7`
- `0x40d1e0`
- `0x40d480`
- `0x40d4b0`
- `0x40d4f0`
- `0x40d860`
- `0x40dba0`
- `0x40ea20`
- `0x40eb05`
- `0x40eb1b`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x40d89b`
- `KERNEL32!GetCurrentThreadId` at `0x40d89b`
- `KERNEL32!VirtualProtect` at `0x40daf3`
- `KERNEL32!VirtualProtect` at `0x40daf3`
- `KERNEL32!GetLastError` at `0x40dafd`
- `KERNEL32!GetLastError` at `0x40dafd`

## pseudocode

```c
DWORD __stdcall DetourAttachEx(LPCVOID *a1, LPCVOID lpAddress, unsigned int *a3, unsigned __int8 **a4, int *a5)
{
  DWORD LastError; // esi
  DWORD result; // eax
  unsigned int v7; // ebx
  int v8; // eax
  _DWORD *v9; // ebp
  unsigned int v10; // ecx
  unsigned __int8 *v11; // edi
  unsigned __int8 *v12; // esi
  size_t v13; // ebx
  unsigned __int8 v14; // al
  _BYTE *v15; // ecx
  unsigned int is_code_filler; // eax
  unsigned int v17; // ecx
  unsigned int v18; // [esp+Ch] [ebp-20h]
  unsigned __int8 *Src; // [esp+10h] [ebp-1Ch]
  unsigned int v20; // [esp+14h] [ebp-18h]
  unsigned int v21; // [esp+18h] [ebp-14h]
  unsigned __int8 *v22; // [esp+1Ch] [ebp-10h] BYREF
  int v23; // [esp+20h] [ebp-Ch] BYREF
  DWORD flOldProtect; // [esp+24h] [ebp-8h] BYREF
  int v25; // [esp+28h] [ebp-4h]

  LastError = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !lpAddress )
    return 87;
  if ( dword_40F47C != GetCurrentThreadId() )
    return 4317;
  result = dword_40F480;
  if ( !dword_40F480 )
  {
    if ( !a1 )
      return 6;
    if ( !*a1 )
    {
      dword_40F480 = 6;
      dword_40F484 = (int)a1;
      return 6;
    }
    v7 = 0;
    Src = (unsigned __int8 *)DetourCodeFromPointer(*a1, 0);
    v8 = DetourCodeFromPointer(lpAddress, 0);
    v25 = v8;
    if ( (unsigned __int8 *)v8 == Src )
    {
      if ( dword_40F474 )
      {
LABEL_71:
        dword_40F484 = (int)a1;
        return LastError;
      }
      v9 = 0;
LABEL_64:
      dword_40F480 = LastError;
      if ( !v7 )
      {
LABEL_69:
        if ( v9 )
          operator delete(v9);
        goto LABEL_71;
      }
LABEL_67:
      detour_free_trampoline((void *)v7);
      if ( a3 )
        *a3 = 0;
      goto LABEL_69;
    }
    if ( a4 )
      *a4 = Src;
    if ( a5 )
      *a5 = v8;
    v9 = operator new(0x18u);
    if ( !v9 )
    {
      LastError = 8;
      goto LABEL_64;
    }
    v7 = detour_alloc_trampoline(Src);
    v18 = v7;
    if ( !v7 )
    {
      LastError = 8;
      goto LABEL_64;
    }
    if ( a3 )
      *a3 = v7;
    *(_QWORD *)(v7 + 56) = 0;
    v10 = v7;
    v22 = (unsigned __int8 *)(v7 + 30);
    v11 = Src;
    v20 = v7;
    v21 = 0;
    while ( 1 )
    {
      v23 = 0;
      v12 = v11;
      v11 = (unsigned __int8 *)DetourCopyInstruction(v10, &v22, v11, 0, &v23);
      v13 = v11 - Src;
      v20 += (unsigned int)&v11[v23 - (_DWORD)v12];
      *(_BYTE *)(v18 + v21 + 56) = ((_BYTE)v11 - (_BYTE)Src) & 7 ^ (8 * (v20 - v18));
      if ( ++v21 >= 8 )
        break;
      v14 = *v12;
      if ( *v12 == 0xEB
        || v14 == 0xE9
        || v14 == 0xE0
        || v14 == 0xC2
        || v14 == 0xC3
        || v14 == 0xCC
        || v14 == 0xF3 && v12[1] == 0xC3 )
      {
        break;
      }
      v15 = v12 + 1;
      if ( v14 == 0xFF )
      {
        v15 = v12 + 1;
        if ( v12[1] == 37 )
          break;
      }
      if ( v14 == 38 || (v15 = v12 + 1, v14 == 46) || v14 == 54 || v14 == 62 || v14 == 100 || v14 == 101 )
      {
        if ( *v15 == 0xFF && v12[2] == 37 )
          break;
      }
      if ( v13 >= 5 )
        goto LABEL_55;
      v10 = v20;
    }
    if ( v13 >= 5 )
    {
LABEL_54:
      if ( v21 <= 8 )
      {
LABEL_55:
        if ( v20 > (unsigned int)v22 )
          __debugbreak();
        *(_BYTE *)(v18 + 30) = v20 - v18;
        *(_BYTE *)(v18 + 54) = v13;
        memcpy((void *)(v18 + 32), Src, v13);
        if ( v13 <= 0x19 )
        {
          *(_DWORD *)(v18 + 68) = v25;
          v17 = v18 + *(unsigned __int8 *)(v18 + 30);
          *(_DWORD *)(v18 + 64) = &Src[v13];
          *(_BYTE *)v17 = -23;
          *(_DWORD *)(v17 + 1) = &Src[v13 - 5 - v17];
          detour_gen_brk((unsigned __int8 *)(v17 + 5), v22);
          flOldProtect = 0;
          if ( VirtualProtect(Src, v13, 0x40u, &flOldProtect) )
          {
            v9[2] = a1;
            v9[4] = v18;
            v9[3] = Src;
            v9[1] = 0;
            v9[5] = flOldProtect;
            *v9 = lpMem;
            result = 0;
            lpMem = v9;
            return result;
          }
          LastError = GetLastError();
        }
        else
        {
          LastError = 6;
        }
        goto LABEL_63;
      }
    }
    else
    {
      while ( 1 )
      {
        is_code_filler = detour_is_code_filler(v11);
        if ( !is_code_filler )
          break;
        v11 += is_code_filler;
        v13 = v11 - Src;
        if ( (unsigned int)(v11 - Src) >= 5 )
          goto LABEL_54;
      }
    }
    LastError = 9;
    if ( dword_40F474 )
    {
      v7 = v18;
      goto LABEL_67;
    }
LABEL_63:
    v7 = v18;
    goto LABEL_64;
  }
  return result;
}

```

## disassembly

```asm
0x40d860  mov     eax, [esp+arg_8]
0x40d864  sub     esp, 20h
0x40d867  push    ebp
0x40d868  push    esi
0x40d869  xor     esi, esi
0x40d86b  push    edi
0x40d86c  test    eax, eax
0x40d86e  jz      short loc_40D872
0x40d870  mov     [eax], esi
0x40d872  mov     edi, [esp+2Ch+arg_C]
0x40d876  test    edi, edi
0x40d878  jz      short loc_40D87C
0x40d87a  mov     [edi], esi
0x40d87c  mov     ebp, [esp+2Ch+arg_10]
0x40d880  test    ebp, ebp
0x40d882  jz      short loc_40D887
0x40d884  mov     [ebp+0], esi
0x40d887  cmp     [esp+2Ch+lpAddress], esi
0x40d88b  jnz     short loc_40D89B
0x40d88d  pop     edi
0x40d88e  pop     esi
0x40d88f  mov     eax, 57h ; 'W'
0x40d894  pop     ebp
0x40d895  add     esp, 20h
0x40d898  retn    14h
0x40d89b  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x40d8a1  cmp     dword_40F47C, eax
0x40d8a7  jz      short loc_40D8B7
0x40d8a9  pop     edi
0x40d8aa  pop     esi
0x40d8ab  mov     eax, 10DDh
0x40d8b0  pop     ebp
0x40d8b1  add     esp, 20h
0x40d8b4  retn    14h
0x40d8b7  mov     eax, dword_40F480
0x40d8bc  test    eax, eax
0x40d8be  jnz     loc_40DB91
0x40d8c4  mov     ecx, [esp+2Ch+arg_0]
0x40d8c8  test    ecx, ecx
0x40d8ca  jz      short loc_40D8E2
0x40d8cc  mov     eax, [ecx]
0x40d8ce  test    eax, eax
0x40d8d0  jnz     short loc_40D8F0
0x40d8d2  mov     dword_40F480, 6
0x40d8dc  mov     dword_40F484, ecx
0x40d8e2  pop     edi
0x40d8e3  pop     esi
0x40d8e4  mov     eax, 6
0x40d8e9  pop     ebp
0x40d8ea  add     esp, 20h
0x40d8ed  retn    14h
0x40d8f0  push    ebx
0x40d8f1  xor     ebx, ebx
0x40d8f3  push    ebx; int
0x40d8f4  push    eax; lpAddress
0x40d8f5  call    _DetourCodeFromPointer@8; DetourCodeFromPointer(x,x)
0x40d8fa  push    ebx; int
0x40d8fb  push    [esp+34h+lpAddress]; lpAddress
0x40d8ff  mov     [esp+38h+Src], eax
0x40d903  call    _DetourCodeFromPointer@8; DetourCodeFromPointer(x,x)
0x40d908  mov     [esp+30h+var_4], eax
0x40d90c  cmp     eax, [esp+30h+Src]
0x40d910  jnz     short loc_40D925
0x40d912  cmp     dword_40F474, ebx
0x40d918  jnz     loc_40DB85
0x40d91e  xor     ebp, ebp
0x40d920  jmp     loc_40DB52
0x40d925  mov     esi, [esp+30h+Src]
0x40d929  test    edi, edi
0x40d92b  jz      short loc_40D92F
0x40d92d  mov     [edi], esi
0x40d92f  test    ebp, ebp
0x40d931  jz      short loc_40D936
0x40d933  mov     [ebp+0], eax
0x40d936  push    18h; dwBytes
0x40d938  call    ??2@YAPAXI@Z; operator new(uint)
0x40d93d  mov     ebp, eax
0x40d93f  add     esp, 4
0x40d942  test    ebp, ebp
0x40d944  jnz     short loc_40D94E
0x40d946  lea     esi, [eax+8]
0x40d949  jmp     loc_40DB52
0x40d94e  push    esi
0x40d94f  call    detour_alloc_trampoline
0x40d954  mov     ebx, eax
0x40d956  mov     [esp+30h+var_20], ebx
0x40d95a  test    ebx, ebx
0x40d95c  jnz     short loc_40D966
0x40d95e  lea     esi, [eax+8]
0x40d961  jmp     loc_40DB52
0x40d966  mov     eax, [esp+30h+arg_8]
0x40d96a  test    eax, eax
0x40d96c  jz      short loc_40D970
0x40d96e  mov     [eax], ebx
0x40d970  xorps   xmm0, xmm0
0x40d973  lea     eax, [ebx+1Eh]
0x40d976  movq    qword ptr [ebx+38h], xmm0
0x40d97b  mov     ecx, ebx
0x40d97d  mov     [esp+30h+var_10], eax
0x40d981  mov     edi, esi
0x40d983  xor     eax, eax
0x40d985  mov     [esp+30h+var_18], ecx
0x40d989  mov     [esp+30h+var_14], eax
0x40d98d  nop     dword ptr [eax]
0x40d990  lea     eax, [esp+30h+var_C]
0x40d994  mov     [esp+30h+var_C], 0
0x40d99c  push    eax
0x40d99d  push    0
0x40d99f  push    edi
0x40d9a0  lea     eax, [esp+3Ch+var_10]
0x40d9a4  mov     esi, edi
0x40d9a6  push    eax
0x40d9a7  push    ecx
0x40d9a8  call    _DetourCopyInstruction@20; DetourCopyInstruction(x,x,x,x,x)
0x40d9ad  mov     ecx, [esp+30h+var_18]
0x40d9b1  mov     edi, eax
0x40d9b3  mov     eax, [esp+30h+var_C]
0x40d9b7  mov     ebx, edi
0x40d9b9  sub     ebx, [esp+30h+Src]
0x40d9bd  sub     eax, esi
0x40d9bf  mov     edx, [esp+30h+var_20]
0x40d9c3  add     eax, edi
0x40d9c5  add     ecx, eax
0x40d9c7  mov     al, bl
0x40d9c9  mov     [esp+30h+var_18], ecx
0x40d9cd  and     al, 7
0x40d9cf  sub     cl, dl
0x40d9d1  shl     cl, 3
0x40d9d4  xor     cl, al
0x40d9d6  mov     eax, [esp+30h+var_14]
0x40d9da  mov     [edx+eax+38h], cl
0x40d9de  inc     eax
0x40d9df  mov     [esp+30h+var_14], eax
0x40d9e3  cmp     eax, 8
0x40d9e6  jnb     short loc_40DA50
0x40d9e8  mov     al, [esi]
0x40d9ea  cmp     al, 0EBh
0x40d9ec  jz      short loc_40DA50
0x40d9ee  cmp     al, 0E9h
0x40d9f0  jz      short loc_40DA50
0x40d9f2  cmp     al, 0E0h
0x40d9f4  jz      short loc_40DA50
0x40d9f6  cmp     al, 0C2h
0x40d9f8  jz      short loc_40DA50
0x40d9fa  cmp     al, 0C3h
0x40d9fc  jz      short loc_40DA50
0x40d9fe  cmp     al, 0CCh
0x40da00  jz      short loc_40DA50
0x40da02  lea     edx, [esi+1]
0x40da05  cmp     al, 0F3h
0x40da07  jnz     short loc_40DA0E
0x40da09  cmp     byte ptr [edx], 0C3h
0x40da0c  jz      short loc_40DA50
0x40da0e  mov     ecx, edx
0x40da10  cmp     al, 0FFh
0x40da12  jnz     short loc_40DA1D
0x40da14  cmp     byte ptr [esi+1], 25h ; '%'
0x40da18  lea     ecx, [esi+1]
0x40da1b  jz      short loc_40DA50
0x40da1d  cmp     al, 26h ; '&'
0x40da1f  jz      short loc_40DA37
0x40da21  mov     ecx, edx
0x40da23  cmp     al, 2Eh ; '.'
0x40da25  jz      short loc_40DA37
0x40da27  cmp     al, 36h ; '6'
0x40da29  jz      short loc_40DA37
0x40da2b  cmp     al, 3Eh ; '>'
0x40da2d  jz      short loc_40DA37
0x40da2f  cmp     al, 64h ; 'd'
0x40da31  jz      short loc_40DA37
0x40da33  cmp     al, 65h ; 'e'
0x40da35  jnz     short loc_40DA42
0x40da37  cmp     byte ptr [ecx], 0FFh
0x40da3a  jnz     short loc_40DA42
0x40da3c  cmp     byte ptr [esi+2], 25h ; '%'
0x40da40  jz      short loc_40DA50
0x40da42  cmp     ebx, 5
0x40da45  jnb     short loc_40DA7B
0x40da47  mov     ecx, [esp+30h+var_18]
0x40da4b  jmp     loc_40D990
0x40da50  cmp     ebx, 5
0x40da53  jnb     short loc_40DA70
0x40da55  push    edi; unsigned __int8 *
0x40da56  call    ?detour_is_code_filler@@YGKPAE@Z; detour_is_code_filler(uchar *)
0x40da5b  test    eax, eax
0x40da5d  jz      loc_40DB40
0x40da63  add     edi, eax
0x40da65  mov     ebx, edi
0x40da67  sub     ebx, [esp+30h+Src]
0x40da6b  cmp     ebx, 5
0x40da6e  jb      short loc_40DA55
0x40da70  cmp     [esp+30h+var_14], 8
0x40da75  ja      loc_40DB40
0x40da7b  mov     ecx, [esp+30h+var_18]
0x40da7f  cmp     ecx, [esp+30h+var_10]
0x40da83  jbe     short loc_40DA86
0x40da85  int     3; Trap to Debugger
0x40da86  mov     eax, [esp+30h+var_20]
0x40da8a  sub     cl, al
0x40da8c  mov     esi, [esp+30h+Src]
0x40da90  push    ebx; Size
0x40da91  push    esi; Src
0x40da92  mov     [eax+1Eh], cl
0x40da95  mov     [eax+36h], bl
0x40da98  add     eax, 20h ; ' '
0x40da9b  push    eax; void *
0x40da9c  call    _memcpy
0x40daa1  add     esp, 0Ch
0x40daa4  cmp     ebx, 19h
0x40daa7  jbe     short loc_40DAB3
0x40daa9  mov     esi, 6
0x40daae  jmp     loc_40DB4E
0x40dab3  mov     eax, [esp+30h+var_20]
0x40dab7  lea     edx, [ebx+esi]
0x40daba  mov     ecx, [esp+30h+var_4]
0x40dabe  mov     [eax+44h], ecx
0x40dac1  movzx   ecx, byte ptr [eax+1Eh]
0x40dac5  add     ecx, eax
0x40dac7  mov     [eax+40h], edx
0x40daca  lea     eax, [ecx+5]
0x40dacd  mov     byte ptr [ecx], 0E9h
0x40dad0  sub     edx, eax
0x40dad2  lea     eax, [ecx+5]
0x40dad5  mov     [ecx+1], edx
0x40dad8  push    [esp+30h+var_10]; unsigned __int8 *
0x40dadc  push    eax; unsigned __int8 *
0x40dadd  call    ?detour_gen_brk@@YGPAEPAE0@Z; detour_gen_brk(uchar *,uchar *)
0x40dae2  lea     eax, [esp+30h+flOldProtect]
0x40dae6  mov     [esp+30h+flOldProtect], 0
0x40daee  push    eax; lpflOldProtect
0x40daef  push    40h ; '@'; flNewProtect
0x40daf1  push    ebx; dwSize
0x40daf2  push    esi; lpAddress
0x40daf3  call    ds:__imp__VirtualProtect@16; VirtualProtect(x,x,x,x)
0x40daf9  test    eax, eax
0x40dafb  jnz     short loc_40DB07
0x40dafd  call    ds:__imp__GetLastError@0; GetLastError()
0x40db03  mov     esi, eax
0x40db05  jmp     short loc_40DB4E
0x40db07  mov     eax, [esp+30h+arg_0]
0x40db0b  mov     [ebp+8], eax
0x40db0e  mov     eax, [esp+30h+var_20]
0x40db12  mov     [ebp+10h], eax
0x40db15  pop     ebx
0x40db16  mov     [ebp+0Ch], esi
0x40db19  mov     dword ptr [ebp+4], 0
0x40db20  mov     eax, [esp+2Ch+flOldProtect]
0x40db24  mov     [ebp+14h], eax
0x40db27  mov     eax, lpMem
0x40db2c  pop     edi
0x40db2d  mov     [ebp+0], eax
0x40db30  xor     eax, eax
0x40db32  pop     esi
0x40db33  mov     lpMem, ebp
0x40db39  pop     ebp
0x40db3a  add     esp, 20h
0x40db3d  retn    14h
0x40db40  cmp     dword_40F474, 0
0x40db47  mov     esi, 9
0x40db4c  jnz     short loc_40DB5E
0x40db4e  mov     ebx, [esp+30h+var_20]
0x40db52  mov     dword_40F480, esi
0x40db58  test    ebx, ebx
0x40db5a  jz      short loc_40DB76
0x40db5c  jmp     short loc_40DB62
0x40db5e  mov     ebx, [esp+30h+var_20]
0x40db62  push    ebx; void *
0x40db63  call    detour_free_trampoline
0x40db68  mov     eax, [esp+30h+arg_8]
0x40db6c  test    eax, eax
0x40db6e  jz      short loc_40DB76
0x40db70  mov     dword ptr [eax], 0
0x40db76  test    ebp, ebp
0x40db78  jz      short loc_40DB85
0x40db7a  push    18h; unsigned int
0x40db7c  push    ebp; lpMem
0x40db7d  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x40db82  add     esp, 8
0x40db85  mov     eax, [esp+30h+arg_0]
0x40db89  mov     dword_40F484, eax
0x40db8e  mov     eax, esi
0x40db90  pop     ebx
0x40db91  pop     edi
0x40db92  pop     esi
0x40db93  pop     ebp
0x40db94  add     esp, 20h
0x40db97  retn    14h
```
