# CCabDecompressor::CabDecompressorFileSeek(__int64,long,int)

- ea: `0x14002f950`
- end: `0x14002f9fe`
- name: `?CabDecompressorFileSeek@CCabDecompressor@@CAJ_JJH@Z`
- size: `174`
- prototype: `__int64 __fastcall(INT_PTR hf, unsigned int dist, int seektype)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400154b4`
- `0x14002f950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f9b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f9b7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x14002f9aa`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x14002f9aa`

## string_xrefs

- `0x14002f9d7`: `CabDecompressorFileSeek - SetFilePointer`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::CabDecompressorFileSeek(INT_PTR hf, unsigned int dist, int seektype)
{
  int v3; // r8d
  DWORD v4; // r9d
  DWORD v5; // r9d
  DWORD v7; // ebx
  signed int LastError; // eax
  signed int v9; // ecx
  __int64 v10; // [rsp+20h] [rbp-18h]

  if ( seektype )
  {
    v3 = seektype - 1;
    if ( !v3 )
    {
      v4 = 1;
      goto LABEL_7;
    }
    if ( v3 == 1 )
    {
      v4 = 2;
      goto LABEL_7;
    }
  }
  v4 = 0;
LABEL_7:
  if ( !*(_DWORD *)(hf + 16) )
  {
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( !v5 )
      {
        *(_DWORD *)(hf + 20) += dist;
        return *(unsigned int *)(hf + 20);
      }
      if ( v5 == 1 )
      {
        *(_DWORD *)(hf + 20) -= dist;
        return *(unsigned int *)(hf + 20);
      }
    }
    *(_DWORD *)(hf + 20) = dist;
    return dist;
  }
  v7 = SetFilePointer(*(HANDLE *)(hf + 8), dist, 0, v4);
  if ( v7 == -1 )
  {
    LastError = GetLastError();
    v9 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v9 = LastError;
    if ( v9 >= 0 )
      v9 = -2147418113;
    LODWORD(v10) = v9;
    WUTrace(0, 0, 32, 3, v10, L"CabDecompressorFileSeek - SetFilePointer");
  }
  return v7;
}

```

## disassembly

```asm
0x14002f950  push    rbx
0x14002f952  sub     rsp, 30h
0x14002f956  test    r8d, r8d
0x14002f959  jz      short loc_14002F975
0x14002f95b  sub     r8d, 1
0x14002f95f  jz      short loc_14002F96D
0x14002f961  cmp     r8d, 1
0x14002f965  jnz     short loc_14002F975
0x14002f967  lea     r9d, [r8+1]
0x14002f96b  jmp     short loc_14002F978
0x14002f96d  mov     r9d, 1
0x14002f973  jmp     short loc_14002F978
0x14002f975  xor     r9d, r9d; dwMoveMethod
0x14002f978  cmp     dword ptr [rcx+10h], 0
0x14002f97c  jnz     short loc_14002F9A3
0x14002f97e  test    r9d, r9d
0x14002f981  jz      short loc_14002F99C
0x14002f983  sub     r9d, 1
0x14002f987  jz      short loc_14002F994
0x14002f989  cmp     r9d, 1
0x14002f98d  jnz     short loc_14002F99C
0x14002f98f  sub     [rcx+14h], edx
0x14002f992  jmp     short loc_14002F997
0x14002f994  add     [rcx+14h], edx
0x14002f997  mov     edx, [rcx+14h]; lDistanceToMove
0x14002f99a  jmp     short loc_14002F99F
0x14002f99c  mov     [rcx+14h], edx
0x14002f99f  mov     eax, edx
0x14002f9a1  jmp     short loc_14002F9F8
0x14002f9a3  mov     rcx, [rcx+8]; hFile
0x14002f9a7  xor     r8d, r8d; lpDistanceToMoveHigh
0x14002f9aa  call    cs:__imp_SetFilePointer
0x14002f9b0  mov     ebx, eax
0x14002f9b2  cmp     eax, 0FFFFFFFFh
0x14002f9b5  jnz     short loc_14002F9F6
0x14002f9b7  call    cs:__imp_GetLastError
0x14002f9bd  movzx   ecx, ax
0x14002f9c0  or      ecx, 80070000h
0x14002f9c6  test    eax, eax
0x14002f9c8  cmovle  ecx, eax
0x14002f9cb  mov     eax, 8000FFFFh
0x14002f9d0  test    ecx, ecx
0x14002f9d2  cmovns  ecx, eax
0x14002f9d5  xor     edx, edx
0x14002f9d7  lea     rax, aCabdecompresso_4; "CabDecompressorFileSeek - SetFilePointe"...
0x14002f9de  mov     [rsp+38h+var_10], rax
0x14002f9e3  mov     dword ptr [rsp+38h+var_18], ecx
0x14002f9e7  xor     ecx, ecx
0x14002f9e9  lea     r9d, [rdx+3]
0x14002f9ed  lea     r8d, [rdx+20h]
0x14002f9f1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002f9f6  mov     eax, ebx
0x14002f9f8  add     rsp, 30h
0x14002f9fc  pop     rbx
0x14002f9fd  retn
```
