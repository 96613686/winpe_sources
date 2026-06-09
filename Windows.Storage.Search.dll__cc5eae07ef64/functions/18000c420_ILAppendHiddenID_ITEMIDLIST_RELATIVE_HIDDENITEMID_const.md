# ILAppendHiddenID(_ITEMIDLIST_RELATIVE *,_HIDDENITEMID const *)

- ea: `0x18000c420`
- end: `0x18000c54f`
- name: `?ILAppendHiddenID@@YAPEAU_ITEMIDLIST_RELATIVE@@PEAU1@PEFBU_HIDDENITEMID@@@Z`
- size: `303`
- prototype: `struct _ITEMIDLIST_RELATIVE *__fastcall(struct _ITEMIDLIST_RELATIVE *Src, const struct _HIDDENITEMID *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001a640`
- `0x180043a2c`
- `0x180058af0`

## callees

- `0x18000b650`
- `0x18000b6d0`
- `0x18000c420`
- `0x180072cdc`
- `0x180072ce8`
- `0x180072cf4`

## import_xrefs

- `Windows.Storage!ILFindLastID` at `0x18000c4b9`
- `Windows.Storage!ILFindLastID` at `0x18000c4b9`
- `Windows.Storage!ILFree` at `0x18000c532`
- `Windows.Storage!ILFree` at `0x18000c532`
- `Windows.Storage!ILGetSize` at `0x18000c46f`
- `Windows.Storage!ILGetSize` at `0x18000c46f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c481`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c481`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c526`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c526`

## pseudocode

```c
ITEMIDLIST *__fastcall ILAppendHiddenID(const ITEMIDLIST *Src, const struct _HIDDENITEMID *a2)
{
  ITEMIDLIST *v3; // rbx
  ITEMIDLIST *v5; // rdi
  UINT v6; // r14d
  ITEMIDLIST *v7; // rax
  size_t v8; // rax
  const struct _ITEMIDLIST_RELATIVE *ID; // rdi
  const struct _ITEMIDLIST_RELATIVE *v10; // rax
  unsigned __int16 v11; // r15
  unsigned __int16 *v12; // r14
  unsigned __int16 v13; // ax
  unsigned __int16 v14; // ax

  v3 = (ITEMIDLIST *)Src;
  if ( Src && Src->mkid.cb )
  {
    v5 = (ITEMIDLIST *)Src;
    v3 = 0;
    if ( HIWORD(*((_DWORD *)a2 + 1)) == 0xBEEF )
    {
      v6 = ILGetSize(Src);
      v7 = (ITEMIDLIST *)CoTaskMemAlloc(v6 + *(unsigned __int16 *)a2 + 2);
      v3 = v7;
      if ( v7 )
      {
        v8 = CTCoAllocPolicy::_CoTaskMemSize(v7);
        memset_0(v3, 0, v8);
        memcpy_0(v3, v5, v6);
        ID = (const struct _ITEMIDLIST_RELATIVE *)ILFindLastID(v3);
        if ( ILFindFirstHiddenID(ID) )
          v10 = (const struct _ITEMIDLIST_RELATIVE *)((char *)ID + *(unsigned __int16 *)ID - 2);
        else
          v10 = ID;
        v11 = *(_WORD *)v10;
        v12 = (unsigned __int16 *)((char *)v3 + v6 - 2);
        memmove_0(v12, a2, *(unsigned __int16 *)a2);
        v13 = *v12 + 2;
        if ( v13 < *v12 || (*v12 = v13, v14 = *(_WORD *)ID + v13, v14 < *(_WORD *)ID) )
        {
          v5 = (ITEMIDLIST *)Src;
          CoTaskMemFree(v3);
          v3 = 0;
        }
        else
        {
          *(_WORD *)ID = v14;
          v5 = (ITEMIDLIST *)Src;
          *(unsigned __int16 *)((char *)v12 + *v12 - 2) = v11;
        }
      }
    }
    ILFree(v5);
  }
  return v3;
}

