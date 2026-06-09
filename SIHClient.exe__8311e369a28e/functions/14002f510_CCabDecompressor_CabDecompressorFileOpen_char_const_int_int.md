# CCabDecompressor::CabDecompressorFileOpen(char const *,int,int)

- ea: `0x14002f510`
- end: `0x14002f674`
- name: `?CabDecompressorFileOpen@CCabDecompressor@@CA_JPEBDHH@Z`
- size: `356`
- prototype: `INT_PTR __fastcall(const CHAR *pszFile, int oflag, int pmode)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002eff8`

## callees

- `0x14000cdb8`
- `0x14000ce30`
- `0x14000fab0`
- `0x1400154b4`
- `0x14002f510`
- `0x1400304ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f5ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f5ce`

## string_xrefs

- `0x14002f60b`: `CreateFile(%ws)`
- `0x14002f5e3`: `CCabDecompressor::CabDecompressorFileOpen`
- `0x14002f652`: `CCabDecompressor::CabDecompressorFileOpen`

## pseudocode

```c
INT_PTR __fastcall CCabDecompressor::CabDecompressorFileOpen(const CHAR *pszFile, int oflag, int pmode)
{
  char *v4; // rax
  _QWORD *v5; // rbx
  signed int v6; // esi
  struct CCabDecompressor *Node; // rax
  struct _SECURITY_ATTRIBUTES *v8; // r9
  struct CCabDecompressor *v9; // rdi
  int v10; // eax
  void *FileRetryIfSharingViolation; // rax
  signed int LastError; // eax
  __int64 v14; // [rsp+20h] [rbp-48h]
  __int64 v15; // [rsp+20h] [rbp-48h]
  void *v16; // [rsp+30h] [rbp-38h]
  unsigned int v17; // [rsp+38h] [rbp-30h]
  void *v18; // [rsp+40h] [rbp-28h]

  v4 = (char *)SusAlloc(0x20u);
  v5 = v4;
  if ( v4 )
  {
    *(_DWORD *)v4 = 0;
    *(_QWORD *)(v4 + 20) = 0;
    Node = CCabDecompressorList::FindNode(pszFile);
    v9 = Node;
    if ( Node )
    {
      v10 = *((_DWORD *)Node + 34);
      if ( v10 )
      {
        if ( v10 == 1 )
        {
          FileRetryIfSharingViolation = SusCreateFileRetryIfSharingViolation(
                                          *((LPCWSTR *)v9 + 15),
                                          0x80000000,
                                          1u,
                                          v8,
                                          3u,
                                          0x80u,
                                          v16,
                                          v17,
                                          v18,
                                          1,
                                          *((_DWORD *)v9 + 38));
          v5[1] = FileRetryIfSharingViolation;
          if ( FileRetryIfSharingViolation != (void *)-1LL )
          {
            *((_DWORD *)v5 + 4) = 1;
            *((_DWORD *)v5 + 6) = *((_DWORD *)v9 + 39);
            return (INT_PTR)v5;
          }
          LastError = GetLastError();
          v6 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v6 = LastError;
          if ( v6 >= 0 )
            v6 = -2147418113;
          LODWORD(v15) = v6;
          WUTrace("CCabDecompressor::CabDecompressorFileOpen", 733, 32, 3, v15, L"CreateFile(%ws)");
        }
        else
        {
          v6 = -2145120257;
        }
        SusFree(v5);
        goto LABEL_17;
      }
      v5[1] = *((_QWORD *)v9 + 7);
      *((_DWORD *)v5 + 4) = 0;
    }
    return (INT_PTR)v5;
  }
  v6 = -2147024882;
LABEL_17:
  LODWORD(v14) = v6;
  WUTrace("CCabDecompressor::CabDecompressorFileOpen", 756, 32, 3, v14, L"Method failed");
  return -1;
}

```

## disassembly

