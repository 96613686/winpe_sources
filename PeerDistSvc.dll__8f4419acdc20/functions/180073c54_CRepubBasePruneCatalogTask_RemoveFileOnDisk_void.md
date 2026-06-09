# CRepubBasePruneCatalogTask::RemoveFileOnDisk(void)

- ea: `0x180073c54`
- end: `0x180073dd4`
- name: `?RemoveFileOnDisk@CRepubBasePruneCatalogTask@@IEAAKXZ`
- size: `384`
- prototype: `unsigned int __fastcall(CRepubBasePruneCatalogTask *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x18006ea90`
- `0x18006eb90`

## callees

- `0x1800024f0`
- `0x180008310`
- `0x18006116c`
- `0x180073c54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073d2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073d2e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180073d20`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180073d20`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRepubBasePruneCatalogTask::RemoveFileOnDisk(CRepubBasePruneCatalogTask *this)
{
  WCHAR *v2; // rbx
  __int64 v3; // rax
  unsigned int LastError; // edi
  CHostedCacheMsgEncoding *v5; // rcx
  __int64 v6; // rdx
  LPCWSTR lpFileName; // [rsp+60h] [rbp+8h] BYREF
  __int64 v9; // [rsp+68h] [rbp+10h]
  unsigned __int64 v10; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  v9 = 0;
  lpFileName = 0;
  v3 = *((unsigned int *)this + 155);
  LastError = ConstructRepubFilePath(
                *((_QWORD *)this + 75),
                *(_DWORD *)(240 * v3 + *((_QWORD *)this + 54) + 224),
                *(_DWORD *)(240 * v3 + *((_QWORD *)this + 54) + 228),
                (const unsigned __int16 *)(768 * v3 + *((_QWORD *)this + 52) + 20LL),
                0,
                *(_QWORD *)(768 * v3 + *((_QWORD *)this + 52) + 624),
                (unsigned __int16 **)&lpFileName,
                &v10);
  if ( LastError )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v6 = 375;
LABEL_18:
      WPP_SF_qD(
        *((_QWORD *)v5 + 12),
        v6,
        WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids,
        *((_QWORD *)this + 75),
        LastError);
    }
  }
  else
  {
    operator delete(0);
    v2 = (WCHAR *)lpFileName;
    if ( !DeleteFileW(lpFileName) )
    {
      LastError = GetLastError();
      if ( LastError == 2 )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
        {
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            376,
            WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids,
            *((_QWORD *)this + 75),
            2);
        }
        LastError = 0;
      }
      else if ( LastError )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v6 = 377;
          goto LABEL_18;
        }
      }
    }
  }
  operator delete(v2);
  return LastError;
}

```

## disassembly

