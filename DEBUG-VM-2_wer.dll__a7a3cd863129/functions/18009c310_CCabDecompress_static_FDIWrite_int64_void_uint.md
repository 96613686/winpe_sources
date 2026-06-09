# CCabDecompress::static_FDIWrite(__int64,void *,uint)

- ea: `0x18009c310`
- end: `0x18009c40d`
- name: `?static_FDIWrite@CCabDecompress@@KAI_JPEAXI@Z`
- size: `253`
- prototype: `UINT __cdecl(INT_PTR hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18001fe24`
- `0x18009c310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c398`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c398`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009c34f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009c34f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18009c375`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18009c375`

## pseudocode

```c
__int64 __fastcall CCabDecompress::static_FDIWrite(INT_PTR hf, void *pv, UINT cb)
{
  HANDLE *v6; // rcx
  DWORD LastError; // eax
  unsigned int v8; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  if ( hf && pv )
  {
    v6 = *(HANDLE **)hf;
    if ( !v6 || WaitForSingleObject(*v6, 0) )
    {
      if ( WriteFile(*(HANDLE *)(hf + 8), pv, cb, &NumberOfBytesWritten, 0) )
        return NumberOfBytesWritten;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        LastError = GetLastError();
        v8 = ERROR_HR_FROM_WIN32(LastError);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids, v8);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18009c310  mov     [rsp+arg_8], rbx
0x18009c315  mov     [rsp+arg_10], rsi
0x18009c31a  push    rdi
0x18009c31b  sub     rsp, 30h
0x18009c31f  mov     [rsp+38h+NumberOfBytesWritten], 0
0x18009c327  mov     esi, r8d
0x18009c32a  mov     rdi, rdx
0x18009c32d  mov     rbx, rcx
0x18009c330  test    rcx, rcx
0x18009c333  jz      loc_18009C3CC
0x18009c339  test    rdx, rdx
0x18009c33c  jz      loc_18009C3CC
0x18009c342  mov     rcx, [rcx]
0x18009c345  test    rcx, rcx
0x18009c348  jz      short loc_18009C35D
0x18009c34a  mov     rcx, [rcx]; hHandle
0x18009c34d  xor     edx, edx; dwMilliseconds
0x18009c34f  call    cs:__imp_WaitForSingleObject
0x18009c355  test    eax, eax
0x18009c357  jz      loc_18009C3FA
0x18009c35d  mov     rcx, [rbx+8]; hFile
0x18009c361  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18009c366  mov     r8d, esi; nNumberOfBytesToWrite
0x18009c369  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18009c372  mov     rdx, rdi; lpBuffer
0x18009c375  call    cs:__imp_WriteFile
0x18009c37b  test    eax, eax
0x18009c37d  jnz     short loc_18009C3C6
0x18009c37f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c386  lea     rax, WPP_GLOBAL_Control
0x18009c38d  cmp     rcx, rax
0x18009c390  jz      short loc_18009C3FA
0x18009c392  test    byte ptr [rcx+1Ch], 1
0x18009c396  jz      short loc_18009C3FA
0x18009c398  call    cs:__imp_GetLastError
0x18009c39e  mov     ecx, eax; unsigned int
0x18009c3a0  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009c3a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c3ac  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009c3b3  mov     edx, 3Ch ; '<'
0x18009c3b8  mov     r9d, eax
0x18009c3bb  mov     rcx, [rcx+10h]
0x18009c3bf  call    WPP_SF_d
0x18009c3c4  jmp     short loc_18009C3FA
0x18009c3c6  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x18009c3ca  jmp     short loc_18009C3FD
0x18009c3cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c3d3  lea     rax, WPP_GLOBAL_Control
0x18009c3da  cmp     rcx, rax
0x18009c3dd  jz      short loc_18009C3FA
0x18009c3df  test    byte ptr [rcx+1Ch], 1
0x18009c3e3  jz      short loc_18009C3FA
0x18009c3e5  mov     rcx, [rcx+10h]
0x18009c3e9  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009c3f0  mov     edx, 3Bh ; ';'
0x18009c3f5  call    WPP_SF_
0x18009c3fa  or      eax, 0FFFFFFFFh
0x18009c3fd  mov     rbx, [rsp+38h+arg_8]
0x18009c402  mov     rsi, [rsp+38h+arg_10]
0x18009c407  add     rsp, 30h
0x18009c40b  pop     rdi
0x18009c40c  retn
```
