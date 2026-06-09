# ILCloneWithHiddenID(_ITEMIDLIST_RELATIVE const *,_HIDDENITEMID const *,_ITEMIDLIST_RELATIVE * *)

- ea: `0x180022f50`
- end: `0x18002306b`
- name: `?ILCloneWithHiddenID@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEFBU_HIDDENITEMID@@PEAPEAU1@@Z`
- size: `283`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST_RELATIVE *Src, const struct _HIDDENITEMID *, struct _ITEMIDLIST_RELATIVE **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022f10`
- `0x180026640`

## callees

- `0x180009d00`
- `0x18000bae0`
- `0x180022f50`
- `0x18004fb18`
- `0x18004fb24`

## import_xrefs

- `SHELL32!__imp_ILFindLastID` at `0x180022fd6`
- `SHELL32!__imp_ILFindLastID` at `0x180022fd6`
- `SHELL32!__imp_ILGetSize` at `0x180022f99`
- `SHELL32!__imp_ILGetSize` at `0x180022f99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002304a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002304a`

## pseudocode

```c
__int64 __fastcall ILCloneWithHiddenID(
        const ITEMIDLIST *Src,
        const struct _HIDDENITEMID *a2,
        struct _ITEMIDLIST_RELATIVE **a3)
{
  UINT v6; // r14d
  void *v7; // rcx
  int v8; // ebx
  const struct _ITEMIDLIST_RELATIVE *ID; // rsi
  const struct _ITEMIDLIST_RELATIVE *v10; // rax
  unsigned __int16 *v11; // r14
  unsigned __int16 v12; // r15
  unsigned __int16 v13; // ax
  unsigned __int16 v14; // ax

  *a3 = 0;
  if ( Src && Src->mkid.cb && HIWORD(*((_DWORD *)a2 + 1)) == 0xBEEF )
  {
    v6 = ILGetSize(Src);
    v8 = CTCoAllocPolicy::Alloc(v7, 1, v6 + *(unsigned __int16 *)a2 + 2, (void **)a3);
    if ( v8 >= 0 )
    {
      memcpy_0(*a3, Src, v6);
      ID = (const struct _ITEMIDLIST_RELATIVE *)ILFindLastID((LPCITEMIDLIST)*a3);
      if ( ILFindFirstHiddenID(ID) )
        v10 = (const struct _ITEMIDLIST_RELATIVE *)((char *)ID + *(unsigned __int16 *)ID - 2);
      else
        v10 = ID;
      v11 = (unsigned __int16 *)((char *)*a3 + v6 - 2);
      v12 = *(_WORD *)v10;
      memmove_0(v11, a2, *(unsigned __int16 *)a2);
      v13 = *v11 + 2;
      if ( v13 < *v11 || (*v11 = v13, v14 = *(_WORD *)ID + v13, v14 < *(_WORD *)ID) )
      {
        v8 = -2147024362;
        CoTaskMemFree(*a3);
        *a3 = 0;
      }
      else
      {
        *(_WORD *)ID = v14;
        v8 = 0;
        *(unsigned __int16 *)((char *)v11 + *v11 - 2) = v12;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180022f50  push    rbx
0x180022f52  push    rbp
0x180022f53  push    rsi
0x180022f54  push    rdi
0x180022f55  push    r12
0x180022f57  push    r14
0x180022f59  push    r15
0x180022f5b  sub     rsp, 20h
0x180022f5f  xor     r12d, r12d
0x180022f62  mov     rdi, r8
0x180022f65  mov     [r8], r12
0x180022f68  mov     rbp, rdx
0x180022f6b  mov     rsi, rcx
0x180022f6e  test    rcx, rcx
0x180022f71  jz      loc_180023055
0x180022f77  cmp     [rcx], r12w
0x180022f7b  jz      loc_180023055
0x180022f81  mov     eax, [rdx+4]
0x180022f84  mov     ecx, 0BEEFh
0x180022f89  shr     rax, 10h
0x180022f8d  cmp     ax, cx
0x180022f90  jnz     loc_180023055
0x180022f96  mov     rcx, rsi; pidl
0x180022f99  call    cs:__imp_ILGetSize
0x180022f9f  movzx   r8d, word ptr [rbp+0]
0x180022fa4  lea     edx, [r12+1]; unsigned int
0x180022fa9  add     r8d, 2
0x180022fad  mov     r14d, eax
0x180022fb0  add     r8d, eax; unsigned __int64
0x180022fb3  mov     r9, rdi; void **
0x180022fb6  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180022fbb  mov     ebx, eax
0x180022fbd  test    eax, eax
0x180022fbf  js      loc_18002305A
0x180022fc5  mov     rcx, [rdi]; void *
0x180022fc8  mov     r8d, r14d; Size
0x180022fcb  mov     rdx, rsi; Src
0x180022fce  call    memcpy_0
0x180022fd3  mov     rcx, [rdi]; pidl
0x180022fd6  call    cs:__imp_ILFindLastID
0x180022fdc  mov     rcx, rax; struct _ITEMIDLIST_RELATIVE *
0x180022fdf  mov     rsi, rax
0x180022fe2  call    ?ILFindFirstHiddenID@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ILFindFirstHiddenID(_ITEMIDLIST_RELATIVE const *)
0x180022fe7  test    rax, rax
0x180022fea  jz      short loc_180022FF8
0x180022fec  movzx   eax, word ptr [rsi]
0x180022fef  add     rax, 0FFFFFFFFFFFFFFFEh
0x180022ff3  add     rax, rsi
0x180022ff6  jmp     short loc_180022FFB
0x180022ff8  mov     rax, rsi
0x180022ffb  movzx   r8d, word ptr [rbp+0]; Size
0x180023000  add     r14d, 0FFFFFFFEh
0x180023004  add     r14, [rdi]
0x180023007  mov     rdx, rbp; Src
0x18002300a  movzx   r15d, word ptr [rax]
0x18002300e  mov     rcx, r14; void *
0x180023011  call    memmove_0
0x180023016  movzx   eax, word ptr [r14]
0x18002301a  add     ax, 2
0x18002301e  cmp     ax, [r14]
0x180023022  jb      short loc_180023042
0x180023024  mov     [r14], ax
0x180023028  add     ax, [rsi]
0x18002302b  cmp     ax, [rsi]
0x18002302e  jb      short loc_180023042
0x180023030  mov     [rsi], ax
0x180023033  mov     ebx, r12d
0x180023036  movzx   eax, word ptr [r14]
0x18002303a  mov     [rax+r14-2], r15w
0x180023040  jmp     short loc_18002305A
0x180023042  mov     rcx, [rdi]; pv
0x180023045  mov     ebx, 80070216h
0x18002304a  call    cs:__imp_CoTaskMemFree
0x180023050  mov     [rdi], r12
0x180023053  jmp     short loc_18002305A
0x180023055  mov     ebx, 80070057h
0x18002305a  mov     eax, ebx
0x18002305c  add     rsp, 20h
0x180023060  pop     r15
0x180023062  pop     r14
0x180023064  pop     r12
0x180023066  pop     rdi
0x180023067  pop     rsi
0x180023068  pop     rbp
0x180023069  pop     rbx
0x18002306a  retn
```