```

## disassembly

```asm
0x18000c420  push    rbx
0x18000c422  push    rbp
0x18000c423  push    rsi
0x18000c424  push    rdi
0x18000c425  push    r12
0x18000c427  push    r14
0x18000c429  push    r15
0x18000c42b  sub     rsp, 20h
0x18000c42f  xor     r12d, r12d
0x18000c432  mov     rbp, rdx
0x18000c435  mov     rbx, rcx
0x18000c438  test    rcx, rcx
0x18000c43b  jz      loc_18000C538
0x18000c441  cmp     [rcx], r12w
0x18000c445  jz      loc_18000C538
0x18000c44b  mov     eax, [rdx+4]
0x18000c44e  mov     rsi, rcx
0x18000c451  mov     r15, rcx
0x18000c454  shr     rax, 10h
0x18000c458  mov     rdi, rcx
0x18000c45b  mov     ebx, r12d
0x18000c45e  mov     ecx, 0BEEFh
0x18000c463  cmp     ax, cx
0x18000c466  jnz     loc_18000C52F
0x18000c46c  mov     rcx, rdi; pidl
0x18000c46f  call    cs:__imp_ILGetSize
0x18000c475  movzx   ecx, word ptr [rbp+0]
0x18000c479  add     ecx, 2
0x18000c47c  mov     r14d, eax
0x18000c47f  add     ecx, eax; cb
0x18000c481  call    cs:__imp_CoTaskMemAlloc
0x18000c487  mov     rbx, rax
0x18000c48a  test    rax, rax
0x18000c48d  jz      loc_18000C52F
0x18000c493  mov     rcx, rax; void *
0x18000c496  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18000c49b  mov     r8, rax; Size
0x18000c49e  xor     edx, edx; Val
0x18000c4a0  mov     rcx, rbx; void *
0x18000c4a3  call    memset_0
0x18000c4a8  mov     r8d, r14d; Size
0x18000c4ab  mov     rdx, rdi; Src
0x18000c4ae  mov     rcx, rbx; void *
0x18000c4b1  call    memcpy_0
0x18000c4b6  mov     rcx, rbx; pidl
0x18000c4b9  call    cs:__imp_ILFindLastID
0x18000c4bf  mov     rcx, rax; struct _ITEMIDLIST_RELATIVE *
0x18000c4c2  mov     rdi, rax
0x18000c4c5  call    ?ILFindFirstHiddenID@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ILFindFirstHiddenID(_ITEMIDLIST_RELATIVE const *)
0x18000c4ca  test    rax, rax
0x18000c4cd  jz      short loc_18000C54A
0x18000c4cf  movzx   eax, word ptr [rdi]
0x18000c4d2  add     rax, 0FFFFFFFFFFFFFFFEh
0x18000c4d6  add     rax, rdi
0x18000c4d9  movzx   r8d, word ptr [rbp+0]; Size
0x18000c4de  add     r14d, 0FFFFFFFEh
0x18000c4e2  movzx   r15d, word ptr [rax]
0x18000c4e6  add     r14, rbx
0x18000c4e9  mov     rcx, r14; void *
0x18000c4ec  mov     rdx, rbp; Src
0x18000c4ef  call    memmove_0
0x18000c4f4  movzx   eax, word ptr [r14]
0x18000c4f8  add     ax, 2
0x18000c4fc  cmp     ax, [r14]
0x18000c500  jb      short loc_18000C520
0x18000c502  mov     [r14], ax
0x18000c506  add     ax, [rdi]
0x18000c509  cmp     ax, [rdi]
0x18000c50c  jb      short loc_18000C520
0x18000c50e  mov     [rdi], ax
0x18000c511  mov     rdi, rsi
0x18000c514  movzx   eax, word ptr [r14]
0x18000c518  mov     [rax+r14-2], r15w
0x18000c51e  jmp     short loc_18000C52F
0x18000c520  mov     rcx, rbx; pv
0x18000c523  mov     rdi, rsi
0x18000c526  call    cs:__imp_CoTaskMemFree
0x18000c52c  mov     rbx, r12
0x18000c52f  mov     rcx, rdi; pidl
0x18000c532  call    cs:__imp_ILFree
0x18000c538  mov     rax, rbx
0x18000c53b  add     rsp, 20h
0x18000c53f  pop     r15
0x18000c541  pop     r14
0x18000c543  pop     r12
0x18000c545  pop     rdi
0x18000c546  pop     rsi
0x18000c547  pop     rbp
0x18000c548  pop     rbx
0x18000c549  retn
0x18000c54a  mov     rax, rdi
0x18000c54d  jmp     short loc_18000C4D9
```
