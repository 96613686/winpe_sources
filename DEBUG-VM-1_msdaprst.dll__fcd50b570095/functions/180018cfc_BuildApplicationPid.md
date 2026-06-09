# BuildApplicationPid

- ea: `0x180018cfc`
- end: `0x180018df1`
- name: `BuildApplicationPid`
- size: `245`
- prototype: `__int64 __fastcall(LPWSTR lpFilename)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180019808`
- `0x18001a394`

## callees

- `0x180018cfc`
- `0x180019504`

## import_xrefs

- `msvcrt!_ultow_s` at `0x180018d8e`
- `msvcrt!_ultow_s` at `0x180018d8e`
- `KERNEL32!GetCurrentProcessId` at `0x180018d76`
- `KERNEL32!GetCurrentProcessId` at `0x180018d76`
- `KERNEL32!GetModuleFileNameW` at `0x180018d2f`
- `KERNEL32!GetModuleFileNameW` at `0x180018d2f`

## pseudocode

```c
__int64 __fastcall BuildApplicationPid(LPWSTR lpFilename, __int64 a2, __int64 *a3, _QWORD *a4)
{
  DWORD ModuleFileNameW; // eax
  const unsigned __int16 *v8; // r8
  wchar_t *v9; // rsi
  DWORD CurrentProcessId; // eax
  unsigned int v11; // edx
  wchar_t *v12; // rcx
  wchar_t *v13; // rax
  unsigned int v15; // [rsp+28h] [rbp-20h]
  size_t BufferCount; // [rsp+50h] [rbp+8h] BYREF
  wchar_t *Buffer; // [rsp+60h] [rbp+18h] BYREF

  *lpFilename = 0;
  *a3 = 0;
  *a4 = 0;
  ModuleFileNameW = GetModuleFileNameW(0, lpFilename, 0x112u);
  if ( ModuleFileNameW - 1 > 0x110
    || (*a4 = ModuleFileNameW,
        BufferCount = 274 - ModuleFileNameW,
        v9 = &lpFilename[ModuleFileNameW],
        Buffer = v9,
        (int)StringCchCopyExW(v9, BufferCount, v8, &Buffer, &BufferCount, v15) < 0)
    || (CurrentProcessId = GetCurrentProcessId(), _ultow_s(CurrentProcessId, Buffer, BufferCount, 10)) )
  {
    v11 = 0;
    *lpFilename = 0;
    *a3 = 0;
    *a4 = 0;
  }
  else
  {
    v11 = 1;
    v12 = v9;
    while ( 1 )
    {
      v13 = v12--;
      if ( v12 < lpFilename )
        break;
      if ( *v12 == 92 || *v12 == 47 )
      {
        if ( v13 >= v9 )
          *a3 = 0;
        else
          *a3 = v13 - lpFilename;
        return v11;
      }
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180018cfc  mov     [rsp+arg_8], rbx
0x180018d01  mov     [rsp+arg_18], rbp
0x180018d06  push    rsi
0x180018d07  push    rdi
0x180018d08  push    r14
0x180018d0a  sub     rsp, 30h
0x180018d0e  xor     eax, eax
0x180018d10  mov     rdi, r8
0x180018d13  mov     [rcx], ax
0x180018d16  mov     rbx, rcx
0x180018d19  mov     [r8], rax
0x180018d1c  mov     rdx, rcx; lpFilename
0x180018d1f  mov     ebp, 112h
0x180018d24  mov     [r9], rax
0x180018d27  mov     r8d, ebp; nSize
0x180018d2a  xor     ecx, ecx; hModule
0x180018d2c  mov     r14, r9
0x180018d2f  call    cs:__imp_GetModuleFileNameW
0x180018d35  lea     edx, [rax-1]
0x180018d38  cmp     edx, 110h
0x180018d3e  ja      loc_180018DCF
0x180018d44  mov     ecx, eax
0x180018d46  lea     r9, [rsp+48h+Buffer]; unsigned __int16 **
0x180018d4b  sub     ebp, eax
0x180018d4d  mov     [r14], rcx
0x180018d50  mov     edx, ebp; unsigned __int64
0x180018d52  lea     rax, [rsp+48h+BufferCount]
0x180018d57  mov     [rsp+48h+BufferCount], rdx
0x180018d5c  lea     rsi, [rbx+rcx*2]
0x180018d60  mov     [rsp+48h+var_28], rax; unsigned __int64 *
0x180018d65  mov     rcx, rsi; unsigned __int16 *
0x180018d68  mov     [rsp+48h+Buffer], rsi
0x180018d6d  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180018d72  test    eax, eax
0x180018d74  js      short loc_180018DCF
0x180018d76  call    cs:__imp_GetCurrentProcessId
0x180018d7c  mov     r8, [rsp+48h+BufferCount]; BufferCount
0x180018d81  mov     r9d, 0Ah; Radix
0x180018d87  mov     rdx, [rsp+48h+Buffer]; Buffer
0x180018d8c  mov     ecx, eax; Value
0x180018d8e  call    cs:__imp__ultow_s
0x180018d94  test    eax, eax
0x180018d96  jnz     short loc_180018DCF
0x180018d98  lea     edx, [rax+1]
0x180018d9b  mov     rcx, rsi
0x180018d9e  mov     rax, rcx
0x180018da1  sub     rcx, 2
0x180018da5  cmp     rcx, rbx
0x180018da8  jb      short loc_180018DDC
0x180018daa  cmp     word ptr [rcx], 5Ch ; '\'
0x180018dae  jz      short loc_180018DB6
0x180018db0  cmp     word ptr [rcx], 2Fh ; '/'
0x180018db4  jnz     short loc_180018D9E
0x180018db6  cmp     rax, rsi
0x180018db9  jnb     short loc_180018DC6
0x180018dbb  sub     rax, rbx
0x180018dbe  sar     rax, 1
0x180018dc1  mov     [rdi], rax
0x180018dc4  jmp     short loc_180018DDC
0x180018dc6  mov     qword ptr [rdi], 0
0x180018dcd  jmp     short loc_180018DDC
0x180018dcf  xor     edx, edx
0x180018dd1  xor     ecx, ecx
0x180018dd3  mov     [rbx], cx
0x180018dd6  mov     [rdi], rcx
0x180018dd9  mov     [r14], rcx
0x180018ddc  mov     rbx, [rsp+48h+arg_8]
0x180018de1  mov     eax, edx
0x180018de3  mov     rbp, [rsp+48h+arg_18]
0x180018de8  add     rsp, 30h
0x180018dec  pop     r14
0x180018dee  pop     rdi
0x180018def  pop     rsi
0x180018df0  retn
```
