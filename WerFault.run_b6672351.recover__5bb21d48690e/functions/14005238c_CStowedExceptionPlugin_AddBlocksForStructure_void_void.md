# CStowedExceptionPlugin::AddBlocksForStructure(void *,void *)

- ea: `0x14005238c`
- end: `0x140052560`
- name: `?AddBlocksForStructure@CStowedExceptionPlugin@@AEAAJPEAX0@Z`
- size: `468`
- prototype: `__int64 __fastcall(CStowedExceptionPlugin *__hidden this, void *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400533b0`

## callees

- `0x1400166ec`
- `0x14005238c`
- `0x140052568`
- `0x140052cdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400523f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400523f4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400523e4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140052473`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400523e4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140052473`

## pseudocode

```c
signed int __fastcall CStowedExceptionPlugin::AddBlocksForStructure(CStowedExceptionPlugin *this, void *a2, void *a3)
{
  unsigned int v6; // r9d
  signed int result; // eax
  __int64 v8; // r9
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  unsigned int v13; // edi
  unsigned __int64 v14; // r8
  void *v15; // rdx
  __int64 Buffer; // [rsp+30h] [rbp-48h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+38h] [rbp-40h] BYREF
  void *v18[7]; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v19; // [rsp+B8h] [rbp+40h] BYREF

  NumberOfBytesRead = 0;
  v19 = 0;
  Buffer = 0;
  memset(v18, 0, 40);
  if ( !ReadProcessMemory(a2, a3, &Buffer, 8u, &NumberOfBytesRead) )
    goto LABEL_2;
  if ( NumberOfBytesRead != 8 )
    return -2147024597;
  if ( (unsigned int)Buffer <= 8 )
    return -2147024883;
  CStowedExceptionPlugin::AddMemoryBlock(this, a3, Buffer, v6);
  if ( (unsigned int)Buffer < 0x28 || (unsigned int)(HIDWORD(Buffer) - 1397043249) > 1 )
    return 0;
  if ( ReadProcessMemory(a2, a3, v18, 0x28u, &NumberOfBytesRead) )
  {
    if ( NumberOfBytesRead == 40 )
    {
      if ( LODWORD(v18[0]) >= 0x28 && (unsigned int)(HIDWORD(v18[0]) - 1397043249) <= 1 )
      {
        if ( (BYTE4(v18[1]) & 3) == 1 )
        {
          if ( !LODWORD(v18[3]) )
            return 0;
          if ( !HIDWORD(v18[3]) )
            return 0;
          v15 = v18[4];
          if ( !v18[4] )
            return 0;
          v14 = LODWORD(v18[3]) * (unsigned __int64)HIDWORD(v18[3]);
          if ( v14 > 0xFFFFFFFF || (unsigned int)v14 >= 0x7FFF8 )
            LODWORD(v14) = 524280;
          goto LABEL_30;
        }
        if ( (BYTE4(v18[1]) & 3) == 2 )
        {
          v9 = CStowedExceptionPlugin::CalculateRemoteStringLength(&v19, a2, v18[2], v8);
          if ( v9 < 0 )
          {
            if ( v9 != -805306106 )
              return 0;
            LODWORD(v14) = 0xFFFF;
          }
          else
          {
            v13 = v19;
            if ( 2 * (unsigned __int64)v19 > 0xFFFF )
              MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12, v8);
            LODWORD(v14) = 2 * v13 + 2;
          }
          v15 = v18[2];
LABEL_30:
          CStowedExceptionPlugin::AddMemoryBlock(this, v15, v14, v8);
          return 0;
        }
      }
      return -2147024883;
    }
    return -2147024597;
  }
