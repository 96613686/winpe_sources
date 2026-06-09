# CStowedExceptionPlugin::AddBlocksForStructure(void *,void *)

- ea: `0x14004ecfc`
- end: `0x14004eebd`
- name: `?AddBlocksForStructure@CStowedExceptionPlugin@@AEAAJPEAX0@Z`
- size: `449`
- prototype: `__int64 __fastcall(CStowedExceptionPlugin *__hidden this, void *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004fc20`

## callees

- `0x140015b40`
- `0x14004ecfc`
- `0x14004eec4`
- `0x14004f5dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004ed5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004ed5e`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004ed54`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004edd7`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004ed54`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004edd7`

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
0x14004ecfc  push    rbp
0x14004ecfe  push    rbx
0x14004ecff  push    rsi
0x14004ed00  push    rdi
0x14004ed01  mov     rbp, rsp
0x14004ed04  sub     rsp, 78h
0x14004ed08  xor     eax, eax
0x14004ed0a  mov     [rbp+NumberOfBytesRead], 0
0x14004ed12  mov     rdi, r8
0x14004ed15  mov     [rbp+var_14], eax
0x14004ed18  mov     rsi, rdx
0x14004ed1b  mov     [rbp+arg_18], eax
0x14004ed1e  xorps   xmm0, xmm0
0x14004ed21  mov     [rbp+Buffer], 0
0x14004ed29  lea     rax, [rbp+NumberOfBytesRead]
0x14004ed2d  mov     [rbp+var_38], 0
0x14004ed34  mov     rbx, rcx
0x14004ed37  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14004ed3c  mov     r9d, 8; nSize
0x14004ed42  lea     r8, [rbp+Buffer]; lpBuffer
0x14004ed46  mov     rdx, rdi; lpBaseAddress
0x14004ed49  mov     rcx, rsi; hProcess
0x14004ed4c  movups  xmmword ptr [rbp+var_34], xmm0
0x14004ed50  movups  xmmword ptr [rbp+var_24], xmm0
0x14004ed54  call    cs:__imp_ReadProcessMemory
0x14004ed5a  test    eax, eax
0x14004ed5c  jnz     short loc_14004ED7F
0x14004ed5e  call    cs:__imp_GetLastError
0x14004ed64  test    eax, eax
0x14004ed66  jle     short loc_14004ED70
0x14004ed68  movzx   eax, ax
0x14004ed6b  or      eax, 80070000h
0x14004ed70  test    eax, eax
0x14004ed72  mov     ecx, 80004005h
0x14004ed77  cmovns  eax, ecx
0x14004ed7a  jmp     loc_14004EEB4
0x14004ed7f  cmp     [rbp+NumberOfBytesRead], 8
0x14004ed84  jnz     loc_14004EEAF
0x14004ed8a  mov     r8, [rbp+Buffer]; unsigned int
0x14004ed8e  cmp     r8d, 8
0x14004ed92  jbe     loc_14004EEA8
0x14004ed98  mov     rdx, rdi; void *
0x14004ed9b  mov     rcx, rbx; this
0x14004ed9e  call    ?AddMemoryBlock@CStowedExceptionPlugin@@AEAAJPEAXKK@Z; CStowedExceptionPlugin::AddMemoryBlock(void *,ulong,ulong)
0x14004eda3  cmp     dword ptr [rbp+Buffer], 28h ; '('
0x14004eda7  jb      loc_14004EEA4
0x14004edad  mov     eax, dword ptr [rbp+Buffer+4]
0x14004edb0  add     eax, 0ACBACFCFh
0x14004edb5  cmp     eax, 1
0x14004edb8  ja      loc_14004EEA4
0x14004edbe  lea     rax, [rbp+NumberOfBytesRead]
0x14004edc2  mov     r9d, 28h ; '('; nSize
0x14004edc8  lea     r8, [rbp+var_38]; lpBuffer
0x14004edcc  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14004edd1  mov     rdx, rdi; lpBaseAddress
0x14004edd4  mov     rcx, rsi; hProcess
0x14004edd7  call    cs:__imp_ReadProcessMemory
0x14004eddd  test    eax, eax
0x14004eddf  jz      loc_14004ED5E
0x14004ede5  cmp     [rbp+NumberOfBytesRead], 28h ; '('
0x14004edea  jnz     loc_14004EEAF
0x14004edf0  cmp     [rbp+var_38], 28h ; '('
0x14004edf4  jb      loc_14004EEA8
0x14004edfa  mov     eax, dword ptr [rbp+var_34]
0x14004edfd  add     eax, 0ACBACFCFh
0x14004ee02  cmp     eax, 1
0x14004ee05  ja      loc_14004EEA8
0x14004ee0b  mov     eax, dword ptr [rbp+var_34+8]
0x14004ee0e  and     eax, 3
0x14004ee11  sub     eax, 1
0x14004ee14  jz      short loc_14004EE65
0x14004ee16  cmp     eax, 1
0x14004ee19  jnz     loc_14004EEA8
0x14004ee1f  mov     r8, [rbp+var_34+0Ch]; void *
0x14004ee23  lea     rcx, [rbp+arg_18]; unsigned int *
0x14004ee27  mov     rdx, rsi; void *
0x14004ee2a  call    ?CalculateRemoteStringLength@CStowedExceptionPlugin@@CAJPEAKPEAX1K@Z; CStowedExceptionPlugin::CalculateRemoteStringLength(ulong *,void *,void *,ulong)
0x14004ee2f  test    eax, eax
0x14004ee31  js      short loc_14004EE56
0x14004ee33  mov     edi, [rbp+arg_18]
0x14004ee36  mov     eax, edi
0x14004ee38  add     rax, rax
0x14004ee3b  cmp     rax, 0FFFFh
0x14004ee41  jbe     short loc_14004EE48
0x14004ee43  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14004ee48  lea     r8d, ds:2[rdi*2]
0x14004ee50  mov     rdx, [rbp+var_34+0Ch]
0x14004ee54  jmp     short loc_14004EE9C
0x14004ee56  cmp     eax, 0D0000106h
0x14004ee5b  jnz     short loc_14004EEA4
0x14004ee5d  mov     r8d, 0FFFFh
0x14004ee63  jmp     short loc_14004EE50
0x14004ee65  mov     eax, dword ptr [rbp+var_24+4]
0x14004ee68  test    eax, eax
0x14004ee6a  jz      short loc_14004EEA4
0x14004ee6c  mov     ecx, dword ptr [rbp+var_24+8]
0x14004ee6f  test    ecx, ecx
0x14004ee71  jz      short loc_14004EEA4
0x14004ee73  mov     rdx, [rbp+var_24+0Ch]; void *
0x14004ee77  test    rdx, rdx
0x14004ee7a  jz      short loc_14004EEA4
0x14004ee7c  mov     r8d, ecx
0x14004ee7f  imul    r8, rax
0x14004ee83  mov     eax, 0FFFFFFFFh
0x14004ee88  cmp     r8, rax
0x14004ee8b  ja      short loc_14004EE96
0x14004ee8d  cmp     r8d, 7FFF8h
0x14004ee94  jb      short loc_14004EE9C
0x14004ee96  mov     r8d, 7FFF8h; unsigned int
0x14004ee9c  mov     rcx, rbx; this
0x14004ee9f  call    ?AddMemoryBlock@CStowedExceptionPlugin@@AEAAJPEAXKK@Z; CStowedExceptionPlugin::AddMemoryBlock(void *,ulong,ulong)
0x14004eea4  xor     eax, eax
0x14004eea6  jmp     short loc_14004EEB4
0x14004eea8  mov     eax, 8007000Dh
0x14004eead  jmp     short loc_14004EEB4
0x14004eeaf  mov     eax, 8007012Bh
0x14004eeb4  add     rsp, 78h
0x14004eeb8  pop     rdi
0x14004eeb9  pop     rsi
0x14004eeba  pop     rbx
0x14004eebb  pop     rbp
0x14004eebc  retn
```
