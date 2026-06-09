# DeleteAccessPath_DeletePath

- ea: `0x14001d1e4`
- end: `0x14001d2c9`
- name: `DeleteAccessPath_DeletePath`
- size: `229`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x14001d190`

## callees

- `0x140008190`
- `0x14001d1e4`

## import_xrefs

- `KERNEL32!DeleteVolumeMountPointW` at `0x14001d201`
- `KERNEL32!DeleteVolumeMountPointW` at `0x14001d201`
- `KERNEL32!DefineDosDeviceW` at `0x14001d29b`
- `KERNEL32!DefineDosDeviceW` at `0x14001d29b`
- `KERNEL32!HeapAlloc` at `0x14001d221`
- `KERNEL32!HeapAlloc` at `0x14001d221`
- `KERNEL32!HeapFree` at `0x14001d2b3`
- `KERNEL32!HeapFree` at `0x14001d2b3`
- `KERNEL32!GetProcessHeap` at `0x14001d1f5`
- `KERNEL32!GetProcessHeap` at `0x14001d1f5`
- `KERNEL32!SetLastError` at `0x14001d232`
- `KERNEL32!SetLastError` at `0x14001d242`
- `KERNEL32!SetLastError` at `0x14001d27a`
- `KERNEL32!SetLastError` at `0x14001d232`
- `KERNEL32!SetLastError` at `0x14001d242`
- `KERNEL32!SetLastError` at `0x14001d27a`
- `KERNEL32!GetLastError` at `0x14001d20d`
- `KERNEL32!GetLastError` at `0x14001d238`
- `KERNEL32!GetLastError` at `0x14001d2a3`
- `KERNEL32!GetLastError` at `0x14001d20d`
- `KERNEL32!GetLastError` at `0x14001d238`
- `KERNEL32!GetLastError` at `0x14001d2a3`

## pseudocode

```c
__int64 __fastcall DeleteAccessPath_DeletePath(unsigned __int16 *a1, unsigned __int64 a2)
{
  HANDLE ProcessHeap; // r14
  unsigned int v5; // ebx
  unsigned __int16 *v6; // rax
  WCHAR *v7; // rsi
  DWORD LastError; // edi
  int v10; // eax
  DWORD v11; // ecx
  BOOL v12; // eax

  ProcessHeap = GetProcessHeap();
  v5 = DeleteVolumeMountPointW(a1);
  if ( v5 || GetLastError() != 87 )
    goto LABEL_5;
  v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 2 * a2);
  v7 = v6;
  if ( !v6 )
  {
    SetLastError(8u);
LABEL_5:
    LastError = GetLastError();
    goto LABEL_6;
  }
  v10 = StringCchCopyW(v6, a2, a1);
  v11 = v10;
  if ( v10 >= 0 )
  {
    if ( v7[a2 - 2] == 92 )
      v7[a2 - 2] = 0;
    v5 = DefineDosDeviceW(2u, v7, 0);
  }
  else
  {
    v5 = 0;
    if ( (v10 & 0x1FFF0000) == 0x70000 )
      v11 = (unsigned __int16)v10;
    SetLastError(v11);
  }
  LastError = GetLastError();
  v12 = HeapFree(ProcessHeap, 0, v7);
  if ( v5 )
  {
    v5 = v12;
    LastError = 6;
  }
LABEL_6:
  SetLastError(LastError);
  return v5;
}

```

## disassembly

```asm
0x14001d1e4  push    rbx
0x14001d1e6  push    rbp
0x14001d1e7  push    rsi
0x14001d1e8  push    rdi
0x14001d1e9  push    r14
0x14001d1eb  sub     rsp, 20h
0x14001d1ef  mov     rdi, rdx
0x14001d1f2  mov     rbp, rcx
0x14001d1f5  call    cs:__imp_GetProcessHeap
0x14001d1fb  mov     rcx, rbp; lpszVolumeMountPoint
0x14001d1fe  mov     r14, rax
0x14001d201  call    cs:__imp_DeleteVolumeMountPointW
0x14001d207  mov     ebx, eax
0x14001d209  test    eax, eax
0x14001d20b  jnz     short loc_14001D238
0x14001d20d  call    cs:__imp_GetLastError
0x14001d213  cmp     eax, 57h ; 'W'
0x14001d216  jnz     short loc_14001D238
0x14001d218  lea     r8, [rdi+rdi]; dwBytes
0x14001d21c  xor     edx, edx; dwFlags
0x14001d21e  mov     rcx, r14; hHeap
0x14001d221  call    cs:__imp_HeapAlloc
0x14001d227  mov     rsi, rax
0x14001d22a  test    rax, rax
0x14001d22d  jnz     short loc_14001D255
0x14001d22f  lea     ecx, [rbx+8]; dwErrCode
0x14001d232  call    cs:__imp_SetLastError
0x14001d238  call    cs:__imp_GetLastError
0x14001d23e  mov     edi, eax
0x14001d240  mov     ecx, edi; dwErrCode
0x14001d242  call    cs:__imp_SetLastError
0x14001d248  mov     eax, ebx
0x14001d24a  add     rsp, 20h
0x14001d24e  pop     r14
0x14001d250  pop     rdi
0x14001d251  pop     rsi
0x14001d252  pop     rbp
0x14001d253  pop     rbx
0x14001d254  retn
0x14001d255  mov     r8, rbp; unsigned __int16 *
0x14001d258  mov     rdx, rdi; unsigned __int64
0x14001d25b  mov     rcx, rsi; unsigned __int16 *
0x14001d25e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001d263  mov     ecx, eax
0x14001d265  test    eax, eax
0x14001d267  jns     short loc_14001D282
0x14001d269  xor     ebx, ebx
0x14001d26b  and     eax, 1FFF0000h
0x14001d270  cmp     eax, 70000h
0x14001d275  jnz     short loc_14001D27A
0x14001d277  movzx   ecx, cx; dwErrCode
0x14001d27a  call    cs:__imp_SetLastError
0x14001d280  jmp     short loc_14001D2A3
0x14001d282  cmp     word ptr [rsi+rdi*2-4], 5Ch ; '\'
0x14001d288  jnz     short loc_14001D291
0x14001d28a  xor     eax, eax
0x14001d28c  mov     [rsi+rdi*2-4], ax
0x14001d291  xor     r8d, r8d; lpTargetPath
0x14001d294  mov     rdx, rsi; lpDeviceName
0x14001d297  lea     ecx, [r8+2]; dwFlags
0x14001d29b  call    cs:__imp_DefineDosDeviceW
0x14001d2a1  mov     ebx, eax
0x14001d2a3  call    cs:__imp_GetLastError
0x14001d2a9  mov     r8, rsi; lpMem
0x14001d2ac  xor     edx, edx; dwFlags
0x14001d2ae  mov     rcx, r14; hHeap
0x14001d2b1  mov     edi, eax
0x14001d2b3  call    cs:__imp_HeapFree
0x14001d2b9  test    ebx, ebx
0x14001d2bb  jz      short loc_14001D240
0x14001d2bd  mov     ebx, eax
0x14001d2bf  mov     edi, 6
0x14001d2c4  jmp     loc_14001D240
```