LABEL_2:
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x14005238c  push    rbp
0x14005238e  push    rbx
0x14005238f  push    rsi
0x140052390  push    rdi
0x140052391  mov     rbp, rsp
0x140052394  sub     rsp, 78h
0x140052398  xor     eax, eax
0x14005239a  mov     [rbp+NumberOfBytesRead], 0
0x1400523a2  mov     rdi, r8
0x1400523a5  mov     [rbp+var_14], eax
0x1400523a8  mov     rsi, rdx
0x1400523ab  mov     [rbp+arg_18], eax
0x1400523ae  xorps   xmm0, xmm0
0x1400523b1  mov     [rbp+Buffer], 0
0x1400523b9  lea     rax, [rbp+NumberOfBytesRead]
0x1400523bd  mov     [rbp+var_38], 0
0x1400523c4  mov     rbx, rcx
0x1400523c7  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x1400523cc  mov     r9d, 8; nSize
0x1400523d2  lea     r8, [rbp+Buffer]; lpBuffer
0x1400523d6  mov     rdx, rdi; lpBaseAddress
0x1400523d9  mov     rcx, rsi; hProcess
0x1400523dc  movups  xmmword ptr [rbp+var_34], xmm0
0x1400523e0  movups  xmmword ptr [rbp+var_24], xmm0
0x1400523e4  call    cs:__imp_ReadProcessMemory
0x1400523eb  nop     dword ptr [rax+rax+00h]
0x1400523f0  test    eax, eax
0x1400523f2  jnz     short loc_14005241B
0x1400523f4  call    cs:__imp_GetLastError
0x1400523fb  nop     dword ptr [rax+rax+00h]
0x140052400  test    eax, eax
0x140052402  jle     short loc_14005240C
0x140052404  movzx   eax, ax
0x140052407  or      eax, 80070000h
0x14005240c  test    eax, eax
0x14005240e  mov     ecx, 80004005h
0x140052413  cmovns  eax, ecx
0x140052416  jmp     loc_140052556
0x14005241b  cmp     [rbp+NumberOfBytesRead], 8
0x140052420  jnz     loc_140052551
0x140052426  mov     r8, [rbp+Buffer]; unsigned int
0x14005242a  cmp     r8d, 8
0x14005242e  jbe     loc_14005254A
0x140052434  mov     rdx, rdi; void *
0x140052437  mov     rcx, rbx; this
0x14005243a  call    ?AddMemoryBlock@CStowedExceptionPlugin@@AEAAJPEAXKK@Z; CStowedExceptionPlugin::AddMemoryBlock(void *,ulong,ulong)
0x14005243f  cmp     dword ptr [rbp+Buffer], 28h ; '('
0x140052443  jb      loc_140052546
0x140052449  mov     eax, dword ptr [rbp+Buffer+4]
0x14005244c  add     eax, 0ACBACFCFh
0x140052451  cmp     eax, 1
0x140052454  ja      loc_140052546
0x14005245a  lea     rax, [rbp+NumberOfBytesRead]
0x14005245e  mov     r9d, 28h ; '('; nSize
0x140052464  lea     r8, [rbp+var_38]; lpBuffer
0x140052468  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14005246d  mov     rdx, rdi; lpBaseAddress
0x140052470  mov     rcx, rsi; hProcess
0x140052473  call    cs:__imp_ReadProcessMemory
0x14005247a  nop     dword ptr [rax+rax+00h]
0x14005247f  test    eax, eax
0x140052481  jz      loc_1400523F4
0x140052487  cmp     [rbp+NumberOfBytesRead], 28h ; '('
0x14005248c  jnz     loc_140052551
0x140052492  cmp     [rbp+var_38], 28h ; '('
0x140052496  jb      loc_14005254A
0x14005249c  mov     eax, dword ptr [rbp+var_34]
0x14005249f  add     eax, 0ACBACFCFh
0x1400524a4  cmp     eax, 1
0x1400524a7  ja      loc_14005254A
0x1400524ad  mov     eax, dword ptr [rbp+var_34+8]
0x1400524b0  and     eax, 3
0x1400524b3  sub     eax, 1
0x1400524b6  jz      short loc_140052507
0x1400524b8  cmp     eax, 1
0x1400524bb  jnz     loc_14005254A
0x1400524c1  mov     r8, [rbp+var_34+0Ch]; void *
0x1400524c5  lea     rcx, [rbp+arg_18]; unsigned int *
0x1400524c9  mov     rdx, rsi; void *
0x1400524cc  call    ?CalculateRemoteStringLength@CStowedExceptionPlugin@@CAJPEAKPEAX1K@Z; CStowedExceptionPlugin::CalculateRemoteStringLength(ulong *,void *,void *,ulong)
0x1400524d1  test    eax, eax
0x1400524d3  js      short loc_1400524F8
0x1400524d5  mov     edi, [rbp+arg_18]
0x1400524d8  mov     eax, edi
0x1400524da  add     rax, rax
0x1400524dd  cmp     rax, 0FFFFh
0x1400524e3  jbe     short loc_1400524EA
0x1400524e5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400524ea  lea     r8d, ds:2[rdi*2]
0x1400524f2  mov     rdx, [rbp+var_34+0Ch]
0x1400524f6  jmp     short loc_14005253E
0x1400524f8  cmp     eax, 0D0000106h
0x1400524fd  jnz     short loc_140052546
0x1400524ff  mov     r8d, 0FFFFh
0x140052505  jmp     short loc_1400524F2
0x140052507  mov     eax, dword ptr [rbp+var_24+4]
0x14005250a  test    eax, eax
0x14005250c  jz      short loc_140052546
0x14005250e  mov     ecx, dword ptr [rbp+var_24+8]
0x140052511  test    ecx, ecx
0x140052513  jz      short loc_140052546
0x140052515  mov     rdx, [rbp+var_24+0Ch]; void *
0x140052519  test    rdx, rdx
0x14005251c  jz      short loc_140052546
0x14005251e  mov     r8d, ecx
0x140052521  imul    r8, rax
0x140052525  mov     eax, 0FFFFFFFFh
0x14005252a  cmp     r8, rax
0x14005252d  ja      short loc_140052538
0x14005252f  cmp     r8d, 7FFF8h
0x140052536  jb      short loc_14005253E
0x140052538  mov     r8d, 7FFF8h; unsigned int
0x14005253e  mov     rcx, rbx; this
0x140052541  call    ?AddMemoryBlock@CStowedExceptionPlugin@@AEAAJPEAXKK@Z; CStowedExceptionPlugin::AddMemoryBlock(void *,ulong,ulong)
0x140052546  xor     eax, eax
0x140052548  jmp     short loc_140052556
0x14005254a  mov     eax, 8007000Dh
0x14005254f  jmp     short loc_140052556
0x140052551  mov     eax, 8007012Bh
0x140052556  add     rsp, 78h
0x14005255a  pop     rdi
0x14005255b  pop     rsi
0x14005255c  pop     rbx
0x14005255d  pop     rbp
0x14005255e  retn
```