```asm
0x14002f510  mov     [rsp+arg_0], rbx
0x14002f515  mov     [rsp+arg_8], rsi
0x14002f51a  push    rdi
0x14002f51b  sub     rsp, 60h
0x14002f51f  mov     rdi, rcx
0x14002f522  mov     ecx, 20h ; ' '; unsigned __int64
0x14002f527  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x14002f52c  mov     rbx, rax
0x14002f52f  test    rax, rax
0x14002f532  jnz     short loc_14002F53E
0x14002f534  mov     esi, 8007000Eh
0x14002f539  jmp     loc_14002F640
0x14002f53e  mov     rcx, rdi; lpString1
0x14002f541  mov     dword ptr [rax], 0
0x14002f547  mov     qword ptr [rax+14h], 0
0x14002f54f  call    ?FindNode@CCabDecompressorList@@SAPEAVCCabDecompressor@@PEBD@Z; CCabDecompressorList::FindNode(char const *)
0x14002f554  mov     rdi, rax
0x14002f557  test    rax, rax
0x14002f55a  jz      short loc_14002F575
0x14002f55c  mov     eax, [rax+88h]
0x14002f562  test    eax, eax
0x14002f564  jnz     short loc_14002F588
0x14002f566  mov     rax, [rdi+38h]
0x14002f56a  mov     [rbx+8], rax
0x14002f56e  mov     dword ptr [rbx+10h], 0
0x14002f575  mov     rax, rbx
0x14002f578  mov     rbx, [rsp+68h+arg_0]
0x14002f57d  mov     rsi, [rsp+68h+arg_8]
0x14002f582  add     rsp, 60h
0x14002f586  pop     rdi
0x14002f587  retn
0x14002f588  mov     esi, 1
0x14002f58d  cmp     eax, esi
0x14002f58f  jnz     loc_14002F633
0x14002f595  mov     eax, [rdi+98h]
0x14002f59b  mov     r8d, esi; dwShareMode
0x14002f59e  mov     rcx, [rdi+78h]; lpFileName
0x14002f5a2  mov     edx, 80000000h; dwDesiredAccess
0x14002f5a7  mov     [rsp+68h+var_18], eax; unsigned int
0x14002f5ab  mov     [rsp+68h+var_20], esi; int
0x14002f5af  mov     [rsp+68h+var_40], 80h; DWORD
0x14002f5b7  mov     dword ptr [rsp+68h+var_48], 3; DWORD
0x14002f5bf  call    ?SusCreateFileRetryIfSharingViolation@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXK2HK@Z; SusCreateFileRetryIfSharingViolation(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,ulong,void *,int,ulong)
0x14002f5c4  mov     [rbx+8], rax
0x14002f5c8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002f5cc  jnz     short loc_14002F622
0x14002f5ce  call    cs:__imp_GetLastError
0x14002f5d4  movzx   esi, ax
0x14002f5d7  mov     r9d, 3
0x14002f5dd  or      esi, 80070000h
0x14002f5e3  lea     rcx, aCcabdecompress; "CCabDecompressor::CabDecompressorFileOp"...
0x14002f5ea  test    eax, eax
0x14002f5ec  mov     edx, 2DDh
0x14002f5f1  cmovle  esi, eax
0x14002f5f4  lea     r8d, [r9+1Dh]
0x14002f5f8  test    esi, esi
0x14002f5fa  mov     eax, 8000FFFFh
0x14002f5ff  cmovns  esi, eax
0x14002f602  mov     rax, [rdi+78h]
0x14002f606  mov     [rsp+68h+var_38], rax
0x14002f60b  lea     rax, aCreatefileWs; "CreateFile(%ws)"
0x14002f612  mov     qword ptr [rsp+68h+var_40], rax
0x14002f617  mov     dword ptr [rsp+68h+var_48], esi
0x14002f61b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002f620  jmp     short loc_14002F638
0x14002f622  mov     [rbx+10h], esi
0x14002f625  mov     eax, [rdi+9Ch]
0x14002f62b  mov     [rbx+18h], eax
0x14002f62e  jmp     loc_14002F575
0x14002f633  mov     esi, 80240FFFh
0x14002f638  mov     rcx, rbx; lpMem
0x14002f63b  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14002f640  lea     rdx, aMethodFailed; "Method failed"
0x14002f647  mov     r9d, 3
0x14002f64d  mov     qword ptr [rsp+68h+var_40], rdx
0x14002f652  lea     rcx, aCcabdecompress; "CCabDecompressor::CabDecompressorFileOp"...
0x14002f659  mov     edx, 2F4h
0x14002f65e  mov     dword ptr [rsp+68h+var_48], esi
0x14002f662  lea     r8d, [r9+1Dh]
0x14002f666  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002f66b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002f66f  jmp     loc_14002F578
```
