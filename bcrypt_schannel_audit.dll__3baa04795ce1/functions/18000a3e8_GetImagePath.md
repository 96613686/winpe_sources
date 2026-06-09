# _GetImagePath

- ea: `0x18000a3e8`
- end: `0x18000a4cc`
- name: `_GetImagePath`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a070`
- `0x18001a3cc`

## callees

- `0x180004200`
- `0x180005060`
- `0x180009430`
- `0x18000a3e8`
- `0x18001b79d`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000a404`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000a434`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000a404`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000a434`

## string_xrefs

- `0x18000a4a8`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall GetImagePath(const void **a1, WCHAR **a2)
{
  UINT SystemDirectoryW; // eax
  UINT v5; // ebx
  WCHAR *v6; // rax
  WCHAR *v7; // rsi
  UINT v8; // eax
  __int64 v9; // rbx
  unsigned int v10; // edi
  __int64 v11; // rdx

  *a2 = 0;
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v5 = SystemDirectoryW;
  if ( SystemDirectoryW )
  {
    v6 = (WCHAR *)SafeAllocaAllocateFromHeap(*(unsigned __int16 *)a1 + 4LL + 2LL * SystemDirectoryW);
    v7 = v6;
    if ( !v6 )
    {
      v10 = -1073741801;
      goto LABEL_9;
    }
    v8 = GetSystemDirectoryW(v6, v5);
    if ( v8 )
    {
      v9 = v8;
      v10 = 0;
      v7[v8] = 92;
      memcpy_0(&v7[v8 + 1], a1[1], *(unsigned __int16 *)a1);
      v11 = v9 + ((unsigned __int64)*(unsigned __int16 *)a1 >> 1);
      *a2 = v7;
      v7[v11 + 1] = 0;
      return v10;
    }
  }
  else
  {
    v7 = 0;
  }
  v10 = -1073741766;
LABEL_9:
  DebugTraceError(v10, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c");
  if ( v7 )
    MSCryptFree(v7);
  return v10;
}

```

## disassembly

```asm
0x18000a3e8  push    rbx
0x18000a3ea  push    rbp
0x18000a3eb  push    rsi
0x18000a3ec  push    rdi
0x18000a3ed  push    r14
0x18000a3ef  sub     rsp, 20h
0x18000a3f3  mov     r14, rdx
0x18000a3f6  mov     qword ptr [rdx], 0
0x18000a3fd  mov     rbp, rcx
0x18000a400  xor     edx, edx; uSize
0x18000a402  xor     ecx, ecx; lpBuffer
0x18000a404  call    cs:__imp_GetSystemDirectoryW
0x18000a40b  nop     dword ptr [rax+rax+00h]
0x18000a410  mov     ebx, eax
0x18000a412  test    eax, eax
0x18000a414  jz      short loc_18000A486
0x18000a416  movzx   eax, word ptr [rbp+0]
0x18000a41a  add     rax, 4
0x18000a41e  lea     rcx, [rax+rbx*2]
0x18000a422  call    SafeAllocaAllocateFromHeap
0x18000a427  mov     rsi, rax
0x18000a42a  test    rax, rax
0x18000a42d  jz      short loc_18000A490
0x18000a42f  mov     edx, ebx; uSize
0x18000a431  mov     rcx, rax; lpBuffer
0x18000a434  call    cs:__imp_GetSystemDirectoryW
0x18000a43b  nop     dword ptr [rax+rax+00h]
0x18000a440  test    eax, eax
0x18000a442  jz      short loc_18000A49D
0x18000a444  mov     ebx, eax
0x18000a446  xor     edi, edi
0x18000a448  mov     word ptr [rsi+rbx*2], 5Ch ; '\'
0x18000a44e  lea     rcx, [rbx+1]
0x18000a452  movzx   r8d, word ptr [rbp+0]; Size
0x18000a457  lea     rcx, [rsi+rcx*2]; void *
0x18000a45b  mov     rdx, [rbp+8]; Src
0x18000a45f  call    memcpy_0
0x18000a464  movzx   edx, word ptr [rbp+0]
0x18000a468  shr     rdx, 1
0x18000a46b  add     rdx, rbx
0x18000a46e  mov     [r14], rsi
0x18000a471  xor     ecx, ecx
0x18000a473  mov     [rsi+rdx*2+2], cx
0x18000a478  mov     eax, edi
0x18000a47a  add     rsp, 20h
0x18000a47e  pop     r14
0x18000a480  pop     rdi
0x18000a481  pop     rsi
0x18000a482  pop     rbp
0x18000a483  pop     rbx
0x18000a484  retn
0x18000a486  xor     esi, esi
0x18000a488  mov     r9d, 419h
0x18000a48e  jmp     short loc_18000A4A3
0x18000a490  mov     edi, 0C0000017h
0x18000a495  mov     r9d, 422h
0x18000a49b  jmp     short loc_18000A4A8
0x18000a49d  mov     r9d, 42Bh
0x18000a4a3  mov     edi, 0C000003Ah
0x18000a4a8  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a4af  mov     ecx, edi
0x18000a4b1  lea     rdx, aSresult; "sResult"
0x18000a4b8  call    DebugTraceError
0x18000a4bd  test    rsi, rsi
0x18000a4c0  jz      short loc_18000A478
0x18000a4c2  mov     rcx, rsi
0x18000a4c5  call    MSCryptFree
0x18000a4ca  jmp     short loc_18000A478
```
