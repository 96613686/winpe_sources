# CTreeWalker::_DeleteAlternateStream(ushort *,ulong,unsigned __int64)

- ea: `0x18004c754`
- end: `0x18004c8bd`
- name: `?_DeleteAlternateStream@CTreeWalker@@AEAAJPEAGK_K@Z`
- size: `361`
- prototype: `__int64 __fastcall(CTreeWalker *__hidden this, unsigned __int16 *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18004c658`

## callees

- `0x1800450e0`
- `0x18004c754`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004c895`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004c895`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004c7e9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004c7e9`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x18004c848`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x18004c848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c868`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c887`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c887`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004c7c3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004c7c3`
- `api-ms-win-core-file-l1-2-5!DeleteFile2W` at `0x18004c85a`
- `api-ms-win-core-file-l1-2-5!DeleteFile2W` at `0x18004c85a`

## pseudocode

```c
__int64 __fastcall CTreeWalker::_DeleteAlternateStream(
        WCHAR *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int64 a4)
{
  unsigned int v4; // esi
  HANDLE FileW; // r14
  int FolderPath; // ebx
  unsigned __int16 *v10; // rdi
  unsigned int i; // eax
  signed int LastError; // eax
  union _LARGE_INTEGER v14; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v15; // [rsp+90h] [rbp+18h] BYREF

  v15 = 0;
  v4 = a3 >> 1;
  v14.QuadPart = 0;
  if ( a3 >> 1 >= 2 && *a2 == 58 )
  {
    FileW = CreateFileW(this + 164, 0x100u, 3u, 0, 3u, 0x2000080u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      return (unsigned int)-2147024891;
    }
    else
    {
      v10 = (unsigned __int16 *)malloc(2LL * (v4 + 260));
      if ( v10 )
      {
        FolderPath = CTreeWalker::GetFolderPath((CTreeWalker *)this, FileW, a4, &v15, v10, &v14);
        if ( FolderPath >= 0 )
        {
          for ( i = 1; i < v4; ++i )
          {
            if ( a2[i] == 58 )
            {
              if ( (unsigned int)_o_wcsncat_s(v10, v4 + 260, a2) )
                goto LABEL_16;
              if ( (unsigned int)DeleteFile2W(v10, 0x10000) )
              {
                FolderPath = 0;
              }
              else
              {
                LastError = GetLastError();
                FolderPath = LastError;
                if ( LastError > 0 )
                  FolderPath = (unsigned __int16)LastError | 0x80070000;
              }
              break;
            }
          }
        }
      }
      else
      {
LABEL_16:
        FolderPath = -2147024882;
      }
      CloseHandle(FileW);
      if ( v10 )
        free(v10);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)FolderPath;
}

```

## disassembly

