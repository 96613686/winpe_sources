# PropVariantToIDList

- ea: `0x180021ec0`
- end: `0x1800220fb`
- name: `PropVariantToIDList`
- size: `571`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800047b0`
- `0x180041300`

## callees

- `0x180009d00`
- `0x1800113b4`
- `0x18001f808`
- `0x180021e18`
- `0x180021ec0`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180022029`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180022029`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18002206f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18002206f`
- `SHELL32!SHGetSpecialFolderLocation` at `0x1800220e4`
- `SHELL32!SHGetSpecialFolderLocation` at `0x1800220e4`
- `SHELL32!SHParseDisplayName` at `0x1800220c6`
- `SHELL32!SHParseDisplayName` at `0x1800220c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022099`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180021f9b`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180021f9b`

## pseudocode

```c
__int64 __fastcall PropVariantToIDList(unsigned __int16 *a1, struct _ITEMIDLIST_ABSOLUTE **a2)
{
  unsigned int v3; // r8d
  unsigned int v5; // ebx
  unsigned int v6; // r8d
  unsigned int v7; // r8d
  unsigned int v8; // r8d
  unsigned int v9; // r8d
  unsigned int v10; // r8d
  int v11; // edx
  struct IUnknown *v12; // rcx
  struct IUnknown **v14; // rcx
  const struct _ITEMIDLIST_RELATIVE *v15; // r11
  const struct _ITEMIDLIST_RELATIVE *v16; // rcx
  int (__fastcall ***v17)(_QWORD, GUID *, IStream **); // rcx
  void *v18; // rcx
  ITEMIDLIST *v19; // rdi
  ULARGE_INTEGER pui; // [rsp+50h] [rbp+20h] BYREF
  IStream *pstm; // [rsp+58h] [rbp+28h] BYREF
  void *pv; // [rsp+60h] [rbp+30h] BYREF

  *a2 = 0;
  v3 = *a1;
  v5 = -2147024809;
  if ( v3 > 0x14 )
  {
    if ( v3 != 21 )
    {
      if ( v3 != 31 )
      {
        switch ( v3 )
        {
          case 0x42u:
            v17 = (int (__fastcall ***)(_QWORD, GUID *, IStream **))*((_QWORD *)a1 + 1);
            pstm = 0;
            if ( (**v17)(v17, &GUID_0000000c_0000_0000_c000_000000000046, &pstm) >= 0 )
            {
              pui.QuadPart = 0;
              v5 = IStream_Size(pstm, &pui);
              if ( (v5 & 0x80000000) == 0 )
              {
                v5 = -2147024809;
                if ( !pui.HighPart )
                {
                  pv = 0;
                  v5 = CTCoAllocPolicy::Alloc(v18, 1u, pui.LowPart, &pv);
                  if ( (v5 & 0x80000000) == 0 )
                  {
                    v19 = (ITEMIDLIST *)pv;
                    v5 = IStream_Read(pstm, pv, pui.LowPart);
                    if ( (v5 & 0x80000000) == 0 )
                    {
                      v5 = -2147024809;
                      if ( IDListContainerIsConsistent(v19, pui.LowPart) )
                      {
                        *a2 = (struct _ITEMIDLIST_ABSOLUTE *)v19;
                        v19 = 0;
                        v5 = 0;
                      }
                    }
                    CoTaskMemFree(v19);
                  }
                }
              }
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)pstm + 16LL))(pstm);
            }
            return v5;
          case 0x1011u:
            if ( !IDListContainerIsConsistent(*((LPCITEMIDLIST *)a1 + 2), *((_DWORD *)a1 + 2)) )
              return v5;
            v16 = (const struct _ITEMIDLIST_RELATIVE *)*((_QWORD *)a1 + 2);
            break;
          case 0x2011u:
            if ( SafeArrayGetDim(*((SAFEARRAY **)a1 + 1)) != 1
              || !IDListContainerIsConsistent(
                    *(LPCITEMIDLIST *)(*((_QWORD *)a1 + 1) + 16LL),
                    *(_DWORD *)(*((_QWORD *)a1 + 1) + 24LL)) )
            {
              return v5;
            }
            v16 = v15;
            break;
          case 0x4009u:
            v14 = (struct IUnknown **)*((_QWORD *)a1 + 1);
            if ( !v14 )
              return v5;
            v12 = *v14;
            return (unsigned int)_GetIDListFromObject(v12, a2);
          default:
            return v5;
        }
        return (unsigned int)SHILClone(v16, a2);
      }
      return (unsigned int)SHParseDisplayName(*((PCWSTR *)a1 + 1), 0, (LPITEMIDLIST *)a2, 0, 0);
    }
    goto LABEL_38;
  }
  if ( v3 == 20 )
  {
LABEL_38:
    if ( *((_QWORD *)a1 + 1) >= 0xFFFFu )
      return v5;
    v11 = *((_DWORD *)a1 + 2);
    return (unsigned int)SHGetSpecialFolderLocation(0, v11 | 0x8000, (LPITEMIDLIST *)a2);
  }
  v6 = v3 - 2;
  if ( !v6 )
  {
    v11 = (__int16)a1[4];
    return (unsigned int)SHGetSpecialFolderLocation(0, v11 | 0x8000, (LPITEMIDLIST *)a2);
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    v8 = v7 - 5;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 4;
        if ( v10 )
        {
          if ( v10 != 6 )
            return v5;
          goto LABEL_9;
        }
      }
      v12 = (struct IUnknown *)*((_QWORD *)a1 + 1);
      return (unsigned int)_GetIDListFromObject(v12, a2);
    }
    return (unsigned int)SHParseDisplayName(*((PCWSTR *)a1 + 1), 0, (LPITEMIDLIST *)a2, 0, 0);
  }
LABEL_9:
  v11 = *((_DWORD *)a1 + 2);
  if ( v11 < 0xFFFF )
    return (unsigned int)SHGetSpecialFolderLocation(0, v11 | 0x8000, (LPITEMIDLIST *)a2);
  return v5;
}

```

