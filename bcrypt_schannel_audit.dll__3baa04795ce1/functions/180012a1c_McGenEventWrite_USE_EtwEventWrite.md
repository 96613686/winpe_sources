# McGenEventWrite_USE_EtwEventWrite

- ea: `0x180012a1c`
- end: `0x180012a62`
- name: `McGenEventWrite_USE_EtwEventWrite`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000dca4`

## callees

- `0x180012a1c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180012a5b`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_USE_EtwEventWrite(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned __int16 *v5; // rax
  int v6; // ecx

  v5 = (unsigned __int16 *)qword_180024008;
  if ( qword_180024008 )
  {
    *(_QWORD *)a5 = qword_180024008;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    *(_QWORD *)a5 = 0;
    v6 = 0;
  }
  *(_DWORD *)(a5 + 8) = (_DWORD)v5;
  *(_DWORD *)(a5 + 12) = v6;
  return EtwEventWrite(ETW_LOG_BCRYPT_PROVIDER_Context, ETW_LOG_BCRYPT_OPEN_PROVIDER_FAILED, 6);
}

```

## disassembly

```asm
0x180012a1c  mov     rax, cs:qword_180024008
0x180012a23  mov     r9, [rsp+arg_20]
0x180012a28  test    rax, rax
0x180012a2b  jnz     short loc_180012A34
0x180012a2d  mov     [r9], rax
0x180012a30  xor     ecx, ecx
0x180012a32  jmp     short loc_180012A3F
0x180012a34  mov     [r9], rax
0x180012a37  mov     ecx, 2
0x180012a3c  movzx   eax, word ptr [rax]
0x180012a3f  mov     [r9+8], eax
0x180012a43  lea     rdx, ETW_LOG_BCRYPT_OPEN_PROVIDER_FAILED
0x180012a4a  mov     [r9+0Ch], ecx
0x180012a4e  mov     r8d, 6
0x180012a54  mov     rcx, cs:ETW_LOG_BCRYPT_PROVIDER_Context
0x180012a5b  jmp     cs:__imp_EtwEventWrite
```
