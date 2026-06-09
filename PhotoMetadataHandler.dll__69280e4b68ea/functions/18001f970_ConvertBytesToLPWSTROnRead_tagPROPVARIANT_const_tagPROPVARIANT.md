# ConvertBytesToLPWSTROnRead(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18001f970`
- end: `0x18001f9f9`
- name: `?ConvertBytesToLPWSTROnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `137`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006ca0`
- `0x180006e90`

## callees

- `0x1800096a0`
- `0x18001f970`
- `0x180027748`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f9a0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f9a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConvertBytesToLPWSTROnRead(const struct tagPROPVARIANT *a1, struct tagPROPVARIANT *a2)
{
  int v4; // ebx
  unsigned __int64 ulVal; // rbx
  unsigned int v6; // esi

  v4 = -2147467259;
  if ( a1->vt == 4113 )
  {
    ulVal = a1->ulVal;
    if ( !(_DWORD)ulVal || (ulVal & 1) != 0 )
    {
      return (unsigned int)-2147024809;
    }
    else
    {
      PropVariantClear(a2);
      v6 = ulVal;
      if ( ulVal + 2 < ulVal )
      {
        return (unsigned int)-2147024362;
      }
      else
      {
        v4 = CoTaskMemAllocWithInit(ulVal + 2, (void **)&a2->puuid);
        if ( v4 >= 0 )
        {
          memcpy_0(a2->puuid, a1->bstrblobVal.pData, v6);
          a2->vt = 31;
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001f970  push    rbx
0x18001f972  push    rsi
0x18001f973  push    rdi
0x18001f974  push    r14
0x18001f976  push    r15
0x18001f978  sub     rsp, 20h
0x18001f97c  mov     eax, 1011h
0x18001f981  mov     r14, rdx
0x18001f984  mov     rdi, rcx
0x18001f987  mov     ebx, 80004005h
0x18001f98c  cmp     [rcx], ax
0x18001f98f  jnz     short loc_18001F9EA
0x18001f991  mov     ebx, [rcx+8]
0x18001f994  test    ebx, ebx
0x18001f996  jz      short loc_18001F9E5
0x18001f998  test    bl, 1
0x18001f99b  jnz     short loc_18001F9E5
0x18001f99d  mov     rcx, rdx; pvar
0x18001f9a0  call    cs:__imp_PropVariantClear
0x18001f9a7  nop     dword ptr [rax+rax+00h]
0x18001f9ac  lea     rcx, [rbx+2]; Size
0x18001f9b0  mov     esi, ebx
0x18001f9b2  cmp     rcx, rbx
0x18001f9b5  jb      short loc_18001F9DE
0x18001f9b7  lea     rdx, [r14+8]; void **
0x18001f9bb  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18001f9c0  mov     ebx, eax
0x18001f9c2  test    eax, eax
0x18001f9c4  js      short loc_18001F9EA
0x18001f9c6  mov     rdx, [rdi+10h]; Src
0x18001f9ca  mov     r8d, esi; Size
0x18001f9cd  mov     rcx, [r14+8]; void *
0x18001f9d1  call    memcpy_0
0x18001f9d6  mov     word ptr [r14], 1Fh
0x18001f9dc  jmp     short loc_18001F9EA
0x18001f9de  mov     ebx, 80070216h
0x18001f9e3  jmp     short loc_18001F9EA
0x18001f9e5  mov     ebx, 80070057h
0x18001f9ea  mov     eax, ebx
0x18001f9ec  add     rsp, 20h
0x18001f9f0  pop     r15
0x18001f9f2  pop     r14
0x18001f9f4  pop     rdi
0x18001f9f5  pop     rsi
0x18001f9f6  pop     rbx
0x18001f9f7  retn
```