## disassembly

```asm
0x180021ec0  mov     [rsp-18h+arg_18], rbx
0x180021ec5  push    rbp
0x180021ec6  push    rsi
0x180021ec7  push    rdi
0x180021ec8  mov     rbp, rsp
0x180021ecb  sub     rsp, 30h
0x180021ecf  mov     qword ptr [rdx], 0
0x180021ed6  mov     rsi, rdx
0x180021ed9  movzx   r8d, word ptr [rcx]
0x180021edd  mov     rdi, rcx
0x180021ee0  mov     ebx, 80070057h
0x180021ee5  cmp     r8d, 14h
0x180021ee9  ja      short loc_180021F48
0x180021eeb  jz      loc_1800220CE
0x180021ef1  sub     r8d, 2
0x180021ef5  jz      short loc_180021F3F
0x180021ef7  sub     r8d, 1
0x180021efb  jz      short loc_180021F1D
0x180021efd  sub     r8d, 5
0x180021f01  jz      loc_1800220B1
0x180021f07  sub     r8d, 1
0x180021f0b  jz      short loc_180021F31
0x180021f0d  sub     r8d, 4
0x180021f11  jz      short loc_180021F31
0x180021f13  cmp     r8d, 6
0x180021f17  jnz     loc_1800220EC
0x180021f1d  mov     edx, [rcx+8]; struct _ITEMIDLIST_ABSOLUTE **
0x180021f20  cmp     edx, 0FFFFh
0x180021f26  jge     loc_1800220EC
0x180021f2c  jmp     loc_1800220DB
0x180021f31  mov     rcx, [rcx+8]; struct IUnknown *
0x180021f35  call    ?_GetIDListFromObject@@YAJPEAUIUnknown@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; _GetIDListFromObject(IUnknown *,_ITEMIDLIST_ABSOLUTE * *)
0x180021f3a  jmp     loc_1800220EA
0x180021f3f  movsx   edx, word ptr [rcx+8]
0x180021f43  jmp     loc_1800220DB
0x180021f48  cmp     r8d, 15h
0x180021f4c  jz      loc_1800220CE
0x180021f52  cmp     r8d, 1Fh
0x180021f56  jz      loc_1800220B1
0x180021f5c  cmp     r8d, 42h ; 'B'
0x180021f60  jz      loc_180021FEF
0x180021f66  cmp     r8d, 1011h
0x180021f6d  jz      short loc_180021FD5
0x180021f6f  cmp     r8d, 2011h
0x180021f76  jz      short loc_180021F97
0x180021f78  cmp     r8d, 4009h
0x180021f7f  jnz     loc_1800220EC
0x180021f85  mov     rcx, [rcx+8]
0x180021f89  test    rcx, rcx
0x180021f8c  jz      loc_1800220EC
0x180021f92  mov     rcx, [rcx]
0x180021f95  jmp     short loc_180021F35
0x180021f97  mov     rcx, [rcx+8]; psa
0x180021f9b  call    cs:__imp_SafeArrayGetDim
0x180021fa1  cmp     eax, 1
0x180021fa4  jnz     loc_1800220EC
0x180021faa  mov     rdx, [rdi+8]
0x180021fae  mov     r11, [rdx+10h]
0x180021fb2  mov     edx, [rdx+18h]; cbAlloc
0x180021fb5  mov     rcx, r11; pidl
0x180021fb8  call    IDListContainerIsConsistent
0x180021fbd  test    eax, eax
0x180021fbf  jz      loc_1800220EC
0x180021fc5  mov     rcx, r11; struct _ITEMIDLIST_RELATIVE *
0x180021fc8  mov     rdx, rsi; struct _ITEMIDLIST_RELATIVE **
0x180021fcb  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x180021fd0  jmp     loc_1800220EA
0x180021fd5  mov     edx, [rcx+8]; cbAlloc
0x180021fd8  mov     rcx, [rcx+10h]; pidl
0x180021fdc  call    IDListContainerIsConsistent
0x180021fe1  test    eax, eax
0x180021fe3  jz      loc_1800220EC
0x180021fe9  mov     rcx, [rdi+10h]
0x180021fed  jmp     short loc_180021FC8
0x180021fef  mov     rcx, [rcx+8]
0x180021ff3  lea     r8, [rbp+pstm]
0x180021ff7  mov     [rbp+pstm], 0
0x180021fff  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180022006  mov     rax, [rcx]
0x180022009  mov     rax, [rax]
0x18002200c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022011  test    eax, eax
0x180022013  js      loc_1800220EC
0x180022019  mov     rcx, [rbp+pstm]; pstm
0x18002201d  lea     rdx, [rbp+pui]; pui
0x180022021  mov     qword ptr [rbp+pui], 0
0x180022029  call    cs:__imp_IStream_Size
0x18002202f  mov     ebx, eax
0x180022031  test    eax, eax
0x180022033  js      short loc_18002209F
0x180022035  cmp     dword ptr [rbp+pui+4], 0
0x180022039  mov     ebx, 80070057h
0x18002203e  jnz     short loc_18002209F
0x180022040  mov     r8d, dword ptr [rbp+pui]; unsigned __int64
0x180022044  lea     r9, [rbp+pv]; void **
0x180022048  mov     edx, 1; unsigned int
0x18002204d  mov     [rbp+pv], 0
0x180022055  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002205a  mov     ebx, eax
0x18002205c  test    eax, eax
0x18002205e  js      short loc_18002209F
0x180022060  mov     rdi, [rbp+pv]
0x180022064  mov     r8d, dword ptr [rbp+pui]; cb
0x180022068  mov     rdx, rdi; pv
0x18002206b  mov     rcx, [rbp+pstm]; pstm
0x18002206f  call    cs:__imp_IStream_Read
0x180022075  mov     ebx, eax
0x180022077  test    eax, eax
0x180022079  js      short loc_180022096
0x18002207b  mov     edx, dword ptr [rbp+pui]; cbAlloc
0x18002207e  mov     rcx, rdi; pidl
0x180022081  mov     ebx, 80070057h
0x180022086  call    IDListContainerIsConsistent
0x18002208b  test    eax, eax
0x18002208d  jz      short loc_180022096
0x18002208f  mov     [rsi], rdi
0x180022092  xor     edi, edi
0x180022094  xor     ebx, ebx
0x180022096  mov     rcx, rdi; pv
0x180022099  call    cs:__imp_CoTaskMemFree
0x18002209f  mov     rcx, [rbp+pstm]
0x1800220a3  mov     rax, [rcx]
0x1800220a6  mov     rax, [rax+10h]
0x1800220aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220af  jmp     short loc_1800220EC
0x1800220b1  mov     rcx, [rcx+8]; pszName
0x1800220b5  xor     r9d, r9d; sfgaoIn
0x1800220b8  mov     r8, rsi; ppidl
0x1800220bb  mov     [rsp+30h+psfgaoOut], 0; psfgaoOut
0x1800220c4  xor     edx, edx; pbc
0x1800220c6  call    cs:__imp_SHParseDisplayName
0x1800220cc  jmp     short loc_1800220EA
0x1800220ce  cmp     qword ptr [rcx+8], 0FFFFh
0x1800220d6  jnb     short loc_1800220EC
0x1800220d8  mov     edx, [rcx+8]
0x1800220db  mov     r8, rsi; ppidl
0x1800220de  bts     edx, 0Fh; csidl
0x1800220e2  xor     ecx, ecx; hwnd
0x1800220e4  call    cs:__imp_SHGetSpecialFolderLocation
0x1800220ea  mov     ebx, eax
0x1800220ec  mov     eax, ebx
0x1800220ee  mov     rbx, [rsp+30h+arg_18]
0x1800220f3  add     rsp, 30h
0x1800220f7  pop     rdi
0x1800220f8  pop     rsi
0x1800220f9  pop     rbp
0x1800220fa  retn
```
