# fdi_seek(__int64,long,int)

- ea: `0x18003efc0`
- end: `0x18003f015`
- name: `?fdi_seek@@YAJ_JJH@Z`
- size: `85`
- prototype: `int __cdecl(INT_PTR hf, int dist, int seektype)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18003efc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003efff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003efff`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003eff2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003eff2`

## pseudocode

```c
DWORD __fastcall fdi_seek(INT_PTR hf, LONG dist, int seektype)
{
  int v3; // r8d
  DWORD result; // eax
  DWORD v5; // r9d

  if ( seektype )
  {
    v3 = seektype - 1;
    if ( v3 )
    {
      if ( v3 != 1 )
        return -1;
      v5 = 2;
    }
    else
    {
      v5 = 1;
    }
  }
  else
  {
    v5 = 0;
  }
  result = SetFilePointer((HANDLE)hf, dist, 0, v5);
  if ( result == -1 )
  {
    GetLastError();
    return -1;
  }
  return result;
}

```

## disassembly

```asm
0x18003efc0  push    rbx
0x18003efc2  sub     rsp, 20h
0x18003efc6  test    r8d, r8d
0x18003efc9  jz      short loc_18003EFEC
0x18003efcb  sub     r8d, 1
0x18003efcf  jz      short loc_18003EFE4
0x18003efd1  cmp     r8d, 1
0x18003efd5  jz      short loc_18003EFDC
0x18003efd7  or      eax, 0FFFFFFFFh
0x18003efda  jmp     short loc_18003F00F
0x18003efdc  mov     r9d, 2
0x18003efe2  jmp     short loc_18003EFEF
0x18003efe4  mov     r9d, 1
0x18003efea  jmp     short loc_18003EFEF
0x18003efec  xor     r9d, r9d; dwMoveMethod
0x18003efef  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003eff2  call    cs:__imp_SetFilePointer
0x18003eff8  mov     ebx, eax
0x18003effa  cmp     eax, 0FFFFFFFFh
0x18003effd  jnz     short loc_18003F00F
0x18003efff  call    cs:__imp_GetLastError
0x18003f005  or      ecx, 0FFFFFFFFh
0x18003f008  test    eax, eax
0x18003f00a  cmovnz  ebx, ecx
0x18003f00d  mov     eax, ebx
0x18003f00f  add     rsp, 20h
0x18003f013  pop     rbx
0x18003f014  retn
```
