# CSpellerGlobalState::RemoveSpellCheckingResources(void)

- ea: `0x180270970`
- end: `0x180270a8d`
- name: `?RemoveSpellCheckingResources@CSpellerGlobalState@@AEAAXXZ`
- size: `285`
- prototype: `void __fastcall(CSpellerGlobalState *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18026f074`
- `0x1802723a0`

## callees

- `0x180048d5c`
- `0x18013bf70`
- `0x18026f2dc`
- `0x180270970`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1802709be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180270a0b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180270a69`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1802709be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180270a0b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180270a69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180270a48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180270a48`

## pseudocode

```c
void __fastcall CSpellerGlobalState::RemoveSpellCheckingResources(CSpellerGlobalState *this, unsigned int a2)
{
  __int64 v2; // rbx
  int v4; // edi
  void *v5; // rcx
  __int64 v6; // rbx
  int v7; // edi
  CSpellCheckSpeller *v8; // rcx
  __int64 v9; // rbx
  int v10; // edi
  HSTRING *v11; // rbx

  v2 = *((_QWORD *)this + 5);
  if ( v2 )
  {
    if ( *(_DWORD *)(v2 + 4) )
    {
      v4 = 0;
      do
      {
        if ( v4 < 0 || (unsigned int)v4 >= *(_DWORD *)(v2 + 4) )
          v5 = 0;
        else
          v5 = *(void **)((unsigned int)(*(_DWORD *)(v2 + 8) * v4) + *(_QWORD *)(v2 + 16));
        operator delete(v5);
        v2 = *((_QWORD *)this + 5);
        ++v4;
      }
      while ( (unsigned int)v4 < *(_DWORD *)(v2 + 4) );
    }
    free(*(void **)(v2 + 16));
    *(_QWORD *)(v2 + 16) = 0;
    *(_QWORD *)v2 = 0;
  }
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    if ( *(_DWORD *)(v6 + 4) )
    {
      v7 = 0;
      do
      {
        if ( v7 >= 0 && (unsigned int)v7 < *(_DWORD *)(v6 + 4) )
        {
          v8 = *(CSpellCheckSpeller **)((unsigned int)(*(_DWORD *)(v6 + 8) * v7) + *(_QWORD *)(v6 + 16));
          if ( v8 )
            CSpellCheckSpeller::`scalar deleting destructor'(v8, a2);
        }
        v6 = *((_QWORD *)this + 3);
        ++v7;
      }
      while ( (unsigned int)v7 < *(_DWORD *)(v6 + 4) );
    }
    free(*(void **)(v6 + 16));
    *(_QWORD *)(v6 + 16) = 0;
    *(_QWORD *)v6 = 0;
  }
  v9 = *((_QWORD *)this + 4);
  if ( v9 )
  {
    if ( *(_DWORD *)(v9 + 4) )
    {
      v10 = 0;
      do
      {
        if ( v10 >= 0 && (unsigned int)v10 < *(_DWORD *)(v9 + 4) )
        {
          v11 = *(HSTRING **)((unsigned int)(*(_DWORD *)(v9 + 8) * v10) + *(_QWORD *)(v9 + 16));
          if ( v11 )
          {
            WindowsDeleteString(v11[1]);
            v11[1] = 0;
            operator delete(v11);
          }
        }
        v9 = *((_QWORD *)this + 4);
        ++v10;
      }
      while ( (unsigned int)v10 < *(_DWORD *)(v9 + 4) );
    }
    free(*(void **)(v9 + 16));
    *(_QWORD *)(v9 + 16) = 0;
    *(_QWORD *)v9 = 0;
  }
  if ( *((_QWORD *)this + 6) )
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 48);
}

