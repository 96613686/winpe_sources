# SecurityContext::GetRuntimeData(_TASK_RUNTIME_DATA *)

- ea: `0x18001fdfc`
- end: `0x18001ff68`
- name: `?GetRuntimeData@SecurityContext@@QEAAJPEAU_TASK_RUNTIME_DATA@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(SecurityContext *__hidden this, struct _TASK_RUNTIME_DATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180017e48`

## callees

- `0x18001fdfc`
- `0x180020250`
- `0x1800202ec`

## import_xrefs

- `msvcrt!free` at `0x18001fe62`
- `msvcrt!free` at `0x18001fe62`
- `msvcrt!malloc` at `0x18001feac`
- `msvcrt!malloc` at `0x18001ff01`
- `msvcrt!malloc` at `0x18001feac`
- `msvcrt!malloc` at `0x18001ff01`

## pseudocode

```c
__int64 __fastcall SecurityContext::GetRuntimeData(SecurityContext *this, struct _TASK_RUNTIME_DATA *a2)
{
  void *v2; // rdi
  int UserSidReturnedCopy; // ebx
  void **v6; // rsi
  unsigned int j; // ebp
  __int64 v9; // rax
  _DWORD *v10; // rax
  _DWORD *v11; // rbx
  unsigned int i; // ebp
  __int64 v13; // rax
  void *Block; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  Block = 0;
  if ( !a2 )
  {
    UserSidReturnedCopy = -2147467261;
    goto LABEL_3;
  }
  if ( !*((_BYTE *)this + 16) )
  {
    UserSidReturnedCopy = -2147467259;
    goto LABEL_3;
  }
  UserSidReturnedCopy = TsiCreateUserSidReturnedCopy(&Block, *(_QWORD *)this);
  if ( UserSidReturnedCopy >= 0 )
  {
    if ( !*((_QWORD *)this + 1) )
      goto LABEL_22;
    v2 = malloc(0x18u);
    if ( !v2 )
    {
LABEL_13:
      UserSidReturnedCopy = -2147024882;
      goto LABEL_3;
    }
    *(_OWORD *)v2 = 0;
    *((_QWORD *)v2 + 2) = 0;
    UserSidReturnedCopy = TsiCreateUserSidReturnedCopy(v2, **((_QWORD **)this + 1));
    if ( UserSidReturnedCopy >= 0 )
    {
      v9 = *((_QWORD *)this + 1);
      if ( *(_DWORD *)(v9 + 16) && *(_QWORD *)(v9 + 8) )
      {
        v10 = malloc(16LL * *(unsigned int *)(v9 + 16));
        *((_QWORD *)v2 + 1) = v10;
        v11 = v10;
        if ( !v10 )
          goto LABEL_13;
        for ( i = 0; ; ++i )
        {
          v13 = *((_QWORD *)this + 1);
          if ( i >= *(_DWORD *)(v13 + 16) )
            break;
          v11[2] = *(_DWORD *)(*(_QWORD *)(v13 + 8) + 16LL * i + 8);
          if ( (int)TsiCreateUserSidReturnedCopy(v11, *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL) + 16LL * i)) < 0 )
            goto LABEL_13;
          v11 += 4;
        }
      }
LABEL_22:
      UserSidReturnedCopy = 0;
      *((_QWORD *)a2 + 2) = Block;
      *((_QWORD *)a2 + 3) = v2;
      return (unsigned int)UserSidReturnedCopy;
    }
  }
LABEL_3:
  TsiFreeUserSidReturnedCopy(Block);
  if ( v2 )
  {
    TsiFreeUserSidReturnedCopy(*(void **)v2);
    v6 = (void **)*((_QWORD *)v2 + 1);
    for ( j = 0; j < *((_DWORD *)v2 + 4); v6 += 2 )
    {
      TsiFreeUserSidReturnedCopy(*v6);
      ++j;
    }
    free(*((void **)v2 + 1));
  }
  return (unsigned int)UserSidReturnedCopy;
}

```

## disassembly

