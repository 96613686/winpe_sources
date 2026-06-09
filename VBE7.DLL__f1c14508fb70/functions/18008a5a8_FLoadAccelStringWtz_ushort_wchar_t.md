# FLoadAccelStringWtz(ushort,wchar_t *)

- ea: `0x18008a5a8`
- end: `0x18008a928`
- name: `?FLoadAccelStringWtz@@YAHGPEA_W@Z`
- size: `896`
- prototype: `__int64 __fastcall(unsigned __int16, wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18008522c`

## callees

- `0x18008a5a8`
- `0x18008a930`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!free` at `0x18008a8b7`
- `MSVCR100!free` at `0x18008a91d`
- `MSVCR100!free` at `0x18008a8b7`
- `MSVCR100!free` at `0x18008a91d`
- `MSVCR100!malloc` at `0x18008a64c`
- `MSVCR100!malloc` at `0x18008a64c`
- `KERNEL32!lstrcatA` at `0x18008a6de`
- `KERNEL32!lstrcatA` at `0x18008a6f2`
- `KERNEL32!lstrcatA` at `0x18008a724`
- `KERNEL32!lstrcatA` at `0x18008a738`
- `KERNEL32!lstrcatA` at `0x18008a76a`
- `KERNEL32!lstrcatA` at `0x18008a77e`
- `KERNEL32!lstrcatA` at `0x18008a8a9`
- `KERNEL32!lstrcatA` at `0x18008a6de`
- `KERNEL32!lstrcatA` at `0x18008a6f2`
- `KERNEL32!lstrcatA` at `0x18008a724`
- `KERNEL32!lstrcatA` at `0x18008a738`
- `KERNEL32!lstrcatA` at `0x18008a76a`
- `KERNEL32!lstrcatA` at `0x18008a77e`
- `KERNEL32!lstrcatA` at `0x18008a8a9`
- `USER32!LoadStringA` at `0x18008a6cc`
- `USER32!LoadStringA` at `0x18008a712`
- `USER32!LoadStringA` at `0x18008a758`
- `USER32!LoadStringA` at `0x18008a897`
- `USER32!LoadStringA` at `0x18008a6cc`
- `USER32!LoadStringA` at `0x18008a712`
- `USER32!LoadStringA` at `0x18008a758`
- `USER32!LoadStringA` at `0x18008a897`
- `USER32!wsprintfA` at `0x18008a6a3`
- `USER32!wsprintfA` at `0x18008a7b1`
- `USER32!wsprintfA` at `0x18008a6a3`
- `USER32!wsprintfA` at `0x18008a7b1`
- `USER32!CopyAcceleratorTableA` at `0x18008a63c`
- `USER32!CopyAcceleratorTableA` at `0x18008a663`
- `USER32!CopyAcceleratorTableA` at `0x18008a63c`
- `USER32!CopyAcceleratorTableA` at `0x18008a663`

## pseudocode

```c
__int64 __fastcall FLoadAccelStringWtz(__int16 a1, wchar_t *a2)
{
  unsigned int v3; // ebx
  int v5; // r12d
  HACCEL v6; // rdi
  __int64 v7; // r15
  struct tagACCEL *v8; // rax
  struct tagACCEL *v9; // rsi
  __int64 v10; // rdi
  WORD *p_cmd; // rcx
  WORD key; // ax
  UINT v13; // edx
  int v14; // edx
  CHAR Buffer[2048]; // [rsp+30h] [rbp-D0h] BYREF
  CHAR String1[2048]; // [rsp+830h] [rbp+730h] BYREF

  v3 = 0;
  if ( !(unsigned int)FLoadAcceleratorTables() )
    return 0;
  v5 = 0;
  while ( 1 )
  {
    if ( v5 )
    {
      if ( v5 == 1 )
      {
        v6 = Pbar_hAccel2;
      }
      else
      {
        if ( v5 != 2 )
          return 0;
        v6 = Pbar_hAccel3;
      }
    }
    else
    {
      v6 = Pbar_hAccel1;
    }
    if ( !v6 )
      goto LABEL_64;
    v7 = CopyAcceleratorTableA(v6, 0, 0);
    v8 = (struct tagACCEL *)malloc(6 * v7);
    v9 = v8;
    if ( !v8 )
      return 0;
    CopyAcceleratorTableA(v6, v8, v7);
    v10 = 0;
    if ( (int)v7 > 0 )
      break;
LABEL_63:
    free(v9);
    if ( v3 )
    {
      MsoSzToWtzAPI(String1, a2, 2048);
      return v3;
    }
LABEL_64:
    if ( ++v5 >= 3 )
      return v3;
  }
  p_cmd = &v9->cmd;
  while ( a1 != *p_cmd )
  {
    ++v10;
    v3 = 0;
    p_cmd += 3;
    if ( v10 >= v7 )
      goto LABEL_63;
  }
  wsprintfA(String1, (LPCSTR)&Class);
  if ( (v9[v10].fVirt & 8) != 0 )
  {
    LoadStringA(Rby_hIntlLib, 0x4DEEu, Buffer, 2048);
    lstrcatA(String1, Buffer);
    lstrcatA(String1, "+");
  }
  if ( (v9[v10].fVirt & 4) != 0 )
  {
    LoadStringA(Rby_hIntlLib, 0x4DF0u, Buffer, 2048);
    lstrcatA(String1, Buffer);
    lstrcatA(String1, "+");
  }
  if ( (v9[v10].fVirt & 0x10) != 0 )
  {
    LoadStringA(Rby_hIntlLib, 0x4DEFu, Buffer, 2048);
    lstrcatA(String1, Buffer);
    lstrcatA(String1, "+");
  }
  key = v9[v10].key;
  if ( key >= 0x41u && key <= 0x5Au || key >= 0x30u && key <= 0x39u )
  {
    wsprintfA(Buffer, "%c", key);
LABEL_62:
    lstrcatA(String1, Buffer);
    v3 = 1;
    goto LABEL_63;
  }
  if ( key >= 0x70u && key <= 0x7Fu )
  {
    v13 = key + 19851;
LABEL_61:
    LoadStringA(Rby_hIntlLib, v13, Buffer, 2048);
    goto LABEL_62;
  }
  if ( key <= 0x24u )
  {
    switch ( key )
    {
      case 0x24u:
        v14 = 960;
        break;
      case 3u:
        v14 = 953;
        break;
      case 8u:
        v14 = 954;
        break;
      case 9u:
        v14 = 955;
        break;
      case 0x13u:
        v14 = 956;
        break;
      case 0x20u:
        v14 = 957;
        break;
      case 0x21u:
        v14 = 958;
        break;
      case 0x22u:
        v14 = 959;
        break;
      default:
        goto LABEL_68;
    }
    goto LABEL_60;
  }
  switch ( key )
  {
    case '%':
      v14 = 979;
      goto LABEL_60;
    case '&':
      v14 = 981;
      goto LABEL_60;
    case '\'':
      v14 = 980;
      goto LABEL_60;
    case '(':
      v14 = 982;
      goto LABEL_60;
    case '-':
      v14 = 961;
      goto LABEL_60;
    case '.':
      v14 = 962;
LABEL_60:
      v13 = v14 + 19000;
      goto LABEL_61;
  }
LABEL_68:
  free(v9);
  return 0;
}