```asm
0x180073c54  push    rbx
0x180073c56  push    rsi
0x180073c57  push    rdi
0x180073c58  sub     rsp, 40h
0x180073c5c  mov     rsi, rcx
0x180073c5f  xor     ebx, ebx
0x180073c61  mov     [rsp+58h+arg_8], rbx
0x180073c66  mov     [rsp+58h+lpFileName], rbx
0x180073c6b  mov     eax, [rcx+26Ch]
0x180073c71  lea     r8, [rax+rax*2]
0x180073c75  shl     r8, 8
0x180073c79  mov     rdx, [rcx+1A0h]
0x180073c80  imul    r11, rax, 0F0h
0x180073c87  mov     r10, [rcx+1B0h]
0x180073c8e  lea     r9, [rdx+14h]
0x180073c92  add     r9, r8; unsigned __int16 *
0x180073c95  lea     rax, [rsp+58h+arg_10]
0x180073c9a  mov     [rsp+58h+var_20], rax; unsigned __int64 *
0x180073c9f  lea     rax, [rsp+58h+lpFileName]
0x180073ca4  mov     [rsp+58h+var_28], rax; unsigned __int16 **
0x180073ca9  mov     rax, [r8+rdx+270h]
0x180073cb1  mov     [rsp+58h+var_30], rax; unsigned __int64
0x180073cb6  mov     [rsp+58h+var_38], bl; bool
0x180073cba  mov     r8d, [r11+r10+0E4h]; unsigned int
0x180073cc2  mov     edx, [r11+r10+0E0h]; unsigned int
0x180073cca  mov     rcx, [rcx+258h]; unsigned __int64
0x180073cd1  call    ?ConstructRepubFilePath@@YAK_KKKPEBG_N0PEAPEAGPEA_K@Z; ConstructRepubFilePath(unsigned __int64,ulong,ulong,ushort const *,bool,unsigned __int64,ushort * *,unsigned __int64 *)
0x180073cd6  mov     edi, eax
0x180073cd8  test    eax, eax
0x180073cda  jz      short loc_180073D11
0x180073cdc  lea     rax, WPP_GLOBAL_Control
0x180073ce3  mov     rcx, cs:WPP_GLOBAL_Control
0x180073cea  cmp     rcx, rax
0x180073ced  jz      loc_180073DC2
0x180073cf3  test    byte ptr [rcx+6Ch], 4
0x180073cf7  jz      loc_180073DC2
0x180073cfd  cmp     byte ptr [rcx+69h], 1
0x180073d01  jb      loc_180073DC2
0x180073d07  mov     edx, 177h
0x180073d0c  jmp     loc_180073DA6
0x180073d11  xor     ecx, ecx; Block
0x180073d13  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180073d18  mov     rbx, [rsp+58h+lpFileName]
0x180073d1d  mov     rcx, rbx; lpFileName
0x180073d20  call    cs:__imp_DeleteFileW
0x180073d26  test    eax, eax
0x180073d28  jnz     loc_180073DC2
0x180073d2e  call    cs:__imp_GetLastError
0x180073d34  mov     edi, eax
0x180073d36  cmp     eax, 2
0x180073d39  jnz     short loc_180073D7E
0x180073d3b  lea     rax, WPP_GLOBAL_Control
0x180073d42  mov     rcx, cs:WPP_GLOBAL_Control
0x180073d49  cmp     rcx, rax
0x180073d4c  jz      short loc_180073D7A
0x180073d4e  test    byte ptr [rcx+6Ch], 4
0x180073d52  jz      short loc_180073D7A
0x180073d54  cmp     byte ptr [rcx+69h], 4
0x180073d58  jb      short loc_180073D7A
0x180073d5a  mov     edx, 178h
0x180073d5f  mov     dword ptr [rsp+58h+var_38], edi
0x180073d63  mov     r9, [rsi+258h]
0x180073d6a  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180073d71  mov     rcx, [rcx+60h]
0x180073d75  call    WPP_SF_qD
0x180073d7a  xor     edi, edi
0x180073d7c  jmp     short loc_180073DC2
0x180073d7e  test    edi, edi
0x180073d80  jz      short loc_180073DC2
0x180073d82  lea     rax, WPP_GLOBAL_Control
0x180073d89  mov     rcx, cs:WPP_GLOBAL_Control
0x180073d90  cmp     rcx, rax
0x180073d93  jz      short loc_180073DC2
0x180073d95  test    byte ptr [rcx+6Ch], 4
0x180073d99  jz      short loc_180073DC2
0x180073d9b  cmp     byte ptr [rcx+69h], 1
0x180073d9f  jb      short loc_180073DC2
0x180073da1  mov     edx, 179h
0x180073da6  mov     dword ptr [rsp+58h+var_38], edi
0x180073daa  mov     r9, [rsi+258h]
0x180073db1  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180073db8  mov     rcx, [rcx+60h]
0x180073dbc  call    WPP_SF_qD
0x180073dc1  nop
0x180073dc2  mov     rcx, rbx; Block
0x180073dc5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180073dca  mov     eax, edi
0x180073dcc  add     rsp, 40h
0x180073dd0  pop     rdi
0x180073dd1  pop     rsi
0x180073dd2  pop     rbx
0x180073dd3  retn
```
