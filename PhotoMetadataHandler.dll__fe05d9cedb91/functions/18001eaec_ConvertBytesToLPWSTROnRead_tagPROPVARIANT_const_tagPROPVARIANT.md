# ConvertBytesToLPWSTROnRead(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18001eaec`
- end: `0x18001eb6e`
- name: `?ConvertBytesToLPWSTROnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `130`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800081a0`
- `0x180008370`

## callees

- `0x180007d90`
- `0x18001eaec`
- `0x180026498`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001eb1c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001eb1c`

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
0x18001eaec  push    rbx
0x18001eaee  push    rsi
0x18001eaef  push    rdi
0x18001eaf0  push    r14
0x18001eaf2  push    r15
0x18001eaf4  sub     rsp, 20h
0x18001eaf8  mov     eax, 1011h
0x18001eafd  mov     r14, rdx
0x18001eb00  mov     rdi, rcx
0x18001eb03  mov     ebx, 80004005h
0x18001eb08  cmp     [rcx], ax
0x18001eb0b  jnz     short loc_18001EB60
0x18001eb0d  mov     ebx, [rcx+8]
0x18001eb10  test    ebx, ebx
0x18001eb12  jz      short loc_18001EB5B
0x18001eb14  test    bl, 1
0x18001eb17  jnz     short loc_18001EB5B
0x18001eb19  mov     rcx, rdx; pvar
0x18001eb1c  call    cs:__imp_PropVariantClear
0x18001eb22  lea     rcx, [rbx+2]; Size
0x18001eb26  mov     esi, ebx
0x18001eb28  cmp     rcx, rbx
0x18001eb2b  jb      short loc_18001EB54
0x18001eb2d  lea     rdx, [r14+8]; void **
0x18001eb31  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18001eb36  mov     ebx, eax
0x18001eb38  test    eax, eax
0x18001eb3a  js      short loc_18001EB60
0x18001eb3c  mov     rdx, [rdi+10h]; Src
0x18001eb40  mov     r8d, esi; Size
0x18001eb43  mov     rcx, [r14+8]; void *
0x18001eb47  call    memcpy_0
0x18001eb4c  mov     word ptr [r14], 1Fh
0x18001eb52  jmp     short loc_18001EB60
0x18001eb54  mov     ebx, 80070216h
0x18001eb59  jmp     short loc_18001EB60
0x18001eb5b  mov     ebx, 80070057h
0x18001eb60  mov     eax, ebx
0x18001eb62  add     rsp, 20h
0x18001eb66  pop     r15
0x18001eb68  pop     r14
0x18001eb6a  pop     rdi
0x18001eb6b  pop     rsi
0x18001eb6c  pop     rbx
0x18001eb6d  retn
```
