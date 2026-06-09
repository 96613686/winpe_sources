# SuGetDiskPath(ulong,int,ushort * *)

- ea: `0x14001480c`
- end: `0x1400148bb`
- name: `?SuGetDiskPath@@YAHKHPEAPEAG@Z`
- size: `175`
- prototype: `__int64 __fastcall(int, int, unsigned __int16 **)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x140015890`
- `0x140015e10`
- `0x140016110`
- `0x1400166f8`
- `0x140016bc4`
- `0x140016cb0`
- `0x140016d64`
- `0x140016f48`
- `0x140017044`

## callees

- `0x14001480c`
- `0x14001a900`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140014893`
- `KERNEL32!LocalFree` at `0x140014893`
- `KERNEL32!SetLastError` at `0x1400148a0`
- `KERNEL32!SetLastError` at `0x1400148a0`
- `KERNEL32!GetLastError` at `0x140014842`
- `KERNEL32!GetLastError` at `0x140014867`
- `KERNEL32!GetLastError` at `0x140014884`
- `KERNEL32!GetLastError` at `0x140014842`
- `KERNEL32!GetLastError` at `0x140014867`
- `KERNEL32!GetLastError` at `0x140014884`
- `KERNEL32!LocalAlloc` at `0x140014857`
- `KERNEL32!LocalAlloc` at `0x140014857`

## pseudocode

```c
__int64 __fastcall SuGetDiskPath(int a1, int a2, unsigned __int16 **a3)
{
  unsigned int DiskPath; // edi
  unsigned __int16 *v7; // rbx
  unsigned __int16 *v8; // rax
  DWORD LastError; // esi
  unsigned __int64 v11; // [rsp+58h] [rbp+20h] BYREF

  v11 = 0;
  DiskPath = GetDiskPath(a1, a2, &v11, 0);
  if ( DiskPath || (v7 = 0, GetLastError() == 122) )
  {
    v8 = (unsigned __int16 *)LocalAlloc(0, 2 * v11);
    v7 = v8;
    if ( !v8 )
    {
      DiskPath = 0;
      LastError = GetLastError();
LABEL_7:
      LocalFree(v7);
      v7 = 0;
      goto LABEL_8;
    }
    DiskPath = GetDiskPath(a1, a2, &v11, v8);
  }
  LastError = GetLastError();
  if ( !DiskPath )
    goto LABEL_7;
LABEL_8:
  *a3 = v7;
  SetLastError(LastError);
  return DiskPath;
}

```

## disassembly

```asm
0x14001480c  mov     rax, rsp
0x14001480f  mov     [rax+8], rbx
0x140014813  mov     [rax+10h], rbp
0x140014817  push    rsi
0x140014818  push    rdi
0x140014819  push    r14
0x14001481b  sub     rsp, 20h
0x14001481f  mov     r14, r8
0x140014822  mov     qword ptr [rax+20h], 0
0x14001482a  lea     r8, [rax+20h]; unsigned __int64 *
0x14001482e  xor     r9d, r9d; unsigned __int16 *
0x140014831  mov     esi, edx
0x140014833  mov     ebp, ecx
0x140014835  call    ?GetDiskPath@@YAHKHPEA_KPEAG@Z; GetDiskPath(ulong,int,unsigned __int64 *,ushort *)
0x14001483a  mov     edi, eax
0x14001483c  test    eax, eax
0x14001483e  jnz     short loc_14001484D
0x140014840  xor     ebx, ebx
0x140014842  call    cs:__imp_GetLastError
0x140014848  cmp     eax, 7Ah ; 'z'
0x14001484b  jnz     short loc_140014884
0x14001484d  mov     rdx, [rsp+38h+arg_18]
0x140014852  xor     ecx, ecx; uFlags
0x140014854  add     rdx, rdx; uBytes
0x140014857  call    cs:__imp_LocalAlloc
0x14001485d  mov     rbx, rax
0x140014860  test    rax, rax
0x140014863  jnz     short loc_140014871
0x140014865  xor     edi, edi
0x140014867  call    cs:__imp_GetLastError
0x14001486d  mov     esi, eax
0x14001486f  jmp     short loc_140014890
0x140014871  mov     r9, rax; unsigned __int16 *
0x140014874  lea     r8, [rsp+38h+arg_18]; unsigned __int64 *
0x140014879  mov     edx, esi; int
0x14001487b  mov     ecx, ebp; unsigned int
0x14001487d  call    ?GetDiskPath@@YAHKHPEA_KPEAG@Z; GetDiskPath(ulong,int,unsigned __int64 *,ushort *)
0x140014882  mov     edi, eax
0x140014884  call    cs:__imp_GetLastError
0x14001488a  mov     esi, eax
0x14001488c  test    edi, edi
0x14001488e  jnz     short loc_14001489B
0x140014890  mov     rcx, rbx; hMem
0x140014893  call    cs:__imp_LocalFree
0x140014899  xor     ebx, ebx
0x14001489b  mov     ecx, esi; dwErrCode
0x14001489d  mov     [r14], rbx
0x1400148a0  call    cs:__imp_SetLastError
0x1400148a6  mov     rbx, [rsp+38h+arg_0]
0x1400148ab  mov     eax, edi
0x1400148ad  mov     rbp, [rsp+38h+arg_8]
0x1400148b2  add     rsp, 20h
0x1400148b6  pop     r14
0x1400148b8  pop     rdi
0x1400148b9  pop     rsi
0x1400148ba  retn
```