```asm
0x18004c754  mov     rax, rsp
0x18004c757  mov     [rax+8], rbx
0x18004c75b  mov     [rax+10h], rbp
0x18004c75f  push    rsi
0x18004c760  push    rdi
0x18004c761  push    r12
0x18004c763  push    r14
0x18004c765  push    r15
0x18004c767  sub     rsp, 50h
0x18004c76b  mov     esi, r8d
0x18004c76e  mov     dword ptr [rax+18h], 0
0x18004c775  shr     esi, 1
0x18004c777  mov     r12, r9
0x18004c77a  mov     qword ptr [rax-38h], 0
0x18004c782  mov     rbp, rdx
0x18004c785  mov     rbx, rcx
0x18004c788  cmp     esi, 2
0x18004c78b  jb      loc_18004C89D
0x18004c791  cmp     word ptr [rdx], 3Ah ; ':'
0x18004c795  jnz     loc_18004C89D
0x18004c79b  mov     qword ptr [rax-48h], 0
0x18004c7a3  mov     r8d, 3; dwShareMode
0x18004c7a9  mov     dword ptr [rax-50h], 2000080h
0x18004c7b0  add     rcx, 148h; lpFileName
0x18004c7b7  xor     r9d, r9d; lpSecurityAttributes
0x18004c7ba  mov     [rax-58h], r8d
0x18004c7be  mov     edx, 100h; dwDesiredAccess
0x18004c7c3  call    cs:__imp_CreateFileW
0x18004c7c9  mov     r14, rax
0x18004c7cc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004c7d0  jnz     short loc_18004C7DC
0x18004c7d2  mov     ebx, 80070005h
0x18004c7d7  jmp     loc_18004C8A2
0x18004c7dc  lea     eax, [rsi+104h]
0x18004c7e2  lea     rcx, [rax+rax]; Size
0x18004c7e6  mov     r15d, eax
0x18004c7e9  call    cs:__imp_malloc
0x18004c7ef  mov     rdi, rax
0x18004c7f2  test    rax, rax
0x18004c7f5  jz      loc_18004C87F
0x18004c7fb  lea     rax, [rsp+78h+var_38]
0x18004c800  mov     r8, r12; __int64
0x18004c803  mov     [rsp+78h+var_50], rax; union _LARGE_INTEGER *
0x18004c808  lea     r9, [rsp+78h+arg_10]; unsigned int *
0x18004c810  mov     rdx, r14; void *
0x18004c813  mov     [rsp+78h+var_58], rdi; unsigned __int16 *
0x18004c818  mov     rcx, rbx; this
0x18004c81b  call    ?GetFolderPath@CTreeWalker@@AEAAJPEAX_JPEAKPEAGPEAT_LARGE_INTEGER@@K@Z; CTreeWalker::GetFolderPath(void *,__int64,ulong *,ushort *,_LARGE_INTEGER *,ulong)
0x18004c820  mov     ebx, eax
0x18004c822  test    eax, eax
0x18004c824  js      short loc_18004C884
0x18004c826  mov     eax, 1
0x18004c82b  cmp     eax, esi
0x18004c82d  jnb     short loc_18004C884
0x18004c82f  mov     r9d, eax
0x18004c832  cmp     word ptr [rbp+r9*2+0], 3Ah ; ':'
0x18004c839  jz      short loc_18004C83F
0x18004c83b  inc     eax
0x18004c83d  jmp     short loc_18004C82B
0x18004c83f  mov     r8, rbp
0x18004c842  mov     rdx, r15
0x18004c845  mov     rcx, rdi
0x18004c848  call    cs:__imp__o_wcsncat_s
0x18004c84e  test    eax, eax
0x18004c850  jnz     short loc_18004C87F
0x18004c852  mov     edx, 10000h
0x18004c857  mov     rcx, rdi
0x18004c85a  call    cs:__imp_DeleteFile2W
0x18004c860  test    eax, eax
0x18004c862  jz      short loc_18004C868
0x18004c864  xor     ebx, ebx
0x18004c866  jmp     short loc_18004C884
0x18004c868  call    cs:__imp_GetLastError
0x18004c86e  mov     ebx, eax
0x18004c870  test    eax, eax
0x18004c872  jle     short loc_18004C884
0x18004c874  movzx   ebx, ax
0x18004c877  or      ebx, 80070000h
0x18004c87d  jmp     short loc_18004C884
0x18004c87f  mov     ebx, 8007000Eh
0x18004c884  mov     rcx, r14; hObject
0x18004c887  call    cs:__imp_CloseHandle
0x18004c88d  test    rdi, rdi
0x18004c890  jz      short loc_18004C8A2
0x18004c892  mov     rcx, rdi; Block
0x18004c895  call    cs:__imp_free
0x18004c89b  jmp     short loc_18004C8A2
0x18004c89d  mov     ebx, 80070057h
0x18004c8a2  lea     r11, [rsp+78h+var_28]
0x18004c8a7  mov     eax, ebx
0x18004c8a9  mov     rbx, [r11+30h]
0x18004c8ad  mov     rbp, [r11+38h]
0x18004c8b1  mov     rsp, r11
0x18004c8b4  pop     r15
0x18004c8b6  pop     r14
0x18004c8b8  pop     r12
0x18004c8ba  pop     rdi
0x18004c8bb  pop     rsi
0x18004c8bc  retn
```
