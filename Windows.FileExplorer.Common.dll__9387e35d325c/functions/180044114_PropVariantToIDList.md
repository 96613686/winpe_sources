# PropVariantToIDList

- ea: `0x180044114`
- end: `0x18004434a`
- name: `PropVariantToIDList`
- size: `566`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041008`

## callees

- `0x18001dd40`
- `0x180043bb4`
- `0x1800440c8`
- `0x180044114`
- `0x180089010`

## import_xrefs

- `Windows.Storage!SHGetSpecialFolderLocation` at `0x180044335`
- `Windows.Storage!SHGetSpecialFolderLocation` at `0x180044335`
- `Windows.Storage!SHParseDisplayName` at `0x180044317`
- `Windows.Storage!SHParseDisplayName` at `0x180044317`
- `Windows.Storage!ILClone` at `0x180044222`
- `Windows.Storage!ILClone` at `0x180044222`
- `SHCORE!IStream_Read` at `0x1800442c2`
- `SHCORE!IStream_Read` at `0x1800442c2`
- `SHCORE!IStream_Size` at `0x18004427e`
- `SHCORE!IStream_Size` at `0x18004427e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800442ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800442ea`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800441e7`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800441e7`

## pseudocode

```c
__int64 __fastcall PropVariantToIDList(unsigned __int16 *a1, struct _ITEMIDLIST_ABSOLUTE **a2)
{
  unsigned int v3; // edx
  unsigned int v5; // ebx
  unsigned int v6; // edx
  unsigned int v7; // edx
  unsigned int v8; // edx
  unsigned int v9; // edx
  unsigned int v10; // edx
  int v11; // edx
  struct IUnknown *v12; // rcx
  struct IUnknown **v14; // rcx
  __int64 v15; // rdx
  const ITEMIDLIST *v16; // r11
  UINT v17; // edx
  const ITEMIDLIST *v18; // r11
  LPITEMIDLIST v19; // rax
  int (__fastcall ***v20)(_QWORD, GUID *, IStream **); // rcx
  void *v21; // rcx
  ITEMIDLIST *v22; // rsi
  ULARGE_INTEGER pui; // [rsp+60h] [rbp+30h] BYREF
  IStream *pstm; // [rsp+68h] [rbp+38h] BYREF
  void *pv; // [rsp+70h] [rbp+40h] BYREF

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
            v20 = (int (__fastcall ***)(_QWORD, GUID *, IStream **))*((_QWORD *)a1 + 1);
            pstm = 0;
            if ( (**v20)(v20, &GUID_0000000c_0000_0000_c000_000000000046, &pstm) >= 0 )
            {
              pui.QuadPart = 0;
              v5 = IStream_Size(pstm, &pui);
              if ( (v5 & 0x80000000) == 0 )
              {
                v5 = -2147024809;
                if ( !pui.HighPart )
                {
                  pv = 0;
                  v5 = CTCoAllocPolicy::Alloc(v21, 1u, pui.LowPart, &pv);
                  if ( (v5 & 0x80000000) == 0 )
                  {
                    v22 = (ITEMIDLIST *)pv;
                    v5 = IStream_Read(pstm, pv, pui.LowPart);
                    if ( (v5 & 0x80000000) == 0 )
                    {
                      v5 = -2147024809;
                      if ( IDListContainerIsConsistent(v22, pui.LowPart) )
                      {
                        *a2 = (struct _ITEMIDLIST_ABSOLUTE *)v22;
                        v22 = 0;
                        v5 = 0;
                      }
                    }
                    CoTaskMemFree(v22);
                  }
                }
              }
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)pstm + 16LL))(pstm);
            }
            return v5;
          case 0x1011u:
            v16 = (const ITEMIDLIST *)*((_QWORD *)a1 + 2);
            v17 = *((_DWORD *)a1 + 2);
            break;
          case 0x2011u:
            if ( SafeArrayGetDim(*((SAFEARRAY **)a1 + 1)) != 1 )
              return v5;
            v15 = *((_QWORD *)a1 + 1);
            v16 = *(const ITEMIDLIST **)(v15 + 16);
            v17 = *(_DWORD *)(v15 + 24);
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
        if ( IDListContainerIsConsistent(v16, v17) )
        {
          if ( v18 )
          {
            v19 = ILClone(v18);
            v5 = v19 == 0 ? 0x8007000E : 0;
          }
          else
          {
            v19 = 0;
          }
          *a2 = (struct _ITEMIDLIST_ABSOLUTE *)v19;
        }
        return v5;
      }
      return (unsigned int)SHParseDisplayName(*((PCWSTR *)a1 + 1), 0, (LPITEMIDLIST *)a2, 0, 0);
    }
    goto LABEL_40;
  }
  if ( v3 == 20 )
  {
LABEL_40:
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
0x180044114  push    rbp
0x180044116  push    rbx
0x180044117  push    rsi
0x180044118  push    rdi
0x180044119  push    r15
0x18004411b  mov     rbp, rsp
0x18004411e  sub     rsp, 30h
0x180044122  mov     rdi, rdx
0x180044125  mov     qword ptr [rdx], 0
0x18004412c  movzx   edx, word ptr [rcx]
0x18004412f  mov     r15d, 80070057h
0x180044135  mov     rsi, rcx
0x180044138  mov     ebx, r15d
0x18004413b  cmp     edx, 14h
0x18004413e  ja      short loc_18004419A
0x180044140  jz      loc_18004431F
0x180044146  sub     edx, 2
0x180044149  jz      short loc_180044191
0x18004414b  sub     edx, 1
0x18004414e  jz      short loc_18004416C
0x180044150  sub     edx, 5
0x180044153  jz      loc_180044302
0x180044159  sub     edx, 1
0x18004415c  jz      short loc_180044180
0x18004415e  sub     edx, 4
0x180044161  jz      short loc_180044180
0x180044163  cmp     edx, 6
0x180044166  jnz     loc_18004433D
0x18004416c  mov     edx, [rcx+8]
0x18004416f  cmp     edx, 0FFFFh
0x180044175  jge     loc_18004433D
0x18004417b  jmp     loc_18004432C
0x180044180  mov     rcx, [rcx+8]; struct IUnknown *
0x180044184  mov     rdx, rdi; struct _ITEMIDLIST_ABSOLUTE **
0x180044187  call    ?_GetIDListFromObject@@YAJPEAUIUnknown@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; _GetIDListFromObject(IUnknown *,_ITEMIDLIST_ABSOLUTE * *)
0x18004418c  jmp     loc_18004433B
0x180044191  movsx   edx, word ptr [rcx+8]
0x180044195  jmp     loc_18004432C
0x18004419a  cmp     edx, 15h
0x18004419d  jz      loc_18004431F
0x1800441a3  cmp     edx, 1Fh
0x1800441a6  jz      loc_180044302
0x1800441ac  cmp     edx, 42h ; 'B'
0x1800441af  jz      loc_180044244
0x1800441b5  cmp     edx, 1011h
0x1800441bb  jz      short loc_180044203
0x1800441bd  cmp     edx, 2011h
0x1800441c3  jz      short loc_1800441E3
0x1800441c5  cmp     edx, 4009h
0x1800441cb  jnz     loc_18004433D
0x1800441d1  mov     rcx, [rcx+8]
0x1800441d5  test    rcx, rcx
0x1800441d8  jz      loc_18004433D
0x1800441de  mov     rcx, [rcx]
0x1800441e1  jmp     short loc_180044184
0x1800441e3  mov     rcx, [rcx+8]; psa
0x1800441e7  call    cs:__imp_SafeArrayGetDim
0x1800441ed  cmp     eax, 1
0x1800441f0  jnz     loc_18004433D
0x1800441f6  mov     rdx, [rsi+8]
0x1800441fa  mov     r11, [rdx+10h]
0x1800441fe  mov     edx, [rdx+18h]
0x180044201  jmp     short loc_18004420A
0x180044203  mov     r11, [rcx+10h]
0x180044207  mov     edx, [rcx+8]; cbAlloc
0x18004420a  mov     rcx, r11; pidl
0x18004420d  call    IDListContainerIsConsistent
0x180044212  test    eax, eax
0x180044214  jz      loc_18004433D
0x18004421a  test    r11, r11
0x18004421d  jz      short loc_18004423A
0x18004421f  mov     rcx, r11; pidl
0x180044222  call    cs:__imp_ILClone
0x180044228  mov     rcx, rax
0x18004422b  neg     rcx
0x18004422e  sbb     ebx, ebx
0x180044230  not     ebx
0x180044232  and     ebx, 8007000Eh
0x180044238  jmp     short loc_18004423C
0x18004423a  xor     eax, eax
0x18004423c  mov     [rdi], rax
0x18004423f  jmp     loc_18004433D
0x180044244  mov     rcx, [rcx+8]
0x180044248  lea     r8, [rbp+pstm]
0x18004424c  mov     [rbp+pstm], 0
0x180044254  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18004425b  mov     rax, [rcx]
0x18004425e  mov     rax, [rax]
0x180044261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044266  test    eax, eax
0x180044268  js      loc_18004433D
0x18004426e  mov     rcx, [rbp+pstm]; pstm
0x180044272  lea     rdx, [rbp+pui]; pui
0x180044276  mov     qword ptr [rbp+pui], 0
0x18004427e  call    cs:__imp_IStream_Size
0x180044284  mov     ebx, eax
0x180044286  test    eax, eax
0x180044288  js      short loc_1800442F0
0x18004428a  cmp     dword ptr [rbp+pui+4], 0
0x18004428e  mov     ebx, r15d
0x180044291  jnz     short loc_1800442F0
0x180044293  mov     r8d, dword ptr [rbp+pui]; unsigned __int64
0x180044297  lea     r9, [rbp+pv]; void **
0x18004429b  mov     edx, 1; unsigned int
0x1800442a0  mov     [rbp+pv], 0
0x1800442a8  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800442ad  mov     ebx, eax
0x1800442af  test    eax, eax
0x1800442b1  js      short loc_1800442F0
0x1800442b3  mov     rsi, [rbp+pv]
0x1800442b7  mov     r8d, dword ptr [rbp+pui]; cb
0x1800442bb  mov     rdx, rsi; pv
0x1800442be  mov     rcx, [rbp+pstm]; pstm
0x1800442c2  call    cs:__imp_IStream_Read
0x1800442c8  mov     ebx, eax
0x1800442ca  test    eax, eax
0x1800442cc  js      short loc_1800442E7
0x1800442ce  mov     edx, dword ptr [rbp+pui]; cbAlloc
0x1800442d1  mov     rcx, rsi; pidl
0x1800442d4  mov     ebx, r15d
0x1800442d7  call    IDListContainerIsConsistent
0x1800442dc  test    eax, eax
0x1800442de  jz      short loc_1800442E7
0x1800442e0  mov     [rdi], rsi
0x1800442e3  xor     esi, esi
0x1800442e5  xor     ebx, ebx
0x1800442e7  mov     rcx, rsi; pv
0x1800442ea  call    cs:__imp_CoTaskMemFree
0x1800442f0  mov     rcx, [rbp+pstm]
0x1800442f4  mov     rax, [rcx]
0x1800442f7  mov     rax, [rax+10h]
0x1800442fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044300  jmp     short loc_18004433D
0x180044302  mov     rcx, [rcx+8]; pszName
0x180044306  xor     r9d, r9d; sfgaoIn
0x180044309  mov     r8, rdi; ppidl
0x18004430c  mov     [rsp+30h+psfgaoOut], 0; psfgaoOut
0x180044315  xor     edx, edx; pbc
0x180044317  call    cs:__imp_SHParseDisplayName
0x18004431d  jmp     short loc_18004433B
0x18004431f  cmp     qword ptr [rcx+8], 0FFFFh
0x180044327  jnb     short loc_18004433D
0x180044329  mov     edx, [rcx+8]
0x18004432c  mov     r8, rdi; ppidl
0x18004432f  bts     edx, 0Fh; csidl
0x180044333  xor     ecx, ecx; hwnd
0x180044335  call    cs:__imp_SHGetSpecialFolderLocation
0x18004433b  mov     ebx, eax
0x18004433d  mov     eax, ebx
0x18004433f  add     rsp, 30h
0x180044343  pop     r15
0x180044345  pop     rdi
0x180044346  pop     rsi
0x180044347  pop     rbx
0x180044348  pop     rbp
0x180044349  retn
```
