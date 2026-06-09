# DirectorySize(ushort const *,unsigned __int64 *)

- ea: `0x18001ff7c`
- end: `0x18002002d`
- name: `?DirectorySize@@YAJPEBGPEA_K@Z`
- size: `177`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b978`

## callees

- `0x18001ff7c`
- `0x180020060`
- `0x1800201d8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18001ffb1`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18001ffb1`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18001ffd8`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18001ffd8`

## string_xrefs

- `0x18001ffaa`: `DirectorySize`
- `0x18001ffcf`: `DirectorySize`

## pseudocode

```c
__int64 __fastcall DirectorySize(const unsigned __int16 *a1, unsigned __int64 *a2)
{
  int v4; // r8d
  int v5; // ecx
  unsigned int v7; // ecx
  int v8; // eax
  int v9; // r8d
  bool v11; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int64 v12; // [rsp+40h] [rbp+18h] BYREF

  v12 = 0;
  v11 = 0;
  if ( a1 )
  {
    v8 = FolderExists(a1, &v11);
    if ( v8 >= 0 )
    {
      if ( !v11 )
      {
        v4 = 811;
        v5 = -2147024893;
        return (unsigned int)ZTraceReportOriginationNoThis(v5, "DirectorySize", v4);
      }
      v8 = RecursiveScanDirectory(
             a1,
             0,
             (__int64 (__fastcall *)(__int64, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *))FileSize,
             &v12);
      if ( v8 >= 0 )
      {
        v7 = 0;
        *a2 = v12;
        return v7;
      }
      v9 = 813;
    }
    else
    {
      v9 = 810;
    }
    return (unsigned int)ZTraceReportPropagationNoThis(v8, "DirectorySize", v9);
  }
  v4 = 808;
  v5 = -2147467261;
  return (unsigned int)ZTraceReportOriginationNoThis(v5, "DirectorySize", v4);
}

```

## disassembly

```asm
0x18001ff7c  mov     [rsp+arg_8], rbx
0x18001ff81  push    rdi
0x18001ff82  sub     rsp, 20h
0x18001ff86  mov     [rsp+28h+arg_10], 0
0x18001ff8f  mov     rdi, rdx
0x18001ff92  mov     [rsp+28h+arg_0], 0
0x18001ff97  mov     rbx, rcx
0x18001ff9a  test    rcx, rcx
0x18001ff9d  jnz     short loc_18001FFBB
0x18001ff9f  mov     r8d, 328h
0x18001ffa5  mov     ecx, 80004003h
0x18001ffaa  lea     rdx, aDirectorysize; "DirectorySize"
0x18001ffb1  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18001ffb7  mov     ecx, eax; unsigned __int16 *
0x18001ffb9  jmp     short loc_180020020
0x18001ffbb  lea     rdx, [rsp+28h+arg_0]; bool *
0x18001ffc0  call    ?FolderExists@@YAJPEBGPEA_N@Z; FolderExists(ushort const *,bool *)
0x18001ffc5  test    eax, eax
0x18001ffc7  jns     short loc_18001FFE0
0x18001ffc9  mov     r8d, 32Ah
0x18001ffcf  lea     rdx, aDirectorysize; "DirectorySize"
0x18001ffd6  mov     ecx, eax
0x18001ffd8  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18001ffde  jmp     short loc_18001FFB7
0x18001ffe0  cmp     [rsp+28h+arg_0], 0
0x18001ffe5  jnz     short loc_18001FFF4
0x18001ffe7  mov     r8d, 32Bh
0x18001ffed  mov     ecx, 80070003h
0x18001fff2  jmp     short loc_18001FFAA
0x18001fff4  lea     r9, [rsp+28h+arg_10]; void *
0x18001fff9  xor     edx, edx; int
0x18001fffb  lea     r8, FileSize; int (__high *)(enum DIRECTORY_SCAN_STATE, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *)
0x180020002  mov     rcx, rbx; unsigned __int16 *
0x180020005  call    ?RecursiveScanDirectory@@YAJPEBGHQ6AJW4DIRECTORY_SCAN_STATE@@0PEAU_WIN32_FIND_DATAW@@PEAX@Z3@Z; RecursiveScanDirectory(ushort const *,int,long (*const)(DIRECTORY_SCAN_STATE,ushort const *,_WIN32_FIND_DATAW *,void *),void *)
0x18002000a  test    eax, eax
0x18002000c  jns     short loc_180020016
0x18002000e  mov     r8d, 32Dh
0x180020014  jmp     short loc_18001FFCF
0x180020016  mov     rax, [rsp+28h+arg_10]
0x18002001b  xor     ecx, ecx
0x18002001d  mov     [rdi], rax
0x180020020  mov     rbx, [rsp+28h+arg_8]
0x180020025  mov     eax, ecx
0x180020027  add     rsp, 20h
0x18002002b  pop     rdi
0x18002002c  retn
```
