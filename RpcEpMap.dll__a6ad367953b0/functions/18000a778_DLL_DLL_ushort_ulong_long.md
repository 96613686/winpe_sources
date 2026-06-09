# DLL::DLL(ushort *,ulong,long *)

- ea: `0x18000a778`
- end: `0x18000a83a`
- name: `??0DLL@@QEAA@PEAGKPEAJ@Z`
- size: `194`
- prototype: `DLL *(DLL *__hidden this, unsigned __int16 *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005994`

## callees

- `0x18000a778`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!_wcsicmp` at `0x18000a7a1`
- `api-ms-win-core-crt-l1-1-0!_wcsicmp` at `0x18000a7a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7cd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a7bf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a7bf`

## string_xrefs

- `0x18000a794`: `rpcrt4.dll`

## pseudocode

```c
DLL *__fastcall DLL::DLL(DLL *this, unsigned __int16 *a2, __int64 a3, int *a4)
{
  HMODULE Library; // rax
  DWORD LastError; // eax
  __int64 v9; // rdx
  _DWORD v11[10]; // [rsp+20h] [rbp-28h]

  *a4 = 0;
  if ( _wcsicmp(a2, L"rpcrt4.dll") )
  {
    Library = LoadLibraryExW(a2, 0, 0x800u);
    *(_QWORD *)this = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      v11[1] = 1450;
      v11[0] = 14;
      v9 = 0;
      v11[2] = 8;
      v11[3] = 1453;
      v11[4] = 1455;
      v11[5] = 1816;
      while ( v11[v9] != LastError )
      {
        v9 = (unsigned int)(v9 + 1);
        if ( (unsigned int)v9 >= 6 )
        {
          if ( LastError != 1114 )
          {
            *a4 = 87;
            return this;
          }
          break;
        }
      }
      *a4 = 14;
    }
  }
  else
  {
    *(_QWORD *)this = 0;
  }
  return this;
}

```

## disassembly

```asm
0x18000a778  mov     [rsp+arg_0], rbx
0x18000a77d  mov     [rsp+arg_8], rsi
0x18000a782  push    rdi
0x18000a783  sub     rsp, 40h
0x18000a787  mov     rsi, rdx
0x18000a78a  mov     dword ptr [r9], 0
0x18000a791  mov     rbx, rcx
0x18000a794  lea     rdx, aRpcrt4Dll_0; "rpcrt4.dll"
0x18000a79b  mov     rcx, rsi; String1
0x18000a79e  mov     rdi, r9
0x18000a7a1  call    cs:__imp__wcsicmp
0x18000a7a7  test    eax, eax
0x18000a7a9  jnz     short loc_18000A7B4
0x18000a7ab  mov     qword ptr [rbx], 0
0x18000a7b2  jmp     short loc_18000A827
0x18000a7b4  xor     edx, edx; hFile
0x18000a7b6  mov     r8d, 800h; dwFlags
0x18000a7bc  mov     rcx, rsi; lpLibFileName
0x18000a7bf  call    cs:__imp_LoadLibraryExW
0x18000a7c5  mov     [rbx], rax
0x18000a7c8  test    rax, rax
0x18000a7cb  jnz     short loc_18000A827
0x18000a7cd  call    cs:__imp_GetLastError
0x18000a7d3  mov     r8d, 0Eh
0x18000a7d9  mov     [rsp+48h+var_24], 5AAh
0x18000a7e1  mov     [rsp+48h+var_28], r8d
0x18000a7e6  xor     edx, edx
0x18000a7e8  mov     [rsp+48h+var_20], 8
0x18000a7f0  mov     [rsp+48h+var_1C], 5ADh
0x18000a7f8  mov     [rsp+48h+var_18], 5AFh
0x18000a800  mov     [rsp+48h+var_14], 718h
0x18000a808  cmp     [rsp+rdx*4+48h+var_28], eax
0x18000a80c  jz      short loc_18000A824
0x18000a80e  inc     edx
0x18000a810  cmp     edx, 6
0x18000a813  jb      short loc_18000A808
0x18000a815  cmp     eax, 45Ah
0x18000a81a  jz      short loc_18000A824
0x18000a81c  mov     dword ptr [rdi], 57h ; 'W'
0x18000a822  jmp     short loc_18000A827
0x18000a824  mov     [rdi], r8d
0x18000a827  mov     rsi, [rsp+48h+arg_8]
0x18000a82c  mov     rax, rbx
0x18000a82f  mov     rbx, [rsp+48h+arg_0]
0x18000a834  add     rsp, 40h
0x18000a838  pop     rdi
0x18000a839  retn
```