```asm
0x18001fdfc  mov     [rsp+arg_0], rbx
0x18001fe01  mov     [rsp+arg_10], rbp
0x18001fe06  push    rsi
0x18001fe07  push    rdi
0x18001fe08  push    r14
0x18001fe0a  sub     rsp, 20h
0x18001fe0e  xor     edi, edi
0x18001fe10  mov     [rsp+38h+Block], 0
0x18001fe19  mov     r14, rdx
0x18001fe1c  mov     rsi, rcx
0x18001fe1f  test    rdx, rdx
0x18001fe22  jnz     short loc_18001FE7D
0x18001fe24  mov     ebx, 80004003h
0x18001fe29  mov     rcx, [rsp+38h+Block]; Block
0x18001fe2e  call    TsiFreeUserSidReturnedCopy
0x18001fe33  test    rdi, rdi
0x18001fe36  jz      short loc_18001FE68
0x18001fe38  mov     rcx, [rdi]; Block
0x18001fe3b  call    TsiFreeUserSidReturnedCopy
0x18001fe40  mov     rsi, [rdi+8]
0x18001fe44  xor     ebp, ebp
0x18001fe46  cmp     [rdi+10h], ebp
0x18001fe49  jbe     short loc_18001FE5E
0x18001fe4b  mov     rcx, [rsi]; Block
0x18001fe4e  call    TsiFreeUserSidReturnedCopy
0x18001fe53  inc     ebp
0x18001fe55  lea     rsi, [rsi+10h]
0x18001fe59  cmp     ebp, [rdi+10h]
0x18001fe5c  jb      short loc_18001FE4B
0x18001fe5e  mov     rcx, [rdi+8]; Block
0x18001fe62  call    cs:__imp_free
0x18001fe68  mov     rbp, [rsp+38h+arg_10]
0x18001fe6d  mov     eax, ebx
0x18001fe6f  mov     rbx, [rsp+38h+arg_0]
0x18001fe74  add     rsp, 20h
0x18001fe78  pop     r14
0x18001fe7a  pop     rdi
0x18001fe7b  pop     rsi
0x18001fe7c  retn
0x18001fe7d  cmp     [rcx+10h], dil
0x18001fe81  jnz     short loc_18001FE8A
0x18001fe83  mov     ebx, 80004005h
0x18001fe88  jmp     short loc_18001FE29
0x18001fe8a  mov     rdx, [rcx]
0x18001fe8d  lea     rcx, [rsp+38h+Block]
0x18001fe92  call    TsiCreateUserSidReturnedCopy
0x18001fe97  mov     ebx, eax
0x18001fe99  test    eax, eax
0x18001fe9b  js      short loc_18001FE29
0x18001fe9d  cmp     [rsi+8], rdi
0x18001fea1  jz      loc_18001FF54
0x18001fea7  mov     ecx, 18h; Size
0x18001feac  call    cs:__imp_malloc
0x18001feb2  mov     rdi, rax
0x18001feb5  test    rax, rax
0x18001feb8  jnz     short loc_18001FEC4
0x18001feba  mov     ebx, 8007000Eh
0x18001febf  jmp     loc_18001FE29
0x18001fec4  xorps   xmm0, xmm0
0x18001fec7  xor     eax, eax
0x18001fec9  movups  xmmword ptr [rdi], xmm0
0x18001fecc  mov     [rdi+10h], rax
0x18001fed0  mov     rcx, rdi
0x18001fed3  mov     rdx, [rsi+8]
0x18001fed7  mov     rdx, [rdx]
0x18001feda  call    TsiCreateUserSidReturnedCopy
0x18001fedf  mov     ebx, eax
0x18001fee1  test    eax, eax
0x18001fee3  js      loc_18001FE29
0x18001fee9  mov     rax, [rsi+8]
0x18001feed  cmp     dword ptr [rax+10h], 0
0x18001fef1  jbe     short loc_18001FF54
0x18001fef3  cmp     qword ptr [rax+8], 0
0x18001fef8  jz      short loc_18001FF54
0x18001fefa  mov     ecx, [rax+10h]
0x18001fefd  shl     rcx, 4; Size
0x18001ff01  call    cs:__imp_malloc
0x18001ff07  mov     [rdi+8], rax
0x18001ff0b  mov     rbx, rax
0x18001ff0e  test    rax, rax
0x18001ff11  jz      short loc_18001FEBA
0x18001ff13  xor     ebp, ebp
0x18001ff15  mov     rax, [rsi+8]
0x18001ff19  cmp     ebp, [rax+10h]
0x18001ff1c  jnb     short loc_18001FF54
0x18001ff1e  mov     rax, [rax+8]
0x18001ff22  mov     r8d, ebp
0x18001ff25  add     r8, r8
0x18001ff28  mov     ecx, [rax+r8*8+8]
0x18001ff2d  mov     [rbx+8], ecx
0x18001ff30  mov     rcx, rbx
0x18001ff33  mov     rax, [rsi+8]
0x18001ff37  mov     rdx, [rax+8]
0x18001ff3b  mov     rdx, [rdx+r8*8]
0x18001ff3f  call    TsiCreateUserSidReturnedCopy
0x18001ff44  test    eax, eax
0x18001ff46  js      loc_18001FEBA
0x18001ff4c  add     rbx, 10h
0x18001ff50  inc     ebp
0x18001ff52  jmp     short loc_18001FF15
0x18001ff54  mov     rax, [rsp+38h+Block]
0x18001ff59  xor     ebx, ebx
0x18001ff5b  mov     [r14+10h], rax
0x18001ff5f  mov     [r14+18h], rdi
0x18001ff63  jmp     loc_18001FE68
```