```

## disassembly

```asm
0x18008a5a8  mov     rax, rsp
0x18008a5ab  mov     [rax+8], rbx
0x18008a5af  mov     [rax+18h], rsi
0x18008a5b3  mov     [rax+20h], rdi
0x18008a5b7  push    rbp
0x18008a5b8  push    r12
0x18008a5ba  push    r13
0x18008a5bc  push    r14
0x18008a5be  push    r15
0x18008a5c0  lea     rbp, [rax-0F68h]
0x18008a5c7  mov     eax, 1040h
0x18008a5cc  call    _alloca_probe
0x18008a5d1  sub     rsp, rax
0x18008a5d4  mov     rax, cs:__security_cookie
0x18008a5db  xor     rax, rsp
0x18008a5de  mov     [rbp+0F60h+var_30], rax
0x18008a5e5  mov     r13, rdx
0x18008a5e8  mov     [rsp+1060h+var_1040], cx
0x18008a5ed  xor     ebx, ebx
0x18008a5ef  call    ?FLoadAcceleratorTables@@YAHXZ; FLoadAcceleratorTables(void)
0x18008a5f4  test    eax, eax
0x18008a5f6  jnz     short loc_18008A5FF
0x18008a5f8  xor     eax, eax
0x18008a5fa  jmp     loc_18008A8EA
0x18008a5ff  xor     r12d, r12d
0x18008a602  mov     ecx, r12d
0x18008a605  test    r12d, r12d
0x18008a608  jz      short loc_18008A624
0x18008a60a  dec     ecx
0x18008a60c  jz      short loc_18008A61B
0x18008a60e  dec     ecx
0x18008a610  jnz     short loc_18008A5F8
0x18008a612  mov     rdi, cs:?Pbar_hAccel3@@3PEAUHACCEL__@@EA; HACCEL__ * Pbar_hAccel3
0x18008a619  jmp     short loc_18008A62B
0x18008a61b  mov     rdi, cs:?Pbar_hAccel2@@3PEAUHACCEL__@@EA; HACCEL__ * Pbar_hAccel2
0x18008a622  jmp     short loc_18008A62B
0x18008a624  mov     rdi, cs:?Pbar_hAccel1@@3PEAUHACCEL__@@EA; HACCEL__ * Pbar_hAccel1
0x18008a62b  test    rdi, rdi
0x18008a62e  jz      loc_18008A8C1
0x18008a634  xor     r8d, r8d; cAccelEntries
0x18008a637  xor     edx, edx; lpAccelDst
0x18008a639  mov     rcx, rdi; hAccelSrc
0x18008a63c  call    cs:__imp_CopyAcceleratorTableA
0x18008a642  movsxd  r15, eax
0x18008a645  lea     rcx, [r15+r15*2]
0x18008a649  add     rcx, rcx; Size
0x18008a64c  call    cs:__imp_malloc
0x18008a652  mov     rsi, rax
0x18008a655  test    rax, rax
0x18008a658  jz      short loc_18008A5F8
0x18008a65a  mov     r8d, r15d; cAccelEntries
0x18008a65d  mov     rdx, rax; lpAccelDst
0x18008a660  mov     rcx, rdi; hAccelSrc
0x18008a663  call    cs:__imp_CopyAcceleratorTableA
0x18008a669  xor     edi, edi
0x18008a66b  test    r15d, r15d
0x18008a66e  jle     loc_18008A8B4
0x18008a674  movzx   eax, [rsp+1060h+var_1040]
0x18008a679  lea     rcx, [rsi+4]
0x18008a67d  cmp     ax, [rcx]
0x18008a680  jz      short loc_18008A695
0x18008a682  inc     rdi
0x18008a685  xor     ebx, ebx
0x18008a687  add     rcx, 6
0x18008a68b  cmp     rdi, r15
0x18008a68e  jl      short loc_18008A67D
0x18008a690  jmp     loc_18008A8B4
0x18008a695  lea     rdx, Class; LPCSTR
0x18008a69c  lea     rcx, [rbp+0F60h+String1]; LPSTR
0x18008a6a3  call    cs:__imp_wsprintfA
0x18008a6a9  lea     rbx, [rdi+rdi*2]
0x18008a6ad  mov     edi, 800h
0x18008a6b2  test    byte ptr [rsi+rbx*2], 8
0x18008a6b6  jz      short loc_18008A6F8
0x18008a6b8  mov     rcx, cs:?Rby_hIntlLib@@3PEAUHINSTANCE__@@EA; hInstance
0x18008a6bf  lea     r8, [rsp+1060h+Buffer]; lpBuffer
0x18008a6c4  mov     r9d, edi; cchBufferMax
0x18008a6c7  mov     edx, 4DEEh; uID
0x18008a6cc  call    cs:__imp_LoadStringA
0x18008a6d2  lea     rdx, [rsp+1060h+Buffer]; lpString2
0x18008a6d7  lea     rcx, [rbp+0F60h+String1]; lpString1
0x18008a6de  call    cs:__imp_lstrcatA
0x18008a6e4  lea     rdx, asc_1803ADF58; "+"
0x18008a6eb  lea     rcx, [rbp+0F60h+String1]; lpString1
0x18008a6f2  call    cs:__imp_lstrcatA
0x18008a6f8  test    byte ptr [rsi+rbx*2], 4
0x18008a6fc  jz      short loc_18008A73E
0x18008a6fe  mov     rcx, cs:?Rby_hIntlLib@@3PEAUHINSTANCE__@@EA; hInstance
0x18008a705  lea     r8, [rsp+1060h+Buffer]; lpBuffer
0x18008a70a  mov     r9d, edi; cchBufferMax
0x18008a70d  mov     edx, 4DF0h; uID
0x18008a712  call    cs:__imp_LoadStringA
0x18008a718  lea     rdx, [rsp+1060h+Buffer]; lpString2
0x18008a71d  lea     rcx, [rbp+0F60h+String1]; lpString1
0x18008a724  call    cs:__imp_lstrcatA
0x18008a72a  lea     rdx, asc_1803ADF58; "+"
0x18008a731  lea     rcx, [rbp+0F60h+String1]; lpString1
0x18008a738  call    cs:__imp_lstrcatA
0x18008a73e  test    byte ptr [rsi+rbx*2], 10h
0x18008a742  jz      short loc_18008A784
0x18008a744  mov     rcx, cs:?Rby_hIntlLib@@3PEAUHINSTANCE__@@EA; hInstance
0x18008a74b  lea     r8, [rsp+1060h+Buffer]; lpBuffer
0x18008a750  mov     r9d, edi; cchBufferMax
0x18008a753  mov     edx, 4DEFh; uID
0x18008a758  call    cs:__imp_LoadStringA
0x18008a75e  lea     rdx, [rsp+1060h+Buffer]; lpString2
0x18008a763  lea     rcx, [rbp+0F60h+String1]; lpString1
0x18008a76a  call    cs:__imp_lstrcatA
0x18008a770  lea     rdx, asc_1803ADF58; "+"
0x18008a777  lea     rcx, [rbp+0F60h+String1]; lpString1
0x18008a77e  call    cs:__imp_lstrcatA
0x18008a784  movzx   eax, word ptr [rsi+rbx*2+2]
0x18008a789  cmp     ax, 41h ; 'A'
0x18008a78d  jb      short loc_18008A795
0x18008a78f  cmp     ax, 5Ah ; 'Z'
0x18008a793  jbe     short loc_18008A7A1
0x18008a795  cmp     ax, 30h ; '0'
0x18008a799  jb      short loc_18008A7BC
0x18008a79b  cmp     ax, 39h ; '9'
0x18008a79f  ja      short loc_18008A7BC
0x18008a7a1  lea     rdx, aC_0; "%c"
0x18008a7a8  lea     rcx, [rsp+1060h+Buffer]; LPSTR
0x18008a7ad  movzx   r8d, ax
0x18008a7b1  call    cs:__imp_wsprintfA
0x18008a7b7  jmp     loc_18008A89D
0x18008a7bc  cmp     ax, 70h ; 'p'
0x18008a7c0  jb      short loc_18008A7D6
0x18008a7c2  cmp     ax, 7Fh
0x18008a7c6  ja      short loc_18008A7D6
0x18008a7c8  movzx   edx, ax
0x18008a7cb  add     edx, 4D8Bh
0x18008a7d1  jmp     loc_18008A888
0x18008a7d6  movzx   ecx, ax
0x18008a7d9  cmp     ecx, 24h ; '$'
0x18008a7dc  jg      short loc_18008A83C
0x18008a7de  jz      short loc_18008A835
0x18008a7e0  sub     ecx, 3
0x18008a7e3  jz      short loc_18008A82E
0x18008a7e5  sub     ecx, 5
0x18008a7e8  jz      short loc_18008A827
0x18008a7ea  dec     ecx
0x18008a7ec  jz      short loc_18008A820
0x18008a7ee  sub     ecx, 0Ah
0x18008a7f1  jz      short loc_18008A819
0x18008a7f3  sub     ecx, 0Dh
0x18008a7f6  jz      short loc_18008A812
0x18008a7f8  dec     ecx
0x18008a7fa  jz      short loc_18008A80B
0x18008a7fc  dec     ecx
0x18008a7fe  jnz     loc_18008A91A
0x18008a804  mov     edx, 3BFh
0x18008a809  jmp     short loc_18008A882
0x18008a80b  mov     edx, 3BEh
0x18008a810  jmp     short loc_18008A882
0x18008a812  mov     edx, 3BDh
0x18008a817  jmp     short loc_18008A882
0x18008a819  mov     edx, 3BCh
0x18008a81e  jmp     short loc_18008A882
0x18008a820  mov     edx, 3BBh
0x18008a825  jmp     short loc_18008A882
0x18008a827  mov     edx, 3BAh
0x18008a82c  jmp     short loc_18008A882
0x18008a82e  mov     edx, 3B9h
0x18008a833  jmp     short loc_18008A882
0x18008a835  mov     edx, 3C0h
0x18008a83a  jmp     short loc_18008A882
0x18008a83c  sub     ecx, 25h ; '%'
0x18008a83f  jz      short loc_18008A87D
0x18008a841  dec     ecx
0x18008a843  jz      short loc_18008A876
0x18008a845  dec     ecx
0x18008a847  jz      short loc_18008A86F
0x18008a849  dec     ecx
0x18008a84b  jz      short loc_18008A868
0x18008a84d  sub     ecx, 5
0x18008a850  jz      short loc_18008A861
0x18008a852  dec     ecx
0x18008a854  jnz     loc_18008A91A
0x18008a85a  mov     edx, 3C2h
0x18008a85f  jmp     short loc_18008A882
0x18008a861  mov     edx, 3C1h
0x18008a866  jmp     short loc_18008A882
0x18008a868  mov     edx, 3D6h
0x18008a86d  jmp     short loc_18008A882
0x18008a86f  mov     edx, 3D4h
0x18008a874  jmp     short loc_18008A882
0x18008a876  mov     edx, 3D5h
0x18008a87b  jmp     short loc_18008A882
0x18008a87d  mov     edx, 3D3h
0x18008a882  add     edx, 4A38h; uID
0x18008a888  mov     rcx, cs:?Rby_hIntlLib@@3PEAUHINSTANCE__@@EA; hInstance
0x18008a88f  lea     r8, [rsp+1060h+Buffer]; lpBuffer
0x18008a894  mov     r9d, edi; cchBufferMax
0x18008a897  call    cs:__imp_LoadStringA
0x18008a89d  lea     rdx, [rsp+1060h+Buffer]; lpString2
0x18008a8a2  lea     rcx, [rbp+0F60h+String1]; lpString1
0x18008a8a9  call    cs:__imp_lstrcatA
0x18008a8af  mov     ebx, 1
0x18008a8b4  mov     rcx, rsi; Block
0x18008a8b7  call    cs:__imp_free
0x18008a8bd  test    ebx, ebx
0x18008a8bf  jnz     short loc_18008A8D2
0x18008a8c1  inc     r12d
0x18008a8c4  cmp     r12d, 3
0x18008a8c8  jl      loc_18008A602
0x18008a8ce  test    ebx, ebx
0x18008a8d0  jz      short loc_18008A8E8
0x18008a8d2  lea     rcx, [rbp+0F60h+String1]
0x18008a8d9  mov     r8d, 800h
0x18008a8df  mov     rdx, r13
0x18008a8e2  call    cs:?MsoSzToWtzAPI@@3P6AHPEBDPEA_WH@ZEA; int (*MsoSzToWtzAPI)(char const *,wchar_t *,int)
0x18008a8e8  mov     eax, ebx
0x18008a8ea  mov     rcx, [rbp+0F60h+var_30]
0x18008a8f1  xor     rcx, rsp; StackCookie
0x18008a8f4  call    __security_check_cookie
0x18008a8f9  lea     r11, [rsp+1060h+var_20]
0x18008a901  mov     rbx, [r11+30h]
0x18008a905  mov     rsi, [r11+40h]
0x18008a909  mov     rdi, [r11+48h]
0x18008a90d  mov     rsp, r11
0x18008a910  pop     r15
0x18008a912  pop     r14
0x18008a914  pop     r13
0x18008a916  pop     r12
0x18008a918  pop     rbp
0x18008a919  retn
0x18008a91a  mov     rcx, rsi; Block
0x18008a91d  call    cs:__imp_free
0x18008a923  jmp     loc_18008A5F8
```