```

## disassembly

```asm
0x180270970  push    rbx
0x180270972  push    rbp
0x180270973  push    rsi
0x180270974  push    rdi
0x180270975  sub     rsp, 28h
0x180270979  mov     rbx, [rcx+28h]
0x18027097d  xor     ebp, ebp
0x18027097f  mov     rsi, rcx
0x180270982  test    rbx, rbx
0x180270985  jz      short loc_1802709CB
0x180270987  cmp     [rbx+4], ebp
0x18027098a  jbe     short loc_1802709BA
0x18027098c  mov     edi, ebp
0x18027098e  test    edi, edi
0x180270990  js      short loc_1802709A7
0x180270992  cmp     edi, [rbx+4]
0x180270995  jnb     short loc_1802709A7
0x180270997  mov     rax, [rbx+10h]
0x18027099b  mov     ecx, edi
0x18027099d  imul    ecx, [rbx+8]
0x1802709a1  mov     rcx, [rcx+rax]
0x1802709a5  jmp     short loc_1802709AA
0x1802709a7  mov     rcx, rbp; Block
0x1802709aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1802709af  mov     rbx, [rsi+28h]
0x1802709b3  inc     edi
0x1802709b5  cmp     edi, [rbx+4]
0x1802709b8  jb      short loc_18027098E
0x1802709ba  mov     rcx, [rbx+10h]; Block
0x1802709be  call    cs:__imp_free
0x1802709c4  mov     [rbx+10h], rbp
0x1802709c8  mov     [rbx], rbp
0x1802709cb  mov     rbx, [rsi+18h]
0x1802709cf  test    rbx, rbx
0x1802709d2  jz      short loc_180270A18
0x1802709d4  cmp     [rbx+4], ebp
0x1802709d7  jbe     short loc_180270A07
0x1802709d9  mov     edi, ebp
0x1802709db  test    edi, edi
0x1802709dd  js      short loc_1802709FC
0x1802709df  cmp     edi, [rbx+4]
0x1802709e2  jnb     short loc_1802709FC
0x1802709e4  mov     rax, [rbx+10h]
0x1802709e8  mov     ecx, edi
0x1802709ea  imul    ecx, [rbx+8]
0x1802709ee  mov     rcx, [rcx+rax]; this
0x1802709f2  test    rcx, rcx
0x1802709f5  jz      short loc_1802709FC
0x1802709f7  call    ??_GCSpellCheckSpeller@@QEAAPEAXI@Z; CSpellCheckSpeller::`scalar deleting destructor'(uint)
0x1802709fc  mov     rbx, [rsi+18h]
0x180270a00  inc     edi
0x180270a02  cmp     edi, [rbx+4]
0x180270a05  jb      short loc_1802709DB
0x180270a07  mov     rcx, [rbx+10h]; Block
0x180270a0b  call    cs:__imp_free
0x180270a11  mov     [rbx+10h], rbp
0x180270a15  mov     [rbx], rbp
0x180270a18  mov     rbx, [rsi+20h]
0x180270a1c  test    rbx, rbx
0x180270a1f  jz      short loc_180270A76
0x180270a21  cmp     [rbx+4], ebp
0x180270a24  jbe     short loc_180270A65
0x180270a26  mov     edi, ebp
0x180270a28  test    edi, edi
0x180270a2a  js      short loc_180270A5A
0x180270a2c  cmp     edi, [rbx+4]
0x180270a2f  jnb     short loc_180270A5A
0x180270a31  mov     rax, [rbx+10h]
0x180270a35  mov     ecx, edi
0x180270a37  imul    ecx, [rbx+8]
0x180270a3b  mov     rbx, [rcx+rax]
0x180270a3f  test    rbx, rbx
0x180270a42  jz      short loc_180270A5A
0x180270a44  mov     rcx, [rbx+8]; string
0x180270a48  call    cs:__imp_WindowsDeleteString
0x180270a4e  mov     rcx, rbx; Block
0x180270a51  mov     [rbx+8], rbp
0x180270a55  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180270a5a  mov     rbx, [rsi+20h]
0x180270a5e  inc     edi
0x180270a60  cmp     edi, [rbx+4]
0x180270a63  jb      short loc_180270A28
0x180270a65  mov     rcx, [rbx+10h]; Block
0x180270a69  call    cs:__imp_free
0x180270a6f  mov     [rbx+10h], rbp
0x180270a73  mov     [rbx], rbp
0x180270a76  lea     rcx, [rsi+30h]
0x180270a7a  cmp     [rcx], rbp
0x180270a7d  jz      short loc_180270A84
0x180270a7f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180270a84  add     rsp, 28h
0x180270a88  pop     rdi
0x180270a89  pop     rsi
0x180270a8a  pop     rbp
0x180270a8b  pop     rbx
0x180270a8c  retn
```
